# Lecture 8: Attention and Transformers
## Stanford CS231n 10th Anniversary - April 24, 2025

---

## The Problem with RNNs

```
┌─────────────────────────────────────────────────────────────────┐
│              LIMITATIONS OF RECURRENT MODELS                     │
│                                                                  │
│   Sequential processing:                                         │
│   ┌───┐    ┌───┐    ┌───┐    ┌───┐    ┌───┐                    │
│   │ h₀│───►│ h₁│───►│ h₂│───►│ h₃│───►│ h₄│───► output        │
│   └───┘    └───┘    └───┘    └───┘    └───┘                    │
│     ↑        ↑        ↑        ↑        ↑                       │
│    x₀       x₁       x₂       x₃       x₄                       │
│                                                                  │
│   PROBLEMS:                                                      │
│   1. Sequential = slow (can't parallelize)                      │
│   2. Long-range dependencies are hard                           │
│   3. Vanishing/exploding gradients                              │
│   4. Information bottleneck (all info through h)                │
│                                                                  │
│   To relate x₀ to x₄, information must flow through             │
│   4 sequential steps → information gets lost!                   │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Attention: The Key Idea

```
┌─────────────────────────────────────────────────────────────────┐
│                    ATTENTION MECHANISM                           │
│                                                                  │
│   Instead of compressing everything into one vector,            │
│   let the decoder LOOK BACK at all encoder states!              │
│                                                                  │
│   ENCODER (input sequence):                                      │
│   ┌───┐    ┌───┐    ┌───┐    ┌───┐                             │
│   │ h₁│    │ h₂│    │ h₃│    │ h₄│                             │
│   └─┬─┘    └─┬─┘    └─┬─┘    └─┬─┘                             │
│     │        │        │        │                                │
│     │    ┌───┴────────┴────────┴───┐                           │
│     │    │      ATTENTION          │                           │
│     │    │  "Which h's matter      │                           │
│     │    │   for this output?"     │                           │
│     └────┤                         │                           │
│          │   weights: [0.1, 0.2, 0.6, 0.1]                     │
│          └────────────┬────────────┘                           │
│                       │                                         │
│                       ▼                                         │
│                  ┌─────────┐                                    │
│                  │ context │  = weighted sum of h's            │
│                  │  vector │                                    │
│                  └────┬────┘                                    │
│                       │                                         │
│                       ▼                                         │
│                   DECODER                                       │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

*Image: Attention mechanism (images/lecture_8/page035_img99.png)*

---

## Attention Weights Computation

```
┌─────────────────────────────────────────────────────────────────┐
│              COMPUTING ATTENTION WEIGHTS                         │
│                                                                  │
│   Input:  Query q (what we're looking for)                      │
│           Keys k₁, k₂, ..., kₙ (what we're searching)           │
│           Values v₁, v₂, ..., vₙ (what we retrieve)             │
│                                                                  │
│   Step 1: Compute alignment scores                               │
│           eᵢ = score(q, kᵢ)   (e.g., dot product)               │
│                                                                  │
│   Step 2: Normalize with softmax                                 │
│           αᵢ = softmax(eᵢ) = exp(eᵢ) / Σⱼ exp(eⱼ)              │
│                                                                  │
│   Step 3: Weighted sum of values                                 │
│           output = Σᵢ αᵢ · vᵢ                                   │
│                                                                  │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │                                                         │   │
│   │    q ──┬──► dot(q,k₁)=e₁ ─┐                            │   │
│   │        │                   │                            │   │
│   │        ├──► dot(q,k₂)=e₂ ─┼──► softmax ──► [α₁,α₂,α₃]  │   │
│   │        │                   │                            │   │
│   │        └──► dot(q,k₃)=e₃ ─┘                            │   │
│   │                                                         │   │
│   │    output = α₁·v₁ + α₂·v₂ + α₃·v₃                      │   │
│   │                                                         │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Self-Attention

```
┌─────────────────────────────────────────────────────────────────┐
│                    SELF-ATTENTION                                │
│                                                                  │
│   Key insight: Attend to YOURSELF (same sequence)               │
│   Each position can attend to ALL other positions!              │
│                                                                  │
│   INPUT: X = [x₁, x₂, x₃]                                       │
│                                                                  │
│   ┌─────┐  ┌─────┐  ┌─────┐                                     │
│   │ x₁  │  │ x₂  │  │ x₃  │                                     │
│   └──┬──┘  └──┬──┘  └──┬──┘                                     │
│      │        │        │                                        │
│      ▼        ▼        ▼                                        │
│   ┌─────┐  ┌─────┐  ┌─────┐                                     │
│   │Q₁K₁V₁│  │Q₂K₂V₂│  │Q₃K₃V₃│  Linear projections             │
│   └──┬──┘  └──┬──┘  └──┬──┘                                     │
│      │        │        │                                        │
│      └────────┼────────┘                                        │
│               ▼                                                  │
│   ┌───────────────────────────────────────┐                     │
│   │     ATTENTION MATRIX (3×3)            │                     │
│   │                                       │                     │
│   │     E = Q · Kᵀ / √d                   │                     │
│   │         ┌───────────────┐             │                     │
│   │         │ e₁₁ e₁₂ e₁₃ │             │                     │
│   │     E = │ e₂₁ e₂₂ e₂₃ │             │                     │
│   │         │ e₃₁ e₃₂ e₃₃ │             │                     │
│   │         └───────────────┘             │                     │
│   │                                       │                     │
│   │     A = softmax(E)  (row-wise)       │                     │
│   │         ┌───────────────┐             │                     │
│   │         │ a₁₁ a₁₂ a₁₃ │ (sums to 1) │                     │
│   │     A = │ a₂₁ a₂₂ a₂₃ │             │                     │
│   │         │ a₃₁ a₃₂ a₃₃ │             │                     │
│   │         └───────────────┘             │                     │
│   │                                       │                     │
│   │     Y = A · V  (weighted values)     │                     │
│   │                                       │                     │
│   └───────────────────────────────────────┘                     │
│               │                                                  │
│               ▼                                                  │
│   ┌─────┐  ┌─────┐  ┌─────┐                                     │
│   │ y₁  │  │ y₂  │  │ y₃  │   OUTPUT                           │
│   └─────┘  └─────┘  └─────┘                                     │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

