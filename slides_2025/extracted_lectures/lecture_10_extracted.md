# lecture_10

Extracted using pdfplumber



---
## Page 1
---


Lecture 10:
Video Understanding
Stanford CS231n 10th Anniversary Lecture 10 - 1 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture 10:
Video Understanding |
| Stanford CS231n 10th Anniversary Lecture 10 - 1 May 1, 2025 |


---
## Page 2
---


Teaching team
Instructor today
Ph.D. at UT Austin
I taught CS231N at Stanford Postdoc at Stanford
from 2021-2023
Some time at Meta
Ruohan Gao
https://ruohangao.github.io/
Teaching multimodal University of Maryland,
compute vision now. College Park
Stanford CS231n 10th Anniversary Lecture 10 - 2 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Instructor today
Ph.D. at UT Austin
I taught CS231N at Stanford Postdoc at Stanford
from 2021-2023
Some time at Meta
Ruohan Gao
https://ruohangao.github.io/
Teaching multimodal University of Maryland,
compute vision now. College Park |
| Stanford CS231n 10th Anniversary Lecture 10 - 2 May 1, 2025 |


[Page contains 6 image(s)]


---
## Page 3
---


Recall: (2D) Image classification
(assume given a set of possible labels)
{dog, cat, truck, plane, ...}
cat
This imageby Nikitais
licensed under CC-BY 2.0
Stanford CS231n 10th Anniversary Lecture 10 - 3 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Recall: (2D) Image classification
(assume given a set of possible labels)
{dog, cat, truck, plane, ...}
cat
This imageby Nikitais
licensed under CC-BY 2.0 |
| Stanford CS231n 10th Anniversary Lecture 10 - 3 May 1, 2025 |


[Page contains 1 image(s)]


---
## Page 4
---


Last Lecture: (2D) Detection and Segmentation
Semantic Instance
Object
Classification
Segmentation Segmentation
Detection
GRASS, CAT, TREE,
CAT DOG, DOG, CAT DOG, DOG, CAT
SKY
Multiple Objects
No spatial extent No objects, just pixels
This imageis CC0 public domain
Stanford CS231n 10th Anniversary Lecture 10 - 4 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Last Lecture: (2D) Detection and Segmentation
Semantic Instance
Object
Classification
Segmentation Segmentation
Detection
GRASS, CAT, TREE,
CAT DOG, DOG, CAT DOG, DOG, CAT
SKY
Multiple Objects
No spatial extent No objects, just pixels
This imageis CC0 public domain |
| Stanford CS231n 10th Anniversary Lecture 10 - 4 May 1, 2025 |


[Page contains 4 image(s)]


---
## Page 5
---


Living room
Dog
Baby
Stanford CS231n 10th Anniversary Lecture 10 - May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Living room
Dog
Baby |
| Stanford CS231n 10th Anniversary Lecture 10 - May 1, 2025 |


[Page contains 1 image(s)]


---
## Page 6
---


Stanford CS231n 10th Anniversary Lecture 10 - May 1, 2025

[Page contains 1 table(s)]


### Table 1

|  |
| Stanford CS231n 10th Anniversary Lecture 10 - May 1, 2025 |


[Page contains 2 image(s)]


---
## Page 7
---


Today: Video = 2D + Time
A video is a sequence of images
4D tensor: T x 3 x H x W
(or 3 x T x H x W)
…
…
This imageis CC0 public domain
Stanford CS231n 10th Anniversary Lecture 10 - 7 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Today: Video = 2D + Time
A video is a sequence of images
4D tensor: T x 3 x H x W
(or 3 x T x H x W)
…
…
This imageis CC0 public domain |
| Stanford CS231n 10th Anniversary Lecture 10 - 7 May 1, 2025 |


[Page contains 5 image(s)]


---
## Page 8
---


Example task: Video Classification
Swimming
Running
Jumping
Eating
Standing
Input video:
T x 3 x H x W
Running videois in the public domain
Stanford CS231n 10th Anniversary Lecture 10 - 8 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Example task: Video Classification
Swimming
Running
Jumping
Eating
Standing
Input video:
T x 3 x H x W
Running videois in the public domain |
| Stanford CS231n 10th Anniversary Lecture 10 - 8 May 1, 2025 |


[Page contains 1 image(s)]


---
## Page 9
---


Example task: Video Classification
Dog
Images: Recognize objects
Cat
Fish
Truck
Swimming
Videos: Recognize actions
Running
Jumping
Eating
Standing
Running videois in the public domain
Stanford CS231n 10th Anniversary Lecture 10 - 9 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Example task: Video Classification
Dog
Images: Recognize objects
Cat
Fish
Truck
Swimming
Videos: Recognize actions
Running
Jumping
Eating
Standing
Running videois in the public domain |
| Stanford CS231n 10th Anniversary Lecture 10 - 9 May 1, 2025 |


[Page contains 2 image(s)]


---
## Page 10
---


Problem: Videos are big!
Videos are ~30 frames per second (fps)
Size of uncompressed video
(3 bytes per pixel):
SD (640 x 480): ~1.5 GB per minute
HD (1920 x 1080): ~10 GB per minute
Input video:
T x 3 x H x W
Stanford CS231n 10th Anniversary Lecture 10 - 10 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Problem: Videos are big!
Videos are ~30 frames per second (fps)
Size of uncompressed video
(3 bytes per pixel):
SD (640 x 480): ~1.5 GB per minute
HD (1920 x 1080): ~10 GB per minute
Input video:
T x 3 x H x W |
| Stanford CS231n 10th Anniversary Lecture 10 - 10 May 1, 2025 |


[Page contains 1 image(s)]


---
## Page 11
---


Problem: Videos are big!
Videos are ~30 frames per second (fps)
Size of uncompressed video
(3 bytes per pixel):
SD (640 x 480): ~1.5 GB per minute
HD (1920 x 1080): ~10 GB per minute
Solution: Train on short clips: low
Input video:
fps and low spatial resolution
T x 3 x H x W
e.g. T = 16, H=W=112
(3.2 seconds at 5 fps, 588 KB)
Stanford CS231n 10th Anniversary Lecture 10 - 11 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Problem: Videos are big!
Videos are ~30 frames per second (fps)
Size of uncompressed video
(3 bytes per pixel):
SD (640 x 480): ~1.5 GB per minute
HD (1920 x 1080): ~10 GB per minute
Solution: Train on short clips: low
Input video:
fps and low spatial resolution
T x 3 x H x W
e.g. T = 16, H=W=112
(3.2 seconds at 5 fps, 588 KB) |
| Stanford CS231n 10th Anniversary Lecture 10 - 11 May 1, 2025 |


[Page contains 1 image(s)]


---
## Page 12
---


Training on Clips
Raw video: Long, high FPS
Stanford CS231n 10th Anniversary Lecture 10 - 12 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Training on Clips
Raw video: Long, high FPS |
| Stanford CS231n 10th Anniversary Lecture 10 - 12 May 1, 2025 |


[Page contains 17 image(s)]


---
## Page 13
---


Training on Clips
Raw video: Long, high FPS
Training: Train model to classify short clips with low FPS
Stanford CS231n 10th Anniversary Lecture 10 - 13 May 1, 2025

[Page contains 3 table(s)]


### Table 1

| Training on Clips
Raw video: Long, high FPS
Training: Train model to classify short clips with low FPS |
| Stanford CS231n 10th Anniversary Lecture 10 - 13 May 1, 2025 |


### Table 2

|  |  |  |  |  |  |


### Table 3

|  |  |  |  |  |


[Page contains 34 image(s)]


---
## Page 14
---


Training on Clips
Raw video: Long, high FPS
Training: Train model to classify short clips with low FPS
Testing: Run model on different clips, average predictions
Stanford CS231n 10th Anniversary Lecture 10 - 14 May 1, 2025

[Page contains 5 table(s)]


### Table 1

| Training on Clips
Raw video: Long, high FPS
Training: Train model to classify short clips with low FPS
Testing: Run model on different clips, average predictions |
| Stanford CS231n 10th Anniversary Lecture 10 - 14 May 1, 2025 |


### Table 2

|  |  |  |  |  |  |


### Table 3

|  |  |  |  |  |


### Table 4

|  |  |  |  |  |  |
|  |  |  |  |  |  |
|  |  |  |  |  |  |


### Table 5

|  |  |


[Page contains 51 image(s)]


---
## Page 15
---


Video Classification: Single-Frame CNN
Simple idea: train normal 2D CNN to classify video frames independently!
(Average predicted probs at test-time)
Often a very strong baseline for video classification
“Running” “Running” “Running” “Running” “Running” “Running” “Running”
CNN CNN CNN CNN CNN CNN CNN
Stanford CS231n 10th Anniversary Lecture 10 - 15 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Video Classification: Single-Frame CNN
Simple idea: train normal 2D CNN to classify video frames independently!
(Average predicted probs at test-time)
Often a very strong baseline for video classification
“Running” “Running” “Running” “Running” “Running” “Running” “Running”
CNN CNN CNN CNN CNN CNN CNN |
| Stanford CS231n 10th Anniversary Lecture 10 - 15 May 1, 2025 |


[Page contains 7 image(s)]


---
## Page 16
---


Video Classification: Late Fusion (with FC layers)
Intuition: Get high-level appearance Class scores: C
Run 2D CNN on each
of each frame, and combine them
frame, concatenate
Clip features: TDH’W’ MLP
features and feed to MLP
Flatten
Frame features
T x D x H’ x W’
CNN CNN CNN CNN CNN CNN
2D CNN on
each frame
Input:
T x 3 x H x W
Karpathyet al, “Large-scale Video Classification with Convolutional Neural Networks”, CVPR 2014
Stanford CS231n 10th Anniversary Lecture 10 - 16 May 1, 2025

[Page contains 2 table(s)]


### Table 1

| Video Classification: Late Fusion (with FC layers)
Intuition: Get high-level appearance Class scores: C
Run 2D CNN on each
of each frame, and combine them
frame, concatenate
Clip features: TDH’W’ MLP
features and feed to MLP
Flatten
Frame features
T x D x H’ x W’
CNN CNN CNN CNN CNN CNN
2D CNN on
each frame
Input:
T x 3 x H x W
Karpathyet al, “Large-scale Video Classification with Convolutional Neural Networks”, CVPR 2014 |
| Stanford CS231n 10th Anniversary Lecture 10 - 16 May 1, 2025 |


### Table 2

|  |
|  |


[Page contains 6 image(s)]


---
## Page 17
---


Video Classification: Late Fusion (with pooling)
Run 2D CNN on each
Intuition: Get high-level appearance Class scores: C
frame, pool features
of each frame, and combine them
and feed to Linear
Linear
Clip features: D
Average Pool over space and time
Frame features
T x D x H’ x W’
CNN CNN CNN CNN CNN CNN
2D CNN on
each
frame
Input:
T x 3 x H x W
Stanford CS231n 10th Anniversary Lecture 10 - 17 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Video Classification: Late Fusion (with pooling)
Run 2D CNN on each
Intuition: Get high-level appearance Class scores: C
frame, pool features
of each frame, and combine them
and feed to Linear
Linear
Clip features: D
Average Pool over space and time
Frame features
T x D x H’ x W’
CNN CNN CNN CNN CNN CNN
2D CNN on
each
frame
Input:
T x 3 x H x W |
| Stanford CS231n 10th Anniversary Lecture 10 - 17 May 1, 2025 |


[Page contains 6 image(s)]


---
## Page 18
---


Video Classification: Late Fusion (with pooling)
Intuition: Get high-level appearance
Run 2D CNN on each
Class scores: C
of each frame, and combine them
frame, pool features
Problem: Hard to compare low-level
and feed to Linear
motion between frames Linear
Clip features: D
Average Pool over space and time
Frame features
T x D x H’ x W’
CNN CNN CNN CNN CNN CNN
2D CNN on
each frame
Input:
T x 3 x H x W
Stanford CS231n 10th Anniversary Lecture 10 - 18 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Video Classification: Late Fusion (with pooling)
Intuition: Get high-level appearance
Run 2D CNN on each
Class scores: C
of each frame, and combine them
frame, pool features
Problem: Hard to compare low-level
and feed to Linear
motion between frames Linear
Clip features: D
Average Pool over space and time
Frame features
T x D x H’ x W’
CNN CNN CNN CNN CNN CNN
2D CNN on
each frame
Input:
T x 3 x H x W |
| Stanford CS231n 10th Anniversary Lecture 10 - 18 May 1, 2025 |


[Page contains 6 image(s)]


---
## Page 19
---


Video Classification: Early Fusion
Intuition: Compare frames
with very first conv layer, after
that normal 2D CNN
Class scores: C
Rest of the network
is standard 2D CNN
First 2D convolution
collapses all temporal 2D CNN
information:
Input: 3T x H x W
Reshape:
Output: D x H x W
3T x H x W
Input:
T x 3 x H x W
Karpathyet al, “Large-scale Video Classification with Convolutional Neural Networks”, CVPR 2014
Stanford CS231n 10th Anniversary Lecture 10 - 19 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Video Classification: Early Fusion
Intuition: Compare frames
with very first conv layer, after
that normal 2D CNN
Class scores: C
Rest of the network
is standard 2D CNN
First 2D convolution
collapses all temporal 2D CNN
information:
Input: 3T x H x W
Reshape:
Output: D x H x W
3T x H x W
Input:
T x 3 x H x W
Karpathyet al, “Large-scale Video Classification with Convolutional Neural Networks”, CVPR 2014 |
| Stanford CS231n 10th Anniversary Lecture 10 - 19 May 1, 2025 |


[Page contains 6 image(s)]


---
## Page 20
---


Video Classification: Early Fusion
Intuition: Compare frames
with very first conv layer, after
that normal 2D CNN
Class scores: C
Problem: One layer of
temporal processing may not
Rest of the network
be enough!
is standard 2D CNN
First 2D convolution
collapses all temporal 2D CNN
information:
Input: 3T x H x W
Reshape:
Output: D x H x W
3T x H x W
Input:
T x 3 x H x W
Karpathyet al, “Large-scale Video Classification with Convolutional Neural Networks”, CVPR 2014
Stanford CS231n 10th Anniversary Lecture 10 - 20 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Video Classification: Early Fusion
Intuition: Compare frames
with very first conv layer, after
that normal 2D CNN
Class scores: C
Problem: One layer of
temporal processing may not
Rest of the network
be enough!
is standard 2D CNN
First 2D convolution
collapses all temporal 2D CNN
information:
Input: 3T x H x W
Reshape:
Output: D x H x W
3T x H x W
Input:
T x 3 x H x W
Karpathyet al, “Large-scale Video Classification with Convolutional Neural Networks”, CVPR 2014 |
| Stanford CS231n 10th Anniversary Lecture 10 - 20 May 1, 2025 |


[Page contains 6 image(s)]


---
## Page 21
---


Video Classification: 3D CNN
Intuition: Use 3D versions of
convolution and pooling to
slowly fuse temporal
Class scores: C
information over the course of
the network
Each layer in the network is a 4D
tensor: D x T x H x W
3D CNN
Use 3D conv and 3D pooling
operations
Input:
3 x T x H x W
Ji et al, “3D Convolutional Neural Networks for Human Action Recognition”, TPAMI 2010 ; Karpathyet al, “Large-scale Video Classification with Convolutional Neural Networks”, CVPR 2014
Stanford CS231n 10th Anniversary Lecture 10 - 21 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Video Classification: 3D CNN
Intuition: Use 3D versions of
convolution and pooling to
slowly fuse temporal
Class scores: C
information over the course of
the network
Each layer in the network is a 4D
tensor: D x T x H x W
3D CNN
Use 3D conv and 3D pooling
operations
Input:
3 x T x H x W
Ji et al, “3D Convolutional Neural Networks for Human Action Recognition”, TPAMI 2010 ; Karpathyet al, “Large-scale Video Classification with Convolutional Neural Networks”, CVPR 2014 |
| Stanford CS231n 10th Anniversary Lecture 10 - 21 May 1, 2025 |


