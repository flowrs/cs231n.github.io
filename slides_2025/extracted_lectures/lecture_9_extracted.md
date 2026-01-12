# lecture_9

Extracted using pdfplumber



---
## Page 1
---


Lecture 9:
Detection, Segmentation,
Visualization, and Understanding
Stanford CS231n 10th Anniversary Lecture 9 - 1 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture 9:
Detection, Segmentation,
Visualization, and Understanding |
| Stanford CS231n 10th Anniversary Lecture 9 - 1 April 29, 2025 |


---
## Page 2
---


Administrative Announcements
• Make sure to start Assignment 2 early. It is the longest of the three assignments,
and the midterm and project milestone deadlines follow closely after the
Assignment 2 deadline.
• Be sure to check out this Ed post for the best Colab practices to avoid
unnecessary bugs and delays.
Stanford CS231n 10th Anniversary Lecture 9 - 2 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Administrative Announcements
• Make sure to start Assignment 2 early. It is the longest of the three assignments,
and the midterm and project milestone deadlines follow closely after the
Assignment 2 deadline.
• Be sure to check out this Ed post for the best Colab practices to avoid
unnecessary bugs and delays. |
| Stanford CS231n 10th Anniversary Lecture 9 - 2 April 29, 2025 |


---
## Page 3
---


Last time: Transformer
Encoder Decoder
Stanford CS231n 10th Anniversary Lecture 9 - 3 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Last time: Transformer
Encoder Decoder |
| Stanford CS231n 10th Anniversary Lecture 9 - 3 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 4
---


Three Ways of Processing Sequences
Recurrent Neural Network Convolution Self-Attention
Y1 Y2 Y3
Product(→),(cid:9)(cid:9)(cid:9)Sum(↑)
y y y y
1 2 3 4
y y y y V3 A1,3 A2,3 A3,3
1 2 3 4 V2 A1,2 A2,2 A3,2
V1 A1,1 A2,1 A3,1
Softmax(↑)
K3 E1,3 E2,3 E3,3
K2 E1,2 E2,2 E3,2
K1 E1,1 E2,1 E3,1
x x x x x x x x Q1 Q2 Q3
1 2 3 4
1 2 3 4 X1 X2 X3
Works on 1D ordered sequences Works on N-dimensional grids Works on sets of vectors
(+) Theoretically good at long (-) Bad for long sequences: need to (+) Great for long sequences; each
sequences: O(N) compute and stack many layers to build up large output depends directly on all inputs
memory for a sequence of length N receptive fields (+) Highly parallel, it’s just 4 matmuls
(-) Not parallelizable. Need to (+) Parallelizable, outputs can be (-) Expensive: O(N2) compute, O(N)
compute hidden states sequentially computed in parallel memory for sequence of length N
Stanford CS231n 10th Anniversary Lecture 9 - 4 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Three Ways of Processing Sequences
Recurrent Neural Network Convolution Self-Attention
Y1 Y2 Y3
Product(→),(cid:9)(cid:9)(cid:9)Sum(↑)
y y y y
y y y y V3 A1,3 A2,3 A3,3
1 2 3 4
1 2 3 4 V2 A1,2 A2,2 A3,2
V1 A1,1 A2,1 A3,1
Softmax(↑)
K3 E1,3 E2,3 E3,3
K2 E1,2 E2,2 E3,2
K1 E1,1 E2,1 E3,1
x x x x x x x x Q1 Q2 Q3
1 2 3 4
1 2 3 4 X1 X2 X3
Works on 1D ordered sequences Works on N-dimensional grids Works on sets of vectors
(+) Theoretically good at long (-) Bad for long sequences: need to (+) Great for long sequences; each
sequences: O(N) compute and stack many layers to build up large output depends directly on all inputs
memory for a sequence of length N receptive fields (+) Highly parallel, it’s just 4 matmuls
(-) Not parallelizable. Need to (+) Parallelizable, outputs can be (-) Expensive: O(N2) compute, O(N)
compute hidden states sequentially computed in parallel memory for sequence of length N |
| Stanford CS231n 10th Anniversary Lecture 9 - 4 April 29, 2025 |


---
## Page 5
---


Vision Transformers (ViT)
Input image:
e.g. 224x224x3
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image
Recognition at Scale”, ICLR 2021
Stanford CS231n 10th Anniversary Lecture 9 - 5 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Vision Transformers (ViT)
Input image:
e.g. 224x224x3
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image
Recognition at Scale”, ICLR 2021 |
| Stanford CS231n 10th Anniversary Lecture 9 - 5 April 29, 2025 |


[Page contains 9 image(s)]


---
## Page 6
---


Vision Transformers (ViT)
Cat imageis free for commercial
Dosovitskiyet al, “An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale”, ICLR 2021
use under a Pixabaylicense
Stanford CS231n 10th Anniversary Lecture 9 - 6 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Vision Transformers (ViT)
Cat imageis free for commercial
Dosovitskiyet al, “An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale”, ICLR 2021
use under a Pixabaylicense |
| Stanford CS231n 10th Anniversary Lecture 9 - 6 April 29, 2025 |


[Page contains 9 image(s)]


---
## Page 7
---


Vision Transformers (ViT)
N input patches, each of
shape 3x16x16
Cat imageis free for commercial
Dosovitskiyet al, “An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale”, ICLR 2021
use under a Pixabaylicense
Stanford CS231n 10th Anniversary Lecture 9 - 7 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Vision Transformers (ViT)
N input patches, each of
shape 3x16x16
Cat imageis free for commercial
Dosovitskiyet al, “An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale”, ICLR 2021
use under a Pixabaylicense |
| Stanford CS231n 10th Anniversary Lecture 9 - 7 April 29, 2025 |


[Page contains 9 image(s)]


---
## Page 8
---


Vision Transformers (ViT)
Linear projection to D-
dimensional vector
N input patches, each of
shape 3x16x16
Cat imageis free for commercial
Dosovitskiyet al, “An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale”, ICLR 2021
use under a Pixabaylicense
Stanford CS231n 10th Anniversary Lecture 9 - 8 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Vision Transformers (ViT)
Linear projection to D-
dimensional vector
N input patches, each of
shape 3x16x16
Cat imageis free for commercial
Dosovitskiyet al, “An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale”, ICLR 2021
use under a Pixabaylicense |
| Stanford CS231n 10th Anniversary Lecture 9 - 8 April 29, 2025 |


[Page contains 9 image(s)]


---
## Page 9
---


Vision Transformers (ViT)
Add positional embedding:
learned D-dim vector per
position
+ + + + + + + + +
Linear projection to D-
dimensional vector
N input patches, each of
shape 3x16x16
Cat imageis free for commercial
Dosovitskiyet al, “An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale”, ICLR 2021
use under a Pixabaylicense
Stanford CS231n 10th Anniversary Lecture 9 - 9 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Vision Transformers (ViT)
Add positional embedding:
learned D-dim vector per
position
+ + + + + + + + +
Linear projection to D-
dimensional vector
N input patches, each of
shape 3x16x16
Cat imageis free for commercial
Dosovitskiyet al, “An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale”, ICLR 2021
use under a Pixabaylicense |
| Stanford CS231n 10th Anniversary Lecture 9 - 9 April 29, 2025 |


[Page contains 9 image(s)]


---
## Page 10
---


Vision Transformers (ViT)
Output vectors
Exact same as NLP
Transformer
Transformer!
Add positional embedding:
learned D-dim vector per
position
+ + + + + + + + +
Linear projection to D-
dimensional vector
N input patches, each of
shape 3x16x16
Cat imageis free for commercial
Dosovitskiyet al, “An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale”, ICLR 2021
use under a Pixabaylicense
Stanford CS231n 10th Anniversary Lecture 9 - 10 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Vision Transformers (ViT)
Output vectors
Exact same as NLP
Transformer
Transformer!
Add positional embedding:
learned D-dim vector per
position
+ + + + + + + + +
Linear projection to D-
dimensional vector
N input patches, each of
shape 3x16x16
Cat imageis free for commercial
Dosovitskiyet al, “An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale”, ICLR 2021
use under a Pixabaylicense |
| Stanford CS231n 10th Anniversary Lecture 9 - 10 April 29, 2025 |


[Page contains 9 image(s)]


---
## Page 11
---


Vision Transformers (ViT)
Output vectors
Exact same as NLP
Transformer
Transformer!
Special extra input:
Add positional embedding:
classification token
learned D-dim vector per
(D dims, learned)
position
+ + + + + + + + +
Linear projection to D-
dimensional vector
N input patches, each of
shape 3x16x16
Cat imageis free for commercial
Dosovitskiyet al, “An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale”, ICLR 2021
use under a Pixabaylicense
Stanford CS231n 10th Anniversary Lecture 9 - 11 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Vision Transformers (ViT)
Output vectors
Exact same as NLP
Transformer
Transformer!
Special extra input:
Add positional embedding:
classification token
learned D-dim vector per
(D dims, learned)
position
+ + + + + + + + +
Linear projection to D-
dimensional vector
N input patches, each of
shape 3x16x16
Cat imageis free for commercial
Dosovitskiyet al, “An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale”, ICLR 2021
use under a Pixabaylicense |
| Stanford CS231n 10th Anniversary Lecture 9 - 11 April 29, 2025 |


[Page contains 9 image(s)]


---
## Page 12
---


Vision Transformers (ViT)
Linear projection to
C-dim vector of
predicted class
scores
Output vectors
Exact same as NLP
Transformer
Transformer!
Special extra input:
Add positional embedding:
classification token
learned D-dim vector per
(D dims, learned)
position
+ + + + + + + + +
Linear projection to D-
dimensional vector
N input patches, each of
shape 3x16x16
Cat imageis free for commercial
Dosovitskiyet al, “An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale”, ICLR 2021
use under a Pixabaylicense
Stanford CS231n 10th Anniversary Lecture 9 - 12 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Vision Transformers (ViT)
Linear projection to
C-dim vector of
predicted class
scores
Output vectors
Exact same as NLP
Transformer
Transformer!
Special extra input:
Add positional embedding:
classification token
learned D-dim vector per
(D dims, learned)
position
+ + + + + + + + +
Linear projection to D-
dimensional vector
N input patches, each of
shape 3x16x16
Cat imageis free for commercial
Dosovitskiyet al, “An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale”, ICLR 2021
use under a Pixabaylicense |
| Stanford CS231n 10th Anniversary Lecture 9 - 12 April 29, 2025 |


[Page contains 9 image(s)]


---
## Page 13
---


Vision Transformers (ViT)
– a similar approach (different classifier)
Input image:
e.g. 224x224x3
Break into patches
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3
Recognition at Scale”, ICLR 2021
Stanford CS231n 10th Anniversary Lecture 9 - 13 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| Vision Transformers (ViT)
– a similar approach (different classifier)
Input image:
e.g. 224x224x3
Break into patches
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3
Recognition at Scale”, ICLR 2021 |
| Stanford CS231n 10th Anniversary Lecture 9 - 13 April 29, 2025 |


### Table 2

|  |  |  |
|  |  |  |
|  |  |  |


[Page contains 18 image(s)]


---
## Page 14
---


Vision Transformers (ViT)
Input image:
e.g. 224x224x3
Break into patches Flatten and apply a linear
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D
Recognition at Scale”, ICLR 2021
Stanford CS231n 10th Anniversary Lecture 9 - 14 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Vision Transformers (ViT)
Input image:
e.g. 224x224x3
Break into patches Flatten and apply a linear
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D
Recognition at Scale”, ICLR 2021 |
| Stanford CS231n 10th Anniversary Lecture 9 - 14 April 29, 2025 |


[Page contains 18 image(s)]


---
## Page 15
---


Vision Transformers (ViT)
Input image:
e.g. 224x224x3
D-dim vector per patch are
Break into patches Flatten and apply a linear the input vectors to the
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D Transformer
Recognition at Scale”, ICLR 2021
Stanford CS231n 10th Anniversary Lecture 9 - 15 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Vision Transformers (ViT)
Input image:
e.g. 224x224x3
D-dim vector per patch are
Break into patches Flatten and apply a linear the input vectors to the
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D Transformer
Recognition at Scale”, ICLR 2021 |
| Stanford CS231n 10th Anniversary Lecture 9 - 15 April 29, 2025 |


[Page contains 20 image(s)]


---
## Page 16
---


Vision Transformers (ViT)
Use positional
encoding to tell
the transformer
the 2D position
of each patch
Input image:
e.g. 224x224x3
D-dim vector per patch are
Break into patches Flatten and apply a linear the input vectors to the
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D Transformer
Recognition at Scale”, ICLR 2021
Stanford CS231n 10th Anniversary Lecture 9 - 16 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Vision Transformers (ViT)
Use positional
encoding to tell
the transformer
the 2D position
of each patch
Input image:
e.g. 224x224x3
D-dim vector per patch are
Break into patches Flatten and apply a linear the input vectors to the
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D Transformer
Recognition at Scale”, ICLR 2021 |
| Stanford CS231n 10th Anniversary Lecture 9 - 16 April 29, 2025 |


[Page contains 20 image(s)]


---
## Page 17
---


Vision Transformers (ViT)
Don’t use any
masking; each
image patch can
look at all other
image patches
Use positional
encoding to tell
the transformer
the 2D position
of each patch
Input image:
e.g. 224x224x3
D-dim vector per patch are
Break into patches Flatten and apply a linear the input vectors to the
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D Transformer
Recognition at Scale”, ICLR 2021
Stanford CS231n 10th Anniversary Lecture 9 - 17 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Vision Transformers (ViT)
Don’t use any
masking; each
image patch can
look at all other
image patches
Use positional
encoding to tell
the transformer
the 2D position
of each patch
Input image:
e.g. 224x224x3
D-dim vector per patch are
Break into patches Flatten and apply a linear the input vectors to the
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D Transformer
Recognition at Scale”, ICLR 2021 |
| Stanford CS231n 10th Anniversary Lecture 9 - 17 April 29, 2025 |


[Page contains 20 image(s)]


---
## Page 18
---


Vision Transformers (ViT)
Transformer
gives an output
vector per patch
Don’t use any
masking; each
image patch can
look at all other
image patches
Use positional
encoding to tell
the transformer
the 2D position
of each patch
Input image:
e.g. 224x224x3
D-dim vector per patch are
Break into patches Flatten and apply a linear the input vectors to the
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D Transformer
Recognition at Scale”, ICLR 2021
Stanford CS231n 10th Anniversary Lecture 9 - 18 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Vision Transformers (ViT)
Transformer
gives an output
vector per patch
Don’t use any
masking; each
image patch can
look at all other
image patches
Use positional
encoding to tell
the transformer
the 2D position
of each patch
Input image:
e.g. 224x224x3
D-dim vector per patch are
Break into patches Flatten and apply a linear the input vectors to the
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D Transformer
Recognition at Scale”, ICLR 2021 |
| Stanford CS231n 10th Anniversary Lecture 9 - 18 April 29, 2025 |


[Page contains 20 image(s)]


---
## Page 19
---


Average pool NxDvectors to
Vision Transformers (ViT) 1xD, apply a linear layer D=>C to
Transformer
predict class scores
gives an output
vector per patch
Pooling
Don’t use any
masking; each
image patch can
look at all other
image patches
Use positional
encoding to tell
the transformer
the 2D position
of each patch
Input image:
e.g. 224x224x3
D-dim vector per patch are
Break into patches Flatten and apply a linear the input vectors to the
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D Transformer
Recognition at Scale”, ICLR 2021
Stanford CS231n 10th Anniversary Lecture 9 - 19 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Average pool NxDvectors to
Vision Transformers (ViT) 1xD, apply a linear layer D=>C to
Transformer
predict class scores
gives an output
vector per patch
Pooling
Don’t use any
masking; each
image patch can
look at all other
image patches
Use positional
encoding to tell
the transformer
the 2D position
of each patch
Input image:
e.g. 224x224x3
D-dim vector per patch are
Break into patches Flatten and apply a linear the input vectors to the
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D Transformer
Recognition at Scale”, ICLR 2021 |
| Stanford CS231n 10th Anniversary Lecture 9 - 19 April 29, 2025 |


[Page contains 20 image(s)]


---
## Page 20
---


Tweaking Transformers
y y y y
1 2 3 4
The Transformer architecture has not changed
Layer Normalization
much since 2017.
+
But a few changes have become common:
MLP MLP MLP MLP
Layer Normalization
+
Self-Attention
x x x x
1 2 3 4
Stanford CS231n 10th Anniversary Lecture 9 - 20 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| Tweaking Transformers
y y y y
1 2 3 4
The Transformer architecture has not changed
Layer Normalization
much since 2017.
+
But a few changes have become common:
MLP MLP MLP MLP
Layer Normalization
+
Self-Attention
x x x x
1 2 3 4 |
| Stanford CS231n 10th Anniversary Lecture 9 - 20 April 29, 2025 |


### Table 2

|  |  |  |


---
## Page 21
---


Pre-Norm Transformer
y y y y
1 2 3 4
Layer Normalization
+
Layer normalization is outside the
residual connections
MLP MLP MLP MLP
Kind of weird, the model can’t
actually learn the identify function
Layer Normalization
+
Self-Attention
x x x x
1 2 3 4
Baevski& Auli, “Adaptive Input Representations for Neural Language Modeling”, arXiv2018
Stanford CS231n 10th Anniversary Lecture 9 - 21 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| Pre-Norm Transformer
y y y y
1 2 3 4
Layer Normalization
+
Layer normalization is outside the
residual connections
MLP MLP MLP MLP
Kind of weird, the model can’t
actually learn the identify function
Layer Normalization
+
Self-Attention
x x x x
1 2 3 4
Baevski& Auli, “Adaptive Input Representations for Neural Language Modeling”, arXiv2018 |
| Stanford CS231n 10th Anniversary Lecture 9 - 21 April 29, 2025 |


### Table 2

|  |  |  |


---
## Page 22
---


Pre-Norm Transformer
y y y y
1 2 3 4
+
Layer normalization is outside the
residual connections MLP MLP MLP MLP
Kind of weird, the model can’t
Layer Normalization
actually learn the identify function
+
Solution: Move layer normalization
before the Self-Attention and MLP,
Self-Attention
inside the residual connections.
Training is more stable. Layer Normalization
x x x x
1 2 3 4
Baevski& Auli, “Adaptive Input Representations for Neural Language Modeling”, arXiv2018
Stanford CS231n 10th Anniversary Lecture 9 - 22 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Pre-Norm Transformer
y y y y
1 2 3 4
+
Layer normalization is outside the
residual connections MLP MLP MLP MLP
Kind of weird, the model can’t
Layer Normalization
actually learn the identify function
+
Solution: Move layer normalization
before the Self-Attention and MLP,
Self-Attention
inside the residual connections.
Training is more stable. Layer Normalization
x x x x
1 2 3 4
Baevski& Auli, “Adaptive Input Representations for Neural Language Modeling”, arXiv2018 |
| Stanford CS231n 10th Anniversary Lecture 9 - 22 April 29, 2025 |


### Table 2

|  |  |  |


### Table 3

|  |
|  |


---
## Page 23
---


RMSNorm
y y y y
1 2 3 4
Replace Layer Normalization
with Root-Mean-Square +
Normalization (RMSNorm)
MLP MLP MLP MLP
Input: x [shape D]
Output: y [shape D]
Weight: 𝛾 [shape D] RMSNorm
𝑥 +
𝑖
𝑦 = ∗ 𝛾
𝑖 𝑖
𝑅𝑀𝑆(𝑥)
Self-Attention
1 𝑁
𝑅𝑀𝑆 𝑥 = 𝜀 + ෍ 𝑥2 RMSNorm
𝑁 𝑖
𝑖=1
Training is a bit more stable
x x x x
1 2 3 4
Zhang and Sennrich, “Root Mean Square Layer Normalization”, NeurIPS2019
Stanford CS231n 10th Anniversary Lecture 9 - 23 April 29, 2025

[Page contains 4 table(s)]


### Table 1

| RMSNorm
y y y y
1 2 3 4
Replace Layer Normalization
with Root-Mean-Square +
Normalization (RMSNorm)
MLP MLP MLP MLP
Input: x [shape D]
Output: y [shape D]
Weight: 𝛾 [shape D] RMSNorm
𝑥 +
𝑖
𝑦 = ∗ 𝛾
𝑖 𝑖
𝑅𝑀𝑆(𝑥)
Self-Attention
1 𝑁
𝑅𝑀𝑆 𝑥 = 𝜀 + ෍ 𝑥2 RMSNorm
𝑁 𝑖
𝑖=1
Training is a bit more stable
x x x x
1 2 3 4
Zhang and Sennrich, “Root Mean Square Layer Normalization”, NeurIPS2019 |
| Stanford CS231n 10th Anniversary Lecture 9 - 23 April 29, 2025 |


