# Lecture 4: Neural Networks and Backpropagation
## Stanford CS231n 10th Anniversary - April 10, 2025

---

## From Linear Classifiers to Neural Networks

```
┌─────────────────────────────────────────────────────────────────┐
│           LINEAR CLASSIFIER vs NEURAL NETWORK                    │
│                                                                  │
│   LINEAR:                     NEURAL NETWORK (2-layer):         │
│                                                                  │
│   f = W·x                     f = W₂·max(0, W₁·x)               │
│                                                                  │
│   ┌───┐     ┌───┐            ┌───┐     ┌───┐     ┌───┐         │
│   │ x │────►│ W │────►scores │ x │────►│W₁ │────►│W₂ │────►scores│
│   └───┘     └───┘            └───┘     └───┘     └───┘         │
│                                          │                      │
│                                       ReLU                      │
│                                    max(0, ·)                    │
│                                                                  │
│   ONE template per class      MANY templates combined!          │
│   (limited)                   (more expressive)                 │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

*Image: Neural network formula (images/lecture_4/page027_img56.png)*

---

## Neural Network Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│              FULLY CONNECTED NEURAL NETWORK                      │
│                                                                  │
│   INPUT        HIDDEN LAYER       HIDDEN LAYER      OUTPUT      │
│   LAYER            #1                 #2            LAYER       │
│                                                                  │
│     ○────────────○                                              │
│      ╲          ╱│╲               ○                             │
│       ╲        ╱ │ ╲             ╱│╲               ○            │
│     ○──╲──────○──┼──╲───────────○─┼─╲─────────────○            │
│      ╲  ╲    ╱│╲ │   ╲         ╱│╲│  ╲           ╱             │
│       ╲  ╲  ╱ │ ╲│    ╲       ╱ │ ╲│   ╲        ╱              │
│     ○──╲──╲╱──┼──╲─────────────○──┼──╲──────────○              │
│      ╲  ╲╱╲   │   ╲          ╱│╲ │   ╲        ╱                │
│       ╲ ╱╲ ╲  │    ╲        ╱ │ ╲│    ╲      ╱                 │
│     ○──╱──○───┼─────────────○──┼──╲──────────○                 │
│       ╱      ╲│              ╲ │   ╲                            │
│      ╱        ╲               ╲│    ╲                           │
│     ○──────────○───────────────○─────╲───────○                 │
│                                                                  │
│   [3072]       [100]            [100]       [10]                │
│   (pixels)   (templates)      (combine)   (scores)              │
│                                                                  │
│   "Fully connected" = every neuron connects to all previous     │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Activation Functions

```
┌─────────────────────────────────────────────────────────────────┐
│                   ACTIVATION FUNCTIONS                           │
│   (Non-linearity between layers - CRITICAL for expressiveness)  │
│                                                                  │
│   ReLU: f(x) = max(0, x)       Sigmoid: f(x) = 1/(1+e^-x)      │
│                                                                  │
│       ↑                              ↑                          │
│       │      ╱                       │      ╭────               │
│       │     ╱                        │     ╱                    │
│       │    ╱                         │    ╱                     │
│   ────┼───╱────→               ──────┼───╱───────→              │
│       │  ╱                           │  ╱                       │
│       │ ╱                            │ ╱                        │
│       │╱                             │╰────                     │
│                                                                  │
│   ✓ Simple, fast              ✗ Saturates (kills gradients)    │
│   ✓ No saturation             ✗ Not zero-centered              │
│   ✗ Dead neurons (x<0)        ✗ Slow (exp)                     │
│                                                                  │
│   Leaky ReLU: f(x) = max(0.01x, x)                              │
│                                                                  │
│       ↑                                                         │
│       │      ╱                                                  │
│       │     ╱                                                   │
│       │    ╱      ← slope = 1                                   │
│   ────┼───╱────→                                                │
│       │  ╱                                                      │
│      ╱│ ╱  ← slope = 0.01 (small leak)                         │
│     ╱ │╱                                                        │
│                                                                  │
│   ✓ Fixes "dead ReLU" problem                                   │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Why Non-Linearity is Essential

