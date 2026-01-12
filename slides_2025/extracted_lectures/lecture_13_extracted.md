# lecture_13

Extracted using pdfplumber



---
## Page 1
---


Lecture 13:
Generative Models (part 1)
Stanford CS231n 10th Anniversary Lecture 13 - 1 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture 13:
Generative Models (part 1) |
| Stanford CS231n 10th Anniversary Lecture 13 - 1 May 15, 2025 |


---
## Page 2
---


Administrative
Tomorrow 5/16:
Assignment 3 out
●
Project milestone due
●
Stanford CS231n 10th Anniversary Lecture 13 - 2 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Administrative
Tomorrow 5/16:
Assignment 3 out
●
Project milestone due
● |
| Stanford CS231n 10th Anniversary Lecture 13 - 2 May 15, 2025 |


---
## Page 3
---


Last Time: Self-Supervised Learning
Dataset
(no labels)
n
o
it
a t Decoder, Labels/outputs
n
e
s
e automatically
Encoder r Classifier,
p
e generated
R
d
e Regressor from data
n
r
a
e
L
Stanford CS231n 10th Anniversary Lecture 13 - 3 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Last Time: Self-Supervised Learning
Dataset
(no labels)
n
o
it
a t Decoder, Labels/outputs
n
e
s
e automatically
Encoder r Classifier,
p
e generated
R
d
e Regressor from data
n
r
a
e
L |
| Stanford CS231n 10th Anniversary Lecture 13 - 3 May 15, 2025 |


[Page contains 1 image(s)]


---
## Page 4
---


Last Time: Self-Supervised Learning
Dataset
(no labels)
n
o
it
a t Decoder, Labels/outputs
n
e
s e automatically
Encoder r ClaFsCsifier,
p Labels
e generated
R
d
e Regressor from data
n
r
a
e
L
Stanford CS231n 10th Anniversary Lecture 13 - 4 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Last Time: Self-Supervised Learning
Dataset
(no labels)
n
o
it
a t Decoder, Labels/outputs
n
e
s e automatically
Encoder r ClaFsCsifier,
p Labels
e generated
R
d
e Regressor from data
n
r
a
e
L |
| Stanford CS231n 10th Anniversary Lecture 13 - 4 May 15, 2025 |


[Page contains 1 image(s)]


---
## Page 5
---


Last Time: Self-Supervised Learning
Pretext tasks from image transformations
• Rotation, inpainting, rearrangement, coloring
• Reconstruction-based learning (MAE)
Rotation Rearrangement Reconstruction
Stanford CS231n 10th Anniversary Lecture 13 - 5 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Last Time: Self-Supervised Learning
Pretext tasks from image transformations
• Rotation, inpainting, rearrangement, coloring
• Reconstruction-based learning (MAE)
Rotation Rearrangement Reconstruction |
| Stanford CS231n 10th Anniversary Lecture 13 - 5 May 15, 2025 |


[Page contains 3 image(s)]


---
## Page 6
---


Last Time: Self-Supervised Learning
Contrastive representation learning
• Intuition and formulation
• Instance contrastive learning: SimCLR and MOCO
• Sequence contrastive learning: CPC
• Self-Distillation Without Labels, DINO
Stanford CS231n 10th Anniversary Lecture 13 - 6 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Last Time: Self-Supervised Learning
Contrastive representation learning
• Intuition and formulation
• Instance contrastive learning: SimCLR and MOCO
• Sequence contrastive learning: CPC
• Self-Distillation Without Labels, DINO |
| Stanford CS231n 10th Anniversary Lecture 13 - 6 May 15, 2025 |


---
## Page 7
---


Last Time: Contrastive Learning (SimCLR)
Random Extract
Input Corresponding pairs
transforms features
batch should have similar
features
Other pairs should have
dissimilar features
Chen et al, “A simple framework for contrastive learning of visual representations”, ICML 2020
Stanford CS231n 10th Anniversary Lecture 13 - 7 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Last Time: Contrastive Learning (SimCLR)
Random Extract
Input Corresponding pairs
transforms features
batch should have similar
features
Other pairs should have
dissimilar features
Chen et al, “A simple framework for contrastive learning of visual representations”, ICML 2020 |
| Stanford CS231n 10th Anniversary Lecture 13 - 7 May 15, 2025 |


[Page contains 1 image(s)]


---
## Page 8
---


Last Time: Contrastive Learning (SimCLR)
Random Extract
Input Corresponding pairs
transforms features
batch should have similar
features
Other pairs should have
dissimilar features
Problem: Need large
batch size with lots of
negatives
Chen et al, “A simple framework for contrastive learning of visual representations”, ICML 2020
Stanford CS231n 10th Anniversary Lecture 13 - 8 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Last Time: Contrastive Learning (SimCLR)
Random Extract
Input Corresponding pairs
transforms features
batch should have similar
features
Other pairs should have
dissimilar features
Problem: Need large
batch size with lots of
negatives
Chen et al, “A simple framework for contrastive learning of visual representations”, ICML 2020 |
| Stanford CS231n 10th Anniversary Lecture 13 - 8 May 15, 2025 |


[Page contains 1 image(s)]


---
## Page 9
---


Contrastive Learning: MoCo
Key differences to SimCLR:
no_grad
● Keep a running queue of keys (negative
samples).
● Compute gradients and update the
encoder only through the queries.
● Decouple min-batch size with the
number of keys: can support a large
number of negative samples.
● The key encoder is slowly progressing
through the momentum update rules:
He et al, “Momentum Contrast for Unsupervised Visual Representation Learning”, CVPR 2020
Stanford CS231n 10th Anniversary Lecture 13 - 9 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Contrastive Learning: MoCo
Key differences to SimCLR:
no_grad
● Keep a running queue of keys (negative
samples).
● Compute gradients and update the
encoder only through the queries.
● Decouple min-batch size with the
number of keys: can support a large
number of negative samples.
● The key encoder is slowly progressing
through the momentum update rules:
He et al, “Momentum Contrast for Unsupervised Visual Representation Learning”, CVPR 2020 |
| Stanford CS231n 10th Anniversary Lecture 13 - 9 May 15, 2025 |


[Page contains 2 image(s)]


---
## Page 10
---


Self-Supervised Learning: DINO
Similar in spirit to MoCo, but matches features using KL divergence
instead of dot product, and uses Vision Transformers instead of ResNets
Caron et al. 2021 Emerging Properties in Self-Supervised Vision Transformers
Stanford CS231n 10th Anniversary Lecture 13 - 10 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Self-Supervised Learning: DINO
Similar in spirit to MoCo, but matches features using KL divergence
instead of dot product, and uses Vision Transformers instead of ResNets
Caron et al. 2021 Emerging Properties in Self-Supervised Vision Transformers |
| Stanford CS231n 10th Anniversary Lecture 13 - 10 May 15, 2025 |


[Page contains 3 image(s)]


---
## Page 11
---


Self-Supervised Learning: DINOv2
Scales up training data from 1M ImageNet images to 142M images
Very strong image features, commonly used in practice
PCA feature
visualization
Oquabet al, “DINOv2: Learning Robust Visual Features without Supervision”, arXiv2023; Darcetet al, “Vision Transformers Need Registers”, arXiv2023
Stanford CS231n 10th Anniversary Lecture 13 - 11 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Self-Supervised Learning: DINOv2
Scales up training data from 1M ImageNet images to 142M images
Very strong image features, commonly used in practice
PCA feature
visualization
Oquabet al, “DINOv2: Learning Robust Visual Features without Supervision”, arXiv2023; Darcetet al, “Vision Transformers Need Registers”, arXiv2023 |
| Stanford CS231n 10th Anniversary Lecture 13 - 11 May 15, 2025 |


[Page contains 1 image(s)]


---
## Page 12
---


Today:
Generative Models (part 1)
Stanford CS231n 10th Anniversary Lecture 13 - 12 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Today:
Generative Models (part 1) |
| Stanford CS231n 10th Anniversary Lecture 13 - 12 May 15, 2025 |


---
## Page 13
---


Supervised vs Unsupervised Learning
Supervised Learning
Data: (x, y)
x is data, y is label
Goal: Learn a function to map x -> y
Examples: Classification, regression,
object detection, semantic
segmentation, image captioning, etc.
Stanford CS231n 10th Anniversary Lecture 13 - 13 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Supervised vs Unsupervised Learning
Supervised Learning
Data: (x, y)
x is data, y is label
Goal: Learn a function to map x -> y
Examples: Classification, regression,
object detection, semantic
segmentation, image captioning, etc. |
| Stanford CS231n 10th Anniversary Lecture 13 - 13 May 15, 2025 |


---
## Page 14
---


Supervised vs Unsupervised Learning
Supervised Learning
Data: (x, y)
x is data, y is label
Cat
Goal: Learn a function to map x -> y
Examples: Classification, regression,
object detection, semantic
Classification
segmentation, image captioning, etc.
This imageis CC0 public domain
Stanford CS231n 10th Anniversary Lecture 13 - 14 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Supervised vs Unsupervised Learning
Supervised Learning
Data: (x, y)
x is data, y is label
Cat
Goal: Learn a function to map x -> y
Examples: Classification, regression,
object detection, semantic
Classification
segmentation, image captioning, etc.
This imageis CC0 public domain |
| Stanford CS231n 10th Anniversary Lecture 13 - 14 May 15, 2025 |


[Page contains 1 image(s)]


---
## Page 15
---


Supervised vs Unsupervised Learning
Supervised Learning
Data: (x, y)
x is data, y is label
Goal: Learn a function to map x -> y
Examples: Classification, regression, A cat sitting on a suitcase on the floor
object detection, semantic
Image captioning
segmentation, image captioning, etc.
Caption generated using neuraltalk2
ImageisCC0 Public domain.
Stanford CS231n 10th Anniversary Lecture 13 - 15 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Supervised vs Unsupervised Learning
Supervised Learning
Data: (x, y)
x is data, y is label
Goal: Learn a function to map x -> y
Examples: Classification, regression, A cat sitting on a suitcase on the floor
object detection, semantic
Image captioning
segmentation, image captioning, etc.
Caption generated using neuraltalk2
ImageisCC0 Public domain. |
| Stanford CS231n 10th Anniversary Lecture 13 - 15 May 15, 2025 |


[Page contains 1 image(s)]


---
## Page 16
---


Supervised vs Unsupervised Learning
Supervised Learning
Data: (x, y)
x is data, y is label
Goal: Learn a function to map x -> y
Examples: Classification, regression,
DOG, DOG, CAT
object detection, semantic
segmentation, image captioning, etc.
Object Detection
This imageis CC0 public domain
Stanford CS231n 10th Anniversary Lecture 13 - 16 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Supervised vs Unsupervised Learning
Supervised Learning
Data: (x, y)
x is data, y is label
Goal: Learn a function to map x -> y
Examples: Classification, regression,
DOG, DOG, CAT
object detection, semantic
segmentation, image captioning, etc.
Object Detection
This imageis CC0 public domain |
| Stanford CS231n 10th Anniversary Lecture 13 - 16 May 15, 2025 |


[Page contains 1 image(s)]


---
## Page 17
---


Supervised vs Unsupervised Learning
Supervised Learning
Data: (x, y)
x is data, y is label
Goal: Learn a function to map x -> y
GRASS, CAT,
Examples: Classification, regression,
TREE, SKY
object detection, semantic
segmentation, image captioning, etc.
Semantic Segmentation
Stanford CS231n 10th Anniversary Lecture 13 - 17 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Supervised vs Unsupervised Learning
Supervised Learning
Data: (x, y)
x is data, y is label
Goal: Learn a function to map x -> y
GRASS, CAT,
Examples: Classification, regression,
TREE, SKY
object detection, semantic
segmentation, image captioning, etc.
Semantic Segmentation |
| Stanford CS231n 10th Anniversary Lecture 13 - 17 May 15, 2025 |


[Page contains 1 image(s)]


---
## Page 18
---


Supervised vs Unsupervised Learning
Supervised Learning Unsupervised Learning
Data: (x, y) Data: x
x is data, y is label Just data, no labels!
Goal: Learn a function to map x -> y Goal: Learn hidden structure in data
Examples: Classification, regression, Examples: Clustering, dimensionality
object detection, semantic reduction, density estimation, etc.
segmentation, image captioning, etc.
Stanford CS231n 10th Anniversary Lecture 13 - 18 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Supervised vs Unsupervised Learning
Supervised Learning Unsupervised Learning
Data: (x, y) Data: x
x is data, y is label Just data, no labels!
Goal: Learn a function to map x -> y Goal: Learn hidden structure in data
Examples: Classification, regression, Examples: Clustering, dimensionality
object detection, semantic reduction, density estimation, etc.
segmentation, image captioning, etc. |
| Stanford CS231n 10th Anniversary Lecture 13 - 18 May 15, 2025 |


---
## Page 19
---


Supervised vs Unsupervised Learning
Unsupervised Learning
Data: x
Just data, no labels!
Goal: Learn hidden structure in data
Examples: Clustering, dimensionality
reduction, density estimation, etc.
K-means clustering
This imageis CC0 public domain
Stanford CS231n 10th Anniversary Lecture 13 - 19 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Supervised vs Unsupervised Learning
Unsupervised Learning
Data: x
Just data, no labels!
Goal: Learn hidden structure in data
Examples: Clustering, dimensionality
reduction, density estimation, etc.
K-means clustering
This imageis CC0 public domain |
| Stanford CS231n 10th Anniversary Lecture 13 - 19 May 15, 2025 |


[Page contains 1 image(s)]


---
## Page 20
---


Supervised vs Unsupervised Learning
Unsupervised Learning
Data: x
Just data, no labels!
Goal: Learn hidden structure in data
3-d 2-d
Examples: Clustering, dimensionality
reduction, density estimation, etc.
Principal Component Analysis
(Dimensionality reduction)
This imagefrom Matthias Scholz
is CC0 public domain
Stanford CS231n 10th Anniversary Lecture 13 - 20 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Supervised vs Unsupervised Learning
Unsupervised Learning
Data: x
Just data, no labels!
Goal: Learn hidden structure in data
3-d 2-d
Examples: Clustering, dimensionality
reduction, density estimation, etc.
Principal Component Analysis
(Dimensionality reduction)
This imagefrom Matthias Scholz
is CC0 public domain |
| Stanford CS231n 10th Anniversary Lecture 13 - 20 May 15, 2025 |


[Page contains 1 image(s)]


---
## Page 21
---


Supervised vs Unsupervised Learning
Unsupervised Learning
Data: x
Figure copyright Ian Goodfellow, 2016. Reproduced with permission.
1-d density estimation
Just data, no labels!
Goal: Learn hidden structure in data
Examples: Clustering, dimensionality
reduction, density estimation, etc.
2-d density estimation
Modeling p(x)
2-d density images leftand right
are CC0 public domain
Stanford CS231n 10th Anniversary Lecture 13 - 21 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Supervised vs Unsupervised Learning
Unsupervised Learning
Data: x
Figure copyright Ian Goodfellow, 2016. Reproduced with permission.
1-d density estimation
Just data, no labels!
Goal: Learn hidden structure in data
Examples: Clustering, dimensionality
reduction, density estimation, etc.
2-d density estimation
Modeling p(x)
2-d density images leftand right
are CC0 public domain |
| Stanford CS231n 10th Anniversary Lecture 13 - 21 May 15, 2025 |


[Page contains 3 image(s)]


---
## Page 22
---


Generative vs Discriminative Models
Discriminative Model:
Data: x
Learn a probability
distribution p(y|x)
Generative Model:
Learn a probability
distribution p(x)
Label: y
Conditional Generative
Cat
Model: Learn p(x|y)
Stanford CS231n 10th Anniversary Lecture 13 - 22 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Generative vs Discriminative Models
Discriminative Model:
Data: x
Learn a probability
distribution p(y|x)
Generative Model:
Learn a probability
distribution p(x)
Label: y
Conditional Generative
Cat
Model: Learn p(x|y) |
| Stanford CS231n 10th Anniversary Lecture 13 - 22 May 15, 2025 |


[Page contains 1 image(s)]


---
## Page 23
---


