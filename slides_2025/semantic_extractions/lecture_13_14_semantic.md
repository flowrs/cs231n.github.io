# Lectures 13-14: Generative Models

## Generative Models Overview

```
    DISCRIMINATIVE vs GENERATIVE:

    DISCRIMINATIVE:              GENERATIVE:
    Learn P(y|x)                 Learn P(x) or P(x,y)

    "Given image, predict       "Model the distribution of
     label"                      images themselves"

    ┌───────────┐               ┌───────────┐
    │   Image   │               │   Noise   │
    │     x     │               │     z     │
    └─────┬─────┘               └─────┬─────┘
          │                           │
          ▼                           ▼
    ┌───────────┐               ┌───────────┐
    │   Model   │               │   Model   │
    └─────┬─────┘               └─────┬─────┘
          │                           │
          ▼                           ▼
    ┌───────────┐               ┌───────────┐
    │  "cat"    │               │   Image   │
    │  (label)  │               │   (new!)  │
    └───────────┘               └───────────┘


    GENERATIVE MODEL FAMILIES:

    ┌──────────────────────────────────────────────────────────────────┐
    │                                                                  │
    │   Autoregressive     VAE           GAN          Diffusion       │
    │   ┌────────────┐  ┌────────┐  ┌────────────┐  ┌────────────┐    │
    │   │PixelCNN    │  │Encoder │  │ Generator  │  │ Denoise    │    │
    │   │GPT (images)│  │Decoder │  │Discriminator│  │ step by    │    │
    │   │pixel by    │  │+latent │  │adversarial │  │ step       │    │
    │   │pixel       │  │space   │  │training    │  │            │    │
    │   └────────────┘  └────────┘  └────────────┘  └────────────┘    │
    │                                                                  │
    └──────────────────────────────────────────────────────────────────┘
```

## Autoencoders (Non-Variational)

```
    ARCHITECTURE:

    ┌─────────────────────────────────────────────────────────────────┐
    │                       AUTOENCODER                               │
    │                                                                 │
    │   Input x        Latent z         Reconstructed x̂              │
    │   (H×W×C)       (small dim)       (H×W×C)                      │
    │                                                                 │
    │   ┌─────┐       ┌───────┐       ┌─────┐                        │
    │   │     │  E    │       │   D   │     │                        │
    │   │  x  │──────►│   z   │──────►│  x̂  │                        │
    │   │     │       │       │       │     │                        │
    │   └─────┘       └───────┘       └─────┘                        │
    │                                                                 │
    │   Encoder E: x → z  (compress)                                 │
    │   Decoder D: z → x̂  (reconstruct)                              │
    │                                                                 │
    │   Loss: ||x - x̂||²  (reconstruction loss)                      │
    └─────────────────────────────────────────────────────────────────┘

    LIMITATION: Can reconstruct, but can't generate new samples!
    - Latent space z has no structure
    - Random z doesn't produce meaningful image
```

## Variational Autoencoder (VAE)

```
    KEY IDEA: Learn a structured latent distribution

    ┌─────────────────────────────────────────────────────────────────┐
    │                            VAE                                  │
    │                                                                 │
    │   Input x          Latent Distribution        Reconstructed x̂  │
    │                                                                 │
    │   ┌─────┐         ┌─────────────────┐        ┌─────┐           │
    │   │     │ Encoder │      μ, σ       │Decoder │     │           │
    │   │  x  │────────►│  z ~ N(μ, σ²)   │───────►│  x̂  │           │
    │   │     │         │                 │        │     │           │
    │   └─────┘         └─────────────────┘        └─────┘           │
    │                           │                                     │
    │                    Reparameterization:                          │
    │                    z = μ + σ ⊙ ε                                │
    │                    where ε ~ N(0, 1)                            │
    └─────────────────────────────────────────────────────────────────┘

    VAE LOSS:

    L = Reconstruction Loss + KL Divergence
      = ||x - x̂||²        + KL(q(z|x) || p(z))

    ┌─────────────────────────────────────────────────────────────────┐
    │   Reconstruction: Make x̂ look like x                           │
    │   KL Divergence:  Push q(z|x) toward N(0,1)                    │
    │                   (regularizes latent space)                    │
    └─────────────────────────────────────────────────────────────────┘


    GENERATION WITH VAE:

    ┌───────────┐         ┌───────────┐
    │  Sample   │ Decoder │   New     │
    │ z ~ N(0,1)│────────►│   Image   │
    └───────────┘         └───────────┘
```