*Image: Self-attention diagram (images/lecture_8/page063_img111.png)*

---

## Scaled Dot-Product Attention

```
┌─────────────────────────────────────────────────────────────────┐
│              ATTENTION FORMULA                                   │
│                                                                  │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │                                                         │   │
│   │           Attention(Q, K, V) = softmax(QKᵀ/√dₖ) · V     │   │
│   │                                                         │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   Q: Queries  [seq_len × d_k]                                   │
│   K: Keys     [seq_len × d_k]                                   │
│   V: Values   [seq_len × d_v]                                   │
│                                                                  │
│   WHY SCALE BY √dₖ?                                             │
│   - Dot products grow with dimension d                          │
│   - Large values → softmax saturates (near 0 or 1)             │
│   - Saturated softmax → vanishing gradients                    │
│   - Scaling keeps values in good range                          │
│                                                                  │
│   Example: d_k = 64                                              │
│   Scale factor = √64 = 8                                        │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Multi-Head Attention

```
┌─────────────────────────────────────────────────────────────────┐
│                  MULTI-HEAD ATTENTION                            │
│                                                                  │
│   One attention head can only focus on ONE type of relationship │
│   Solution: Use MULTIPLE attention heads in parallel!           │
│                                                                  │
│                    INPUT                                         │
│                      │                                           │
│       ┌──────────────┼──────────────┐                           │
│       │              │              │                           │
│       ▼              ▼              ▼                           │
│   ┌────────┐    ┌────────┐    ┌────────┐                       │
│   │ Head 1 │    │ Head 2 │    │ Head 3 │    ... H heads        │
│   │  Q,K,V │    │  Q,K,V │    │  Q,K,V │                       │
│   └────┬───┘    └────┬───┘    └────┬───┘                       │
│        │             │             │                            │
│        │    Attention(Q,K,V)       │                            │
│        │             │             │                            │
│        ▼             ▼             ▼                           │
│   ┌────────┐    ┌────────┐    ┌────────┐                       │
│   │ out_1  │    │ out_2  │    │ out_3  │                       │
│   └────┬───┘    └────┬───┘    └────┬───┘                       │
│        │             │             │                            │
│        └──────┬──────┴──────┬──────┘                           │
│               │  CONCATENATE │                                   │
│               ▼              │                                   │
│        ┌──────────────┐                                         │
│        │   [out_1 ;   │                                         │
│        │    out_2 ;   │                                         │
│        │    out_3]    │                                         │
│        └──────┬───────┘                                         │
│               │                                                  │
│               ▼                                                  │
│        ┌──────────────┐                                         │
│        │   Linear W_O │   Project back to d_model               │
│        └──────┬───────┘                                         │
│               │                                                  │
│               ▼                                                  │
│            OUTPUT                                                │
│                                                                  │
│   Each head learns different relationships:                     │
│   - Head 1: syntax (subject-verb)                               │
│   - Head 2: coreference (pronouns)                              │
│   - Head 3: positional (nearby words)                           │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## The Transformer Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                    TRANSFORMER                                   │
│           "Attention Is All You Need" (2017)                    │
│                                                                  │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │                                                         │   │
│   │                      OUTPUTS                            │   │
│   │                         ↑                               │   │
│   │                    ┌─────────┐                          │   │
│   │                    │ Softmax │                          │   │
│   │                    └────┬────┘                          │   │
│   │                    ┌────┴────┐                          │   │
│   │                    │ Linear  │                          │   │
│   │                    └────┬────┘                          │   │
│   │                         │                               │   │
│   │   ENCODER          DECODER                              │   │
│   │   ┌──────┐         ┌──────────┐                        │   │
│   │   │Add & │         │ Add &    │                        │   │
│   │   │Norm  │         │ Norm     │                        │   │
│   │   ├──────┤         ├──────────┤                        │   │
│   │   │Feed  │         │  Feed    │                        │   │
│   │   │Forward│        │ Forward  │                        │   │
│   │ Nx├──────┤       Nx├──────────┤                        │   │
│   │   │Add & │         │ Add &    │                        │   │
│   │   │Norm  │◄────────┤ Norm     │  Cross-attention       │   │
│   │   ├──────┤         ├──────────┤  (decoder attends      │   │
│   │   │Multi │         │ Masked   │   to encoder)          │   │
│   │   │Head  │         │Multi-Head│                        │   │
│   │   │Attn  │         │ Attention│                        │   │
│   │   └──┬───┘         └────┬─────┘                        │   │
│   │      │                  │                              │   │
│   │   ┌──┴───┐         ┌────┴─────┐                        │   │
│   │   │Input │         │ Output   │                        │   │
│   │   │Embed │         │ Embed    │                        │   │
│   │   │ +PE  │         │  +PE     │                        │   │
│   │   └──────┘         └──────────┘                        │   │
│   │      ↑                  ↑                              │   │
│   │   INPUTS         OUTPUTS (shifted)                     │   │
│   │                                                         │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   PE = Positional Encoding (since no recurrence)                │
│   N = number of layers (typically 6 or 12)                      │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Positional Encoding