[Page contains 6 image(s)]


---
## Page 22
---


Convolution Layer
activation map
32x32x3 image
5x5x3 filter
32
28
convolve (slide) over all spatial
locations
28
32
3 1
Stanford CS231n 10th Anniversary Lecture 10 - 22 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Convolution Layer
activation map
32x32x3 image
5x5x3 filter
32
28
convolve (slide) over all spatial
locations
28
32
3 1 |
| Stanford CS231n 10th Anniversary Lecture 10 - 22 May 1, 2025 |


---
## Page 23
---


3D Convolution
6x6x6 conv 5x5x5 conv 4x4x4 conv
Input:
Class
FC
C x T x H x W
Scores
Layer
Stanford CS231n 10th Anniversary Lecture 10 - 23 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| 3D Convolution
6x6x6 conv 5x5x5 conv 4x4x4 conv
Input:
Class
FC
C x T x H x W
Scores
Layer |
| Stanford CS231n 10th Anniversary Lecture 10 - 23 May 1, 2025 |


---
## Page 24
---


Early Fusion vs Late Fusion vs 3D CNN
Size Receptive Field
Layer (C x T x H x W) (T x H x W)
Input 3 x 20 x 64 x 64
Late
Conv2D(3x3, 3->12) 12 x 20 x 64 x 64 1 x 3 x 3
Fusion Pool2D(4x4) 12 x 20 x 16 x 16 1 x 6 x 6
Conv2D(3x3, 12->24) 24 x 20 x 16 x 16 1 x 14 x 14
GlobalAvgPool 24 x 1 x 1 x 1 20 x 64 x 64
(Small example
architectures, in
practice much bigger)
Stanford CS231n 10th Anniversary Lecture 10 - 24 May 1, 2025

[Page contains 2 table(s)]


### Table 1

| Early Fusion vs Late Fusion vs 3D CNN
Size Receptive Field
Layer (C x T x H x W) (T x H x W)
Input 3 x 20 x 64 x 64
Late
Conv2D(3x3, 3->12) 12 x 20 x 64 x 64 1 x 3 x 3
Fusion Pool2D(4x4) 12 x 20 x 16 x 16 1 x 6 x 6
Conv2D(3x3, 12->24) 24 x 20 x 16 x 16 1 x 14 x 14
GlobalAvgPool 24 x 1 x 1 x 1 20 x 64 x 64
(Small example
architectures, in
practice much bigger) |
| Stanford CS231n 10th Anniversary Lecture 10 - 24 May 1, 2025 |


### Table 2

| Layer | Size
(C x T x H x W) | Receptive Field
(T x H x W) |
| Input | 3 x 20 x 64 x 64 |  |
| Conv2D(3x3, 3->12) | 12 x 20 x 64 x 64 | 1 x 3 x 3 |
| Pool2D(4x4) | 12 x 20 x 16 x 16 | 1 x 6 x 6 |
| Conv2D(3x3, 12->24) | 24 x 20 x 16 x 16 | 1 x 14 x 14 |
| GlobalAvgPool | 24 x 1 x 1 x 1 | 20 x 64 x 64 |


---
## Page 25
---


Early Fusion vs Late Fusion vs 3D CNN
Size Receptive Field
Layer (C x T x H x W) (T x H x W)
Input 3 x 20 x 64 x 64
Late
Conv2D(3x3, 3->12) 12 x 20 x 64 x 64 1 x 3 x 3
Fusion Pool2D(4x4) 12 x 20 x 16 x 16 1 x 6 x 6
Conv2D(3x3, 12->24) 24 x 20 x 16 x 16 1 x 14 x 14
GlobalAvgPool 24 x 1 x 1 x 1 20 x 64 x 64
Conv(3x3)
(Small example
Input
architectures, in
practice much bigger)
Stanford CS231n 10th Anniversary Lecture 10 - 25 May 1, 2025

[Page contains 2 table(s)]


### Table 1

| Early Fusion vs Late Fusion vs 3D CNN
Size Receptive Field
Layer (C x T x H x W) (T x H x W)
Input 3 x 20 x 64 x 64
Late
Conv2D(3x3, 3->12) 12 x 20 x 64 x 64 1 x 3 x 3
Fusion Pool2D(4x4) 12 x 20 x 16 x 16 1 x 6 x 6
Conv2D(3x3, 12->24) 24 x 20 x 16 x 16 1 x 14 x 14
GlobalAvgPool 24 x 1 x 1 x 1 20 x 64 x 64
Conv(3x3)
(Small example
Input
architectures, in
practice much bigger) |
| Stanford CS231n 10th Anniversary Lecture 10 - 25 May 1, 2025 |


### Table 2

| Layer | Size
(C x T x H x W) | Receptive Field
(T x H x W) |
| Input | 3 x 20 x 64 x 64 |  |
| Conv2D(3x3, 3->12) | 12 x 20 x 64 x 64 | 1 x 3 x 3 |
| Pool2D(4x4) | 12 x 20 x 16 x 16 | 1 x 6 x 6 |
| Conv2D(3x3, 12->24) | 24 x 20 x 16 x 16 | 1 x 14 x 14 |
| GlobalAvgPool | 24 x 1 x 1 x 1 | 20 x 64 x 64 |


---
## Page 26
---


Early Fusion vs Late Fusion vs 3D CNN
Size Receptive Field
Layer (C x T x H x W) (T x H x W)
Input 3 x 20 x 64 x 64
Late
Conv2D(3x3, 3->12) 12 x 20 x 64 x 64 1 x 3 x 3
Fusion Pool2D(4x4) 12 x 20 x 16 x 16 1 x 6 x 6
Conv2D(3x3, 12->24) 24 x 20 x 16 x 16 1 x 14 x 14
GlobalAvgPool 24 x 1 x 1 x 1 20 x 64 x 64
Pool(4x4)
Conv(3x3)
(Small example
Input
architectures, in
practice much bigger)
Stanford CS231n 10th Anniversary Lecture 10 - 26 May 1, 2025

[Page contains 2 table(s)]


### Table 1

| Early Fusion vs Late Fusion vs 3D CNN
Size Receptive Field
Layer (C x T x H x W) (T x H x W)
Input 3 x 20 x 64 x 64
Late
Conv2D(3x3, 3->12) 12 x 20 x 64 x 64 1 x 3 x 3
Fusion Pool2D(4x4) 12 x 20 x 16 x 16 1 x 6 x 6
Conv2D(3x3, 12->24) 24 x 20 x 16 x 16 1 x 14 x 14
GlobalAvgPool 24 x 1 x 1 x 1 20 x 64 x 64
Pool(4x4)
Conv(3x3)
(Small example
Input
architectures, in
practice much bigger) |
| Stanford CS231n 10th Anniversary Lecture 10 - 26 May 1, 2025 |


### Table 2

| Layer | Size
(C x T x H x W) | Receptive Field
(T x H x W) |
| Input | 3 x 20 x 64 x 64 |  |
| Conv2D(3x3, 3->12) | 12 x 20 x 64 x 64 | 1 x 3 x 3 |
| Pool2D(4x4) | 12 x 20 x 16 x 16 | 1 x 6 x 6 |
| Conv2D(3x3, 12->24) | 24 x 20 x 16 x 16 | 1 x 14 x 14 |
| GlobalAvgPool | 24 x 1 x 1 x 1 | 20 x 64 x 64 |


---
## Page 27
---


Early Fusion vs Late Fusion vs 3D CNN
Size Receptive Field
Layer (C x T x H x W) (T x H x W)
Input 3 x 20 x 64 x 64
Late
Conv2D(3x3, 3->12) 12 x 20 x 64 x 64 1 x 3 x 3 Build slowly in space
Fusion Pool2D(4x4) 12 x 20 x 16 x 16 1 x 6 x 6
Conv2D(3x3, 12->24) 24 x 20 x 16 x 16 1 x 14 x 14
GlobalAvgPool 24 x 1 x 1 x 1 20 x 64 x 64
Conv(3x3)
Pool(4x4)
Conv(3x3)
(Small example
Input
architectures, in
practice much bigger)
Stanford CS231n 10th Anniversary Lecture 10 - 27 May 1, 2025

[Page contains 2 table(s)]


### Table 1

| Early Fusion vs Late Fusion vs 3D CNN
Size Receptive Field
Layer (C x T x H x W) (T x H x W)
Input 3 x 20 x 64 x 64
Late
Conv2D(3x3, 3->12) 12 x 20 x 64 x 64 1 x 3 x 3 Build slowly in space
Fusion Pool2D(4x4) 12 x 20 x 16 x 16 1 x 6 x 6
Conv2D(3x3, 12->24) 24 x 20 x 16 x 16 1 x 14 x 14
GlobalAvgPool 24 x 1 x 1 x 1 20 x 64 x 64
Conv(3x3)
Pool(4x4)
Conv(3x3)
(Small example
Input
architectures, in
practice much bigger) |
| Stanford CS231n 10th Anniversary Lecture 10 - 27 May 1, 2025 |


### Table 2

| Layer | Size
(C x T x H x W) | Receptive Field
(T x H x W) |
| Input | 3 x 20 x 64 x 64 |  |
| Conv2D(3x3, 3->12) | 12 x 20 x 64 x 64 | 1 x 3 x 3 |
| Pool2D(4x4) | 12 x 20 x 16 x 16 | 1 x 6 x 6 |
| Conv2D(3x3, 12->24) | 24 x 20 x 16 x 16 | 1 x 14 x 14 |
| GlobalAvgPool | 24 x 1 x 1 x 1 | 20 x 64 x 64 |


---
## Page 28
---


Early Fusion vs Late Fusion vs 3D CNN
Size Receptive Field
Layer (C x T x H x W) (T x H x W)
Input 3 x 20 x 64 x 64
Late
Conv2D(3x3, 3->12) 12 x 20 x 64 x 64 1 x 3 x 3 Build slowly in space,
All-at-once in time at end
Fusion Pool2D(4x4) 12 x 20 x 16 x 16 1 x 6 x 6
Conv2D(3x3, 12->24) 24 x 20 x 16 x 16 1 x 14 x 14
GlobalAvgPool 24 x 1 x 1 x 1 20 x 64 x 64
GlobalAvg
Conv(3x3)
Pool(4x4)
Conv(3x3)
(Small example
Input
architectures, in
practice much bigger)
Stanford CS231n 10th Anniversary Lecture 10 - 28 May 1, 2025

[Page contains 2 table(s)]


### Table 1

| Early Fusion vs Late Fusion vs 3D CNN
Size Receptive Field
Layer (C x T x H x W) (T x H x W)
Input 3 x 20 x 64 x 64
Late
Conv2D(3x3, 3->12) 12 x 20 x 64 x 64 1 x 3 x 3 Build slowly in space,
All-at-once in time at end
Fusion Pool2D(4x4) 12 x 20 x 16 x 16 1 x 6 x 6
Conv2D(3x3, 12->24) 24 x 20 x 16 x 16 1 x 14 x 14
GlobalAvgPool 24 x 1 x 1 x 1 20 x 64 x 64
GlobalAvg
Conv(3x3)
Pool(4x4)
Conv(3x3)
(Small example
Input
architectures, in
practice much bigger) |
| Stanford CS231n 10th Anniversary Lecture 10 - 28 May 1, 2025 |


### Table 2

| Layer | Size
(C x T x H x W) | Receptive Field
(T x H x W) |
| Input | 3 x 20 x 64 x 64 |  |
| Conv2D(3x3, 3->12) | 12 x 20 x 64 x 64 | 1 x 3 x 3 |
| Pool2D(4x4) | 12 x 20 x 16 x 16 | 1 x 6 x 6 |
| Conv2D(3x3, 12->24) | 24 x 20 x 16 x 16 | 1 x 14 x 14 |
| GlobalAvgPool | 24 x 1 x 1 x 1 | 20 x 64 x 64 |


---
## Page 29
---


Early Fusion vs Late Fusion vs 3D CNN
Size Receptive Field
Layer (C x T x H x W) (T x H x W)
Input 3 x 20 x 64 x 64
Late
Conv2D(3x3, 3->12) 12 x 20 x 64 x 64 1 x 3 x 3 Build slowly in space,
All-at-once in time at end
Fusion
Pool2D(4x4) 12 x 20 x 16 x 16 1 x 6 x 6
Conv2D(3x3, 12->24) 24 x 20 x 16 x 16 1 x 14 x 14
GlobalAvgPool 24 x 1 x 1 x 1 20 x 64 x 64
Input 3 x 20 x 64 x 64
Early
Conv2D(3x3, 3*20->12) 12 x 64 x 64 20 x 3 x 3 Build slowly in space,
All-at-once in time at start
Fusion Pool2D(4x4) 12 x 16 x 16 20 x 6 x 6
Conv2D(3x3, 12->24) 24 x 16 x 16 20 x 14 x 14
GlobalAvgPool 24 x 1 x 1 20 x 64 x 64
Input 3 x 20 x 64 x 64
Conv3D(3x3x3, 3->12) 12 x 20 x 64 x 64 3 x 3 x 3 (Small example
3D
architectures, in
Pool3D(4x4x4) 12 x 5 x 16 x 16 6 x 6 x 6
practice much bigger)
CNN
Conv3D(3x3x3, 12->24) 24 x 5 x 16 x 16 14 x 14 x 14
GlobalAvgPool 24 x 1 x 1 20 x 64 x 64
Stanford CS231n 10th Anniversary Lecture 10 - 29 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Early Fusion vs Late Fusion vs 3D CNN
Size Receptive Field
Layer (C x T x H x W) (T x H x W)
Input 3 x 20 x 64 x 64
Late
Conv2D(3x3, 3->12) 12 x 20 x 64 x 64 1 x 3 x 3 Build slowly in space,
All-at-once in time at end
Fusion
Pool2D(4x4) 12 x 20 x 16 x 16 1 x 6 x 6
Conv2D(3x3, 12->24) 24 x 20 x 16 x 16 1 x 14 x 14
GlobalAvgPool 24 x 1 x 1 x 1 20 x 64 x 64
Input 3 x 20 x 64 x 64
Early
Conv2D(3x3, 3*20->12) 12 x 64 x 64 20 x 3 x 3 Build slowly in space,
All-at-once in time at start
Fusion Pool2D(4x4) 12 x 16 x 16 20 x 6 x 6
Conv2D(3x3, 12->24) 24 x 16 x 16 20 x 14 x 14
GlobalAvgPool 24 x 1 x 1 20 x 64 x 64
Input 3 x 20 x 64 x 64
Conv3D(3x3x3, 3->12) 12 x 20 x 64 x 64 3 x 3 x 3 (Small example
3D
architectures, in
Pool3D(4x4x4) 12 x 5 x 16 x 16 6 x 6 x 6
practice much bigger)
CNN
Conv3D(3x3x3, 12->24) 24 x 5 x 16 x 16 14 x 14 x 14
GlobalAvgPool 24 x 1 x 1 20 x 64 x 64 |  |  |  |  |
|  | Layer | Size
(C x T x H x W) | Receptive Field
(T x H x W) |  |
|  | Input | 3 x 20 x 64 x 64 |  |  |
|  | Conv2D(3x3, 3->12) | 12 x 20 x 64 x 64 | 1 x 3 x 3 |  |
|  | Pool2D(4x4) | 12 x 20 x 16 x 16 | 1 x 6 x 6 |  |
|  | Conv2D(3x3, 12->24) | 24 x 20 x 16 x 16 | 1 x 14 x 14 |  |
|  | GlobalAvgPool | 24 x 1 x 1 x 1 | 20 x 64 x 64 |  |
|  |  |  |  |  |
|  | Input | 3 x 20 x 64 x 64 |  |  |
|  | Conv2D(3x3, 3*20->12) | 12 x 64 x 64 | 20 x 3 x 3 |  |
|  | Pool2D(4x4) | 12 x 16 x 16 | 20 x 6 x 6 |  |
|  | Conv2D(3x3, 12->24) | 24 x 16 x 16 | 20 x 14 x 14 |  |
|  | GlobalAvgPool | 24 x 1 x 1 | 20 x 64 x 64 |  |
| 3D
CNN |  |  |  |  |
|  |  |  |  |  |
|  | Input | 3 x 20 x 64 x 64 |  |  |
|  | Conv3D(3x3x3, 3->12) | 12 x 20 x 64 x 64 | 3 x 3 x 3 |  |
|  | Pool3D(4x4x4) | 12 x 5 x 16 x 16 | 6 x 6 x 6 |  |
|  | Conv3D(3x3x3, 12->24) | 24 x 5 x 16 x 16 | 14 x 14 x 14 |  |
|  | GlobalAvgPool | 24 x 1 x 1 | 20 x 64 x 64 |  |
|  |  |  |  |  |


