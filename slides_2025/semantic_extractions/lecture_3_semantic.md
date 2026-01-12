# Lecture 3: Regularization and Optimization
## Stanford CS231n 10th Anniversary - April 8, 2025

---

## Review: Linear Classifier

From Lecture 2: f(x, W) = Wx + b produces class scores

```
┌─────────────────────────────────────────────────────────────────┐
│              LINEAR CLASSIFIER WITH LOSS FUNCTIONS               │
│                                                                  │
│   ┌────────────────┐   ┌────┐   ┌────┐     ┌────────┐           │
│   │ 0.01 -0.05 0.1 │   │-15 │   │ 0.0│     │ -2.85  │           │
│   │ 0.7   0.2 0.05│ × │ 22 │ + │ 0.2│  =  │  0.86  │  scores   │
│   │ 0.0  -0.45-0.2│   │-44 │   │-0.3│     │  0.28  │           │
│   └────────────────┘   │ 56 │   └────┘     └────────┘           │
│          W             └────┘      b                             │
│                          x_i                y_i = 2 (true class) │
│                                                                  │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   HINGE LOSS (SVM)              CROSS-ENTROPY (Softmax)         │
│   ┌─────────────────┐           ┌─────────────────────────┐     │
│   │                 │           │                         │     │
│   │ L = Σ max(0,    │           │ scores → exp → normalize│     │
│   │     s_j - s_y   │           │                         │     │
│   │     + margin)   │           │ -2.85 → 0.058 → 0.016   │     │
│   │                 │           │  0.86 → 2.36  → 0.631   │     │
│   │ max(0,-2.85-    │           │  0.28 → 1.32  → 0.353   │     │
│   │     0.28+1)=0   │           │                         │     │
│   │ max(0, 0.86-    │           │ L = -log(0.353) = 0.452 │     │
│   │     0.28+1)=1.58│           │                         │     │
│   │                 │           │ (want prob of true class│     │
│   │ Total: 1.58     │           │  to be close to 1)      │     │
│   └─────────────────┘           └─────────────────────────┘     │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

*Image: Loss comparison diagram (images/lecture_3/page115_img202.png)*

---

## Regularization: Preventing Overfitting

```
┌─────────────────────────────────────────────────────────────────┐
│                    FULL LOSS FUNCTION                            │
│                                                                  │
│           L(W) = (1/N) Σ L_i(f(x_i, W), y_i) + λR(W)            │
│                  \_________________________/   \____/            │
│                       Data Loss              Regularization      │
│                  (fit the training data)   (prefer simpler W)    │
│                                                                  │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   COMMON REGULARIZATION TYPES:                                   │
│                                                                  │
│   L2 (Ridge):     R(W) = Σ W²    → spreads weights evenly       │
│   L1 (Lasso):     R(W) = Σ |W|   → encourages sparsity          │
│   Elastic Net:    R(W) = Σ (β·W² + |W|)                         │
│   Dropout:        Randomly zero neurons during training         │
│                                                                  │
│   WHY REGULARIZE?                                                │
│   ┌──────────────┐    ┌──────────────┐    ┌──────────────┐      │
│   │  Underfit    │    │   Just Right │    │   Overfit    │      │
│   │    ╱         │    │      ∿       │    │   ∿∿∿∿∿∿     │      │
│   │   ╱          │    │     ∿ ∿      │    │  ∿    ∿∿    │      │
│   │  ● ●  ●      │    │   ●  ●  ●    │    │ ●  ●  ● ●   │      │
│   │ ●    ●  ●    │    │  ●    ●  ●   │    │●    ●    ●  │      │
│   └──────────────┘    └──────────────┘    └──────────────┘      │
│   High bias          Low bias/variance    High variance          │
│   (too simple)       (good generalization)(memorizing noise)    │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

*Image: Loss formula (images/lecture_3/page016_img25.png)*

---

## Optimization: Finding the Best W

**Goal**: Find W that minimizes L(W)

