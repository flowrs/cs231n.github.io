# Lecture 11: Large-Scale Distributed Training

## GPU Hardware Basics

```
    NVIDIA H100 GPU ARCHITECTURE:

    ┌─────────────────────────────────────────────────────────────────┐
    │                       NVIDIA H100 GPU                           │
    │                                                                 │
    │   ┌─────────────────────────────────────────────────────────┐   │
    │   │                  Streaming Multiprocessors               │   │
    │   │   ┌──┬──┬──┬──┬──┬──┬──┬──┬──┬──┬──┬──┬──┬──┬──┬──┐    │   │
    │   │   │SM│SM│SM│SM│SM│SM│SM│SM│SM│SM│SM│SM│SM│SM│SM│SM│    │   │
    │   │   └──┴──┴──┴──┴──┴──┴──┴──┴──┴──┴──┴──┴──┴──┴──┴──┘    │   │
    │   │   × 132 SMs                                             │   │
    │   │   = 16,896 FP32 CUDA cores                              │   │
    │   │   = 528 Tensor cores                                    │   │
    │   └─────────────────────────────────────────────────────────┘   │
    │                                                                 │
    │   ┌─────────────────────────────────────────────────────────┐   │
    │   │                     HBM3 Memory                          │   │
    │   │   80 GB capacity                                        │   │
    │   │   3.35 TB/sec bandwidth (inside GPU)                    │   │
    │   └─────────────────────────────────────────────────────────┘   │
    │                                                                 │
    │   Peak: ~4 PFLOPS (FP8), ~2 PFLOPS (FP16), ~60 TFLOPS (FP32)   │
    └─────────────────────────────────────────────────────────────────┘


    GPU SERVER (8× GPU):

    ┌───────────────────────────────────────────────────────────────────┐
    │   ┌─────┐  ┌─────┐  ┌─────┐  ┌─────┐  ┌─────┐  ┌─────┐  ┌─────┐  ┌─────┐ │
    │   │GPU 0│  │GPU 1│  │GPU 2│  │GPU 3│  │GPU 4│  │GPU 5│  │GPU 6│  │GPU 7│ │
    │   └──┬──┘  └──┬──┘  └──┬──┘  └──┬──┘  └──┬──┘  └──┬──┘  └──┬──┘  └──┬──┘ │
    │      │       │       │       │       │       │       │       │      │
    │      └───────┴───────┴───────┴───────┴───────┴───────┴───────┘      │
    │                       NVLink/NVSwitch                               │
    │                    900 GB/sec between GPUs                          │
    └─────────────────────────────────────────────────────────────────────┘
```

## GPU Evolution and Scaling

```
    GPU PERFORMANCE GROWTH:

    Year    GPU         FP16 TFLOPS    Memory
    ────────────────────────────────────────────
    2016    P100        22             16 GB
    2017    V100        125            32 GB
    2020    A100        312            80 GB
    2023    H100        1979           80 GB

    ~100× improvement in 7 years!

    MEMORY BANDWIDTH HIERARCHY:

    ┌────────────────────────────────────────────────────────────┐
    │                                                            │
    │   Inside GPU (HBM)           3,350 GB/s                   │
    │          │                                                │
    │          ▼                                                │
    │   Between GPUs (NVLink)        900 GB/s                   │
    │          │                                                │
    │          ▼                                                │
    │   Between Nodes (InfiniBand)   400 GB/s                   │
    │          │                                                │
    │          ▼                                                │
    │   Ethernet                       25 GB/s                   │
    │                                                            │
    └────────────────────────────────────────────────────────────┘

    Key insight: Communication becomes bottleneck at scale!
```

## Parallelism Strategies Overview

```
    ┌─────────────────────────────────────────────────────────────────┐
    │               DISTRIBUTED TRAINING STRATEGIES                   │
    ├─────────────────────────────────────────────────────────────────┤
    │                                                                 │
    │   ┌───────────────────────┐   ┌───────────────────────┐         │
    │   │   DATA PARALLELISM    │   │   MODEL PARALLELISM   │         │
    │   │   (DP)                │   │   (split model)       │         │
    │   │                       │   │                       │         │
    │   │   Same model on       │   │   ┌─────────────────┐│         │
    │   │   each GPU,           │   │   │  TENSOR (TP)    ││         │
    │   │   different data      │   │   │  Split layers   ││         │
    │   │                       │   │   └─────────────────┘│         │
    │   │                       │   │   ┌─────────────────┐│         │
    │   │                       │   │   │  PIPELINE (PP)  ││         │
    │   │                       │   │   │  Split stages   ││         │
    │   │                       │   │   └─────────────────┘│         │
    │   └───────────────────────┘   └───────────────────────┘         │
    │                                                                 │
    │   ┌───────────────────────┐   ┌───────────────────────┐         │
    │   │   CONTEXT PARALLEL    │   │   FSDP / ZeRO         │         │
    │   │   (CP)                │   │   (Sharded DP)        │         │
    │   │   Split sequence      │   │   Shard weights,      │         │
    │   │   across GPUs         │   │   grads, optimizer    │         │
    │   └───────────────────────┘   └───────────────────────┘         │
    └─────────────────────────────────────────────────────────────────┘
```