Generative vs Discriminative Models
Probability Recap:
Density Function
Discriminative Model:
Data: x
p(x) assigns a positive
Learn a probability
number to each possible
distribution p(y|x)
x; higher numbers mean
x is more likely.
Generative Model:
Density functions are
Learn a probability normalized:
distribution p(x)
න 𝑝 𝑥 𝑑𝑥 = 1
𝑋
Label: y
Conditional Generative
Cat Different values of x
Model: Learn p(x|y)
compete for density
Stanford CS231n 10th Anniversary Lecture 13 - 23 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Generative vs Discriminative Models
Probability Recap:
Density Function
Discriminative Model:
Data: x
p(x) assigns a positive
Learn a probability
number to each possible
distribution p(y|x)
x; higher numbers mean
x is more likely.
Generative Model:
Density functions are
Learn a probability normalized:
distribution p(x)
න 𝑝 𝑥 𝑑𝑥 = 1
𝑋
Label: y
Conditional Generative
Cat Different values of x
Model: Learn p(x|y)
compete for density |  |  |
|  | x; higher numbers me
x is more likely.
Density functions are
normalized:
න 𝑝 𝑥 𝑑𝑥 = 1
𝑋
Different values of x
compete for density |  |
| Stanford CS231n 10th Anniversary Lect | ure 13 - 23 May 15, 20 | 25 |
|  |  |  |


[Page contains 1 image(s)]


---
## Page 24
---


Generative vs Discriminative Models
P(cat| )
Discriminative Model:
Data: x
Learn a probability
distribution p(y|x)
P(dog| )
Generative Model:
Learn a probability
distribution p(x)
න 𝑝 𝑥 𝑑𝑥 = 1
𝑋
Label: y
Conditional Generative
Cat Different values of x
Model: Learn p(x|y)
compete for density
Stanford CS231n 10th Anniversary Lecture 13 - 24 May 15, 2025

[Page contains 2 table(s)]


### Table 1

| Generative vs Discriminative Models
P(cat| )
Discriminative Model:
Data: x
Learn a probability
distribution p(y|x)
P(dog| )
Generative Model:
Learn a probability
distribution p(x)
න 𝑝 𝑥 𝑑𝑥 = 1
𝑋
Label: y
Conditional Generative
Cat Different values of x
Model: Learn p(x|y)
compete for density |  |  |
|  | P(dog|
න 𝑝 𝑥 𝑑𝑥 = 1
𝑋
Different values of x
compete for density |  |
| Stanford CS231n 10th Anniversary Lect | ure 13 - 24 May 15, 20 | 25 |
|  |  |  |


### Table 2

|  |
|  |


[Page contains 3 image(s)]


---
## Page 25
---


Generative vs Discriminative Models
P(cat| )
Discriminative Model:
Learn a probability
distribution p(y|x)
P(dog| )
Generative Model:
P(dog| )
Learn a probability
distribution p(x)
P(cat| )
Conditional Generative
Model: Learn p(x|y)
Possible labels for each image compete for probability.
No competition between images
Stanford CS231n 10th Anniversary Lecture 13 - 25 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Generative vs Discriminative Models
P(cat| )
Discriminative Model:
Learn a probability
distribution p(y|x)
P(dog| )
Generative Model:
P(dog| )
Learn a probability
distribution p(x)
P(cat| )
Conditional Generative
Model: Learn p(x|y)
Possible labels for each image compete for probability.
No competition between images |
| Stanford CS231n 10th Anniversary Lecture 13 - 25 May 15, 2025 |


[Page contains 6 image(s)]


---
## Page 26
---


Monkey imageis CC0 Public Domain
Abstract image is free to use under the Pixabaylicense
Generative vs Discriminative Models
P(cat| )
Discriminative Model:
Learn a probability
distribution p(y|x)
P(dog| )
Generative Model:
P(dog| )
Learn a probability
distribution p(x)
P(cat| )
Conditional Generative
Model: Learn p(x|y)
No way to handle unreasonable inputs; must
give a label distribution for all possible inputs
Stanford CS231n 10th Anniversary Lecture 13 - 26 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Monkey imageis CC0 Public Domain
Abstract image is free to use under the Pixabaylicense
Generative vs Discriminative Models
P(cat| )
Discriminative Model:
Learn a probability
distribution p(y|x)
P(dog| )
Generative Model:
P(dog| )
Learn a probability
distribution p(x)
P(cat| )
Conditional Generative
Model: Learn p(x|y)
No way to handle unreasonable inputs; must
give a label distribution for all possible inputs |
| Stanford CS231n 10th Anniversary Lecture 13 - 26 May 15, 2025 |


[Page contains 6 image(s)]


---
## Page 27
---


Cat imageis CC0 public domain
Dog imageis CC0 Public Domain
Monkey imageis CC0 Public Domain
Generative vs Discriminative Models Abstract image is free to use under the Pixabaylicense
P( )
Discriminative Model:
P( )
Learn a probability P( )
distribution p(y|x)
P( )
Generative Model:
…
Learn a probability
distribution p(x)
All possible images compete for probability mass
Conditional Generative
Model: Learn p(x|y)
Stanford CS231n 10th Anniversary Lecture 13 - 27 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Cat imageis CC0 public domain
Dog imageis CC0 Public Domain
Monkey imageis CC0 Public Domain
Generative vs Discriminative Models Abstract image is free to use under the Pixabaylicense
P( )
Discriminative Model:
P( )
Learn a probability P( )
distribution p(y|x)
P( )
Generative Model:
…
Learn a probability
distribution p(x)
All possible images compete for probability mass
Conditional Generative
Model: Learn p(x|y) |
| Stanford CS231n 10th Anniversary Lecture 13 - 27 May 15, 2025 |


[Page contains 8 image(s)]


---
## Page 28
---


Cat imageis CC0 public domain
Dog imageis CC0 Public Domain
Monkey imageis CC0 Public Domain
Generative vs Discriminative Models Abstract image is free to use under the Pixabaylicense
P( )
Discriminative Model:
P( )
Learn a probability P( )
distribution p(y|x)
P( )
Generative Model:
…
Learn a probability
distribution p(x)
All possible images compete for probability mass
Conditional Generative
Requires deep understanding: Is a dog more
Model: Learn p(x|y)
likely to sit or stand? Is a 3-legged dog more likely
than a 3-armed monkey?
Stanford CS231n 10th Anniversary Lecture 13 - 28 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Cat imageis CC0 public domain
Dog imageis CC0 Public Domain
Monkey imageis CC0 Public Domain
Generative vs Discriminative Models Abstract image is free to use under the Pixabaylicense
P( )
Discriminative Model:
P( )
Learn a probability P( )
distribution p(y|x)
P( )
Generative Model:
…
Learn a probability
distribution p(x)
All possible images compete for probability mass
Conditional Generative
Requires deep understanding: Is a dog more
Model: Learn p(x|y)
likely to sit or stand? Is a 3-legged dog more likely
than a 3-armed monkey? |
| Stanford CS231n 10th Anniversary Lecture 13 - 28 May 15, 2025 |


[Page contains 8 image(s)]


---
## Page 29
---


Cat imageis CC0 public domain
Dog imageis CC0 Public Domain
Monkey imageis CC0 Public Domain
Generative vs Discriminative Models Abstract image is free to use under the Pixabaylicense
P( )
Discriminative Model:
P( )
Learn a probability P( )
distribution p(y|x)
P( )
Generative Model:
…
Learn a probability
distribution p(x)
All possible images compete for probability mass
Conditional Generative
Model can “reject” unreasonable inputs by giving
Model: Learn p(x|y)
them small probability mass
Stanford CS231n 10th Anniversary Lecture 13 - 29 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Cat imageis CC0 public domain
Dog imageis CC0 Public Domain
Monkey imageis CC0 Public Domain
Generative vs Discriminative Models Abstract image is free to use under the Pixabaylicense
P( )
Discriminative Model:
P( )
Learn a probability P( )
distribution p(y|x)
P( )
Generative Model:
…
Learn a probability
distribution p(x)
All possible images compete for probability mass
Conditional Generative
Model can “reject” unreasonable inputs by giving
Model: Learn p(x|y)
them small probability mass |
| Stanford CS231n 10th Anniversary Lecture 13 - 29 May 15, 2025 |


[Page contains 8 image(s)]


---
## Page 30
---


Cat imageis CC0 public domain
Dog imageis CC0 Public Domain
Monkey imageis CC0 Public Domain
Generative vs Discriminative Models Abstract image is free to use under the Pixabaylicense
P( |cat)
Discriminative Model:
P( |cat)
Learn a probability P( |cat) P( |cat)
distribution p(y|x)
P( |dog)
P( |dog)
P( |dog)
Generative Model: P( |dog)
Learn a probability
distribution p(x) …
Conditional Generative
Model: Learn p(x|y) Each possible label induces a
competition across all possible images
Stanford CS231n 10th Anniversary Lecture 13 - 30 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Cat imageis CC0 public domain
Dog imageis CC0 Public Domain
Monkey imageis CC0 Public Domain
Generative vs Discriminative Models Abstract image is free to use under the Pixabaylicense
P( |cat)
Discriminative Model:
P( |cat)
Learn a probability P( |cat) P( |cat)
distribution p(y|x)
P( |dog)
P( |dog)
P( |dog)
Generative Model: P( |dog)
Learn a probability
distribution p(x) …
Conditional Generative
Model: Learn p(x|y) Each possible label induces a
competition across all possible images |
| Stanford CS231n 10th Anniversary Lecture 13 - 30 May 15, 2025 |


[Page contains 12 image(s)]


---
## Page 31
---


Generative vs Discriminative Models
Discriminative Model:
Recall Bayes’ Rule:
Learn a probability
distribution p(y|x)
𝑃 𝑦 𝑥)
Generative Model:
𝑃 𝑥 𝑦) = 𝑃(𝑥)
Learn a probability
𝑃 𝑦
distribution p(x)
Conditional Generative
Model: Learn p(x|y)
Stanford CS231n 10th Anniversary Lecture 13 - 31 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Generative vs Discriminative Models
Discriminative Model:
Recall Bayes’ Rule:
Learn a probability
distribution p(y|x)
𝑃 𝑦 𝑥)
Generative Model:
𝑃 𝑥 𝑦) = 𝑃(𝑥)
Learn a probability
𝑃 𝑦
distribution p(x)
Conditional Generative
Model: Learn p(x|y) |
| Stanford CS231n 10th Anniversary Lecture 13 - 31 May 15, 2025 |


---
## Page 32
---


Generative vs Discriminative Models
Discriminative Model:
Recall Bayes’ Rule:
Learn a probability
distribution p(y|x)
Discriminative Model
𝑃 𝑦 𝑥)
Generative Model:
𝑃 𝑥 𝑦) = 𝑃(𝑥)
Learn a probability
𝑃 𝑦
distribution p(x)
Conditional (Unconditional)
Generative Model Prior over Generative Model
labels
Conditional Generative
We can build a conditional generative model from
Model: Learn p(x|y)
other components … but not common in practice
Stanford CS231n 10th Anniversary Lecture 13 - 32 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Generative vs Discriminative Models
Discriminative Model:
Recall Bayes’ Rule:
Learn a probability
distribution p(y|x)
Discriminative Model
𝑃 𝑦 𝑥)
Generative Model:
𝑃 𝑥 𝑦) = 𝑃(𝑥)
Learn a probability
𝑃 𝑦
distribution p(x)
Conditional (Unconditional)
Generative Model Prior over Generative Model
labels
Conditional Generative
We can build a conditional generative model from
Model: Learn p(x|y)
other components … but not common in practice |
| Stanford CS231n 10th Anniversary Lecture 13 - 32 May 15, 2025 |


---
## Page 33
---


Generative vs Discriminative Models
Discriminative Model:
Assign labels to data
Learn a probability
Feature learning (with labels)
distribution p(y|x)
Generative Model:
Learn a probability
distribution p(x)
Conditional Generative
Model: Learn p(x|y)
Stanford CS231n 10th Anniversary Lecture 13 - 33 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Generative vs Discriminative Models
Discriminative Model:
Assign labels to data
Learn a probability
Feature learning (with labels)
distribution p(y|x)
Generative Model:
Learn a probability
distribution p(x)
Conditional Generative
Model: Learn p(x|y) |
| Stanford CS231n 10th Anniversary Lecture 13 - 33 May 15, 2025 |


---
## Page 34
---


Generative vs Discriminative Models
Discriminative Model:
Assign labels to data
Learn a probability
Feature learning (with labels)
distribution p(y|x)
Generative Model: Detect outliers
Learn a probability Feature learning (without labels)
distribution p(x) Sample to generate new data
Conditional Generative
Model: Learn p(x|y)
Stanford CS231n 10th Anniversary Lecture 13 - 34 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Generative vs Discriminative Models
Discriminative Model:
Assign labels to data
Learn a probability
Feature learning (with labels)
distribution p(y|x)
Generative Model: Detect outliers
Learn a probability Feature learning (without labels)
distribution p(x) Sample to generate new data
Conditional Generative
Model: Learn p(x|y) |
| Stanford CS231n 10th Anniversary Lecture 13 - 34 May 15, 2025 |


---
## Page 35
---


Generative vs Discriminative Models
Discriminative Model:
Assign labels to data
Learn a probability
Feature learning (with labels)
distribution p(y|x)
Generative Model: Detect outliers
Learn a probability Feature learning (without labels)
distribution p(x) Sample to generate new data
Conditional Generative Assign labels while rejecting outliers
Model: Learn p(x|y) Sample to generate data from labels
Stanford CS231n 10th Anniversary Lecture 13 - 35 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Generative vs Discriminative Models
Discriminative Model:
Assign labels to data
Learn a probability
Feature learning (with labels)
distribution p(y|x)
Generative Model: Detect outliers
Learn a probability Feature learning (without labels)
distribution p(x) Sample to generate new data
Conditional Generative Assign labels while rejecting outliers
Model: Learn p(x|y) Sample to generate data from labels |
| Stanford CS231n 10th Anniversary Lecture 13 - 35 May 15, 2025 |


---
## Page 36
---


Generative vs Discriminative Models
Discriminative Model:
Learn a probability
distribution p(y|x)
Generative Model:
Learn a probability
”Generative models” means
distribution p(x)
either of these; conditional
generative models are most
common in practice
Conditional Generative
Model: Learn p(x|y)
Stanford CS231n 10th Anniversary Lecture 13 - 36 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Generative vs Discriminative Models
Discriminative Model:
Learn a probability
distribution p(y|x)
Generative Model:
Learn a probability
”Generative models” means
distribution p(x)
either of these; conditional
generative models are most
common in practice
Conditional Generative
Model: Learn p(x|y) |
| Stanford CS231n 10th Anniversary Lecture 13 - 36 May 15, 2025 |


---
## Page 37
---


Why Generative Models?
Modeling ambiguity: If there are many possible
outputs x for an input y, we want to model P(x | y)
Language Modeling: Produce output text x from input text y
They sample from a learned P,
Write me a short
A distribution—structured, free.
rhyming poem about
Each token comes conditionally,
generative models
On all the ones that used to be.
Stanford CS231n 10th Anniversary Lecture 13 - 37 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Why Generative Models?
Modeling ambiguity: If there are many possible
outputs x for an input y, we want to model P(x | y)
Language Modeling: Produce output text x from input text y
They sample from a learned P,
Write me a short
A distribution—structured, free.
rhyming poem about
Each token comes conditionally,
generative models
On all the ones that used to be. |
| Stanford CS231n 10th Anniversary Lecture 13 - 37 May 15, 2025 |


---
## Page 38
---


Why Generative Models?
Modeling ambiguity: If there are many possible
outputs x for an input y, we want to model P(x | y)
Text to Image: Produce output image x from input text y
Make me an image showing
a person teaching a class on
generative models in front of
a whiteboard
Stanford CS231n 10th Anniversary Lecture 13 - 38 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Why Generative Models?
Modeling ambiguity: If there are many possible
outputs x for an input y, we want to model P(x | y)
Text to Image: Produce output image x from input text y
Make me an image showing
a person teaching a class on
generative models in front of
a whiteboard |
| Stanford CS231n 10th Anniversary Lecture 13 - 38 May 15, 2025 |


[Page contains 1 image(s)]


---
## Page 39
---


Why Generative Models?
Modeling ambiguity: If there are many possible
outputs x for an input y, we want to model P(x | y)
Image to Video: What happens next?
Stanford CS231n 10th Anniversary Lecture 13 - 39 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Why Generative Models?
Modeling ambiguity: If there are many possible
outputs x for an input y, we want to model P(x | y)
Image to Video: What happens next? |
| Stanford CS231n 10th Anniversary Lecture 13 - 39 May 15, 2025 |


[Page contains 2 image(s)]


---
## Page 40
---


Figure adapted from Ian
Goodfellow, Tutorial on
Taxonomy of Generative Models Generative Adversarial
Networks, 2017
Generative models
Stanford CS231n 10th Anniversary Lecture 13 - 40 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Figure adapted from Ian
Goodfellow, Tutorial on
Taxonomy of Generative Models Generative Adversarial
Networks, 2017
Generative models |
| Stanford CS231n 10th Anniversary Lecture 13 - 40 May 15, 2025 |


---
## Page 41
---


