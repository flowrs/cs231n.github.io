# CS231n: Deep Learning for Computer Vision
## Lecture 1: Introduction (Part 1)

**Instructors:** Fei-Fei Li, Ehsan Adeli, Zane Durante
**Date:** April 1, 2025

---

## Slide 1: Title

# CS231n: Deep Learning for Computer Vision
## Lecture 1: Introduction

---

## Slide 2-3: Welcome to CS231n

Course history spanning 2015-2023 with various instructors and teaching assistants.

---

## Slide 4: CS231n's Ten Year Anniversary: Returning Lecturers

| Lecturer | Years |
|----------|-------|
| Fei-Fei Li | 2015-2025 |
| Andrej Karpathy | 2015-2016 |
| Justin Johnson | 2016-2019, 2025 |
| Serena Yeung | 2017-2019 |
| Ranjay Krishna | 2020-2021 |
| Danfei Xu | 2020-2021 |
| Jiajun Wu | 2022 |
| Ruohan Gao | 2022-2023 |
| Yunzhu Li | 2023 |
| Ehsan Adeli | 2024-2025 |
| Zane Durante | 2024-2025 |

---

## Slides 5-12: Field Relationships Venn Diagram

```
┌─────────────────────────────────────────────────────────────────────────┐
│                         ARTIFICIAL INTELLIGENCE                          │
│    ┌──────────────────────────────────────────────────────────────┐     │
│    │                                                              │     │
│    │  ┌──────────────────┐      ┌─────────────────────────────┐  │     │
│    │  │                  │      │      MACHINE LEARNING       │  │     │
│    │  │   COMPUTER       │      │                             │  │     │
│    │  │   VISION         │      │    ┌─────────────────┐      │  │     │
│    │  │                  │      │    │                 │      │  │     │
│    │  │              ┌───┼──────┼────┤  DEEP LEARNING  │      │  │     │
│    │  │              │###│      │    │                 │      │  │     │
│    │  │              │###│ <────┼────│  THIS CLASS     │      │  │     │
│    │  │              │###│      │    │                 │      │  │     │
│    │  │              └───┼──────┼────┤                 │      │  │     │
│    │  │                  │      │    └─────────────────┘      │  │     │
│    │  └──────────────────┘      │                             │  │     │
│    │                            └─────────────────────────────┘  │     │
│    │                                                              │     │
│    │     ┌─────────────────────┐    ┌────────────────────┐       │     │
│    │     │  NATURAL LANGUAGE   │    │      SPEECH        │       │     │
│    │     │    PROCESSING       │    │    RECOGNITION     │       │     │
│    │     └─────────────────────┘    └────────────────────┘       │     │
│    │                                                              │     │
│    │  ROBOTICS                                                    │     │
│    └──────────────────────────────────────────────────────────────┘     │
│                                                                         │
│  Related Fields: Mathematics, Neuroscience, Computer Science,           │
│                  Physics, Biology, Psychology                           │
└─────────────────────────────────────────────────────────────────────────┘

The ### shaded region represents "This class" - the intersection of
Computer Vision and Deep Learning within Machine Learning within AI.
```

---

## Slide 13: Today's Agenda

- A brief history of computer vision and deep learning
- CS231n overview

---

## Slide 14: Evolution's Big Bang

**Cambrian Explosion: 530-540 million years B.C.**

The rapid diversification of life forms, including the evolution of eyes.

---

## Slide 15: Eyes Across Species

[Images showing diversity of eyes: octopus, insect compound eyes, chameleon, human baby]

---

## Slide 16: Camera Obscura