## Generative Adversarial Networks (GANs)

```
    TWO-PLAYER GAME:

    ┌─────────────────────────────────────────────────────────────────┐
    │                            GAN                                  │
    │                                                                 │
    │   ┌───────────┐        ┌───────────────┐                       │
    │   │   Noise   │        │   Generator   │                       │
    │   │ z ~ N(0,1)│───────►│      G        │                       │
    │   └───────────┘        └───────┬───────┘                       │
    │                                │                               │
    │                                ▼                               │
    │                        ┌───────────────┐                       │
    │                        │  Fake Image   │                       │
    │                        │    G(z)       │                       │
    │                        └───────┬───────┘                       │
    │                                │                               │
    │   ┌───────────┐                │                               │
    │   │Real Image │                │                               │
    │   │    x      │────────────────┼───────┐                       │
    │   └───────────┘                │       │                       │
    │                                ▼       ▼                       │
    │                        ┌───────────────┐                       │
    │                        │ Discriminator │                       │
    │                        │      D        │                       │
    │                        └───────┬───────┘                       │
    │                                │                               │
    │                                ▼                               │
    │                         Real or Fake?                          │
    └─────────────────────────────────────────────────────────────────┘

    TRAINING OBJECTIVES:

    Generator:      max log(D(G(z)))         "Fool discriminator"
    Discriminator:  max log(D(x)) + log(1-D(G(z)))  "Detect fakes"

    Minimax game:
    min_G max_D  E[log D(x)] + E[log(1 - D(G(z)))]
```

## GAN Architectures

```
    DC-GAN (Deep Convolutional GAN):

    ┌─────────────────────────────────────────────────────────────────┐
    │   Generator (Transpose Convolutions):                          │
    │                                                                 │
    │   z (100)   4×4×512   8×8×256   16×16×128   32×32×64   64×64×3 │
    │   ──────►  ────────► ───────►  ─────────► ─────────► ───────── │
    │            ConvT     ConvT      ConvT      ConvT     tanh      │
    │            +BN+ReLU  +BN+ReLU   +BN+ReLU   +BN+ReLU             │
    │                                                                 │
    │   Discriminator (Strided Convolutions):                        │
    │                                                                 │
    │   64×64×3   32×32×64  16×16×128  8×8×256   4×4×512   1 (prob)  │
    │   ────────► ────────► ─────────► ───────► ────────► ────────── │
    │             Conv+LReLU Conv+BN   Conv+BN   Conv+BN   sigmoid   │
    └─────────────────────────────────────────────────────────────────┘


    STYLEGAN:

    ┌─────────────────────────────────────────────────────────────────┐
    │   z ~ N(0,1)                                                    │
    │       │                                                         │
    │       ▼                                                         │
    │   ┌───────────┐                                                 │
    │   │ Mapping   │  8-layer MLP                                   │
    │   │ Network   │                                                 │
    │   └─────┬─────┘                                                 │
    │         │ w (style vector)                                      │
    │         │                                                       │
    │         ▼ inject at each layer (AdaIN)                         │
    │   ┌─────────────────────────────────┐                          │
    │   │   Synthesis Network             │                          │
    │   │   4×4 → 8×8 → ... → 1024×1024  │                          │
    │   │   + noise injection at each     │                          │
    │   │   layer for stochastic details  │                          │
    │   └─────────────────────────────────┘                          │
    │                                                                 │
    │   Key: w space is more disentangled than z space               │
    └─────────────────────────────────────────────────────────────────┘
```

## GAN Challenges