Figure adapted from Ian
Goodfellow, Tutorial on
Taxonomy of Generative Models Generative Adversarial
Networks, 2017
Model can Generative models
compute P(x)
Explicit density
Stanford CS231n 10th Anniversary Lecture 13 - 41 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Figure adapted from Ian
Goodfellow, Tutorial on
Taxonomy of Generative Models Generative Adversarial
Networks, 2017
Model can Generative models
compute P(x)
Explicit density |
| Stanford CS231n 10th Anniversary Lecture 13 - 41 May 15, 2025 |


---
## Page 42
---


Figure adapted from Ian
Goodfellow, Tutorial on
Taxonomy of Generative Models Generative Adversarial
Networks, 2017
Model can Generative models Cannot compute p(x) but
compute P(x) can sample from P(x)
Explicit density Implicit density
Stanford CS231n 10th Anniversary Lecture 13 - 42 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Figure adapted from Ian
Goodfellow, Tutorial on
Taxonomy of Generative Models Generative Adversarial
Networks, 2017
Model can Generative models Cannot compute p(x) but
compute P(x) can sample from P(x)
Explicit density Implicit density |
| Stanford CS231n 10th Anniversary Lecture 13 - 42 May 15, 2025 |


---
## Page 43
---


Figure adapted from Ian
Goodfellow, Tutorial on
Taxonomy of Generative Models Generative Adversarial
Networks, 2017
Model can Generative models Cannot compute p(x) but
compute P(x) can sample from P(x)
Explicit density Implicit density
Really
compute
P(x)
Tractable density
Autoregressive
Stanford CS231n 10th Anniversary Lecture 13 - 43 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Figure adapted from Ian
Goodfellow, Tutorial on
Taxonomy of Generative Models Generative Adversarial
Networks, 2017
Model can Generative models Cannot compute p(x) but
compute P(x) can sample from P(x)
Explicit density Implicit density
Really
compute
P(x)
Tractable density
Autoregressive |
| Stanford CS231n 10th Anniversary Lecture 13 - 43 May 15, 2025 |


---
## Page 44
---


Figure adapted from Ian
Goodfellow, Tutorial on
Taxonomy of Generative Models Generative Adversarial
Networks, 2017
Model can Generative models Cannot compute p(x) but
compute P(x) can sample from P(x)
Explicit density Implicit density
Really
Approximate
compute
P(x)
P(x)
Tractable density Approximate density
Variational Autoencoder
Autoregressive
(VAE)
Stanford CS231n 10th Anniversary Lecture 13 - 44 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Figure adapted from Ian
Goodfellow, Tutorial on
Taxonomy of Generative Models Generative Adversarial
Networks, 2017
Model can Generative models Cannot compute p(x) but
compute P(x) can sample from P(x)
Explicit density Implicit density
Really
Approximate
compute
P(x)
P(x)
Tractable density Approximate density
Variational Autoencoder
Autoregressive
(VAE) |
| Stanford CS231n 10th Anniversary Lecture 13 - 44 May 15, 2025 |


---
## Page 45
---


Figure adapted from Ian
Goodfellow, Tutorial on
Taxonomy of Generative Models Generative Adversarial
Networks, 2017
Model can Generative models Cannot compute p(x) but
compute P(x) can sample from P(x)
Explicit density Implicit density
Really Can directly
Approximate
compute sample
P(x)
P(x) from P(x)
Tractable density Approximate density Direct
Variational Autoencoder Generative Adversarial
Autoregressive
(VAE) Network (GAN)
Stanford CS231n 10th Anniversary Lecture 13 - 45 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Figure adapted from Ian
Goodfellow, Tutorial on
Taxonomy of Generative Models Generative Adversarial
Networks, 2017
Model can Generative models Cannot compute p(x) but
compute P(x) can sample from P(x)
Explicit density Implicit density
Really Can directly
Approximate
compute sample
P(x)
P(x) from P(x)
Tractable density Approximate density Direct
Variational Autoencoder Generative Adversarial
Autoregressive
(VAE) Network (GAN) |
| Stanford CS231n 10th Anniversary Lecture 13 - 45 May 15, 2025 |


---
## Page 46
---


Figure adapted from Ian
Goodfellow, Tutorial on
Taxonomy of Generative Models Generative Adversarial
Networks, 2017
Model can Generative models Cannot compute p(x) but
compute P(x) can sample from P(x)
Iterative
Explicit density Implicit density
procedure to
Really Can directly approximate
Approximate
compute sample samples
P(x)
P(x) from P(x) from P(x)
Tractable density Approximate density Direct Indirect
Variational Autoencoder Generative Adversarial
Autoregressive Diffusion Models
(VAE) Network (GAN)
Stanford CS231n 10th Anniversary Lecture 13 - 46 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Figure adapted from Ian
Goodfellow, Tutorial on
Taxonomy of Generative Models Generative Adversarial
Networks, 2017
Model can Generative models Cannot compute p(x) but
compute P(x) can sample from P(x)
Iterative
Explicit density Implicit density
procedure to
Really Can directly approximate
Approximate
compute sample samples
P(x)
P(x) from P(x) from P(x)
Tractable density Approximate density Direct Indirect
Variational Autoencoder Generative Adversarial
Autoregressive Diffusion Models
(VAE) Network (GAN) |
| Stanford CS231n 10th Anniversary Lecture 13 - 46 May 15, 2025 |


---
## Page 47
---


Figure adapted from Ian
Goodfellow, Tutorial on
Taxonomy of Generative Models Generative Adversarial
Networks, 2017
Model can Generative models Cannot compute p(x) but
compute P(x) can sample from P(x)
Iterative
Explicit density Implicit density
procedure to
Really Can directly approximate
Approximate
compute sample samples
P(x)
P(x) from P(x) from P(x)
Tractable density Approximate density Direct Indirect
Variational Autoencoder Generative Adversarial
Autoregressive Diffusion Models
(VAE) Network (GAN)
Today Next Time
Stanford CS231n 10th Anniversary Lecture 13 - 47 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Figure adapted from Ian
Goodfellow, Tutorial on
Taxonomy of Generative Models Generative Adversarial
Networks, 2017
Model can Generative models Cannot compute p(x) but
compute P(x) can sample from P(x)
Iterative
Explicit density Implicit density
procedure to
Really Can directly approximate
Approximate
compute sample samples
P(x)
P(x) from P(x) from P(x)
Tractable density Approximate density Direct Indirect
Variational Autoencoder Generative Adversarial
Autoregressive Diffusion Models
(VAE) Network (GAN)
Today Next Time |
| Stanford CS231n 10th Anniversary Lecture 13 - 47 May 15, 2025 |


---
## Page 48
---


Autoregressive Models
Stanford CS231n 10th Anniversary Lecture 13 - 48 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Autoregressive Models |
| Stanford CS231n 10th Anniversary Lecture 13 - 48 May 15, 2025 |


---
## Page 49
---


Maximum Likelihood Estimation
Goal: Write down an explicit function for 𝑝 𝑥 = 𝑓(𝑥, 𝑊)
Stanford CS231n 10th Anniversary Lecture 13 - 49 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Maximum Likelihood Estimation
Goal: Write down an explicit function for 𝑝 𝑥 = 𝑓(𝑥, 𝑊) |
| Stanford CS231n 10th Anniversary Lecture 13 - 49 May 15, 2025 |


---
## Page 50
---


Maximum Likelihood Estimation
Goal: Write down an explicit function for 𝑝 𝑥 = 𝑓(𝑥, 𝑊)
(1) (2) 𝑁
Given dataset 𝑥 , 𝑥 , … 𝑥 , train the model by solving:
∗ 𝑖 Maximize probability of training data
𝑊 = arg max ෑ 𝑝(𝑥 )
(Maximum likelihood estimation)
W
𝑖
Stanford CS231n 10th Anniversary Lecture 13 - 50 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Maximum Likelihood Estimation
Goal: Write down an explicit function for 𝑝 𝑥 = 𝑓(𝑥, 𝑊)
(1) (2) 𝑁
Given dataset 𝑥 , 𝑥 , … 𝑥 , train the model by solving:
∗ 𝑖 Maximize probability of training data
𝑊 = arg max ෑ 𝑝(𝑥 )
(Maximum likelihood estimation)
W
𝑖 |
| Stanford CS231n 10th Anniversary Lecture 13 - 50 May 15, 2025 |


---
## Page 51
---


Maximum Likelihood Estimation
Goal: Write down an explicit function for 𝑝 𝑥 = 𝑓(𝑥, 𝑊)
(1) (2) 𝑁
Given dataset 𝑥 , 𝑥 , … 𝑥 , train the model by solving:
∗ 𝑖 Maximize probability of training data
𝑊 = arg max ෑ 𝑝(𝑥 )
(Maximum likelihood estimation)
W
𝑖
= arg max σ log 𝑝(𝑥 𝑖 ) Log trick: Swap product and sum
𝑖
𝑊
Stanford CS231n 10th Anniversary Lecture 13 - 51 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Maximum Likelihood Estimation
Goal: Write down an explicit function for 𝑝 𝑥 = 𝑓(𝑥, 𝑊)
(1) (2) 𝑁
Given dataset 𝑥 , 𝑥 , … 𝑥 , train the model by solving:
∗ 𝑖 Maximize probability of training data
𝑊 = arg max ෑ 𝑝(𝑥 )
(Maximum likelihood estimation)
W
𝑖
= arg max σ log 𝑝(𝑥 𝑖 ) Log trick: Swap product and sum
𝑖
𝑊 |
| Stanford CS231n 10th Anniversary Lecture 13 - 51 May 15, 2025 |


---
## Page 52
---


Maximum Likelihood Estimation
Goal: Write down an explicit function for 𝑝 𝑥 = 𝑓(𝑥, 𝑊)
(1) (2) 𝑁
Given dataset 𝑥 , 𝑥 , … 𝑥 , train the model by solving:
∗ 𝑖 Maximize probability of training data
𝑊 = arg max ෑ 𝑝(𝑥 )
(Maximum likelihood estimation)
W
𝑖
= arg max σ log 𝑝(𝑥 𝑖 ) Log trick: Swap product and sum
𝑖
𝑊
= arg max σ log 𝑓(𝑥 𝑖 , 𝑊) This is our loss function.
𝑖 maximize it with gradient descent
𝑊
Stanford CS231n 10th Anniversary Lecture 13 - 52 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Maximum Likelihood Estimation
Goal: Write down an explicit function for 𝑝 𝑥 = 𝑓(𝑥, 𝑊)
(1) (2) 𝑁
Given dataset 𝑥 , 𝑥 , … 𝑥 , train the model by solving:
∗ 𝑖 Maximize probability of training data
𝑊 = arg max ෑ 𝑝(𝑥 )
(Maximum likelihood estimation)
W
𝑖
= arg max σ log 𝑝(𝑥 𝑖 ) Log trick: Swap product and sum
𝑖
𝑊
= arg max σ log 𝑓(𝑥 𝑖 , 𝑊) This is our loss function.
𝑖 maximize it with gradient descent
𝑊 |  |  |
|  | ∗ 𝑖
𝑊 = arg max ෑ 𝑝(𝑥 )
W
𝑖
= arg max σ log 𝑝(𝑥 𝑖 )
𝑖
𝑊
= arg max σ log 𝑓(𝑥 𝑖 , 𝑊)
𝑖
𝑊 |  |
| S | tanford CS231n 10th Anniversary | Lecture 13 - 52 May 15, 2025 |
|  |  |  |


---
## Page 53
---


Autoregressive Models
Goal: Write down an explicit function for 𝑝 𝑥 = 𝑓(𝑥, 𝑊)
Assume x is a sequence: 𝑥 = (𝑥 , 𝑥 , … , 𝑥 )
1 2 𝑇
Stanford CS231n 10th Anniversary Lecture 13 - 53 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Autoregressive Models
Goal: Write down an explicit function for 𝑝 𝑥 = 𝑓(𝑥, 𝑊)
Assume x is a sequence: 𝑥 = (𝑥 , 𝑥 , … , 𝑥 )
1 2 𝑇 |
| Stanford CS231n 10th Anniversary Lecture 13 - 53 May 15, 2025 |


---
## Page 54
---


Autoregressive Models
Goal: Write down an explicit function for 𝑝 𝑥 = 𝑓(𝑥, 𝑊)
Assume x is a sequence: 𝑥 = (𝑥 , 𝑥 , … , 𝑥 )
1 2 𝑇
Use the chain rule of probability:
𝑝 𝑥 = 𝑝 𝑥 , 𝑥 , 𝑥 , … , 𝑥
1 2 3 𝑇
= 𝑝 𝑥 𝑝 𝑥 𝑥 )𝑝 𝑥 𝑥 , 𝑥 ) …
1 2 1 3 1 2
𝑇
= ς 𝑝 𝑥 𝑥 , … , 𝑥 )
𝑡=1 𝑡 1 𝑡−1
Stanford CS231n 10th Anniversary Lecture 13 - 54 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Autoregressive Models
Goal: Write down an explicit function for 𝑝 𝑥 = 𝑓(𝑥, 𝑊)
Assume x is a sequence: 𝑥 = (𝑥 , 𝑥 , … , 𝑥 )
1 2 𝑇
Use the chain rule of probability:
𝑝 𝑥 = 𝑝 𝑥 , 𝑥 , 𝑥 , … , 𝑥
1 2 3 𝑇
= 𝑝 𝑥 𝑝 𝑥 𝑥 )𝑝 𝑥 𝑥 , 𝑥 ) …
1 2 1 3 1 2
𝑇
= ς 𝑝 𝑥 𝑥 , … , 𝑥 )
𝑡=1 𝑡 1 𝑡−1 |  |  |
|  | 𝑝 𝑥 = 𝑝 𝑥 , 𝑥 , 𝑥 , … , 𝑥
1 2 3 𝑇
= 𝑝 𝑥 𝑝 𝑥 𝑥 )𝑝 𝑥 𝑥 , 𝑥 ) …
1 2 1 3 1 2
𝑇
= ς 𝑝 𝑥 𝑥 , … , 𝑥 )
𝑡=1 𝑡 1 𝑡−1 |  |
| Stanford CS231n 10th Anniversary | Lecture 13 - 54 May 15, 2025 |  |
|  |  |  |


---
## Page 55
---


Autoregressive Models
Goal: Write down an explicit function for 𝑝 𝑥 = 𝑓(𝑥, 𝑊)
Assume x is a sequence: 𝑥 = (𝑥 , 𝑥 , … , 𝑥 )
1 2 𝑇
We have already seen this!
Use the chain rule of probability:
𝑝 𝑥 = 𝑝 𝑥 , 𝑥 , 𝑥 , … , 𝑥
1 2 3 𝑇
= 𝑝 𝑥 𝑝 𝑥 𝑥 )𝑝 𝑥 𝑥 , 𝑥 ) …
1 2 1 3 1 2
𝑇
= ς 𝑝 𝑥 𝑥 , … , 𝑥 )
𝑡=1 𝑡 1 𝑡−1
Language modeling with RNN
Stanford CS231n 10th Anniversary Lecture 13 - 55 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Autoregressive Models
Goal: Write down an explicit function for 𝑝 𝑥 = 𝑓(𝑥, 𝑊)
Assume x is a sequence: 𝑥 = (𝑥 , 𝑥 , … , 𝑥 )
1 2 𝑇
We have already seen this!
Use the chain rule of probability:
𝑝 𝑥 = 𝑝 𝑥 , 𝑥 , 𝑥 , … , 𝑥
1 2 3 𝑇
= 𝑝 𝑥 𝑝 𝑥 𝑥 )𝑝 𝑥 𝑥 , 𝑥 ) …
1 2 1 3 1 2
𝑇
= ς 𝑝 𝑥 𝑥 , … , 𝑥 )
𝑡=1 𝑡 1 𝑡−1
Language modeling with RNN |  |  |
|  | 𝑝 𝑥 = 𝑝 𝑥 , 𝑥 , 𝑥 , … , 𝑥
1 2 3 𝑇
= 𝑝 𝑥 𝑝 𝑥 𝑥 )𝑝 𝑥 𝑥 , 𝑥 ) …
1 2 1 3 1 2
𝑇
= ς 𝑝 𝑥 𝑥 , … , 𝑥 )
𝑡=1 𝑡 1 𝑡−1 |  |
| Stanford CS231n 10th Anniversary | Lecture 13 - 55 May 15, 2025 |  |
|  |  |  |


[Page contains 1 image(s)]


---
## Page 56
---


