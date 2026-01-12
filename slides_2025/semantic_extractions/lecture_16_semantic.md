# Lecture 16: Multi-Modal Foundation Models

## From Single-Modal to Multi-Modal

```
    EVOLUTION OF MODELS:

    ┌─────────────────────────────────────────────────────────────────┐
    │                                                                 │
    │   SINGLE-MODAL MODELS:                                          │
    │   ┌─────────────┐  ┌─────────────┐  ┌─────────────┐            │
    │   │   Vision    │  │   Language  │  │    Audio    │            │
    │   │   (CNN/ViT) │  │   (GPT/BERT)│  │  (Wav2Vec)  │            │
    │   │             │  │             │  │             │            │
    │   │  Images     │  │    Text     │  │   Speech    │            │
    │   └─────────────┘  └─────────────┘  └─────────────┘            │
    │         │                │                │                    │
    │         │                │                │                    │
    │         ▼                ▼                ▼                    │
    │   ┌─────────────────────────────────────────────────┐          │
    │   │           MULTI-MODAL FOUNDATION MODEL          │          │
    │   │                                                 │          │
    │   │   Image + Text + Audio + Video + ...           │          │
    │   │                                                 │          │
    │   │         Unified representation                 │          │
    │   └─────────────────────────────────────────────────┘          │
    │                                                                 │
    └─────────────────────────────────────────────────────────────────┘
```

## CLIP Architecture Revisited

```
    CONTRASTIVE LANGUAGE-IMAGE PRETRAINING:

    ┌─────────────────────────────────────────────────────────────────┐
    │                         CLIP                                    │
    │                                                                 │
    │   ┌─────────────────┐         ┌─────────────────┐              │
    │   │     Image       │         │      Text       │              │
    │   │   Encoder       │         │    Encoder      │              │
    │   │   (ViT-L/14)    │         │  (Transformer)  │              │
    │   └────────┬────────┘         └────────┬────────┘              │
    │            │                           │                        │
    │            ▼                           ▼                        │
    │        ┌───────┐                   ┌───────┐                    │
    │        │ I_emb │                   │ T_emb │                    │
    │        └───┬───┘                   └───┬───┘                    │
    │            │                           │                        │
    │            └───────────┬───────────────┘                        │
    │                        │                                        │
    │                 Cosine Similarity                               │
    │                        │                                        │
    │   ┌────────────────────┼────────────────────┐                   │
    │   │  Similarity Matrix │                    │                   │
    │   │  ┌─────────────────┴──────────────────┐│                   │
    │   │  │ "a dog" "a cat" "car" ...          ││                   │
    │   │  │  [0.9]   [0.1]  [0.0]   Image 1   ││                   │
    │   │  │  [0.1]   [0.8]  [0.1]   Image 2   ││                   │
    │   │  │  [0.0]   [0.1]  [0.9]   Image 3   ││                   │
    │   │  └────────────────────────────────────┘│                   │
    │   │  Contrastive loss: maximize diagonal   │                   │
    │   └─────────────────────────────────────────┘                   │
    └─────────────────────────────────────────────────────────────────┘
```

## Vision-Language Models (VLMs)

```
    ARCHITECTURE PATTERNS:

    ┌─────────────────────────────────────────────────────────────────┐
    │   PATTERN 1: Frozen LLM + Vision Encoder                       │
    │                                                                 │
    │   Image ──► Vision Encoder ──► Projection ──► [LLM]           │
    │                                     │           │              │
    │   Text ────────────────────────────────────────►               │
    │                                                                 │
    │   Examples: LLaVA, BLIP-2, Flamingo                            │
    └─────────────────────────────────────────────────────────────────┘

    ┌─────────────────────────────────────────────────────────────────┐
    │   PATTERN 2: End-to-End Training                               │
    │                                                                 │
    │   Image + Text ──► Unified Transformer ──► Output             │
    │                                                                 │
    │   Examples: GPT-4V, Gemini, Claude                             │
    └─────────────────────────────────────────────────────────────────┘


    LLAVA ARCHITECTURE:

    ┌─────────────────────────────────────────────────────────────────┐
    │                         LLaVA                                   │
    │                                                                 │
    │   Image ──► CLIP ViT ──► Linear Projection ──┐                 │
    │                                              │                  │
    │                                              ▼                  │
    │   "Describe this image" ──────────────────► LLaMA ──► Response │
    │                                                                 │
    │   Visual tokens concatenated with text tokens                  │
    │   LLM generates response conditioned on both                   │
    └─────────────────────────────────────────────────────────────────┘
```

## Multimodal Tasks

```
    ┌─────────────────────────────────────────────────────────────────┐
    │                    MULTIMODAL CAPABILITIES                      │
    ├─────────────────────────────────────────────────────────────────┤
    │                                                                 │
    │   IMAGE CAPTIONING:                                            │
    │   [Image] ──► "A dog playing with a ball in the park"         │
    │                                                                 │
    │   VISUAL QA:                                                    │
    │   [Image] + "What color is the car?" ──► "Red"                │
    │                                                                 │
    │   IMAGE GENERATION:                                            │
    │   "A cat wearing a hat" ──► [Generated Image]                 │
    │                                                                 │
    │   OCR + UNDERSTANDING:                                         │
    │   [Document Image] + "What is the total?" ──► "$150.00"       │
    │                                                                 │
    │   VIDEO UNDERSTANDING:                                         │
    │   [Video] + "What happened?" ──► "Person fell off bike"       │
    │                                                                 │
    │   EMBODIED AI:                                                  │
    │   [Robot View] + "Pick up the red cup" ──► [Actions]          │
    └─────────────────────────────────────────────────────────────────┘
```