```
┌─────────────────────────────────────────────────────────────────┐
│            WITHOUT NON-LINEARITY: STILL LINEAR!                  │
│                                                                  │
│   f = W₂(W₁·x) = (W₂W₁)·x = W'·x                               │
│                                                                  │
│   Without activation functions, stacking layers is pointless!   │
│   Multiple linear transforms = single linear transform          │
│                                                                  │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   WITH NON-LINEARITY: UNIVERSAL APPROXIMATION                   │
│                                                                  │
│   f = W₂·max(0, W₁·x)  ← Can approximate ANY function!         │
│                                                                  │
│   Example: XOR problem (not linearly separable)                 │
│                                                                  │
│      Linear:              With hidden layer:                    │
│      ○───────○             ○───────○                            │
│      │ Can't │             │  ✓!   │                            │
│      │separate│            │       │                            │
│      ●───────●             ●───────●                            │
│      (fails)              (succeeds)                            │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Computational Graphs

```
┌─────────────────────────────────────────────────────────────────┐
│              COMPUTATIONAL GRAPH REPRESENTATION                  │
│                                                                  │
│   f(x, y, z) = (x + y) * z                                      │
│                                                                  │
│   Forward pass (compute output):                                │
│                                                                  │
│     x = -2  ─────┐                                              │
│                  ├──► (+) ──► q = 3 ──┐                         │
│     y =  5  ─────┘                    ├──► (*) ──► f = -12      │
│                                       │                         │
│     z = -4  ─────────────────────────┘                         │
│                                                                  │
│   Values flow LEFT to RIGHT                                     │
│                                                                  │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   Backward pass (compute gradients):                            │
│                                                                  │
│     ∂f/∂x = ?  ◄────┐                                           │
│                     ├◄─ (+) ◄── ∂f/∂q = z = -4 ◄─┐              │
│     ∂f/∂y = ?  ◄────┘                            ├◄─ (*) ◄── 1  │
│                                                  │              │
│     ∂f/∂z = q = 3 ◄──────────────────────────────┘              │
│                                                                  │
│   ∂f/∂x = ∂f/∂q · ∂q/∂x = (-4) · 1 = -4                        │
│   ∂f/∂y = ∂f/∂q · ∂q/∂y = (-4) · 1 = -4                        │
│                                                                  │
│   Gradients flow RIGHT to LEFT                                  │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

*Image: Computational graph with forward/backward values (images/lecture_4/page058_img151.png)*

---

## Backpropagation: The Chain Rule

```
┌─────────────────────────────────────────────────────────────────┐
│                    BACKPROPAGATION                               │
│                                                                  │
│   Key insight: Use CHAIN RULE to compute gradients efficiently  │
│                                                                  │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │                                                         │   │
│   │  upstream      local          downstream                │   │
│   │  gradient    gradient          gradient                 │   │
│   │                                                         │   │
│   │    ∂L         ∂f              ∂L       ∂L     ∂f        │   │
│   │   ─── ◄──── ─── ◄──────     ─── = ─── · ───            │   │
│   │   ∂x         ∂x              ∂x     ∂f     ∂x           │   │
│   │     ↑         ↑                                         │   │
│   │     │    ┌────┴────┐                                    │   │
│   │     │    │  node   │                                    │   │
│   │     └────┤  f(x)   │◄──── upstream gradient             │   │
│   │          └─────────┘                                    │   │
│   │                                                         │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   Each node only needs to know:                                 │
│   1. Local gradient (∂output/∂input)                           │
│   2. Upstream gradient (passed from later nodes)               │
│                                                                  │
│   Multiply them → pass backward                                 │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Common Gate Gradients

```
┌─────────────────────────────────────────────────────────────────┐
│                 GRADIENT PATTERNS TO KNOW                        │
│                                                                  │
│   ADD GATE: Distributes gradient equally                        │
│   ┌─────────────────────────────────────────┐                   │
│   │  x ──┐                                  │                   │
│   │      ├──► (+) ──► z = x + y            │                   │
│   │  y ──┘                                  │                   │
│   │                                          │                   │
│   │  ∂z/∂x = 1,  ∂z/∂y = 1                  │                   │
│   │  Both inputs get SAME upstream gradient │                   │
│   └─────────────────────────────────────────┘                   │
│                                                                  │
│   MUL GATE: Swaps and scales                                    │
│   ┌─────────────────────────────────────────┐                   │
│   │  x ──┐                                  │                   │
│   │      ├──► (*) ──► z = x * y            │                   │
│   │  y ──┘                                  │                   │
│   │                                          │                   │
│   │  ∂z/∂x = y,  ∂z/∂y = x                  │                   │
│   │  Gradient on x is scaled by y (& vice versa)│              │
│   └─────────────────────────────────────────┘                   │
│                                                                  │
│   MAX GATE: Routes gradient to max input                        │
│   ┌─────────────────────────────────────────┐                   │
│   │  x ──┐                                  │                   │
│   │      ├──► max ──► z = max(x, y)        │                   │
│   │  y ──┘                                  │                   │
│   │                                          │                   │
│   │  ∂z/∂x = 1 if x>y else 0               │                   │
│   │  Only the max input gets gradient!      │                   │
│   └─────────────────────────────────────────┘                   │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Neural Network Loss Function