LLMs are Autoregressive Models
Goal: Write down an explicit function for 𝑝 𝑥 = 𝑓(𝑥, 𝑊)
Assume x is a sequence: 𝑥 = (𝑥 , 𝑥 , … , 𝑥 )
1 2 𝑇
Use the chain rule of probability:
Language
modeling
𝑝 𝑥 = 𝑝 𝑥 , 𝑥 , 𝑥 , … , 𝑥
with masked 1 2 3 𝑇
= 𝑝 𝑥 𝑝 𝑥 𝑥 )𝑝 𝑥 𝑥 , 𝑥 ) …
Transformer
1 2 1 3 1 2
𝑇
= ς 𝑝 𝑥 𝑥 , … , 𝑥 )
𝑡=1 𝑡 1 𝑡−1
Stanford CS231n 10th Anniversary Lecture 13 - 56 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| LLMs are Autoregressive Models
Goal: Write down an explicit function for 𝑝 𝑥 = 𝑓(𝑥, 𝑊)
Assume x is a sequence: 𝑥 = (𝑥 , 𝑥 , … , 𝑥 )
1 2 𝑇
Use the chain rule of probability:
Language
modeling
𝑝 𝑥 = 𝑝 𝑥 , 𝑥 , 𝑥 , … , 𝑥
with masked 1 2 3 𝑇
= 𝑝 𝑥 𝑝 𝑥 𝑥 )𝑝 𝑥 𝑥 , 𝑥 ) …
Transformer
1 2 1 3 1 2
𝑇
= ς 𝑝 𝑥 𝑥 , … , 𝑥 )
𝑡=1 𝑡 1 𝑡−1 |  |  |
|  | 𝑝 𝑥 = 𝑝 𝑥 , 𝑥 , 𝑥 , … , 𝑥
1 2 3 𝑇
= 𝑝 𝑥 𝑝 𝑥 𝑥 )𝑝 𝑥 𝑥 , 𝑥 ) …
1 2 1 3 1 2
𝑇
= ς 𝑝 𝑥 𝑥 , … , 𝑥 )
𝑡=1 𝑡 1 𝑡−1 |  |
| Stanford CS231n 10th Anniversary | Lecture 13 - 56 May 15, 2025 |  |
|  |  |  |


[Page contains 1 image(s)]


---
## Page 57
---


Autoregressive Models of Images
Treat an image as a sequence of 8-bit
subpixel values (scanline order)
Predict each subpixel as a classification
among 256 values [0…255]
…
Model with an RNN or Transformer
…
… … …
Van den Oord et al, “Pixel Recurrent Neural Networks”, ICML 2016
Van den Oord et al, “Conditional Image Generation with PixelCNNDecoders”, NeurIPS2016
Stanford CS231n 10th Anniversary Lecture 13 - 57 May 15, 2025

[Page contains 7 table(s)]


### Table 1

| Autoregressive Models of Images
Treat an image as a sequence of 8-bit
subpixel values (scanline order)
Predict each subpixel as a classification
among 256 values [0…255]
…
Model with an RNN or Transformer
…
… … …
Van den Oord et al, “Pixel Recurrent Neural Networks”, ICML 2016
Van den Oord et al, “Conditional Image Generation with PixelCNNDecoders”, NeurIPS2016 |
| Stanford CS231n 10th Anniversary Lecture 13 - 57 May 15, 2025 |


### Table 2

|  |  |
|  |  |
|  |  |


### Table 3

|  |  |
|  |  |
|  |  |


### Table 4

|  |  |
|  |  |
|  |  |


### Table 5

|  |  |
|  |  |
|  |  |


### Table 6

|  |  |
|  |  |
|  |  |


### Table 7

|  |  |
|  |  |
|  |  |


[Page contains 1 image(s)]


---
## Page 58
---


Autoregressive Models of Images
Treat an image as a sequence of 8-bit
subpixel values (scanline order)
Predict each subpixel as a classification
among 256 values [0…255]
…
Model with an RNN or Transformer
Problem: Too expensive. 1024x1024
image is a sequence of 3M subpixels …
… … …
Van den Oord et al, “Pixel Recurrent Neural Networks”, ICML 2016
Van den Oord et al, “Conditional Image Generation with PixelCNNDecoders”, NeurIPS2016
Stanford CS231n 10th Anniversary Lecture 13 - 58 May 15, 2025

[Page contains 7 table(s)]


### Table 1

| Autoregressive Models of Images
Treat an image as a sequence of 8-bit
subpixel values (scanline order)
Predict each subpixel as a classification
among 256 values [0…255]
…
Model with an RNN or Transformer
Problem: Too expensive. 1024x1024
image is a sequence of 3M subpixels …
… … …
Van den Oord et al, “Pixel Recurrent Neural Networks”, ICML 2016
Van den Oord et al, “Conditional Image Generation with PixelCNNDecoders”, NeurIPS2016 |
| Stanford CS231n 10th Anniversary Lecture 13 - 58 May 15, 2025 |


### Table 2

|  |  |
|  |  |
|  |  |


### Table 3

|  |  |
|  |  |
|  |  |


### Table 4

|  |  |
|  |  |
|  |  |


### Table 5

|  |  |
|  |  |
|  |  |


### Table 6

|  |  |
|  |  |
|  |  |


### Table 7

|  |  |
|  |  |
|  |  |


[Page contains 1 image(s)]


---
## Page 59
---


Autoregressive Models of Images
Treat an image as a sequence of 8-bit
subpixel values (scanline order)
Predict each subpixel as a classification
among 256 values [0…255]
…
Model with an RNN or Transformer
Problem: Too expensive. 1024x1024
image is a sequence of 3M subpixels …
Solution (jumping ahead): Model as
sequence of tiles, not sequence of subpixels … … …
Stanford CS231n 10th Anniversary Lecture 13 - 59 May 15, 2025

[Page contains 7 table(s)]


### Table 1

| Autoregressive Models of Images
Treat an image as a sequence of 8-bit
subpixel values (scanline order)
Predict each subpixel as a classification
among 256 values [0…255]
…
Model with an RNN or Transformer
Problem: Too expensive. 1024x1024
image is a sequence of 3M subpixels …
Solution (jumping ahead): Model as
sequence of tiles, not sequence of subpixels … … … |
| Stanford CS231n 10th Anniversary Lecture 13 - 59 May 15, 2025 |


### Table 2

|  |  |
|  |  |
|  |  |


### Table 3

|  |  |
|  |  |
|  |  |


### Table 4

|  |  |
|  |  |
|  |  |


### Table 5

|  |  |
|  |  |
|  |  |


### Table 6

|  |  |
|  |  |
|  |  |


### Table 7

|  |  |
|  |  |
|  |  |


[Page contains 1 image(s)]


---
## Page 60
---


Variational Autoencoders (VAEs)
Stanford CS231n 10th Anniversary Lecture 13 - 60 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders (VAEs) |
| Stanford CS231n 10th Anniversary Lecture 13 - 60 May 15, 2025 |


---
## Page 61
---


Variational Autoencoders
PixelRNN / PixelCNN explicitly parameterizes density function with a
neural network, so we can train to maximize likelihood of training data:
𝑇
p (𝑥) = ෑ 𝑝 𝑥 𝑥 , … , 𝑥 )
𝑊 𝑊 𝑡 1 𝑡−1
𝑡=1
Variational Autoencoders (VAE) define an intractable density that we
cannot explicitly compute or optimize
But we will be able to directly optimize a lower bound on the density
Stanford CS231n 10th Anniversary Lecture 13 - 61 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders
PixelRNN / PixelCNN explicitly parameterizes density function with a
neural network, so we can train to maximize likelihood of training data:
𝑇
p (𝑥) = ෑ 𝑝 𝑥 𝑥 , … , 𝑥 )
𝑊 𝑊 𝑡 1 𝑡−1
𝑡=1
Variational Autoencoders (VAE) define an intractable density that we
cannot explicitly compute or optimize
But we will be able to directly optimize a lower bound on the density |
| Stanford CS231n 10th Anniversary Lecture 13 - 61 May 15, 2025 |


---
## Page 62
---


Variational Autoencoders (VAEs)
Stanford CS231n 10th Anniversary Lecture 13 - 62 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders (VAEs) |
| Stanford CS231n 10th Anniversary Lecture 13 - 62 May 15, 2025 |


---
## Page 63
---


(Non-Variational) Autoencoders
Idea: Unsupervised method for learning to extract features z from inputs x, without labels
Features should extract useful information
(object identity, appearance, scene type, etc)
that can be used for downstream tasks
Encoder can be MLP,
CNN, Transformer, …
Features
Encoder
Input data
Input Data
Stanford CS231n 10th Anniversary Lecture 13 - 63 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| (Non-Variational) Autoencoders
Idea: Unsupervised method for learning to extract features z from inputs x, without labels
Features should extract useful information
(object identity, appearance, scene type, etc)
that can be used for downstream tasks
Encoder can be MLP,
CNN, Transformer, …
Features
Encoder
Input data
Input Data |
| Stanford CS231n 10th Anniversary Lecture 13 - 63 May 15, 2025 |


[Page contains 3 image(s)]


---
## Page 64
---


(Non-Variational) Autoencoders
Problem: How can we learn without labels?
Features should extract useful information
(object identity, appearance, scene type, etc)
that can be used for downstream tasks
Encoder can be MLP,
CNN, Transformer, …
Features
Encoder
Input data
Input Data
Stanford CS231n 10th Anniversary Lecture 13 - 64 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| (Non-Variational) Autoencoders
Problem: How can we learn without labels?
Features should extract useful information
(object identity, appearance, scene type, etc)
that can be used for downstream tasks
Encoder can be MLP,
CNN, Transformer, …
Features
Encoder
Input data
Input Data |
| Stanford CS231n 10th Anniversary Lecture 13 - 64 May 15, 2025 |


[Page contains 3 image(s)]


---
## Page 65
---


(Non-Variational) Autoencoders
“Autoencoding” =
Encoding yourself
Problem: How can we learn without labels?
Decoder can be MLP,
Solution: Reconstruct the input data with a decoder.
CNN, Transformer, …
Reconstructed
input data
Decoder
Features
Encoder
Input data
Input Data
Stanford CS231n 10th Anniversary Lecture 13 - 65 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| (Non-Variational) Autoencoders
“Autoencoding” =
Encoding yourself
Problem: How can we learn without labels?
Decoder can be MLP,
Solution: Reconstruct the input data with a decoder.
CNN, Transformer, …
Reconstructed
input data
Decoder
Features
Encoder
Input data
Input Data |
| Stanford CS231n 10th Anniversary Lecture 13 - 65 May 15, 2025 |


[Page contains 3 image(s)]


---
## Page 66
---


(Non-Variational) Autoencoders Reconstructed data
Loss: L2 distance between input and reconstructed data.
Loss Function
Does not use any
2
labels! Just raw data! 𝑥ො − 𝑥
2
Reconstructed
input data
Decoder
Features
Encoder
Input data
Input Data
Stanford CS231n 10th Anniversary Lecture 13 - 66 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| (Non-Variational) Autoencoders Reconstructed data
Loss: L2 distance between input and reconstructed data.
Loss Function
Does not use any
2
labels! Just raw data! 𝑥ො − 𝑥
2
Reconstructed
input data
Decoder
Features
Encoder
Input data
Input Data |
| Stanford CS231n 10th Anniversary Lecture 13 - 66 May 15, 2025 |


[Page contains 5 image(s)]


---
## Page 67
---


(Non-Variational) Autoencoders Reconstructed data
After training, can use encoder for downstream tasks
Loss Function
(Softmax)
Predicted label
Classifier
Features
Encoder
Input data
Input Data
Stanford CS231n 10th Anniversary Lecture 13 - 67 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| (Non-Variational) Autoencoders Reconstructed data
After training, can use encoder for downstream tasks
Loss Function
(Softmax)
Predicted label
Classifier
Features
Encoder
Input data
Input Data |
| Stanford CS231n 10th Anniversary Lecture 13 - 67 May 15, 2025 |


[Page contains 6 image(s)]


---
## Page 68
---


(Non-Variational) Autoencoders
If we could generate new z, could use the decoder to generate images
Generated image
Decoder
Features
Stanford CS231n 10th Anniversary Lecture 13 - 68 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| (Non-Variational) Autoencoders
If we could generate new z, could use the decoder to generate images
Generated image
Decoder
Features |
| Stanford CS231n 10th Anniversary Lecture 13 - 68 May 15, 2025 |


[Page contains 2 image(s)]


---
## Page 69
---


(Non-Variational) Autoencoders
If we could generate new z, could use the decoder to generate images
Generated image
Decoder
Features
Problem: Generating new z is not any easier than generating new x
Stanford CS231n 10th Anniversary Lecture 13 - 69 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| (Non-Variational) Autoencoders
If we could generate new z, could use the decoder to generate images
Generated image
Decoder
Features
Problem: Generating new z is not any easier than generating new x |
| Stanford CS231n 10th Anniversary Lecture 13 - 69 May 15, 2025 |


[Page contains 2 image(s)]


---
## Page 70
---


(Non-Variational) Autoencoders
If we could generate new z, could use the decoder to generate images
Generated image
Decoder
Features
Problem: Generating new z is not any easier than generating new x
Solution: What if we force all z to come from a known distribution?
Stanford CS231n 10th Anniversary Lecture 13 - 70 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| (Non-Variational) Autoencoders
If we could generate new z, could use the decoder to generate images
Generated image
Decoder
Features
Problem: Generating new z is not any easier than generating new x
Solution: What if we force all z to come from a known distribution? |
| Stanford CS231n 10th Anniversary Lecture 13 - 70 May 15, 2025 |


[Page contains 2 image(s)]


---
## Page 71
---


Variational Autoencoders (VAEs)
Kingma and Welling, Auto-Encoding Variational Beyes, ICLR 2014
Stanford CS231n 10th Anniversary Lecture 13 - 71 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders (VAEs)
Kingma and Welling, Auto-Encoding Variational Beyes, ICLR 2014 |
| Stanford CS231n 10th Anniversary Lecture 13 - 71 May 15, 2025 |


---
## Page 72
---


Variational Autoencoders
Probabilistic spin on autoencoders:
1. Learn latent features z from raw data
2. Sample from the model to generate new data
Stanford CS231n 10th Anniversary Lecture 13 - 72 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders
Probabilistic spin on autoencoders:
1. Learn latent features z from raw data
2. Sample from the model to generate new data |
| Stanford CS231n 10th Anniversary Lecture 13 - 72 May 15, 2025 |


---
## Page 73
---


Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
Intuition: x is an image, z is latent
factors used to generate x: attributes,
orientation, etc.
Stanford CS231n 10th Anniversary Lecture 13 - 73 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
Intuition: x is an image, z is latent
factors used to generate x: attributes,
orientation, etc. |
| Stanford CS231n 10th Anniversary Lecture 13 - 73 May 15, 2025 |


---
## Page 74
---


Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
After training, sample new data like this: Intuition: x is an image, z is latent
factors used to generate x: attributes,
Sample from orientation, etc.
conditional
Sample z
from prior
Stanford CS231n 10th Anniversary Lecture 13 - 74 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
After training, sample new data like this: Intuition: x is an image, z is latent
factors used to generate x: attributes,
Sample from orientation, etc.
conditional
Sample z
from prior |
| Stanford CS231n 10th Anniversary Lecture 13 - 74 May 15, 2025 |


[Page contains 4 image(s)]


---
## Page 75
---


Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
After training, sample new data like this: Intuition: x is an image, z is latent
factors used to generate x: attributes,
Sample from orientation, etc.
conditional
Assume simple prior p(z), e.g. Gaussian
Sample z
from prior
Stanford CS231n 10th Anniversary Lecture 13 - 75 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
After training, sample new data like this: Intuition: x is an image, z is latent
factors used to generate x: attributes,
Sample from orientation, etc.
conditional
Assume simple prior p(z), e.g. Gaussian
Sample z
from prior |
| Stanford CS231n 10th Anniversary Lecture 13 - 75 May 15, 2025 |


[Page contains 4 image(s)]


---
## Page 76
---


Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
How can we train this?
After training, sample new data like this:
Basic idea: maximum likelihood
Sample from
conditional
If we had a dataset of (x, z) then train a
conditional generative model p(x | z)
Sample z
from prior
Stanford CS231n 10th Anniversary Lecture 13 - 76 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
How can we train this?
After training, sample new data like this:
Basic idea: maximum likelihood
Sample from
conditional
If we had a dataset of (x, z) then train a
conditional generative model p(x | z)
Sample z
from prior |
| Stanford CS231n 10th Anniversary Lecture 13 - 76 May 15, 2025 |


[Page contains 4 image(s)]