```
CAMERA OBSCURA PRINCIPLE (Leonardo da Vinci, 16th Century)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

        Object                      Inverted Image
          ●                              ○
           \                            /
            \     ┌─────────┐          /
             \    │         │         /
              \   │  tiny   │        /
               \  │  hole   │       /
                \ │    ○    │      /
                 \│         │     /
                  │         │    /
                  │         │   /
                  └─────────┘  /
                              ○
                        Projected Image

Light passes through a small aperture, projecting an inverted
image on the opposite surface.

Historical Sources:
- Gemma Frisius, 1545
- Leonardo da Vinci, 16th Century AD
- Encyclopedia, 18th Century
```

---

## Slide 17: Computer Vision is Everywhere!

Applications shown:
- Photographers and cameras
- Drones
- Smartphones (face detection)
- Security cameras
- Mars rovers
- Underwater exploration
- Google Glass

---

## Slide 18: Where did we come from?

*Transition to history section*

---

## Slide 19: Hubel and Wiesel, 1959

```
HUBEL & WIESEL'S VISUAL CORTEX EXPERIMENTS (1959)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Experimental Setup:
                                    ┌─────────────────────┐
    ┌─────────┐                     │   STIMULUS SCREEN   │
    │   CAT   │                     │                     │
    │  ┌───┐  │ ──────────────────► │        /            │
    │  │ ● │  │  Measures brain     │       /             │
    │  └───┘  │  activity           │      / (oriented    │
    │ (brain) │                     │     /   bar)        │
    └─────────┘                     └─────────────────────┘

Neural Response Patterns:
━━━━━━━━━━━━━━━━━━━━━━━━━

SIMPLE CELLS: Response to specific rotation and orientation
┌────────────────────────────────────────────────────────────┐
│                                                            │
│  Stimulus:    |    —    /    \    ●    ◯                  │
│               ↑    ↑    ↑    ↑    ↑    ↑                  │
│  Response: [HIGH][MED][MED][LOW][LOW][NONE]               │
│                                                            │
│  Each simple cell responds maximally to a specific         │
│  orientation of edges or lines                             │
└────────────────────────────────────────────────────────────┘

COMPLEX CELLS: Response to light orientation and movement,
               with some translation invariance

┌────────────────────────────────────────────────────────────┐
│                                                            │
│  Position 1:  ╲         Position 2:    ╲                  │
│                 responds                  responds         │
│                                                            │
│  Same orientation at different positions → similar         │
│  response (translation invariance)                         │
└────────────────────────────────────────────────────────────┘
```

**Key Discovery:** The visual cortex has a hierarchical organization with simple and complex cells that detect oriented edges and bars.

---

## Slide 20: Larry Roberts, 1963

```
MACHINE PERCEPTION OF THREE-DIMENSIONAL SOLIDS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

(a) Original Picture     (b) Differentiated      (c) Feature Points
                              Picture                 Selected

    ┌───────────┐           ┌───────────┐          ╳───────────╳
   /│          /│          /│          /│         /│          /│
  / │         / │         / │         / │        ╳ │         ╳ │
 ┌───────────┐  │        ┌───────────┐  │       ╳───────────╳  ╳
 │           │  │        │           │  │       │╳          │╳ │
 │   3D      │  │        │  edge     │  │       │ ╳   ╳╳   │ ╳ │
 │   solid   │ /         │  lines    │ /        │  ╳ ╳ ╳   │  ╳
 │           │/          │           │/         │   ╳   ╳  │  /
 └───────────┘           └───────────┘          ╳───────────╳/

Roberts' PhD thesis: First work on extracting 3D structure
from 2D images using edge detection and geometric reasoning.
```

---

## Slide 21: The Summer Vision Project (MIT, 1966)

> "The summer vision project is an attempt to use our summer workers
> effectively in the construction of a significant part of a visual system.
> The particular task was chosen partly because it can be segmented into
> sub-problems which will allow individuals to work independently and yet
> participate in the construction of a system complex enough to be a real
> landmark in the development of 'pattern recognition'."
>
> — Seymour Papert, MIT, July 7, 1966

---

## Slide 22: David Marr's Vision Theory (1970s)