### Table 2

| Replace Layer Normalization
with Root-Mean-Square
Normalization (RMSNorm)
Input: x [shape D]
Output: y [shape D]
Weight: 𝛾 [shape D]
𝑥
𝑖
𝑦 = ∗ 𝛾
𝑖 𝑖
𝑅𝑀𝑆(𝑥)
1 𝑁
𝑅𝑀𝑆 𝑥 = 𝜀 + ෍ 𝑥2
𝑁 𝑖
𝑖=1
Training is a bit more stable
g and Sennrich, “Root Mean Square Layer Normalization”, |
|  |


### Table 3

|  |  |  |


### Table 4

|  |
|  |


---
## Page 24
---


SwiGLU MLP
y y y y
1 2 3 4
Classic MLP:
+
Input: X [N x D]
Weights: W [D x 4D]
1 MLP MLP MLP MLP
W [4D x D]
2
Output: Y = σ(XW )W [N x D]
1 2
RMSNorm
+
Self-Attention
RMSNorm
x x x x
1 2 3 4
Shazeer, “GLU Variants Improve Transformers”, 2020
Stanford CS231n 10th Anniversary Lecture 9 - 24 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| SwiGLU MLP
y y y y
1 2 3 4
Classic MLP:
+
Input: X [N x D]
Weights: W [D x 4D]
1 MLP MLP MLP MLP
W [4D x D]
2
Output: Y = σ(XW )W [N x D]
1 2
RMSNorm
+
Self-Attention
RMSNorm
x x x x
1 2 3 4
Shazeer, “GLU Variants Improve Transformers”, 2020 |
| Stanford CS231n 10th Anniversary Lecture 9 - 24 April 29, 2025 |


### Table 2

|  |  |  |


### Table 3

|  |
|  |


---
## Page 25
---


SwiGLU MLP
y y y y
1 2 3 4
Classic MLP:
+
Input: X [N x D]
Weights: W [D x 4D]
1 MLP MLP MLP MLP
W [4D x D]
2
Output: Y = σ(XW )W [N x D]
1 2
RMSNorm
SwiGLU MLP:
+
Input: X [N x D]
Self-Attention
Weights: W , W [D x H]
1 2
W [H x D]
RMSNorm
3
Output:
𝑌 = 𝜎 𝑋𝑊 ⊙𝑋𝑊 𝑊
1 2 3
Setting H = 8D/3 keeps
x x x x
same total params
1 2 3 4
Shazeer, “GLU Variants Improve Transformers”, 2020
Stanford CS231n 10th Anniversary Lecture 9 - 25 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| SwiGLU MLP
y y y y
1 2 3 4
Classic MLP:
+
Input: X [N x D]
Weights: W [D x 4D]
1 MLP MLP MLP MLP
W [4D x D]
2
Output: Y = σ(XW )W [N x D]
1 2
RMSNorm
SwiGLU MLP:
+
Input: X [N x D]
Self-Attention
Weights: W , W [D x H]
1 2
W [H x D]
RMSNorm
3
Output:
𝑌 = 𝜎 𝑋𝑊 ⊙𝑋𝑊 𝑊
1 2 3
Setting H = 8D/3 keeps
x x x x
same total params
1 2 3 4
Shazeer, “GLU Variants Improve Transformers”, 2020 |
| Stanford CS231n 10th Anniversary Lecture 9 - 25 April 29, 2025 |


### Table 2

|  |  |  |


### Table 3

|  |
|  |


---
## Page 26
---


Mixture of Experts (MoE)
y y y y
1 2 3 4
Learn E separate sets of MLP weights in
each block; each MLP is an expert +
W : [D x 4D] => [E x D x 4D]
1 MLP MLP MLP MLP
W : [4D x D] => [E x 4D x D]
2
RMSNorm
+
Self-Attention
RMSNorm
x x x x
1 2 3 4
Shazeeret al, “Outrageously Large Neural Networks: The Sparsely-Gated Mixture-of-Experts Layer”, 2017
Stanford CS231n 10th Anniversary Lecture 9 - 26 April 29, 2025

[Page contains 4 table(s)]


### Table 1

| Mixture of Experts (MoE)
y y y y
1 2 3 4
Learn E separate sets of MLP weights in
each block; each MLP is an expert +
W : [D x 4D] => [E x D x 4D]
1 MLP MLP MLP MLP
W : [4D x D] => [E x 4D x D]
2
RMSNorm
+
Self-Attention
RMSNorm
x x x x
1 2 3 4
Shazeeret al, “Outrageously Large Neural Networks: The Sparsely-Gated Mixture-of-Experts Layer”, 2017 |
| Stanford CS231n 10th Anniversary Lecture 9 - 26 April 29, 2025 |


### Table 2

|  |  |  |


### Table 3

|  |
|  |


### Table 4

| Outrageously Large Neural Networks: The Sparsely | -Gated Mixture | -of | -Experts Layer |


---
## Page 27
---


Mixture of Experts (MoE)
y y y y
1 2 3 4
Learn E separate sets of MLP weights in
each block; each MLP is an expert +
W : [D x 4D] => [E x D x 4D]
1 MLP MLP MLP MLP
W : [4D x D] => [E x 4D x D]
2
Each token gets routed to A < E of the RMSNorm
experts. These are the active experts.
+
Increases params by E,
Self-Attention
But only increases compute by A
RMSNorm
x x x x
1 2 3 4
Shazeeret al, “Outrageously Large Neural Networks: The Sparsely-Gated Mixture-of-Experts Layer”, 2017
Stanford CS231n 10th Anniversary Lecture 9 - 27 April 29, 2025

[Page contains 4 table(s)]


### Table 1

| Mixture of Experts (MoE)
y y y y
1 2 3 4
Learn E separate sets of MLP weights in
each block; each MLP is an expert +
W : [D x 4D] => [E x D x 4D]
1 MLP MLP MLP MLP
W : [4D x D] => [E x 4D x D]
2
Each token gets routed to A < E of the RMSNorm
experts. These are the active experts.
+
Increases params by E,
Self-Attention
But only increases compute by A
RMSNorm
x x x x
1 2 3 4
Shazeeret al, “Outrageously Large Neural Networks: The Sparsely-Gated Mixture-of-Experts Layer”, 2017 |
| Stanford CS231n 10th Anniversary Lecture 9 - 27 April 29, 2025 |


### Table 2

|  |  |  |


### Table 3

|  |
|  |


### Table 4

| Outrageously Large Neural Networks: The Sparsely | -Gated Mixture | -of | -Experts Layer |


---
## Page 28
---


Mixture of Experts (MoE)
y y y y
1 2 3 4
Learn E separate sets of MLP weights in
each block; each MLP is an expert +
W : [D x 4D] => [E x D x 4D]
1 MLP MLP MLP MLP
W : [4D x D] => [E x 4D x D]
2
Each token gets routed to A < E of the RMSNorm
experts. These are the active experts.
+
Increases params by E,
Self-Attention
But only increases compute by A
RMSNorm
All of the biggest LLMs today (e.g. GPT4o,
GPT4.5, Claude 3.7, Gemini 2.5 Pro, etc)
almost certainly use MoEand have > 1T
params; but they don’t publish details
x x x x
anymore
1 2 3 4
Stanford CS231n 10th Anniversary Lecture 9 - 28 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Mixture of Experts (MoE)
y y y y
1 2 3 4
Learn E separate sets of MLP weights in
each block; each MLP is an expert +
W : [D x 4D] => [E x D x 4D]
1 MLP MLP MLP MLP
W : [4D x D] => [E x 4D x D]
2
Each token gets routed to A < E of the RMSNorm
experts. These are the active experts.
+
Increases params by E,
Self-Attention
But only increases compute by A
RMSNorm
All of the biggest LLMs today (e.g. GPT4o,
GPT4.5, Claude 3.7, Gemini 2.5 Pro, etc)
almost certainly use MoEand have > 1T
params; but they don’t publish details
x x x x
anymore
1 2 3 4 |
| Stanford CS231n 10th Anniversary Lecture 9 - 28 April 29, 2025 |


### Table 2

|  |  |  |


### Table 3

|  |
|  |


---
## Page 29
---


Tweaking Transformers
y y y y
1 2 3 4
The Transformer architecture has not changed
much since 2017. +
But a few changes have become common:
MLP MLP MLP MLP
- Pre-Norm: Move normalization inside
residual
- RMSNorm: Different normalization layer
RMSNorm
- SwiGLU: Different MLP architecture
- Mixture of Experts (MoE): Learn E different +
MLPs, use A < E of them per token. Massively
Self-Attention
increase params, modest increase to
compute cost.
RMSNorm
x x x x
1 2 3 4
Stanford CS231n 10th Anniversary Lecture 9 - 29 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Tweaking Transformers
y y y y
1 2 3 4
The Transformer architecture has not changed
much since 2017. +
But a few changes have become common:
MLP MLP MLP MLP
- Pre-Norm: Move normalization inside
residual
- RMSNorm: Different normalization layer
RMSNorm
- SwiGLU: Different MLP architecture
- Mixture of Experts (MoE): Learn E different +
MLPs, use A < E of them per token. Massively
Self-Attention
increase params, modest increase to
compute cost.
RMSNorm
x x x x
1 2 3 4 |
| Stanford CS231n 10th Anniversary Lecture 9 - 29 April 29, 2025 |


### Table 2

|  |  |  |


### Table 3

|  |
|  |


---
## Page 30
---


Today
● Transformers Recap
● Computer Vision Tasks
○ Semantic Segmentation
○ Object Detection
○ Instance Segmentation
● Visualization & Understanding
○ Model Layers Visualization
○ Saliency Maps
○ CAM & Grad-CAM
Stanford CS231n 10th Anniversary Lecture 9 - 30 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Today
● Transformers Recap
● Computer Vision Tasks
○ Semantic Segmentation
○ Object Detection
○ Instance Segmentation
● Visualization & Understanding
○ Model Layers Visualization
○ Saliency Maps
○ CAM & Grad-CAM |
| Stanford CS231n 10th Anniversary Lecture 9 - 30 April 29, 2025 |


---
## Page 31
---


Computer Vision Tasks
Semantic Instance
Object
Classification
Segmentation Segmentation
Detection
GRASS, CAT, TREE,
CAT DOG, DOG, CAT DOG, DOG, CAT
SKY
Multiple Object
No spatial extent No objects, just pixels
This imageis CC0 public domain
Stanford CS231n 10th Anniversary Lecture 9 - 31 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Computer Vision Tasks
Semantic Instance
Object
Classification
Segmentation Segmentation
Detection
GRASS, CAT, TREE,
CAT DOG, DOG, CAT DOG, DOG, CAT
SKY
Multiple Object
No spatial extent No objects, just pixels
This imageis CC0 public domain |
| Stanford CS231n 10th Anniversary Lecture 9 - 31 April 29, 2025 |


[Page contains 4 image(s)]


---
## Page 32
---


Recall: Image Classification: A core task in Computer Vision
(assume given a set of possible labels)
{dog, cat, truck, plane, ...}
cat
This imageby Nikitais
licensed under CC-BY 2.0
Stanford CS231n 10th Anniversary Lecture 9 - 32 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Recall: Image Classification: A core task in Computer Vision
(assume given a set of possible labels)
{dog, cat, truck, plane, ...}
cat
This imageby Nikitais
licensed under CC-BY 2.0 |
| Stanford CS231n 10th Anniversary Lecture 9 - 32 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 33
---


Semantic Segmentation
Semantic Instance
Object
Classification
Segmentation Segmentation
Detection
GRASS, CAT, TREE,
CAT DOG, DOG, CAT DOG, DOG, CAT
SKY
Multiple Object
No spatial extent No objects, just pixels
Stanford CS231n 10th Anniversary Lecture 9 - 33 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Semantic Segmentation
Semantic Instance
Object
Classification
Segmentation Segmentation
Detection
GRASS, CAT, TREE,
CAT DOG, DOG, CAT DOG, DOG, CAT
SKY
Multiple Object
No spatial extent No objects, just pixels |
| Stanford CS231n 10th Anniversary Lecture 9 - 33 April 29, 2025 |


[Page contains 4 image(s)]


---
## Page 34
---


Semantic Segmentation: The Problem
?
GRASS, CAT, TREE,
At test time, classify each pixel of a new image.
SKY, ...
Paired training data: for each training image,
each pixel is labeled with a semantic category.
Stanford CS231n 10th Anniversary Lecture 9 - 34 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Semantic Segmentation: The Problem
?
GRASS, CAT, TREE,
At test time, classify each pixel of a new image.
SKY, ...
Paired training data: for each training image,
each pixel is labeled with a semantic category. |
| Stanford CS231n 10th Anniversary Lecture 9 - 34 April 29, 2025 |


[Page contains 3 image(s)]


---
## Page 35
---


Semantic Segmentation Idea: Sliding Window
Full image
?
Stanford CS231n 10th Anniversary Lecture 9 - 35 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Semantic Segmentation Idea: Sliding Window
Full image
? |
| Stanford CS231n 10th Anniversary Lecture 9 - 35 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 36
---


Semantic Segmentation Idea: Sliding Window
Full image
?
Impossible to classify without context
Q: how do we include context?
Stanford CS231n 10th Anniversary Lecture 9 - 36 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Semantic Segmentation Idea: Sliding Window
Full image
?
Impossible to classify without context
Q: how do we include context? |
| Stanford CS231n 10th Anniversary Lecture 9 - 36 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 37
---


Semantic Segmentation Idea: Sliding Window
Full image
Q: how do we model this?
Stanford CS231n 10th Anniversary Lecture 9 - 37 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Semantic Segmentation Idea: Sliding Window
Full image
Q: how do we model this? |
| Stanford CS231n 10th Anniversary Lecture 9 - 37 April 29, 2025 |


### Table 2

|  |  |
|  |  |


### Table 3

|  |  |
|  |  |
|  |  |


[Page contains 4 image(s)]


---
## Page 38
---


Semantic Segmentation Idea: Sliding Window
Classify center pixel
Extract patch
with CNN
Full image
Cow
Cow
Grass
Farabetet al, “Learning Hierarchical Features for Scene Labeling,” TPAMI 2013
Pinheiro and Collobert, “Recurrent Convolutional Neural Networks for Scene Labeling”, ICML 2014
Stanford CS231n 10th Anniversary Lecture 9 - 38 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Semantic Segmentation Idea: Sliding Window
Classify center pixel
Extract patch
with CNN
Full image
Cow
Cow
Grass
Farabetet al, “Learning Hierarchical Features for Scene Labeling,” TPAMI 2013
Pinheiro and Collobert, “Recurrent Convolutional Neural Networks for Scene Labeling”, ICML 2014 |
| Stanford CS231n 10th Anniversary Lecture 9 - 38 April 29, 2025 |


### Table 2

|  |  |
|  |  |


### Table 3

|  |  |
|  |  |
|  |  |


[Page contains 7 image(s)]


---
## Page 39
---


Semantic Segmentation Idea: Sliding Window
Classify center pixel
Extract patch
with CNN
Full image
Cow
Cow
Grass
Problem: Very inefficient! Not
reusing shared features between
overlapping patches
Farabetet al, “Learning Hierarchical Features for Scene Labeling,” TPAMI 2013
Pinheiro and Collobert, “Recurrent Convolutional Neural Networks for Scene Labeling”, ICML 2014
Stanford CS231n 10th Anniversary Lecture 9 - 39 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Semantic Segmentation Idea: Sliding Window
Classify center pixel
Extract patch
with CNN
Full image
Cow
Cow
Grass
Problem: Very inefficient! Not
reusing shared features between
overlapping patches
Farabetet al, “Learning Hierarchical Features for Scene Labeling,” TPAMI 2013
Pinheiro and Collobert, “Recurrent Convolutional Neural Networks for Scene Labeling”, ICML 2014 |
| Stanford CS231n 10th Anniversary Lecture 9 - 39 April 29, 2025 |


### Table 2

|  |  |
|  |  |


### Table 3

|  |  |
|  |  |
|  |  |


[Page contains 7 image(s)]


---
## Page 40
---


Semantic Segmentation Idea: Convolution
Full image
An intuitive idea: encode the entire image with conv net, and do semantic segmentation on
top.
Problem: classification architectures often reduce feature spatial sizes to go deeper, but
semantic segmentation requires the output size to be the same as input size.
Stanford CS231n 10th Anniversary Lecture 9 - 40 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Semantic Segmentation Idea: Convolution
Full image
An intuitive idea: encode the entire image with conv net, and do semantic segmentation on
top.
Problem: classification architectures often reduce feature spatial sizes to go deeper, but
semantic segmentation requires the output size to be the same as input size. |
| Stanford CS231n 10th Anniversary Lecture 9 - 40 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 41
---


Semantic Segmentation Idea: Fully Convolutional
Design a network with only convolutional layers
without downsamplingoperators to make predictions
for pixels all at once!
Conv Conv Conv Conv argmax
Input:
Predictions:
Scores:
3 x H x W
H x W
C x H x W
Convolutions:
D x H x W
Stanford CS231n 10th Anniversary Lecture 9 - 41 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Semantic Segmentation Idea: Fully Convolutional
Design a network with only convolutional layers
without downsamplingoperators to make predictions
for pixels all at once!
Conv Conv Conv Conv argmax
Input:
Predictions:
Scores:
3 x H x W
H x W
C x H x W
Convolutions:
D x H x W |
| Stanford CS231n 10th Anniversary Lecture 9 - 41 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 42
---


Semantic Segmentation Idea: Fully Convolutional
Design a network with only convolutional layers
without downsamplingoperators to make predictions
for pixels all at once!
Conv Conv Conv Conv argmax
Input:
Predictions:
Scores:
3 x H x W
H x W
C x H x W
Convolutions:
Problem: convolutions at
D x H x W
original image resolution will be
very expensive ...
Stanford CS231n 10th Anniversary Lecture 9 - 42 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Semantic Segmentation Idea: Fully Convolutional
Design a network with only convolutional layers
without downsamplingoperators to make predictions
for pixels all at once!
Conv Conv Conv Conv argmax
Input:
Predictions:
Scores:
3 x H x W
H x W
C x H x W
Convolutions:
Problem: convolutions at
D x H x W
original image resolution will be
very expensive ... |
| Stanford CS231n 10th Anniversary Lecture 9 - 42 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 43
---


Semantic Segmentation Idea: Fully Convolutional
Design network as a bunch of convolutional layers, with
downsamplingand upsamplinginside the network!
Med-res: Med-res:
D x H/4 x W/4 D x H/4 x W/4
2 2
Low-res:
D x H/4 x W/4
3
Input: High-res: C x H x W
High-res: Predictions:
3 x H x W D x H/2 x W/2
1 D x H/2 x W/2 H x W
1
Long, Shelhamer, and Darrell, “Fully Convolutional Networks for Semantic Segmentation”, CVPR 2015
Noh et al, “Learning Deconvolution Network for Semantic Segmentation”, ICCV 2015
Stanford CS231n 10th Anniversary Lecture 9 - 43 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Semantic Segmentation Idea: Fully Convolutional
Design network as a bunch of convolutional layers, with
downsamplingand upsamplinginside the network!
Med-res: Med-res:
D x H/4 x W/4 D x H/4 x W/4
2 2
Low-res:
D x H/4 x W/4
3
Input: High-res: C x H x W
High-res: Predictions:
3 x H x W D x H/2 x W/2
1 D x H/2 x W/2 H x W
1
Long, Shelhamer, and Darrell, “Fully Convolutional Networks for Semantic Segmentation”, CVPR 2015
Noh et al, “Learning Deconvolution Network for Semantic Segmentation”, ICCV 2015 |
| Stanford CS231n 10th Anniversary Lecture 9 - 43 April 29, 2025 |


### Table 2

|  |
|  |


### Table 3

|  |  |  |


[Page contains 1 image(s)]


---
## Page 44
---