---
## Page 77
---


Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
How can we train this?
After training, sample new data like this:
Basic idea: maximum likelihood
Sample from
conditional
We don’t observe z, so marginalize:
𝑝 𝑥 = න𝑝 𝑥, 𝑧 𝑑𝑧 = න 𝑝 𝑥 𝑧 𝑝 𝑧 𝑑𝑧
Sample z
𝜃 𝜃 𝜃 𝜃
from prior
Stanford CS231n 10th Anniversary Lecture 13 - 77 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
How can we train this?
After training, sample new data like this:
Basic idea: maximum likelihood
Sample from
conditional
We don’t observe z, so marginalize:
𝑝 𝑥 = න𝑝 𝑥, 𝑧 𝑑𝑧 = න 𝑝 𝑥 𝑧 𝑝 𝑧 𝑑𝑧
Sample z
𝜃 𝜃 𝜃 𝜃
from prior |  |  |
|  | Basic idea: maximum likelihood
We don’t observe z, so marginalize:
𝑝 𝑥 = න𝑝 𝑥, 𝑧 𝑑𝑧 = න 𝑝 𝑥 𝑧 𝑝 𝑧 𝑑𝑧
𝜃 𝜃 𝜃 𝜃 |  |
| Stanford CS231n 10th Anniversary | Lecture 13 - 77 May 15, 2025 |  |
|  |  |  |


[Page contains 4 image(s)]


---
## Page 78
---


Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
How can we train this?
After training, sample new data like this:
Basic idea: maximum likelihood
Sample from
conditional
We don’t observe z, so marginalize:
𝑝 𝑥 = න𝑝 𝑥, 𝑧 𝑑𝑧 = න 𝑝 𝑥 𝑧 𝑝 𝑧 𝑑𝑧
Sample z
𝜃 𝜃 𝜃 𝜃
from prior
Ok, we can compute this with the decoder
Stanford CS231n 10th Anniversary Lecture 13 - 78 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
How can we train this?
After training, sample new data like this:
Basic idea: maximum likelihood
Sample from
conditional
We don’t observe z, so marginalize:
𝑝 𝑥 = න𝑝 𝑥, 𝑧 𝑑𝑧 = න 𝑝 𝑥 𝑧 𝑝 𝑧 𝑑𝑧
Sample z
𝜃 𝜃 𝜃 𝜃
from prior
Ok, we can compute this with the decoder |  |  |
|  | Basic idea: maximum likelihood
We don’t observe z, so marginalize:
𝑝 𝑥 = න𝑝 𝑥, 𝑧 𝑑𝑧 = න 𝑝 𝑥 𝑧 𝑝 𝑧 𝑑𝑧
𝜃 𝜃 𝜃 𝜃
Ok, we can compute this with the decoder |  |
| Stanford CS231n 10th Anniversary | Lecture 13 - 78 May 15, 2025 |  |
|  |  |  |


[Page contains 4 image(s)]


---
## Page 79
---


Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
How can we train this?
After training, sample new data like this:
Basic idea: maximum likelihood
Sample from
conditional
We don’t observe z, so marginalize:
𝑝 𝑥 = න𝑝 𝑥, 𝑧 𝑑𝑧 = න 𝑝 𝑥 𝑧 𝑝 𝑧 𝑑𝑧
Sample z
𝜃 𝜃 𝜃 𝜃
from prior
Ok, we assumed Gaussian prior for z
Stanford CS231n 10th Anniversary Lecture 13 - 79 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
How can we train this?
After training, sample new data like this:
Basic idea: maximum likelihood
Sample from
conditional
We don’t observe z, so marginalize:
𝑝 𝑥 = න𝑝 𝑥, 𝑧 𝑑𝑧 = න 𝑝 𝑥 𝑧 𝑝 𝑧 𝑑𝑧
Sample z
𝜃 𝜃 𝜃 𝜃
from prior
Ok, we assumed Gaussian prior for z |  |  |
|  | Basic idea: maximum likelihood
We don’t observe z, so marginalize:
𝑝 𝑥 = න𝑝 𝑥, 𝑧 𝑑𝑧 = න 𝑝 𝑥 𝑧 𝑝 𝑧 𝑑𝑧
𝜃 𝜃 𝜃 𝜃
Ok, we assumed Gaussian prior for z |  |
| Stanford CS231n 10th Anniversary | Lecture 13 - 79 May 15, 2025 |  |
|  |  |  |


[Page contains 4 image(s)]


---
## Page 80
---


Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
How can we train this?
After training, sample new data like this:
Basic idea: maximum likelihood
Sample from
conditional
We don’t observe z, so marginalize:
𝑝 𝑥 = න𝑝 𝑥, 𝑧 𝑑𝑧 = න𝑝 𝑥 𝑧 𝑝 𝑧 𝒅𝒛
Sample z
𝜃 𝜃 𝜃 𝜃
from prior
Problem, we can’t integrate over all z
Stanford CS231n 10th Anniversary Lecture 13 - 80 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
How can we train this?
After training, sample new data like this:
Basic idea: maximum likelihood
Sample from
conditional
We don’t observe z, so marginalize:
𝑝 𝑥 = න𝑝 𝑥, 𝑧 𝑑𝑧 = න𝑝 𝑥 𝑧 𝑝 𝑧 𝒅𝒛
Sample z
𝜃 𝜃 𝜃 𝜃
from prior
Problem, we can’t integrate over all z |  |  |
|  | Basic idea: maximum likelihood
We don’t observe z, so marginalize:
𝑝 𝑥 = න𝑝 𝑥, 𝑧 𝑑𝑧 = න𝑝 𝑥 𝑧 𝑝 𝑧 𝒅𝒛
𝜃 𝜃 𝜃 𝜃
Problem, we can’t integrate over all z |  |
| Stanford CS231n 10th Anniversary | Lecture 13 - 80 May 15, 2025 |  |
|  |  |  |


[Page contains 4 image(s)]


---
## Page 81
---


Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
How can we train this?
After training, sample new data like this:
Basic idea: maximum likelihood
Sample from
conditional
Another idea: Try Bayes’ Rule:
𝑝 𝑥 𝑧)𝑝 (𝑧)
𝜃 𝜃
𝑝 𝑥 =
Sample z 𝜃
𝑝 𝑧 | 𝑥
𝜃
from prior
Stanford CS231n 10th Anniversary Lecture 13 - 81 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
How can we train this?
After training, sample new data like this:
Basic idea: maximum likelihood
Sample from
conditional
Another idea: Try Bayes’ Rule:
𝑝 𝑥 𝑧)𝑝 (𝑧)
𝜃 𝜃
𝑝 𝑥 =
Sample z 𝜃
𝑝 𝑧 | 𝑥
𝜃
from prior |
| Stanford CS231n 10th Anniversary Lecture 13 - 81 May 15, 2025 |


[Page contains 4 image(s)]


---
## Page 82
---


Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
How can we train this?
After training, sample new data like this:
Basic idea: maximum likelihood
Sample from
conditional
Another idea: Try Bayes’ Rule:
𝑝 𝑥 𝑧)𝑝 (𝑧)
𝜃 𝜃
𝑝 𝑥 =
Sample z 𝜃
𝑝 𝑧 | 𝑥
𝜃
from prior
Ok, we can compute this with the decoder
Stanford CS231n 10th Anniversary Lecture 13 - 82 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
How can we train this?
After training, sample new data like this:
Basic idea: maximum likelihood
Sample from
conditional
Another idea: Try Bayes’ Rule:
𝑝 𝑥 𝑧)𝑝 (𝑧)
𝜃 𝜃
𝑝 𝑥 =
Sample z 𝜃
𝑝 𝑧 | 𝑥
𝜃
from prior
Ok, we can compute this with the decoder |
| Stanford CS231n 10th Anniversary Lecture 13 - 82 May 15, 2025 |


[Page contains 4 image(s)]


---
## Page 83
---


Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
How can we train this?
After training, sample new data like this:
Basic idea: maximum likelihood
Sample from
conditional
Another idea: Try Bayes’ Rule:
𝑝 𝑥 𝑧)𝑝 (𝑧)
𝜃 𝜃
𝑝 𝑥 =
Sample z 𝜃
𝑝 𝑧 | 𝑥
𝜃
from prior
Ok, we assumed Gaussian prior for z
Stanford CS231n 10th Anniversary Lecture 13 - 83 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
How can we train this?
After training, sample new data like this:
Basic idea: maximum likelihood
Sample from
conditional
Another idea: Try Bayes’ Rule:
𝑝 𝑥 𝑧)𝑝 (𝑧)
𝜃 𝜃
𝑝 𝑥 =
Sample z 𝜃
𝑝 𝑧 | 𝑥
𝜃
from prior
Ok, we assumed Gaussian prior for z |
| Stanford CS231n 10th Anniversary Lecture 13 - 83 May 15, 2025 |


[Page contains 4 image(s)]


---
## Page 84
---


Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
How can we train this?
After training, sample new data like this:
Basic idea: maximum likelihood
Sample from
conditional
Another idea: Try Bayes’ Rule:
𝑝 𝑥 𝑧)𝑝 (𝑧)
𝜃 𝜃 Problem: no way
𝑝 𝑥 =
Sample z 𝜃
𝑝 𝑧 | 𝑥 to compute this
𝜃
from prior
Stanford CS231n 10th Anniversary Lecture 13 - 84 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
How can we train this?
After training, sample new data like this:
Basic idea: maximum likelihood
Sample from
conditional
Another idea: Try Bayes’ Rule:
𝑝 𝑥 𝑧)𝑝 (𝑧)
𝜃 𝜃 Problem: no way
𝑝 𝑥 =
Sample z 𝜃
𝑝 𝑧 | 𝑥 to compute this
𝜃
from prior |
| Stanford CS231n 10th Anniversary Lecture 13 - 84 May 15, 2025 |


[Page contains 4 image(s)]


---
## Page 85
---


Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
How can we train this?
After training, sample new data like this:
Basic idea: maximum likelihood
Sample from
conditional
Another idea: Try Bayes’ Rule:
𝑝 𝑥 𝑧)𝑝 (𝑧)
𝜃 𝜃 Problem: no way
𝑝 𝑥 =
Sample z 𝜃
𝑝 𝑧 | 𝑥 to compute this
𝜃
from prior
Solution: Train another network
that learns 𝑞 𝑧 𝑥) ≈ 𝑝 𝑧 𝑥)
𝜙 𝜃
Stanford CS231n 10th Anniversary Lecture 13 - 85 May 15, 2025

[Page contains 2 table(s)]


### Table 1

| Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
How can we train this?
After training, sample new data like this:
Basic idea: maximum likelihood
Sample from
conditional
Another idea: Try Bayes’ Rule:
𝑝 𝑥 𝑧)𝑝 (𝑧)
𝜃 𝜃 Problem: no way
𝑝 𝑥 =
Sample z 𝜃
𝑝 𝑧 | 𝑥 to compute this
𝜃
from prior
Solution: Train another network
that learns 𝑞 𝑧 𝑥) ≈ 𝑝 𝑧 𝑥)
𝜙 𝜃 |
| Stanford CS231n 10th Anniversary Lecture 13 - 85 May 15, 2025 |


### Table 2

| 𝑝 𝑥 𝑧)𝑝 (𝑧)
𝜃 𝜃
𝑝 𝑥 =
𝜃
𝑝 𝑧 | 𝑥
𝜃 |  |
|  |  |


[Page contains 4 image(s)]


---
## Page 86
---


Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
How can we train this?
After training, sample new data like this:
Basic idea: maximum likelihood
Sample from
conditional
Another idea: Try Bayes’ Rule:
𝑝 𝑥 𝑧)𝑝 (𝑧) 𝑝 𝑥 𝑧)𝑝 (𝑧)
𝜃 𝜃 𝜃 𝜃
𝑝 𝑥 = ≈
Sample z 𝜃
𝑝 𝑧 | 𝑥 𝑞 𝑧 | 𝑥
𝜃 𝜙
from prior
Solution: Train another network
that learns 𝑞 𝑧 𝑥) ≈ 𝑝 𝑧 𝑥)
𝜙 𝜃
Stanford CS231n 10th Anniversary Lecture 13 - 86 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders
𝑁
Probabilistic spin on autoencoders: Assume training data 𝑥 𝑖 is
𝑖=1
1. Learn latent features z from raw data
generated from unobserved (latent)
2. Sample from the model to generate new data
representation z
How can we train this?
After training, sample new data like this:
Basic idea: maximum likelihood
Sample from
conditional
Another idea: Try Bayes’ Rule:
𝑝 𝑥 𝑧)𝑝 (𝑧) 𝑝 𝑥 𝑧)𝑝 (𝑧)
𝜃 𝜃 𝜃 𝜃
𝑝 𝑥 = ≈
Sample z 𝜃
𝑝 𝑧 | 𝑥 𝑞 𝑧 | 𝑥
𝜃 𝜙
from prior
Solution: Train another network
that learns 𝑞 𝑧 𝑥) ≈ 𝑝 𝑧 𝑥)
𝜙 𝜃 |  |  |  |
|  | 𝑝 𝑥 𝑧)𝑝 (𝑧) 𝑝 𝑥 𝑧)𝑝 (𝑧)
𝜃 𝜃 𝜃 𝜃
𝑝 𝑥 = ≈
𝜃
𝑝 𝑧 | 𝑥 𝑞 𝑧 | 𝑥
𝜃 𝜙 |  |  |
|  |  |  |  |
|  |  | Solution: Train another network
that learns 𝑞 𝑧 𝑥) ≈ 𝑝 𝑧 𝑥)
𝜙 𝜃 |  |
| Stanford CS231n 10th Anniversary Lecture 13 - 86 May 15, 2025 |  |  |  |


[Page contains 4 image(s)]


---
## Page 87
---


Variational Autoencoders
If we can ensure that
𝑞 𝑧 𝑥) ≈ 𝑝 𝑧 𝑥),
𝜙 𝜃
Encoder Network:
Decoder Network:
Input data x,
Input latent code z,
then we can approximate
Output distribution
Output distribution over data x
over latent codes z 𝑝 𝑥 𝑧)𝑝(𝑧)
𝜃
𝑝 𝑥 ≈
𝜃
𝑞 𝑧 𝑥)
𝜙
Idea: Jointly train both
encoder and decoder
𝑝 𝑥 𝑧) 𝑞 𝑧 | 𝑥
𝜃 𝜙
𝑧 𝑥
Stanford CS231n 10th Anniversary Lecture 13 - 87 May 15, 2025

[Page contains 2 table(s)]


### Table 1

| Variational Autoencoders
If we can ensure that
𝑞 𝑧 𝑥) ≈ 𝑝 𝑧 𝑥),
𝜙 𝜃
Encoder Network:
Decoder Network:
Input data x,
Input latent code z,
then we can approximate
Output distribution
Output distribution over data x
over latent codes z 𝑝 𝑥 𝑧)𝑝(𝑧)
𝜃
𝑝 𝑥 ≈
𝜃
𝑞 𝑧 𝑥)
𝜙
Idea: Jointly train both
encoder and decoder
𝑝 𝑥 𝑧) 𝑞 𝑧 | 𝑥
𝜃 𝜙
𝑧 𝑥 |
| Stanford CS231n 10th Anniversary Lecture 13 - 87 May 15, 2025 |


### Table 2

| If we can ensure that
𝑞 𝑧 𝑥) ≈ 𝑝 𝑧 𝑥),
𝜙 𝜃
then we can approximate
𝑝 𝑥 𝑧)𝑝(𝑧)
𝜃
𝑝 𝑥 ≈
𝜃
𝑞 𝑧 𝑥)
𝜙
Idea: Jointly train both
encoder and decoder |  |


---
## Page 88
---


Variational Autoencoders
If we can ensure that
𝑞 𝑧 𝑥) ≈ 𝑝 𝑧 𝑥),
𝜙 𝜃
Encoder Network:
Decoder Network:
Input data x,
Input latent code z,
then we can approximate
Output distribution
Output distribution over data x
over latent codes z 𝑝 𝑥 𝑧)𝑝(𝑧)
𝜃
𝑝 𝑥 ≈
𝜃
𝑞 𝑧 𝑥)
𝜙
Idea: Jointly train both
encoder and decoder
𝑝 𝑥 𝑧) 𝑞 𝑧 | 𝑥
𝜃 𝜙
Aside: How to output probability
distributions from neural networks?
Network outputs mean (and std) of
𝑧 𝑥
a (diagonal) distribution
Stanford CS231n 10th Anniversary Lecture 13 - 88 May 15, 2025

[Page contains 2 table(s)]


### Table 1

| Variational Autoencoders
If we can ensure that
𝑞 𝑧 𝑥) ≈ 𝑝 𝑧 𝑥),
𝜙 𝜃
Encoder Network:
Decoder Network:
Input data x,
Input latent code z,
then we can approximate
Output distribution
Output distribution over data x
over latent codes z 𝑝 𝑥 𝑧)𝑝(𝑧)
𝜃
𝑝 𝑥 ≈
𝜃
𝑞 𝑧 𝑥)
𝜙
Idea: Jointly train both
encoder and decoder
𝑝 𝑥 𝑧) 𝑞 𝑧 | 𝑥
𝜃 𝜙
Aside: How to output probability
distributions from neural networks?
Network outputs mean (and std) of
𝑧 𝑥
a (diagonal) distribution |
| Stanford CS231n 10th Anniversary Lecture 13 - 88 May 15, 2025 |