## BLIP-2: Bridging Vision and Language

```
    Q-FORMER: Efficient Vision-Language Connection

    ┌─────────────────────────────────────────────────────────────────┐
    │                         BLIP-2                                  │
    │                                                                 │
    │   ┌─────────────────────────────────────────────────┐          │
    │   │              Frozen Image Encoder               │          │
    │   │                   (ViT-G)                       │          │
    │   └──────────────────────┬──────────────────────────┘          │
    │                          │                                      │
    │                          ▼                                      │
    │   ┌─────────────────────────────────────────────────┐          │
    │   │                 Q-Former                         │          │
    │   │   ┌─────────────────────────────────────────┐   │          │
    │   │   │  Learnable Query Tokens                 │   │          │
    │   │   │  ┌───┬───┬───┬───┬───┐                  │   │          │
    │   │   │  │ Q │ Q │ Q │...│ Q │  (32 queries)   │   │          │
    │   │   │  └─┬─┴─┬─┴─┬─┴───┴─┬─┘                  │   │          │
    │   │   │    │   │   │       │                    │   │          │
    │   │   │    └───┴───┴───────┘                    │   │          │
    │   │   │    Cross-attention with image features │   │          │
    │   │   └─────────────────────────────────────────┘   │          │
    │   └──────────────────────┬──────────────────────────┘          │
    │                          │ Visual representations              │
    │                          ▼                                      │
    │   ┌─────────────────────────────────────────────────┐          │
    │   │              Frozen LLM (OPT / FlanT5)          │          │
    │   └─────────────────────────────────────────────────┘          │
    │                                                                 │
    │   Key: Q-Former bridges modalities without fine-tuning LLM    │
    └─────────────────────────────────────────────────────────────────┘
```

## Text-to-Image Generation

```
    STABLE DIFFUSION PIPELINE:

    ┌─────────────────────────────────────────────────────────────────┐
    │                                                                 │
    │   Text: "astronaut riding horse on mars"                       │
    │           │                                                     │
    │           ▼                                                     │
    │   ┌───────────────┐                                            │
    │   │ CLIP Text     │                                            │
    │   │ Encoder       │                                            │
    │   └───────┬───────┘                                            │
    │           │ text embeddings                                    │
    │           ▼                                                     │
    │   ┌─────────────────────────────────────────────────┐          │
    │   │              U-Net (Denoising)                   │          │
    │   │                                                  │          │
    │   │   Noise z_T ──► Cross-Attention ──► z_{T-1}    │          │
    │   │                  with text          │           │          │
    │   │                                     │           │          │
    │   │                  ... × T steps ...  │           │          │
    │   │                                     ▼           │          │
    │   │                                    z_0          │          │
    │   └────────────────────────────────────┬────────────┘          │
    │                                        │                        │
    │                                        ▼                        │
    │   ┌───────────────────────────────────────────────┐            │
    │   │              VAE Decoder                       │            │
    │   │              z_0 ──► Image (512×512)          │            │
    │   └───────────────────────────────────────────────┘            │
    └─────────────────────────────────────────────────────────────────┘
```

## Foundation Model Scaling

```
    EMERGENT CAPABILITIES WITH SCALE:

    ┌─────────────────────────────────────────────────────────────────┐
    │   Model Size    │  Capabilities                                │
    ├─────────────────┼──────────────────────────────────────────────┤
    │   ~1B params    │  Basic understanding, simple tasks           │
    │   ~10B params   │  Better reasoning, few-shot learning         │
    │   ~100B params  │  Complex reasoning, chain-of-thought         │
    │   ~1T params    │  Emergent abilities, multimodal mastery     │
    └─────────────────────────────────────────────────────────────────┘

    GPT-4V / GEMINI / CLAUDE CAPABILITIES:

    ┌─────────────────────────────────────────────────────────────────┐
    │   • Read and understand complex documents/charts               │
    │   • Spatial reasoning about images                             │
    │   • Generate code from UI screenshots                          │
    │   • Multi-turn visual dialogue                                 │
    │   • Scientific figure analysis                                 │
    │   • Real-world knowledge integration                           │
    └─────────────────────────────────────────────────────────────────┘
```

## Key Takeaways

```
┌────────────────────────────────────────────────────────────────────┐
│ 1. Multi-modal models combine vision + language (+ other modes)   │
│    in unified representations                                      │
│                                                                    │
│ 2. CLIP-style contrastive pretraining aligns image-text spaces    │
│    enabling zero-shot transfer                                     │
│                                                                    │
│ 3. VLMs (LLaVA, BLIP-2): connect frozen vision encoders to LLMs  │
│    via projection layers or Q-Former                              │
│                                                                    │
│ 4. Text-to-image (Stable Diffusion): diffusion in latent space   │
│    with CLIP text conditioning via cross-attention                │
│                                                                    │
│ 5. Foundation models show emergent capabilities at scale:         │
│    complex reasoning, instruction following, few-shot learning    │
│                                                                    │
│ 6. Future: unified models handling any input/output modality     │
│    (text, image, audio, video, actions)                           │
└────────────────────────────────────────────────────────────────────┘
```