Semantic Segmentation Idea: Fully Convolutional
Downsampling: Design network as a bunch of convolutional layers, with Upsampling:
Pooling, strided downsamplingand upsamplinginside the network! ???
convolution
Med-res: Med-res:
D x H/4 x W/4 D x H/4 x W/4
2 2
Low-res:
D x H/4 x W/4
3
Input: High-res: C x H x W
High-res: Predictions:
3 x H x W D x H/2 x W/2
1 D x H/2 x W/2 H x W
1
Long, Shelhamer, and Darrell, “Fully Convolutional Networks for Semantic Segmentation”, CVPR 2015
Noh et al, “Learning Deconvolution Network for Semantic Segmentation”, ICCV 2015
Stanford CS231n 10th Anniversary Lecture 9 - 44 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Semantic Segmentation Idea: Fully Convolutional
Downsampling: Design network as a bunch of convolutional layers, with Upsampling:
Pooling, strided downsamplingand upsamplinginside the network! ???
convolution
Med-res: Med-res:
D x H/4 x W/4 D x H/4 x W/4
2 2
Low-res:
D x H/4 x W/4
3
Input: High-res: C x H x W
High-res: Predictions:
3 x H x W D x H/2 x W/2
1 D x H/2 x W/2 H x W
1
Long, Shelhamer, and Darrell, “Fully Convolutional Networks for Semantic Segmentation”, CVPR 2015
Noh et al, “Learning Deconvolution Network for Semantic Segmentation”, ICCV 2015 |
| Stanford CS231n 10th Anniversary Lecture 9 - 44 April 29, 2025 |


### Table 2

|  |
|  |


### Table 3

|  |  |  |


[Page contains 1 image(s)]


---
## Page 45
---


In-Network upsampling: “Unpooling”
Nearest Neighbor “Bed of Nails”
1 1 2 2 1 0 2 0
1 2 1 1 2 2 1 2 0 0 0 0
3 4 3 3 4 4 3 4 3 0 4 0
3 3 4 4 0 0 0 0
Input: 2 x 2 Output: 4 x 4 Input: 2 x 2 Output: 4 x 4
Stanford CS231n 10th Anniversary Lecture 9 - 45 April 29, 2025

[Page contains 5 table(s)]


### Table 1

| In-Network upsampling: “Unpooling”
Nearest Neighbor “Bed of Nails”
1 1 2 2 1 0 2 0
1 2 1 1 2 2 1 2 0 0 0 0
3 4 3 3 4 4 3 4 3 0 4 0
3 3 4 4 0 0 0 0
Input: 2 x 2 Output: 4 x 4 Input: 2 x 2 Output: 4 x 4 |
| Stanford CS231n 10th Anniversary Lecture 9 - 45 April 29, 2025 |


### Table 2

| 1 | 1 | 2 | 2 |
| 1 | 1 | 2 | 2 |
| 3 | 3 | 4 | 4 |
| 3 | 3 | 4 | 4 |


### Table 3

| 1 | 0 | 2 | 0 |
| 0 | 0 | 0 | 0 |
| 3 | 0 | 4 | 0 |
| 0 | 0 | 0 | 0 |


### Table 4

| 1 | 2 |
| 3 | 4 |


### Table 5

| 1 | 2 |
| 3 | 4 |


---
## Page 46
---


In-Network upsampling: “Max Unpooling”
Max Pooling
Max Unpooling
Remember which element was max!
Use positions from
pooling layer
1 2 6 3 0 0 2 0
3 5 2 1 5 6 … 1 2 0 1 0 0
1 2 2 1 7 8 3 4 0 0 0 0
Rest of the network
7 3 4 8 3 0 0 4
Input: 4 x 4 Output: 2 x 2 Input: 2 x 2 Output: 4 x 4
Corresponding pairs of
downsamplingand
upsamplinglayers
Stanford CS231n 10th Anniversary Lecture 9 - 46 April 29, 2025

[Page contains 9 table(s)]


### Table 1

| In-Network upsampling: “Max Unpooling”
Max Pooling
Max Unpooling
Remember which element was max!
Use positions from
pooling layer
1 2 6 3 0 0 2 0
3 5 2 1 5 6 … 1 2 0 1 0 0
1 2 2 1 7 8 3 4 0 0 0 0
Rest of the network
7 3 4 8 3 0 0 4
Input: 4 x 4 Output: 2 x 2 Input: 2 x 2 Output: 4 x 4
Corresponding pairs of
downsamplingand
upsamplinglayers |
| Stanford CS231n 10th Anniversary Lecture 9 - 46 April 29, 2025 |


### Table 2

| 1 | 2 | 6 | 3 |
| 3 | 5 | 2 | 1 |
| 1 | 2 | 2 | 1 |
| 7 | 3 | 4 | 8 |


### Table 3

| 0 | 0 | 2 | 0 |
| 0 | 1 | 0 | 0 |
| 0 | 0 | 0 | 0 |
| 3 | 0 | 0 | 4 |


### Table 4

| 5 | 6 |
| 7 | 8 |


### Table 5

| 1 | 2 |


### Table 6

|  |  |  |
|  |  |  |
|  |  |  |


### Table 7

|  |  |


### Table 8

|  |  |  |  |
|  |  |  |  |


### Table 9

|  |  |


---
## Page 47
---


Learnable Upsampling
Recall: Normal 3 x 3 convolution, stride 1 pad 1
Input: 4 x 4 Output: 4 x 4
Stanford CS231n 10th Anniversary Lecture 9 - 47 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Learnable Upsampling
Recall: Normal 3 x 3 convolution, stride 1 pad 1
Input: 4 x 4 Output: 4 x 4 |
| Stanford CS231n 10th Anniversary Lecture 9 - 47 April 29, 2025 |


### Table 2

|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |


### Table 3

|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |


---
## Page 48
---


Learnable Upsampling
Recall: Normal 3 x 3 convolution, stride 1 pad 1
Dot product
between filter
and input
Input: 4 x 4 Output: 4 x 4
Stanford CS231n 10th Anniversary Lecture 9 - 48 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Learnable Upsampling
Recall: Normal 3 x 3 convolution, stride 1 pad 1
Dot product
between filter
and input
Input: 4 x 4 Output: 4 x 4 |
| Stanford CS231n 10th Anniversary Lecture 9 - 48 April 29, 2025 |


### Table 2

|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |


### Table 3

|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |


---
## Page 49
---


Learnable Upsampling
Recall: Normal 3 x 3 convolution, stride 1 pad 1
Dot product
between filter
and input
Input: 4 x 4 Output: 4 x 4
Stanford CS231n 10th Anniversary Lecture 9 - 49 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Learnable Upsampling
Recall: Normal 3 x 3 convolution, stride 1 pad 1
Dot product
between filter
and input
Input: 4 x 4 Output: 4 x 4 |
| Stanford CS231n 10th Anniversary Lecture 9 - 49 April 29, 2025 |


### Table 2

|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |


### Table 3

|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |


---
## Page 50
---


Learnable Upsampling
Recall: Normal 3 x 3 convolution, stride 2 pad 1
Input: 4 x 4 Output: 2 x 2
Stanford CS231n 10th Anniversary Lecture 9 - 50 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Learnable Upsampling
Recall: Normal 3 x 3 convolution, stride 2 pad 1
Input: 4 x 4 Output: 2 x 2 |
| Stanford CS231n 10th Anniversary Lecture 9 - 50 April 29, 2025 |


### Table 2

|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |


### Table 3

|  |  |
|  |  |


---
## Page 51
---


Learnable Upsampling
Recall: Normal 3 x 3 convolution, stride 2 pad 1
Dot product
between filter
and input
Input: 4 x 4 Output: 2 x 2
Stanford CS231n 10th Anniversary Lecture 9 - 51 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Learnable Upsampling
Recall: Normal 3 x 3 convolution, stride 2 pad 1
Dot product
between filter
and input
Input: 4 x 4 Output: 2 x 2 |
| Stanford CS231n 10th Anniversary Lecture 9 - 51 April 29, 2025 |


### Table 2

|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |


### Table 3

|  |  |
|  |  |


---
## Page 52
---


Learnable Upsampling
Recall: Normal 3 x 3 convolution, stride 2 pad 1
Filter moves 2 pixels in the
input for every one pixel in
the output
Dot product
between filter Stride gives ratio between
and input movement in input and
output
We can interpret strided
Input: 4 x 4 Output: 2 x 2 convolution as “learnable
downsampling”.
Stanford CS231n 10th Anniversary Lecture 9 - 52 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Learnable Upsampling
Recall: Normal 3 x 3 convolution, stride 2 pad 1
Filter moves 2 pixels in the
input for every one pixel in
the output
Dot product
between filter Stride gives ratio between
and input movement in input and
output
We can interpret strided
Input: 4 x 4 Output: 2 x 2 convolution as “learnable
downsampling”. |
| Stanford CS231n 10th Anniversary Lecture 9 - 52 April 29, 2025 |


### Table 2

|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |


### Table 3

|  |  |
|  |  |


---
## Page 53
---


Learnable Upsampling: Transposed Convolution
3 x 3 transposed convolution, stride 2 pad 1
Input: 2 x 2 Output: 4 x 4
Stanford CS231n 10th Anniversary Lecture 9 - 53 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Learnable Upsampling: Transposed Convolution
3 x 3 transposed convolution, stride 2 pad 1
Input: 2 x 2 Output: 4 x 4 |
| Stanford CS231n 10th Anniversary Lecture 9 - 53 April 29, 2025 |


### Table 2

|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |


### Table 3

|  |  |
|  |  |


---
## Page 54
---


Learnable Upsampling: Transposed Convolution
3 x 3 transposed convolution, stride 2 pad 1
Input gives
weight for
filter
Input: 2 x 2 Output: 4 x 4
Stanford CS231n 10th Anniversary Lecture 9 - 54 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Learnable Upsampling: Transposed Convolution
3 x 3 transposed convolution, stride 2 pad 1
Input gives
weight for
filter
Input: 2 x 2 Output: 4 x 4 |
| Stanford CS231n 10th Anniversary Lecture 9 - 54 April 29, 2025 |


### Table 2

|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |


### Table 3

|  |  |
|  |  |


---
## Page 55
---


Learnable Upsampling: Transposed Convolution
3 x 3 transposed convolution, stride 2 pad 1
Filter moves 2 pixels in the
Input gives outputfor every one pixel
weight for in the input
filter
Stride gives ratio between
movement in output and
input
Input: 2 x 2 Output: 4 x 4
Stanford CS231n 10th Anniversary Lecture 9 - 55 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Learnable Upsampling: Transposed Convolution
3 x 3 transposed convolution, stride 2 pad 1
Filter moves 2 pixels in the
Input gives outputfor every one pixel
weight for in the input
filter
Stride gives ratio between
movement in output and
input
Input: 2 x 2 Output: 4 x 4 |
| Stanford CS231n 10th Anniversary Lecture 9 - 55 April 29, 2025 |


### Table 2

|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |


### Table 3

|  |  |
|  |  |


---
## Page 56
---


Learnable Upsampling: Transposed Convolution
Sum where
3 x 3 transposed convolution, stride 2 pad 1
output overlaps
Filter moves 2 pixels in the
Input gives outputfor every one pixel
weight for in the input
filter
Stride gives ratio between
movement in output and
input
Input: 2 x 2 Output: 4 x 4
Stanford CS231n 10th Anniversary Lecture 9 - 56 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Learnable Upsampling: Transposed Convolution
Sum where
3 x 3 transposed convolution, stride 2 pad 1
output overlaps
Filter moves 2 pixels in the
Input gives outputfor every one pixel
weight for in the input
filter
Stride gives ratio between
movement in output and
input
Input: 2 x 2 Output: 4 x 4 |
| Stanford CS231n 10th Anniversary Lecture 9 - 56 April 29, 2025 |


### Table 2

|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |


### Table 3

|  |  |
|  |  |


---
## Page 57
---


Learnable Upsampling: Transposed Convolution
Sum where
3 x 3 transposed convolution, stride 2 pad 1
output overlaps
Filter moves 2 pixels in the
Input gives outputfor every one pixel
weight for in the input
filter
Stride gives ratio between
movement in output and
input
Input: 2 x 2 Output: 4 x 4
Stanford CS231n 10th Anniversary Lecture 9 - 57 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Learnable Upsampling: Transposed Convolution
Sum where
3 x 3 transposed convolution, stride 2 pad 1
output overlaps
Filter moves 2 pixels in the
Input gives outputfor every one pixel
weight for in the input
filter
Stride gives ratio between
movement in output and
input
Input: 2 x 2 Output: 4 x 4 |
| Stanford CS231n 10th Anniversary Lecture 9 - 57 April 29, 2025 |


### Table 2

|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |


### Table 3

|  |  |
|  |  |


---
## Page 58
---


Learnable Upsampling: 1D Example
Output
Input
Filter
Output contains
ax
copies of the filter
weighted by the
x
ay input, summing at
a where at overlaps in
the output
y
az + bx
b
z
by
bz
Stanford CS231n 10th Anniversary Lecture 9 - 58 April 29, 2025

[Page contains 4 table(s)]


### Table 1

| Learnable Upsampling: 1D Example
Output
Input
Filter
Output contains
ax
copies of the filter
weighted by the
x
ay input, summing at
a where at overlaps in
the output
y
az + bx
b
z
by
bz |
| Stanford CS231n 10th Anniversary Lecture 9 - 58 April 29, 2025 |


### Table 2

| ax |  |  |  |  |
|  | ax |  |  |  |
|  | ay |  |  |  |
| az + bx | az |  |  |  |
|  |  |  | bx |  |
|  |  |  | by |  |
| bz |  |  | bz |  |


### Table 3

| x |
| y |
| z |


### Table 4

| a |
| b |


---
## Page 59
---


Semantic Segmentation Idea: Fully Convolutional
Upsampling:
Downsampling: Design network as a bunch of convolutional layers, with
Unpoolingor strided
Pooling, strided downsamplingand upsamplinginside the network!
transposed convolution
convolution
Med-res: Med-res:
D x H/4 x W/4 D x H/4 x W/4
2 2
Low-res:
D x H/4 x W/4
3
Input: High-res: High-res:
Predictions:
3 x H x W D x H/2 x W/2 D x H/2 x W/2
1 1 H x W
Long, Shelhamer, and Darrell, “Fully Convolutional Networks for Semantic Segmentation”, CVPR 2015
Noh et al, “Learning Deconvolution Network for Semantic Segmentation”, ICCV 2015
Stanford CS231n 10th Anniversary Lecture 9 - 59 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Semantic Segmentation Idea: Fully Convolutional
Upsampling:
Downsampling: Design network as a bunch of convolutional layers, with
Unpoolingor strided
Pooling, strided downsamplingand upsamplinginside the network!
transposed convolution
convolution
Med-res: Med-res:
D x H/4 x W/4 D x H/4 x W/4
2 2
Low-res:
D x H/4 x W/4
3
Input: High-res: High-res:
Predictions:
3 x H x W D x H/2 x W/2 D x H/2 x W/2
1 1 H x W
Long, Shelhamer, and Darrell, “Fully Convolutional Networks for Semantic Segmentation”, CVPR 2015
Noh et al, “Learning Deconvolution Network for Semantic Segmentation”, ICCV 2015 |
| Stanford CS231n 10th Anniversary Lecture 9 - 59 April 29, 2025 |


### Table 2

|  |
|  |


### Table 3

|  |  |  |


[Page contains 1 image(s)]


---
## Page 60
---


U-Net
Ronnebergeret al. (2015) U-net Architecture
Stanford CS231n 10th Anniversary Lecture 9 - 60 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| U-Net
Ronnebergeret al. (2015) U-net Architecture |
| Stanford CS231n 10th Anniversary Lecture 9 - 60 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 61
---


U-Net
“downsampling” Phase
-Increases field of view
-Lose Spatial Information
Ronnebergeret al. (2015) U-net Architecture
Stanford CS231n 10th Anniversary Lecture 9 - 61 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| U-Net
“downsampling” Phase
-Increases field of view
-Lose Spatial Information
Ronnebergeret al. (2015) U-net Architecture |
| Stanford CS231n 10th Anniversary Lecture 9 - 61 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 62
---


U-Net
“Upsampling” Phase
- Create High Resolution
Mapping
Ronnebergeret al. (2015) U-net Architecture
Stanford CS231n 10th Anniversary Lecture 9 - 62 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| U-Net
“Upsampling” Phase
- Create High Resolution
Mapping
Ronnebergeret al. (2015) U-net Architecture |
| Stanford CS231n 10th Anniversary Lecture 9 - 62 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 63
---


U-Net
Concatenate with high-resolution feature maps
from the downsamplingPhase
Ronnebergeret al. (2015) U-net Architecture
Stanford CS231n 10th Anniversary Lecture 9 - 63 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| U-Net
Concatenate with high-resolution feature maps
from the downsamplingPhase
Ronnebergeret al. (2015) U-net Architecture |
| Stanford CS231n 10th Anniversary Lecture 9 - 63 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 64
---


Semantic Segmentation: Summary
Stanford CS231n 10th Anniversary Lecture 9 - 64 April 29, 2025

[Page contains 4 table(s)]


### Table 1

| Semantic Segmentation: Summary |
| Stanford CS231n 10th Anniversary Lecture 9 - 64 April 29, 2025 |


### Table 2

|  |  |
|  |  |
|  |  |


### Table 3

|  |
|  |


### Table 4

|  |  |


[Page contains 6 image(s)]


---
## Page 65
---


Semantic Segmentation
This imageis CC0 public domain
Label each pixel in the
image with a category label
Sky
Sky
Don’t differentiate
instances, only care about
Cow
pixels Cat
Grass
Grass
Stanford CS231n 10th Anniversary Lecture 9 - 65 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Semantic Segmentation
This imageis CC0 public domain
Label each pixel in the
image with a category label
Sky
Sky
Don’t differentiate
instances, only care about
Cow
pixels Cat
Grass
Grass |
| Stanford CS231n 10th Anniversary Lecture 9 - 65 April 29, 2025 |


[Page contains 3 image(s)]


---
## Page 66
---


Object Detection
Semantic Instance
Object
Classification
Segmentation Segmentation
Detection
GRASS, CAT, TREE,
CAT DOG, DOG, CAT DOG, DOG, CAT
SKY
Multiple Object
No spatial extent No objects, just pixels
Stanford CS231n 10th Anniversary Lecture 9 - 66 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Object Detection
Semantic Instance
Object
Classification
Segmentation Segmentation
Detection
GRASS, CAT, TREE,
CAT DOG, DOG, CAT DOG, DOG, CAT
SKY
Multiple Object
No spatial extent No objects, just pixels |
| Stanford CS231n 10th Anniversary Lecture 9 - 66 April 29, 2025 |


[Page contains 4 image(s)]


---
## Page 67
---


Object Detection
Semantic Instance
Object
Classification
Segmentation Segmentation
Detection
GRASS, CAT, TREE,
CAT DOG, DOG, CAT DOG, DOG, CAT
SKY
Multiple Object
No spatial extent No objects, just pixels
Stanford CS231n 10th Anniversary Lecture 9 - 67 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Object Detection
Semantic Instance
Object
Classification
Segmentation Segmentation
Detection
GRASS, CAT, TREE,
CAT DOG, DOG, CAT DOG, DOG, CAT
SKY
Multiple Object
No spatial extent No objects, just pixels |
| Stanford CS231n 10th Anniversary Lecture 9 - 67 April 29, 2025 |


[Page contains 4 image(s)]


---
## Page 68
---


Object Detection: Single Object
(Classification + Localization)
Class Scores
Fully Cat: 0.9
Connected: Dog: 0.05
4096 to 1000
Car: 0.01
...
x, y
h
w
Fully
Vector:
This imageis CC0 public domain Connected:
4096 Box
4096 to 4
Coordinates
(x, y, w, h)
Stanford CS231n 10th Anniversary Lecture 9 - 68 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Object Detection: Single Object
(Classification + Localization)
Class Scores
Fully Cat: 0.9
Connected: Dog: 0.05
4096 to 1000
Car: 0.01
...
x, y
h
w
Fully
Vector:
This imageis CC0 public domain Connected:
4096 Box
4096 to 4
Coordinates
(x, y, w, h) |
| Stanford CS231n 10th Anniversary Lecture 9 - 68 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 69
---


Object Detection: Single Object
Correct label:
Cat
(Classification + Localization)
Class Scores
Fully Cat: 0.9 Softmax
Connected: Dog: 0.05 Loss
4096 to 1000
Car: 0.01
...
x, y
h
w
Fully
Vector:
This imageis CC0 public domain Connected:
4096 Box
4096 to 4
Coordinates L2 Loss
(x, y, w, h)
Treat localization as a
regression problem! Correct box:
(x’, y’, w’, h’)
Stanford CS231n 10th Anniversary Lecture 9 - 69 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Object Detection: Single Object
Correct label:
Cat
(Classification + Localization)
Class Scores
Fully Cat: 0.9 Softmax
Connected: Dog: 0.05 Loss
4096 to 1000
Car: 0.01
...
x, y
h
w
Fully
Vector:
This imageis CC0 public domain Connected:
4096 Box
4096 to 4
Coordinates L2 Loss
(x, y, w, h)
Treat localization as a
regression problem! Correct box:
(x’, y’, w’, h’) |
| Stanford CS231n 10th Anniversary Lecture 9 - 69 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 70
---