```
    ┌─────────────────────────────────────────────────────────────────┐
    │                    GAN TRAINING CHALLENGES                      │
    │                                                                 │
    │   1. MODE COLLAPSE                                              │
    │      Generator produces limited variety                         │
    │      ┌─────────────────────────────────┐                       │
    │      │ Real distribution    Generated  │                       │
    │      │    ●  ●  ●  ●           ●●●     │                       │
    │      │ ●           ●      (all same!)  │                       │
    │      └─────────────────────────────────┘                       │
    │                                                                 │
    │   2. TRAINING INSTABILITY                                       │
    │      - D too strong → G gets no gradient                       │
    │      - G too strong → D can't learn                            │
    │      - Careful hyperparameter tuning needed                    │
    │                                                                 │
    │   3. NO EXPLICIT LIKELIHOOD                                     │
    │      - Hard to evaluate quality objectively                    │
    │      - Use FID, IS scores instead                              │
    └─────────────────────────────────────────────────────────────────┘
```

## Diffusion Models

```
    CORE IDEA: Learn to reverse gradual noising

    ┌─────────────────────────────────────────────────────────────────┐
    │                    DIFFUSION PROCESS                            │
    │                                                                 │
    │   FORWARD PROCESS (fixed, add noise):                          │
    │                                                                 │
    │   x₀ ──► x₁ ──► x₂ ──► ... ──► x_T                            │
    │   clean   ↘      ↘              pure                           │
    │   image    +noise +noise        noise                          │
    │                                                                 │
    │   q(x_t | x_{t-1}) = N(x_t; √(1-β_t)x_{t-1}, β_t I)           │
    │                                                                 │
    ├─────────────────────────────────────────────────────────────────┤
    │   REVERSE PROCESS (learned, denoise):                          │
    │                                                                 │
    │   x_T ──► x_{T-1} ──► ... ──► x₁ ──► x₀                       │
    │   noise    ↘           ↘        ↘    clean                    │
    │            denoise    denoise  denoise                         │
    │                                                                 │
    │   p_θ(x_{t-1} | x_t) = N(x_{t-1}; μ_θ(x_t, t), Σ_θ(x_t, t))  │
    │                                                                 │
    │   Neural network learns to predict: μ_θ (or equivalently, ε)  │
    └─────────────────────────────────────────────────────────────────┘


    TRAINING:

    ┌─────────────────────────────────────────────────────────────────┐
    │   1. Sample clean image x₀                                      │
    │   2. Sample timestep t ~ Uniform(1, T)                         │
    │   3. Sample noise ε ~ N(0, I)                                  │
    │   4. Create noisy image: x_t = √ᾱ_t x₀ + √(1-ᾱ_t) ε           │
    │   5. Train network to predict ε:                               │
    │      Loss = ||ε - ε_θ(x_t, t)||²                               │
    └─────────────────────────────────────────────────────────────────┘


    SAMPLING:

    ┌─────────────────────────────────────────────────────────────────┐
    │   Start: x_T ~ N(0, I)  (pure noise)                           │
    │                                                                 │
    │   For t = T, T-1, ..., 1:                                      │
    │       ε = ε_θ(x_t, t)   # predict noise                        │
    │       x_{t-1} = denoise(x_t, ε)  # remove predicted noise      │
    │                                                                 │
    │   Return x₀  (clean image!)                                     │
    └─────────────────────────────────────────────────────────────────┘
```

## Diffusion Model Architecture

```
    U-NET FOR DENOISING:

    ┌─────────────────────────────────────────────────────────────────┐
    │                                                                 │
    │   Input: (noisy image x_t, timestep t)                         │
    │                                                                 │
    │   ┌─────────────────────────────────────────────────────────┐   │
    │   │                      U-Net                               │   │
    │   │                                                          │   │
    │   │   Encoder              Decoder                           │   │
    │   │   ┌───┐               ┌───┐                              │   │
    │   │   │   │───────────────│   │  skip connections           │   │
    │   │   └─┬─┘               └─▲─┘                              │   │
    │   │     │                   │                                │   │
    │   │   ┌─▼─┐               ┌─┴─┐                              │   │
    │   │   │   │───────────────│   │                              │   │
    │   │   └─┬─┘               └─▲─┘                              │   │
    │   │     │                   │                                │   │
    │   │   ┌─▼─┐               ┌─┴─┐                              │   │
    │   │   │   │───────────────│   │                              │   │
    │   │   └─┬─┘               └─▲─┘                              │   │
    │   │     │     ┌─────┐      │                                │   │
    │   │     └────►│ mid │──────┘                                │   │
    │   │           └─────┘                                        │   │
    │   │                                                          │   │
    │   │   + Time embedding (sinusoidal + MLP)                   │   │
    │   │   + Self-attention layers                               │   │
    │   └──────────────────────────────────────────────────────────┘   │
    │                                                                 │
    │   Output: predicted noise ε                                     │
    └─────────────────────────────────────────────────────────────────┘
```