## Data Parallelism (DP)

```
    BASIC DATA PARALLELISM:

    ┌─────────────────────────────────────────────────────────────────┐
    │                                                                 │
    │   Global Batch (e.g., 256)                                      │
    │   ┌─────────────────────────────────────────────────────────┐   │
    │   │  batch 0-63  │ batch 64-127 │ batch 128-191 │ batch 192-255│   │
    │   └──────┬───────┴──────┬───────┴──────┬────────┴──────┬─────┘   │
    │          │              │              │               │         │
    │          ▼              ▼              ▼               ▼         │
    │      ┌───────┐      ┌───────┐      ┌───────┐      ┌───────┐     │
    │      │ GPU 0 │      │ GPU 1 │      │ GPU 2 │      │ GPU 3 │     │
    │      │Model W│      │Model W│      │Model W│      │Model W│     │
    │      │ copy  │      │ copy  │      │ copy  │      │ copy  │     │
    │      └───┬───┘      └───┬───┘      └───┬───┘      └───┬───┘     │
    │          │              │              │               │         │
    │          │   Forward    │              │               │         │
    │          │   Backward   │              │               │         │
    │          ▼              ▼              ▼               ▼         │
    │        ∇W₀            ∇W₁            ∇W₂             ∇W₃         │
    │          │              │              │               │         │
    │          └──────────────┴──────────────┴───────────────┘         │
    │                              │                                   │
    │                         AllReduce                                │
    │                        (average ∇W)                              │
    │                              │                                   │
    │                              ▼                                   │
    │                    All GPUs update W                             │
    └─────────────────────────────────────────────────────────────────┘

    ALLREDUCE OPERATION:

    Before:  GPU0:[∇W₀]  GPU1:[∇W₁]  GPU2:[∇W₂]  GPU3:[∇W₃]
                 │          │          │          │
                 └──────────┴──────────┴──────────┘
                            AllReduce
                              │
    After:   GPU0:[∇W_avg] GPU1:[∇W_avg] GPU2:[∇W_avg] GPU3:[∇W_avg]

    where ∇W_avg = (∇W₀ + ∇W₁ + ∇W₂ + ∇W₃) / 4
```

## Ring AllReduce

```
    EFFICIENT GRADIENT SYNCHRONIZATION:

    ┌─────────────────────────────────────────────────────────────────┐
    │   RING ALLREDUCE (N GPUs, N-1 steps each direction)            │
    │                                                                 │
    │   Step 1-3: Reduce-Scatter                                      │
    │                                                                 │
    │       GPU 0 ──────► GPU 1 ──────► GPU 2 ──────► GPU 3          │
    │         ▲                                         │             │
    │         └─────────────────────────────────────────┘             │
    │                                                                 │
    │   Each GPU sends one chunk, receives and accumulates another   │
    │   After N-1 steps: each GPU has sum of one chunk               │
    │                                                                 │
    │   Step 4-6: All-Gather                                          │
    │                                                                 │
    │   Each GPU broadcasts its complete chunk around the ring       │
    │   After N-1 steps: all GPUs have complete sum                  │
    │                                                                 │
    └─────────────────────────────────────────────────────────────────┘

    BANDWIDTH EFFICIENCY:

    Naive AllReduce: O(N × model_size)
    Ring AllReduce:  O(model_size) regardless of N GPUs

    Critical for scaling to thousands of GPUs!
```

## Fully Sharded Data Parallelism (FSDP / ZeRO)