Object Detection: Single Object
Correct label:
Cat
(Classification + Localization)
Class Scores
Fully Cat: 0.9 Softmax
Connected: Dog: 0.05 Loss
4096 to 1000
Car: 0.01
...
x, y
Multitask Loss +
h Loss
w
Fully
Vector:
This imageis CC0 public domain Connected:
4096 Box
4096 to 4
Coordinates L2 Loss
(x, y, w, h)
Treat localization as a
regression problem! Correct box:
(x’, y’, w’, h’)
Stanford CS231n 10th Anniversary Lecture 9 - 70 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Object Detection: Single Object
Correct label:
Cat
(Classification + Localization)
Class Scores
Fully Cat: 0.9 Softmax
Connected: Dog: 0.05 Loss
4096 to 1000
Car: 0.01
...
x, y
Multitask Loss +
h Loss
w
Fully
Vector:
This imageis CC0 public domain Connected:
4096 Box
4096 to 4
Coordinates L2 Loss
(x, y, w, h)
Treat localization as a
regression problem! Correct box:
(x’, y’, w’, h’) |
| Stanford CS231n 10th Anniversary Lecture 9 - 70 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 71
---


Object Detection: Multiple Objects
CAT: (x, y, w, h)
DOG: (x, y, w, h)
DOG: (x, y, w, h)
CAT: (x, y, w, h)
DUCK: (x, y, w, h)
DUCK: (x, y, w, h)
….
Stanford CS231n 10th Anniversary Lecture 9 - 71 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Object Detection: Multiple Objects
CAT: (x, y, w, h)
DOG: (x, y, w, h)
DOG: (x, y, w, h)
CAT: (x, y, w, h)
DUCK: (x, y, w, h)
DUCK: (x, y, w, h)
…. |
| Stanford CS231n 10th Anniversary Lecture 9 - 71 April 29, 2025 |


[Page contains 6 image(s)]


---
## Page 72
---


Each image needs a different
Object Detection: Multiple Objects
number of outputs!
CAT: (x, y, w, h)
4 numbers
DOG: (x, y, w, h)
DOG: (x, y, w, h)
12 numbers
CAT: (x, y, w, h)
DUCK: (x, y, w, h)
Many
DUCK: (x, y, w, h)
numbers!
….
Stanford CS231n 10th Anniversary Lecture 9 - 72 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Each image needs a different
Object Detection: Multiple Objects
number of outputs!
CAT: (x, y, w, h)
4 numbers
DOG: (x, y, w, h)
DOG: (x, y, w, h)
12 numbers
CAT: (x, y, w, h)
DUCK: (x, y, w, h)
Many
DUCK: (x, y, w, h)
numbers!
…. |
| Stanford CS231n 10th Anniversary Lecture 9 - 72 April 29, 2025 |


[Page contains 6 image(s)]


---
## Page 73
---


Object Detection: Multiple Objects
Apply a CNN to many different crops of the
image, CNN classifies each crop as object or
background
Dog? NO
Cat? NO
Background? YES
Stanford CS231n 10th Anniversary Lecture 9 - 73 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Object Detection: Multiple Objects
Apply a CNN to many different crops of the
image, CNN classifies each crop as object or
background
Dog? NO
Cat? NO
Background? YES |
| Stanford CS231n 10th Anniversary Lecture 9 - 73 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 74
---


Object Detection: Multiple Objects
Apply a CNN to many different crops of the
image, CNN classifies each crop as object or
background
Dog? YES
Cat? NO
Background? NO
Stanford CS231n 10th Anniversary Lecture 9 - 74 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Object Detection: Multiple Objects
Apply a CNN to many different crops of the
image, CNN classifies each crop as object or
background
Dog? YES
Cat? NO
Background? NO |
| Stanford CS231n 10th Anniversary Lecture 9 - 74 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 75
---


Object Detection: Multiple Objects
Apply a CNN to many different crops of the
image, CNN classifies each crop as object or
background
Dog? YES
Cat? NO
Background? NO
Stanford CS231n 10th Anniversary Lecture 9 - 75 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Object Detection: Multiple Objects
Apply a CNN to many different crops of the
image, CNN classifies each crop as object or
background
Dog? YES
Cat? NO
Background? NO |
| Stanford CS231n 10th Anniversary Lecture 9 - 75 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 76
---


Object Detection: Multiple Objects
Apply a CNN to many different crops of the
image, CNN classifies each crop as object or
background
Dog? NO
Cat? YES
Background? NO
Q: What’s the problem with this approach?
Stanford CS231n 10th Anniversary Lecture 9 - 76 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Object Detection: Multiple Objects
Apply a CNN to many different crops of the
image, CNN classifies each crop as object or
background
Dog? NO
Cat? YES
Background? NO
Q: What’s the problem with this approach? |
| Stanford CS231n 10th Anniversary Lecture 9 - 76 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 77
---


Object Detection: Multiple Objects
Apply a CNN to many different crops of the
image, CNN classifies each crop as object or
background
Dog? NO
Cat? YES
Background? NO
Problem: Need to apply CNN to huge number
of locations, scales, and aspect ratios, very
computationally expensive!
Stanford CS231n 10th Anniversary Lecture 9 - 77 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| Object Detection: Multiple Objects
Apply a CNN to many different crops of the
image, CNN classifies each crop as object or
background
Dog? NO
Cat? YES
Background? NO
Problem: Need to apply CNN to huge number
of locations, scales, and aspect ratios, very
computationally expensive! |
| Stanford CS231n 10th Anniversary Lecture 9 - 77 April 29, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |


[Page contains 2 image(s)]


---
## Page 78
---


Region Proposals: Selective Search
● Find “blobby” image regions that are likely to contain objects
● Relatively fast to run; e.g. Selective Search gives 2000 region
proposals in a few seconds on CPU
Alexeet al, “Measuring the objectnessof image windows”, TPAMI 2012
Uijlingset al, “Selective Search for Object Recognition”, IJCV 2013
Cheng et al, “BING: Binarized normed gradients for objectnessestimation at 300fps”, CVPR 2014
Zitnickand Dollar, “Edge boxes: Locating object proposals from edges”, ECCV 2014
Stanford CS231n 10th Anniversary Lecture 9 - 78 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Region Proposals: Selective Search
● Find “blobby” image regions that are likely to contain objects
● Relatively fast to run; e.g. Selective Search gives 2000 region
proposals in a few seconds on CPU
Alexeet al, “Measuring the objectnessof image windows”, TPAMI 2012
Uijlingset al, “Selective Search for Object Recognition”, IJCV 2013
Cheng et al, “BING: Binarized normed gradients for objectnessestimation at 300fps”, CVPR 2014
Zitnickand Dollar, “Edge boxes: Locating object proposals from edges”, ECCV 2014 |
| Stanford CS231n 10th Anniversary Lecture 9 - 78 April 29, 2025 |


### Table 2

|  |  |  |
|  |  |  |
|  |  |  |


### Table 3

|  |  |  |
|  |  |  |


[Page contains 2 image(s)]


---
## Page 79
---


R-CNN
Girshicket al, “Rich feature hierarchies for accurate object detection and semantic
Input image segmentation”, CVPR 2014.
Figure copyright Ross Girshick, 2015; source. Reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 9 - 79 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| R-CNN
Girshicket al, “Rich feature hierarchies for accurate object detection and semantic
Input image segmentation”, CVPR 2014.
Figure copyright Ross Girshick, 2015; source. Reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 9 - 79 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 80
---


R-CNN
Regions of Interest
(RoI) from a proposal
method(~2k)
Girshicket al, “Rich feature hierarchies for accurate object detection and semantic
Input image segmentation”, CVPR 2014.
Figure copyright Ross Girshick, 2015; source. Reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 9 - 80 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| R-CNN
Regions of Interest
(RoI) from a proposal
method(~2k)
Girshicket al, “Rich feature hierarchies for accurate object detection and semantic
Input image segmentation”, CVPR 2014.
Figure copyright Ross Girshick, 2015; source. Reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 9 - 80 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 81
---


R-CNN
Warped image regions
(224x224 pixels)
Regions of Interest
(RoI) from a proposal
method(~2k)
Girshicket al, “Rich feature hierarchies for accurate object detection and semantic
Input image segmentation”, CVPR 2014.
Figure copyright Ross Girshick, 2015; source. Reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 9 - 81 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| R-CNN
Warped image regions
(224x224 pixels)
Regions of Interest
(RoI) from a proposal
method(~2k)
Girshicket al, “Rich feature hierarchies for accurate object detection and semantic
Input image segmentation”, CVPR 2014.
Figure copyright Ross Girshick, 2015; source. Reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 9 - 81 April 29, 2025 |


### Table 2

|  |
|  |


### Table 3

|  |
|  |


[Page contains 1 image(s)]


---
## Page 82
---


R-CNN
Forward each region
Conv
through ConvNet
Conv Net
(ImageNet-pretranied)
Net
Conv
Net Warped image regions
(224x224 pixels)
Regions of Interest
(RoI) from a proposal
method(~2k)
Girshicket al, “Rich feature hierarchies for accurate object detection and semantic
Input image segmentation”, CVPR 2014.
Figure copyright Ross Girshick, 2015; source. Reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 9 - 82 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| R-CNN
Forward each region
Conv
through ConvNet
Conv Net
(ImageNet-pretranied)
Net
Conv
Net Warped image regions
(224x224 pixels)
Regions of Interest
(RoI) from a proposal
method(~2k)
Girshicket al, “Rich feature hierarchies for accurate object detection and semantic
Input image segmentation”, CVPR 2014.
Figure copyright Ross Girshick, 2015; source. Reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 9 - 82 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 83
---


R-CNN
SVMs Classify regions with
SVMs
SVMs
SVMs
Forward each region
Conv
through ConvNet
Conv Net
(ImageNet-pretranied)
Net
Conv
Net Warped image regions
(224x224 pixels)
Regions of Interest
(RoI) from a proposal
method(~2k)
Girshicket al, “Rich feature hierarchies for accurate object detection and semantic
Input image segmentation”, CVPR 2014.
Figure copyright Ross Girshick, 2015; source. Reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 9 - 83 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| R-CNN
SVMs Classify regions with
SVMs
SVMs
SVMs
Forward each region
Conv
through ConvNet
Conv Net
(ImageNet-pretranied)
Net
Conv
Net Warped image regions
(224x224 pixels)
Regions of Interest
(RoI) from a proposal
method(~2k)
Girshicket al, “Rich feature hierarchies for accurate object detection and semantic
Input image segmentation”, CVPR 2014.
Figure copyright Ross Girshick, 2015; source. Reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 9 - 83 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 84
---


Predict “corrections” to the RoI: 4 numbers: (dx, dy, dw, dh)
R-CNN
Bboxreg SVMs Classify regions with
SVMs
Bboxreg SVMs
Bboxreg SVMs
Forward each region
Conv
through ConvNet
Conv Net
(ImageNet-
Net
Conv pretranied)
Net Warped image regions
(224x224 pixels)
Regions of Interest
(RoI) from a proposal
method(~2k)
Girshicket al, “Rich feature hierarchies for accurate object detection and semantic
Input image segmentation”, CVPR 2014.
Figure copyright Ross Girshick, 2015; source. Reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 9 - 84 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| Predict “corrections” to the RoI: 4 numbers: (dx, dy, dw, dh)
R-CNN
Bboxreg SVMs Classify regions with
SVMs
Bboxreg SVMs
Bboxreg SVMs
Forward each region
Conv
through ConvNet
Conv Net
(ImageNet-
Net
Conv pretranied)
Net Warped image regions
(224x224 pixels)
Regions of Interest
(RoI) from a proposal
method(~2k)
Girshicket al, “Rich feature hierarchies for accurate object detection and semantic
Input image segmentation”, CVPR 2014.
Figure copyright Ross Girshick, 2015; source. Reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 9 - 84 April 29, 2025 |


### Table 2

| Bboxreg | SVMs |


[Page contains 1 image(s)]


---
## Page 85
---


Predict “corrections” to the RoI: 4 numbers: (dx, dy, dw, dh)
R-CNN
Bboxreg SVMs Classify regions with
Problem: Very slow!
SVMs
Bboxreg SVMs Need to do ~2k
independent forward
Bboxreg SVMs
Forward each
Conv passes for each image!
region through
Conv Net
ConvNet
Net
Conv
Net Warped image regions
(224x224 pixels)
Regions of Interest
(RoI) from a proposal
method(~2k)
Girshicket al, “Rich feature hierarchies for accurate object detection and semantic
Input image segmentation”, CVPR 2014.
Figure copyright Ross Girshick, 2015; source. Reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 9 - 85 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| Predict “corrections” to the RoI: 4 numbers: (dx, dy, dw, dh)
R-CNN
Bboxreg SVMs Classify regions with
Problem: Very slow!
SVMs
Bboxreg SVMs Need to do ~2k
independent forward
Bboxreg SVMs
Forward each
Conv passes for each image!
region through
Conv Net
ConvNet
Net
Conv
Net Warped image regions
(224x224 pixels)
Regions of Interest
(RoI) from a proposal
method(~2k)
Girshicket al, “Rich feature hierarchies for accurate object detection and semantic
Input image segmentation”, CVPR 2014.
Figure copyright Ross Girshick, 2015; source. Reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 9 - 85 April 29, 2025 |


### Table 2

| Bboxreg | SVMs |


[Page contains 1 image(s)]


---
## Page 86
---


Predict “corrections” to the RoI: 4 numbers: (dx, dy, dw, dh)
“Slow” R-CNN
Bboxreg SVMs Classify regions with
Problem: Very slow!
SVMs
Bboxreg SVMs Need to do ~2k
independent forward
Bboxreg SVMs
Forward each
Conv passes for each image!
region through
Conv Net
ConvNet
Net Idea: Pass the image
Conv
through convnet
Net Warped image regions
before cropping! Crop
(224x224 pixels)
the conv feature
Regions of Interest
instead!
(RoI) from a proposal
method(~2k)
Girshicket al, “Rich feature hierarchies for accurate object detection and semantic
Input image segmentation”, CVPR 2014.
Figure copyright Ross Girshick, 2015; source. Reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 9 - 86 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| Predict “corrections” to the RoI: 4 numbers: (dx, dy, dw, dh)
“Slow” R-CNN
Bboxreg SVMs Classify regions with
Problem: Very slow!
SVMs
Bboxreg SVMs Need to do ~2k
independent forward
Bboxreg SVMs
Forward each
Conv passes for each image!
region through
Conv Net
ConvNet
Net Idea: Pass the image
Conv
through convnet
Net Warped image regions
before cropping! Crop
(224x224 pixels)
the conv feature
Regions of Interest
instead!
(RoI) from a proposal
method(~2k)
Girshicket al, “Rich feature hierarchies for accurate object detection and semantic
Input image segmentation”, CVPR 2014.
Figure copyright Ross Girshick, 2015; source. Reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 9 - 86 April 29, 2025 |


### Table 2

| Bboxreg | SVMs |


[Page contains 1 image(s)]


---
## Page 87
---


Fast R-CNN
“Slow” R-CNN
Input image
Girshick, “Fast R-CNN”, ICCV 2015. Figure copyright Ross Girshick, 2015; source. Reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 9 - 87 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Fast R-CNN
“Slow” R-CNN
Input image
Girshick, “Fast R-CNN”, ICCV 2015. Figure copyright Ross Girshick, 2015; source. Reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 9 - 87 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 88
---


Fast R-CNN
“Slow” R-CNN
“conv5”
features
Run whole image
“Backbone”
through ConvNet
network:
ConvNet
AlexNet, VGG,
ResNet, etc
Input image
Girshick, “Fast R-CNN”, ICCV 2015. Figure copyright Ross Girshick, 2015; source. Reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 9 - 88 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Fast R-CNN
“Slow” R-CNN
“conv5”
features
Run whole image
“Backbone”
through ConvNet
network:
ConvNet
AlexNet, VGG,
ResNet, etc
Input image
Girshick, “Fast R-CNN”, ICCV 2015. Figure copyright Ross Girshick, 2015; source. Reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 9 - 88 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 89
---


Fast R-CNN
“Slow” R-CNN
Regions of
Interest (RoIs)
from a proposal
method “conv5”
features
Run whole image
“Backbone”
through ConvNet
network:
ConvNet
AlexNet, VGG,
ResNet, etc
Input image
Girshick, “Fast R-CNN”, ICCV 2015. Figure copyright Ross Girshick, 2015; source. Reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 9 - 89 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Fast R-CNN
“Slow” R-CNN
Regions of
Interest (RoIs)
from a proposal
method “conv5”
features
Run whole image
“Backbone”
through ConvNet
network:
ConvNet
AlexNet, VGG,
ResNet, etc
Input image
Girshick, “Fast R-CNN”, ICCV 2015. Figure copyright Ross Girshick, 2015; source. Reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 9 - 89 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 90
---


Fast R-CNN
“Slow” R-CNN
Regions of
Interest (RoIs)
Crop + Resize features
from a proposal
method “conv5” features
Run whole image
“Backbone”
through ConvNet
network:
ConvNet
AlexNet, VGG,
ResNet, etc
Input image
Girshick, “Fast R-CNN”, ICCV 2015. Figure copyright Ross Girshick, 2015; source. Reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 9 - 90 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Fast R-CNN
“Slow” R-CNN
Regions of
Interest (RoIs)
Crop + Resize features
from a proposal
method “conv5” features
Run whole image
“Backbone”
through ConvNet
network:
ConvNet
AlexNet, VGG,
ResNet, etc
Input image
Girshick, “Fast R-CNN”, ICCV 2015. Figure copyright Ross Girshick, 2015; source. Reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 9 - 90 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 91
---


Fast R-CNN
Object Linear +
category softmax Linear Box offset
“Slow” R-CNN
Regions of CNN Per-Region Network
Interest (RoIs)
Crop + Resize features
from a proposal
method “conv5” features
Run whole image
“Backbone”
through ConvNet
network:
ConvNet
AlexNet, VGG,
ResNet, etc
Input image
Girshick, “Fast R-CNN”, ICCV 2015. Figure copyright Ross Girshick, 2015; source. Reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 9 - 91 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Fast R-CNN
Object Linear +
category softmax Linear Box offset
“Slow” R-CNN
Regions of CNN Per-Region Network
Interest (RoIs)
Crop + Resize features
from a proposal
method “conv5” features
Run whole image
“Backbone”
through ConvNet
network:
ConvNet
AlexNet, VGG,
ResNet, etc
Input image
Girshick, “Fast R-CNN”, ICCV 2015. Figure copyright Ross Girshick, 2015; source. Reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 9 - 91 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 92
---


Fast R-CNN
Object Linear +
category softmax Linear Box offset
“Slow” R-CNN
Regions of CNN Per-Region Network
Interest (RoIs)
Crop + Resize features
from a proposal
method “conv5” features
Run whole image
“Backbone”
through ConvNet
network:
ConvNet
AlexNet, VGG,
ResNet, etc
Input image
Girshick, “Fast R-CNN”, ICCV 2015. Figure copyright Ross Girshick, 2015; source. Reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 9 - 92 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Fast R-CNN
Object Linear +
category softmax Linear Box offset
“Slow” R-CNN
Regions of CNN Per-Region Network
Interest (RoIs)
Crop + Resize features
from a proposal
method “conv5” features
Run whole image
“Backbone”
through ConvNet
network:
ConvNet
AlexNet, VGG,
ResNet, etc
Input image
Girshick, “Fast R-CNN”, ICCV 2015. Figure copyright Ross Girshick, 2015; source. Reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 9 - 92 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 93
---


Region Proposal Network
CNN
Input Image
(e.g. 3 x 640 x 480) Image features
(e.g. 512 x 20 x 15)
Stanford CS231n 10th Anniversary Lecture 9 - 93 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| Region Proposal Network
CNN
Input Image
(e.g. 3 x 640 x 480) Image features
(e.g. 512 x 20 x 15) |
| Stanford CS231n 10th Anniversary Lecture 9 - 93 April 29, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |


[Page contains 2 image(s)]


---
## Page 94
---


Region Proposal Network Imagine an anchor box of
fixed size at each point in
the feature map
CNN
Input Image
(e.g. 3 x 640 x 480) Image features
(e.g. 512 x 20 x 15)
Stanford CS231n 10th Anniversary Lecture 9 - 94 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| Region Proposal Network Imagine an anchor box of
fixed size at each point in
the feature map
CNN
Input Image
(e.g. 3 x 640 x 480) Image features
(e.g. 512 x 20 x 15) |
| Stanford CS231n 10th Anniversary Lecture 9 - 94 April 29, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| N |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |


[Page contains 2 image(s)]


---
## Page 95
---


Region Proposal Network Imagine an anchor box of
fixed size at each point in
the feature map
Anchor is an object?
1 x 20 x 15
CNN Conv
At each point, predict whether
Input Image
the corresponding anchor
(e.g. 3 x 640 x 480) Image features
contains an object (binary
(e.g. 512 x 20 x 15)
classification)
Stanford CS231n 10th Anniversary Lecture 9 - 95 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| Region Proposal Network Imagine an anchor box of
fixed size at each point in
the feature map
Anchor is an object?
1 x 20 x 15
CNN Conv
At each point, predict whether
Input Image
the corresponding anchor
(e.g. 3 x 640 x 480) Image features
contains an object (binary
(e.g. 512 x 20 x 15)
classification) |
| Stanford CS231n 10th Anniversary Lecture 9 - 95 April 29, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| N |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |


[Page contains 2 image(s)]


---
## Page 96
---


Region Proposal Network Imagine an anchor box of
fixed size at each point in
the feature map
Anchor is an object?
1 x 20 x 15
CNN Conv
Box corrections
4 x 20 x 15
For positive boxes, also predict a
Input Image
corrections from the anchor to
(e.g. 3 x 640 x 480) Image features
the ground-truth box (regress 4
(e.g. 512 x 20 x 15)
numbers per pixel)
Stanford CS231n 10th Anniversary Lecture 9 - 96 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| Region Proposal Network Imagine an anchor box of
fixed size at each point in
the feature map
Anchor is an object?
1 x 20 x 15
CNN Conv
Box corrections
4 x 20 x 15
For positive boxes, also predict a
Input Image
corrections from the anchor to
(e.g. 3 x 640 x 480) Image features
the ground-truth box (regress 4
(e.g. 512 x 20 x 15)
numbers per pixel) |
| Stanford CS231n 10th Anniversary Lecture 9 - 96 April 29, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |


[Page contains 2 image(s)]


---
## Page 97
---


In practice use K different
Region Proposal Network
anchor boxes of different
size / scale at each point
Anchor is an object?
K x 20 x 15
CNN Conv
Box transforms
4K x 20 x 15
Input Image
(e.g. 3 x 640 x 480) Image features
(e.g. 512 x 20 x 15)
Stanford CS231n 10th Anniversary Lecture 9 - 97 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| In practice use K different
Region Proposal Network
anchor boxes of different
size / scale at each point
Anchor is an object?
K x 20 x 15
CNN Conv
Box transforms
4K x 20 x 15
Input Image
(e.g. 3 x 640 x 480) Image features
(e.g. 512 x 20 x 15) |
| Stanford CS231n 10th Anniversary Lecture 9 - 97 April 29, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |


[Page contains 2 image(s)]


---
## Page 98
---


In practice use K different
Region Proposal Network
anchor boxes of different
size / scale at each point
Anchor is an object?
K x 20 x 15
CNN Conv
Box transforms
4K x 20 x 15
Sort the K*20*15 boxes by
their “objectness” score, take
Input Image
top ~300 as our proposals
(e.g. 3 x 640 x 480) Image features
(e.g. 512 x 20 x 15)
Stanford CS231n 10th Anniversary Lecture 9 - 98 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| In practice use K different
Region Proposal Network
anchor boxes of different
size / scale at each point
Anchor is an object?
K x 20 x 15
CNN Conv
Box transforms
4K x 20 x 15
Sort the K*20*15 boxes by
their “objectness” score, take
Input Image
top ~300 as our proposals
(e.g. 3 x 640 x 480) Image features
(e.g. 512 x 20 x 15) |
| Stanford CS231n 10th Anniversary Lecture 9 - 98 April 29, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |


[Page contains 2 image(s)]


---
## Page 99
---


Single-Stage Object Detectors: YOLO / SSD / RetinaNet
Within each grid cell:
- Regress from each of the B
base boxes to a final box with
5 numbers:
(dx, dy, dh, dw, confidence)
- Predict scores for each of C
classes (including
background as a class)
- Looks a lot like RPN, but
category-specific!
Input image Divide image into grid
3 x H x W 7 x 7
Output:
Image a set of base boxes
Redmon et al, “You Only Look Once: 7 x 7 x (5 * B + C)
centered at each grid cell
Unified, Real-Time Object Detection”, CVPR 2016
Liu et al, “SSD: Single-Shot MultiBoxDetector”, ECCV 2016 Here B = 3
Lin et al, “Focal Loss for Dense Object Detection”, ICCV 2017
Stanford CS231n 10th Anniversary Lecture 9 - 99 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| Single-Stage Object Detectors: YOLO / SSD / RetinaNet
Within each grid cell:
- Regress from each of the B
base boxes to a final box with
5 numbers:
(dx, dy, dh, dw, confidence)
- Predict scores for each of C
classes (including
background as a class)
- Looks a lot like RPN, but
category-specific!
Input image Divide image into grid
3 x H x W 7 x 7
Output:
Image a set of base boxes
Redmon et al, “You Only Look Once: 7 x 7 x (5 * B + C)
centered at each grid cell
Unified, Real-Time Object Detection”, CVPR 2016
Liu et al, “SSD: Single-Shot MultiBoxDetector”, ECCV 2016 Here B = 3
Lin et al, “Focal Loss for Dense Object Detection”, ICCV 2017 |
| Stanford CS231n 10th Anniversary Lecture 9 - 99 April 29, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |


[Page contains 2 image(s)]


---
## Page 100
---


YOLO (You Only Look Once)
real-time object detection
Redmon et al. "You only look once: unified, real-time object detection (2015)."
Stanford CS231n 10th Anniversary Lecture 9 - 100 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| YOLO (You Only Look Once)
real-time object detection
Redmon et al. "You only look once: unified, real-time object detection (2015)." |
| Stanford CS231n 10th Anniversary Lecture 9 - 100 April 29, 2025 |


### Table 2

| Redmon et al. "You only look once: unified, real | - | time object detection (2015)." |


[Page contains 1 image(s)]


---
## Page 101
---


YOLO
SxS Grid
Redmon et al. "You only look once: unified, real-time object detection (2015)."
Stanford CS231n 10th Anniversary Lecture 9 - 101 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| YOLO
SxS Grid
Redmon et al. "You only look once: unified, real-time object detection (2015)." |
| Stanford CS231n 10th Anniversary Lecture 9 - 101 April 29, 2025 |


### Table 2

| Redmon et al. "You only look once: unified, real | - | time object detection (2015)." |


[Page contains 1 image(s)]


---
## Page 102
---


YOLO
For each box output:
• P(object): probability that the box contains an object
• B bounding boxes (x, y, h, w)
• P(class): probability of belonging to a class
SxSGrid
Redmon et al. "You only look once: unified, real-time object detection (2015)."
Stanford CS231n 10th Anniversary Lecture 9 - 102 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| YOLO
For each box output:
• P(object): probability that the box contains an object
• B bounding boxes (x, y, h, w)
• P(class): probability of belonging to a class
SxSGrid
Redmon et al. "You only look once: unified, real-time object detection (2015)." |
| Stanford CS231n 10th Anniversary Lecture 9 - 102 April 29, 2025 |


### Table 2

| Redmon et al. "You only look once: unified, real | - | time object detection (2015)." |


[Page contains 1 image(s)]


---
## Page 103
---


YOLO
For each box output:
• P(object): probability that the box contains an object
• B bounding boxes (x, y, h, w)
• P(class): probability of belonging to a class
B=2
SxSGrid
Redmon et al. "You only look once: unified, real-time object detection (2015)."
Stanford CS231n 10th Anniversary Lecture 9 - 103 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| YOLO
For each box output:
• P(object): probability that the box contains an object
• B bounding boxes (x, y, h, w)
• P(class): probability of belonging to a class
B=2
SxSGrid
Redmon et al. "You only look once: unified, real-time object detection (2015)." |
| Stanford CS231n 10th Anniversary Lecture 9 - 103 April 29, 2025 |


### Table 2

| Redmon et al. "You only look once: unified, real | - | time object detection (2015)." |


[Page contains 1 image(s)]


---
## Page 104
---


YOLO
For each box output:
• P(object): probability that the box contains an object
• B bounding boxes (x, y, h, w)
• P(class): probability of belonging to a class
B=2
SxSGrid
Redmon et al. "You only look once: unified, real-time object detection (2015)."
Stanford CS231n 10th Anniversary Lecture 9 - 104 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| YOLO
For each box output:
• P(object): probability that the box contains an object
• B bounding boxes (x, y, h, w)
• P(class): probability of belonging to a class
B=2
SxSGrid
Redmon et al. "You only look once: unified, real-time object detection (2015)." |
| Stanford CS231n 10th Anniversary Lecture 9 - 104 April 29, 2025 |


### Table 2

| Redmon et al. "You only look once: unified, real | - | time object detection (2015)." |


[Page contains 1 image(s)]


---
## Page 105
---


YOLO
Many bounding boxes with
different object probabilities
SxS Grid
Redmon et al. "You only look once: unified, real-time object detection (2015)."
Stanford CS231n 10th Anniversary Lecture 9 - 105 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| YOLO
Many bounding boxes with
different object probabilities
SxS Grid
Redmon et al. "You only look once: unified, real-time object detection (2015)." |
| Stanford CS231n 10th Anniversary Lecture 9 - 105 April 29, 2025 |


### Table 2

| Redmon et al. "You only look once: unified, real | - | time object detection (2015)." |


[Page contains 1 image(s)]


---
## Page 106
---


YOLO
SxS Grid
Redmon et al. "You only look once: unified, real-time object detection (2015)."
Stanford CS231n 10th Anniversary Lecture 9 - 106 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| YOLO
SxS Grid
Redmon et al. "You only look once: unified, real-time object detection (2015)." |
| Stanford CS231n 10th Anniversary Lecture 9 - 106 April 29, 2025 |


### Table 2

| Redmon et al. "You only look once: unified, real | - | time object detection (2015)." |


[Page contains 1 image(s)]


---
## Page 107
---


Object Detection with Transformers: DETR
Simple object detection pipeline: directly output a set of boxes from a Transformer
No anchors, no regression of box transforms
Match predicted boxes to GT boxes with bipartite matching; train to regress box coordinates
Carionet al, “End-to-End Object Detection with Transformers”, ECCV 2020
Stanford CS231n 10th Anniversary Lecture 9 - 107 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Object Detection with Transformers: DETR
Simple object detection pipeline: directly output a set of boxes from a Transformer
No anchors, no regression of box transforms
Match predicted boxes to GT boxes with bipartite matching; train to regress box coordinates
Carionet al, “End-to-End Object Detection with Transformers”, ECCV 2020 |
| Stanford CS231n 10th Anniversary Lecture 9 - 107 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 108
---


Object Detection with Transformers: DETR
Carionet al, “End-to-End Object Detection with Transformers”, ECCV 2020
Stanford CS231n 10th Anniversary Lecture 9 - 108 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Object Detection with Transformers: DETR
Carionet al, “End-to-End Object Detection with Transformers”, ECCV 2020 |
| Stanford CS231n 10th Anniversary Lecture 9 - 108 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 109
---


Object Detection with Transformers: DETR
Carionet al, “End-to-End Object Detection with Transformers”, ECCV 2020
Stanford CS231n 10th Anniversary Lecture 9 - 109 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Object Detection with Transformers: DETR
Carionet al, “End-to-End Object Detection with Transformers”, ECCV 2020 |
| Stanford CS231n 10th Anniversary Lecture 9 - 109 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 110
---


Object Detection with Transformers: DETR
Carionet al, “End-to-End Object Detection with Transformers”, ECCV 2020
Stanford CS231n 10th Anniversary Lecture 9 - 110 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Object Detection with Transformers: DETR
Carionet al, “End-to-End Object Detection with Transformers”, ECCV 2020 |
| Stanford CS231n 10th Anniversary Lecture 9 - 110 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 111
---


Object Detection with Transformers: DETR
Carionet al, “End-to-End Object Detection with Transformers”, ECCV 2020
Stanford CS231n 10th Anniversary Lecture 9 - 111 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Object Detection with Transformers: DETR
Carionet al, “End-to-End Object Detection with Transformers”, ECCV 2020 |
| Stanford CS231n 10th Anniversary Lecture 9 - 111 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 112
---


Object Detection with Transformers: DETR
Carionet al, “End-to-End Object Detection with Transformers”, ECCV 2020
Stanford CS231n 10th Anniversary Lecture 9 - 112 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Object Detection with Transformers: DETR
Carionet al, “End-to-End Object Detection with Transformers”, ECCV 2020 |
| Stanford CS231n 10th Anniversary Lecture 9 - 112 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 113
---


Instance Segmentation
Semantic Instance
Object
Classification
Segmentation Segmentation
Detection
GRASS, CAT, TREE,
CAT DOG, DOG, CAT DOG, DOG, CAT
SKY
Multiple Object
No spatial extent No objects, just pixels
Stanford CS231n 10th Anniversary Lecture 9 - 113 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| Instance Segmentation
Semantic Instance
Object
Classification
Segmentation Segmentation
Detection
GRASS, CAT, TREE,
CAT DOG, DOG, CAT DOG, DOG, CAT
SKY
Multiple Object
No spatial extent No objects, just pixels |
| Stanford CS231n 10th Anniversary Lecture 9 - 113 April 29, 2025 |


### Table 2

| Semantic
Classification
Segmentation
GRASS, CAT, TREE,
CAT
SKY
No spatial extent No objects, just pixels | Object
Detection
DOG, DOG, CAT |


[Page contains 4 image(s)]


---
## Page 114
---


Object Detection:
Faster R-CNN
Stanford CS231n 10th Anniversary Lecture 9 - 114 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Object Detection:
Faster R-CNN |
| Stanford CS231n 10th Anniversary Lecture 9 - 114 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 115
---


Instance Segmentation:
Mask Prediction
Mask R-CNN
Add a small mask
network that operates
on each RoI and
predicts a 28x28 binary
mask
He et al, “Mask R-CNN”, ICCV 2017
Stanford CS231n 10th Anniversary Lecture 9 - 115 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Instance Segmentation:
Mask Prediction
Mask R-CNN
Add a small mask
network that operates
on each RoI and
predicts a 28x28 binary
mask
He et al, “Mask R-CNN”, ICCV 2017 |
| Stanford CS231n 10th Anniversary Lecture 9 - 115 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 116
---


Mask R-CNN
Classification Scores: C
Box coordinates (per class): 4 * C
CNN
+RPN RoIAlign
256 x 14 x 14
He et al, “Mask R-CNN”, arXiv2017
Stanford CS231n 10th Anniversary Lecture 9 - 116 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Mask R-CNN
Classification Scores: C
Box coordinates (per class): 4 * C
CNN
+RPN RoIAlign
256 x 14 x 14
He et al, “Mask R-CNN”, arXiv2017 |
| Stanford CS231n 10th Anniversary Lecture 9 - 116 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 117
---


Mask R-CNN
Classification Scores: C
Box coordinates (per class): 4 * C
CNN
Conv Conv
+RPN RoIAlign
256 x 14 x 14 256 x 14 x 14 Predict a mask for
each of C classes
C x 28 x 28
He et al, “Mask R-CNN”, arXiv2017
Stanford CS231n 10th Anniversary Lecture 9 - 117 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| Mask R-CNN
Classification Scores: C
Box coordinates (per class): 4 * C
CNN
Conv Conv
+RPN RoIAlign
256 x 14 x 14 256 x 14 x 14 Predict a mask for
each of C classes
C x 28 x 28
He et al, “Mask R-CNN”, arXiv2017 |
| Stanford CS231n 10th Anniversary Lecture 9 - 117 April 29, 2025 |


### Table 2

|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |


[Page contains 1 image(s)]


---
## Page 118
---


Mask R-CNN: Example Mask Training Targets
Stanford CS231n 10th Anniversary Lecture 9 - 118 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Mask R-CNN: Example Mask Training Targets |
| Stanford CS231n 10th Anniversary Lecture 9 - 118 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 119
---


Mask R-CNN: Example Mask Training Targets
Stanford CS231n 10th Anniversary Lecture 9 - 119 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Mask R-CNN: Example Mask Training Targets |
| Stanford CS231n 10th Anniversary Lecture 9 - 119 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 120
---


Mask R-CNN: Example Mask Training Targets
Stanford CS231n 10th Anniversary Lecture 9 - 120 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Mask R-CNN: Example Mask Training Targets |
| Stanford CS231n 10th Anniversary Lecture 9 - 120 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 121
---


Mask R-CNN: Example Mask Training Targets
Stanford CS231n 10th Anniversary Lecture 9 - 121 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Mask R-CNN: Example Mask Training Targets |
| Stanford CS231n 10th Anniversary Lecture 9 - 121 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 122
---


Mask R-CNN: Very Good Results!
He et al, “Mask R-CNN”, ICCV 2017
Stanford CS231n 10th Anniversary Lecture 9 - 122 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Mask R-CNN: Very Good Results!
He et al, “Mask R-CNN”, ICCV 2017 |
| Stanford CS231n 10th Anniversary Lecture 9 - 122 April 29, 2025 |


[Page contains 3 image(s)]


---
## Page 123
---


Mask R-CNN
Also does pose
He et al, “Mask R-CNN”, ICCV 2017
Stanford CS231n 10th Anniversary Lecture 9 - 123 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Mask R-CNN
Also does pose
He et al, “Mask R-CNN”, ICCV 2017 |
| Stanford CS231n 10th Anniversary Lecture 9 - 123 April 29, 2025 |


[Page contains 3 image(s)]


---
## Page 124
---


Open Source Frameworks
Lots of good implementations on GitHub!
TensorFlow Detection API:
https://github.com/tensorflow/models/tree/master/research/object_detection
Faster RCNN, SSD, RFCN, Mask R-CNN, ...
Detectron2 (PyTorch)
https://github.com/facebookresearch/detectron2
Mask R-CNN, RetinaNet, Faster R-CNN, RPN, Fast R-CNN, R-FCN, ...
Finetune on your own dataset with pre-trained models
Stanford CS231n 10th Anniversary Lecture 9 - 124 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Open Source Frameworks
Lots of good implementations on GitHub!
TensorFlow Detection API:
https://github.com/tensorflow/models/tree/master/research/object_detection
Faster RCNN, SSD, RFCN, Mask R-CNN, ...
Detectron2 (PyTorch)
https://github.com/facebookresearch/detectron2
Mask R-CNN, RetinaNet, Faster R-CNN, RPN, Fast R-CNN, R-FCN, ...
Finetune on your own dataset with pre-trained models |
| Stanford CS231n 10th Anniversary Lecture 9 - 124 April 29, 2025 |


---
## Page 125
---


Recap: Lots of computer vision tasks!
Semantic Instance
Object
Classification
Segmentation Segmentation
Detection
GRASS, CAT, TREE,
CAT DOG, DOG, CAT DOG, DOG, CAT
SKY
Multiple Object
No spatial extent No objects, just pixels
This imageis CC0 public domain
Stanford CS231n 10th Anniversary Lecture 9 - 125 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Recap: Lots of computer vision tasks!
Semantic Instance
Object
Classification
Segmentation Segmentation
Detection
GRASS, CAT, TREE,
CAT DOG, DOG, CAT DOG, DOG, CAT
SKY
Multiple Object
No spatial extent No objects, just pixels
This imageis CC0 public domain |
| Stanford CS231n 10th Anniversary Lecture 9 - 125 April 29, 2025 |


[Page contains 4 image(s)]


---
## Page 126
---


Today
● Transformers Recap
● Computer Vision Tasks
○ Semantic Segmentation
○ Object Detection
○ Instance Segmentation
● Visualization & Understanding
○ Model Layers Visualization
○ Saliency Maps
○ CAM & Grad-CAM
Stanford CS231n 10th Anniversary Lecture 9 - 126 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Today
● Transformers Recap
● Computer Vision Tasks
○ Semantic Segmentation
○ Object Detection
○ Instance Segmentation
● Visualization & Understanding
○ Model Layers Visualization
○ Saliency Maps
○ CAM & Grad-CAM |
| Stanford CS231n 10th Anniversary Lecture 9 - 126 April 29, 2025 |


---
## Page 127
---


Interpreting a Linear Classifier: Visual Viewpoint
Stanford CS231n 10th Anniversary Lecture 9 - 127 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Interpreting a Linear Classifier: Visual Viewpoint |
| Stanford CS231n 10th Anniversary Lecture 9 - 127 April 29, 2025 |