---
## Page 30
---


Early Fusion vs Late Fusion vs 3D CNN
Size Receptive Field
Layer (C x T x H x W) (T x H x W)
Input 3 x 20 x 64 x 64
Late
Conv2D(3x3, 3->12) 12 x 20 x 64 x 64 1 x 3 x 3 Build slowly in space,
All-at-once in time at end
Fusion Pool2D(4x4) 12 x 20 x 16 x 16 1 x 6 x 6
Conv2D(3x3, 12->24) 24 x 20 x 16 x 16 1 x 14 x 14
GlobalAvgPool 24 x 1 x 1 x 1 20 x 64 x 64
Input 3 x 20 x 64 x 64
Early
Conv2D(3x3, 3*20->12) 12 x 64 x 64 20 x 3 x 3 Build slowly in space,
All-at-once in time at start
Fusion Pool2D(4x4) 12 x 16 x 16 20 x 6 x 6
Conv2D(3x3, 12->24) 24 x 16 x 16 20 x 14 x 14
GlobalAvgPool 24 x 1 x 1 20 x 64 x 64
Input 3 x 20 x 64 x 64
Build slowly in space,
Conv3D(3x3x3, 3->12) 12 x 20 x 64 x 64 3 x 3 x 3
Build slowly in time
3D CNN (Small example
Pool3D(4x4x4) 12 x 5 x 16 x 16 6 x 6 x 6
”Slow Fusion”
architectures, in
Conv3D(3x3x3, 12->24) 24 x 5 x 16 x 16 14 x 14 x 14 practice much bigger)
GlobalAvgPool 24 x 1 x 1 20 x 64 x 64
Stanford CS231n 10th Anniversary Lecture 10 - 30 May 1, 2025

[Page contains 2 table(s)]


### Table 1

| Early Fusion vs Late Fusion vs 3D CNN
Size Receptive Field
Layer (C x T x H x W) (T x H x W)
Input 3 x 20 x 64 x 64
Late
Conv2D(3x3, 3->12) 12 x 20 x 64 x 64 1 x 3 x 3 Build slowly in space,
All-at-once in time at end
Fusion Pool2D(4x4) 12 x 20 x 16 x 16 1 x 6 x 6
Conv2D(3x3, 12->24) 24 x 20 x 16 x 16 1 x 14 x 14
GlobalAvgPool 24 x 1 x 1 x 1 20 x 64 x 64
Input 3 x 20 x 64 x 64
Early
Conv2D(3x3, 3*20->12) 12 x 64 x 64 20 x 3 x 3 Build slowly in space,
All-at-once in time at start
Fusion Pool2D(4x4) 12 x 16 x 16 20 x 6 x 6
Conv2D(3x3, 12->24) 24 x 16 x 16 20 x 14 x 14
GlobalAvgPool 24 x 1 x 1 20 x 64 x 64
Input 3 x 20 x 64 x 64
Build slowly in space,
Conv3D(3x3x3, 3->12) 12 x 20 x 64 x 64 3 x 3 x 3
Build slowly in time
3D CNN (Small example
Pool3D(4x4x4) 12 x 5 x 16 x 16 6 x 6 x 6
”Slow Fusion”
architectures, in
Conv3D(3x3x3, 12->24) 24 x 5 x 16 x 16 14 x 14 x 14 practice much bigger)
GlobalAvgPool 24 x 1 x 1 20 x 64 x 64 |
| Stanford CS231n 10th Anniversary Lecture 10 - 30 May 1, 2025 |


### Table 2

| Layer | Size
(C x T x H x W) | Receptive Field
(T x H x W) |
| Input | 3 x 20 x 64 x 64 |  |
| Conv2D(3x3, 3->12) | 12 x 20 x 64 x 64 | 1 x 3 x 3 |
| Pool2D(4x4) | 12 x 20 x 16 x 16 | 1 x 6 x 6 |
| Conv2D(3x3, 12->24) | 24 x 20 x 16 x 16 | 1 x 14 x 14 |
| GlobalAvgPool | 24 x 1 x 1 x 1 | 20 x 64 x 64 |
|  |  |  |
| Input | 3 x 20 x 64 x 64 |  |
| Conv2D(3x3, 3*20->12) | 12 x 64 x 64 | 20 x 3 x 3 |
| Pool2D(4x4) | 12 x 16 x 16 | 20 x 6 x 6 |
| Conv2D(3x3, 12->24) | 24 x 16 x 16 | 20 x 14 x 14 |
| GlobalAvgPool | 24 x 1 x 1 | 20 x 64 x 64 |
|  |  |  |
| Input | 3 x 20 x 64 x 64 |  |
| Conv3D(3x3x3, 3->12) | 12 x 20 x 64 x 64 | 3 x 3 x 3 |
| Pool3D(4x4x4) | 12 x 5 x 16 x 16 | 6 x 6 x 6 |
| Conv3D(3x3x3, 12->24) | 24 x 5 x 16 x 16 | 14 x 14 x 14 |
| GlobalAvgPool | 24 x 1 x 1 | 20 x 64 x 64 |


---
## Page 31
---


Early Fusion vs Late Fusion vs 3D CNN
What is the
Size Receptive Field
difference?
Layer (C x T x H x W) (T x H x W)
Input 3 x 20 x 64 x 64
Late
Build slowly in space,
Conv2D(3x3, 3->12) 12 x 20 x 64 x 64 1 x 3 x 3
All-at-once in time at end
Fusion Pool2D(4x4) 12 x 20 x 16 x 16 1 x 6 x 6
Conv2D(3x3, 12->24) 24 x 20 x 16 x 16 1 x 14 x 14
GlobalAvgPool 24 x 1 x 1 x 1 20 x 64 x 64
Input 3 x 20 x 64 x 64
Early
Conv2D(3x3, 3*20->12) 12 x 64 x 64 20 x 3 x 3 Build slowly in space,
All-at-once in time at start
Fusion Pool2D(4x4) 12 x 16 x 16 20 x 6 x 6
Conv2D(3x3, 12->24) 24 x 16 x 16 20 x 14 x 14
GlobalAvgPool 24 x 1 x 1 20 x 64 x 64
Input 3 x 20 x 64 x 64
Build slowly in space,
Conv3D(3x3x3, 3->12) 12 x 20 x 64 x 64 3 x 3 x 3
3D Build slowly in time (Small example
Pool3D(4x4x4) 12 x 5 x 16 x 16 6 x 6 x 6
”Slow Fusion” architectures, in
CNN
Conv3D(3x3x3, 12->24) 24 x 5 x 16 x 16 14 x 14 x 14 practice much bigger)
GlobalAvgPool 24 x 1 x 1 20 x 64 x 64
Stanford CS231n 10th Anniversary Lecture 10 - 31 May 1, 2025

[Page contains 2 table(s)]


### Table 1

| Early Fusion vs Late Fusion vs 3D CNN
What is the
Size Receptive Field
difference?
Layer (C x T x H x W) (T x H x W)
Input 3 x 20 x 64 x 64
Late
Build slowly in space,
Conv2D(3x3, 3->12) 12 x 20 x 64 x 64 1 x 3 x 3
All-at-once in time at end
Fusion Pool2D(4x4) 12 x 20 x 16 x 16 1 x 6 x 6
Conv2D(3x3, 12->24) 24 x 20 x 16 x 16 1 x 14 x 14
GlobalAvgPool 24 x 1 x 1 x 1 20 x 64 x 64
Input 3 x 20 x 64 x 64
Early
Conv2D(3x3, 3*20->12) 12 x 64 x 64 20 x 3 x 3 Build slowly in space,
All-at-once in time at start
Fusion Pool2D(4x4) 12 x 16 x 16 20 x 6 x 6
Conv2D(3x3, 12->24) 24 x 16 x 16 20 x 14 x 14
GlobalAvgPool 24 x 1 x 1 20 x 64 x 64
Input 3 x 20 x 64 x 64
Build slowly in space,
Conv3D(3x3x3, 3->12) 12 x 20 x 64 x 64 3 x 3 x 3
3D Build slowly in time (Small example
Pool3D(4x4x4) 12 x 5 x 16 x 16 6 x 6 x 6
”Slow Fusion” architectures, in
CNN
Conv3D(3x3x3, 12->24) 24 x 5 x 16 x 16 14 x 14 x 14 practice much bigger)
GlobalAvgPool 24 x 1 x 1 20 x 64 x 64 |
| Stanford CS231n 10th Anniversary Lecture 10 - 31 May 1, 2025 |


### Table 2

| Layer | Size
(C x T x H x W) | Receptive Field
(T x H x W) |
| Input | 3 x 20 x 64 x 64 |  |
| Conv2D(3x3, 3->12) | 12 x 20 x 64 x 64 | 1 x 3 x 3 |
| Pool2D(4x4) | 12 x 20 x 16 x 16 | 1 x 6 x 6 |
| Conv2D(3x3, 12->24) | 24 x 20 x 16 x 16 | 1 x 14 x 14 |
| GlobalAvgPool | 24 x 1 x 1 x 1 | 20 x 64 x 64 |
|  |  |  |
| Input | 3 x 20 x 64 x 64 |  |
| Conv2D(3x3, 3*20->12) | 12 x 64 x 64 | 20 x 3 x 3 |
| Pool2D(4x4) | 12 x 16 x 16 | 20 x 6 x 6 |
| Conv2D(3x3, 12->24) | 24 x 16 x 16 | 20 x 14 x 14 |
| GlobalAvgPool | 24 x 1 x 1 | 20 x 64 x 64 |
|  |  |  |
| Input | 3 x 20 x 64 x 64 |  |
| Conv3D(3x3x3, 3->12) | 12 x 20 x 64 x 64 | 3 x 3 x 3 |
| Pool3D(4x4x4) | 12 x 5 x 16 x 16 | 6 x 6 x 6 |
| Conv3D(3x3x3, 12->24) | 24 x 5 x 16 x 16 | 14 x 14 x 14 |
| GlobalAvgPool | 24 x 1 x 1 | 20 x 64 x 64 |


---
## Page 32
---


2D Conv (Early Fusion) vs 3D Conv (3D CNN)
Output:
Input: C x T x H x W Weight:
in
C x H x W
(3D grid with C -dim C x C x T x 3 x 3 out
in out in
2D grid with C – dim
feat at each point) Slide over x and y out
feat at each point
H = 224
T = 16
H = 224
T = 16 C different filters
out
W = 224
W = 224
Stanford CS231n 10th Anniversary Lecture 10 - 32 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| 2D Conv (Early Fusion) vs 3D Conv (3D CNN)
Output:
Input: C x T x H x W Weight:
in
C x H x W
(3D grid with C -dim C x C x T x 3 x 3 out
in out in
2D grid with C – dim
feat at each point) Slide over x and y out
feat at each point
H = 224
T = 16
H = 224
T = 16 C different filters
out
W = 224
W = 224 |
| Stanford CS231n 10th Anniversary Lecture 10 - 32 May 1, 2025 |


---
## Page 33
---


2D Conv (Early Fusion) vs 3D Conv (3D CNN)
Output:
Input: C x T x H x W Weight:
in
C x H x W
(3D grid with C -dim feat C x C x T x 3 x 3
out
in out in
2D grid with C –dim
at each point) Slide over x and y
out
feat at each point
No temporal shift-invariance!
Needs to learn separate filters for
the same motion at different times
in the clip
H = 224
C different filters
out
T = 16
W = 224
W = 224
Stanford CS231n 10th Anniversary Lecture 10 - 33 May 1, 2025

[Page contains 3 table(s)]


### Table 1

| 2D Conv (Early Fusion) vs 3D Conv (3D CNN)
Output:
Input: C x T x H x W Weight:
in
C x H x W
(3D grid with C -dim feat C x C x T x 3 x 3
out
in out in
2D grid with C –dim
at each point) Slide over x and y
out
feat at each point
No temporal shift-invariance!
Needs to learn separate filters for
the same motion at different times
in the clip
H = 224
C different filters
out
T = 16
W = 224
W = 224 |
| Stanford CS231n 10th Anniversary Lecture 10 - 33 May 1, 2025 |


### Table 2

|  |  |
|  |  |


### Table 3

|  |  |
|  |  |


---
## Page 34
---


2D Conv (Early Fusion) vs 3D Conv (3D CNN)
Output:
Input: C x T x H x W Weight:
in
C x H x W
(3D grid with C -dim feat C x C x T x 3 x 3
out
in out in
2D grid with C –dim
at each point) Slide over x and y
out
feat at each point
No temporal shift-invariance!
Needs to learn separate filters for
the same motion at different times
in the clip
H = 224
C different filters
out
T = 16
How to recognize blue to orange
W = 224
W = 224
transitions anywhere in space and time?
Stanford CS231n 10th Anniversary Lecture 10 - 34 May 1, 2025

[Page contains 3 table(s)]


### Table 1

| 2D Conv (Early Fusion) vs 3D Conv (3D CNN)
Output:
Input: C x T x H x W Weight:
in
C x H x W
(3D grid with C -dim feat C x C x T x 3 x 3
out
in out in
2D grid with C –dim
at each point) Slide over x and y
out
feat at each point
No temporal shift-invariance!
Needs to learn separate filters for
the same motion at different times
in the clip
H = 224
C different filters
out
T = 16
How to recognize blue to orange
W = 224
W = 224
transitions anywhere in space and time? |
| Stanford CS231n 10th Anniversary Lecture 10 - 34 May 1, 2025 |


### Table 2

|  |  |
|  |  |


### Table 3

|  |  |
|  |  |


---
## Page 35
---