```
    PROBLEM: Model doesn't fit on single GPU

    Memory per GPU = Weights + Gradients + Optimizer states
                   =   W    +     W      +      2W (Adam)
                   = 4W total per GPU

    FSDP SOLUTION: Shard everything across GPUs

    ┌─────────────────────────────────────────────────────────────────┐
    │   STANDARD DATA PARALLEL:                                       │
    │                                                                 │
    │   GPU 0: [W₀ W₁ W₂ W₃] + [∇W₀ ∇W₁ ∇W₂ ∇W₃] + [Opt states]     │
    │   GPU 1: [W₀ W₁ W₂ W₃] + [∇W₀ ∇W₁ ∇W₂ ∇W₃] + [Opt states]     │
    │   GPU 2: [W₀ W₁ W₂ W₃] + [∇W₀ ∇W₁ ∇W₂ ∇W₃] + [Opt states]     │
    │   GPU 3: [W₀ W₁ W₂ W₃] + [∇W₀ ∇W₁ ∇W₂ ∇W₃] + [Opt states]     │
    │                                                                 │
    │   Total memory = 4 × (4W) = 16W                                 │
    ├─────────────────────────────────────────────────────────────────┤
    │   FSDP (ZeRO-3):                                                │
    │                                                                 │
    │   GPU 0: [W₀] + [∇W₀] + [Opt₀]  ← only 1/4 of everything       │
    │   GPU 1: [W₁] + [∇W₁] + [Opt₁]                                 │
    │   GPU 2: [W₂] + [∇W₂] + [Opt₂]                                 │
    │   GPU 3: [W₃] + [∇W₃] + [Opt₃]                                 │
    │                                                                 │
    │   Total memory = 4 × (W) = 4W (4× reduction!)                  │
    └─────────────────────────────────────────────────────────────────┘

    FSDP WORKFLOW:

    Forward pass:
    1. AllGather weights (reconstruct full layer)
    2. Compute forward
    3. Discard gathered weights (keep only shard)

    Backward pass:
    1. AllGather weights
    2. Compute backward
    3. ReduceScatter gradients (each GPU keeps its shard)
    4. Discard gathered weights
```

## Pipeline Parallelism (PP)

```
    SPLIT MODEL INTO STAGES ACROSS GPUs:

    ┌─────────────────────────────────────────────────────────────────┐
    │   Model: 24 transformer layers → 4 stages × 6 layers           │
    │                                                                 │
    │   GPU 0: Layers 0-5    (Stage 0)                               │
    │   GPU 1: Layers 6-11   (Stage 1)                               │
    │   GPU 2: Layers 12-17  (Stage 2)                               │
    │   GPU 3: Layers 18-23  (Stage 3)                               │
    │                                                                 │
    │   NAIVE PIPELINE (poor utilization):                           │
    │                                                                 │
    │   Time →                                                        │
    │   GPU 0: [F0]                    [B0]                           │
    │   GPU 1:      [F1]          [B1]                                │
    │   GPU 2:           [F2][B2]                                     │
    │   GPU 3:                [F3][B3]                                │
    │                                                                 │
    │   "Bubble" = idle time waiting for previous stage              │
    ├─────────────────────────────────────────────────────────────────┤
    │   MICRO-BATCHING (reduce bubble):                              │
    │                                                                 │
    │   Split batch into micro-batches, pipeline them:               │
    │                                                                 │
    │   GPU 0: [F0.1][F0.2][F0.3][F0.4]    [B0.4][B0.3][B0.2][B0.1]  │
    │   GPU 1:      [F1.1][F1.2][F1.3][F1.4][B1.4][B1.3][B1.2][B1.1] │
    │   GPU 2:           [F2.1][F2.2][F2.3][F2.4][B2.4][B2.3][B2.2]  │
    │   GPU 3:                [F3.1][F3.2][F3.3][F3.4][B3.4][B3.3]   │
    │                                                                 │
    │   More micro-batches → smaller bubble ratio                    │
    └─────────────────────────────────────────────────────────────────┘
```

## Tensor Parallelism (TP)

