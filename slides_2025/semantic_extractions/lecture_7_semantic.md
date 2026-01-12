# Lecture 7: Recurrent Neural Networks (RNNs)

## RNN Architecture Types

```
ONE-TO-ONE              ONE-TO-MANY             MANY-TO-ONE            MANY-TO-MANY
(Standard NN)           (Image Captioning)      (Sentiment)            (Translation)

    ┌───┐                 ┌───┐ ┌───┐ ┌───┐         ┌───┐                ┌───┐ ┌───┐ ┌───┐
    │ y │                 │y₁ │ │y₂ │ │y₃ │         │ y │                │y₁ │ │y₂ │ │y₃ │
    └─▲─┘                 └─▲─┘ └─▲─┘ └─▲─┘         └─▲─┘                └─▲─┘ └─▲─┘ └─▲─┘
      │                     │     │     │             │                    │     │     │
    ┌─┴─┐                 ┌─┴─┐─►┌┴──┐─►┌┴──┐      ┌──┴─┐─►┌───┐─►┌───┐  ┌─┴─┐─►┌┴──┐─►┌┴──┐
    │ h │                 │h₁ │  │h₂ │  │h₃ │      │ h₁ │  │h₂ │  │h₃ │  │h₁ │  │h₂ │  │h₃ │
    └─▲─┘                 └─▲─┘  └───┘  └───┘      └──▲─┘  └─▲─┘  └─▲─┘  └─▲─┘  └─▲─┘  └─▲─┘
      │                     │                        │      │      │      │      │      │
    ┌─┴─┐                 ┌─┴─┐                    ┌──┴─┐ ┌──┴─┐ ┌──┴─┐  ┌─┴─┐  ┌─┴─┐  ┌─┴─┐
    │ x │                 │ x │                    │ x₁ │ │ x₂ │ │ x₃ │  │x₁ │  │x₂ │  │x₃ │
    └───┘                 └───┘                    └────┘ └────┘ └────┘  └───┘  └───┘  └───┘

 Standard               Single input             Sequence input         Sequence to
 feedforward            generates                produces single        sequence
 network                sequence output          output                 (aligned)
```

## Core RNN Recurrence Formula

```
                    ┌─────────────────────────────────────┐
                    │   h_t = f_W(h_{t-1}, x_t)           │
                    │                                     │
                    │   h_t = tanh(W_hh·h_{t-1} + W_xh·x_t)│
                    │                                     │
                    │   y_t = W_hy·h_t                    │
                    └─────────────────────────────────────┘

    UNROLLED RNN THROUGH TIME:

    x₁           x₂           x₃           x₄
    │            │            │            │
    ▼            ▼            ▼            ▼
┌───────┐   ┌───────┐   ┌───────┐   ┌───────┐
│       │   │       │   │       │   │       │
│  RNN  │──►│  RNN  │──►│  RNN  │──►│  RNN  │──►  h₄
│       │   │       │   │       │   │       │
│  h₀   │   │  h₁   │   │  h₂   │   │  h₃   │
└───┬───┘   └───┬───┘   └───┬───┘   └───┬───┘
    │           │           │           │
    ▼           ▼           ▼           ▼
    y₁          y₂          y₃          y₄

    Same weights W_hh, W_xh, W_hy used at every time step!
```

## RNN Computational Graph

```
           FORWARD PASS                    BACKWARD PASS (BPTT)

    h₀ ──► [W_hh] ──► h₁ ──► [W_hh] ──► h₂    ∂L/∂h₀ ◄── ∂L/∂h₁ ◄── ∂L/∂h₂
              ▲                   ▲              │           │
           [W_xh]              [W_xh]           ×W_hh      ×W_hh
              │                   │              │           │
             x₁                  x₂           gradients   gradients
              │                   │            shrink!     shrink!
              ▼                   ▼
             y₁                  y₂
              │                   │
              ▼                   ▼
             L₁                  L₂

    Backpropagation Through Time (BPTT):
    - Unroll entire sequence
    - Compute loss at each step
    - Backpropagate through all timesteps
    - Gradients multiply by W_hh repeatedly → vanishing/exploding!
```