2D Conv (Early Fusion) vs 3D Conv (3D CNN)
Output:
Input: C x T x H x W Weight:
in
C x T x H x W
(3D grid with C -dim C x C x 3 x 3 x 3
out
in out in
3D grid with C –dim
feat at each point) Slide over x and y
out
feat at each point
H = 224
T = 3
H = 224
C different filters
out
T = 16
How to recognize blue to orange
W = 224
W = 224
transitions anywhere in space and time?
Stanford CS231n 10th Anniversary Lecture 10 - 35 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| 2D Conv (Early Fusion) vs 3D Conv (3D CNN)
Output:
Input: C x T x H x W Weight:
in
C x T x H x W
(3D grid with C -dim C x C x 3 x 3 x 3
out
in out in
3D grid with C –dim
feat at each point) Slide over x and y
out
feat at each point
H = 224
T = 3
H = 224
C different filters
out
T = 16
How to recognize blue to orange
W = 224
W = 224
transitions anywhere in space and time? |
| Stanford CS231n 10th Anniversary Lecture 10 - 35 May 1, 2025 |


---
## Page 36
---


2D Conv (Early Fusion) vs 3D Conv (3D CNN)
Output:
Input: C x T x H x W Weight:
in
C x T x H x W
(3D grid with C -dim C x C x 3 x 3 x 3
out
in out in
3D grid with C –dim
feat at each point) Slide over x and y
out
feat at each point
Temporal shift-invariant since
each filter slides over time!
H = 224
T = 3
H = 224
C different filters
out
T = 16
How to recognize blue to orange
W = 224
W = 224
transitions anywhere in space and time?
Stanford CS231n 10th Anniversary Lecture 10 - 36 May 1, 2025

[Page contains 2 table(s)]


### Table 1

| 2D Conv (Early Fusion) vs 3D Conv (3D CNN)
Output:
Input: C x T x H x W Weight:
in
C x T x H x W
(3D grid with C -dim C x C x 3 x 3 x 3
out
in out in
3D grid with C –dim
feat at each point) Slide over x and y
out
feat at each point
Temporal shift-invariant since
each filter slides over time!
H = 224
T = 3
H = 224
C different filters
out
T = 16
How to recognize blue to orange
W = 224
W = 224
transitions anywhere in space and time? |
| Stanford CS231n 10th Anniversary Lecture 10 - 36 May 1, 2025 |


### Table 2

|  |  |
|  |  |


---
## Page 37
---


2D Conv (Early Fusion) vs 3D Conv (3D CNN)
Input: C x T x H x W Weight: First-layer filters have shape
in
3 (RGB) x 4 (frames) x 5 x 5
(3D grid with C -dim C x C x 3 x 3 x 3
in out in
(space)
feat at each point) Slide over x and y
Can visualize as video clips!
Temporal shift-invariant since
each filter slides over time!
T = 3
H = 224
C different filters
out
T = 16
How to recognize blue to orange
W = 224
transitions anywhere in space and time?
Stanford CS231n 10th Anniversary Lecture 10 - 37 May 1, 2025

[Page contains 2 table(s)]


### Table 1

| 2D Conv (Early Fusion) vs 3D Conv (3D CNN)
Input: C x T x H x W Weight: First-layer filters have shape
in
3 (RGB) x 4 (frames) x 5 x 5
(3D grid with C -dim C x C x 3 x 3 x 3
in out in
(space)
feat at each point) Slide over x and y
Can visualize as video clips!
Temporal shift-invariant since
each filter slides over time!
T = 3
H = 224
C different filters
out
T = 16
How to recognize blue to orange
W = 224
transitions anywhere in space and time? |
| Stanford CS231n 10th Anniversary Lecture 10 - 37 May 1, 2025 |


### Table 2

|  |  |
|  |  |


[Page contains 1 image(s)]


---
## Page 38
---


Example Video Dataset: Sports-1M
1 million YouTube videos Ground Truth
annotated with labels for 487 Correct prediction
different types of sports Incorrect prediction
Karpathyet al, “Large-scale Video Classification with Convolutional Neural Networks”, CVPR 2014
Stanford CS231n 10th Anniversary Lecture 10 - 38 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Example Video Dataset: Sports-1M
1 million YouTube videos Ground Truth
annotated with labels for 487 Correct prediction
different types of sports Incorrect prediction
Karpathyet al, “Large-scale Video Classification with Convolutional Neural Networks”, CVPR 2014 |
| Stanford CS231n 10th Anniversary Lecture 10 - 38 May 1, 2025 |


[Page contains 1 image(s)]


---
## Page 39
---


Early Fusion vs Late Fusion vs 3D CNN
Sports-1M Top-5 Accuracy
Single Frame
85
model works well –
84.4
always try this first!
80
80.2
78.7
77.7
75
76.8
3D CNNs have
improved a lot
70
since 2014!
Single Early Late 3D C3D
Frame Fusion Fusion CNN
Karpathyet al, “Large-scale Video Classification with Convolutional Neural Networks”, CVPR 2014
Stanford CS231n 10th Anniversary Lecture 10 - 39 May 1, 2025

[Page contains 5 table(s)]


### Table 1

| Early Fusion vs Late Fusion vs 3D CNN
Sports-1M Top-5 Accuracy
Single Frame
85
model works well –
84.4
always try this first!
80
80.2
78.7
77.7
75
76.8
3D CNNs have
improved a lot
70
since 2014!
Single Early Late 3D C3D
Frame Fusion Fusion CNN
Karpathyet al, “Large-scale Video Classification with Convolutional Neural Networks”, CVPR 2014 |
| Stanford CS231n 10th Anniversary Lecture 10 - 39 May 1, 2025 |


### Table 2

|  |  |  | mod
84.4
alwa |
| 80.2 |  |  |  |
|  |  |  | 3D C
impr |


### Table 3

| 78.7 |
|  |


### Table 4

| 77.7 |
|  |


### Table 5

|  |
| 76.8 |


---
## Page 40
---


C3D: The VGG of 3D CNNs Layer Size
Input 3 x 16 x 112 x 112
Conv1 (3x3x3) 64 x 16 x 112 x 112
Pool1 (1x2x2) 64 x 16 x 56 x 56
Conv2 (3x3x3) 128 x 16 x 56 x 56
3D CNN that uses all 3x3x3 conv and
Pool2 (2x2x2) 128 x 8 x 28 x 28
2x2x2 pooling
Conv3a (3x3x3) 256 x 8 x 28 x 28
(except Pool1 which is 1x2x2)
Conv3b (3x3x3) 256 x 8 x 28 x 28
Pool3 (2x2x2) 256 x 4 x 14 x 14
Released model pretrained on
Sports-1M: Many people used this as Conv4a (3x3x3) 512 x 4 x 14 x 14
a video feature extractor
Conv4b (3x3x3) 512 x 4 x 14 x 14
Pool4 (2x2x2) 512 x 2 x 7 x 7
Conv5a (3x3x3) 512 x 2 x 7 x 7
Conv5b (3x3x3) 512 x 2 x 7 x 7
Pool5 512 x 1 x 3 x 3
FC6 4096
FC7 4096
Tran et al, “Learning Spatiotemporal Features with 3D Convolutional Networks”, ICCV 2015 FC8 C
Stanford CS231n 10th Anniversary Lecture 10 - 40 May 1, 2025

[Page contains 2 table(s)]


### Table 1

| C3D: The VGG of 3D CNNs Layer Size
Input 3 x 16 x 112 x 112
Conv1 (3x3x3) 64 x 16 x 112 x 112
Pool1 (1x2x2) 64 x 16 x 56 x 56
Conv2 (3x3x3) 128 x 16 x 56 x 56
3D CNN that uses all 3x3x3 conv and
Pool2 (2x2x2) 128 x 8 x 28 x 28
2x2x2 pooling
Conv3a (3x3x3) 256 x 8 x 28 x 28
(except Pool1 which is 1x2x2)
Conv3b (3x3x3) 256 x 8 x 28 x 28
Pool3 (2x2x2) 256 x 4 x 14 x 14
Released model pretrained on
Sports-1M: Many people used this as Conv4a (3x3x3) 512 x 4 x 14 x 14
a video feature extractor
Conv4b (3x3x3) 512 x 4 x 14 x 14
Pool4 (2x2x2) 512 x 2 x 7 x 7
Conv5a (3x3x3) 512 x 2 x 7 x 7
Conv5b (3x3x3) 512 x 2 x 7 x 7
Pool5 512 x 1 x 3 x 3
FC6 4096
FC7 4096
Tran et al, “Learning Spatiotemporal Features with 3D Convolutional Networks”, ICCV 2015 FC8 C |
| Stanford CS231n 10th Anniversary Lecture 10 - 40 May 1, 2025 |


### Table 2

| Layer | Size |
| Input | 3 x 16 x 112 x 112 |
| Conv1 (3x3x3) | 64 x 16 x 112 x 112 |
| Pool1 (1x2x2) | 64 x 16 x 56 x 56 |
| Conv2 (3x3x3) | 128 x 16 x 56 x 56 |
| Pool2 (2x2x2) | 128 x 8 x 28 x 28 |
| Conv3a (3x3x3) | 256 x 8 x 28 x 28 |
| Conv3b (3x3x3) | 256 x 8 x 28 x 28 |
| Pool3 (2x2x2) | 256 x 4 x 14 x 14 |
| Conv4a (3x3x3) | 512 x 4 x 14 x 14 |
| Conv4b (3x3x3) | 512 x 4 x 14 x 14 |
| Pool4 (2x2x2) | 512 x 2 x 7 x 7 |
| Conv5a (3x3x3) | 512 x 2 x 7 x 7 |
| Conv5b (3x3x3) | 512 x 2 x 7 x 7 |
| Pool5 | 512 x 1 x 3 x 3 |
| FC6 | 4096 |
| FC7 | 4096 |
| FC8 | C |


---
## Page 41
---


C3D: The VGG of 3D CNNs
Layer Size MFLOPs
Input 3 x 16 x 112 x 112
3D CNN that uses all 3x3x3 conv and
Conv1 (3x3x3) 64 x 16 x 112 x 112 1.04
Pool1 (1x2x2) 64 x 16 x 56 x 56
2x2x2 pooling
(except Pool1 which is 1x2x2) Conv2 (3x3x3) 128 x 16 x 56 x 56 11.10
Pool2 (2x2x2) 128 x 8 x 28 x 28
Conv3a (3x3x3) 256 x 8 x 28 x 28 5.55
Released model pretrained on
Conv3b (3x3x3) 256 x 8 x 28 x 28 11.10
Sports-1M: Many people used this as
Pool3 (2x2x2) 256 x 4 x 14 x 14
a video feature extractor
Conv4a (3x3x3) 512 x 4 x 14 x 14 2.77
Conv4b (3x3x3) 512 x 4 x 14 x 14 5.55
Problem: 3x3x3 conv is very
Pool4 (2x2x2) 512 x 2 x 7 x 7
expensive!
Conv5a (3x3x3) 512 x 2 x 7 x 7 0.69
AlexNet: 0.7 GFLOP
Conv5b (3x3x3) 512 x 2 x 7 x 7 0.69
VGG-16: 13.6 GFLOP
Pool5 512 x 1 x 3 x 3
C3D: 39.5 GFLOP (2.9x VGG!) FC6 4096 0.51
FC7 4096 0.45
FC8 C 0.05
Tran et al, “Learning Spatiotemporal Features with 3D Convolutional Networks”, ICCV 2015
Stanford CS231n 10th Anniversary Lecture 10 - 41 May 1, 2025

[Page contains 2 table(s)]


### Table 1

| C3D: The VGG of 3D CNNs
Layer Size MFLOPs
Input 3 x 16 x 112 x 112
3D CNN that uses all 3x3x3 conv and
Conv1 (3x3x3) 64 x 16 x 112 x 112 1.04
Pool1 (1x2x2) 64 x 16 x 56 x 56
2x2x2 pooling
(except Pool1 which is 1x2x2) Conv2 (3x3x3) 128 x 16 x 56 x 56 11.10
Pool2 (2x2x2) 128 x 8 x 28 x 28
Conv3a (3x3x3) 256 x 8 x 28 x 28 5.55
Released model pretrained on
Conv3b (3x3x3) 256 x 8 x 28 x 28 11.10
Sports-1M: Many people used this as
Pool3 (2x2x2) 256 x 4 x 14 x 14
a video feature extractor
Conv4a (3x3x3) 512 x 4 x 14 x 14 2.77
Conv4b (3x3x3) 512 x 4 x 14 x 14 5.55
Problem: 3x3x3 conv is very
Pool4 (2x2x2) 512 x 2 x 7 x 7
expensive!
Conv5a (3x3x3) 512 x 2 x 7 x 7 0.69
AlexNet: 0.7 GFLOP
Conv5b (3x3x3) 512 x 2 x 7 x 7 0.69
VGG-16: 13.6 GFLOP
Pool5 512 x 1 x 3 x 3
C3D: 39.5 GFLOP (2.9x VGG!) FC6 4096 0.51
FC7 4096 0.45
FC8 C 0.05
Tran et al, “Learning Spatiotemporal Features with 3D Convolutional Networks”, ICCV 2015 |
| Stanford CS231n 10th Anniversary Lecture 10 - 41 May 1, 2025 |


### Table 2

| Layer | Size | MFLOPs |
| Input | 3 x 16 x 112 x 112 |  |
| Conv1 (3x3x3) | 64 x 16 x 112 x 112 | 1.04 |
| Pool1 (1x2x2) | 64 x 16 x 56 x 56 |  |
| Conv2 (3x3x3) | 128 x 16 x 56 x 56 | 11.10 |
| Pool2 (2x2x2) | 128 x 8 x 28 x 28 |  |
| Conv3a (3x3x3) | 256 x 8 x 28 x 28 | 5.55 |
| Conv3b (3x3x3) | 256 x 8 x 28 x 28 | 11.10 |
| Pool3 (2x2x2) | 256 x 4 x 14 x 14 |  |
| Conv4a (3x3x3) | 512 x 4 x 14 x 14 | 2.77 |
| Conv4b (3x3x3) | 512 x 4 x 14 x 14 | 5.55 |
| Pool4 (2x2x2) | 512 x 2 x 7 x 7 |  |
| Conv5a (3x3x3) | 512 x 2 x 7 x 7 | 0.69 |
| Conv5b (3x3x3) | 512 x 2 x 7 x 7 | 0.69 |
| Pool5 | 512 x 1 x 3 x 3 |  |
| FC6 | 4096 | 0.51 |
| FC7 | 4096 | 0.45 |
| FC8 | C | 0.05 |


---
## Page 42
---


Early Fusion vs Late Fusion vs 3D CNN
Sports-1M Top-5 Accuracy
85
84.4
80
80.2
78.7
77.7
75
76.8
70
Single Early Late 3D C3D
Frame Fusion Fusion CNN
Karpathyet al, “Large-scale Video Classification with Convolutional Neural Networks”, CVPR 2014
Tran et al, “Learning Spatiotemporal Features with 3D Convolutional Networks”, ICCV 2015
Stanford CS231n 10th Anniversary Lecture 10 - 42 May 1, 2025

[Page contains 5 table(s)]


### Table 1

| Early Fusion vs Late Fusion vs 3D CNN
Sports-1M Top-5 Accuracy
85
84.4
80
80.2
78.7
77.7
75
76.8
70
Single Early Late 3D C3D
Frame Fusion Fusion CNN
Karpathyet al, “Large-scale Video Classification with Convolutional Neural Networks”, CVPR 2014
Tran et al, “Learning Spatiotemporal Features with 3D Convolutional Networks”, ICCV 2015 |
| Stanford CS231n 10th Anniversary Lecture 10 - 42 May 1, 2025 |


### Table 2

|  |  | 84.4 |
| 80.2 |  |  |
|  |  |  |


### Table 3

| 78.7 |
|  |


### Table 4

| 77.7 |
|  |


### Table 5

|  |
| 76.8 |


---
## Page 43
---