```
┌─────────────────────────────────────────────────────────────────┐
│           FULL NEURAL NETWORK LOSS                               │
│                                                                  │
│   Score function:  s = f(x; W₁, W₂) = W₂ · max(0, W₁ · x)      │
│                                                                  │
│   Per-example loss (SVM hinge):                                 │
│                                                                  │
│            Lᵢ = Σ max(0, sⱼ - sᵧᵢ + 1)                         │
│               j≠yᵢ                                               │
│                                                                  │
│   Regularization:                                                │
│                                                                  │
│            R(W) = Σ Wₖ²                                         │
│                   k                                              │
│                                                                  │
│   FULL LOSS:                                                     │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │         1  N                                            │   │
│   │    L = ─── Σ  Lᵢ  +  λR(W₁)  +  λR(W₂)                 │   │
│   │         N i=1                                           │   │
│   │        ╲____╱     ╲______________╱                      │   │
│   │       data loss     regularization                      │   │
│   │                    (on ALL weight matrices)             │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

*Image: Loss formulas (images/lecture_4/page050_img124.png)*

---

## Vectorized Backprop

```
┌─────────────────────────────────────────────────────────────────┐
│              VECTORIZED OPERATIONS                               │
│                                                                  │
│   In practice, we work with MATRICES not scalars:               │
│                                                                  │
│   Forward:                                                       │
│     X: [N × D]      input batch                                 │
│     W: [D × H]      weights                                     │
│     Y = X · W       [N × H]  hidden activations                 │
│                                                                  │
│   Backward:                                                      │
│     Given: dL/dY    [N × H]  upstream gradient                  │
│                                                                  │
│     dL/dX = (dL/dY) · Wᵀ    [N × D]                            │
│     dL/dW = Xᵀ · (dL/dY)    [D × H]                            │
│                                                                  │
│   KEY INSIGHT: Gradient has SAME SHAPE as original variable!   │
│                                                                  │
│   ┌──────────────────────────────────────────────────┐          │
│   │ Shape of dL/dW = Shape of W                      │          │
│   │ Shape of dL/dX = Shape of X                      │          │
│   │                                                  │          │
│   │ Use this to sanity-check your implementations!  │          │
│   └──────────────────────────────────────────────────┘          │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Modular Implementation

```python
# Each layer implements forward() and backward()

class ReLU:
    def forward(self, x):
        self.x = x  # cache for backward
        return np.maximum(0, x)

    def backward(self, dout):
        dx = dout.copy()
        dx[self.x < 0] = 0  # gradient is 0 where input was negative
        return dx

class Linear:
    def forward(self, x, W, b):
        self.x, self.W = x, W  # cache
        return x @ W + b

    def backward(self, dout):
        dx = dout @ self.W.T
        dW = self.x.T @ dout
        db = dout.sum(axis=0)
        return dx, dW, db
```

```
┌─────────────────────────────────────────────────────────────────┐
│              MODULAR NETWORK DESIGN                              │
│                                                                  │
│   ┌────────┐    ┌────────┐    ┌────────┐    ┌────────┐         │
│   │ Linear │───►│  ReLU  │───►│ Linear │───►│Softmax │         │
│   │        │◄───│        │◄───│        │◄───│  Loss  │         │
│   └────────┘    └────────┘    └────────┘    └────────┘         │
│     forward ──────────────────────────────────────►            │
│     ◄────────────────────────────────────── backward            │
│                                                                  │
│   Each module is a LEGO block with:                             │
│   - forward(input) → output                                     │
│   - backward(upstream_grad) → downstream_grad                   │
│                                                                  │
│   PyTorch/TensorFlow do this automatically!                     │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Summary

```
┌─────────────────────────────────────────────────────────────────┐
│                    KEY TAKEAWAYS                                 │
│                                                                  │
│   1. NEURAL NETWORKS = stacked linear layers + non-linearities  │
│      - More expressive than linear classifiers                  │
│      - Can learn complex decision boundaries                    │
│                                                                  │
│   2. COMPUTATIONAL GRAPHS represent computations                │
│      - Forward: compute outputs                                 │
│      - Backward: compute gradients using chain rule             │
│                                                                  │
│   3. BACKPROPAGATION = efficient gradient computation           │
│      - Each node multiplies upstream grad × local grad          │
│      - Gradients flow backward through graph                    │
│                                                                  │
│   4. MODULAR DESIGN enables flexible architectures              │
│      - Each layer: forward() + backward()                       │
│      - Compose layers like LEGO blocks                          │
│                                                                  │
│   5. AUTOMATIC DIFFERENTIATION (PyTorch) does this for you!    │
│      - Just define forward pass                                 │
│      - Framework computes gradients automatically               │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Image References

Key images from: `images/lecture_4/`

- `page010_img21.png` - Training loss curve with step decay
- `page019_img40.png` - Shiba Inu example image
- `page026_img53.png` - Linear formula f = Wx
- `page027_img56.png` - Neural network formula
- `page050_img124.png` - Full loss function formulas
- `page055_img133.png` - Complex computational graph
- `page058_img151.png` - Simple computational graph with backprop
- `page060_img155.png` - Function definition f(x,y,z)