```
┌─────────────────────────────────────────────────────────────────┐
│                    GRADIENT DESCENT                              │
│                                                                  │
│   The gradient ∇L(W) tells us the direction of steepest ascent  │
│   We move in the OPPOSITE direction to minimize loss            │
│                                                                  │
│   LOSS LANDSCAPE (2D visualization):                            │
│                                                                  │
│            ↑ Loss                                                │
│            │     ╱╲                                              │
│            │    ╱  ╲    ╱╲                                       │
│            │   ╱    ╲  ╱  ╲                                      │
│            │  ╱      ╲╱    ╲                                     │
│            │ ╱   ●→→→→★     ╲    ★ = minimum                    │
│            │╱    start  end  ╲   ● = starting point             │
│            └──────────────────→ W                                │
│                                                                  │
│   DERIVATIVE DEFINITION:                                         │
│                                                                  │
│        df(x)         f(x + h) - f(x)                            │
│        ───── = lim   ───────────────                            │
│         dx    h→0          h                                     │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

*Image: Mountain landscape representing loss surface (images/lecture_3/page027_img63.png)*
*Image: Derivative formula (images/lecture_3/page035_img73.png)*

---

## Vanilla Gradient Descent

```python
# Vanilla Gradient Descent
while True:
    weights_grad = evaluate_gradient(loss_fun, data, weights)
    weights += - step_size * weights_grad  # perform parameter update
```

```
┌─────────────────────────────────────────────────────────────────┐
│              GRADIENT DESCENT VARIANTS                           │
│                                                                  │
│   BATCH GRADIENT DESCENT:                                        │
│   - Uses ALL training data to compute gradient                   │
│   - Slow but accurate gradient estimate                          │
│                                                                  │
│   STOCHASTIC GRADIENT DESCENT (SGD):                             │
│   - Uses SINGLE random sample                                    │
│   - Very fast but noisy gradient estimate                        │
│                                                                  │
│   MINI-BATCH GRADIENT DESCENT:                                   │
│   - Uses small batch (32, 64, 128 samples)                      │
│   - Best of both worlds: fast and reasonably accurate           │
│   - This is what people mean by "SGD" in practice               │
│                                                                  │
│   ┌─────────────────────────────────────────────────────┐       │
│   │                                                     │       │
│   │  Batch:    ●────────────────────────→★              │       │
│   │            (smooth but slow)                        │       │
│   │                                                     │       │
│   │  SGD:      ●∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿→★              │       │
│   │            (noisy but fast)                         │       │
│   │                                                     │       │
│   │  Mini-batch: ●~~→~~→~~→~~→~~→★                     │       │
│   │            (good balance)                           │       │
│   │                                                     │       │
│   └─────────────────────────────────────────────────────┘       │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

*Image: Gradient descent code (images/lecture_3/page045_img86.png)*

---

## SGD Problems and Solutions

```
┌─────────────────────────────────────────────────────────────────┐
│               PROBLEMS WITH VANILLA SGD                          │
│                                                                  │
│   PROBLEM 1: Different scales in different dimensions           │
│                                                                  │
│         ↑                     Gradient in steep direction       │
│         │  ╲                  is much larger than in            │
│         │   ╲   ●→            shallow direction.                │
│         │    ╲↙ ↓             This causes zigzagging!           │
│         │     ↘↙                                                │
│         │      ★                                                 │
│         └────────→                                               │
│                                                                  │
│   PROBLEM 2: Local minima and saddle points                     │
│                                                                  │
│         Local Min:    Saddle Point:                             │
│           ╲╱             ╲  ╱                                   │
│           ●              ╲●╱                                    │
│         (stuck!)       (gradient = 0 but not minimum)           │
│                                                                  │
│   PROBLEM 3: Noisy gradients                                     │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## SGD + Momentum

```
┌─────────────────────────────────────────────────────────────────┐
│                    SGD WITH MOMENTUM                             │
│                                                                  │
│   Idea: Maintain a "velocity" that accumulates gradient history │
│                                                                  │
│   v = ρ * v - α * ∇L(W)     # update velocity                   │
│   W = W + v                  # update weights                    │
│                                                                  │
│   ρ = momentum (typically 0.9 or 0.99)                          │
│   α = learning rate                                              │
│                                                                  │
│   INTUITION (ball rolling down hill):                           │
│                                                                  │
│         Without momentum:        With momentum:                  │
│         ●                        ●                               │
│          ↘                        ↘                              │
│           →                        ↘                             │
│            ↙                        ↘                            │
│           ←                          ↘                           │
│          (zigzag)                     ↘ (smooth path)            │
│                                        ★                         │
│                                                                  │
│   Benefits:                                                      │
│   - Dampens oscillations in steep directions                    │
│   - Accelerates in consistent gradient directions               │
│   - Can escape shallow local minima                             │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## AdaGrad and RMSProp