## Character-Level Language Model

```
    INPUT: "hello" → predict next character

    One-hot encoding (vocab size = 4: h, e, l, o):

    "h" → [1,0,0,0]    "e" → [0,1,0,0]    "l" → [0,0,1,0]    "o" → [0,0,0,1]

    ┌─────┐    ┌─────┐    ┌─────┐    ┌─────┐
    │  1  │    │  0  │    │  0  │    │  0  │
    │  0  │    │  1  │    │  0  │    │  0  │
    │  0  │    │  0  │    │  1  │    │  1  │
    │  0  │    │  0  │    │  0  │    │  0  │
    └──┬──┘    └──┬──┘    └──┬──┘    └──┬──┘
       │W_xh     │W_xh     │W_xh     │W_xh
       ▼         ▼         ▼         ▼
    ┌─────┐──►┌─────┐──►┌─────┐──►┌─────┐
    │ h₁  │   │ h₂  │   │ h₃  │   │ h₄  │
    └──┬──┘   └──┬──┘   └──┬──┘   └──┬──┘
       │W_hy     │W_hy     │W_hy     │W_hy
       ▼         ▼         ▼         ▼
    ┌─────┐   ┌─────┐   ┌─────┐   ┌─────┐
    │  e  │   │  l  │   │  l  │   │  o  │  ← target: next char
    └─────┘   └─────┘   └─────┘   └─────┘

    Training: Cross-entropy loss on predicted vs actual next character
```

## Vanishing Gradient Problem

```
    FORWARD:  h_t = tanh(W_hh·h_{t-1} + W_xh·x_t)

    BACKWARD: ∂L/∂h₀ = ∂L/∂h_T × ∂h_T/∂h_{T-1} × ... × ∂h₁/∂h₀
                     = ∂L/∂h_T × (W_hh × tanh')^T

    ┌────────────────────────────────────────────────────────────┐
    │ If max eigenvalue of W_hh < 1:  gradients → 0 (vanishing)  │
    │ If max eigenvalue of W_hh > 1:  gradients → ∞ (exploding)  │
    └────────────────────────────────────────────────────────────┘

    Gradient magnitude over time:

    |grad|
      │
    1 ┼────╮
      │     ╲
      │      ╲  vanishing
      │       ╲
      │        ╲____
    0 ┼───────────────────────► time
         1  2  3  4  5  6  7

    Long sequences → earlier timesteps get near-zero gradients
    → Network can't learn long-range dependencies!
```

## Sequence-to-Sequence (Encoder-Decoder)

```
    ENCODER                              DECODER

    "the"    "cat"    "sat"              <SOS>    "le"     "chat"
      │        │        │                  │        │        │
      ▼        ▼        ▼                  ▼        ▼        ▼
    ┌───┐    ┌───┐    ┌───┐    context   ┌───┐    ┌───┐    ┌───┐
    │   │───►│   │───►│   │─────────────►│   │───►│   │───►│   │
    │RNN│    │RNN│    │RNN│     vector   │RNN│    │RNN│    │RNN│
    └───┘    └───┘    └───┘      (c)     └───┘    └───┘    └───┘
                         │                 │        │        │
                         │                 ▼        ▼        ▼
                         │               "le"    "chat"   <EOS>
                         │
                    Final hidden state
                    encodes entire input

    Problem: Entire input compressed into single fixed-size vector!
    → Information bottleneck for long sequences
    → Solution: Attention mechanism (next lecture)
```

## LSTM (Long Short-Term Memory)