```
STAGES OF VISUAL REPRESENTATION (David Marr, 1970s)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

┌─────────────┐    ┌─────────────┐    ┌─────────────┐    ┌─────────────┐
│   INPUT     │    │   PRIMAL    │    │   2½-D      │    │    3-D      │
│   IMAGE     │───►│   SKETCH    │───►│   SKETCH    │───►│   MODEL     │
│             │    │             │    │             │    │             │
├─────────────┤    ├─────────────┤    ├─────────────┤    ├─────────────┤
│             │    │ Zero        │    │ Local       │    │ 3-D models  │
│ Perceived   │    │ crossings,  │    │ surface     │    │ hierarchi-  │
│ intensities │    │ blobs,      │    │ orientation │    │ cally       │
│             │    │ edges,      │    │ and discon- │    │ organized   │
│             │    │ bars, ends, │    │ tinuities   │    │ in terms    │
│             │    │ virtual     │    │ in depth    │    │ of surface  │
│             │    │ lines,      │    │ and surface │    │ and         │
│             │    │ groups,     │    │ orientation │    │ volumetric  │
│             │    │ curves,     │    │             │    │ primitives  │
│             │    │ boundaries  │    │             │    │             │
└─────────────┘    └─────────────┘    └─────────────┘    └─────────────┘

Example: Basketball

┌─────────────┐    ┌─────────────┐    ┌─────────────┐    ┌─────────────┐
│   🏀        │    │   ╭───╮     │    │   ◐         │    │     ●       │
│  (photo)    │───►│   │   │     │───►│  (depth)    │───►│   (sphere)  │
│             │    │   ╰───╯     │    │             │    │             │
│             │    │  (edges)    │    │             │    │             │
└─────────────┘    └─────────────┘    └─────────────┘    └─────────────┘
```

---

## Slide 23: Recognition via Parts (1970s)

```
GENERALIZED CYLINDERS              PICTORIAL STRUCTURES
(Brooks & Binford, 1979)          (Fischler & Elshlager, 1973)

        ┌───┐                              ○
        │   │  ← head                     /│\
        └───┘                            / │ \
       ┌─────┐                          ○──○──○
       │     │  ← torso                    │
       │     │                          ○──┼──○
       └─────┘                         /   │   \
      ┌─┐   ┌─┐                       ○    │    ○
      │ │   │ │  ← arms                    │
      └─┘   └─┘                           ○
      ┌─┐   ┌─┐                          / \
      │ │   │ │  ← legs                 ○   ○
      │ │   │ │
      └─┘   └─┘

Objects represented as          Objects as graph structures
collections of 3D volumetric    with parts (nodes) and
primitives (cylinders, cones)   spatial relationships (edges)
```

---

## Slide 24: Recognition via Edge Detection (1980s)

**John Canny, 1986** - Canny Edge Detector
**David Lowe, 1987**

```
INPUT IMAGE                    EDGE DETECTION OUTPUT

┌───────────────────┐         ┌───────────────────┐
│  ┌─┐ ┌─┐ ┌─┐     │         │  ┌─┐ ┌─┐ ┌─┐     │
│  │ │ │ │ │ │     │   ──►   │  │ │ │ │ │ │     │
│  │ │ │ │ │ │     │         │  │ │ │ │ │ │     │
│  └─┘ └─┘ └─┘     │         │  └─┘ └─┘ └─┘     │
│    Razors        │         │    Edge outlines  │
└───────────────────┘         └───────────────────┘
```

---

## Slide 25: Arriving at an "AI Winter"

- Enthusiasm (and funding!) for AI research dwindled
- "Expert Systems" failed to deliver on their promises
- But subfields of AI continued to grow:
  - Computer vision, NLP, robotics, computational biology, etc.

---

## Slides 26-31: Cognitive and Neuroscience Work

### Biederman (1972): Perceiving Real-World Scenes
Scene context helps object recognition - jumbled scenes are harder to parse.