```python
# AdaGrad - Adaptive learning rates per parameter
grad_squared = 0
while True:
    dx = compute_gradient(x)
    grad_squared += dx * dx
    x -= learning_rate * dx / (np.sqrt(grad_squared) + 1e-7)
```

```
┌─────────────────────────────────────────────────────────────────┐
│              ADAPTIVE LEARNING RATE METHODS                      │
│                                                                  │
│   ADAGRAD:                                                       │
│   - Divide by sqrt(sum of squared gradients)                    │
│   - Large gradients → smaller effective learning rate           │
│   - Problem: Learning rate decays to zero over time!            │
│                                                                  │
│   RMSPROP (fix for AdaGrad):                                    │
│   - Use exponential moving average instead of sum               │
│   - grad_squared = decay * grad_squared + (1-decay) * dx²       │
│   - Keeps learning rate from going to zero                      │
│                                                                  │
│   Effect on loss landscape:                                      │
│                                                                  │
│         Before:               After (adaptive):                  │
│         ╱────╲                 ○                                 │
│        ╱      ╲               ╱│╲                                │
│       ╱   ●→   ╲             ╱ ↓ ╲                               │
│      ╱  zigzag  ╲           ╱  ★  ╲                              │
│     ╱            ╲         (direct path)                         │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

*Image: AdaGrad code (images/lecture_3/page110_img198.png)*

---

## Adam: Combining Momentum + Adaptive LR

```python
# Adam (Adaptive Moment Estimation)
first_moment = 0   # momentum
second_moment = 0  # RMSProp-style
for t in range(1, num_iterations):
    dx = compute_gradient(x)
    first_moment = beta1 * first_moment + (1 - beta1) * dx
    second_moment = beta2 * second_moment + (1 - beta2) * dx * dx
    first_unbias = first_moment / (1 - beta1 ** t)   # bias correction
    second_unbias = second_moment / (1 - beta2 ** t)
    x -= learning_rate * first_unbias / (np.sqrt(second_unbias) + 1e-7)
```

```
┌─────────────────────────────────────────────────────────────────┐
│                         ADAM                                     │
│                                                                  │
│   Combines the best of:                                         │
│   - Momentum (first moment)  → smooth gradient direction        │
│   - RMSProp (second moment)  → adaptive learning rate           │
│                                                                  │
│   Typical hyperparameters:                                       │
│   - beta1 = 0.9  (momentum decay)                               │
│   - beta2 = 0.999 (RMSProp decay)                               │
│   - learning_rate = 1e-3 or 3e-4                                │
│                                                                  │
│   WHY BIAS CORRECTION?                                           │
│   - At t=1, first_moment ≈ 0.1 * gradient (too small!)          │
│   - Dividing by (1 - beta^t) compensates for this               │
│                                                                  │
│   ADAM IS THE DEFAULT CHOICE for most deep learning!            │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

*Image: Adam code (images/lecture_3/page075_img133.png)*

---

## Weight Decay vs L2 Regularization