[Page contains 3 image(s)]


---
## Page 128
---


First Layer: Visualize Filters
AlexNet:
64 x 3 x 11 x 11
Krizhevsky, “One weird trick for parallelizing convolutional neural networks”, arXiv2014
He et al, “Deep Residual Learning for Image Recognition”, CVPR 2016
Huang et al, “Densely Connected Convolutional Networks”, CVPR 2017
Stanford CS231n 10th Anniversary Lecture 9 - 128 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| First Layer: Visualize Filters
AlexNet:
64 x 3 x 11 x 11
Krizhevsky, “One weird trick for parallelizing convolutional neural networks”, arXiv2014
He et al, “Deep Residual Learning for Image Recognition”, CVPR 2016
Huang et al, “Densely Connected Convolutional Networks”, CVPR 2017 |
| Stanford CS231n 10th Anniversary Lecture 9 - 128 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 129
---


First Layer: Visualize Filters
ResNet-18: ResNet-101: DenseNet-121:
64 x 3 x 7 x 7 64 x 3 x 7 x 7 64 x 3 x 7 x 7
AlexNet:
64 x 3 x 11 x 11
Krizhevsky, “One weird trick for parallelizing convolutional neural networks”, arXiv2014
He et al, “Deep Residual Learning for Image Recognition”, CVPR 2016
Huang et al, “Densely Connected Convolutional Networks”, CVPR 2017
Stanford CS231n 10th Anniversary Lecture 9 - 129 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| First Layer: Visualize Filters
ResNet-18: ResNet-101: DenseNet-121:
64 x 3 x 7 x 7 64 x 3 x 7 x 7 64 x 3 x 7 x 7
AlexNet:
64 x 3 x 11 x 11
Krizhevsky, “One weird trick for parallelizing convolutional neural networks”, arXiv2014
He et al, “Deep Residual Learning for Image Recognition”, CVPR 2016
Huang et al, “Densely Connected Convolutional Networks”, CVPR 2017 |
| Stanford CS231n 10th Anniversary Lecture 9 - 129 April 29, 2025 |


[Page contains 5 image(s)]


---
## Page 130
---


Which pixels matter: Saliency via Backprop
Forward pass: Compute probabilities
Dog
Simonyan, Vedaldi, and Zisserman, “Deep Inside Convolutional Networks: VisualisingImage Classification Models and
Saliency Maps”, ICLR Workshop 2014.
Figures copyright Karen Simonyan, Andrea Vedaldi, and Andrew Zisserman, 2014; reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 9 - 130 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Which pixels matter: Saliency via Backprop
Forward pass: Compute probabilities
Dog
Simonyan, Vedaldi, and Zisserman, “Deep Inside Convolutional Networks: VisualisingImage Classification Models and
Saliency Maps”, ICLR Workshop 2014.
Figures copyright Karen Simonyan, Andrea Vedaldi, and Andrew Zisserman, 2014; reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 9 - 130 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 131
---


Which pixels matter: Saliency via Backprop
Forward pass: Compute probabilities
Dog
Compute gradient of (unnormalized) class score
with respect to image pixels, take absolute value
and max over RGB channels
Simonyan, Vedaldi, and Zisserman, “Deep Inside Convolutional Networks: VisualisingImage Classification Models and
Saliency Maps”, ICLR Workshop 2014.
Figures copyright Karen Simonyan, Andrea Vedaldi, and Andrew Zisserman, 2014; reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 9 - 131 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Which pixels matter: Saliency via Backprop
Forward pass: Compute probabilities
Dog
Compute gradient of (unnormalized) class score
with respect to image pixels, take absolute value
and max over RGB channels
Simonyan, Vedaldi, and Zisserman, “Deep Inside Convolutional Networks: VisualisingImage Classification Models and
Saliency Maps”, ICLR Workshop 2014.
Figures copyright Karen Simonyan, Andrea Vedaldi, and Andrew Zisserman, 2014; reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 9 - 131 April 29, 2025 |


[Page contains 3 image(s)]


---
## Page 132
---


Saliency Maps
Simonyan, Vedaldi, and Zisserman, “Deep Inside Convolutional Networks: VisualisingImage Classification Models and
Saliency Maps”, ICLR Workshop 2014.
Figures copyright Karen Simonyan, Andrea Vedaldi, and Andrew Zisserman, 2014; reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 9 - 132 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Saliency Maps
Simonyan, Vedaldi, and Zisserman, “Deep Inside Convolutional Networks: VisualisingImage Classification Models and
Saliency Maps”, ICLR Workshop 2014.
Figures copyright Karen Simonyan, Andrea Vedaldi, and Andrew Zisserman, 2014; reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 9 - 132 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 133
---


Class Activation Mapping (CAM)
Global Fully Connected
Average Layer, weights
𝐾×𝐶
Pooling 𝑤 ∈ ℝ
H K C
K
W
Last layer CNN features: Pooled features: Class Scores:
𝑓 ∈ ℝ 𝐻×𝑊×𝐾 𝐹 ∈ ℝ 𝐾 𝑆 ∈ ℝ 𝐶
Zhou et al, “Learning Deep Features for Discriminative Localization”, CVPR 2016
Stanford CS231n 10th Anniversary Lecture 9 - 133 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Class Activation Mapping (CAM)
Global Fully Connected
Average Layer, weights
𝐾×𝐶
Pooling 𝑤 ∈ ℝ
H K C
K
W
Last layer CNN features: Pooled features: Class Scores:
𝑓 ∈ ℝ 𝐻×𝑊×𝐾 𝐹 ∈ ℝ 𝐾 𝑆 ∈ ℝ 𝐶
Zhou et al, “Learning Deep Features for Discriminative Localization”, CVPR 2016 |
| Stanford CS231n 10th Anniversary Lecture 9 - 133 April 29, 2025 |


---
## Page 134
---


Class Activation Mapping (CAM)
Global Fully Connected
Average Layer, weights
𝐾×𝐶
Pooling 𝑤 ∈ ℝ
H K C
K
W
Last layer CNN features: Pooled features: Class Scores:
𝑓 ∈ ℝ 𝐻×𝑊×𝐾 𝐹 ∈ ℝ 𝐾 𝑆 ∈ ℝ 𝐶
1
𝐹 = ෍ 𝑓
𝑘 ℎ,𝑤,𝑘
𝐻𝑊
ℎ,𝑤
Zhou et al, “Learning Deep Features for Discriminative Localization”, CVPR 2016
Stanford CS231n 10th Anniversary Lecture 9 - 134 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Class Activation Mapping (CAM)
Global Fully Connected
Average Layer, weights
𝐾×𝐶
Pooling 𝑤 ∈ ℝ
H K C
K
W
Last layer CNN features: Pooled features: Class Scores:
𝑓 ∈ ℝ 𝐻×𝑊×𝐾 𝐹 ∈ ℝ 𝐾 𝑆 ∈ ℝ 𝐶
1
𝐹 = ෍ 𝑓
𝑘 ℎ,𝑤,𝑘
𝐻𝑊
ℎ,𝑤
Zhou et al, “Learning Deep Features for Discriminative Localization”, CVPR 2016 |  |  |
| Last layer CNN fea
𝐻×𝑊×𝐾
𝑓 ∈ ℝ
1
𝐹 = ෍ 𝑓
𝑘 ℎ,𝑤,𝑘
𝐻𝑊
ℎ,𝑤
Zhou et al, “Learning Deep Features for D | Last layer CNN fea
𝐻×𝑊×𝐾
𝑓 ∈ ℝ | tures: |
| Stanford CS231n 10 |  | th Anniversary Lecture 9 - 134 April 29, 2025 |
|  |  |  |


---
## Page 135
---


Class Activation Mapping (CAM)
Global Fully Connected
Average Layer, weights
𝐾×𝐶
Pooling 𝑤 ∈ ℝ
H K C
K
W
Last layer CNN features: Pooled features: Class Scores:
𝑓 ∈ ℝ 𝐻×𝑊×𝐾 𝐹 ∈ ℝ 𝐾 𝑆 ∈ ℝ 𝐶
1 1
𝐹 = ෍ 𝑓 𝑆 = ෍ 𝑤 𝐹 = ෍ 𝑤 ෍ 𝑓
𝑘 𝐻𝑊 ℎ,𝑤,𝑘 𝑐 𝑘,𝑐 𝑘 𝐻𝑊 𝑘,𝑐 ℎ,𝑤,𝑘
ℎ,𝑤 𝑘 𝑘 ℎ,𝑤
1
= ෍ ෍ 𝑤 𝑓
𝑘,𝑐 ℎ,𝑤,𝑘
𝐻𝑊
ℎ,𝑤 𝑘
Zhou et al, “Learning Deep Features for Discriminative Localization”, CVPR 2016
Stanford CS231n 10th Anniversary Lecture 9 - 135 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| Class Activation Mapping (CAM)
Global Fully Connected
Average Layer, weights
𝐾×𝐶
Pooling 𝑤 ∈ ℝ
H K C
K
W
Last layer CNN features: Pooled features: Class Scores:
𝑓 ∈ ℝ 𝐻×𝑊×𝐾 𝐹 ∈ ℝ 𝐾 𝑆 ∈ ℝ 𝐶
1 1
𝐹 = ෍ 𝑓 𝑆 = ෍ 𝑤 𝐹 = ෍ 𝑤 ෍ 𝑓
𝑘 𝐻𝑊 ℎ,𝑤,𝑘 𝑐 𝑘,𝑐 𝑘 𝐻𝑊 𝑘,𝑐 ℎ,𝑤,𝑘
ℎ,𝑤 𝑘 𝑘 ℎ,𝑤
1
= ෍ ෍ 𝑤 𝑓
𝑘,𝑐 ℎ,𝑤,𝑘
𝐻𝑊
ℎ,𝑤 𝑘
Zhou et al, “Learning Deep Features for Discriminative Localization”, CVPR 2016 |  |  |  |  |
| Last layer CNN fe
𝐻×𝑊×
𝑓 ∈ ℝ
1
𝐹 = ෍ 𝑓
𝑘 ℎ,𝑤,
𝐻𝑊
ℎ,𝑤
Zhou et al, “Learning Deep Features fo | Last layer CNN fe
𝐻×𝑊×
𝑓 ∈ ℝ | a
𝐾 | tures: |  |
|  |  | 𝑘
r D |  |  |
| Stanford CS231n 1 |  | 0 | th Anniversary Lecture 9 - 1 | 35 April 29, 2025 |
|  |  |  |  |  |


### Table 2

| 1
= ෍ 𝑤 ෍ 𝑓
𝑘,𝑐 ℎ,𝑤,
𝐻𝑊
𝑘 ℎ,𝑤
1 |  |
|  | 1
෍ 𝑤 ෍ 𝑓
𝑘,𝑐 ℎ,𝑤,
𝐻𝑊
𝑘 ℎ,𝑤
1 |


---
## Page 136
---


Class Activation Mapping (CAM)
Global Fully Connected
Average Layer, weights
𝐾×𝐶
Pooling 𝑤 ∈ ℝ
H K C
K
W
Last layer CNN features: Pooled features: Class Scores:
𝑓 ∈ ℝ 𝐻×𝑊×𝐾 𝐹 ∈ ℝ 𝐾 𝑆 ∈ ℝ 𝐶
1 1
𝐹 = ෍ 𝑓 𝑆 = ෍ 𝑤 𝐹 = ෍ 𝑤 ෍ 𝑓
𝑘 𝐻𝑊 ℎ,𝑤,𝑘 𝑐 𝑘,𝑐 𝑘 𝐻𝑊 𝑘,𝑐 ℎ,𝑤,𝑘
ℎ,𝑤 𝑘 𝑘 ℎ,𝑤
1
= ෍ ෍ 𝑤 𝑓
𝑘,𝑐 ℎ,𝑤,𝑘
𝐻𝑊
ℎ,𝑤 𝑘
Zhou et al, “Learning Deep Features for Discriminative Localization”, CVPR 2016
Stanford CS231n 10th Anniversary Lecture 9 - 136 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Class Activation Mapping (CAM)
Global Fully Connected
Average Layer, weights
𝐾×𝐶
Pooling 𝑤 ∈ ℝ
H K C
K
W
Last layer CNN features: Pooled features: Class Scores:
𝑓 ∈ ℝ 𝐻×𝑊×𝐾 𝐹 ∈ ℝ 𝐾 𝑆 ∈ ℝ 𝐶
1 1
𝐹 = ෍ 𝑓 𝑆 = ෍ 𝑤 𝐹 = ෍ 𝑤 ෍ 𝑓
𝑘 𝐻𝑊 ℎ,𝑤,𝑘 𝑐 𝑘,𝑐 𝑘 𝐻𝑊 𝑘,𝑐 ℎ,𝑤,𝑘
ℎ,𝑤 𝑘 𝑘 ℎ,𝑤
1
= ෍ ෍ 𝑤 𝑓
𝑘,𝑐 ℎ,𝑤,𝑘
𝐻𝑊
ℎ,𝑤 𝑘
Zhou et al, “Learning Deep Features for Discriminative Localization”, CVPR 2016 |  |  |  |  |
| Last layer CNN fe
𝐻×𝑊×
𝑓 ∈ ℝ
1
𝐹 = ෍ 𝑓
𝑘 ℎ,𝑤,
𝐻𝑊
ℎ,𝑤
Zhou et al, “Learning Deep Features fo | Last layer CNN fe
𝐻×𝑊×
𝑓 ∈ ℝ | a
𝐾 | tures: |  |
|  |  | 𝑘
r D |  |  |
| Stanford CS231n 1 |  | 0 | th Anniversary Lecture 9 - 1 | 36 April 29, 2025 |
|  |  |  |  |  |


---
## Page 137
---


Class Activation Mapping (CAM)
Global Fully Connected
Average Layer, weights
𝐾×𝐶
Pooling 𝑤 ∈ ℝ
H K C
K
W
Last layer CNN features: Pooled features: Class Scores:
𝑓 ∈ ℝ 𝐻×𝑊×𝐾 𝐹 ∈ ℝ 𝐾 𝑆 ∈ ℝ 𝐶
1 1
𝐹 = ෍ 𝑓 𝑆 = ෍ 𝑤 𝐹 = ෍ 𝑤 ෍ 𝑓
𝑘 𝐻𝑊 ℎ,𝑤,𝑘 𝑐 𝑘,𝑐 𝑘 𝐻𝑊 𝑘,𝑐 ℎ,𝑤,𝑘
ℎ,𝑤 𝑘 𝑘 ℎ,𝑤
1
= ෍ ෍ 𝑤 𝑓
𝑘,𝑐 ℎ,𝑤,𝑘
𝐻𝑊
ℎ,𝑤 𝑘
Zhou et al, “Learning Deep Features for Discriminative Localization”, CVPR 2016
Stanford CS231n 10th Anniversary Lecture 9 - 137 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Class Activation Mapping (CAM)
Global Fully Connected
Average Layer, weights
𝐾×𝐶
Pooling 𝑤 ∈ ℝ
H K C
K
W
Last layer CNN features: Pooled features: Class Scores:
𝑓 ∈ ℝ 𝐻×𝑊×𝐾 𝐹 ∈ ℝ 𝐾 𝑆 ∈ ℝ 𝐶
1 1
𝐹 = ෍ 𝑓 𝑆 = ෍ 𝑤 𝐹 = ෍ 𝑤 ෍ 𝑓
𝑘 𝐻𝑊 ℎ,𝑤,𝑘 𝑐 𝑘,𝑐 𝑘 𝐻𝑊 𝑘,𝑐 ℎ,𝑤,𝑘
ℎ,𝑤 𝑘 𝑘 ℎ,𝑤
1
= ෍ ෍ 𝑤 𝑓
𝑘,𝑐 ℎ,𝑤,𝑘
𝐻𝑊
ℎ,𝑤 𝑘
Zhou et al, “Learning Deep Features for Discriminative Localization”, CVPR 2016 |  |  |  |  |
| Last layer CNN fe
𝐻×𝑊×
𝑓 ∈ ℝ
1
𝐹 = ෍ 𝑓
𝑘 ℎ,𝑤,
𝐻𝑊
ℎ,𝑤
Zhou et al, “Learning Deep Features fo | Last layer CNN fe
𝐻×𝑊×
𝑓 ∈ ℝ | a
𝐾 | tures: |  |
|  |  | 𝑘
r D |  |  |
| Stanford CS231n 1 |  | 0 | th Anniversary Lecture 9 - 1 | 37 April 29, 2025 |
|  |  |  |  |  |


---
## Page 138
---


Class Activation Mapping (CAM)
Global Fully Connected
Average Layer, weights
𝐾×𝐶
Pooling 𝑤 ∈ ℝ
H K C
K
W
Last layer CNN features: Pooled features: Class Scores:
𝑓 ∈ ℝ 𝐻×𝑊×𝐾 𝐹 ∈ ℝ 𝐾 𝑆 ∈ ℝ 𝐶
1 1
𝐹 = ෍ 𝑓 𝑆 = ෍ 𝑤 𝐹 = ෍ 𝑤 ෍ 𝑓
𝑘 𝐻𝑊 ℎ,𝑤,𝑘 𝑐 𝑘,𝑐 𝑘 𝐻𝑊 𝑘,𝑐 ℎ,𝑤,𝑘
ℎ,𝑤 𝑘 𝑘 ℎ,𝑤
1
= ෍ ෍ 𝒘 𝒇
𝒌,𝒄 𝒉,𝒘,𝒌
𝐻𝑊
ℎ,𝑤 𝒌
Zhou et al, “Learning Deep Features for Discriminative Localization”, CVPR 2016
Stanford CS231n 10th Anniversary Lecture 9 - 138 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Class Activation Mapping (CAM)
Global Fully Connected
Average Layer, weights
𝐾×𝐶
Pooling 𝑤 ∈ ℝ
H K C
K
W
Last layer CNN features: Pooled features: Class Scores:
𝑓 ∈ ℝ 𝐻×𝑊×𝐾 𝐹 ∈ ℝ 𝐾 𝑆 ∈ ℝ 𝐶
1 1
𝐹 = ෍ 𝑓 𝑆 = ෍ 𝑤 𝐹 = ෍ 𝑤 ෍ 𝑓
𝑘 𝐻𝑊 ℎ,𝑤,𝑘 𝑐 𝑘,𝑐 𝑘 𝐻𝑊 𝑘,𝑐 ℎ,𝑤,𝑘
ℎ,𝑤 𝑘 𝑘 ℎ,𝑤
1
= ෍ ෍ 𝒘 𝒇
𝒌,𝒄 𝒉,𝒘,𝒌
𝐻𝑊
ℎ,𝑤 𝒌
Zhou et al, “Learning Deep Features for Discriminative Localization”, CVPR 2016 |  |  |  |  |
| Last layer CNN fe
𝐻×𝑊×
𝑓 ∈ ℝ
1
𝐹 = ෍ 𝑓
𝑘 ℎ,𝑤,
𝐻𝑊
ℎ,𝑤
Zhou et al, “Learning Deep Features fo | Last layer CNN fe
𝐻×𝑊×
𝑓 ∈ ℝ | a
𝐾 | tures: |  |
|  |  | 𝑘
r D |  |  |
| Stanford CS231n 1 |  | 0 | th Anniversary Lecture 9 - 1 | 38 April 29, 2025 |
|  |  |  |  |  |


---
## Page 139
---