### Potter (1970s): Rapid Serial Visual Perception (RSVP)
Humans can categorize images shown for very brief durations.

### Thorpe et al. (1996): Speed of Processing
Human visual system can detect animals in images in ~150ms!

### Kanwisher et al. (1997), Epstein & Kanwisher (1998)
Neural correlates of object and scene recognition:
- Fusiform Face Area (FFA) responds to faces
- Parahippocampal Place Area (PPA) responds to scenes/places

---

## Slide 32: Recognition via Grouping (1990s)

**Normalized Cuts** - Shi and Malik, 1997

```
IMAGE SEGMENTATION USING GRAPH CUTS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Original Image          Segmented Result
┌─────────────────┐     ┌─────────────────┐
│     ┌───────┐   │     │     ┌───────┐   │
│     │ MONK  │   │     │ ████│ MONK  │███│
│     │       │   │     │ ████│       │███│
│     └───┬───┘   │ ──► │ ████└───┬───┘███│
│         │       │     │ ░░░░░░░░│░░░░░░░│
│ ════════╧══════ │     │ ░░░░░░░░╧░░░░░░░│
│  (railing/bg)   │     │  (background)   │
└─────────────────┘     └─────────────────┘

Algorithm treats image as a graph and finds optimal cuts
to separate regions based on similarity.
```

---

## Slide 33: Recognition via Matching (2000s)

**SIFT: Scale-Invariant Feature Transform** - David Lowe, 1999

```
SIFT FEATURE MATCHING
━━━━━━━━━━━━━━━━━━━━━

Image 1: Stop Sign         Image 2: Stop Sign (different view)
┌─────────────────┐        ┌─────────────────┐
│      ____       │        │    ____         │
│     /STOP\      │        │   /STOP\        │
│    │  ●   │     │========│==│  ●   │       │
│    │    ● │     │========│==│    ● │       │
│     \____/      │========│===\____/        │
│         ●       │========│=======●         │
└─────────────────┘        └─────────────────┘
       ╲                           ╱
        ╲═════════════════════════╱
         Feature correspondences

SIFT detects keypoints and creates descriptors that are
invariant to scale, rotation, and illumination changes.
```

---

## Slide 34: Face Detection

**Viola and Jones, 2001**

One of the first successful applications of machine learning to vision.

```
VIOLA-JONES FACE DETECTION
━━━━━━━━━━━━━━━━━━━━━━━━━━

┌──────────────────────────────────────┐
│                  ┌──────┐            │
│      ┌──────┐    │ FACE │   ┌──────┐ │
│      │ FACE │    │  ✓   │   │ FACE │ │
│      │  ✓   │    └──────┘   │  ✓   │ │
│      └──────┘               └──────┘ │
│                                      │
│  Uses Haar-like features and         │
│  cascade of classifiers for          │
│  real-time face detection            │
└──────────────────────────────────────┘
```

---

## Slide 35: Benchmark Datasets (2004-2007)

**Caltech 101** (2004): 101 object categories, ~40-800 images each
**PASCAL Visual Object Challenge** (2007): Object detection and classification

---

## Slide 36: The Perceptron (Frank Rosenblatt, ~1957-1958)

```
THE PERCEPTRON
━━━━━━━━━━━━━━

          x₁ ───┐
                 ╲
          x₂ ────●────► y = f(Σwᵢxᵢ + b)
                 ╱
          x₃ ───┘

A single-layer neural network for binary classification.
```

---

## Slide 37: Minsky and Papert, 1969

```
THE XOR PROBLEM
━━━━━━━━━━━━━━━

   y                    XOR Truth Table
   │                    ┌───┬───┬───────┐
   │  ●           ●     │ X │ Y │ F(X,Y)│
   │                    ├───┼───┼───────┤
   │                    │ 0 │ 0 │   0   │
   │                    │ 0 │ 1 │   1   │
   ├─────●───────●─► x  │ 1 │ 0 │   1   │
   │                    │ 1 │ 1 │   0   │
   │                    └───┴───┴───────┘

● = class 1 (output = 1)
○ = class 0 (output = 0)

Problem: No single line can separate the classes!
Perceptrons cannot learn XOR → caused disillusionment in the field.
```