### Table 2

| If we can ensure that
𝑞 𝑧 𝑥) ≈ 𝑝 𝑧 𝑥),
𝜙 𝜃
then we can approximate
𝑝 𝑥 𝑧)𝑝(𝑧)
𝜃
𝑝 𝑥 ≈
𝜃
𝑞 𝑧 𝑥)
𝜙
Idea: Jointly train both
encoder and decoder |  |


---
## Page 89
---


Variational Autoencoders
If we can ensure that
𝑞 𝑧 𝑥) ≈ 𝑝 𝑧 𝑥),
𝜙 𝜃
Encoder Network:
Decoder Network:
Input data x,
Input latent code z,
then we can approximate
Output distribution
Output distribution over data x
over latent codes z 𝑝 𝑥 𝑧)𝑝(𝑧)
𝜃
𝑝 𝑥 ≈
𝑝 𝑥 | 𝑧 = 𝑁(𝜇 , 𝜎2) 𝑞 𝑧 | 𝑥 = 𝑁(𝜇 , Σ ) 𝜃 𝑞 𝑧 𝑥)
𝜃 𝑥|𝑧 𝜙 𝑧|𝑥 𝑧|𝑥 𝜙
Idea: Jointly train both
encoder and decoder
𝜇 𝜇 Σ
𝑥|𝑧 𝑧|𝑥 𝑧|𝑥
Aside: How to output probability
distributions from neural networks?
Network outputs mean (and std) of
𝑧 𝑥
a (diagonal) distribution
Stanford CS231n 10th Anniversary Lecture 13 - 89 May 15, 2025

[Page contains 2 table(s)]


### Table 1

| Variational Autoencoders
If we can ensure that
𝑞 𝑧 𝑥) ≈ 𝑝 𝑧 𝑥),
𝜙 𝜃
Encoder Network:
Decoder Network:
Input data x,
Input latent code z,
then we can approximate
Output distribution
Output distribution over data x
over latent codes z 𝑝 𝑥 𝑧)𝑝(𝑧)
𝜃
𝑝 𝑥 ≈
𝑝 𝑥 | 𝑧 = 𝑁(𝜇 , 𝜎2) 𝑞 𝑧 | 𝑥 = 𝑁(𝜇 , Σ ) 𝜃 𝑞 𝑧 𝑥)
𝜃 𝑥|𝑧 𝜙 𝑧|𝑥 𝑧|𝑥 𝜙
Idea: Jointly train both
encoder and decoder
𝜇 𝜇 Σ
𝑥|𝑧 𝑧|𝑥 𝑧|𝑥
Aside: How to output probability
distributions from neural networks?
Network outputs mean (and std) of
𝑧 𝑥
a (diagonal) distribution |
| Stanford CS231n 10th Anniversary Lecture 13 - 89 May 15, 2025 |


### Table 2

| If we can ensure that
𝑞 𝑧 𝑥) ≈ 𝑝 𝑧 𝑥),
𝜙 𝜃
then we can approximate
𝑝 𝑥 𝑧)𝑝(𝑧)
𝜃
𝑝 𝑥 ≈
𝜃
𝑞 𝑧 𝑥)
𝜙
Idea: Jointly train both
encoder and decoder |  |


---
## Page 90
---


Variational Autoencoders
If we can ensure that
𝑞 𝑧 𝑥) ≈ 𝑝 𝑧 𝑥),
𝜙 𝜃
Encoder Network:
Decoder Network:
Input data x,
Input latent code z,
then we can approximate
Output distribution
Output distribution over data x
over latent codes z 𝑝 𝑥 𝑧)𝑝(𝑧)
𝜃
𝑝 𝑥 ≈
𝑝 𝑥 | 𝑧 = 𝑁(𝜇 , 𝜎2) 𝑞 𝑧 | 𝑥 = 𝑁(𝜇 , Σ ) 𝜃 𝑞 𝑧 𝑥)
𝜃 𝑥|𝑧 𝜙 𝑧|𝑥 𝑧|𝑥 𝜙
1
2
log 𝑝 𝑥 𝑧) = − 𝑥 − 𝜇 + 𝐶
𝜃 2𝜎2 2 2 Idea: Jointly train both
encoder and decoder
𝜇 𝜇 Σ
𝑥|𝑧 𝑧|𝑥 𝑧|𝑥
Maximizing log 𝑝 𝑥 𝑧) is
𝜃
equivalent to minimizing
L2 distance between x
𝑧 𝑥 and network output!
Stanford CS231n 10th Anniversary Lecture 13 - 90 May 15, 2025

[Page contains 3 table(s)]


### Table 1

| Variational Autoencoders
If we can ensure that
𝑞 𝑧 𝑥) ≈ 𝑝 𝑧 𝑥),
𝜙 𝜃
Encoder Network:
Decoder Network:
Input data x,
Input latent code z,
then we can approximate
Output distribution
Output distribution over data x
over latent codes z 𝑝 𝑥 𝑧)𝑝(𝑧)
𝜃
𝑝 𝑥 ≈
𝑝 𝑥 | 𝑧 = 𝑁(𝜇 , 𝜎2) 𝑞 𝑧 | 𝑥 = 𝑁(𝜇 , Σ ) 𝜃 𝑞 𝑧 𝑥)
𝜃 𝑥|𝑧 𝜙 𝑧|𝑥 𝑧|𝑥 𝜙
1
2
log 𝑝 𝑥 𝑧) = − 𝑥 − 𝜇 + 𝐶
𝜃 2𝜎2 2 2 Idea: Jointly train both
encoder and decoder
𝜇 𝜇 Σ
𝑥|𝑧 𝑧|𝑥 𝑧|𝑥
Maximizing log 𝑝 𝑥 𝑧) is
𝜃
equivalent to minimizing
L2 distance between x
𝑧 𝑥 and network output! |
| Stanford CS231n 10th Anniversary Lecture 13 - 90 May 15, 2025 |


### Table 2

| If we can ensure that
𝑞 𝑧 𝑥) ≈ 𝑝 𝑧 𝑥),
𝜙 𝜃
then we can approximate
𝑝 𝑥 𝑧)𝑝(𝑧)
𝜃
𝑝 𝑥 ≈
𝜃
𝑞 𝑧 𝑥)
𝜙
Idea: Jointly train both
encoder and decoder |  |
|  |  |
| Maximizing log 𝑝 𝑥 𝑧) is
𝜃
equivalent to minimizing
L2 distance between x
and network output! |  |


### Table 3

| 𝑝 𝑥 | 𝑧 = 𝑁(𝜇 , 𝜎2)
𝜃 𝑥|𝑧 |
| 1
2
log 𝑝 𝑥 𝑧) = − 𝑥 − 𝜇 + 𝐶
𝜃 2𝜎2 2 2 |


---
## Page 91
---


Variational Autoencoders
If we can ensure that
𝑞 𝑧 𝑥) ≈ 𝑝 𝑧 𝑥),
𝜙 𝜃
Encoder Network:
Decoder Network:
Input data x,
Input latent code z,
then we can approximate
Output distribution
Output distribution over data x
over latent codes z 𝑝 𝑥 𝑧)𝑝(𝑧)
𝜃
𝑝 𝑥 ≈
𝑝 𝑥 | 𝑧 = 𝑁(𝜇 , 𝜎2) 𝑞 𝑧 | 𝑥 = 𝑁(𝜇 , Σ ) 𝜃 𝑞 𝑧 𝑥)
𝜃 𝑥|𝑧 𝜙 𝑧|𝑥 𝑧|𝑥 𝜙
1
2
log 𝑝 𝑥 𝑧) = − 𝑥 − 𝜇 + 𝐶
𝜃 2𝜎2 2 2 Idea: Jointly train both
encoder and decoder
𝜇 𝜇 Σ
𝑥|𝑧 𝑧|𝑥 𝑧|𝑥
Q: What’s our
training objective?
𝑧 𝑥
Stanford CS231n 10th Anniversary Lecture 13 - 91 May 15, 2025

[Page contains 3 table(s)]


### Table 1

| Variational Autoencoders
If we can ensure that
𝑞 𝑧 𝑥) ≈ 𝑝 𝑧 𝑥),
𝜙 𝜃
Encoder Network:
Decoder Network:
Input data x,
Input latent code z,
then we can approximate
Output distribution
Output distribution over data x
over latent codes z 𝑝 𝑥 𝑧)𝑝(𝑧)
𝜃
𝑝 𝑥 ≈
𝑝 𝑥 | 𝑧 = 𝑁(𝜇 , 𝜎2) 𝑞 𝑧 | 𝑥 = 𝑁(𝜇 , Σ ) 𝜃 𝑞 𝑧 𝑥)
𝜃 𝑥|𝑧 𝜙 𝑧|𝑥 𝑧|𝑥 𝜙
1
2
log 𝑝 𝑥 𝑧) = − 𝑥 − 𝜇 + 𝐶
𝜃 2𝜎2 2 2 Idea: Jointly train both
encoder and decoder
𝜇 𝜇 Σ
𝑥|𝑧 𝑧|𝑥 𝑧|𝑥
Q: What’s our
training objective?
𝑧 𝑥 |
| Stanford CS231n 10th Anniversary Lecture 13 - 91 May 15, 2025 |


### Table 2

| If we can ensure that
𝑞 𝑧 𝑥) ≈ 𝑝 𝑧 𝑥),
𝜙 𝜃
then we can approximate
𝑝 𝑥 𝑧)𝑝(𝑧)
𝜃
𝑝 𝑥 ≈
𝜃
𝑞 𝑧 𝑥)
𝜙
Idea: Jointly train both
encoder and decoder |  |


### Table 3

| 𝑝 𝑥 | 𝑧 = 𝑁(𝜇 , 𝜎2)
𝜃 𝑥|𝑧 |
| 1
2
log 𝑝 𝑥 𝑧) = − 𝑥 − 𝜇 + 𝐶
𝜃 2𝜎2 2 2 |


---
## Page 92
---


Variational Autoencoders (ELBO)
𝑝 𝑥 𝑧)𝑝(𝑧) 𝑝 𝑥 𝑧 𝑝 𝑧 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
log 𝑝 (𝑥) = log = log
𝜃
𝑝 𝑧 𝑥) 𝑝 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
Bayes’ Rule
Stanford CS231n 10th Anniversary Lecture 13 - 92 May 15, 2025

[Page contains 2 table(s)]


### Table 1

| Variational Autoencoders (ELBO)
𝑝 𝑥 𝑧)𝑝(𝑧) 𝑝 𝑥 𝑧 𝑝 𝑧 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
log 𝑝 (𝑥) = log = log
𝜃
𝑝 𝑧 𝑥) 𝑝 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
Bayes’ Rule |
| Stanford CS231n 10th Anniversary Lecture 13 - 92 May 15, 2025 |


### Table 2

| 𝑝 𝑥 𝑧)𝑝(𝑧)
𝜃
log 𝑝 (𝑥) = log
𝜃
𝑝 𝑧 𝑥)
𝜃 | 𝑝 𝑥 𝑧 𝑝 𝑧 𝑞 (𝑧|𝑥)
𝜃 𝜙
= log
𝑝 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜃 𝜙 |


---
## Page 93
---


Variational Autoencoders (ELBO)
𝑝 𝑥 𝑧)𝑝(𝑧) 𝑝 𝑥 𝑧 𝑝 𝑧 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
log 𝑝 (𝑥) = log = log
𝜃
𝑝 𝑧 𝑥) 𝑝 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
Multiply top and bottom by q (z|x)
Φ
Stanford CS231n 10th Anniversary Lecture 13 - 93 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders (ELBO)
𝑝 𝑥 𝑧)𝑝(𝑧) 𝑝 𝑥 𝑧 𝑝 𝑧 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
log 𝑝 (𝑥) = log = log
𝜃
𝑝 𝑧 𝑥) 𝑝 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
Multiply top and bottom by q (z|x)
Φ |
| Stanford CS231n 10th Anniversary Lecture 13 - 93 May 15, 2025 |


---
## Page 94
---


Variational Autoencoders (ELBO)
𝑝 𝑥 𝑧)𝑝(𝑧) 𝑝 𝑥 𝑧 𝑝 𝑧 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
log 𝑝 (𝑥) = log = log
𝜃
𝑝 𝑧 𝑥) 𝑝 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
𝑞 𝑧|𝑥 𝑞 (𝑧|𝑥)
𝜙 𝜙
= log 𝑝 𝑥 𝑧 − log + log
𝜃
𝑝(𝑧) 𝑝 (𝑧|𝑥)
𝜃
Logarithms + rearranging
Stanford CS231n 10th Anniversary Lecture 13 - 94 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders (ELBO)
𝑝 𝑥 𝑧)𝑝(𝑧) 𝑝 𝑥 𝑧 𝑝 𝑧 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
log 𝑝 (𝑥) = log = log
𝜃
𝑝 𝑧 𝑥) 𝑝 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
𝑞 𝑧|𝑥 𝑞 (𝑧|𝑥)
𝜙 𝜙
= log 𝑝 𝑥 𝑧 − log + log
𝜃
𝑝(𝑧) 𝑝 (𝑧|𝑥)
𝜃
Logarithms + rearranging |
| Stanford CS231n 10th Anniversary Lecture 13 - 94 May 15, 2025 |


---
## Page 95
---


Variational Autoencoders (ELBO)
𝑝 𝑥 𝑧)𝑝(𝑧) 𝑝 𝑥 𝑧 𝑝 𝑧 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
log 𝑝 (𝑥) = log = log
𝜃
𝑝 𝑧 𝑥) 𝑝 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
𝑞 𝑧|𝑥 𝑞 (𝑧|𝑥)
𝜙 𝜙
= log 𝑝 𝑥 𝑧 − log + log
𝜃
𝑝(𝑧) 𝑝 (𝑧|𝑥)
𝜃
We can wrap in an
log 𝑝 𝑥 = 𝐸 log 𝑝 (𝑥) expectation since it
𝜃 𝑧~𝑞 (𝑧|𝑥) 𝜃
𝜙
doesn’t depend on z
Stanford CS231n 10th Anniversary Lecture 13 - 95 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders (ELBO)
𝑝 𝑥 𝑧)𝑝(𝑧) 𝑝 𝑥 𝑧 𝑝 𝑧 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
log 𝑝 (𝑥) = log = log
𝜃
𝑝 𝑧 𝑥) 𝑝 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
𝑞 𝑧|𝑥 𝑞 (𝑧|𝑥)
𝜙 𝜙
= log 𝑝 𝑥 𝑧 − log + log
𝜃
𝑝(𝑧) 𝑝 (𝑧|𝑥)
𝜃
We can wrap in an
log 𝑝 𝑥 = 𝐸 log 𝑝 (𝑥) expectation since it
𝜃 𝑧~𝑞 (𝑧|𝑥) 𝜃
𝜙
doesn’t depend on z |
| Stanford CS231n 10th Anniversary Lecture 13 - 95 May 15, 2025 |


---
## Page 96
---


Variational Autoencoders (ELBO)
𝑝 𝑥 𝑧)𝑝(𝑧) 𝑝 𝑥 𝑧 𝑝 𝑧 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
log 𝑝 (𝑥) = log = log
𝜃
𝑝 𝑧 𝑥) 𝑝 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
𝑞 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜙 𝜙
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐸 log + 𝐸 log
𝑧 𝜃 𝑧 𝑧
𝑝 𝑧 𝑝 (𝑧|𝑥)
𝜃
We can wrap in an
log 𝑝 𝑥 = 𝐸 log 𝑝 (𝑥) expectation since it
𝜃 𝑧~𝑞 (𝑧|𝑥) 𝜃
𝜙
doesn’t depend on z
Stanford CS231n 10th Anniversary Lecture 13 - 96 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders (ELBO)
𝑝 𝑥 𝑧)𝑝(𝑧) 𝑝 𝑥 𝑧 𝑝 𝑧 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
log 𝑝 (𝑥) = log = log
𝜃
𝑝 𝑧 𝑥) 𝑝 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
𝑞 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜙 𝜙
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐸 log + 𝐸 log
𝑧 𝜃 𝑧 𝑧
𝑝 𝑧 𝑝 (𝑧|𝑥)
𝜃
We can wrap in an
log 𝑝 𝑥 = 𝐸 log 𝑝 (𝑥) expectation since it
𝜃 𝑧~𝑞 (𝑧|𝑥) 𝜃
𝜙
doesn’t depend on z |
| Stanford CS231n 10th Anniversary Lecture 13 - 96 May 15, 2025 |


---
## Page 97
---