```
┌─────────────────────────────────────────────────────────────────┐
│           WEIGHT DECAY vs L2 REGULARIZATION                      │
│                                                                  │
│   L2 Regularization (in loss):                                   │
│       L_total = L_data + (λ/2) * ||W||²                         │
│       Gradient includes: ∇L_data + λW                           │
│                                                                  │
│   Weight Decay (in update):                                      │
│       W = W - α * (∇L_data + λW)                                │
│       W = (1 - αλ)W - α * ∇L_data                               │
│                                                                  │
│   For vanilla SGD: EQUIVALENT                                    │
│   For Adam: DIFFERENT! (because of adaptive scaling)            │
│                                                                  │
│   ┌───────────────────────────────────────────────────────┐     │
│   │  0.94 ┤                              ─── wd (better)   │     │
│   │  0.90 ┤                    ∿∿∿∿∿∿∿∿   ─── L2            │     │
│   │  0.86 ┤              ∿∿∿∿                              │     │
│   │  0.82 ┤         ∿∿∿                                    │     │
│   │  0.78 ┤      ∿∿                                        │     │
│   │  0.70 ┤    ∿                                           │     │
│   │  0.60 ┤ ∿                                              │     │
│   │       └────────────────────────────────────────────    │     │
│   │         0    5    10   15   20   25   30 (epochs)      │     │
│   └───────────────────────────────────────────────────────┘     │
│                                                                  │
│   Use "decoupled weight decay" (AdamW) for best results!        │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

*Image: Training curves (images/lecture_3/page076_img134.png)*

---

## Learning Rate Schedules

```
┌─────────────────────────────────────────────────────────────────┐
│                  LEARNING RATE SCHEDULES                         │
│                                                                  │
│   Start high (explore) → decrease over time (fine-tune)         │
│                                                                  │
│   STEP DECAY:              COSINE DECAY:                         │
│   α │▔▔▔▔▔┐               α │╲                                  │
│     │     └▔▔▔┐             │ ╲                                 │
│     │         └▔▔▔          │  ╲                                │
│     └───────────→ t         │   ╲___                            │
│   (drop by 10x every N)     └───────→ t                         │
│                            (smooth decrease)                     │
│                                                                  │
│   LINEAR WARMUP + DECAY:                                         │
│   α │    ╱╲                                                      │
│     │   ╱  ╲╲                                                   │
│     │  ╱    ╲╲                                                  │
│     │ ╱      ╲╲___                                              │
│     └───────────→ t                                              │
│   (gradual start, then decay)                                    │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Summary: Optimization Hierarchy

```
┌─────────────────────────────────────────────────────────────────┐
│              OPTIMIZATION METHODS SUMMARY                        │
│                                                                  │
│   SGD                                                            │
│    │                                                             │
│    ├──► + Momentum ──► SGD+Momentum (helps with oscillation)    │
│    │                                                             │
│    ├──► + Adaptive LR ──► AdaGrad ──► RMSProp (fixes decay)     │
│    │                                                             │
│    └──► + Both ──► Adam (default choice!)                       │
│                     │                                            │
│                     └──► + Decoupled WD ──► AdamW (best!)       │
│                                                                  │
│   PRACTICAL ADVICE:                                              │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │ 1. Start with Adam, lr=3e-4                             │   │
│   │ 2. If that doesn't work, try AdamW with weight decay    │   │
│   │ 3. For vision, SGD+Momentum often beats Adam            │   │
│   │ 4. Always use learning rate warmup for large batches    │   │
│   │ 5. Use cosine or step decay schedule                    │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Image References

Key images from: `images/lecture_3/`

- `page016_img25.png` - Loss function formula
- `page027_img63.png` - Mountain landscape (loss surface metaphor)
- `page035_img73.png` - Derivative definition
- `page045_img86.png` - Gradient descent code
- `page055_img92.png` - Partial derivatives example
- `page070_img127.png` - Adam optimizer code
- `page075_img133.png` - Adam code (duplicate)
- `page076_img134.png` - Weight decay vs L2 training curves
- `page110_img198.png` - AdaGrad code
- `page115_img202.png` - SVM vs Softmax loss comparison