```
┌─────────────────────────────────────────────────────────────────┐
│              POSITIONAL ENCODING                                 │
│                                                                  │
│   Problem: Self-attention is permutation invariant!             │
│   "cat sat mat" = "mat cat sat" (same attention)                │
│                                                                  │
│   Solution: Add position information to embeddings              │
│                                                                  │
│   PE(pos, 2i)   = sin(pos / 10000^(2i/d))                      │
│   PE(pos, 2i+1) = cos(pos / 10000^(2i/d))                      │
│                                                                  │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │                                                         │   │
│   │   Position:  0    1    2    3    4    5                │   │
│   │              │    │    │    │    │    │                │   │
│   │   dim 0:    sin  sin  sin  sin  sin  sin  (low freq)  │   │
│   │   dim 1:    cos  cos  cos  cos  cos  cos               │   │
│   │   dim 2:    sin  sin  sin  sin  sin  sin  (higher)    │   │
│   │   dim 3:    cos  cos  cos  cos  cos  cos               │   │
│   │   ...                                                   │   │
│   │                                                         │   │
│   │   Each position gets a UNIQUE pattern                  │   │
│   │   Nearby positions have similar encodings              │   │
│   │   Can generalize to longer sequences                   │   │
│   │                                                         │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   Final input = word_embedding + positional_encoding            │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Feed-Forward Network

```
┌─────────────────────────────────────────────────────────────────┐
│              FEED-FORWARD NETWORK (FFN)                          │
│                                                                  │
│   Applied to each position independently (same weights)         │
│                                                                  │
│   FFN(x) = ReLU(x · W₁ + b₁) · W₂ + b₂                         │
│                                                                  │
│   ┌───────────────────────────────────────────────────────┐     │
│   │                                                       │     │
│   │   INPUT           HIDDEN           OUTPUT             │     │
│   │   [d_model]      [d_ff]           [d_model]          │     │
│   │                                                       │     │
│   │      ○             ○                 ○                │     │
│   │      ○             ○                 ○                │     │
│   │      ○──────────►  ○ ──────────────► ○                │     │
│   │      ○    W₁      ○      W₂         ○                │     │
│   │      ○             ○ (ReLU)         ○                │     │
│   │      ○             ○                 ○                │     │
│   │      ○             ○                 ○                │     │
│   │                    ○                                  │     │
│   │                    ○                                  │     │
│   │     512           2048              512               │     │
│   │                                                       │     │
│   └───────────────────────────────────────────────────────┘     │
│                                                                  │
│   Typically d_ff = 4 × d_model                                  │
│   This is where most parameters live!                           │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Residual Connections & Layer Norm