Variational Autoencoders (ELBO)
𝑝 𝑥 𝑧)𝑝(𝑧) 𝑝 𝑥 𝑧 𝑝 𝑧 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
log 𝑝 (𝑥) = log = log
𝜃
𝑝 𝑧 𝑥) 𝑝 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
𝑞 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜙 𝜙
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐸 log + 𝐸 log
𝑧 𝜃 𝑧 𝑧
𝑝 𝑧 𝑝 (𝑧|𝑥)
𝜃
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧 + 𝐷 (𝑞 𝑧 𝑥 , 𝑝 𝑧 𝑥 )
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙 𝐾𝐿 𝜙 𝜃
𝜙
Stanford CS231n 10th Anniversary Lecture 13 - 97 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders (ELBO)
𝑝 𝑥 𝑧)𝑝(𝑧) 𝑝 𝑥 𝑧 𝑝 𝑧 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
log 𝑝 (𝑥) = log = log
𝜃
𝑝 𝑧 𝑥) 𝑝 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
𝑞 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜙 𝜙
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐸 log + 𝐸 log
𝑧 𝜃 𝑧 𝑧
𝑝 𝑧 𝑝 (𝑧|𝑥)
𝜃
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧 + 𝐷 (𝑞 𝑧 𝑥 , 𝑝 𝑧 𝑥 )
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙 𝐾𝐿 𝜙 𝜃
𝜙 |
| Stanford CS231n 10th Anniversary Lecture 13 - 97 May 15, 2025 |


---
## Page 98
---


Variational Autoencoders (ELBO)
𝑝 𝑥 𝑧)𝑝(𝑧) 𝑝 𝑥 𝑧 𝑝 𝑧 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
log 𝑝 (𝑥) = log = log
𝜃
𝑝 𝑧 𝑥) 𝑝 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
𝑞 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜙 𝜙
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐸 log + 𝐸 log
𝑧 𝜃 𝑧 𝑧
𝑝 𝑧 𝑝 (𝑧|𝑥)
𝜃
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧 + 𝐷 (𝑞 𝑧 𝑥 , 𝑝 𝑧 𝑥 )
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙 𝐾𝐿 𝜙 𝜃
𝜙
Data reconstruction: x => encoder => decoder should reconstruct x
Can compute in closed form for Gaussians.
Stanford CS231n 10th Anniversary Lecture 13 - 98 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders (ELBO)
𝑝 𝑥 𝑧)𝑝(𝑧) 𝑝 𝑥 𝑧 𝑝 𝑧 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
log 𝑝 (𝑥) = log = log
𝜃
𝑝 𝑧 𝑥) 𝑝 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
𝑞 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜙 𝜙
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐸 log + 𝐸 log
𝑧 𝜃 𝑧 𝑧
𝑝 𝑧 𝑝 (𝑧|𝑥)
𝜃
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧 + 𝐷 (𝑞 𝑧 𝑥 , 𝑝 𝑧 𝑥 )
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙 𝐾𝐿 𝜙 𝜃
𝜙
Data reconstruction: x => encoder => decoder should reconstruct x
Can compute in closed form for Gaussians. |
| Stanford CS231n 10th Anniversary Lecture 13 - 98 May 15, 2025 |


---
## Page 99
---


Variational Autoencoders (ELBO)
𝑝 𝑥 𝑧)𝑝(𝑧) 𝑝 𝑥 𝑧 𝑝 𝑧 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
log 𝑝 (𝑥) = log = log
𝜃
𝑝 𝑧 𝑥) 𝑝 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
𝑞 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜙 𝜙
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐸 log + 𝐸 log
𝑧 𝜃 𝑧 𝑧
𝑝 𝑧 𝑝 (𝑧|𝑥)
𝜃
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧 + 𝐷 (𝑞 𝑧 𝑥 , 𝑝 𝑧 𝑥 )
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙 𝐾𝐿 𝜙 𝜃
𝜙
Prior: Encoder output should match prior over z.
Can compute in closed for for Gaussians.
Stanford CS231n 10th Anniversary Lecture 13 - 99 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders (ELBO)
𝑝 𝑥 𝑧)𝑝(𝑧) 𝑝 𝑥 𝑧 𝑝 𝑧 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
log 𝑝 (𝑥) = log = log
𝜃
𝑝 𝑧 𝑥) 𝑝 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
𝑞 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜙 𝜙
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐸 log + 𝐸 log
𝑧 𝜃 𝑧 𝑧
𝑝 𝑧 𝑝 (𝑧|𝑥)
𝜃
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧 + 𝐷 (𝑞 𝑧 𝑥 , 𝑝 𝑧 𝑥 )
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙 𝐾𝐿 𝜙 𝜃
𝜙
Prior: Encoder output should match prior over z.
Can compute in closed for for Gaussians. |
| Stanford CS231n 10th Anniversary Lecture 13 - 99 May 15, 2025 |


---
## Page 100
---


Variational Autoencoders (ELBO)
𝑝 𝑥 𝑧)𝑝(𝑧) 𝑝 𝑥 𝑧 𝑝 𝑧 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
log 𝑝 (𝑥) = log = log
𝜃
𝑝 𝑧 𝑥) 𝑝 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
𝑞 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜙 𝜙
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐸 log + 𝐸 log
𝑧 𝜃 𝑧 𝑧
𝑝 𝑧 𝑝 (𝑧|𝑥)
𝜃
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧 + 𝐷 (𝑞 𝑧 𝑥 , 𝑝 𝑧 𝑥 )
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙 𝐾𝐿 𝜙 𝜃
𝜙
Posterior Approximation: Encoder output 𝑞 (𝑧|𝑥) should match 𝑝 𝑧 𝑥
𝜙 𝜃
We cannot compute this for Gaussians…
Stanford CS231n 10th Anniversary Lecture 13 - 100 May 15, 2025

[Page contains 2 table(s)]


### Table 1

| Variational Autoencoders (ELBO)
𝑝 𝑥 𝑧)𝑝(𝑧) 𝑝 𝑥 𝑧 𝑝 𝑧 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
log 𝑝 (𝑥) = log = log
𝜃
𝑝 𝑧 𝑥) 𝑝 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
𝑞 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜙 𝜙
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐸 log + 𝐸 log
𝑧 𝜃 𝑧 𝑧
𝑝 𝑧 𝑝 (𝑧|𝑥)
𝜃
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧 + 𝐷 (𝑞 𝑧 𝑥 , 𝑝 𝑧 𝑥 )
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙 𝐾𝐿 𝜙 𝜃
𝜙
Posterior Approximation: Encoder output 𝑞 (𝑧|𝑥) should match 𝑝 𝑧 𝑥
𝜙 𝜃
We cannot compute this for Gaussians… |
| Stanford CS231n 10th Anniversary Lecture 13 - 100 May 15, 2025 |


### Table 2

| = 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧 + 𝐷 (𝑞 𝑧 𝑥 , 𝑝 𝑧 𝑥 )
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙 𝐾𝐿 𝜙 𝜃
𝜙 |  |
|  |  |


---
## Page 101
---


Variational Autoencoders (ELBO)
𝑝 𝑥 𝑧)𝑝(𝑧) 𝑝 𝑥 𝑧 𝑝 𝑧 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
log 𝑝 (𝑥) = log = log
𝜃
𝑝 𝑧 𝑥) 𝑝 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
𝑞 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜙 𝜙
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐸 log + 𝐸 log
𝑧 𝜃 𝑧 𝑧
𝑝 𝑧 𝑝 (𝑧|𝑥)
𝜃
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧 + 𝐷 (𝑞 𝑧 𝑥 , 𝑝 𝑧 𝑥 )
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙 𝐾𝐿 𝜙 𝜃
𝜙
Posterior Approximation: Decoder output 𝑞 (𝑧|𝑥) should match 𝑝 𝑧 𝑥
𝜙 𝜃
KL is >= 0, so we can drop it to get a lower bound on likelihood
Stanford CS231n 10th Anniversary Lecture 13 - 101 May 15, 2025

[Page contains 2 table(s)]


### Table 1

| Variational Autoencoders (ELBO)
𝑝 𝑥 𝑧)𝑝(𝑧) 𝑝 𝑥 𝑧 𝑝 𝑧 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
log 𝑝 (𝑥) = log = log
𝜃
𝑝 𝑧 𝑥) 𝑝 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
𝑞 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜙 𝜙
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐸 log + 𝐸 log
𝑧 𝜃 𝑧 𝑧
𝑝 𝑧 𝑝 (𝑧|𝑥)
𝜃
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧 + 𝐷 (𝑞 𝑧 𝑥 , 𝑝 𝑧 𝑥 )
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙 𝐾𝐿 𝜙 𝜃
𝜙
Posterior Approximation: Decoder output 𝑞 (𝑧|𝑥) should match 𝑝 𝑧 𝑥
𝜙 𝜃
KL is >= 0, so we can drop it to get a lower bound on likelihood |
| Stanford CS231n 10th Anniversary Lecture 13 - 101 May 15, 2025 |


### Table 2

| = 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧 + 𝐷 (𝑞 𝑧 𝑥 , 𝑝 𝑧 𝑥 )
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙 𝐾𝐿 𝜙 𝜃
𝜙 |  |
|  |  |


---
## Page 102
---


Variational Autoencoders (ELBO)
𝑝 𝑥 𝑧)𝑝(𝑧) 𝑝 𝑥 𝑧 𝑝 𝑧 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
log 𝑝 (𝑥) = log = log
𝜃
𝑝 𝑧 𝑥) 𝑝 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
𝑞 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜙 𝜙
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐸 log + 𝐸 log
𝑧 𝜃 𝑧 𝑧
𝑝 𝑧 𝑝 (𝑧|𝑥)
𝜃
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧 + 𝐷 (𝑞 𝑧 𝑥 , 𝑝 𝑧 𝑥 )
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙 𝐾𝐿 𝜙 𝜃
𝜙
This is our VAE
log 𝑝 (𝑥) ≥ 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝜃 𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙 training objective
𝜙
Stanford CS231n 10th Anniversary Lecture 13 - 102 May 15, 2025

[Page contains 2 table(s)]


### Table 1

| Variational Autoencoders (ELBO)
𝑝 𝑥 𝑧)𝑝(𝑧) 𝑝 𝑥 𝑧 𝑝 𝑧 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
log 𝑝 (𝑥) = log = log
𝜃
𝑝 𝑧 𝑥) 𝑝 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜃 𝜃 𝜙
𝑞 𝑧 𝑥 𝑞 (𝑧|𝑥)
𝜙 𝜙
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐸 log + 𝐸 log
𝑧 𝜃 𝑧 𝑧
𝑝 𝑧 𝑝 (𝑧|𝑥)
𝜃
= 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧 + 𝐷 (𝑞 𝑧 𝑥 , 𝑝 𝑧 𝑥 )
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙 𝐾𝐿 𝜙 𝜃
𝜙
This is our VAE
log 𝑝 (𝑥) ≥ 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝜃 𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙 training objective
𝜙 |
| Stanford CS231n 10th Anniversary Lecture 13 - 102 May 15, 2025 |


### Table 2

| = 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧 + 𝐷 (𝑞 𝑧 𝑥 , 𝑝 𝑧 𝑥 )
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙 𝐾𝐿 𝜙 𝜃
𝜙 |  |  |
|  |  |  |
|  | log 𝑝 (𝑥) ≥ 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝜃 𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙 |  |


---
## Page 103
---


Variational Autoencoders
Jointly train encoder q and decoder p to maximize
the variational lower bound on the data likelihood
Also called Evidence Lower Bound (ELBo)
log 𝑝 (𝑥) ≥ 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝜃 𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙
Encoder Network Decoder Network
𝑞 𝑧 | 𝑥 = 𝑁(𝜇 , Σ ) 𝑝 𝑥 | 𝑧 = 𝑁(𝜇 , 𝜎2)
𝜙 𝑧|𝑥 𝑧|𝑥 𝜃 𝑥|𝑧
𝜇 Σ 𝜇
𝑧|𝑥 𝑧|𝑥 𝑥|𝑧
𝑥 𝑧
Stanford CS231n 10th Anniversary Lecture 13 - 103 May 15, 2025

[Page contains 4 table(s)]


### Table 1

| Variational Autoencoders
Jointly train encoder q and decoder p to maximize
the variational lower bound on the data likelihood
Also called Evidence Lower Bound (ELBo)
log 𝑝 (𝑥) ≥ 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝜃 𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙
Encoder Network Decoder Network
𝑞 𝑧 | 𝑥 = 𝑁(𝜇 , Σ ) 𝑝 𝑥 | 𝑧 = 𝑁(𝜇 , 𝜎2)
𝜙 𝑧|𝑥 𝑧|𝑥 𝜃 𝑥|𝑧
𝜇 Σ 𝜇
𝑧|𝑥 𝑧|𝑥 𝑥|𝑧
𝑥 𝑧 |
| Stanford CS231n 10th Anniversary Lecture 13 - 103 May 15, 2025 |


### Table 2

|  |
| 𝜇
𝑧|𝑥 |


### Table 3

|  |
| Σ
𝑧|𝑥 |


### Table 4

|  |
| 𝜇
𝑥|𝑧 |


---
## Page 104
---