Recognizing Actions from Motion
We can easily recognize actions using only motion information
Johansson, “Visual perception of biological motion and a model for its analysis.” Perception & Psychophysics. 14(2):201-211. 1973.
Stanford CS231n 10th Anniversary Lecture 10 - 43 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Recognizing Actions from Motion
We can easily recognize actions using only motion information
Johansson, “Visual perception of biological motion and a model for its analysis.” Perception & Psychophysics. 14(2):201-211. 1973. |
| Stanford CS231n 10th Anniversary Lecture 10 - 43 May 1, 2025 |


[Page contains 1 image(s)]


---
## Page 44
---


Measuring Motion: Optical Flow
Image at frame t
Image at frame t+1
Simonyanand Zisserman, “Two-stream convolutional networks for action recognition in videos”, NeurIPS2014
Stanford CS231n 10th Anniversary Lecture 10 - 44 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Measuring Motion: Optical Flow
Image at frame t
Image at frame t+1
Simonyanand Zisserman, “Two-stream convolutional networks for action recognition in videos”, NeurIPS2014 |
| Stanford CS231n 10th Anniversary Lecture 10 - 44 May 1, 2025 |


[Page contains 2 image(s)]


---
## Page 45
---


Measuring Motion: Optical Flow
Optical flow gives a
Image at frame t
displacement field F between
images I and I
t t+1
Tells where each pixel will
move in the next frame:
F(x, y) = (dx, dy)
I (x+dx, y+dy) = I (x, y)
t+1 t
Image at frame t+1
Simonyanand Zisserman, “Two-stream convolutional networks for action recognition in videos”, NeurIPS2014
Stanford CS231n 10th Anniversary Lecture 10 - 45 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Measuring Motion: Optical Flow
Optical flow gives a
Image at frame t
displacement field F between
images I and I
t t+1
Tells where each pixel will
move in the next frame:
F(x, y) = (dx, dy)
I (x+dx, y+dy) = I (x, y)
t+1 t
Image at frame t+1
Simonyanand Zisserman, “Two-stream convolutional networks for action recognition in videos”, NeurIPS2014 |
| Stanford CS231n 10th Anniversary Lecture 10 - 45 May 1, 2025 |


[Page contains 3 image(s)]


---
## Page 46
---


Optical Flow highlights
Measuring Motion: Optical Flow
local motion
Optical flow gives a
Horizontal flow dx
Image at frame t
displacement field F between
images I and I
t t+1
Tells where each pixel will
move in the next frame:
F(x, y) = (dx, dy)
I (x+dx, y+dy) = I (x, y)
t+1 t
Image at frame t+1 Vertical Flow dy
Simonyanand Zisserman, “Two-stream convolutional networks for action recognition in videos”, NeurIPS2014
Stanford CS231n 10th Anniversary Lecture 10 - 46 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Optical Flow highlights
Measuring Motion: Optical Flow
local motion
Optical flow gives a
Horizontal flow dx
Image at frame t
displacement field F between
images I and I
t t+1
Tells where each pixel will
move in the next frame:
F(x, y) = (dx, dy)
I (x+dx, y+dy) = I (x, y)
t+1 t
Image at frame t+1 Vertical Flow dy
Simonyanand Zisserman, “Two-stream convolutional networks for action recognition in videos”, NeurIPS2014 |
| Stanford CS231n 10th Anniversary Lecture 10 - 46 May 1, 2025 |


[Page contains 5 image(s)]


---
## Page 47
---


Separating Motion and Appearance: Two-Stream Networks
Input: Single Image
3 x H x W
Input: Stack of optical flow: Early fusion: First 2D conv
[2*(T-1)] x H x W processes all flow images
Simonyanand Zisserman, “Two-stream convolutional networks for action recognition in videos”, NeurIPS2014
Stanford CS231n 10th Anniversary Lecture 10 - 47 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Separating Motion and Appearance: Two-Stream Networks
Input: Single Image
3 x H x W
Input: Stack of optical flow: Early fusion: First 2D conv
[2*(T-1)] x H x W processes all flow images
Simonyanand Zisserman, “Two-stream convolutional networks for action recognition in videos”, NeurIPS2014 |
| Stanford CS231n 10th Anniversary Lecture 10 - 47 May 1, 2025 |


[Page contains 1 image(s)]


---
## Page 48
---


Separating Motion and Appearance: Two-Stream Networks
Accuracy on UCF-101
90
88
86.9
80
83.7
70
73
60 65.4
50
3D CNN Spatial only Temporal Two-stream Two-stream
only (fuse by (fuse by
average) SVM)
Simonyanand Zisserman, “Two-stream convolutional networks for action recognition in videos”, NeurIPS2014
Stanford CS231n 10th Anniversary Lecture 10 - 48 May 1, 2025

[Page contains 3 table(s)]


### Table 1

| Separating Motion and Appearance: Two-Stream Networks
Accuracy on UCF-101
90
88
86.9
80
83.7
70
73
60 65.4
50
3D CNN Spatial only Temporal Two-stream Two-stream
only (fuse by (fuse by
average) SVM)
Simonyanand Zisserman, “Two-stream convolutional networks for action recognition in videos”, NeurIPS2014 |
| Stanford CS231n 10th Anniversary Lecture 10 - 48 May 1, 2025 |


### Table 2

|  |  |  |  |  |  | 88 |
|  |  |  |  | 86.9 |  |  |
|  |  |  |  |  |  |  |
|  |  | 83.7 |  |  |  |  |
|  |  |  |  |  |  |  |
| 73 |  |  |  |  |  |  |
|  |  |  |  |  |  |  |


### Table 3

|  |
| 65.4 |


---
## Page 49
---


Modeling long-term temporal structure
So far all our temporal CNNs only model local
motion between frames in very short clips of ~2-5
seconds. What about long-term structure?
First event 3D Second event
CNN
Time
~5 seconds
Stanford CS231n 10th Anniversary Lecture 10 - 49 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Modeling long-term temporal structure
So far all our temporal CNNs only model local
motion between frames in very short clips of ~2-5
seconds. What about long-term structure?
First event 3D Second event
CNN
Time
~5 seconds |
| Stanford CS231n 10th Anniversary Lecture 10 - 49 May 1, 2025 |


---
## Page 50
---


Modeling long-term temporal structure
So far all our temporal CNNs only model local We know how to handle
motion between frames in very short clips of ~2-5 sequences! How about
seconds. What about long-term structure? recurrent networks?
First event 3D Second event
CNN
Time
~5 seconds
Stanford CS231n 10th Anniversary Lecture 10 - 50 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Modeling long-term temporal structure
So far all our temporal CNNs only model local We know how to handle
motion between frames in very short clips of ~2-5 sequences! How about
seconds. What about long-term structure? recurrent networks?
First event 3D Second event
CNN
Time
~5 seconds |
| Stanford CS231n 10th Anniversary Lecture 10 - 50 May 1, 2025 |


---
## Page 51
---


Modeling long-term temporal structure
Extract
features
with CNN CNN CNN CNN CNN CNN
(2D or 3D)
Time
Stanford CS231n 10th Anniversary Lecture 10 - 51 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Modeling long-term temporal structure
Extract
features
with CNN CNN CNN CNN CNN CNN
(2D or 3D)
Time |
| Stanford CS231n 10th Anniversary Lecture 10 - 51 May 1, 2025 |


---
## Page 52
---


Modeling long-term temporal structure
Process local features using recurrent network (e.g. LSTM)
Extract
features
with CNN CNN CNN CNN CNN CNN
(2D or 3D)
Time
Stanford CS231n 10th Anniversary Lecture 10 - 52 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Modeling long-term temporal structure
Process local features using recurrent network (e.g. LSTM)
Extract
features
with CNN CNN CNN CNN CNN CNN
(2D or 3D)
Time |
| Stanford CS231n 10th Anniversary Lecture 10 - 52 May 1, 2025 |


---
## Page 53
---


Modeling long-term temporal structure
Process local features using recurrent network (e.g. LSTM)
Many to one: One output at end of video
Extract
features
with CNN CNN CNN CNN CNN CNN
(2D or 3D)
Time
Stanford CS231n 10th Anniversary Lecture 10 - 53 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Modeling long-term temporal structure
Process local features using recurrent network (e.g. LSTM)
Many to one: One output at end of video
Extract
features
with CNN CNN CNN CNN CNN CNN
(2D or 3D)
Time |
| Stanford CS231n 10th Anniversary Lecture 10 - 53 May 1, 2025 |


---
## Page 54
---


Modeling long-term temporal structure
Process local features using recurrent network (e.g. LSTM)
Many to many: one output per video frame
Extract
features
with CNN CNN CNN CNN CNN CNN
(2D or 3D)
Time
Stanford CS231n 10th Anniversary Lecture 10 - 54 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Modeling long-term temporal structure
Process local features using recurrent network (e.g. LSTM)
Many to many: one output per video frame
Extract
features
with CNN CNN CNN CNN CNN CNN
(2D or 3D)
Time |
| Stanford CS231n 10th Anniversary Lecture 10 - 54 May 1, 2025 |


---
## Page 55
---


Modeling long-term temporal structure
Sometimes don’t backprop to CNN to save memory;
pretrain and use it as a feature extractor
Extract
features
with CNN CNN CNN CNN CNN CNN
(2D or 3D)
Time
Baccouche et al, "Sequential Deep Learning for Human Action Recognition”, 2011
Donahue et al, “Long-term recurrent convolutional networks for visual recognition and description”, CVPR 2015
Stanford CS231n 10th Anniversary Lecture 10 - 55 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Modeling long-term temporal structure
Sometimes don’t backprop to CNN to save memory;
pretrain and use it as a feature extractor
Extract
features
with CNN CNN CNN CNN CNN CNN
(2D or 3D)
Time
Baccouche et al, "Sequential Deep Learning for Human Action Recognition”, 2011
Donahue et al, “Long-term recurrent convolutional networks for visual recognition and description”, CVPR 2015 |
| Stanford CS231n 10th Anniversary Lecture 10 - 55 May 1, 2025 |


---
## Page 56
---


Modeling long-term temporal structure
Inside CNN: Each value is a function of a fixed temporal window (local temporal structure)
Inside RNN: Each vector is a function of all previous vectors (global temporal structure)
Can we merge both approaches?
Extract
features
with CNN CNN CNN CNN CNN CNN
(2D or 3D)
Time
Baccouche et al, "Sequential Deep Learning for Human Action Recognition”, 2011
Donahue et al, “Long-term recurrent convolutional networks for visual recognition and description”, CVPR 2015
Stanford CS231n 10th Anniversary Lecture 10 - 56 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Modeling long-term temporal structure
Inside CNN: Each value is a function of a fixed temporal window (local temporal structure)
Inside RNN: Each vector is a function of all previous vectors (global temporal structure)
Can we merge both approaches?
Extract
features
with CNN CNN CNN CNN CNN CNN
(2D or 3D)
Time
Baccouche et al, "Sequential Deep Learning for Human Action Recognition”, 2011
Donahue et al, “Long-term recurrent convolutional networks for visual recognition and description”, CVPR 2015 |
| Stanford CS231n 10th Anniversary Lecture 10 - 56 May 1, 2025 |


---
## Page 57
---


Three-layer RNN
Recall: Multi-layer RNN
y y y y y y y
0 1 2 3 4 5 6
h3 h3 h3 h3 h3 h3 h3
0 1 2 3 4 5 6
We can use a similar
h2 h2 h2 h2 h2 h2 h2
0 1 2 3 4 5 6
structure to process
videos!
h1 h1 h1 h1 h1 h1 h1
0 1 2 3 4 5 6
depth
x x x x x x x
0 1 2 3 4 5 6
time
Stanford CS231n 10th Anniversary Lecture 10 - 57 May 1, 2025

[Page contains 22 table(s)]


### Table 1

| Three-layer RNN
Recall: Multi-layer RNN
y y y y y y y
0 1 2 3 4 5 6
h3 h3 h3 h3 h3 h3 h3
0 1 2 3 4 5 6
We can use a similar
h2 h2 h2 h2 h2 h2 h2
0 1 2 3 4 5 6
structure to process
videos!
h1 h1 h1 h1 h1 h1 h1
0 1 2 3 4 5 6
depth
x x x x x x x
0 1 2 3 4 5 6
time |
| Stanford CS231n 10th Anniversary Lecture 10 - 57 May 1, 2025 |


### Table 2

|  | h3
0 |
| h3
0 | h3
0 |


### Table 3

|  |
| h3
1 |
|  |


### Table 4

|  |
| h3
2 |
|  |


### Table 5

|  | h3
3 |
| h3
3 | h3
3 |


### Table 6

|  |
| h3
4 |
|  |


### Table 7

|  | h3
5 |
| h3
5 | h3
5 |


### Table 8

|  | h3
6 |
| h3
6 | h3
6 |


### Table 9

|  | h2
0 |
| h2
0 | h2
0 |


### Table 10

|  |
| h2
1 |
|  |


### Table 11

|  |
| h2
2 |
|  |


### Table 12

|  | h2
3 |
| h2
3 | h2
3 |


### Table 13

|  |
| h2
4 |
|  |


### Table 14

|  | h2
5 |
| h2
5 | h2
5 |


### Table 15

|  | h2
6 |
| h2
6 | h2
6 |


### Table 16

|  | h1
0 |
| h1
0 | h1
0 |


### Table 17

|  |
| h1
1 |
|  |


### Table 18

|  |
| h1
2 |
|  |


### Table 19

|  | h1
3 |
| h1
3 | h1
3 |


### Table 20

|  |
| h1
4 |
|  |


### Table 21

|  | h1
5 |
| h1
5 | h1
5 |


### Table 22

|  | h1
6 |
| h1
6 | h1
6 |


---
## Page 58
---


Recurrent Convolutional Network
Entire network
uses 2D feature
maps: C x H x W
Layer 3
Each depends on
two inputs:
1. Same layer,
Layer 2
previous timestep
2. Prev layer,
same timestep
Layer 1
Use different weights
at each layer, share
2D conv 2D conv 2D conv 2D conv
weights across time
Ballas et al, “Delving Deeper into
Convolutional Networks for Learning
Video Representations”, ICLR 2016
Stanford CS231n 10th Anniversary Lecture 10 - 58 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Recurrent Convolutional Network
Entire network
uses 2D feature
maps: C x H x W
Layer 3
Each depends on
two inputs:
1. Same layer,
Layer 2
previous timestep
2. Prev layer,
same timestep
Layer 1
Use different weights
at each layer, share
2D conv 2D conv 2D conv 2D conv
weights across time
Ballas et al, “Delving Deeper into
Convolutional Networks for Learning
Video Representations”, ICLR 2016 |
| Stanford CS231n 10th Anniversary Lecture 10 - 58 May 1, 2025 |


[Page contains 4 image(s)]


---
## Page 59
---


Recurrent Convolutional Network
Normal 2D CNN:
2D Conv
Input features: Output features:
C x H x W C x H x W
Stanford CS231n 10th Anniversary Lecture 10 - 59 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Recurrent Convolutional Network
Normal 2D CNN:
2D Conv
Input features: Output features:
C x H x W C x H x W |
| Stanford CS231n 10th Anniversary Lecture 10 - 59 May 1, 2025 |


---
## Page 60
---


Recurrent Convolutional Network
Recall: Recurrent Network
new state old state
some function
with parameters W
Features from layer L,
timestep t-1
RNN-like
recurrence
Features for layer
L, timestep t
Features from layer
L-1, timestep t
Ballas et al, “Delving Deeper into Convolutional Networks for Learning Video Representations”, ICLR 2016
Stanford CS231n 10th Anniversary Lecture 10 - 60 May 1, 2025