---

## Slide 38: Neocognitron (Fukushima, 1980)

```
NEOCOGNITRON ARCHITECTURE
━━━━━━━━━━━━━━━━━━━━━━━━━

  Input     S1      C1      S2      C2      S3      C3    Output
    │       │       │       │       │       │       │       │
┌───┴───┐ ┌─┴─┐   ┌─┴─┐   ┌─┴─┐   ┌─┴─┐   ┌─┴─┐   ┌─┴─┐  ┌─┴─┐
│       │ │   │   │   │   │   │   │   │   │   │   │   │  │   │
│ IMAGE │►│ S │──►│ C │──►│ S │──►│ C │──►│ S │──►│ C │─►│OUT│
│       │ │   │   │   │   │   │   │   │   │   │   │   │  │   │
└───────┘ └───┘   └───┘   └───┘   └───┘   └───┘   └───┘  └───┘
            │       │       │       │       │       │
            ▼       ▼       ▼       ▼       ▼       ▼
          Simple  Complex Simple  Complex Simple  Complex
          cells   cells   cells   cells   cells   cells

Inspired by Hubel & Wiesel's findings:
- S-cells (Simple): Feature detection (like convolution)
- C-cells (Complex): Pooling for translation invariance

Problem: No practical training algorithm at the time!
```

---

## Slide 39: Backpropagation (Rumelhart, Hinton, Williams, 1986)

```
BACKPROPAGATION
━━━━━━━━━━━━━━━

                  ∂Eₚ     ∂Eₚ   ∂oₚⱼ
Forward Pass:     ──── = ──── · ────
                  ∂wⱼᵢ    ∂oₚⱼ  ∂wⱼᵢ

     Input          Hidden         Output
     Layer          Layer          Layer

       ○              ○
        ╲            ╱ ╲
         ╲──────────●───╲
        ╱ ╲        ╱ ╲   ╲
       ○   ╲──────●   ╲───●──► Error Eₚ
        ╲   ╲    ╱ ╲   ╲ ╱
         ╲───────●───╲──╳
        ╱       ╱     ╲
       ○       ╱       ╲
              ○         ○

    ←─────────────────────────
       Gradients flow backward

Key insight: Use chain rule to compute gradients of loss
with respect to all weights, enabling training of
multi-layer networks.
```

---

## Slide 40: Convolutional Networks - LeNet (LeCun et al, 1998)