```
    ┌─────────────────────────────────────────────────────────────────┐
    │                      LSTM CELL                                   │
    │                                                                  │
    │   c_{t-1} ───────────────[×]─────────[+]──────────► c_t         │
    │                           │           │                          │
    │                    forget │     ┌─────┴─────┐                    │
    │                    gate   │     │  [×]      │                    │
    │                           │     │   │       │                    │
    │                           │    tanh │  input gate                │
    │                           │     │   │       │                    │
    │   h_{t-1} ──┬──────────[σ]     [σ] [σ]    [σ]──► output gate    │
    │             │             f_t   │   i_t    │                     │
    │             │                   │          │                     │
    │   x_t ──────┴───────────────────┴──────────┘                    │
    │                                                                  │
    │                                  ▼                               │
    │                           h_t = o_t × tanh(c_t)                  │
    └─────────────────────────────────────────────────────────────────┘

    GATES (all sigmoid → output in [0,1]):

    f_t = σ(W_f·[h_{t-1}, x_t] + b_f)    ← Forget gate: what to forget
    i_t = σ(W_i·[h_{t-1}, x_t] + b_i)    ← Input gate: what to remember
    o_t = σ(W_o·[h_{t-1}, x_t] + b_o)    ← Output gate: what to output

    c̃_t = tanh(W_c·[h_{t-1}, x_t] + b_c) ← Candidate cell state
    c_t = f_t × c_{t-1} + i_t × c̃_t      ← New cell state
    h_t = o_t × tanh(c_t)                 ← Hidden state output
```

## LSTM Gradient Flow

```
    WHY LSTM SOLVES VANISHING GRADIENTS:

    Cell state c_t has additive connections:

    c_{t-1} ────[×f_t]────[+]────► c_t
                          │
                     [×i_t]
                          │
                        c̃_t

    Gradient flow through cell state:
    ∂c_t/∂c_{t-1} = f_t  (just multiplication by forget gate!)

    If f_t ≈ 1: gradient flows unchanged! (no vanishing)

    ┌────────────────────────────────────────────────────────┐
    │ LSTM "highway" for gradients:                          │
    │                                                        │
    │ c₀ ───[×f₁]──► c₁ ───[×f₂]──► c₂ ───[×f₃]──► c₃       │
    │                                                        │
    │ If all f ≈ 1: ∂L/∂c₀ ≈ ∂L/∂c₃ (gradient preserved!)   │
    └────────────────────────────────────────────────────────┘

    Compare to vanilla RNN:
    ∂h_t/∂h_{t-1} = W_hh × tanh'(...)  ← repeated multiplication!
```

## GRU (Gated Recurrent Unit)

```
    Simplified version of LSTM (fewer parameters):

    ┌──────────────────────────────────────────────────┐
    │               GRU CELL                           │
    │                                                  │
    │   h_{t-1} ──┬──[σ]────────────────[×]──┬──► h_t │
    │             │   r_t (reset)        │    │        │
    │             │   │                  │   [+]       │
    │             │   ▼           z_t ──[×]  │        │
    │             └──[×]──[tanh]──────────┘   │        │
    │                 │                       │        │
    │   x_t ─────────┴──[σ]───────────────(1-z_t)     │
    │                    z_t (update)                  │
    └──────────────────────────────────────────────────┘

    z_t = σ(W_z·[h_{t-1}, x_t])         ← Update gate
    r_t = σ(W_r·[h_{t-1}, x_t])         ← Reset gate
    h̃_t = tanh(W·[r_t × h_{t-1}, x_t])  ← Candidate hidden state
    h_t = (1-z_t) × h_{t-1} + z_t × h̃_t ← New hidden state

    LSTM vs GRU:
    ┌─────────┬──────────────────┬─────────────────┐
    │         │      LSTM        │      GRU        │
    ├─────────┼──────────────────┼─────────────────┤
    │ Gates   │ 3 (f, i, o)      │ 2 (z, r)        │
    │ States  │ 2 (c, h)         │ 1 (h)           │
    │ Params  │ More             │ Fewer           │
    └─────────┴──────────────────┴─────────────────┘
```

## Applications