[Page contains 3 table(s)]


### Table 1

| Recurrent Convolutional Network
Recall: Recurrent Network
new state old state
some function
with parameters W
Features from layer L,
timestep t-1
RNN-like
recurrence
Features for layer
L, timestep t
Features from layer
L-1, timestep t
Ballas et al, “Delving Deeper into Convolutional Networks for Learning Video Representations”, ICLR 2016 |
| Stanford CS231n 10th Anniversary Lecture 10 - 60 May 1, 2025 |


### Table 2

|  |  |
|  |  |


### Table 3

|  |  |  |
|  |  |  |
|  |  |  |


[Page contains 1 image(s)]


---
## Page 61
---


Recurrent Convolutional Network
Recall: Vanilla RNN
ℎ = tanh(𝑊 ℎ + 𝑊 𝑥)
!"# $ ! %
2D Conv Replace all matrix multiply
with 2D convolution!
𝑊
!
Features from layer L,
timestep t-1
tanh
+
2D Conv
𝑊
Features for layer
"
L, timestep t
Features from layer
L-1, timestep t
Ballas et al, “Delving Deeper into Convolutional Networks for Learning Video Representations”, ICLR 2016
Stanford CS231n 10th Anniversary Lecture 10 - 61 May 1, 2025

[Page contains 3 table(s)]


### Table 1

| Recurrent Convolutional Network
Recall: Vanilla RNN
ℎ = tanh(𝑊 ℎ + 𝑊 𝑥)
!"# $ ! %
2D Conv Replace all matrix multiply
with 2D convolution!
𝑊
!
Features from layer L,
timestep t-1
tanh
+
2D Conv
𝑊
Features for layer
"
L, timestep t
Features from layer
L-1, timestep t
Ballas et al, “Delving Deeper into Convolutional Networks for Learning Video Representations”, ICLR 2016 |
| Stanford CS231n 10th Anniversary Lecture 10 - 61 May 1, 2025 |


### Table 2

|  |  |
|  |  |


### Table 3

|  |  |
|  |  |


---
## Page 62
---


Modeling long-term temporal structure
Recurrent CNN: Infinite
temporal extent
RNN: Infinite
(convolutional)
temporal extent
(fully-connected)
Recurrent Recurrent
CNN: finite
CNN CNN
temporal extent
CNN CNN
(convolutional)
Time Time
Baccoucheet al, "Sequential Deep Learning for Human Action Recognition”, 2011 Ballas et al, “Delving Deeper into Convolutional Networks for
Donahue et al, “Long-term recurrent convolutional networks for visual recognition and description”, CVPR 2015 Learning Video Representations”, ICLR 2016
Stanford CS231n 10th Anniversary Lecture 10 - 62 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Modeling long-term temporal structure
Recurrent CNN: Infinite
temporal extent
RNN: Infinite
(convolutional)
temporal extent
(fully-connected)
Recurrent Recurrent
CNN: finite
CNN CNN
temporal extent
CNN CNN
(convolutional)
Time Time
Baccoucheet al, "Sequential Deep Learning for Human Action Recognition”, 2011 Ballas et al, “Delving Deeper into Convolutional Networks for
Donahue et al, “Long-term recurrent convolutional networks for visual recognition and description”, CVPR 2015 Learning Video Representations”, ICLR 2016 |
| Stanford CS231n 10th Anniversary Lecture 10 - 62 May 1, 2025 |


---
## Page 63
---


Modeling long-term temporal structure
Problem: RNNs are slow for long
sequences (can’t be parallelized) Recurrent CNN: Infinite
temporal extent
RNN: Infinite
(convolutional)
temporal extent
(fully-connected)
Recurrent Recurrent
CNN: finite
CNN CNN
temporal extent
CNN CNN
(convolutional)
Time Time
Baccoucheet al, "Sequential Deep Learning for Human Action Recognition”, 2011 Ballas et al, “Delving Deeper into Convolutional Networks for
Donahue et al, “Long-term recurrent convolutional networks for visual recognition and description”, CVPR 2015 Learning Video Representations”, ICLR 2016
Stanford CS231n 10th Anniversary Lecture 10 - 63 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Modeling long-term temporal structure
Problem: RNNs are slow for long
sequences (can’t be parallelized) Recurrent CNN: Infinite
temporal extent
RNN: Infinite
(convolutional)
temporal extent
(fully-connected)
Recurrent Recurrent
CNN: finite
CNN CNN
temporal extent
CNN CNN
(convolutional)
Time Time
Baccoucheet al, "Sequential Deep Learning for Human Action Recognition”, 2011 Ballas et al, “Delving Deeper into Convolutional Networks for
Donahue et al, “Long-term recurrent convolutional networks for visual recognition and description”, CVPR 2015 Learning Video Representations”, ICLR 2016 |
| Stanford CS231n 10th Anniversary Lecture 10 - 63 May 1, 2025 |


---
## Page 64
---


Recall: Self-Attention
mul(→) + add (↑)
Stanford CS231n 10th Anniversary Lecture 10 - May 1, 2025
tnemngilA
q
0
noitnettA
y y y
0 1 2
Outputs:
context vectors: y (shape: D )
v
a a a
0,0 0,1 0,2
a a a
1,0 1,1 1,2 Operations:
Key vectors: k = xW
k a a a
2,0 2,1 2,2
Value vectors: v = xW
v
Query vectors: q = xW
q
softmax (↑)
Alignment: e = q ᐧ k / √D
i,j j i
Attention: a = softmax(e)
Output: y = ∑ a v
x 0 e 0,0 e 0,1 e 0,2 j i i,j i
x e e e
1 1,0 1,1 1,2
x e e e
2 2,0 2,1 2,2
Inputs:
Input vectors: x (shape: N x D)
q q
1 2
srotcev
tupnI
v
0
y y y
0 1 2
v
1
v self-attention
2
x x x
0 1 2
k 0
k
1
k
2
64

[Page contains 13 table(s)]


### Table 1

| Recall: Self-Attention
y y y
0 1 2
Outputs:
context vectors: y (shape: D )
v
mul(→) + add (↑)
a a a v
0,0 0,1 0,2 0
noitnettA
y y y
0 1 2
a a a v
1,0 1,1 1,2 Operations: 1
Key vectors: k = xW
k a a a v self-attention
2,0 2,1 2,2 2
Value vectors: v = xW
v
Query vectors: q = xW
q
softmax (↑) x x x
Alignment: e = q ᐧ k / √D 0 1 2
i,j j i
srotcev
Attention: a = softmax(e)
Output: y = ∑ a v
tnemngilA x 0 e 0,0 e 0,1 e 0,2 j i i,j i k 0
x e e e tupnI k
1 1,0 1,1 1,2 1
x e e e k
2 2,0 2,1 2,2 2
Inputs:
Input vectors: x (shape: N x D)
q q q
0 1 2 |
| Stanford CS231n 10th Anniversary Lecture 10 - 64 May 1, 2025 |


### Table 2

| y
1 | y
2 |


### Table 3

|  | mul(→) + add (↑)
v a a a
0 0,0 0,1 0,2
noitnettA
v a a a
1 1,0 1,1 1,2
v a a a
2 2,0 2,1 2,2
softmax (↑)
k e e e
tnemngilA 0 0,0 0,1 0,2
k e e e
1 1,0 1,1 1,2
k e e e
2 2,0 2,1 2,2
q q q
0 1 2 |
| x
0
x
1
x
2 |  |


### Table 4

| a
0,1 | a
0,2 |


### Table 5

| y
0 | y
1 | y
2 |


### Table 6

| a
1,1 | a
1,2 |


### Table 7

| a
2,1 | a
2,2 |


### Table 8

| x
0 | x
1 |


### Table 9

| x
0 |
| x
1 |
| x
2 |


### Table 10

| k
0 |
| k
1 |
| k
2 |


### Table 11

| e
0,0 |
| e
1,0 |
| e
2,0 |


### Table 12

| e
0,1 | e
0,2 |
| e
1,1 | e
1,2 |
| e
2,1 | e
2,2 |


### Table 13

| q
1 | q
2 |


---
## Page 65
---


Spatio-Temporal Self-Attention (Nonlocal Block)
Input clip
3D
CNN
Features:
C x T x H x W
Nonlocal Block
Wang et al, “Non-local neural networks”, CVPR 2018
Stanford CS231n 10th Anniversary Lecture 10 - 65 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Spatio-Temporal Self-Attention (Nonlocal Block)
Input clip
3D
CNN
Features:
C x T x H x W
Nonlocal Block
Wang et al, “Non-local neural networks”, CVPR 2018 |
| Stanford CS231n 10th Anniversary Lecture 10 - 65 May 1, 2025 |


[Page contains 4 image(s)]


---
## Page 66
---


Spatio-Temporal Self-Attention (Nonlocal Block)
Input clip
Queries:
C’ x T x H x W
1x1x1 Conv
Keys:
3D C’ x T x H x W
CNN
1x1x1 Conv
Features:
C x T x H x W
Values:
C’ x T x H x W
1x1x1 Conv
Nonlocal Block
Wang et al, “Non-local neural networks”, CVPR 2018
Stanford CS231n 10th Anniversary Lecture 10 - 66 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Spatio-Temporal Self-Attention (Nonlocal Block)
Input clip
Queries:
C’ x T x H x W
1x1x1 Conv
Keys:
3D C’ x T x H x W
CNN
1x1x1 Conv
Features:
C x T x H x W
Values:
C’ x T x H x W
1x1x1 Conv
Nonlocal Block
Wang et al, “Non-local neural networks”, CVPR 2018 |
| Stanford CS231n 10th Anniversary Lecture 10 - 66 May 1, 2025 |


[Page contains 4 image(s)]


---
## Page 67
---


Spatio-Temporal Self-Attention (Nonlocal Block)
Input clip
Attention Weights
Queries:
(THW) x (THW)
Transpose
C’ x T x H x W
1x1x1 Conv
softmax
x
Keys:
3D C’ x T x H x W
CNN
1x1x1 Conv
Features:
C x T x H x W
Values:
C’ x T x H x W
1x1x1 Conv
Nonlocal Block
Wang et al, “Non-local neural networks”, CVPR 2018
Stanford CS231n 10th Anniversary Lecture 10 - 67 May 1, 2025

[Page contains 3 table(s)]


### Table 1

| Spatio-Temporal Self-Attention (Nonlocal Block)
Input clip
Attention Weights
Queries:
(THW) x (THW)
Transpose
C’ x T x H x W
1x1x1 Conv
softmax
x
Keys:
3D C’ x T x H x W
CNN
1x1x1 Conv
Features:
C x T x H x W
Values:
C’ x T x H x W
1x1x1 Conv
Nonlocal Block
Wang et al, “Non-local neural networks”, CVPR 2018 |
| Stanford CS231n 10th Anniversary Lecture 10 - 67 May 1, 2025 |


### Table 2

|  |  |
|  |  |


### Table 3

|  |  |
|  |  |


[Page contains 4 image(s)]


---
## Page 68
---


Spatio-Temporal Self-Attention (Nonlocal Block)
Input clip
Attention Weights
Queries:
(THW) x (THW)
Transpose
C’ x T x H x W
1x1x1 Conv
softmax
x
Keys:
3D C’ x T x H x W
CNN
1x1x1 Conv
Features:
C x T x H x W
C’ x T x H x W
Values:
C’ x T x H x W
x
1x1x1 Conv
Nonlocal Block
Wang et al, “Non-local neural networks”, CVPR 2018
Stanford CS231n 10th Anniversary Lecture 10 - 68 May 1, 2025

[Page contains 3 table(s)]


### Table 1

| Spatio-Temporal Self-Attention (Nonlocal Block)
Input clip
Attention Weights
Queries:
(THW) x (THW)
Transpose
C’ x T x H x W
1x1x1 Conv
softmax
x
Keys:
3D C’ x T x H x W
CNN
1x1x1 Conv
Features:
C x T x H x W
C’ x T x H x W
Values:
C’ x T x H x W
x
1x1x1 Conv
Nonlocal Block
Wang et al, “Non-local neural networks”, CVPR 2018 |
| Stanford CS231n 10th Anniversary Lecture 10 - 68 May 1, 2025 |


### Table 2

|  |  |
|  |  |


### Table 3

|  |  |
|  |  |


[Page contains 4 image(s)]


---
## Page 69
---


Spatio-Temporal Self-Attention (Nonlocal Block)
Input clip
Attention Weights
Queries:
(THW) x (THW)
Transpose
C’ x T x H x W
1x1x1 Conv
softmax
x
C x T x H x W
Keys:
3D C’ x T x H x W
CNN
1x1x1 Conv
Features:
C x T x H x W
C’ x T x H x W
Values:
C’ x T x H x W
x
1x1x1 Conv
1x1x1 Conv
Nonlocal Block
Wang et al, “Non-local neural networks”, CVPR 2018
Stanford CS231n 10th Anniversary Lecture 10 - 69 May 1, 2025

[Page contains 4 table(s)]


### Table 1

| Spatio-Temporal Self-Attention (Nonlocal Block)
Input clip
Attention Weights
Queries:
(THW) x (THW)
Transpose
C’ x T x H x W
1x1x1 Conv
softmax
x
C x T x H x W
Keys:
3D C’ x T x H x W
CNN
1x1x1 Conv
Features:
C x T x H x W
C’ x T x H x W
Values:
C’ x T x H x W
x
1x1x1 Conv
1x1x1 Conv
Nonlocal Block
Wang et al, “Non-local neural networks”, CVPR 2018 |
| Stanford CS231n 10th Anniversary Lecture 10 - 69 May 1, 2025 |


### Table 2

|  |  |
|  |  |


### Table 3

|  |  |
|  |  |


### Table 4

|  |  |
|  |  |


[Page contains 4 image(s)]


---
## Page 70
---


Spatio-Temporal Self-Attention (Nonlocal Block)
Input clip Residual Connection
Attention Weights
Queries:
(THW) x (THW)
Transpose
C’ x T x H x W
1x1x1 Conv
softmax
x
C x T x H x W
Keys:
3D C’ x T x H x W +
CNN
1x1x1 Conv
Features:
C x T x H x W
C’ x T x H x W
Values:
C’ x T x H x W
x
1x1x1 Conv
1x1x1 Conv
Nonlocal Block
Wang et al, “Non-local neural networks”, CVPR 2018
Stanford CS231n 10th Anniversary Lecture 10 - 70 May 1, 2025

[Page contains 5 table(s)]


### Table 1

| Spatio-Temporal Self-Attention (Nonlocal Block)
Input clip Residual Connection
Attention Weights
Queries:
(THW) x (THW)
Transpose
C’ x T x H x W
1x1x1 Conv
softmax
x
C x T x H x W
Keys:
3D C’ x T x H x W +
CNN
1x1x1 Conv
Features:
C x T x H x W
C’ x T x H x W
Values:
C’ x T x H x W
x
1x1x1 Conv
1x1x1 Conv
Nonlocal Block
Wang et al, “Non-local neural networks”, CVPR 2018 |
| Stanford CS231n 10th Anniversary Lecture 10 - 70 May 1, 2025 |


### Table 2

|  |  |  |
|  |  |  |


### Table 3

|  |  |
|  |  |


### Table 4

|  |  |
|  |  |


### Table 5

|  |  |
|  |  |


[Page contains 4 image(s)]


---
## Page 71
---