```
┌─────────────────────────────────────────────────────────────────┐
│          RESIDUAL CONNECTIONS + LAYER NORMALIZATION              │
│                                                                  │
│   Each sub-layer has:                                           │
│   output = LayerNorm(x + Sublayer(x))                           │
│                                                                  │
│   ┌───────────────────────────────────────────────────────┐     │
│   │                                                       │     │
│   │          ┌────────────────────┐                      │     │
│   │          │                    │                      │     │
│   │    x ────┤                    ├───► LayerNorm ──► out│     │
│   │          │    Sublayer        │                      │     │
│   │          │  (Attention or     │         ↑            │     │
│   │          │   FFN)             │         │            │     │
│   │          │                    │         │            │     │
│   │          └─────────┬──────────┘         │            │     │
│   │                    │                    │            │     │
│   │                    └──────────(+)───────┘            │     │
│   │                           residual                   │     │
│   │                           connection                 │     │
│   └───────────────────────────────────────────────────────┘     │
│                                                                  │
│   WHY?                                                           │
│   - Residual: enables training very deep networks               │
│   - LayerNorm: stabilizes training, normalizes activations      │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Vision Transformer (ViT)

```
┌─────────────────────────────────────────────────────────────────┐
│                 VISION TRANSFORMER (ViT)                         │
│                                                                  │
│   Idea: Treat image patches as "tokens" (like words)            │
│                                                                  │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │                                                         │   │
│   │   1. Split image into patches (e.g., 16×16 pixels)     │   │
│   │                                                         │   │
│   │      ┌───┬───┬───┬───┐                                 │   │
│   │      │ 1 │ 2 │ 3 │ 4 │                                 │   │
│   │      ├───┼───┼───┼───┤                                 │   │
│   │      │ 5 │ 6 │ 7 │ 8 │     16 patches                  │   │
│   │      ├───┼───┼───┼───┤     (for 4×4 grid)              │   │
│   │      │ 9 │10 │11 │12 │                                 │   │
│   │      ├───┼───┼───┼───┤                                 │   │
│   │      │13 │14 │15 │16 │                                 │   │
│   │      └───┴───┴───┴───┘                                 │   │
│   │                                                         │   │
│   │   2. Flatten each patch → linear projection → embedding│   │
│   │                                                         │   │
│   │   3. Add [CLS] token + positional embeddings           │   │
│   │                                                         │   │
│   │      [CLS] [P1] [P2] [P3] ... [P16]                    │   │
│   │        +     +    +    +        +                       │   │
│   │      PE0   PE1  PE2  PE3  ... PE16                     │   │
│   │                                                         │   │
│   │   4. Feed through Transformer encoder                  │   │
│   │                                                         │   │
│   │   5. Use [CLS] output for classification               │   │
│   │                                                         │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   Requires LOTS of data (or pre-training)                       │
│   But scales better than CNNs with more compute                 │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Summary: Attention vs RNNs vs CNNs

```
┌─────────────────────────────────────────────────────────────────┐
│              COMPARISON                                          │
│                                                                  │
│               RNN         CNN         Transformer               │
│   ────────────────────────────────────────────────              │
│                                                                  │
│   Parallelizable    ✗           ✓           ✓                   │
│                                                                  │
│   Long-range deps   Hard        Hard        Easy                │
│                   (vanish)   (receptive)  (direct)              │
│                                                                  │
│   Sequential bias   ✓           ✗           ✗                   │
│                                                                  │
│   Local bias        ✗           ✓           ✗                   │
│                                                                  │
│   Computation      O(n)        O(n)        O(n²)                │
│   per layer                                                      │
│                                                                  │
│   Memory           O(1)        O(1)        O(n²)                │
│                                                                  │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   TRANSFORMERS WIN because:                                     │
│   1. Better at long-range dependencies                          │
│   2. Parallelizable (faster training)                           │
│   3. Scale better with more data and compute                    │
│   4. Flexible (works for text, images, audio, video)            │
│                                                                  │
│   But: O(n²) attention is expensive for long sequences          │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Image References

Key images from: `images/lecture_8/`

- `page035_img99.png` - Attention mechanism with encoder-decoder
- `page063_img111.png` - Self-attention Q, K, V diagram
- `page040_img109.png` - Attention weights visualization