Variational Autoencoders: Training
Train by maximizing the
variational lower bound
𝐸 [𝑙𝑜𝑔 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙
Stanford CS231n 10th Anniversary Lecture 13 - 104 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders: Training
Train by maximizing the
variational lower bound
𝐸 [𝑙𝑜𝑔 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙 |
| Stanford CS231n 10th Anniversary Lecture 13 - 104 May 15, 2025 |


---
## Page 105
---


Variational Autoencoders: Training
Train by maximizing the
variational lower bound
𝐸 [𝑙𝑜𝑔 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙
1. Run input data through encoder to get
distribution over z
𝑞 𝑧 | 𝑥 = 𝑁(𝜇 , Σ )
𝜙 𝑧|𝑥 𝑧|𝑥
𝜇 Σ
𝑧|𝑥 𝑧|𝑥
Encoder
𝑥
Stanford CS231n 10th Anniversary Lecture 13 - 105 May 15, 2025

[Page contains 3 table(s)]


### Table 1

| Variational Autoencoders: Training
Train by maximizing the
variational lower bound
𝐸 [𝑙𝑜𝑔 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙
1. Run input data through encoder to get
distribution over z
𝑞 𝑧 | 𝑥 = 𝑁(𝜇 , Σ )
𝜙 𝑧|𝑥 𝑧|𝑥
𝜇 Σ
𝑧|𝑥 𝑧|𝑥
Encoder
𝑥 |
| Stanford CS231n 10th Anniversary Lecture 13 - 105 May 15, 2025 |


### Table 2

|  |
| 𝜇
𝑧|𝑥 |


### Table 3

|  |
| Σ
𝑧|𝑥 |


---
## Page 106
---


Variational Autoencoders: Training
Train by maximizing the
variational lower bound
𝐸 [𝑙𝑜𝑔 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙
1. Run input data through encoder to get
distribution over z
2. Prior loss: Encoder output should be unit
Gaussian (zero mean, unit variance)
𝑞 𝑧 | 𝑥 = 𝑁(𝜇 , Σ )
𝜙 𝑧|𝑥 𝑧|𝑥
𝜇 Σ
𝑧|𝑥 𝑧|𝑥
Encoder
𝑥
Stanford CS231n 10th Anniversary Lecture 13 - 106 May 15, 2025

[Page contains 4 table(s)]


### Table 1

| Variational Autoencoders: Training
Train by maximizing the
variational lower bound
𝐸 [𝑙𝑜𝑔 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙
1. Run input data through encoder to get
distribution over z
2. Prior loss: Encoder output should be unit
Gaussian (zero mean, unit variance)
𝑞 𝑧 | 𝑥 = 𝑁(𝜇 , Σ )
𝜙 𝑧|𝑥 𝑧|𝑥
𝜇 Σ
𝑧|𝑥 𝑧|𝑥
Encoder
𝑥 |
| Stanford CS231n 10th Anniversary Lecture 13 - 106 May 15, 2025 |


### Table 2

| 𝐸 [𝑙𝑜𝑔 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙 |  |
|  | 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝐾𝐿 𝜙 |
|  |  |


### Table 3

|  |
| 𝜇
𝑧|𝑥 |


### Table 4

|  |
| Σ
𝑧|𝑥 |


---
## Page 107
---


Variational Autoencoders: Training
Train by maximizing the
variational lower bound
𝐸 [𝑙𝑜𝑔 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙
𝑧
1. Run input data through encoder to get
distribution over z 𝜖 ∼ 𝑁 0, 𝐼
2. Prior loss: Encoder output should be unit 𝑧 = 𝜖 ⊙ Σ + 𝜇
𝑧|𝑥 𝑧|𝑥
Gaussian (zero mean, unit variance)
𝑞 𝑧 | 𝑥 = 𝑁(𝜇 , Σ )
3. Sample z from encoder output 𝑞 𝑧 | 𝑥 𝜙 𝑧|𝑥 𝑧|𝑥
𝜙
(Reparameterization trick) 𝜇 Σ
𝑧|𝑥 𝑧|𝑥
Encoder
𝑥
Stanford CS231n 10th Anniversary Lecture 13 - 107 May 15, 2025

[Page contains 4 table(s)]


### Table 1

| Variational Autoencoders: Training
Train by maximizing the
variational lower bound
𝐸 [𝑙𝑜𝑔 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙
𝑧
1. Run input data through encoder to get
distribution over z 𝜖 ∼ 𝑁 0, 𝐼
2. Prior loss: Encoder output should be unit 𝑧 = 𝜖 ⊙ Σ + 𝜇
𝑧|𝑥 𝑧|𝑥
Gaussian (zero mean, unit variance)
𝑞 𝑧 | 𝑥 = 𝑁(𝜇 , Σ )
3. Sample z from encoder output 𝑞 𝑧 | 𝑥 𝜙 𝑧|𝑥 𝑧|𝑥
𝜙
(Reparameterization trick) 𝜇 Σ
𝑧|𝑥 𝑧|𝑥
Encoder
𝑥 |
| Stanford CS231n 10th Anniversary Lecture 13 - 107 May 15, 2025 |


### Table 2

| 𝐸 [𝑙𝑜𝑔 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙 |
| 1. Run input data through encoder to get
distribution over z
2. Prior loss: Encoder output should be unit
Gaussian (zero mean, unit variance)
3. Sample z from encoder output 𝑞 𝑧 | 𝑥
𝜙
(Reparameterization trick) |


### Table 3

|  |
| 𝜇
𝑧|𝑥 |


### Table 4

|  |
| Σ
𝑧|𝑥 |


---
## Page 108
---


Variational Autoencoders: Training
𝑝 𝑥 | 𝑧 = 𝑁(𝜇 , 𝜎2)
𝜃 𝑥|𝑧
Train by maximizing the 𝜇
𝑥|𝑧
variational lower bound
Decoder
𝐸 [𝑙𝑜𝑔 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙
𝑧
1. Run input data through encoder to get
distribution over z 𝜖 ∼ 𝑁 0, 𝐼
2. Prior loss: Encoder output should be unit 𝑧 = 𝜖 ⊙ Σ + 𝜇
𝑧|𝑥 𝑧|𝑥
Gaussian (zero mean, unit variance)
𝑞 𝑧 | 𝑥 = 𝑁(𝜇 , Σ )
3. Sample z from encoder output 𝑞 𝑧 | 𝑥 𝜙 𝑧|𝑥 𝑧|𝑥
𝜙
(Reparameterization trick) 𝜇 Σ
𝑧|𝑥 𝑧|𝑥
4. Run z through decoder to get predicted
Encoder
data mean
𝑥
Stanford CS231n 10th Anniversary Lecture 13 - 108 May 15, 2025

[Page contains 5 table(s)]


### Table 1

| Variational Autoencoders: Training
𝑝 𝑥 | 𝑧 = 𝑁(𝜇 , 𝜎2)
𝜃 𝑥|𝑧
Train by maximizing the 𝜇
𝑥|𝑧
variational lower bound
Decoder
𝐸 [𝑙𝑜𝑔 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙
𝑧
1. Run input data through encoder to get
distribution over z 𝜖 ∼ 𝑁 0, 𝐼
2. Prior loss: Encoder output should be unit 𝑧 = 𝜖 ⊙ Σ + 𝜇
𝑧|𝑥 𝑧|𝑥
Gaussian (zero mean, unit variance)
𝑞 𝑧 | 𝑥 = 𝑁(𝜇 , Σ )
3. Sample z from encoder output 𝑞 𝑧 | 𝑥 𝜙 𝑧|𝑥 𝑧|𝑥
𝜙
(Reparameterization trick) 𝜇 Σ
𝑧|𝑥 𝑧|𝑥
4. Run z through decoder to get predicted
Encoder
data mean
𝑥 |
| Stanford CS231n 10th Anniversary Lecture 13 - 108 May 15, 2025 |


### Table 2

|  |
| 𝜇
𝑥|𝑧 |


### Table 3

| 𝐸 [𝑙𝑜𝑔 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙 |
| 1. Run input data through encoder to get
distribution over z
2. Prior loss: Encoder output should be unit
Gaussian (zero mean, unit variance)
3. Sample z from encoder output 𝑞 𝑧 | 𝑥
𝜙
(Reparameterization trick)
4. Run z through decoder to get predicted
data mean |


### Table 4

|  |
| 𝜇
𝑧|𝑥 |


### Table 5

|  |
| Σ
𝑧|𝑥 |


---
## Page 109
---


Variational Autoencoders: Training
𝑝 𝑥 | 𝑧 = 𝑁(𝜇 , 𝜎2)
𝜃 𝑥|𝑧
Train by maximizing the 𝜇
𝑥|𝑧
variational lower bound
Decoder
𝐸 [𝑙𝑜𝑔 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙
𝑧
1. Run input data through encoder to get
distribution over z 𝜖 ∼ 𝑁 0, 𝐼
2. Prior loss: Encoder output should be unit 𝑧 = 𝜖 ⊙ Σ + 𝜇
𝑧|𝑥 𝑧|𝑥
Gaussian (zero mean, unit variance)
𝑞 𝑧 | 𝑥 = 𝑁(𝜇 , Σ )
3. Sample z from encoder output 𝑞 𝑧 | 𝑥 𝜙 𝑧|𝑥 𝑧|𝑥
𝜙
(Reparameterization trick) 𝜇 Σ
𝑧|𝑥 𝑧|𝑥
4. Run z through decoder to get predicted
Encoder
data mean
5. Reconstruction loss: predicted mean
𝑥
should match x in L2
Stanford CS231n 10th Anniversary Lecture 13 - 109 May 15, 2025

[Page contains 5 table(s)]


### Table 1

| Variational Autoencoders: Training
𝑝 𝑥 | 𝑧 = 𝑁(𝜇 , 𝜎2)
𝜃 𝑥|𝑧
Train by maximizing the 𝜇
𝑥|𝑧
variational lower bound
Decoder
𝐸 [𝑙𝑜𝑔 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙
𝑧
1. Run input data through encoder to get
distribution over z 𝜖 ∼ 𝑁 0, 𝐼
2. Prior loss: Encoder output should be unit 𝑧 = 𝜖 ⊙ Σ + 𝜇
𝑧|𝑥 𝑧|𝑥
Gaussian (zero mean, unit variance)
𝑞 𝑧 | 𝑥 = 𝑁(𝜇 , Σ )
3. Sample z from encoder output 𝑞 𝑧 | 𝑥 𝜙 𝑧|𝑥 𝑧|𝑥
𝜙
(Reparameterization trick) 𝜇 Σ
𝑧|𝑥 𝑧|𝑥
4. Run z through decoder to get predicted
Encoder
data mean
5. Reconstruction loss: predicted mean
𝑥
should match x in L2 |
| Stanford CS231n 10th Anniversary Lecture 13 - 109 May 15, 2025 |


### Table 2

|  |
| 𝜇
𝑥|𝑧 |


### Table 3

|  | 𝐸 [𝑙𝑜𝑔 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙 |
|  | 𝐸 [𝑙𝑜𝑔 𝑝 (𝑥|𝑧)]
𝑧~𝑞 (𝑧|𝑥) 𝜃
𝜙 |
|  | 1. Run input data through encoder to get
distribution over z
2. Prior loss: Encoder output should be unit
Gaussian (zero mean, unit variance)
3. Sample z from encoder output 𝑞 𝑧 | 𝑥
𝜙
(Reparameterization trick)
4. Run z through decoder to get predicted
data mean
5. Reconstruction loss: predicted mean
should match x in L2 |
|  |  |


### Table 4

|  |
| 𝜇
𝑧|𝑥 |


### Table 5

|  |
| Σ
𝑧|𝑥 |


---
## Page 110
---


Variational Autoencoders: Training
𝑝 𝑥 | 𝑧 = 𝑁(𝜇 , 𝜎2)
𝜃 𝑥|𝑧
Train by maximizing the 𝜇
𝑥|𝑧
variational lower bound
Decoder
𝐸 [𝑙𝑜𝑔 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙
𝑧
The loss terms fight against each other!
𝜖 ∼ 𝑁 0, 𝐼
Reconstruction loss wants Σ = 0 and 𝑧 = 𝜖 ⊙ Σ + 𝜇
𝑧|𝑥 𝑧|𝑥 𝑧|𝑥
𝜇 to be unique for each x, so decoder can
𝑧|𝑥
𝑞 𝑧 | 𝑥 = 𝑁(𝜇 , Σ )
deterministically reconstruct x 𝜙 𝑧|𝑥 𝑧|𝑥
𝜇 Σ
𝑧|𝑥 𝑧|𝑥
Prior loss wants Σ = 𝐈 and 𝜇 = 0 so
𝑧|𝑥 𝑧|𝑥
Encoder
encoder output is always a unit Gaussian
𝑥
Stanford CS231n 10th Anniversary Lecture 13 - 110 May 15, 2025

[Page contains 5 table(s)]


### Table 1

| Variational Autoencoders: Training
𝑝 𝑥 | 𝑧 = 𝑁(𝜇 , 𝜎2)
𝜃 𝑥|𝑧
Train by maximizing the 𝜇
𝑥|𝑧
variational lower bound
Decoder
𝐸 [𝑙𝑜𝑔 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙
𝑧
The loss terms fight against each other!
𝜖 ∼ 𝑁 0, 𝐼
Reconstruction loss wants Σ = 0 and 𝑧 = 𝜖 ⊙ Σ + 𝜇
𝑧|𝑥 𝑧|𝑥 𝑧|𝑥
𝜇 to be unique for each x, so decoder can
𝑧|𝑥
𝑞 𝑧 | 𝑥 = 𝑁(𝜇 , Σ )
deterministically reconstruct x 𝜙 𝑧|𝑥 𝑧|𝑥
𝜇 Σ
𝑧|𝑥 𝑧|𝑥
Prior loss wants Σ = 𝐈 and 𝜇 = 0 so
𝑧|𝑥 𝑧|𝑥
Encoder
encoder output is always a unit Gaussian
𝑥 |
| Stanford CS231n 10th Anniversary Lecture 13 - 110 May 15, 2025 |


### Table 2

|  |
| 𝜇
𝑥|𝑧 |


### Table 3

| 𝐸 [𝑙𝑜𝑔 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙 |
| The loss terms fight against each other!
Reconstruction loss wants Σ = 0 and
𝑧|𝑥
𝜇 to be unique for each x, so decoder can
𝑧|𝑥
deterministically reconstruct x
Prior loss wants Σ = 𝐈 and 𝜇 = 0 so
𝑧|𝑥 𝑧|𝑥
encoder output is always a unit Gaussian |


### Table 4

|  |
| 𝜇
𝑧|𝑥 |


### Table 5

|  |
| Σ
𝑧|𝑥 |


---
## Page 111
---


Variational Autoencoders: Sampling
1. Sample z from the prior
𝑝 𝑥 | 𝑧 = 𝑁(𝜇 , 𝜎2)
𝜃 𝑥|𝑧
2. Run through decoder to get an image
𝜇
𝑥|𝑧
Decoder
𝑧
𝑧 ∼ 𝑁 0, 𝐼
Stanford CS231n 10th Anniversary Lecture 13 - 111 May 15, 2025

[Page contains 2 table(s)]


### Table 1

| Variational Autoencoders: Sampling
1. Sample z from the prior
𝑝 𝑥 | 𝑧 = 𝑁(𝜇 , 𝜎2)
𝜃 𝑥|𝑧
2. Run through decoder to get an image
𝜇
𝑥|𝑧
Decoder
𝑧
𝑧 ∼ 𝑁 0, 𝐼 |
| Stanford CS231n 10th Anniversary Lecture 13 - 111 May 15, 2025 |


### Table 2

|  |
| 𝜇
𝑥|𝑧 |


---
## Page 112
---


Variational Autoencoders: Disentangling
The diagonal prior on p(z) causes
dimensions of z to be independent
Vary z
1
“Disentangling factors of variation”
Vary z
Kingma and Welling, Auto-Encoding Variational Beyes, ICLR 2014 2
Stanford CS231n 10th Anniversary Lecture 13 - 112 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Variational Autoencoders: Disentangling
The diagonal prior on p(z) causes
dimensions of z to be independent
Vary z
1
“Disentangling factors of variation”
Vary z
Kingma and Welling, Auto-Encoding Variational Beyes, ICLR 2014 2 |
| Stanford CS231n 10th Anniversary Lecture 13 - 112 May 15, 2025 |


[Page contains 1 image(s)]


---
## Page 113
---


Recap: Supervised vs Unsupervised Learning
Supervised Learning Unsupervised Learning
Data: (x, y) Data: x
x is data, y is label Just data, no labels!
Goal: Learn a function to map x -> y Goal: Learn hidden structure in data
Examples: Classification, regression, Examples: Clustering, dimensionality
object detection, semantic reduction, density estimation, etc.
segmentation, image captioning, etc.
Stanford CS231n 10th Anniversary Lecture 13 - 113 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Recap: Supervised vs Unsupervised Learning
Supervised Learning Unsupervised Learning
Data: (x, y) Data: x
x is data, y is label Just data, no labels!
Goal: Learn a function to map x -> y Goal: Learn hidden structure in data
Examples: Classification, regression, Examples: Clustering, dimensionality
object detection, semantic reduction, density estimation, etc.
segmentation, image captioning, etc. |
| Stanford CS231n 10th Anniversary Lecture 13 - 113 May 15, 2025 |


---
## Page 114
---


Recap: Generative vs Discriminative Models
Density Function
Discriminative Model:
Data: x
p(x) assigns a positive
Learn a probability
number to each possible
distribution p(y|x)
x; higher numbers mean
x is more likely.
Generative Model: Density functions are
Learn a probability normalized:
distribution p(x)
න 𝑝 𝑥 𝑑𝑥 = 1
𝑋
Label: y
Conditional Generative
Cat Different values of x
Model: Learn p(x|y)
compete for density
Stanford CS231n 10th Anniversary Lecture 13 - 114 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Recap: Generative vs Discriminative Models
Density Function
Discriminative Model:
Data: x
p(x) assigns a positive
Learn a probability
number to each possible
distribution p(y|x)
x; higher numbers mean
x is more likely.
Generative Model: Density functions are
Learn a probability normalized:
distribution p(x)
න 𝑝 𝑥 𝑑𝑥 = 1
𝑋
Label: y
Conditional Generative
Cat Different values of x
Model: Learn p(x|y)
compete for density |  |  |
|  | x; higher numbers m
x is more likely.
Density functions are
normalized:
න 𝑝 𝑥 𝑑𝑥 = 1
𝑋
Different values of x
compete for density |  |
| Stanford CS231n 10th Anniversary Lect | ure 13 - 114 May 15, 20 | 25 |
|  |  |  |


[Page contains 1 image(s)]


---
## Page 115
---


Figure adapted from Ian
Goodfellow, Tutorial on
Recap: Generative Models Generative Adversarial
Networks, 2017
Model can Generative models Cannot compute p(x) but
compute P(x) can sample from P(x)
Iterative
Explicit density Implicit density
procedure to
Really Can directly approximate
Approximate
compute sample samples
P(x)
P(x) from P(x) from P(x)
Tractable density Approximate density Direct Indirect
Variational Autoencoder Generative Adversarial
Autoregressive Diffusion Models
(VAE) Network (GAN)
Today Next Time
Stanford CS231n 10th Anniversary Lecture 13 - 115 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Figure adapted from Ian
Goodfellow, Tutorial on
Recap: Generative Models Generative Adversarial
Networks, 2017
Model can Generative models Cannot compute p(x) but
compute P(x) can sample from P(x)
Iterative
Explicit density Implicit density
procedure to
Really Can directly approximate
Approximate
compute sample samples
P(x)
P(x) from P(x) from P(x)
Tractable density Approximate density Direct Indirect
Variational Autoencoder Generative Adversarial
Autoregressive Diffusion Models
(VAE) Network (GAN)
Today Next Time |
| Stanford CS231n 10th Anniversary Lecture 13 - 115 May 15, 2025 |


---
## Page 116
---


Next Time:
Generative Models (part 2)
Generative Adversarial Networks
Diffusion Models
Stanford CS231n 10th Anniversary Lecture 13 - 116 May 15, 2025

[Page contains 1 table(s)]


### Table 1

| Next Time:
Generative Models (part 2)
Generative Adversarial Networks
Diffusion Models |
| Stanford CS231n 10th Anniversary Lecture 13 - 116 May 15, 2025 |