Class Activation Mapping (CAM)
Global Fully Connected
Average Layer, weights
𝐾×𝐶
Pooling 𝑤 ∈ ℝ
H K C
K
W
Last layer CNN features: Pooled features: Class Scores:
𝑓 ∈ ℝ 𝐻×𝑊×𝐾 𝐹 ∈ ℝ 𝐾 𝑆 ∈ ℝ 𝐶
1 1 Class Activation Maps:
𝐹 = ෍ 𝑓 𝑆 = ෍ 𝑤 𝐹 = ෍ 𝑤 ෍ 𝑓
𝑘 𝐻𝑊 ℎ,𝑤,𝑘 𝑐 𝑘,𝑐 𝑘 𝐻𝑊 𝑘,𝑐 ℎ,𝑤,𝑘 𝑴 ∈ ℝ𝑪,𝑯,𝑾
ℎ,𝑤 𝑘 𝑘 ℎ,𝑤
1
= ෍ ෍ 𝒘 𝒇 𝑴 = ෍ 𝒘 𝒇
𝒌,𝒄 𝒉,𝒘,𝒌 𝒄,𝒉,𝒘 𝒌,𝒄 𝒉,𝒘,𝒌
𝐻𝑊
ℎ,𝑤 𝒌 𝒌
Zhou et al, “Learning Deep Features for Discriminative Localization”, CVPR 2016
Stanford CS231n 10th Anniversary Lecture 9 - 139 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| Class Activation Mapping (CAM)
Global Fully Connected
Average Layer, weights
𝐾×𝐶
Pooling 𝑤 ∈ ℝ
H K C
K
W
Last layer CNN features: Pooled features: Class Scores:
𝑓 ∈ ℝ 𝐻×𝑊×𝐾 𝐹 ∈ ℝ 𝐾 𝑆 ∈ ℝ 𝐶
1 1 Class Activation Maps:
𝐹 = ෍ 𝑓 𝑆 = ෍ 𝑤 𝐹 = ෍ 𝑤 ෍ 𝑓
𝑘 𝐻𝑊 ℎ,𝑤,𝑘 𝑐 𝑘,𝑐 𝑘 𝐻𝑊 𝑘,𝑐 ℎ,𝑤,𝑘 𝑴 ∈ ℝ𝑪,𝑯,𝑾
ℎ,𝑤 𝑘 𝑘 ℎ,𝑤
1
= ෍ ෍ 𝒘 𝒇 𝑴 = ෍ 𝒘 𝒇
𝒌,𝒄 𝒉,𝒘,𝒌 𝒄,𝒉,𝒘 𝒌,𝒄 𝒉,𝒘,𝒌
𝐻𝑊
ℎ,𝑤 𝒌 𝒌
Zhou et al, “Learning Deep Features for Discriminative Localization”, CVPR 2016 |  |  |  |  |  |  |
| Last layer CNN fe
𝐻×𝑊×
𝑓 ∈ ℝ
1
𝐹 = ෍ 𝑓
𝑘 ℎ,𝑤,
𝐻𝑊
ℎ,𝑤
Zhou et al, “Learning Deep Features fo | Last layer CNN fe
𝐻×𝑊×
𝑓 ∈ ℝ | a
𝐾 | tures: |  |  |  |
|  |  |  |  |  | 𝐶
𝑆 ∈ ℝ
Class Activation Maps:
𝑴 ∈ ℝ𝑪,𝑯,𝑾
𝑴 = ෍ 𝒘 𝒇
𝒄,𝒉,𝒘 𝒌,𝒄 𝒉,𝒘,𝒌
𝒌 |  |
|  |  | 𝑘
r D |  |  |  |  |
| Stanford CS231n 1 |  | 0 | th Anniversary Lecture 9 - 1 | 39 | April 29, 2025 |  |
|  |  |  |  |  |  |  |


### Table 2

| Class Scores: |
| 𝐶
𝑆 ∈ ℝ |


---
## Page 140
---


Class Activation Mapping (CAM)
Zhou et al, “Learning Deep Features for Discriminative Localization”, CVPR 2016
Stanford CS231n 10th Anniversary Lecture 9 - 140 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Class Activation Mapping (CAM)
Zhou et al, “Learning Deep Features for Discriminative Localization”, CVPR 2016 |
| Stanford CS231n 10th Anniversary Lecture 9 - 140 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 141
---


Problem: Can only
Class Activation Mapping (CAM)
apply to last conv layer
Zhou et al, “Learning Deep Features for Discriminative Localization”, CVPR 2016
Stanford CS231n 10th Anniversary Lecture 9 - 141 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Problem: Can only
Class Activation Mapping (CAM)
apply to last conv layer
Zhou et al, “Learning Deep Features for Discriminative Localization”, CVPR 2016 |
| Stanford CS231n 10th Anniversary Lecture 9 - 141 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 142
---


Gradient-Weighted Class Activation Mapping (Grad-CAM)
𝐻×𝑊×𝐾
1. Pick any layer, with activations 𝐴 ∈ ℝ
Selvarajuet al, “Grad-CAM: Visual Explanations from Deep Networks via Gradient-based Localization”, CVPR 2017
Stanford CS231n 10th Anniversary Lecture 9 - 142 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Gradient-Weighted Class Activation Mapping (Grad-CAM)
𝐻×𝑊×𝐾
1. Pick any layer, with activations 𝐴 ∈ ℝ
Selvarajuet al, “Grad-CAM: Visual Explanations from Deep Networks via Gradient-based Localization”, CVPR 2017 |
| Stanford CS231n 10th Anniversary Lecture 9 - 142 April 29, 2025 |


---
## Page 143
---


Gradient-Weighted Class Activation Mapping (Grad-CAM)
𝐻×𝑊×𝐾
1. Pick any layer, with activations 𝐴 ∈ ℝ
2. Compute gradient of class score 𝑆 with respect to A:
𝑐
𝜕𝑆
𝑐
𝐻×𝑊×𝐾
∈ ℝ
𝜕𝐴
Selvarajuet al, “Grad-CAM: Visual Explanations from Deep Networks via Gradient-based Localization”, CVPR 2017
Stanford CS231n 10th Anniversary Lecture 9 - 143 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Gradient-Weighted Class Activation Mapping (Grad-CAM)
𝐻×𝑊×𝐾
1. Pick any layer, with activations 𝐴 ∈ ℝ
2. Compute gradient of class score 𝑆 with respect to A:
𝑐
𝜕𝑆
𝑐
𝐻×𝑊×𝐾
∈ ℝ
𝜕𝐴
Selvarajuet al, “Grad-CAM: Visual Explanations from Deep Networks via Gradient-based Localization”, CVPR 2017 |
| Stanford CS231n 10th Anniversary Lecture 9 - 143 April 29, 2025 |


---
## Page 144
---


Gradient-Weighted Class Activation Mapping (Grad-CAM)
𝐻×𝑊×𝐾
1. Pick any layer, with activations 𝐴 ∈ ℝ
2. Compute gradient of class score 𝑆 with respect to A:
𝑐
𝜕𝑆
𝑐
𝐻×𝑊×𝐾
∈ ℝ
𝜕𝐴
𝐾
3. Global Average Pool the gradients to get weights 𝛼 ∈ ℝ :
1 𝜕𝑆
𝑐
𝛼 = ෍
𝑘
𝐻𝑊 𝜕𝐴
ℎ,𝑤 ℎ,𝑤,𝑘
Selvarajuet al, “Grad-CAM: Visual Explanations from Deep Networks via Gradient-based Localization”, CVPR 2017
Stanford CS231n 10th Anniversary Lecture 9 - 144 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Gradient-Weighted Class Activation Mapping (Grad-CAM)
𝐻×𝑊×𝐾
1. Pick any layer, with activations 𝐴 ∈ ℝ
2. Compute gradient of class score 𝑆 with respect to A:
𝑐
𝜕𝑆
𝑐
𝐻×𝑊×𝐾
∈ ℝ
𝜕𝐴
𝐾
3. Global Average Pool the gradients to get weights 𝛼 ∈ ℝ :
1 𝜕𝑆
𝑐
𝛼 = ෍
𝑘
𝐻𝑊 𝜕𝐴
ℎ,𝑤 ℎ,𝑤,𝑘
Selvarajuet al, “Grad-CAM: Visual Explanations from Deep Networks via Gradient-based Localization”, CVPR 2017 |  |  |
|  | 𝐻×𝑊×𝐾
1. Pick any layer, with activations 𝐴 ∈ ℝ
2. Compute gradient of class score 𝑆 with respect to A:
𝑐
𝜕𝑆
𝑐
𝐻×𝑊×𝐾
∈ ℝ
𝜕𝐴
𝐾
3. Global Average Pool the gradients to get weights 𝛼 ∈ ℝ :
1 𝜕𝑆
𝑐
𝛼 = ෍
𝑘
𝐻𝑊 𝜕𝐴
ℎ,𝑤 ℎ,𝑤,𝑘
rad-CAM: Visual Explanations from Deep Networks via Gradient-based Localization”, CVPR 2017 |  |
| Stanford | CS231n 10th Anniversary Lecture 9 - 144 April 2 | 9, 2025 |


---
## Page 145
---


Gradient-Weighted Class Activation Mapping (Grad-CAM)
𝐻×𝑊×𝐾
1. Pick any layer, with activations 𝐴 ∈ ℝ
2. Compute gradient of class score 𝑆 with respect to A:
𝑐
𝜕𝑆
𝑐
𝐻×𝑊×𝐾
∈ ℝ
𝜕𝐴
𝐾
3. Global Average Pool the gradients to get weights 𝛼 ∈ ℝ :
1 𝜕𝑆
𝑐
𝛼 = ෍
𝑘
𝐻𝑊 𝜕𝐴
ℎ,𝑤 ℎ,𝑤,𝑘
𝑐 𝐻,𝑊
4. Compute activation map 𝑀 ∈ ℝ :
𝑐
𝑀 = 𝑅𝑒𝐿𝑈 ෍ 𝛼 𝐴
ℎ,𝑤 𝑘 ℎ,𝑤,𝑘
𝑘
Selvarajuet al, “Grad-CAM: Visual Explanations from Deep Networks via Gradient-based Localization”, CVPR 2017
Stanford CS231n 10th Anniversary Lecture 9 - 145 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Gradient-Weighted Class Activation Mapping (Grad-CAM)
𝐻×𝑊×𝐾
1. Pick any layer, with activations 𝐴 ∈ ℝ
2. Compute gradient of class score 𝑆 with respect to A:
𝑐
𝜕𝑆
𝑐
𝐻×𝑊×𝐾
∈ ℝ
𝜕𝐴
𝐾
3. Global Average Pool the gradients to get weights 𝛼 ∈ ℝ :
1 𝜕𝑆
𝑐
𝛼 = ෍
𝑘
𝐻𝑊 𝜕𝐴
ℎ,𝑤 ℎ,𝑤,𝑘
𝑐 𝐻,𝑊
4. Compute activation map 𝑀 ∈ ℝ :
𝑐
𝑀 = 𝑅𝑒𝐿𝑈 ෍ 𝛼 𝐴
ℎ,𝑤 𝑘 ℎ,𝑤,𝑘
𝑘
Selvarajuet al, “Grad-CAM: Visual Explanations from Deep Networks via Gradient-based Localization”, CVPR 2017 |  |  |
|  | 𝐻×𝑊×𝐾
1. Pick any layer, with activations 𝐴 ∈ ℝ
2. Compute gradient of class score 𝑆 with respect to A:
𝑐
𝜕𝑆
𝑐
𝐻×𝑊×𝐾
∈ ℝ
𝜕𝐴
𝐾
3. Global Average Pool the gradients to get weights 𝛼 ∈ ℝ :
1 𝜕𝑆
𝑐
𝛼 = ෍
𝑘
𝐻𝑊 𝜕𝐴
ℎ,𝑤 ℎ,𝑤,𝑘
𝑐 𝐻,𝑊
4. Compute activation map 𝑀 ∈ ℝ :
𝑐
𝑀 = 𝑅𝑒𝐿𝑈 ෍ 𝛼 𝐴
ℎ,𝑤 𝑘 ℎ,𝑤,𝑘
𝑘
rad-CAM: Visual Explanations from Deep Networks via Gradient-based Localization”, CVPR 2017 |  |
| Stanford | CS231n 10th Anniversary Lecture 9 - 145 April 2 | 9, 2025 |
|  |  |  |


---
## Page 146
---


Gradient-Weighted Class Activation Mapping (Grad-CAM)
Selvarajuet al, “Grad-CAM: Visual Explanations from Deep Networks via Gradient-based Localization”, CVPR 2017
Stanford CS231n 10th Anniversary Lecture 9 - 146 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Gradient-Weighted Class Activation Mapping (Grad-CAM)
Selvarajuet al, “Grad-CAM: Visual Explanations from Deep Networks via Gradient-based Localization”, CVPR 2017 |
| Stanford CS231n 10th Anniversary Lecture 9 - 146 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 147
---


Visualizing ViT features
Chen et al., When Vision Transformers Outperform ResnetsWithout Pre-training Or
Strong Data Augmentations, ICLR 2022; Paul and Chen, Vision Transformers are Robust
Learners, AAAI 2022. Reproduced for educational purposes.
Stanford CS231n 10th Anniversary Lecture 9 - 147 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Visualizing ViT features
Chen et al., When Vision Transformers Outperform ResnetsWithout Pre-training Or
Strong Data Augmentations, ICLR 2022; Paul and Chen, Vision Transformers are Robust
Learners, AAAI 2022. Reproduced for educational purposes. |
| Stanford CS231n 10th Anniversary Lecture 9 - 147 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 148
---


Today
● Transformers Recap
● Computer Vision Tasks
○ Semantic Segmentation
○ Object Detection
○ Instance Segmentation
● Visualization & Understanding
○ Model Layers Visualization
○ Saliency Maps
○ CAM & Grad-CAM
Stanford CS231n 10th Anniversary Lecture 9 - 148 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Today
● Transformers Recap
● Computer Vision Tasks
○ Semantic Segmentation
○ Object Detection
○ Instance Segmentation
● Visualization & Understanding
○ Model Layers Visualization
○ Saliency Maps
○ CAM & Grad-CAM |
| Stanford CS231n 10th Anniversary Lecture 9 - 148 April 29, 2025 |


---
## Page 149
---


Next time: Video Understanding
Stanford CS231n 10th Anniversary Lecture 9 - 149 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Next time: Video Understanding |
| Stanford CS231n 10th Anniversary Lecture 9 - 149 April 29, 2025 |


---
## Page 150
---


Additional Reading Material
Stanford CS231n 10th Anniversary Lecture 9 - 150 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Additional Reading Material |
| Stanford CS231n 10th Anniversary Lecture 9 - 150 April 29, 2025 |


---
## Page 151
---


Convolution as Matrix Multiplication (1D Example)
We can express convolution in
terms of a matrix multiplication
Example: 1D conv, kernel size=3,
stride=2, padding=1
Stanford CS231n 10th Anniversary Lecture 9 - 151 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Convolution as Matrix Multiplication (1D Example)
We can express convolution in
terms of a matrix multiplication
Example: 1D conv, kernel size=3,
stride=2, padding=1 |
| Stanford CS231n 10th Anniversary Lecture 9 - 151 April 29, 2025 |


[Page contains 4 image(s)]


---
## Page 152
---


Convolution as Matrix Multiplication (1D Example)
We can express convolution in Transposed convolution multiplies by the
terms of a matrix multiplication transpose of the same matrix:
Example: 1D conv, kernel size=3,
Example: 1D transposed conv, kernel size=3,
stride=2, padding=1
stride=2, padding=0
Stanford CS231n 10th Anniversary Lecture 9 - 152 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Convolution as Matrix Multiplication (1D Example)
We can express convolution in Transposed convolution multiplies by the
terms of a matrix multiplication transpose of the same matrix:
Example: 1D conv, kernel size=3,
Example: 1D transposed conv, kernel size=3,
stride=2, padding=1
stride=2, padding=0 |
| Stanford CS231n 10th Anniversary Lecture 9 - 152 April 29, 2025 |


[Page contains 6 image(s)]


---
## Page 153
---


Cropping Features: RoI Pool
CNN
Input Image Image features: C x H x W
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
Girshick, “Fast R-CNN”, ICCV 2015.
Girshick, “Fast R-CNN”, ICCV 2015.
Stanford CS231n 10th Anniversary Lecture 9 - 153 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| Cropping Features: RoI Pool
CNN
Input Image Image features: C x H x W
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
Girshick, “Fast R-CNN”, ICCV 2015.
Girshick, “Fast R-CNN”, ICCV 2015. |
| Stanford CS231n 10th Anniversary Lecture 9 - 153 April 29, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |


[Page contains 1 image(s)]


---
## Page 154
---


Cropping Features: RoI Pool
Project proposal
onto features
CNN
Input Image Image features: C x H x W
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
Girshick, “Fast R-CNN”, ICCV 2015.
Girshick, “Fast R-CNN”, ICCV 2015.
Stanford CS231n 10th Anniversary Lecture 9 - 154 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| Cropping Features: RoI Pool
Project proposal
onto features
CNN
Input Image Image features: C x H x W
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
Girshick, “Fast R-CNN”, ICCV 2015.
Girshick, “Fast R-CNN”, ICCV 2015. |
| Stanford CS231n 10th Anniversary Lecture 9 - 154 April 29, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |


[Page contains 1 image(s)]


---
## Page 155
---


Cropping Features: RoI Pool
“Snap” to
grid cells
Project proposal
onto features
CNN
Input Image Image features: C x H x W
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
Girshick, “Fast R-CNN”, ICCV 2015.
Stanford CS231n 10th Anniversary Lecture 9 - 155 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| Cropping Features: RoI Pool
“Snap” to
grid cells
Project proposal
onto features
CNN
Input Image Image features: C x H x W
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
Girshick, “Fast R-CNN”, ICCV 2015. |
| Stanford CS231n 10th Anniversary Lecture 9 - 155 April 29, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |


[Page contains 1 image(s)]


---
## Page 156
---


Cropping Features: RoI Pool
“Snap” to
grid cells
Project proposal
onto features
Q: how do we resize the 512 x 5
x 4 region to, e.g., a 512 x 2 x 2
tensor?.
CNN
Input Image Image features: C x H x W
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
Girshick, “Fast R-CNN”, ICCV 2015.
Stanford CS231n 10th Anniversary Lecture 9 - 156 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| Cropping Features: RoI Pool
“Snap” to
grid cells
Project proposal
onto features
Q: how do we resize the 512 x 5
x 4 region to, e.g., a 512 x 2 x 2
tensor?.
CNN
Input Image Image features: C x H x W
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
Girshick, “Fast R-CNN”, ICCV 2015. |
| Stanford CS231n 10th Anniversary Lecture 9 - 156 April 29, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |


[Page contains 1 image(s)]


---
## Page 157
---


Cropping Features: RoI Pool
Divide into 2x2
“Snap” to
grid of (roughly)
grid cells
equal subregions
Project proposal
onto features
Q: how do we resize the 512 x 5
x 4region to, e.g., a 512 x 2 x 2
tensor?.
CNN
Input Image Image features: C x H x W
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
Girshick, “Fast R-CNN”, ICCV 2015.
Stanford CS231n 10th Anniversary Lecture 9 - 157 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| Cropping Features: RoI Pool
Divide into 2x2
“Snap” to
grid of (roughly)
grid cells
equal subregions
Project proposal
onto features
Q: how do we resize the 512 x 5
x 4region to, e.g., a 512 x 2 x 2
tensor?.
CNN
Input Image Image features: C x H x W
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
Girshick, “Fast R-CNN”, ICCV 2015. |
| Stanford CS231n 10th Anniversary Lecture 9 - 157 April 29, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |


[Page contains 1 image(s)]


---
## Page 158
---


Cropping Features: RoI Pool
Divide into 2x2
“Snap” to
grid of (roughly)
grid cells
equal subregions
Project proposal
onto features
Max-pool within
each subregion
CNN
Region features
(here 512 x 2 x 2;
In practice e.g512 x 7 x 7)
Input Image Image features: C x H x W
Region features always the
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
same size even if input regions
have different sizes!
Girshick, “Fast R-CNN”, ICCV 2015.
Stanford CS231n 10th Anniversary Lecture 9 - 158 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Cropping Features: RoI Pool
Divide into 2x2
“Snap” to
grid of (roughly)
grid cells
equal subregions
Project proposal
onto features
Max-pool within
each subregion
CNN
Region features
(here 512 x 2 x 2;
In practice e.g512 x 7 x 7)
Input Image Image features: C x H x W
Region features always the
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
same size even if input regions
have different sizes!
Girshick, “Fast R-CNN”, ICCV 2015. |
| Stanford CS231n 10th Anniversary Lecture 9 - 158 April 29, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |


### Table 3

|  |  |


[Page contains 1 image(s)]


---
## Page 159
---


Cropping Features: RoI Pool
Divide into 2x2
“Snap” to
grid of (roughly)
grid cells
equal subregions
Project proposal
onto features
Max-pool within
each subregion
CNN
Region features
(here 512 x 2 x 2;
In practice e.g512 x 7 x 7)
Input Image Image features: C x H x W
Region features always the
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
same size even if input regions
have different sizes!
Problem: Region features slightly misaligned
Girshick, “Fast R-CNN”, ICCV 2015.
Stanford CS231n 10th Anniversary Lecture 9 - 159 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Cropping Features: RoI Pool
Divide into 2x2
“Snap” to
grid of (roughly)
grid cells
equal subregions
Project proposal
onto features
Max-pool within
each subregion
CNN
Region features
(here 512 x 2 x 2;
In practice e.g512 x 7 x 7)
Input Image Image features: C x H x W
Region features always the
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
same size even if input regions
have different sizes!
Problem: Region features slightly misaligned
Girshick, “Fast R-CNN”, ICCV 2015. |
| Stanford CS231n 10th Anniversary Lecture 9 - 159 April 29, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |


### Table 3

|  |  |


[Page contains 1 image(s)]


---
## Page 160
---


Cropping Features: RoI Align
No “snapping”!
Project proposal
onto features
CNN
Input Image Image features: C x H x W
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
He et al, “Mask R-CNN”, ICCV 2017
Stanford CS231n 10th Anniversary Lecture 9 - 160 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| Cropping Features: RoI Align
No “snapping”!
Project proposal
onto features
CNN
Input Image Image features: C x H x W
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
He et al, “Mask R-CNN”, ICCV 2017 |
| Stanford CS231n 10th Anniversary Lecture 9 - 160 April 29, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |


[Page contains 1 image(s)]


---
## Page 161
---


Sample at regular points in
Cropping Features: RoI Align
each subregion using
bilinear interpolation
No “snapping”!
Project proposal
onto features
CNN
Input Image Image features: C x H x W
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
He et al, “Mask R-CNN”, ICCV 2017
Stanford CS231n 10th Anniversary Lecture 9 - 161 April 29, 2025

[Page contains 2 table(s)]


### Table 1

| Sample at regular points in
Cropping Features: RoI Align
each subregion using
bilinear interpolation
No “snapping”!
Project proposal
onto features
CNN
Input Image Image features: C x H x W
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
He et al, “Mask R-CNN”, ICCV 2017 |
| Stanford CS231n 10th Anniversary Lecture 9 - 161 April 29, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |


[Page contains 1 image(s)]


---
## Page 162
---


Sample at regular points in
Cropping Features: RoI Align
each subregion using
bilinear interpolation
No “snapping”!
Project proposal
onto features
CNN
Feature f for point (x, y) is
xy
a linear combination of
Input Image Image features: C x H x W features at its four
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
neighboring grid cells:
He et al, “Mask R-CNN”, ICCV 2017
Stanford CS231n 10th Anniversary Lecture 9 - 162 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Sample at regular points in
Cropping Features: RoI Align
each subregion using
bilinear interpolation
No “snapping”!
Project proposal
onto features
CNN
Feature f for point (x, y) is
xy
a linear combination of
Input Image Image features: C x H x W features at its four
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
neighboring grid cells:
He et al, “Mask R-CNN”, ICCV 2017 |
| Stanford CS231n 10th Anniversary Lecture 9 - 162 April 29, 2025 |


### Table 2

|  |  |
|  |  |


### Table 3

|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |


[Page contains 1 image(s)]


---
## Page 163
---


Sample at regular points in
Cropping Features: RoI Align
each subregion using
bilinear interpolation
No “snapping”!
Project proposal
onto features
f ∈R512 f ∈R512
11 21
(x ,y ) (x ,y )
1 1 2 1
(x,y)
f ∈R512 f ∈R512
12 22
CNN
(x ,y ) (x ,y )
1 2 2 2
Feature f for point (x, y) is
xy
a linear combination of
Input Image Image features: C x H x W features at its four
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
neighboring grid cells:
He et al, “Mask R-CNN”, ICCV 2017
Stanford CS231n 10th Anniversary Lecture 9 - 163 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Sample at regular points in
Cropping Features: RoI Align
each subregion using
bilinear interpolation
No “snapping”!
Project proposal
onto features
f ∈R512 f ∈R512
11 21
(x ,y ) (x ,y )
1 1 2 1
(x,y)
f ∈R512 f ∈R512
12 22
CNN
(x ,y ) (x ,y )
1 2 2 2
Feature f for point (x, y) is
xy
a linear combination of
Input Image Image features: C x H x W features at its four
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
neighboring grid cells:
He et al, “Mask R-CNN”, ICCV 2017 |
| Stanford CS231n 10th Anniversary Lecture 9 - 163 April 29, 2025 |


### Table 2

| f ∈R512
11
(x ,y )
1 1 | f ∈R512
21
(x ,y )
2 1 |
| f ∈R512
12
(x ,y )
1 2 | f ∈R512
22
(x ,y )
2 2 |


### Table 3

|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |


[Page contains 2 image(s)]


---
## Page 164
---


Sample at regular points in
Cropping Features: RoI Align
each subregion using
bilinear interpolation
No “snapping”!
Project proposal
onto features
Max-pool within
each subregion
CNN
Region features
(here 512 x 2 x 2;
In practice e.g512 x 7 x 7)
Input Image Image features: C x H x W
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
He et al, “Mask R-CNN”, ICCV 2017
Stanford CS231n 10th Anniversary Lecture 9 - 164 April 29, 2025

[Page contains 3 table(s)]


### Table 1

| Sample at regular points in
Cropping Features: RoI Align
each subregion using
bilinear interpolation
No “snapping”!
Project proposal
onto features
Max-pool within
each subregion
CNN
Region features
(here 512 x 2 x 2;
In practice e.g512 x 7 x 7)
Input Image Image features: C x H x W
(e.g. 3 x 640 x 480) (e.g. 512 x 20 x 15)
He et al, “Mask R-CNN”, ICCV 2017 |
| Stanford CS231n 10th Anniversary Lecture 9 - 164 April 29, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |


### Table 3

|  |  |


[Page contains 1 image(s)]


---
## Page 165
---


R-CNN vs Fast R-CNN
Girshicket al, “Rich feature hierarchies for accurate object detection and semantic segmentation”, CVPR 2014.
He et al, “Spatial pyramid pooling in deep convolutional networks for visual recognition”, ECCV 2014
Girshick, “Fast R-CNN”, ICCV 2015
Stanford CS231n 10th Anniversary Lecture 9 - 165 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| R-CNN vs Fast R-CNN
Girshicket al, “Rich feature hierarchies for accurate object detection and semantic segmentation”, CVPR 2014.
He et al, “Spatial pyramid pooling in deep convolutional networks for visual recognition”, ECCV 2014
Girshick, “Fast R-CNN”, ICCV 2015 |
| Stanford CS231n 10th Anniversary Lecture 9 - 165 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 166
---


R-CNN vs Fast R-CNN
Problem:
Runtime dominated by
region proposals!
Girshicket al, “Rich feature hierarchies for accurate object detection and semantic segmentation”, CVPR 2014.
He et al, “Spatial pyramid pooling in deep convolutional networks for visual recognition”, ECCV 2014
Girshick, “Fast R-CNN”, ICCV 2015
Stanford CS231n 10th Anniversary Lecture 9 - 166 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| R-CNN vs Fast R-CNN
Problem:
Runtime dominated by
region proposals!
Girshicket al, “Rich feature hierarchies for accurate object detection and semantic segmentation”, CVPR 2014.
He et al, “Spatial pyramid pooling in deep convolutional networks for visual recognition”, ECCV 2014
Girshick, “Fast R-CNN”, ICCV 2015 |
| Stanford CS231n 10th Anniversary Lecture 9 - 166 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 167
---


Faster R-CNN:
Make CNN do proposals!
Insert Region Proposal
Network (RPN) to predict
proposals from features
Otherwise same as Fast R-CNN: Crop
features for each proposal, classify
each one
Ren et al, “Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks”, NIPS 2015
Figure copyright 2015, Ross Girshick; reproduced with permission
Stanford CS231n 10th Anniversary Lecture 9 - 167 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Faster R-CNN:
Make CNN do proposals!
Insert Region Proposal
Network (RPN) to predict
proposals from features
Otherwise same as Fast R-CNN: Crop
features for each proposal, classify
each one
Ren et al, “Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks”, NIPS 2015
Figure copyright 2015, Ross Girshick; reproduced with permission |
| Stanford CS231n 10th Anniversary Lecture 9 - 167 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 168
---


Faster R-CNN:
Make CNN do proposals!
Jointly train with 4 losses:
1. RPN classify object / not object
2. RPN regress box coordinates
3. Final classification score (object
classes)
4. Final box coordinates
Ren et al, “Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks”, NIPS 2015
Figure copyright 2015, Ross Girshick; reproduced with permission
Stanford CS231n 10th Anniversary Lecture 9 - 168 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Faster R-CNN:
Make CNN do proposals!
Jointly train with 4 losses:
1. RPN classify object / not object
2. RPN regress box coordinates
3. Final classification score (object
classes)
4. Final box coordinates
Ren et al, “Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks”, NIPS 2015
Figure copyright 2015, Ross Girshick; reproduced with permission |
| Stanford CS231n 10th Anniversary Lecture 9 - 168 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 169
---


Faster R-CNN:
Make CNN do proposals!
Stanford CS231n 10th Anniversary Lecture 9 - 169 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Faster R-CNN:
Make CNN do proposals! |
| Stanford CS231n 10th Anniversary Lecture 9 - 169 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 170
---


Faster R-CNN:
Make CNN do proposals!
Glossing over many details:
- Ignore overlapping proposals with
non-max suppression
- How are anchors determined?
- How do we sample positive /
negative samples for training the
RPN?
- How to parameterize bounding box
regression?
Ren et al, “Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks”, NIPS 2015
Figure copyright 2015, Ross Girshick; reproduced with permission
Stanford CS231n 10th Anniversary Lecture 9 - 170 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Faster R-CNN:
Make CNN do proposals!
Glossing over many details:
- Ignore overlapping proposals with
non-max suppression
- How are anchors determined?
- How do we sample positive /
negative samples for training the
RPN?
- How to parameterize bounding box
regression?
Ren et al, “Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks”, NIPS 2015
Figure copyright 2015, Ross Girshick; reproduced with permission |
| Stanford CS231n 10th Anniversary Lecture 9 - 170 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 171
---


Faster R-CNN:
Make CNN do proposals!
Faster R-CNN is a
Two-stage object detector
First stage: Run once per image
- Backbone network
- Region proposal network
Second stage: Run once per region
- Crop features: RoI pool / align
- Predict object class
- Prediction bbox offset
Stanford CS231n 10th Anniversary Lecture 9 - 171 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Faster R-CNN:
Make CNN do proposals!
Faster R-CNN is a
Two-stage object detector
First stage: Run once per image
- Backbone network
- Region proposal network
Second stage: Run once per region
- Crop features: RoI pool / align
- Predict object class
- Prediction bbox offset |
| Stanford CS231n 10th Anniversary Lecture 9 - 171 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 172
---


Faster R-CNN:
Do we really need
the second stage?
Make CNN do proposals!
Faster R-CNN is a
Two-stage object detector
First stage: Run once per image
- Backbone network
- Region proposal network
Second stage: Run once per region
- Crop features: RoI pool / align
- Predict object class
- Prediction bbox offset
Stanford CS231n 10th Anniversary Lecture 9 - 172 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Faster R-CNN:
Do we really need
the second stage?
Make CNN do proposals!
Faster R-CNN is a
Two-stage object detector
First stage: Run once per image
- Backbone network
- Region proposal network
Second stage: Run once per region
- Crop features: RoI pool / align
- Predict object class
- Prediction bbox offset |
| Stanford CS231n 10th Anniversary Lecture 9 - 172 April 29, 2025 |


[Page contains 1 image(s)]


---
## Page 173
---


Object Detection: Lots of variables ...
Backbone Takeaways
“Meta-Architecture”
Network Faster R-CNN is slower but
Two-stage: Faster R-CNN
VGG16 more accurate
Single-stage: YOLO / SSD
ResNet-101
Hybrid: R-FCN
Inception V2 SSD is much faster but not
Inception V3 Image Size as accurate
Inception ResNet # Region Proposals
MobileNet … Bigger / Deeper backbones
work better
Huang et al, “Speed/accuracy trade-offs for modern convolutional object detectors”, CVPR 2017
R-FCN: Dai et al, “R-FCN: Object Detection via Region-based Fully Convolutional Networks”, NIPS 2016
Inception-V2: Ioffeand Szegedy, “Batch Normalization: Accelerating Deep Network Training by Reducing Internal Covariate Shift”, ICML 2015
Inception V3: Szegedyet al, “Rethinking the Inception Architecture for Computer Vision”, arXiv2016
Inception ResNet: Szegedyet al, “Inception-V4, Inception-ResNetand the Impact of Residual Connections on Learning”, arXiv2016
MobileNet: Howard et al, “Efficient Convolutional Neural Networks for Mobile Vision Applications”, arXiv2017
Stanford CS231n 10th Anniversary Lecture 9 - 173 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Object Detection: Lots of variables ...
Backbone Takeaways
“Meta-Architecture”
Network Faster R-CNN is slower but
Two-stage: Faster R-CNN
VGG16 more accurate
Single-stage: YOLO / SSD
ResNet-101
Hybrid: R-FCN
Inception V2 SSD is much faster but not
Inception V3 Image Size as accurate
Inception ResNet # Region Proposals
MobileNet … Bigger / Deeper backbones
work better
Huang et al, “Speed/accuracy trade-offs for modern convolutional object detectors”, CVPR 2017
R-FCN: Dai et al, “R-FCN: Object Detection via Region-based Fully Convolutional Networks”, NIPS 2016
Inception-V2: Ioffeand Szegedy, “Batch Normalization: Accelerating Deep Network Training by Reducing Internal Covariate Shift”, ICML 2015
Inception V3: Szegedyet al, “Rethinking the Inception Architecture for Computer Vision”, arXiv2016
Inception ResNet: Szegedyet al, “Inception-V4, Inception-ResNetand the Impact of Residual Connections on Learning”, arXiv2016
MobileNet: Howard et al, “Efficient Convolutional Neural Networks for Mobile Vision Applications”, arXiv2017 |
| Stanford CS231n 10th Anniversary Lecture 9 - 173 April 29, 2025 |


---
## Page 174
---


Object Detection: Lots of variables ...
Backbone Takeaways
“Meta-Architecture”
Network Faster R-CNN is slower but
Two-stage: Faster R-CNN
VGG16 more accurate
Single-stage: YOLO / SSD
ResNet-101
Hybrid: R-FCN
Inception V2 SSD is much faster but not
Inception V3 Image Size as accurate
Inception ResNet # Region Proposals
MobileNet … Bigger / Deeper backbones
work better
Huang et al, “Speed/accuracy trade-offs for modern convolutional object detectors”, CVPR 2017
Zou et al, “Object Detection in 20 Years: A Survey”, arXiv2019
R-FCN: Dai et al, “R-FCN: Object Detection via Region-based Fully Convolutional Networks”, NIPS 2016
Inception-V2: Ioffeand Szegedy, “Batch Normalization: Accelerating Deep Network Training by Reducing Internal Covariate Shift”, ICML 2015
Inception V3: Szegedyet al, “Rethinking the Inception Architecture for Computer Vision”, arXiv2016
Inception ResNet: Szegedyet al, “Inception-V4, Inception-ResNetand the Impact of Residual Connections on Learning”, arXiv2016
MobileNet: Howard et al, “Efficient Convolutional Neural Networks for Mobile Vision Applications”, arXiv2017
Stanford CS231n 10th Anniversary Lecture 9 - 174 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Object Detection: Lots of variables ...
Backbone Takeaways
“Meta-Architecture”
Network Faster R-CNN is slower but
Two-stage: Faster R-CNN
VGG16 more accurate
Single-stage: YOLO / SSD
ResNet-101
Hybrid: R-FCN
Inception V2 SSD is much faster but not
Inception V3 Image Size as accurate
Inception ResNet # Region Proposals
MobileNet … Bigger / Deeper backbones
work better
Huang et al, “Speed/accuracy trade-offs for modern convolutional object detectors”, CVPR 2017
Zou et al, “Object Detection in 20 Years: A Survey”, arXiv2019
R-FCN: Dai et al, “R-FCN: Object Detection via Region-based Fully Convolutional Networks”, NIPS 2016
Inception-V2: Ioffeand Szegedy, “Batch Normalization: Accelerating Deep Network Training by Reducing Internal Covariate Shift”, ICML 2015
Inception V3: Szegedyet al, “Rethinking the Inception Architecture for Computer Vision”, arXiv2016
Inception ResNet: Szegedyet al, “Inception-V4, Inception-ResNetand the Impact of Residual Connections on Learning”, arXiv2016
MobileNet: Howard et al, “Efficient Convolutional Neural Networks for Mobile Vision Applications”, arXiv2017 |
| Stanford CS231n 10th Anniversary Lecture 9 - 174 April 29, 2025 |


---
## Page 175
---


Intermediate Features via (guided) backprop
Pick a single intermediate channel, e.g. one value
in 128 x 13 x 13 conv5 feature map
Compute gradient of activation value with respect
to image pixels
Zeiler and Fergus, “Visualizing and Understanding Convolutional Networks”, ECCV 2014
Springenberget al, “Striving for Simplicity: The All Convolutional Net”, ICLR Workshop 2015
Stanford CS231n 10th Anniversary Lecture 9 - 175 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Intermediate Features via (guided) backprop
Pick a single intermediate channel, e.g. one value
in 128 x 13 x 13 conv5 feature map
Compute gradient of activation value with respect
to image pixels
Zeiler and Fergus, “Visualizing and Understanding Convolutional Networks”, ECCV 2014
Springenberget al, “Striving for Simplicity: The All Convolutional Net”, ICLR Workshop 2015 |
| Stanford CS231n 10th Anniversary Lecture 9 - 175 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 176
---


Intermediate Features via (guided) backprop
ReLU
Pick a single intermediate neuron, e.g. one value in
128 x 13 x 13 conv5 feature map
Compute gradient of neuron value with respect to
image pixels
Images come out nicer if you only
backprop positive gradients through
each ReLU(guided backprop)
Zeiler and Fergus, “Visualizing and Understanding Convolutional Networks”, ECCV 2014 Figure copyright Jost Tobias Springenberg, Alexey Dosovitskiy, Thomas Brox,
Springenberget al, “Striving for Simplicity: The All Convolutional Net”, ICLR Workshop 2015 Martin Riedmiller, 2015; reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 9 - 176 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Intermediate Features via (guided) backprop
ReLU
Pick a single intermediate neuron, e.g. one value in
128 x 13 x 13 conv5 feature map
Compute gradient of neuron value with respect to
image pixels
Images come out nicer if you only
backprop positive gradients through
each ReLU(guided backprop)
Zeiler and Fergus, “Visualizing and Understanding Convolutional Networks”, ECCV 2014 Figure copyright Jost Tobias Springenberg, Alexey Dosovitskiy, Thomas Brox,
Springenberget al, “Striving for Simplicity: The All Convolutional Net”, ICLR Workshop 2015 Martin Riedmiller, 2015; reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 9 - 176 April 29, 2025 |


[Page contains 4 image(s)]


---
## Page 177
---


Intermediate features via (guided) backprop
Maximally activating patches Guided Backprop
(Each row is a different neuron)
Zeiler and Fergus, “Visualizing and Understanding Convolutional Networks”, ECCV 2014
Springenberget al, “Striving for Simplicity: The All Convolutional Net”, ICLR Workshop 2015
Figure copyright Jost Tobias Springenberg, Alexey Dosovitskiy, Thomas Brox, Martin Riedmiller, 2015; reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 9 - 177 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Intermediate features via (guided) backprop
Maximally activating patches Guided Backprop
(Each row is a different neuron)
Zeiler and Fergus, “Visualizing and Understanding Convolutional Networks”, ECCV 2014
Springenberget al, “Striving for Simplicity: The All Convolutional Net”, ICLR Workshop 2015
Figure copyright Jost Tobias Springenberg, Alexey Dosovitskiy, Thomas Brox, Martin Riedmiller, 2015; reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 9 - 177 April 29, 2025 |


[Page contains 2 image(s)]


---
## Page 178
---


Intermediate features via (guided) backprop
Maximally activating patches Guided Backprop
(Each row is a different neuron)
Zeilerand Fergus, “Visualizing and Understanding Convolutional Networks”, ECCV 2014
Springenberget al, “Striving for Simplicity: The All Convolutional Net”, ICLR Workshop 2015
Figure copyright JostTobias Springenberg, Alexey Dosovitskiy, Thomas Brox, Martin Riedmiller, 2015; reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 9 - 178 April 29, 2025

[Page contains 1 table(s)]


### Table 1

| Intermediate features via (guided) backprop
Maximally activating patches Guided Backprop
(Each row is a different neuron)
Zeilerand Fergus, “Visualizing and Understanding Convolutional Networks”, ECCV 2014
Springenberget al, “Striving for Simplicity: The All Convolutional Net”, ICLR Workshop 2015
Figure copyright JostTobias Springenberg, Alexey Dosovitskiy, Thomas Brox, Martin Riedmiller, 2015; reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 9 - 178 April 29, 2025 |


[Page contains 2 image(s)]