```
LeNet-5 ARCHITECTURE (LeCun et al., 1998)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

         INPUT        CONVOLUTIONS          SUBSAMPLING        FULLY CONNECTED
         32x32
                    ┌─────────────────────────────────────────────────────────┐
                    │                                                         │
    ┌─────────┐     │  ┌────┐    ┌────┐    ┌────┐    ┌────┐    ┌────┐       │
    │         │     │  │C1  │    │S2  │    │C3  │    │S4  │    │C5  │       │
    │    K    │────►│  │    │───►│    │───►│    │───►│    │───►│    │──┐    │
    │         │     │  │6@  │    │6@  │    │16@ │    │16@ │    │120 │  │    │
    │ (input) │     │  │28x │    │14x │    │10x │    │5x  │    │    │  │    │
    └─────────┘     │  │28  │    │14  │    │10  │    │5   │    │    │  │    │
                    │  └────┘    └────┘    └────┘    └────┘    └────┘  │    │
                    │     │          │         │          │         │  │    │
                    │     ▼          ▼         ▼          ▼         ▼  │    │
                    │  ┌─────┐   ┌─────┐   ┌─────┐   ┌─────┐   ┌────┐│    │
                    │  │█████│   │░░░░░│   │█████│   │░░░░░│   │████││    │
                    │  │█████│   │░░░░░│   │█████│   │░░░░░│   │    ││    │
                    │  └─────┘   └─────┘   └─────┘   └─────┘   └────┘│    │
                    │  CONV      POOL      CONV      POOL      CONV  │    │
                    └───────────────────────────────────────────────────┘    │
                                                                       │    │
                                                              ┌────────┘    │
                                                              │             │
                                                              ▼             │
                                                         ┌────────┐        │
                                                         │   F6   │        │
                                                         │   84   │        │
                                                         └────┬───┘        │
                                                              │            │
                                                              ▼            │
                                                         ┌────────┐       │
                                                         │ OUTPUT │       │
                                                         │   10   │◄──────┘
                                                         │(digits)│
                                                         └────────┘

    LAYER DETAILS:
    ━━━━━━━━━━━━━━
    INPUT:  32×32 grayscale image
    C1:     6 feature maps, 5×5 kernels → 28×28
    S2:     Subsampling (avg pool) 2×2 → 14×14
    C3:     16 feature maps, 5×5 kernels → 10×10
    S4:     Subsampling 2×2 → 5×5
    C5:     120 feature maps, 5×5 kernels → 1×1
    F6:     84 fully connected neurons
    OUTPUT: 10 classes (digits 0-9)

Applied backprop to Neocognitron-like architecture.
Deployed commercially by NEC for handwritten check processing.
Very similar to modern convolutional networks!
```

---

## Slides 41-42: 2000s "Deep Learning"

Research by:
- Hinton and Salakhutdinov, 2006
- Bengio et al, 2007
- Lee et al, 2009
- Glorot and Bengio, 2010

People tried to train deeper neural networks.
Not mainstream research at this time.
**No good dataset to work on.**

---

## Slide 43: ImageNet (Deng et al, 2009)

```
ImageNet Large Scale Visual Recognition Challenge
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

┌────────────────────────────────────────────────┐
│                                                │
│   1,000 object classes                         │
│   1,431,167 images                             │
│                                                │
│   Challenge: Given an image, output top-5      │
│   most likely class labels                     │
│                                                │
│   Example output:                              │
│   • Scale                                      │
│   • T-shirt                                    │
│   • Steel drum  ← (correct)                    │
│   • Drumstick                                  │
│   • Mud turtle                                 │
│                                                │
└────────────────────────────────────────────────┘
```

---

## Slides 44-45: ImageNet Challenge Results

```
IMAGENET CLASSIFICATION ERROR RATES (%)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

30 │ ▓▓▓ 28.2
   │ ▓▓▓
25 │ ▓▓▓  ▓▓▓ 25.8
   │ ▓▓▓  ▓▓▓
20 │ ▓▓▓  ▓▓▓
   │ ▓▓▓  ▓▓▓  ▓▓▓ 16.4  ← AlexNet (2012)
15 │ ▓▓▓  ▓▓▓  ▓▓▓
   │ ▓▓▓  ▓▓▓  ▓▓▓  ▓▓▓ 11.7
10 │ ▓▓▓  ▓▓▓  ▓▓▓  ▓▓▓
   │ ▓▓▓  ▓▓▓  ▓▓▓  ▓▓▓  ▓▓▓ 7.3  ▓▓▓ 6.7
 5 │ ▓▓▓  ▓▓▓  ▓▓▓  ▓▓▓  ▓▓▓ ▓▓▓  ▓▓▓ ▓▓▓ 3.6  ▓▓▓ 3.0  ▓▓▓ 2.3     5.1
   │ ▓▓▓  ▓▓▓  ▓▓▓  ▓▓▓  ▓▓▓ ▓▓▓  ▓▓▓ ▓▓▓ ▓▓▓  ▓▓▓ ▓▓▓  ▓▓▓ ▓▓▓      ▓▓▓
 0 └────────────────────────────────────────────────────────────────────────
   2010 2011 2012 2013 2014 2014 2015 2016 2017 Human

   Lin  S&P  AlexNet Z&F  VGG  GoogLe ResNet Shao SENet  Human
                                  Net         et al
```