## Conditional Generation

```
    TEXT-TO-IMAGE (Stable Diffusion / DALL-E):

    ┌─────────────────────────────────────────────────────────────────┐
    │                                                                 │
    │   Text: "a cat wearing a hat"                                  │
    │           │                                                     │
    │           ▼                                                     │
    │   ┌───────────────┐                                            │
    │   │ Text Encoder  │  (CLIP or T5)                              │
    │   └───────┬───────┘                                            │
    │           │ text embedding                                     │
    │           ▼                                                     │
    │   ┌───────────────────────────────────────────────────┐        │
    │   │              Diffusion U-Net                       │        │
    │   │                                                    │        │
    │   │   x_t (noisy image) ──► Cross-Attention ◄── text  │        │
    │   │                          with text                 │        │
    │   │                              │                     │        │
    │   │                              ▼                     │        │
    │   │                        predicted ε                 │        │
    │   └───────────────────────────────────────────────────┘        │
    │                                                                 │
    │   CLASSIFIER-FREE GUIDANCE:                                    │
    │   ε = ε_uncond + w × (ε_cond - ε_uncond)                       │
    │   Higher w → stronger text influence                           │
    └─────────────────────────────────────────────────────────────────┘


    LATENT DIFFUSION (Stable Diffusion):

    ┌─────────────────────────────────────────────────────────────────┐
    │   Work in compressed latent space (faster!):                   │
    │                                                                 │
    │   Image (512×512) → VAE Encoder → Latent (64×64)              │
    │                                        │                       │
    │                                   Diffusion                    │
    │                                   (in latent space)            │
    │                                        │                       │
    │   Image (512×512) ← VAE Decoder ← Latent (64×64)              │
    └─────────────────────────────────────────────────────────────────┘
```

## Model Comparison

```
    ┌────────────────────────────────────────────────────────────────┐
    │              GENERATIVE MODEL COMPARISON                       │
    ├───────────┬────────────┬────────────┬─────────────┬────────────┤
    │           │    VAE     │    GAN     │  Diffusion  │ Autoregres│
    ├───────────┼────────────┼────────────┼─────────────┼────────────┤
    │ Quality   │  Medium    │   High     │  Very High  │   High    │
    │ Diversity │  High      │   Lower    │  High       │   High    │
    │ Training  │  Stable    │  Unstable  │  Stable     │   Stable  │
    │ Sampling  │  Fast      │   Fast     │  Slow       │   Slow    │
    │ Likelihood│  Approx    │   None     │  Yes        │   Exact   │
    │ Latent    │  Yes       │   Yes      │  No*        │   No      │
    └───────────┴────────────┴────────────┴─────────────┴────────────┘

    * Diffusion can be combined with VAE (latent diffusion)
```

## Key Takeaways

```
┌────────────────────────────────────────────────────────────────────┐
│ 1. Autoencoders compress and reconstruct; VAE adds structure       │
│    to enable generation via sampling from N(0,1)                   │
│                                                                    │
│ 2. GANs use adversarial training (Generator vs Discriminator)     │
│    - High quality but unstable training                           │
│    - StyleGAN: state-of-art face generation                       │
│                                                                    │
│ 3. Diffusion models: learn to reverse gradual noising             │
│    - Very stable training                                          │
│    - High quality and diversity                                    │
│    - Slow sampling (many denoising steps)                         │
│                                                                    │
│ 4. Conditional generation (text-to-image):                        │
│    - Cross-attention to inject text                               │
│    - Classifier-free guidance for control                         │
│                                                                    │
│ 5. Latent diffusion (Stable Diffusion):                          │
│    - Diffusion in compressed latent space                         │
│    - Much faster than pixel-space diffusion                       │
│                                                                    │
│ 6. Current SOTA: Diffusion models dominate image generation       │
│    (DALL-E, Midjourney, Stable Diffusion)                         │
└────────────────────────────────────────────────────────────────────┘
```