```
    SPLIT INDIVIDUAL LAYERS ACROSS GPUs:

    ┌─────────────────────────────────────────────────────────────────┐
    │   COLUMN-WISE SPLIT (Linear layer):                            │
    │                                                                 │
    │   Y = XW    where W is [d_in × d_out]                          │
    │                                                                 │
    │   Split W columns:  W = [W₀ | W₁]                              │
    │                                                                 │
    │   GPU 0:  Y₀ = X × W₀                                          │
    │   GPU 1:  Y₁ = X × W₁                                          │
    │                                                                 │
    │   Y = [Y₀ | Y₁]  (concatenate outputs)                         │
    ├─────────────────────────────────────────────────────────────────┤
    │   TRANSFORMER ATTENTION with TP:                               │
    │                                                                 │
    │          X                                                      │
    │          │                                                      │
    │    ┌─────┴─────┐                                                │
    │    │           │                                                │
    │    ▼           ▼                                                │
    │  [Q₀,K₀,V₀]  [Q₁,K₁,V₁]   ← Split heads across GPUs            │
    │    │           │                                                │
    │    ▼           ▼                                                │
    │  Attn₀       Attn₁         ← Each GPU computes its heads       │
    │    │           │                                                │
    │    └─────┬─────┘                                                │
    │          │ AllReduce                                            │
    │          ▼                                                      │
    │        Output                                                   │
    └─────────────────────────────────────────────────────────────────┘

    TP requires high bandwidth → use within node (NVLink)
```

## Combining Parallelism Strategies

```
    3D PARALLELISM FOR LARGE MODELS:

    ┌─────────────────────────────────────────────────────────────────┐
    │                                                                 │
    │   Cluster: 256 GPUs (32 nodes × 8 GPUs/node)                   │
    │                                                                 │
    │   ┌─────────────────────────────────────────────────────────┐   │
    │   │ Node 0 (TP)   Node 1 (TP)   Node 2 (TP)   Node 3 (TP)  │   │
    │   │ [8 GPUs]      [8 GPUs]      [8 GPUs]      [8 GPUs]     │   │
    │   │ Stage 0       Stage 1       Stage 2       Stage 3      │   │
    │   │              (Pipeline Parallelism)                     │   │
    │   └─────────────────────────────────────────────────────────┘   │
    │   └─────────────────────────────────────────────────────────┘   │
    │   └─────────────────────────────────────────────────────────┘   │
    │   └─────────────────────────────────────────────────────────┘   │
    │         ↑                                                       │
    │         └──── Data Parallelism (8 replicas)                    │
    │                                                                 │
    │   TP = 8 (within node, NVLink)                                 │
    │   PP = 4 (across nodes, slower network OK)                     │
    │   DP = 8 (across groups)                                       │
    │   Total = 8 × 4 × 8 = 256 GPUs                                 │
    └─────────────────────────────────────────────────────────────────┘
```

## Mixed Precision Training

```
    FP32 vs FP16/BF16:

    ┌─────────────────────────────────────────────────────────────────┐
    │   FP32: 1 sign + 8 exp + 23 mantissa = 32 bits                 │
    │   FP16: 1 sign + 5 exp + 10 mantissa = 16 bits                 │
    │   BF16: 1 sign + 8 exp + 7 mantissa  = 16 bits                 │
    │                                                                 │
    │   BF16 = same range as FP32, less precision                    │
    │   FP16 = more precision, smaller range (overflow risk)         │
    └─────────────────────────────────────────────────────────────────┘

    MIXED PRECISION TRAINING:

    ┌─────────────────────────────────────────────────────────────────┐
    │   Master weights: FP32 (for accurate updates)                  │
    │   Forward/Backward: FP16/BF16 (for speed)                      │
    │   Gradients: FP16/BF16 → cast to FP32 for update              │
    │                                                                 │
    │   Benefits:                                                     │
    │   - 2× memory reduction                                        │
    │   - 2-4× compute speedup (tensor cores)                        │
    │   - Same accuracy as FP32 training                             │
    └─────────────────────────────────────────────────────────────────┘
```

## Key Takeaways

```
┌────────────────────────────────────────────────────────────────────┐
│ 1. Modern training requires distributed computing across GPUs      │
│                                                                    │
│ 2. Parallelism strategies:                                         │
│    - Data Parallel: same model, different data (scales easily)    │
│    - Tensor Parallel: split layers (high bandwidth needed)        │
│    - Pipeline Parallel: split stages (handles bubble overhead)    │
│    - FSDP/ZeRO: shard weights, grads, optimizer (memory efficient)│
│                                                                    │
│ 3. Communication is the bottleneck:                               │
│    - Ring AllReduce for bandwidth-efficient gradient sync         │
│    - TP within node (fast NVLink), PP across nodes               │
│                                                                    │
│ 4. 3D parallelism combines DP + TP + PP for trillion-param models │
│                                                                    │
│ 5. Mixed precision (FP16/BF16) gives 2× memory + compute savings  │
│                                                                    │
│ 6. Key insight: different parallelism strategies have different   │
│    communication patterns and bandwidth requirements              │
└────────────────────────────────────────────────────────────────────┘
```