```
    IMAGE CAPTIONING (CNN + RNN):

    ┌─────────┐      ┌─────────┐
    │  Image  │      │   CNN   │──► feature vector
    └────┬────┘      └────┬────┘
         │                │
         ▼                ▼
    ┌─────────────────────────────────────────┐
    │              RNN Decoder                 │
    │  [feat]──►[RNN]──►[RNN]──►[RNN]──►...  │
    │             │       │       │           │
    │            "A"    "dog"   "runs"        │
    └─────────────────────────────────────────┘


    SENTIMENT ANALYSIS (Many-to-One):

    "This movie was great" ──► [RNN]──►[RNN]──►[RNN]──►[RNN] ──► Positive
                                  │       │       │       │
                                "This"  "movie"  "was"  "great"


    MACHINE TRANSLATION (Seq2Seq):

    [English] ──► Encoder ──► context ──► Decoder ──► [French]

    "I am a student" ──► [h₄] ──► "Je suis étudiant"
```

## Text Generation Example

```
    Training on Shakespeare:

    ┌────────────────────────────────────────────────┐
    │ THE SONNETS                                    │
    │ by William Shakespeare                         │
    │                                                │
    │ From fairest creatures we desire increase,    │
    │ That thereby beauty's rose might never die... │
    └────────────────────────────────────────────────┘

    Character-level RNN learns:
    - Spelling patterns
    - Word structures
    - Basic grammar
    - Style mimicry

    Generated samples (temperature = 1.0):

    "Thence comes it that my name receives a brand,
     And almost thence my nature is subdued
     To what it works in, like the dyer's hand..."

    Temperature controls randomness:
    - Low (0.5): Conservative, repetitive
    - High (1.5): Creative, sometimes nonsensical
```

## Bidirectional RNNs

```
    Problem: Standard RNN only sees past context

    "The movie was not bad, it was actually ___"
                          │
    Standard RNN at "bad": doesn't know "actually" comes next!

    BIDIRECTIONAL RNN:

    Forward:   x₁ ──► h₁ ──► h₂ ──► h₃ ──► h₄
                      │       │       │       │
                      ▼       ▼       ▼       ▼
    Output:          [h₁,h'₁] [h₂,h'₂] [h₃,h'₃] [h₄,h'₄]
                      ▲       ▲       ▲       ▲
                      │       │       │       │
    Backward:  x₁ ◄── h'₁◄── h'₂◄── h'₃◄── h'₄

    At each position: both past AND future context!

    Use cases:
    - Named Entity Recognition
    - Part-of-Speech tagging
    - Any task where full sequence is available

    NOT usable for: Language generation (can't see future)
```

## Implementation: NumPy RNN

```python
import numpy as np

# Weight matrices
W_xh = np.array([[1], [0], [0]])    # input → hidden
W_hh = np.array([[0, 0, 0],         # hidden → hidden
                 [1, 0, 0],
                 [0, 0, 1]])
W_hy = np.array([1, 1, -1])         # hidden → output

# Input sequence: 0, 1, 0, 1, 1, 1, 0, 1, 1
x_seq = [0, 1, 0, 1, 1, 1, 0, 1, 1]

# Initial hidden state
h_t_prev = np.array([[0], [0], [1]])

# RNN forward pass
for t, x in enumerate(x_seq):
    h_t = relu(W_hh @ h_t_prev + (W_xh @ x))  # hidden state
    y_t = relu(W_hy @ h_t)                     # output
    h_t_prev = h_t                             # update for next step
```

## Key Takeaways

```
┌────────────────────────────────────────────────────────────────┐
│ 1. RNNs process sequences by maintaining hidden state          │
│                                                                │
│ 2. Same weights shared across all time steps (parameter       │
│    efficiency)                                                 │
│                                                                │
│ 3. Vanilla RNNs suffer from vanishing gradients on long       │
│    sequences                                                   │
│                                                                │
│ 4. LSTM/GRU use gating mechanisms to preserve gradients:      │
│    - Forget gate: what to discard                             │
│    - Input gate: what to remember                             │
│    - Output gate: what to expose                              │
│                                                                │
│ 5. Seq2Seq: encoder compresses input, decoder generates output │
│    - Bottleneck problem → motivates attention                 │
│                                                                │
│ 6. Bidirectional RNNs see both past and future context        │
│                                                                │
│ 7. Applications: translation, captioning, sentiment, generation│
└────────────────────────────────────────────────────────────────┘
```