Spatio-Temporal Self-Attention (Nonlocal Block)
Input clip
We can add nonlocal blocks into existing 3D CNN architectures.
But what is the best 3D CNN architecture?
Residual Connection Residual Connection
Queries: Attention Weights Queries: Attention Weights
C’ x T x H x W Transpose (THW) x (THW) C’ x T x H x W Transpose (THW) x (THW)
1x1x1 Conv 1x1x1 Conv
softmax softmax
3D CNN x x
Keys: C x T x H x W 3D CNN Keys: C x T x H x W 3D CNN Running
C’ x T x H x W + C’ x T x H x W +
Features: 1x1x1 Conv Features: 1x1x1 Conv
C x T x H x W C’ x T x H x W C x T x H x W C’ x T x H x W
Values: Values:
C’ x T x H x W x 1x1x1 Conv C’ x T x H x W x 1x1x1 Conv
1x1x1 Conv 1x1x1 Conv
Nonlocal Block Nonlocal Block
Wang et al, “Non-local neural networks”, CVPR 2018
Stanford CS231n 10th Anniversary Lecture 10 - 71 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Spatio-Temporal Self-Attention (Nonlocal Block)
Input clip
We can add nonlocal blocks into existing 3D CNN architectures.
But what is the best 3D CNN architecture?
Residual Connection Residual Connection
Queries: Attention Weights Queries: Attention Weights
C’ x T x H x W Transpose (THW) x (THW) C’ x T x H x W Transpose (THW) x (THW)
1x1x1 Conv 1x1x1 Conv
softmax softmax
3D CNN x x
Keys: C x T x H x W 3D CNN Keys: C x T x H x W 3D CNN Running
C’ x T x H x W + C’ x T x H x W +
Features: 1x1x1 Conv Features: 1x1x1 Conv
C x T x H x W C’ x T x H x W C x T x H x W C’ x T x H x W
Values: Values:
C’ x T x H x W x 1x1x1 Conv C’ x T x H x W x 1x1x1 Conv
1x1x1 Conv 1x1x1 Conv
Nonlocal Block Nonlocal Block
Wang et al, “Non-local neural networks”, CVPR 2018 |
| Stanford CS231n 10th Anniversary Lecture 10 - 71 May 1, 2025 |


[Page contains 4 image(s)]


---
## Page 72
---


Inflating 2D Networks to 3D (I3D)
There has been a lot of work on architectures for images.
Can we reuse image architectures for video?
Idea: take a 2D CNN architecture.
Replace each 2D K x K conv/pool
h w
layer with a 3D K x K x K version
t h w
Carreiraand Zisserman, “Quo Vadis, Action Recognition? A New Model and the Kinetics Dataset”, CVPR 2017
Stanford CS231n 10th Anniversary Lecture 10 - 72 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Inflating 2D Networks to 3D (I3D)
There has been a lot of work on architectures for images.
Can we reuse image architectures for video?
Idea: take a 2D CNN architecture.
Replace each 2D K x K conv/pool
h w
layer with a 3D K x K x K version
t h w
Carreiraand Zisserman, “Quo Vadis, Action Recognition? A New Model and the Kinetics Dataset”, CVPR 2017 |
| Stanford CS231n 10th Anniversary Lecture 10 - 72 May 1, 2025 |


---
## Page 73
---


Inflating 2D Networks to 3D (I3D)
There has been a lot of work on architectures for images.
Can we reuse image architectures for video?
Idea: take a 2D CNN architecture. Inception Block: Original
Replace each 2D K x K conv/pool
Concatenate
h w
layer with a 3D K x K x K version
t h w
5x5 Conv 3x3 Conv 1x1 Conv
1x1 Conv
3x3
1x1 Conv 1x1 Conv
MaxPool
Previous layer
Carreiraand Zisserman, “Quo Vadis, Action Recognition? A New Model and the Kinetics Dataset”, CVPR 2017
Stanford CS231n 10th Anniversary Lecture 10 - 73 May 1, 2025

[Page contains 4 table(s)]


### Table 1

| Inflating 2D Networks to 3D (I3D)
There has been a lot of work on architectures for images.
Can we reuse image architectures for video?
Idea: take a 2D CNN architecture. Inception Block: Original
Replace each 2D K x K conv/pool
Concatenate
h w
layer with a 3D K x K x K version
t h w
5x5 Conv 3x3 Conv 1x1 Conv
1x1 Conv
3x3
1x1 Conv 1x1 Conv
MaxPool
Previous layer
Carreiraand Zisserman, “Quo Vadis, Action Recognition? A New Model and the Kinetics Dataset”, CVPR 2017 |
| Stanford CS231n 10th Anniversary Lecture 10 - 73 May 1, 2025 |


### Table 2

|  |  |
|  |  |


### Table 3

|  |  |
|  |  |


### Table 4

|  |  |  |  |
|  |  |  |  |


---
## Page 74
---


Inflating 2D Networks to 3D (I3D)
There has been a lot of work on architectures for images.
Can we reuse image architectures for video?
Idea: take a 2D CNN architecture. Inception Block: Inflated
Replace each 2D K x K conv/pool
Concatenate
h w
layer with a 3D K x K x K version
t h w
5x5x5 3x3x3 1x1x1
Conv Conv Conv
1x1x1
Conv
1x1x1 1x1x1 3x3x3
Conv Conv MaxPool
Previous layer
Carreiraand Zisserman, “Quo Vadis, Action Recognition? A New Model and the Kinetics Dataset”, CVPR 2017
Stanford CS231n 10th Anniversary Lecture 10 - 74 May 1, 2025

[Page contains 4 table(s)]


### Table 1

| Inflating 2D Networks to 3D (I3D)
There has been a lot of work on architectures for images.
Can we reuse image architectures for video?
Idea: take a 2D CNN architecture. Inception Block: Inflated
Replace each 2D K x K conv/pool
Concatenate
h w
layer with a 3D K x K x K version
t h w
5x5x5 3x3x3 1x1x1
Conv Conv Conv
1x1x1
Conv
1x1x1 1x1x1 3x3x3
Conv Conv MaxPool
Previous layer
Carreiraand Zisserman, “Quo Vadis, Action Recognition? A New Model and the Kinetics Dataset”, CVPR 2017 |
| Stanford CS231n 10th Anniversary Lecture 10 - 74 May 1, 2025 |


### Table 2

|  |  |
|  |  |


### Table 3

|  |  |
|  |  |


### Table 4

|  |  |  |  |
|  |  |  |  |


---
## Page 75
---


Inflating 2D Networks to 3D (I3D)
There has been a lot of work on architectures for images.
Can we reuse image architectures for video?
Input: 2D conv kernel: Output:
Idea: take a 2D CNN architecture.
3 x H x W C x K x K H x W
in h w
Replace each 2D K x K conv/pool
h w
layer with a 3D K x K x K version
t h w
Duplicate input K Copy kernel K Output is the
t t
times times, divide same!
Can use weights of 2D conv to by K
t
initialize 3D conv: copy K times in
t
space and divide by K
t
This gives the same result as 2D conv
given “constant” video input
Input: 3D conv kernel: Output:
3 x K x H x W C x K x K x K 1 x H x W
t in t h w
Carreiraand Zisserman, “Quo Vadis, Action Recognition? A New Model and the Kinetics Dataset”, CVPR 2017
Stanford CS231n 10th Anniversary Lecture 10 - 75 May 1, 2025

[Page contains 2 table(s)]


### Table 1

| Inflating 2D Networks to 3D (I3D)
There has been a lot of work on architectures for images.
Can we reuse image architectures for video?
Input: 2D conv kernel: Output:
Idea: take a 2D CNN architecture.
3 x H x W C x K x K H x W
in h w
Replace each 2D K x K conv/pool
h w
layer with a 3D K x K x K version
t h w
Duplicate input K Copy kernel K Output is the
t t
times times, divide same!
Can use weights of 2D conv to by K
t
initialize 3D conv: copy K times in
t
space and divide by K
t
This gives the same result as 2D conv
given “constant” video input
Input: 3D conv kernel: Output:
3 x K x H x W C x K x K x K 1 x H x W
t in t h w
Carreiraand Zisserman, “Quo Vadis, Action Recognition? A New Model and the Kinetics Dataset”, CVPR 2017 |
| Stanford CS231n 10th Anniversary Lecture 10 - 75 May 1, 2025 |


### Table 2

|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |


[Page contains 4 image(s)]


---
## Page 76
---


Inflating 2D Networks to 3D (I3D)
There has been a lot of work on architectures for images.
Can we reuse image architectures for video?
Top-1 Accuracy on Kinetics-400
Idea: take a 2D CNN architecture.
80
75
Replace each 2D K x K conv/pool
h w
70 74.2
layer with a 3D K x K x K version 71.1 71.6
t h w 65
68.4
65.6
60
63.3 62.8
62.2
Can use weights of 2D conv to 55
57.9
50 53.9
initialize 3D conv: copy K times in
t
45
space and divide by K
t 40
This gives the same result as 2D conv
Per-frame CNN+LSTM Two-stream Inflated CNN Two-stream
CNN CNN inflated CNN
given “constant” video input
Train from scratch Pretrain on ImageNet
All using Inception CNN
Carreiraand Zisserman, “Quo Vadis, Action Recognition? A New Model and the Kinetics Dataset”, CVPR 2017
Stanford CS231n 10th Anniversary Lecture 10 - 76 May 1, 2025

[Page contains 2 table(s)]


### Table 1

| Inflating 2D Networks to 3D (I3D)
There has been a lot of work on architectures for images.
Can we reuse image architectures for video?
Top-1 Accuracy on Kinetics-400
Idea: take a 2D CNN architecture.
80
75
Replace each 2D K x K conv/pool
h w
70 74.2
layer with a 3D K x K x K version 71.1 71.6
t h w 65
68.4
65.6
60
63.3 62.8
62.2
Can use weights of 2D conv to 55
57.9
50 53.9
initialize 3D conv: copy K times in
t
45
space and divide by K
t 40
This gives the same result as 2D conv
Per-frame CNN+LSTM Two-stream Inflated CNN Two-stream
CNN CNN inflated CNN
given “constant” video input
Train from scratch Pretrain on ImageNet
All using Inception CNN
Carreiraand Zisserman, “Quo Vadis, Action Recognition? A New Model and the Kinetics Dataset”, CVPR 2017 |
| Stanford CS231n 10th Anniversary Lecture 10 - 76 May 1, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  | 71.1 |  | 71.6 |  | 74.2 |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  | 65.6 |  | 68.4 |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  | 62.2 |  |  |  | 63.3 |  | 62.8 |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| 57.9 |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  | 53.9 |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |


---
## Page 77
---


Vision Transformers for Video
Factorized attention: Pooling module: Video masked autoencoders:
Attend over space / time Reduce number of tokens Efficient scalable pretraining
Wangetal.VideoMAEV2:ScalingVideoMasked
AutoencoderswithDualMaking.CVPR2023.
Fan et al, “Multiscale Vision Transformers”, ICCV 2021
Bertasiuset al, “Is Space-Time Attention All You Need for Video Tongetal.VideoMAE:MaskedAutoencodersareData-
Li et al, “MViTv2: Improved Multiscale Vision
Understanding?”, ICML2021 EfficientLearnersforSelf-SupervisedVideoPre-Training.
Transformers for Classification and Detection”, CVPR
Arnab et al, “ViViT: A Video Vision Transformer”, ICCV 2021 NeurIPS2022.
2022
Neimarket al, “Video Transformer Network”, ICCV 2021 Feichtenhoferetal.Maskedautoencodersas
spatiotemporallearners.NeurIPS2022.
Stanford CS231n 10th Anniversary Lecture 10 - 77 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Vision Transformers for Video
Factorized attention: Pooling module: Video masked autoencoders:
Attend over space / time Reduce number of tokens Efficient scalable pretraining
Wangetal.VideoMAEV2:ScalingVideoMasked
AutoencoderswithDualMaking.CVPR2023.
Fan et al, “Multiscale Vision Transformers”, ICCV 2021
Bertasiuset al, “Is Space-Time Attention All You Need for Video Tongetal.VideoMAE:MaskedAutoencodersareData-
Li et al, “MViTv2: Improved Multiscale Vision
Understanding?”, ICML2021 EfficientLearnersforSelf-SupervisedVideoPre-Training.
Transformers for Classification and Detection”, CVPR
Arnab et al, “ViViT: A Video Vision Transformer”, ICCV 2021 NeurIPS2022.
2022
Neimarket al, “Video Transformer Network”, ICCV 2021 Feichtenhoferetal.Maskedautoencodersas
spatiotemporallearners.NeurIPS2022. |
| Stanford CS231n 10th Anniversary Lecture 10 - 77 May 1, 2025 |


[Page contains 3 image(s)]


---
## Page 78
---


Vision Transformers for Video
Top-1 Accuracy on Kinetics-400
100 90
86.1
90
79.8
74.2
80 71.1
65.6
62.2 63.3
70
60
50
40
30
20
10
0
Per-frame CNN+LSTM Two-Stream I3D Inflated I3D SlowFast MViTv2-L VideoMAE
CNN CNN 16x8+NL V2-g
Stanford CS231n 10th Anniversary Lecture 10 - 78 May 1, 2025

[Page contains 2 table(s)]


### Table 1

| Vision Transformers for Video
Top-1 Accuracy on Kinetics-400
100 90
86.1
90
79.8
74.2
80 71.1
65.6
62.2 63.3
70
60
50
40
30
20
10
0
Per-frame CNN+LSTM Two-Stream I3D Inflated I3D SlowFast MViTv2-L VideoMAE
CNN CNN 16x8+NL V2-g |
| Stanford CS231n 10th Anniversary Lecture 10 - 78 May 1, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |


---
## Page 79
---


Visualizing Video Models
Forward: Compute class score
Image
”weightlifting
” score
Flow
Backward: Compute gradient
Add a term to encourage spatially
Figure credit: Simonyanand Zisserman, “Two-stream convolutional networks for action recognition in videos”, NeurIPS2014
smooth flow; tune penalty to pick out
Feichtenhoferet al, “What have we learned from deep representations for action recognition?”, CVPR 2018
Feichtenhoferet al, “Deep insights into convolutional networks for video recognition?”, IJCV 2019.
“slow” vs “fast” motion
Stanford CS231n 10th Anniversary Lecture 10 - 79 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Visualizing Video Models
Forward: Compute class score
Image
”weightlifting
” score
Flow
Backward: Compute gradient
Add a term to encourage spatially
Figure credit: Simonyanand Zisserman, “Two-stream convolutional networks for action recognition in videos”, NeurIPS2014
smooth flow; tune penalty to pick out
Feichtenhoferet al, “What have we learned from deep representations for action recognition?”, CVPR 2018
Feichtenhoferet al, “Deep insights into convolutional networks for video recognition?”, IJCV 2019.
“slow” vs “fast” motion |
| Stanford CS231n 10th Anniversary Lecture 10 - 79 May 1, 2025 |


[Page contains 1 image(s)]


---
## Page 80
---


Can you guess the action?
Feichtenhoferet al, “What have we learned from deep
representations for action recognition?”, CVPR 2018
Feichtenhoferet al, “Deep insights into convolutional
networks for video recognition?”, IJCV 2019.
Slide credit: Christoph Feichtenhofers
Appearance “Slow” motion “Fast” motion
Fast motion appearance
Stanford CS231n 10th Anniversary Lecture 10 - 80 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Can you guess the action?
Feichtenhoferet al, “What have we learned from deep
representations for action recognition?”, CVPR 2018
Feichtenhoferet al, “Deep insights into convolutional
networks for video recognition?”, IJCV 2019.
Slide credit: Christoph Feichtenhofers
Appearance “Slow” motion “Fast” motion
Fast motion appearance |
| Stanford CS231n 10th Anniversary Lecture 10 - 80 May 1, 2025 |