---

## Slides 46-47: AlexNet - Deep Learning Goes Mainstream

**Krizhevsky, Sutskever, and Hinton, NeurIPS 2012**

```
AlexNet ARCHITECTURE (2012)
━━━━━━━━━━━━━━━━━━━━━━━━━━━

Input: 224×224×3 RGB Image

┌─────────┐    ┌─────────┐    ┌─────────┐    ┌─────────┐    ┌─────────┐
│  CONV1  │    │  CONV2  │    │  CONV3  │    │  CONV4  │    │  CONV5  │
│ 96@55×55│───►│256@27×27│───►│384@13×13│───►│384@13×13│───►│256@13×13│
│ 11×11,s4│    │ 5×5     │    │ 3×3     │    │ 3×3     │    │ 3×3     │
└────┬────┘    └────┬────┘    └─────────┘    └─────────┘    └────┬────┘
     │              │                                             │
     ▼              ▼                                             ▼
 MaxPool        MaxPool                                       MaxPool
  3×3,s2         3×3,s2                                        3×3,s2
     │              │                                             │
     └──────────────┴─────────────────────────────────────────────┘
                                    │
                                    ▼
                    ┌─────────────────────────────┐
                    │       FC: 4096 neurons      │
                    │       FC: 4096 neurons      │
                    │       FC: 1000 (softmax)    │
                    └─────────────────────────────┘

Key innovations:
• ReLU activation (faster training)
• Dropout (regularization)
• Data augmentation
• GPU training (2 GPUs)
• ~60 million parameters

COMPARISON: AlexNet vs Neocognitron (32 years apart!)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Neocognitron (1980)              AlexNet (2012)
• Conceptually similar           • Same basic architecture
• No training algorithm          • Trained with backprop
• Small scale                    • Large scale (ImageNet)
• Theoretical                    • Practical breakthrough
```

---

## Slides 48-57: 2012 to Present - Deep Learning is Everywhere

### Applications:
- **Image Classification** - Categorizing images
- **Image Retrieval** - Finding similar images
- **Object Detection** - Locating objects with bounding boxes (Faster R-CNN)
- **Image Segmentation** - Pixel-wise classification
- **Video Classification** - Two-stream ConvNets
- **Activity Recognition** - Understanding human actions
- **Pose Estimation** - Detecting body keypoints
- **Playing Atari Games** - Deep Q-Learning
- **Medical Imaging** - Disease detection
- **Galaxy Classification** - Astronomical image analysis
- **Whale Recognition** - Wildlife identification
- **Image Captioning** - Generating text descriptions
- **Visual Relationships** - Understanding object interactions
- **Neural Style Transfer** - Artistic rendering
- **Face Generation** - GANs (Progressive Growing)
- **Text-to-Image** - DALL-E (2021)

---

## Slide 61: The Three Pillars of Deep Learning

```
┌──────────────────────────────────────────────────────────────────────┐
│                                                                      │
│    COMPUTATION          ALGORITHMS              DATA                 │
│                                                                      │
│   ┌──────────┐        ┌──────────┐         ┌──────────┐             │
│   │ ████████ │        │    ●     │         │ ▓▓▓▓▓▓▓▓ │             │
│   │ ████████ │        │   ╱│╲    │         │ ▓▓▓▓▓▓▓▓ │             │
│   │ ████████ │        │  ● ● ●   │         │ Images   │             │
│   │ ████████ │        │  │╲│╱│   │         │ ▓▓▓▓▓▓▓▓ │             │
│   │ GPUs     │        │  ●─●─●   │         │ ▓▓▓▓▓▓▓▓ │             │
│   │ TPUs     │        │  │╲│╱│   │         │ ▓▓▓▓▓▓▓▓ │             │
│   │ Clusters │        │  ● ● ●   │         │ ▓▓▓▓▓▓▓▓ │             │
│   └──────────┘        └──────────┘         └──────────┘             │
│                                                                      │
│   Hardware advances   Neural network        Large labeled            │
│   enabling massive    architectures         datasets                 │
│   parallel computing  and training          (ImageNet, etc.)         │
│                       algorithms                                     │
└──────────────────────────────────────────────────────────────────────┘
```

---

## Slides 62-63: GPU Performance Growth

```
GFLOP per Dollar Over Time
━━━━━━━━━━━━━━━━━━━━━━━━━━

200 │                                          ○ Tensor Core GPUs
    │                                        ○
    │                                      ○
150 │                                    ○
    │                                  ○
    │                                ○
100 │                              ○
    │
    │                          ●   ← RTX 2080 Ti (FP32)
 50 │                        ●
    │         Deep Learning  ●
    │         Explosion ──►●●
  0 │___●●●●●●●●●●●●●●●●●●●●●●●●_____________________________
    2004    2008    2012    2016    2020

    ● = CPU (flat)
    ● = GPU FP32 (exponential growth)
    ○ = GPU Tensor Core (even faster!)

Recent GPUs have "Tensor Cores": Special hardware for deep learning!
```

---

## Slide 64: AI's Explosive Growth & Impact

- Conference attendance: Exponential growth (CVPR, NeurIPS, ICML, etc.)
- AI Startups: Rapid increase since 2012
- Enterprise AI Revenue: From ~$1B (2016) to ~$30B+ (2020s)

---

## Slides 65-68: Computer Vision's Future

### Despite successes, computer vision still has a long way to go

**Computer Vision Can Cause Harm:**
- Harmful stereotypes (bias in facial recognition)
- Affecting people's lives (AI hiring algorithms)
- Performance disparities across demographic groups

**Computer Vision Can Save Lives:**
- Healthcare monitoring for seniors
- Early symptom detection
- Managing chronic conditions
- Privacy-preserving approaches

**Much We Don't Know How To Do:**
- Deep scene understanding
- Common sense reasoning
- Contextual understanding of complex social situations

---

## Slide 69: Today's Agenda (Recap)

- ✓ A brief history of computer vision & deep learning
- CS231n overview (continued in Part 2)

---

## Historical Timeline

```
COMPUTER VISION & DEEP LEARNING TIMELINE
════════════════════════════════════════════════════════════════════════════

1958    1959    1963    1969    1970s   1979    1980    1985    1986
  │       │       │       │       │       │       │       │       │
  ▼       ▼       ▼       ▼       ▼       ▼       ▼       ▼       ▼
Percep- Hubel   Larry  Minsky  David   Gen.   Neoco- Back-  Canny
tron    &       Roberts &       Marr   Cylin- gnitron prop   Edge
        Wiesel          Papert         ders                  Detect

════════════════════════════════════════════════════════════════════════════

                        AI WINTER (late 1980s - 1990s)

════════════════════════════════════════════════════════════════════════════

1997    1998    1999    2001    2004-07  2006    2009    2012    Present
  │       │       │       │       │        │       │       │       │
  ▼       ▼       ▼       ▼       ▼        ▼       ▼       ▼       ▼
Norm.   LeNet   SIFT   Viola   Caltech  Deep   ImageNet AlexNet Deep
Cuts                   &       101,    Learn-                    Learning
                       Jones   PASCAL  ing                       Explosion

════════════════════════════════════════════════════════════════════════════
```

---

*Slide inspiration credits: Justin Johnson, Andrej Karpathy*

*Document extracted from CS231n Lecture 1 Part 1 PDF (69 slides)*
*Stanford University, April 2025*