[Page contains 3 image(s)]


---
## Page 81
---


Can you guess the action? Weightlifting
Appearance “Slow” motion “Fast” motion
”Bar Shaking” “Push overhead”
Fast motion appearance
Stanford CS231n 10th Anniversary Lecture 10 - 81 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Can you guess the action? Weightlifting
Appearance “Slow” motion “Fast” motion
”Bar Shaking” “Push overhead”
Fast motion appearance |
| Stanford CS231n 10th Anniversary Lecture 10 - 81 May 1, 2025 |


[Page contains 7 image(s)]


---
## Page 82
---


Can you guess the action?
Appearance “Slow” motion “Fast” motion
”Bar Shaking” “Push overhead”
FFaasstt mmoottiioonn aappppeeaarraannccee
Stanford CS231n 10th Anniversary Lecture 10 - 82 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Can you guess the action?
Appearance “Slow” motion “Fast” motion
”Bar Shaking” “Push overhead”
FFaasstt mmoottiioonn aappppeeaarraannccee |
| Stanford CS231n 10th Anniversary Lecture 10 - 82 May 1, 2025 |


[Page contains 3 image(s)]


---
## Page 83
---


Can you guess the action? Apply Eye Makeup
Appearance “Slow” motion “Fast” motion
”Bar Shaking” “Push overhead”
FFaasstt mmoottiioonn aappppeeaarraannccee
Stanford CS231n 10th Anniversary Lecture 10 - 83 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Can you guess the action? Apply Eye Makeup
Appearance “Slow” motion “Fast” motion
”Bar Shaking” “Push overhead”
FFaasstt mmoottiioonn aappppeeaarraannccee |
| Stanford CS231n 10th Anniversary Lecture 10 - 83 May 1, 2025 |


[Page contains 7 image(s)]


---
## Page 84
---


So far: Classify short clips
Swimming
Videos: Recognize actions
Running
Jumping
Eating
Standing
Stanford CS231n 10th Anniversary Lecture 10 - 84 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| So far: Classify short clips
Swimming
Videos: Recognize actions
Running
Jumping
Eating
Standing |
| Stanford CS231n 10th Anniversary Lecture 10 - 84 May 1, 2025 |


[Page contains 1 image(s)]


---
## Page 85
---


Temporal Action Localization
Given a long untrimmed video sequence, identify
frames corresponding to different actions
Running Jumping
Can use architecture similar to Faster R-CNN: first
generate temporal proposals then classify
Chao et al, ” Rethinking the Faster R-CNN Architecture for Temporal Action Localization”, CVPR 2018
Stanford CS231n 10th Anniversary Lecture 10 - 85 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Temporal Action Localization
Given a long untrimmed video sequence, identify
frames corresponding to different actions
Running Jumping
Can use architecture similar to Faster R-CNN: first
generate temporal proposals then classify
Chao et al, ” Rethinking the Faster R-CNN Architecture for Temporal Action Localization”, CVPR 2018 |
| Stanford CS231n 10th Anniversary Lecture 10 - 85 May 1, 2025 |


[Page contains 17 image(s)]


---
## Page 86
---


Spatio-Temporal Detection
Given a long untrimmed video, detect all the people in both
space and time and classify the activities they are performing.
Some examples from AVA Dataset:
Gu et al, “AVA: A Video Dataset of Spatio-temporally Localized Atomic Visual Actions”, CVPR 2018
Stanford CS231n 10th Anniversary Lecture 10 - 86 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Spatio-Temporal Detection
Given a long untrimmed video, detect all the people in both
space and time and classify the activities they are performing.
Some examples from AVA Dataset:
Gu et al, “AVA: A Video Dataset of Spatio-temporally Localized Atomic Visual Actions”, CVPR 2018 |
| Stanford CS231n 10th Anniversary Lecture 10 - 86 May 1, 2025 |


[Page contains 1 image(s)]


---
## Page 87
---


Today: Temporal Stream
…
…
3D CNN, Two-Stream Neural Network, Spatial-Temporal Self-Attention……
Stanford CS231n 10th Anniversary Lecture 10 - 87 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Today: Temporal Stream
…
…
3D CNN, Two-Stream Neural Network, Spatial-Temporal Self-Attention…… |
| Stanford CS231n 10th Anniversary Lecture 10 - 87 May 1, 2025 |


[Page contains 5 image(s)]


---
## Page 88
---


Stanford CS231n 10th Anniversary Lecture 10 - May 1, 2025

[Page contains 1 table(s)]


### Table 1

|  |
| Stanford CS231n 10th Anniversary Lecture 10 - May 1, 2025 |


[Page contains 2 image(s)]


---
## Page 89
---


Ba Ba Ba …
Stanford CS231n 10th Anniversary Lectu(rMec 1G0u-rk & McDoMnaayl d1 ,1 2907265)
Video source: BBC

[Page contains 1 table(s)]


### Table 1

| Ba Ba Ba … |
| Stanford CS231n 10th Anniversary Lectu(rMec 1G0u-rk & McDoMnaayl d1 ,1 2907265)
Video source: BBC |


[Page contains 3 image(s)]


---
## Page 90
---


Multisensory fusion
Fa Fa Fa …
Stanford CS231n 10th Anniversary Lectu(rMec 1G0u-rk & McDoMnaayl d1 ,1 2907265)
Video source: BBC

[Page contains 1 table(s)]


### Table 1

| Fa Fa Fa … |
| Stanford CS231n 10th Anniversary Lectu(rMec 1G0u-rk & McDoMnaayl d1 ,1 2907265)
Video source: BBC |


[Page contains 3 image(s)]


---
## Page 91
---


(McGurk & McDonald 1976)
Stanford CS231n 10th Anniversary Lectu(rMec 1G0u-rk & McDoMnaayl d1 ,1 2907265)
Video source: BBC

[Page contains 1 table(s)]


### Table 1

|  |
| (McGurk & McDonald 1976)
Stanford CS231n 10th Anniversary Lectu(rMec 1G0u-rk & McDoMnaayl d1 ,1 2907265)
Video source: BBC |


[Page contains 5 image(s)]


---
## Page 92
---


Visually-guided audio source separation
[Gao et al. ECCV 2018, Afouras et al. Interspeech’18, Gabby et al. Interspeech’18, Owens & Efros ECCV’18, Ephrat et al.
SIGGRAPH’18, Zhao et al. ECCV 2018, Gao & Grauman ICCV 2019, Zhao et al. ICCV 2019, Xu et al. ICCV 2019, Gan et al.
CVPR 2020, Gao et al. CVPR 2021, Tzinis et al. ECCV 2022, Chen et al. CVPR 2023]
Stanford CS231n 10th Anniversary Lecture 10 - 92 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Visually-guided audio source separation
[Gao et al. ECCV 2018, Afouras et al. Interspeech’18, Gabby et al. Interspeech’18, Owens & Efros ECCV’18, Ephrat et al.
SIGGRAPH’18, Zhao et al. ECCV 2018, Gao & Grauman ICCV 2019, Zhao et al. ICCV 2019, Xu et al. ICCV 2019, Gan et al.
CVPR 2020, Gao et al. CVPR 2021, Tzinis et al. ECCV 2022, Chen et al. CVPR 2023] |
| Stanford CS231n 10th Anniversary Lecture 10 - 92 May 1, 2025 |


[Page contains 14 image(s)]


---
## Page 93
---


Speech mixture
Stanford CS231n 10th Anniversary Lecture 10 - May 1, 2025
Gao et al., VisualVoice, CVPR 2021

[Page contains 1 table(s)]


### Table 1

| Speech mixture |
| Stanford CS231n 10th Anniversary Lecture 10 - May 1, 2025
Gao et al., VisualVoice, CVPR 2021 |


[Page contains 1 image(s)]


---
## Page 94
---


Separated voice for the left speaker
Stanford CS231n 10th Anniversary Lecture 10 - May 1, 2025
Gao et al., VisualVoice, CVPR 2021

[Page contains 1 table(s)]


### Table 1

| Separated voice for the left speaker |
| Stanford CS231n 10th Anniversary Lecture 10 - May 1, 2025
Gao et al., VisualVoice, CVPR 2021 |


[Page contains 1 image(s)]


---
## Page 95
---


Separated voice for the right speaker
Stanford CS231n 10th Anniversary Lecture 10 - May 1, 2025
Gao et al., VisualVoice, CVPR 2021

[Page contains 1 table(s)]


### Table 1

| Separated voice for the right speaker |
| Stanford CS231n 10th Anniversary Lecture 10 - May 1, 2025
Gao et al., VisualVoice, CVPR 2021 |


[Page contains 1 image(s)]


---
## Page 96
---


Musical instruments source separation
Train on 100,000 unlabeled multi-source video clips,
then separate audio for novel video.
Gao & Grauman, Co-Separating Sounds of Visual Objects, ICCV 2019
Stanford CS231n 10th Anniversary Lecture 10 - 96 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Musical instruments source separation
Train on 100,000 unlabeled multi-source video clips,
then separate audio for novel video.
Gao & Grauman, Co-Separating Sounds of Visual Objects, ICCV 2019 |
| Stanford CS231n 10th Anniversary Lecture 10 - 96 May 1, 2025 |


[Page contains 3 image(s)]


---
## Page 97
---


Audio-Visual Video Understanding
Attention Bottlenecks for Multimodal Fusion, Nagrani et al. NeurIPS 2021
Audio-Adaptive Activity Recognition Across Video Domains,
Audio-Visual Masked Autoencoders. Georgescu et al. ICCV 2023.
Zhang et al. CVPR 2022
Stanford CS231n 10th Anniversary Lecture 10 - 97 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Audio-Visual Video Understanding
Attention Bottlenecks for Multimodal Fusion, Nagrani et al. NeurIPS 2021
Audio-Adaptive Activity Recognition Across Video Domains,
Audio-Visual Masked Autoencoders. Georgescu et al. ICCV 2023.
Zhang et al. CVPR 2022 |
| Stanford CS231n 10th Anniversary Lecture 10 - 97 May 1, 2025 |


[Page contains 3 image(s)]


---
## Page 98
---


Efficient Video Understanding
Action recognition in long videos
Image Credit: Korbar et al.
Stanford CS231n 10th Anniversary Lecture 10 - 98 May 1, 2025
98

[Page contains 1 table(s)]


### Table 1

| Efficient Video Understanding
Action recognition in long videos
Image Credit: Korbar et al. |
| Stanford CS231n 10th Anniversary Lecture 10 - 98 May 1, 2025
98 |


[Page contains 1 image(s)]


---
## Page 99
---


Efficient Video Understanding
MoViNets: Mobile Video Networks for Efficient Video Recognition.
SCSampler: Sampling Salient Clips from Video for
Kondratyuk et al. CVPR 2021
Efficient Action Recognition. Korbar et al. ICCV 2019
X3D: Expanding Architecture for Efficient Video Recognition.
AdaMML: Adaptive Multi-Modal Learning for Efficient Video
Christoph Feichtenhofer. CVPR 2020.
Recognition. Pandal et al. ICCV 2021
Stanford CS231n 10th Anniversary Lecture 10 - 99 May 1, 2025
99

[Page contains 1 table(s)]


### Table 1

| Efficient Video Understanding
MoViNets: Mobile Video Networks for Efficient Video Recognition.
SCSampler: Sampling Salient Clips from Video for
Kondratyuk et al. CVPR 2021
Efficient Action Recognition. Korbar et al. ICCV 2019
X3D: Expanding Architecture for Efficient Video Recognition.
AdaMML: Adaptive Multi-Modal Learning for Efficient Video
Christoph Feichtenhofer. CVPR 2020.
Recognition. Pandal et al. ICCV 2021 |
| Stanford CS231n 10th Anniversary Lecture 10 - 99 May 1, 2025
99 |


[Page contains 4 image(s)]


---
## Page 100
---


h
!
I(⋅)
y
r
e u Q
IndexI
LSTM
IndexA
QueryA(⋅)
Stanford CS231n 10th Anniversary Lecture 10 - May 1, 2025
Fusion
layer
𝐈 z# h
$
! ! $
LSTM
𝐀 z#
!
Fusion
layer
Efficient Video Understanding
Image feature
𝐈 z#
!%$
h
!
Step 𝒕 Step 𝑡+1
𝑨 z#
!%$
Audio feature
Audio as a preview mechanism for efficient action recognition
Gao et al., Listen to Look: Action Recognition by Previewing Audio, CVPR 2020
100

[Page contains 3 table(s)]


### Table 1

| Efficient Video Understanding
Image feature
h 𝐈 z# h 𝐈 z#
$
! ! ! $ !%$
I(⋅)
y
r
e u Q Fusion Fusion h
IndexI
!
Step 𝒕 Step 𝑡+1
LSTM LSTM
IndexA
layer layer
QueryA(⋅)
𝐀 z# 𝑨 z#
! !%$
Audio feature
Audio as a preview mechanism for efficient action recognition
Gao et al., Listen to Look: Action Recognition by Previewing Audio, CVPR 2020 |
| Stanford CS231n 10th Anniversary Lecture 10 - 100 May 1, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |


### Table 3

|  |  |  |  |


[Page contains 24 image(s)]


---
## Page 101
---


Multimodal Egocentric Video Understanding
Camera
Microphone array
T
Ego-Exo Conversational Graph Prediction
The Audio-Visual Conversational Graph: From and Egocentric-Exocentric Perspective. Jia et al. CVPR 2024
Stanford CS231n 10th Anniversary Lecture 10 - 101 May 1, 2025

[Page contains 2 table(s)]


### Table 1

| Multimodal Egocentric Video Understanding
Camera
Microphone array
T
Ego-Exo Conversational Graph Prediction
The Audio-Visual Conversational Graph: From and Egocentric-Exocentric Perspective. Jia et al. CVPR 2024 |
| Stanford CS231n 10th Anniversary Lecture 10 - 101 May 1, 2025 |


### Table 2

|  |  |  |
|  |  |  |
|  |  |  |


[Page contains 10 image(s)]


---
## Page 102
---


Video Understanding + LLMs
Video-LLaVA: Learning United Visual Representations
by Alignment Before Projection. Lin et al. EMNLP 2024
VideoLLaMA 3: Frontier Multimodal Foundation Models
for Video Understanding. Zhang et al. arXiv 2025
Video-ChatGPT: Towards Detailed Video Understanding via
Large Vision and Language Models. Maaz et al. ACL 2024.
Stanford CS231n 10th Anniversary Lecture 10 - 102 May 1, 2025
102

[Page contains 1 table(s)]


### Table 1

| Video Understanding + LLMs
Video-LLaVA: Learning United Visual Representations
by Alignment Before Projection. Lin et al. EMNLP 2024
VideoLLaMA 3: Frontier Multimodal Foundation Models
for Video Understanding. Zhang et al. arXiv 2025
Video-ChatGPT: Towards Detailed Video Understanding via
Large Vision and Language Models. Maaz et al. ACL 2024. |
| Stanford CS231n 10th Anniversary Lecture 10 - 102 May 1, 2025
102 |


[Page contains 3 image(s)]


---
## Page 103
---


Next time: Large Scale Distributed Training
Stanford CS231n 10th Anniversary Lecture 10 - 103 May 1, 2025

[Page contains 1 table(s)]


### Table 1

| Next time: Large Scale Distributed Training |
| Stanford CS231n 10th Anniversary Lecture 10 - 103 May 1, 2025 |
