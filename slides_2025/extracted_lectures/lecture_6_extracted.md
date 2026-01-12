# lecture_6

Extracted using pdfplumber



---
## Page 1
---


Lecture 6:
Training CNNs and CNN
Architectures
Stanford CS231n 10th Anniversary Lecture 6 - 1 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture 6:
Training CNNs and CNN
Architectures |
| Stanford CS231n 10th Anniversary Lecture 6 - 1 April 17, 2025 |


---
## Page 2
---


Course Logistics
● Assignment 1 is due next Wednesday (4/23) at 11:59PM!
● Project proposal deadline is due on Friday next week (4/25)
Stanford CS231n 10th Anniversary Lecture 6 - 2 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Course Logistics
● Assignment 1 is due next Wednesday (4/23) at 11:59PM!
● Project proposal deadline is due on Friday next week (4/25) |
| Stanford CS231n 10th Anniversary Lecture 6 - 2 April 17, 2025 |


---
## Page 3
---


Lecture Overview – Two Broad Sets of Topics
Layers in CNNs
Activation Functions
How to build CNNs?
CNN Architectures
Weight Initialization
Data Preprocessing
Data augmentation
How to train CNNs?
Transfer Learning
Hyperparameter Selection
Stanford CS231n 10th Anniversary Lecture 6 - 3 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture Overview – Two Broad Sets of Topics
Layers in CNNs
Activation Functions
How to build CNNs?
CNN Architectures
Weight Initialization
Data Preprocessing
Data augmentation
How to train CNNs?
Transfer Learning
Hyperparameter Selection |
| Stanford CS231n 10th Anniversary Lecture 6 - 3 April 17, 2025 |


---
## Page 4
---


Lecture Overview – Two Broad Sets of Topics
Layers in CNNs
Activation Functions
How to build CNNs?
CNN Architectures
Weight Initialization
Data Preprocessing
Data augmentation
How to train CNNs?
Transfer Learning
Hyperparameter Selection
Stanford CS231n 10th Anniversary Lecture 6 - 4 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture Overview – Two Broad Sets of Topics
Layers in CNNs
Activation Functions
How to build CNNs?
CNN Architectures
Weight Initialization
Data Preprocessing
Data augmentation
How to train CNNs?
Transfer Learning
Hyperparameter Selection |
| Stanford CS231n 10th Anniversary Lecture 6 - 4 April 17, 2025 |


---
## Page 5
---


Lecture Overview – Two Broad Sets of Topics
Layers in CNNs
Activation Functions
How to build CNNs?
CNN Architectures
Weight Initialization
Data Preprocessing
Data augmentation
How to train CNNs?
Transfer Learning
Hyperparameter Selection
Stanford CS231n 10th Anniversary Lecture 6 - 5 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture Overview – Two Broad Sets of Topics
Layers in CNNs
Activation Functions
How to build CNNs?
CNN Architectures
Weight Initialization
Data Preprocessing
Data augmentation
How to train CNNs?
Transfer Learning
Hyperparameter Selection |
| Stanford CS231n 10th Anniversary Lecture 6 - 5 April 17, 2025 |


---
## Page 6
---


Recap: Convolution Layer
6 activation maps,
each 1x28x28
3x32x32 image Don’t forget bias terms!
Activation
Function!
Convolution
Layer
(ReLU)
32
6x3x5x5
32
Stack activations to get a
filters
3
6x28x28 output image!
Slide inspiration: Justin Johnson
Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
6

[Page contains 2 table(s)]


### Table 1

| Recap: Convolution Layer
6 activation maps,
each 1x28x28
3x32x32 image Don’t forget bias terms!
Activation
Function!
Convolution
Layer
(ReLU)
32
6x3x5x5
32
Stack activations to get a
filters
3
6x28x28 output image!
Slide inspiration: Justin Johnson |
| Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
6 |


### Table 2

|  |  |  |  |  |  |


---
## Page 7
---


Recap: Pooling Layer
Single depth slice
6 8
Max
1 1 2 4
x 3 4 Pooling
pool with 2x2 filters and
5 6 7 8
stride 2
3 2 1 0
3.25 5.25
1 2 3 4
Average
Pooling
2 2
y
Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
7

[Page contains 4 table(s)]


### Table 1

| Recap: Pooling Layer
Single depth slice
6 8
Max
1 1 2 4
x 3 4 Pooling
pool with 2x2 filters and
5 6 7 8
stride 2
3 2 1 0
3.25 5.25
1 2 3 4
Average
Pooling
2 2
y |
| Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
7 |


### Table 2

| 6 | 8 |
| 3 | 4 |


### Table 3

| 1 | 1 | 2 | 4 |
| 5 | 6 | 7 | 8 |
| 3 | 2 | 1 | 0 |
| 1 | 2 | 3 | 4 |


### Table 4

| 3.25 | 5.25 |
| 2 | 2 |


---
## Page 8
---


Components of CNNs
Convolution Layers Pooling Layers Fully-Connected Layers
x
h s
Normalization Layers Dropout Activation Functions
(sometimes)
𝑥 − 𝜇
!,# #
𝑥! =
!,#
$
𝜎 + 𝜀
#
Stanford CS231n 10th Anniversary Lecture 6 - 8 April 17, 2025

[Page contains 3 table(s)]


### Table 1

| Components of CNNs
Convolution Layers Pooling Layers Fully-Connected Layers
x
h s
Normalization Layers Dropout Activation Functions
(sometimes)
𝑥 − 𝜇
!,# #
𝑥! =
!,#
$
𝜎 + 𝜀
# |
| Stanford CS231n 10th Anniversary Lecture 6 - 8 April 17, 2025 |


### Table 2

|  |
|  |


### Table 3

| x | h s |


[Page contains 2 image(s)]


---
## Page 9
---


Components of CNNs
Convolution Layers Pooling Layers Fully-Connected Layers
x
h s
Normalization Layers Dropout Activation Functions
(sometimes)
𝑥 − 𝜇
!,# #
𝑥! =
!,#
$
𝜎 + 𝜀
#
Stanford CS231n 10th Anniversary Lecture 6 - 9 April 17, 2025

[Page contains 3 table(s)]


### Table 1

| Components of CNNs
Convolution Layers Pooling Layers Fully-Connected Layers
x
h s
Normalization Layers Dropout Activation Functions
(sometimes)
𝑥 − 𝜇
!,# #
𝑥! =
!,#
$
𝜎 + 𝜀
# |
| Stanford CS231n 10th Anniversary Lecture 6 - 9 April 17, 2025 |


### Table 2

|  |
|  |


### Table 3

| x | h s |


[Page contains 2 image(s)]


---
## Page 10
---


Example Normalization Layer: LayerNorm
High-level Idea: Learn parameters that let us scale / shift the input data
1. Normalize input data
2. Scale / shift using learned parameters
Ba, Kiros, and Hinton, “Layer Normalization”, arXiv 2016
Stanford CS231n 10th Anniversary Lecture 6 - 10 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Example Normalization Layer: LayerNorm
High-level Idea: Learn parameters that let us scale / shift the input data
1. Normalize input data
2. Scale / shift using learned parameters
Ba, Kiros, and Hinton, “Layer Normalization”, arXiv 2016 |
| Stanford CS231n 10th Anniversary Lecture 6 - 10 April 17, 2025 |


---
## Page 11
---


Example Normalization Layer: LayerNorm
High-level Idea: Learn parameters that let us scale / shift the input data
1. Normalize input data
2. Scale / shift using learned parameters
x: N × D
Normalize
𝞵 𝝈
, : N × 1
Statistics calculated per batch à
ɣ,β: 1 × D
Learned parameters applied to each sample à
𝞵 𝝈
y = ɣ(x- )/ +β
Ba, Kiros, and Hinton, “Layer Normalization”, arXiv 2016
Stanford CS231n 10th Anniversary Lecture 6 - 11 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Example Normalization Layer: LayerNorm
High-level Idea: Learn parameters that let us scale / shift the input data
1. Normalize input data
2. Scale / shift using learned parameters
x: N × D
Normalize
𝞵 𝝈
, : N × 1
Statistics calculated per batch à
ɣ,β: 1 × D
Learned parameters applied to each sample à
𝞵 𝝈
y = ɣ(x- )/ +β
Ba, Kiros, and Hinton, “Layer Normalization”, arXiv 2016 |
| Stanford CS231n 10th Anniversary Lecture 6 - 11 April 17, 2025 |


---
## Page 12
---


Other Normalization Layers
You will implement some of these in assignment 2!
Wu and He, “Group Normalization”, ECCV 2018
Stanford CS231n 10th Anniversary Lecture 6 - 12 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Other Normalization Layers
You will implement some of these in assignment 2!
Wu and He, “Group Normalization”, ECCV 2018 |
| Stanford CS231n 10th Anniversary Lecture 6 - 12 April 17, 2025 |


[Page contains 1 image(s)]


---
## Page 13
---


Components of CNNs
Convolution Layers Pooling Layers Fully-Connected Layers
x
h s
Normalization Layers Dropout Activation Functions
(sometimes)
𝑥 − 𝜇
!,# #
𝑥! =
!,#
$
𝜎 + 𝜀
#
Stanford CS231n 10th Anniversary Lecture 6 - 13 April 17, 2025

[Page contains 3 table(s)]


### Table 1

| Components of CNNs
Convolution Layers Pooling Layers Fully-Connected Layers
x
h s
Normalization Layers Dropout Activation Functions
(sometimes)
𝑥 − 𝜇
!,# #
𝑥! =
!,#
$
𝜎 + 𝜀
# |
| Stanford CS231n 10th Anniversary Lecture 6 - 13 April 17, 2025 |


### Table 2

|  |
|  |


### Table 3

| x | h s |


[Page contains 2 image(s)]


---
## Page 14
---


Components of CNNs
Convolution Layers Pooling Layers Fully-Connected Layers
x
h s
Normalization Layers Dropout Activation Functions
(sometimes)
𝑥 − 𝜇
!,# #
𝑥! =
!,#
$
𝜎 + 𝜀
#
Stanford CS231n 10th Anniversary Lecture 6 - 14 April 17, 2025

[Page contains 3 table(s)]


### Table 1

| Components of CNNs
Convolution Layers Pooling Layers Fully-Connected Layers
x
h s
Normalization Layers Dropout Activation Functions
(sometimes)
𝑥 − 𝜇
!,# #
𝑥! =
!,#
$
𝜎 + 𝜀
# |
| Stanford CS231n 10th Anniversary Lecture 6 - 14 April 17, 2025 |


### Table 2

|  |
|  |


### Table 3

| x | h s |


[Page contains 2 image(s)]


---
## Page 15
---


Regularization: Dropout
In each forward pass, randomly set some neurons to zero
Probability of dropping is a hyperparameter; 0.5 is common
Srivastava et al, “Dropout: A simple way to prevent neural networks from overfitting”, JMLR 2014
Stanford CS231n 10th Anniversary Lecture 6 - 15 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Regularization: Dropout
In each forward pass, randomly set some neurons to zero
Probability of dropping is a hyperparameter; 0.5 is common
Srivastava et al, “Dropout: A simple way to prevent neural networks from overfitting”, JMLR 2014 |
| Stanford CS231n 10th Anniversary Lecture 6 - 15 April 17, 2025 |


---
## Page 16
---


Regularization: Dropout
How can this possibly be a good idea?
Forces the network to have a redundant representation;
Prevents co-adaptation of features
has an ear
X
has a tail
X
cat
is furry
score
has claws
mischievous X
look
Stanford CS231n 10th Anniversary Lecture 6 - 16 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Regularization: Dropout
How can this possibly be a good idea?
Forces the network to have a redundant representation;
Prevents co-adaptation of features
has an ear
X
has a tail
X
cat
is furry
score
has claws
mischievous X
look |
| Stanford CS231n 10th Anniversary Lecture 6 - 16 April 17, 2025 |


---
## Page 17
---


Regularization: Dropout
How can this possibly be a good idea?
Another interpretation:
Dropout is training a large ensemble of
models (that share parameters).
Each binary mask is one model
An FC layer with 4096 units has
24096 ~ 101233 possible masks!
Only ~ 1082 atoms in the universe...
Stanford CS231n 10th Anniversary Lecture 6 - 17 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Regularization: Dropout
How can this possibly be a good idea?
Another interpretation:
Dropout is training a large ensemble of
models (that share parameters).
Each binary mask is one model
An FC layer with 4096 units has
24096 ~ 101233 possible masks!
Only ~ 1082 atoms in the universe... |
| Stanford CS231n 10th Anniversary Lecture 6 - 17 April 17, 2025 |


---
## Page 18
---


Dropout: Test time
At test time all neurons are active always
=> We must scale the activations so that for each neuron:
output at test time = expected output at training time
Stanford CS231n 10th Anniversary Lecture 6 - 18 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Dropout: Test time
At test time all neurons are active always
=> We must scale the activations so that for each neuron:
output at test time = expected output at training time |
| Stanford CS231n 10th Anniversary Lecture 6 - 18 April 17, 2025 |


[Page contains 1 image(s)]


---
## Page 19
---


Dropout Summary
drop in train time
scale at test time
Stanford CS231n 10th Anniversary Lecture 6 - 19 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Dropout Summary
drop in train time
scale at test time |
| Stanford CS231n 10th Anniversary Lecture 6 - 19 April 17, 2025 |


[Page contains 1 image(s)]


---
## Page 20
---


Lecture Overview – Two Broad Sets of Topics
Layers in CNNs
Activation Functions
How to build CNNs?
CNN Architectures
Weight Initialization
Data Preprocessing
Data augmentation
How to train CNNs?
Transfer Learning
Hyperparameter Selection
Stanford CS231n 10th Anniversary Lecture 6 - 20 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture Overview – Two Broad Sets of Topics
Layers in CNNs
Activation Functions
How to build CNNs?
CNN Architectures
Weight Initialization
Data Preprocessing
Data augmentation
How to train CNNs?
Transfer Learning
Hyperparameter Selection |
| Stanford CS231n 10th Anniversary Lecture 6 - 20 April 17, 2025 |


---
## Page 21
---


Components of CNNs
Convolution Layers Pooling Layers Fully-Connected Layers
x
h s
Normalization Layers Dropout Activation Functions
(sometimes)
𝑥 − 𝜇
!,# #
𝑥! =
!,#
$
𝜎 + 𝜀
#
Stanford CS231n 10th Anniversary Lecture 6 - 21 April 17, 2025

[Page contains 3 table(s)]


### Table 1

| Components of CNNs
Convolution Layers Pooling Layers Fully-Connected Layers
x
h s
Normalization Layers Dropout Activation Functions
(sometimes)
𝑥 − 𝜇
!,# #
𝑥! =
!,#
$
𝜎 + 𝜀
# |
| Stanford CS231n 10th Anniversary Lecture 6 - 21 April 17, 2025 |


### Table 2

|  |
|  |


### Table 3

| x | h s |


[Page contains 2 image(s)]


---
## Page 22
---


Components of CNNs
Convolution Layers Pooling Layers Fully-Connected Layers
x
h s
Normalization Layers Dropout Activation Functions
(sometimes)
𝑥 − 𝜇
Goal: Introduce non-
!,# #
𝑥! =
!,#
linearities to our model!
$
𝜎 + 𝜀
#
Stanford CS231n 10th Anniversary Lecture 6 - 22 April 17, 2025

[Page contains 3 table(s)]


### Table 1

| Components of CNNs
Convolution Layers Pooling Layers Fully-Connected Layers
x
h s
Normalization Layers Dropout Activation Functions
(sometimes)
𝑥 − 𝜇
Goal: Introduce non-
!,# #
𝑥! =
!,#
linearities to our model!
$
𝜎 + 𝜀
# |
| Stanford CS231n 10th Anniversary Lecture 6 - 22 April 17, 2025 |


### Table 2

|  |
|  |


### Table 3

| x | h s |


[Page contains 2 image(s)]


---
## Page 23
---


Activation Functions
- Squashes numbers to range [0,1]
- Historically popular since they
have nice interpretation as a
saturating “firing rate” of a neuron
Key problem:
Many layers of sigmoids à smaller
Sigmoid and smaller gradients.
Q: In which regions does sigmoid
have a small gradient?
Stanford CS231n 10th Anniversary Lecture 6 - 23 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Activation Functions
- Squashes numbers to range [0,1]
- Historically popular since they
have nice interpretation as a
saturating “firing rate” of a neuron
Key problem:
Many layers of sigmoids à smaller
Sigmoid and smaller gradients.
Q: In which regions does sigmoid
have a small gradient? |
| Stanford CS231n 10th Anniversary Lecture 6 - 23 April 17, 2025 |


[Page contains 2 image(s)]


---
## Page 24
---


Activation Functions
- Squashes numbers to range [0,1]
- Historically popular since they
have nice interpretation as a
saturating “firing rate” of a neuron
Key problem:
Large positive or negative values
Sigmoid can “kill” the gradients. Many layers
of sigmoids à smaller and smaller
gradients in practice
Stanford CS231n 10th Anniversary Lecture 6 - 24 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Activation Functions
- Squashes numbers to range [0,1]
- Historically popular since they
have nice interpretation as a
saturating “firing rate” of a neuron
Key problem:
Large positive or negative values
Sigmoid can “kill” the gradients. Many layers
of sigmoids à smaller and smaller
gradients in practice |
| Stanford CS231n 10th Anniversary Lecture 6 - 24 April 17, 2025 |


[Page contains 2 image(s)]


---
## Page 25
---


- Computes f(x) = max(0,x)
Activation Functions
- Does not saturate (in +region)
- Very computationally efficient
- Converges much faster than
sigmoid in practice (e.g. 6x)
ReLU
(Rectified Linear Unit)
[Krizhevsky et al., 2012]
Stanford CS231n 10th Anniversary Lecture 6 - 25 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| - Computes f(x) = max(0,x)
Activation Functions
- Does not saturate (in +region)
- Very computationally efficient
- Converges much faster than
sigmoid in practice (e.g. 6x)
ReLU
(Rectified Linear Unit)
[Krizhevsky et al., 2012] |
| Stanford CS231n 10th Anniversary Lecture 6 - 25 April 17, 2025 |


[Page contains 1 image(s)]


---
## Page 26
---


- Computes f(x) = max(0,x)
Activation Functions
- Does not saturate (in +region)
- Very computationally efficient
- Converges much faster than
sigmoid in practice (e.g. 6x)
- Not zero-centered output
ReLU - An annoyance:
(Rectified Linear Unit)
Dead ReLUs when x < 0!
Stanford CS231n 10th Anniversary Lecture 6 - 26 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| - Computes f(x) = max(0,x)
Activation Functions
- Does not saturate (in +region)
- Very computationally efficient
- Converges much faster than
sigmoid in practice (e.g. 6x)
- Not zero-centered output
ReLU - An annoyance:
(Rectified Linear Unit)
Dead ReLUs when x < 0! |
| Stanford CS231n 10th Anniversary Lecture 6 - 26 April 17, 2025 |


[Page contains 1 image(s)]


---
## Page 27
---


[Hendrycks et al., 2016]
Activation Functions
- Computes f(x) = x*Φ(x)
- Very nice behavior around 0
- Smoothness facilitates training in
practice
- Higher computational cost than ReLU
- Large negative values can still have
Source: https://en.m.wikipedia.org/wiki/File:ReLU_and_GELU.svg
gradient à 0
GELU
(Gaussian Error
Linear Unit)
Stanford CS231n 10th Anniversary Lecture 6 - 27 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| [Hendrycks et al., 2016]
Activation Functions
- Computes f(x) = x*Φ(x)
- Very nice behavior around 0
- Smoothness facilitates training in
practice
- Higher computational cost than ReLU
- Large negative values can still have
Source: https://en.m.wikipedia.org/wiki/File:ReLU_and_GELU.svg
gradient à 0
GELU
(Gaussian Error
Linear Unit) |
| Stanford CS231n 10th Anniversary Lecture 6 - 27 April 17, 2025 |


[Page contains 1 image(s)]


---
## Page 28
---


Activation Function Zoo
Stanford CS231n 10th Anniversary Lecture 6 - 28 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Activation Function Zoo |
| Stanford CS231n 10th Anniversary Lecture 6 - 28 April 17, 2025 |


[Page contains 10 image(s)]


---
## Page 29
---


Activation Function Zoo
Q: Where are activations used in CNNs?
Stanford CS231n 10th Anniversary Lecture 6 - 29 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Activation Function Zoo
Q: Where are activations used in CNNs? |
| Stanford CS231n 10th Anniversary Lecture 6 - 29 April 17, 2025 |


[Page contains 10 image(s)]


---
## Page 30
---


Activation Function Zoo
Q: Where are activations used in CNNs?
A: Generally placed after linear operators (feedforward/linear
layer, convolutional layer, etc.)
Stanford CS231n 10th Anniversary Lecture 6 - 30 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Activation Function Zoo
Q: Where are activations used in CNNs?
A: Generally placed after linear operators (feedforward/linear
layer, convolutional layer, etc.) |
| Stanford CS231n 10th Anniversary Lecture 6 - 30 April 17, 2025 |


[Page contains 10 image(s)]


---
## Page 31
---


Lecture Overview – Two Broad Sets of Topics
Layers in CNNs
Activation Functions
How to build CNNs?
CNN Architectures
Weight Initialization
Data Preprocessing
Data augmentation
How to train CNNs?
Transfer Learning
Hyperparameter Selection
Stanford CS231n 10th Anniversary Lecture 6 - 31 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture Overview – Two Broad Sets of Topics
Layers in CNNs
Activation Functions
How to build CNNs?
CNN Architectures
Weight Initialization
Data Preprocessing
Data augmentation
How to train CNNs?
Transfer Learning
Hyperparameter Selection |
| Stanford CS231n 10th Anniversary Lecture 6 - 31 April 17, 2025 |


---
## Page 32
---


ImageNet Large Scale Visual Recognition Challenge (ILSVRC) winners
152 layers 152 layers 152 layers
19 layers 22 layers
shallow 8 layers 8 layers
Lin et al Sanchez & Krizhevsky et al Zeiler & Simonyan & Szegedy et al He et al Shao et al Hu et al Russakovsky et al
Perronnin (AlexNet) Fergus Zisserman (VGG) (GoogLeNet) (ResNet) (SENet)
Stanford CS231n 10th Anniversary Lecture 6 - 32 April 17, 2025

[Page contains 2 table(s)]


### Table 1

| ImageNet Large Scale Visual Recognition Challenge (ILSVRC) winners
152 layers 152 layers 152 layers
19 layers 22 layers
shallow 8 layers 8 layers
Lin et al Sanchez & Krizhevsky et al Zeiler & Simonyan & Szegedy et al He et al Shao et al Hu et al Russakovsky et al
Perronnin (AlexNet) Fergus Zisserman (VGG) (GoogLeNet) (ResNet) (SENet) |
| Stanford CS231n 10th Anniversary Lecture 6 - 32 April 17, 2025 |


### Table 2

| 22 la | yers |


[Page contains 1 image(s)]


---
## Page 33
---


ImageNet Large Scale Visual Recognition Challenge (ILSVRC) winners
152 layers 152 layers 152 layers
19 layers 22 layers
shallow 8 layers 8 layers
Lin et al Sanchez & Krizhevsky et al Zeiler & Simonyan & Szegedy et al He et al Shao et al Hu et al Russakovsky et al
Perronnin (AlexNet) Fergus Zisserman (VGG) (GoogLeNet) (ResNet) (SENet)
Stanford CS231n 10th Anniversary Lecture 6 - 33 April 17, 2025

[Page contains 2 table(s)]


### Table 1

| ImageNet Large Scale Visual Recognition Challenge (ILSVRC) winners
152 layers 152 layers 152 layers
19 layers 22 layers
shallow 8 layers 8 layers
Lin et al Sanchez & Krizhevsky et al Zeiler & Simonyan & Szegedy et al He et al Shao et al Hu et al Russakovsky et al
Perronnin (AlexNet) Fergus Zisserman (VGG) (GoogLeNet) (ResNet) (SENet) |
| Stanford CS231n 10th Anniversary Lecture 6 - 33 April 17, 2025 |


### Table 2

| 22 la | yers |


[Page contains 1 image(s)]


---
## Page 34
---


ImageNet Large Scale Visual Recognition Challenge (ILSVRC) winners
152 layers 152 layers 152 layers
19 layers 22 layers
shallow 8 layers 8 layers
Lin et al Sanchez & Krizhevsky et al Zeiler & Simonyan & Szegedy et al He et al Shao et al Hu et al Russakovsky et al
Perronnin (AlexNet) Fergus Zisserman (VGG) (GoogLeNet) (ResNet) (SENet)
Stanford CS231n 10th Anniversary Lecture 6 - 34 April 17, 2025

[Page contains 2 table(s)]


### Table 1

| ImageNet Large Scale Visual Recognition Challenge (ILSVRC) winners
152 layers 152 layers 152 layers
19 layers 22 layers
shallow 8 layers 8 layers
Lin et al Sanchez & Krizhevsky et al Zeiler & Simonyan & Szegedy et al He et al Shao et al Hu et al Russakovsky et al
Perronnin (AlexNet) Fergus Zisserman (VGG) (GoogLeNet) (ResNet) (SENet) |
| Stanford CS231n 10th Anniversary Lecture 6 - 34 April 17, 2025 |


### Table 2

| 22 la | yers |


[Page contains 1 image(s)]


---
## Page 35
---


Case Study: VGGNet
Softmax
FC 1000
Softmax FC 4096
[Simonyan and Zisserman, 2014]
FC 1000 FC 4096
FC 4096 Pool
FC 4096 3x3 conv, 512
Pool 3x3 conv, 512
Small filters, Deeper networks
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 Pool
8 layers (AlexNet)
Pool 3x3 conv, 512
Softmax 3x3 conv, 512 3x3 conv, 512
-> 16 - 19 layers (VGG16Net)
FC 1000 3x3 conv, 512 3x3 conv, 512
FC 4096 3x3 conv, 512 3x3 conv, 512
FC 4096 Pool Pool
Only 3x3 CONV stride 1, pad 1 Pool 3x3 conv, 256 3x3 conv, 256
3x3 conv, 256 3x3 conv, 256 3x3 conv, 256
and 2x2 MAX POOL stride 2
3x3 conv, 384 Pool Pool
Pool 3x3 conv, 128 3x3 conv, 128
3x3 conv, 384 3x3 conv, 128 3x3 conv, 128
11.7% top 5 error in ILSVRC’13 Pool Pool Pool
5x5 conv, 256 3x3 conv, 64 3x3 conv, 64
(ZFNet)
11x11 conv, 96 3x3 conv, 64 3x3 conv, 64
Input Input Input
-> 7.3% top 5 error in ILSVRC’14
AlexNet VGG16 VGG19
Stanford CS231n 10th Anniversary Lecture 6 - 35 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Case Study: VGGNet
Softmax
FC 1000
Softmax FC 4096
[Simonyan and Zisserman, 2014]
FC 1000 FC 4096
FC 4096 Pool
FC 4096 3x3 conv, 512
Pool 3x3 conv, 512
Small filters, Deeper networks
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 Pool
8 layers (AlexNet)
Pool 3x3 conv, 512
Softmax 3x3 conv, 512 3x3 conv, 512
-> 16 - 19 layers (VGG16Net)
FC 1000 3x3 conv, 512 3x3 conv, 512
FC 4096 3x3 conv, 512 3x3 conv, 512
FC 4096 Pool Pool
Only 3x3 CONV stride 1, pad 1 Pool 3x3 conv, 256 3x3 conv, 256
3x3 conv, 256 3x3 conv, 256 3x3 conv, 256
and 2x2 MAX POOL stride 2
3x3 conv, 384 Pool Pool
Pool 3x3 conv, 128 3x3 conv, 128
3x3 conv, 384 3x3 conv, 128 3x3 conv, 128
11.7% top 5 error in ILSVRC’13 Pool Pool Pool
5x5 conv, 256 3x3 conv, 64 3x3 conv, 64
(ZFNet)
11x11 conv, 96 3x3 conv, 64 3x3 conv, 64
Input Input Input
-> 7.3% top 5 error in ILSVRC’14
AlexNet VGG16 VGG19 |
| Stanford CS231n 10th Anniversary Lecture 6 - 35 April 17, 2025 |


---
## Page 36
---


Case Study: VGGNet
Softmax
FC 1000
Softmax FC 4096
[Simonyan and Zisserman, 2014]
FC 1000 FC 4096
FC 4096 Pool
FC 4096 3x3 conv, 512
Q: Why use smaller filters? (3x3 conv) Pool 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 Pool
Pool 3x3 conv, 512
Softmax 3x3 conv, 512 3x3 conv, 512
FC 1000 3x3 conv, 512 3x3 conv, 512
FC 4096 3x3 conv, 512 3x3 conv, 512
FC 4096 Pool Pool
Pool 3x3 conv, 256 3x3 conv, 256
3x3 conv, 256 3x3 conv, 256 3x3 conv, 256
3x3 conv, 384 Pool Pool
Pool 3x3 conv, 128 3x3 conv, 128
3x3 conv, 384 3x3 conv, 128 3x3 conv, 128
Pool Pool Pool
5x5 conv, 256 3x3 conv, 64 3x3 conv, 64
11x11 conv, 96 3x3 conv, 64 3x3 conv, 64
Input Input Input
AlexNet VGG16 VGG19
Stanford CS231n 10th Anniversary Lecture 6 - 36 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Case Study: VGGNet
Softmax
FC 1000
Softmax FC 4096
[Simonyan and Zisserman, 2014]
FC 1000 FC 4096
FC 4096 Pool
FC 4096 3x3 conv, 512
Q: Why use smaller filters? (3x3 conv) Pool 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 Pool
Pool 3x3 conv, 512
Softmax 3x3 conv, 512 3x3 conv, 512
FC 1000 3x3 conv, 512 3x3 conv, 512
FC 4096 3x3 conv, 512 3x3 conv, 512
FC 4096 Pool Pool
Pool 3x3 conv, 256 3x3 conv, 256
3x3 conv, 256 3x3 conv, 256 3x3 conv, 256
3x3 conv, 384 Pool Pool
Pool 3x3 conv, 128 3x3 conv, 128
3x3 conv, 384 3x3 conv, 128 3x3 conv, 128
Pool Pool Pool
5x5 conv, 256 3x3 conv, 64 3x3 conv, 64
11x11 conv, 96 3x3 conv, 64 3x3 conv, 64
Input Input Input
AlexNet VGG16 VGG19 |
| Stanford CS231n 10th Anniversary Lecture 6 - 36 April 17, 2025 |


---
## Page 37
---


Case Study: VGGNet
Softmax
FC 1000
Softmax FC 4096
[Simonyan and Zisserman, 2014]
FC 1000 FC 4096
FC 4096 Pool
Q: What is the effective receptive field FC 4096 3x3 conv, 512
Pool 3x3 conv, 512
of three 3x3 conv (stride 1) layers? 3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 Pool
Pool 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
Input A1 A2 A3
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
Pool Pool
3x3 conv, 256 3x3 conv, 256
3x3 conv, 256 3x3 conv, 256
Pool Pool
3x3 conv, 128 3x3 conv, 128
3x3 conv, 128 3x3 conv, 128
Pool Pool
3x3 conv, 64 3x3 conv, 64
3x3 conv, 64 3x3 conv, 64
Conv1 (3x3) Conv2 (3x3) Conv3 (3x3) Input Input
VGG16 VGG19
Stanford CS231n 10th Anniversary Lecture 6 - 37 April 17, 2025

[Page contains 5 table(s)]


### Table 1

| Case Study: VGGNet
Softmax
FC 1000
Softmax FC 4096
[Simonyan and Zisserman, 2014]
FC 1000 FC 4096
FC 4096 Pool
Q: What is the effective receptive field FC 4096 3x3 conv, 512
Pool 3x3 conv, 512
of three 3x3 conv (stride 1) layers? 3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 Pool
Pool 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
Input A1 A2 A3
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
Pool Pool
3x3 conv, 256 3x3 conv, 256
3x3 conv, 256 3x3 conv, 256
Pool Pool
3x3 conv, 128 3x3 conv, 128
3x3 conv, 128 3x3 conv, 128
Pool Pool
3x3 conv, 64 3x3 conv, 64
3x3 conv, 64 3x3 conv, 64
Conv1 (3x3) Conv2 (3x3) Conv3 (3x3) Input Input
VGG16 VGG19 |
| Stanford CS231n 10th Anniversary Lecture 6 - 37 April 17, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |


### Table 3

|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |


### Table 4

|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |


### Table 5

|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |


---
## Page 38
---


Case Study: VGGNet
Softmax
FC 1000
Softmax FC 4096
[Simonyan and Zisserman, 2014]
FC 1000 FC 4096
FC 4096 Pool
Q: What is the effective receptive field FC 4096 3x3 conv, 512
Pool 3x3 conv, 512
of three 3x3 conv (stride 1) layers? 3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 Pool
Pool 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
Input A1 A2 A3
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
Pool Pool
3x3 conv, 256 3x3 conv, 256
3x3 conv, 256 3x3 conv, 256
Pool Pool
3x3 conv, 128 3x3 conv, 128
3x3 conv, 128 3x3 conv, 128
Pool Pool
3x3 conv, 64 3x3 conv, 64
3x3 conv, 64 3x3 conv, 64
Conv1 (3x3) Conv2 (3x3) Conv3 (3x3) Input Input
VGG16 VGG19
Stanford CS231n 10th Anniversary Lecture 6 - 38 April 17, 2025

[Page contains 5 table(s)]


### Table 1

| Case Study: VGGNet
Softmax
FC 1000
Softmax FC 4096
[Simonyan and Zisserman, 2014]
FC 1000 FC 4096
FC 4096 Pool
Q: What is the effective receptive field FC 4096 3x3 conv, 512
Pool 3x3 conv, 512
of three 3x3 conv (stride 1) layers? 3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 Pool
Pool 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
Input A1 A2 A3
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
Pool Pool
3x3 conv, 256 3x3 conv, 256
3x3 conv, 256 3x3 conv, 256
Pool Pool
3x3 conv, 128 3x3 conv, 128
3x3 conv, 128 3x3 conv, 128
Pool Pool
3x3 conv, 64 3x3 conv, 64
3x3 conv, 64 3x3 conv, 64
Conv1 (3x3) Conv2 (3x3) Conv3 (3x3) Input Input
VGG16 VGG19 |
| Stanford CS231n 10th Anniversary Lecture 6 - 38 April 17, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |


### Table 3

|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |


### Table 4

|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |


### Table 5

|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |


---
## Page 39
---


Case Study: VGGNet
Softmax
FC 1000
Softmax FC 4096
[Simonyan and Zisserman, 2014]
FC 1000 FC 4096
FC 4096 Pool
Q: What is the effective receptive field FC 4096 3x3 conv, 512
Pool 3x3 conv, 512
of three 3x3 conv (stride 1) layers? 3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 Pool
Pool 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
Input A1 A2 A3
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
Pool Pool
3x3 conv, 256 3x3 conv, 256
3x3 conv, 256 3x3 conv, 256
Pool Pool
3x3 conv, 128 3x3 conv, 128
3x3 conv, 128 3x3 conv, 128
Pool Pool
3x3 conv, 64 3x3 conv, 64
3x3 conv, 64 3x3 conv, 64
Conv1 (3x3) Conv2 (3x3) Conv3 (3x3) Input Input
VGG16 VGG19
Stanford CS231n 10th Anniversary Lecture 6 - 39 April 17, 2025

[Page contains 5 table(s)]


### Table 1

| Case Study: VGGNet
Softmax
FC 1000
Softmax FC 4096
[Simonyan and Zisserman, 2014]
FC 1000 FC 4096
FC 4096 Pool
Q: What is the effective receptive field FC 4096 3x3 conv, 512
Pool 3x3 conv, 512
of three 3x3 conv (stride 1) layers? 3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 Pool
Pool 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
Input A1 A2 A3
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
Pool Pool
3x3 conv, 256 3x3 conv, 256
3x3 conv, 256 3x3 conv, 256
Pool Pool
3x3 conv, 128 3x3 conv, 128
3x3 conv, 128 3x3 conv, 128
Pool Pool
3x3 conv, 64 3x3 conv, 64
3x3 conv, 64 3x3 conv, 64
Conv1 (3x3) Conv2 (3x3) Conv3 (3x3) Input Input
VGG16 VGG19 |
| Stanford CS231n 10th Anniversary Lecture 6 - 39 April 17, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |


### Table 3

|  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |


### Table 4

|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |


### Table 5

|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |


---
## Page 40
---


Case Study: VGGNet
Softmax
FC 1000
Softmax FC 4096
[Simonyan and Zisserman, 2014]
FC 1000 FC 4096
FC 4096 Pool
Q: What is the effective receptive field FC 4096 3x3 conv, 512
Pool 3x3 conv, 512
of three 3x3 conv (stride 1) layers? 3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 Pool
Pool 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
Input A1 A2 A3
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
Pool Pool
3x3 conv, 256 3x3 conv, 256
3x3 conv, 256 3x3 conv, 256
Pool Pool
3x3 conv, 128 3x3 conv, 128
3x3 conv, 128 3x3 conv, 128
Pool Pool
3x3 conv, 64 3x3 conv, 64
3x3 conv, 64 3x3 conv, 64
Conv1 (3x3) Conv2 (3x3) Conv3 (3x3) Input Input
VGG16 VGG19
Stanford CS231n 10th Anniversary Lecture 6 - 40 April 17, 2025

[Page contains 5 table(s)]


### Table 1

| Case Study: VGGNet
Softmax
FC 1000
Softmax FC 4096
[Simonyan and Zisserman, 2014]
FC 1000 FC 4096
FC 4096 Pool
Q: What is the effective receptive field FC 4096 3x3 conv, 512
Pool 3x3 conv, 512
of three 3x3 conv (stride 1) layers? 3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 Pool
Pool 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
Input A1 A2 A3
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
Pool Pool
3x3 conv, 256 3x3 conv, 256
3x3 conv, 256 3x3 conv, 256
Pool Pool
3x3 conv, 128 3x3 conv, 128
3x3 conv, 128 3x3 conv, 128
Pool Pool
3x3 conv, 64 3x3 conv, 64
3x3 conv, 64 3x3 conv, 64
Conv1 (3x3) Conv2 (3x3) Conv3 (3x3) Input Input
VGG16 VGG19 |
| Stanford CS231n 10th Anniversary Lecture 6 - 40 April 17, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |


### Table 3

|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |


### Table 4

|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |


### Table 5

|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |


---
## Page 41
---


Case Study: VGGNet
Softmax
FC 1000
Softmax FC 4096
[Simonyan and Zisserman, 2014]
FC 1000 FC 4096
FC 4096 Pool
Q: What is the effective receptive field FC 4096 3x3 conv, 512
Pool 3x3 conv, 512
of three 3x3 conv (stride 1) layers? 3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 Pool
Pool 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
Input A1 A2 A3
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
Pool Pool
3x3 conv, 256 3x3 conv, 256
3x3 conv, 256 3x3 conv, 256
Pool Pool
3x3 conv, 128 3x3 conv, 128
3x3 conv, 128 3x3 conv, 128
Pool Pool
3x3 conv, 64 3x3 conv, 64
3x3 conv, 64 3x3 conv, 64
Conv1 (3x3) Conv2 (3x3) Conv3 (3x3) Input Input
VGG16 VGG19
Stanford CS231n 10th Anniversary Lecture 6 - 41 April 17, 2025

[Page contains 5 table(s)]


### Table 1

| Case Study: VGGNet
Softmax
FC 1000
Softmax FC 4096
[Simonyan and Zisserman, 2014]
FC 1000 FC 4096
FC 4096 Pool
Q: What is the effective receptive field FC 4096 3x3 conv, 512
Pool 3x3 conv, 512
of three 3x3 conv (stride 1) layers? 3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 Pool
Pool 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
Input A1 A2 A3
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
Pool Pool
3x3 conv, 256 3x3 conv, 256
3x3 conv, 256 3x3 conv, 256
Pool Pool
3x3 conv, 128 3x3 conv, 128
3x3 conv, 128 3x3 conv, 128
Pool Pool
3x3 conv, 64 3x3 conv, 64
3x3 conv, 64 3x3 conv, 64
Conv1 (3x3) Conv2 (3x3) Conv3 (3x3) Input Input
VGG16 VGG19 |
| Stanford CS231n 10th Anniversary Lecture 6 - 41 April 17, 2025 |


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
|  |  |  |  |  |  |  |  |  |  |


### Table 3

|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |


### Table 4

|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |


### Table 5

|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |


---
## Page 42
---


Case Study: VGGNet
Softmax
FC 1000
Softmax FC 4096
[Simonyan and Zisserman, 2014]
FC 1000 FC 4096
FC 4096 Pool
FC 4096 3x3 conv, 512
Q: Why use smaller filters? (3x3 conv) Pool 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 Pool
Pool 3x3 conv, 512
Softmax 3x3 conv, 512 3x3 conv, 512
FC 1000 3x3 conv, 512 3x3 conv, 512
Stack of three 3x3 conv (stride 1) layers
FC 4096 3x3 conv, 512 3x3 conv, 512
FC 4096 Pool Pool
has same effective receptive field as
Pool 3x3 conv, 256 3x3 conv, 256
one 7x7 conv layer 3x3 conv, 256 3x3 conv, 256 3x3 conv, 256
3x3 conv, 384 Pool Pool
Pool 3x3 conv, 128 3x3 conv, 128
3x3 conv, 384 3x3 conv, 128 3x3 conv, 128
[7x7]
Pool Pool Pool
5x5 conv, 256 3x3 conv, 64 3x3 conv, 64
11x11 conv, 96 3x3 conv, 64 3x3 conv, 64
Input Input Input
AlexNet VGG16 VGG19
Stanford CS231n 10th Anniversary Lecture 6 - 42 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Case Study: VGGNet
Softmax
FC 1000
Softmax FC 4096
[Simonyan and Zisserman, 2014]
FC 1000 FC 4096
FC 4096 Pool
FC 4096 3x3 conv, 512
Q: Why use smaller filters? (3x3 conv) Pool 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 Pool
Pool 3x3 conv, 512
Softmax 3x3 conv, 512 3x3 conv, 512
FC 1000 3x3 conv, 512 3x3 conv, 512
Stack of three 3x3 conv (stride 1) layers
FC 4096 3x3 conv, 512 3x3 conv, 512
FC 4096 Pool Pool
has same effective receptive field as
Pool 3x3 conv, 256 3x3 conv, 256
one 7x7 conv layer 3x3 conv, 256 3x3 conv, 256 3x3 conv, 256
3x3 conv, 384 Pool Pool
Pool 3x3 conv, 128 3x3 conv, 128
3x3 conv, 384 3x3 conv, 128 3x3 conv, 128
[7x7]
Pool Pool Pool
5x5 conv, 256 3x3 conv, 64 3x3 conv, 64
11x11 conv, 96 3x3 conv, 64 3x3 conv, 64
Input Input Input
AlexNet VGG16 VGG19 |
| Stanford CS231n 10th Anniversary Lecture 6 - 42 April 17, 2025 |


---
## Page 43
---


Case Study: VGGNet
Softmax
FC 1000
Softmax FC 4096
[Simonyan and Zisserman, 2014]
FC 1000 FC 4096
FC 4096 Pool
FC 4096 3x3 conv, 512
Q: Why use smaller filters? (3x3 conv) Pool 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 Pool
Stack of three 3x3 conv (stride 1) layers Pool 3x3 conv, 512
Softmax 3x3 conv, 512 3x3 conv, 512
has same effective receptive field as FC 1000 3x3 conv, 512 3x3 conv, 512
FC 4096 3x3 conv, 512 3x3 conv, 512
one 7x7 conv layer
FC 4096 Pool Pool
Pool 3x3 conv, 256 3x3 conv, 256
3x3 conv, 256 3x3 conv, 256 3x3 conv, 256
But deeper, more non-linearities 3x3 conv, 384 Pool Pool
Pool 3x3 conv, 128 3x3 conv, 128
3x3 conv, 384 3x3 conv, 128 3x3 conv, 128
Pool Pool Pool
And fewer parameters: 3 * (32C2) vs.
5x5 conv, 256 3x3 conv, 64 3x3 conv, 64
72C2 for C channels per layer 11x11 conv, 96 3x3 conv, 64 3x3 conv, 64
Input Input Input
AlexNet VGG16 VGG19
Stanford CS231n 10th Anniversary Lecture 6 - 43 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Case Study: VGGNet
Softmax
FC 1000
Softmax FC 4096
[Simonyan and Zisserman, 2014]
FC 1000 FC 4096
FC 4096 Pool
FC 4096 3x3 conv, 512
Q: Why use smaller filters? (3x3 conv) Pool 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 3x3 conv, 512
3x3 conv, 512 Pool
Stack of three 3x3 conv (stride 1) layers Pool 3x3 conv, 512
Softmax 3x3 conv, 512 3x3 conv, 512
has same effective receptive field as FC 1000 3x3 conv, 512 3x3 conv, 512
FC 4096 3x3 conv, 512 3x3 conv, 512
one 7x7 conv layer
FC 4096 Pool Pool
Pool 3x3 conv, 256 3x3 conv, 256
3x3 conv, 256 3x3 conv, 256 3x3 conv, 256
But deeper, more non-linearities 3x3 conv, 384 Pool Pool
Pool 3x3 conv, 128 3x3 conv, 128
3x3 conv, 384 3x3 conv, 128 3x3 conv, 128
Pool Pool Pool
And fewer parameters: 3 * (32C2) vs.
5x5 conv, 256 3x3 conv, 64 3x3 conv, 64
72C2 for C channels per layer 11x11 conv, 96 3x3 conv, 64 3x3 conv, 64
Input Input Input
AlexNet VGG16 VGG19 |
| Stanford CS231n 10th Anniversary Lecture 6 - 43 April 17, 2025 |


---
## Page 44
---


ImageNet Large Scale Visual Recognition Challenge (ILSVRC) winners
“Revolution of Depth”
152 layers 152 layers 152 layers
19 layers 22 layers
shallow 8 layers 8 layers
Lin et al Sanchez & Krizhevsky et al Zeiler & Simonyan & Szegedy et al He et al Shao et al Hu et al Russakovsky et al
Perronnin (AlexNet) Fergus Zisserman (VGG) (GoogLeNet) (ResNet) (SENet)
Stanford CS231n 10th Anniversary Lecture 6 - 44 April 17, 2025

[Page contains 2 table(s)]


### Table 1

| ImageNet Large Scale Visual Recognition Challenge (ILSVRC) winners
“Revolution of Depth”
152 layers 152 layers 152 layers
19 layers 22 layers
shallow 8 layers 8 layers
Lin et al Sanchez & Krizhevsky et al Zeiler & Simonyan & Szegedy et al He et al Shao et al Hu et al Russakovsky et al
Perronnin (AlexNet) Fergus Zisserman (VGG) (GoogLeNet) (ResNet) (SENet) |
| Stanford CS231n 10th Anniversary Lecture 6 - 44 April 17, 2025 |


### Table 2

| 22 la | yers |


[Page contains 1 image(s)]


---
## Page 45
---


Case Study: ResNet
[He et al., 2015]
What happens when we continue stacking deeper layers on a “plain” convolutional
neural network?
Stanford CS231n 10th Anniversary Lecture 6 - 45 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Case Study: ResNet
[He et al., 2015]
What happens when we continue stacking deeper layers on a “plain” convolutional
neural network? |
| Stanford CS231n 10th Anniversary Lecture 6 - 45 April 17, 2025 |


---
## Page 46
---


Stanford CS231n 10th Anniversary Lecture 6 - 46 April 17, 2025
rorre
gniniarT
56-layer
20-layer
Iterations
rorre
tseT
Case Study: ResNet
[He et al., 2015]
What happens when we continue stacking deeper layers on a “plain” convolutional
neural network?
56-layer
20-layer
Iterations

[Page contains 1 table(s)]


### Table 1

| Case Study: ResNet
[He et al., 2015]
What happens when we continue stacking deeper layers on a “plain” convolutional
neural network?
56-layer
rorre
56-layer
rorre
gniniarT
20-layer
tseT
20-layer
Iterations Iterations |
| Stanford CS231n 10th Anniversary Lecture 6 - 46 April 17, 2025 |


---
## Page 47
---


Case Study: ResNet
[He et al., 2015]
What happens when we continue stacking deeper layers on a “plain” convolutional
neural network?
56-layer model performs worse on both test and training error
-> The deeper model performs worse, but it’s not caused by overfitting!
Stanford CS231n 10th Anniversary Lecture 6 - 47 April 17, 2025
rorre
gniniarT
56-layer
20-layer
Iterations
rorre
tseT
56-layer
20-layer
Iterations

[Page contains 1 table(s)]


### Table 1

| Case Study: ResNet
[He et al., 2015]
What happens when we continue stacking deeper layers on a “plain” convolutional
neural network?
56-layer
rorre
56-layer
rorre
gniniarT
20-layer
tseT
20-layer
Iterations Iterations
56-layer model performs worse on both test and training error
-> The deeper model performs worse, but it’s not caused by overfitting! |
| Stanford CS231n 10th Anniversary Lecture 6 - 47 April 17, 2025 |


---
## Page 48
---


Case Study: ResNet
[He et al., 2015]
Fact: Deep models have more representation power
(more parameters) than shallower models.
Hypothesis: the problem is an optimization problem,
deeper models are harder to optimize
Stanford CS231n 10th Anniversary Lecture 6 - 48 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Case Study: ResNet
[He et al., 2015]
Fact: Deep models have more representation power
(more parameters) than shallower models.
Hypothesis: the problem is an optimization problem,
deeper models are harder to optimize |
| Stanford CS231n 10th Anniversary Lecture 6 - 48 April 17, 2025 |


---
## Page 49
---


Case Study: ResNet
[He et al., 2015]
Fact: Deep models have more representation power
(more parameters) than shallower models.
Hypothesis: the problem is an optimization problem,
H(x)
deeper models are harder to optimize
H(x)
What should the deeper model learn to be at least Identity
as good as the shallower model?
relu relu
conv conv
A solution by construction is copying the learned
layers from the shallower model and setting
X X
additional layers to identity mapping.
Stanford CS231n 10th Anniversary Lecture 6 - 49 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Case Study: ResNet
[He et al., 2015]
Fact: Deep models have more representation power
(more parameters) than shallower models.
Hypothesis: the problem is an optimization problem,
H(x)
deeper models are harder to optimize
H(x)
What should the deeper model learn to be at least Identity
as good as the shallower model?
relu relu
conv conv
A solution by construction is copying the learned
layers from the shallower model and setting
X X
additional layers to identity mapping. |
| Stanford CS231n 10th Anniversary Lecture 6 - 49 April 17, 2025 |


---
## Page 50
---


Case Study: ResNet
[He et al., 2015]
Solution: Use network layers to fit a residual mapping instead of directly trying to fit a
desired underlying mapping
H(x)
conv
relu
conv
X
“Plain” layers
Stanford CS231n 10th Anniversary Lecture 6 - 50 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Case Study: ResNet
[He et al., 2015]
Solution: Use network layers to fit a residual mapping instead of directly trying to fit a
desired underlying mapping
H(x)
conv
relu
conv
X
“Plain” layers |
| Stanford CS231n 10th Anniversary Lecture 6 - 50 April 17, 2025 |


---
## Page 51
---


Case Study: ResNet
[He et al., 2015]
Solution: Use network layers to fit a residual mapping instead of directly trying to fit a
desired underlying mapping
Identity mapping:
relu
H(x) = x if F(x) = 0
H(x)
H(x) = F(x) + x
conv
conv
X
F(x)
relu
relu
identity
conv
conv
X
X
“Plain” layers Residual block
Stanford CS231n 10th Anniversary Lecture 6 - 51 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Case Study: ResNet
[He et al., 2015]
Solution: Use network layers to fit a residual mapping instead of directly trying to fit a
desired underlying mapping
Identity mapping:
relu
H(x) = x if F(x) = 0
H(x)
H(x) = F(x) + x
conv
conv
X
F(x)
relu
relu
identity
conv
conv
X
X
“Plain” layers Residual block |
| Stanford CS231n 10th Anniversary Lecture 6 - 51 April 17, 2025 |


---
## Page 52
---


Case Study: ResNet
[He et al., 2015]
Solution: Use network layers to fit a residual mapping instead of directly trying to fit a
desired underlying mapping
Identity mapping:
H(x) = F(x) + x relu
H(x) = x if F(x) = 0
H(x)
H(x) = F(x) + x
Use layers to
conv
conv
fit residual
X
F(x)
relu
relu
identity F(x) = H(x) - x
conv
instead of
conv
H(x) directly
X
X
“Plain” layers Residual block
Stanford CS231n 10th Anniversary Lecture 6 - 5522 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Case Study: ResNet
[He et al., 2015]
Solution: Use network layers to fit a residual mapping instead of directly trying to fit a
desired underlying mapping
Identity mapping:
H(x) = F(x) + x relu
H(x) = x if F(x) = 0
H(x)
H(x) = F(x) + x
Use layers to
conv
conv
fit residual
X
F(x)
relu
relu
identity F(x) = H(x) - x
conv
instead of
conv
H(x) directly
X
X
“Plain” layers Residual block |
| Stanford CS231n 10th Anniversary Lecture 6 - 5522 April 17, 2025 |


---
## Page 53
---


Softmax
Case Study: ResNet
FC 1000
Pool
[He et al., 2015] 3x3 conv, 512
3x3 conv, 512
3x3 conv, 512
Full ResNet architecture: 3x3 conv, 512
relu
3x3 conv, 512
- Stack residual blocks
3x3 conv, 512, /2
F(x) + x
- Every residual block has
..
two 3x3 conv layers .
3x3 conv, 128
3x3 conv
3x3 conv, 128
X
3x3 conv, 128
F(x)
relu
3x3 conv, 128
identity
3x3 conv, 128
3x3 conv
3x3 conv, 128, / 2
3x3 conv, 64
3x3 conv, 64
3x3 conv, 64
X
3x3 conv, 64
Residual block
3x3 conv, 64
3x3 conv, 64
Pool
7x7 conv, 64, / 2
Input
Stanford CS231n 10th Anniversary Lecture 6 - 53 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Softmax
Case Study: ResNet
FC 1000
Pool
[He et al., 2015] 3x3 conv, 512
3x3 conv, 512
3x3 conv, 512
Full ResNet architecture: 3x3 conv, 512
relu
3x3 conv, 512
- Stack residual blocks
3x3 conv, 512, /2
F(x) + x
- Every residual block has
..
two 3x3 conv layers .
3x3 conv, 128
3x3 conv
3x3 conv, 128
X
3x3 conv, 128
F(x)
relu
3x3 conv, 128
identity
3x3 conv, 128
3x3 conv
3x3 conv, 128, / 2
3x3 conv, 64
3x3 conv, 64
3x3 conv, 64
X
3x3 conv, 64
Residual block
3x3 conv, 64
3x3 conv, 64
Pool
7x7 conv, 64, / 2
Input |
| Stanford CS231n 10th Anniversary Lecture 6 - 53 April 17, 2025 |


---
## Page 54
---


Softmax
Case Study: ResNet
FC 1000
Pool
[He et al., 2015] 3x3 conv, 512
3x3 conv, 512
3x3 conv, 512
Full ResNet architecture: 3x3 conv, 512
relu
3x3 conv, 512
- Stack residual blocks
3x3 conv, 512, /2
F(x) + x
- Every residual block has
..
two 3x3 conv layers .
3x3 conv, 128
- Periodically, double # of 3x3 conv
3x3 conv, 128
3x3 conv, 128
filters and downsample X
3x3 conv, 128
F(x) filters, /2
relu
3x3 conv, 128
identity spatially with
spatially using stride 2
3x3 conv, 128 stride 2
3x3 conv
(/2 in each dimension) 3x3 conv, 128, / 2
3x3 conv, 64 3x3 conv, 64
Reduce the activation
3x3 conv, 64
filters
volume by half.
3x3 conv, 64
X
3x3 conv, 64
Residual block
3x3 conv, 64
3x3 conv, 64
Pool
7x7 conv, 64, / 2
Input
Stanford CS231n 10th Anniversary Lecture 6 - 54 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Softmax
Case Study: ResNet
FC 1000
Pool
[He et al., 2015] 3x3 conv, 512
3x3 conv, 512
3x3 conv, 512
Full ResNet architecture: 3x3 conv, 512
relu
3x3 conv, 512
- Stack residual blocks
3x3 conv, 512, /2
F(x) + x
- Every residual block has
..
two 3x3 conv layers .
3x3 conv, 128
- Periodically, double # of 3x3 conv
3x3 conv, 128
3x3 conv, 128
filters and downsample X
3x3 conv, 128
F(x) filters, /2
relu
3x3 conv, 128
identity spatially with
spatially using stride 2
3x3 conv, 128 stride 2
3x3 conv
(/2 in each dimension) 3x3 conv, 128, / 2
3x3 conv, 64 3x3 conv, 64
Reduce the activation
3x3 conv, 64
filters
volume by half.
3x3 conv, 64
X
3x3 conv, 64
Residual block
3x3 conv, 64
3x3 conv, 64
Pool
7x7 conv, 64, / 2
Input |
| Stanford CS231n 10th Anniversary Lecture 6 - 54 April 17, 2025 |


---
## Page 55
---


Softmax
Case Study: ResNet
FC 1000
Pool
[He et al., 2015] 3x3 conv, 512
3x3 conv, 512
3x3 conv, 512
Full ResNet architecture: 3x3 conv, 512
relu
3x3 conv, 512
- Stack residual blocks
3x3 conv, 512, /2
F(x) + x
- Every residual block has
..
two 3x3 conv layers .
3x3 conv, 128
- Periodically, double # of 3x3 conv
3x3 conv, 128
filters and downsample X
3x3 conv, 128
F(x)
relu
3x3 conv, 128
identity
spatially using stride 2
3x3 conv, 128
3x3 conv
(/2 in each dimension) 3x3 conv, 128, / 2
3x3 conv, 64
- Additional conv layer at
3x3 conv, 64
the beginning (stem)
3x3 conv, 64
X
3x3 conv, 64
Residual block
3x3 conv, 64
3x3 conv, 64
Pool
7x7 conv, 64, / 2 Beginning
Input conv layer
Stanford CS231n 10th Anniversary Lecture 6 - 55 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Softmax
Case Study: ResNet
FC 1000
Pool
[He et al., 2015] 3x3 conv, 512
3x3 conv, 512
3x3 conv, 512
Full ResNet architecture: 3x3 conv, 512
relu
3x3 conv, 512
- Stack residual blocks
3x3 conv, 512, /2
F(x) + x
- Every residual block has
..
two 3x3 conv layers .
3x3 conv, 128
- Periodically, double # of 3x3 conv
3x3 conv, 128
filters and downsample X
3x3 conv, 128
F(x)
relu
3x3 conv, 128
identity
spatially using stride 2
3x3 conv, 128
3x3 conv
(/2 in each dimension) 3x3 conv, 128, / 2
3x3 conv, 64
- Additional conv layer at
3x3 conv, 64
the beginning (stem)
3x3 conv, 64
X
3x3 conv, 64
Residual block
3x3 conv, 64
3x3 conv, 64
Pool
7x7 conv, 64, / 2 Beginning
Input conv layer |
| Stanford CS231n 10th Anniversary Lecture 6 - 55 April 17, 2025 |


---
## Page 56
---


Softmax
Case Study: ResNet
FC 1000
Pool
[He et al., 2015] 3x3 conv, 512
3x3 conv, 512
3x3 conv, 512
3x3 conv, 512
3x3 conv, 512
Total depths of 18, 34, 50, 3x3 conv, 512, /2
101, or 152 layers for ..
.
ImageNet
3x3 conv, 128
3x3 conv, 128
3x3 conv, 128
3x3 conv, 128
3x3 conv, 128
3x3 conv, 128, / 2
3x3 conv, 64
3x3 conv, 64
3x3 conv, 64
3x3 conv, 64
3x3 conv, 64
3x3 conv, 64
Pool
7x7 conv, 64, / 2
Input
Stanford CS231n 10th Anniversary Lecture 6 - 56 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Softmax
Case Study: ResNet
FC 1000
Pool
[He et al., 2015] 3x3 conv, 512
3x3 conv, 512
3x3 conv, 512
3x3 conv, 512
3x3 conv, 512
Total depths of 18, 34, 50, 3x3 conv, 512, /2
101, or 152 layers for ..
.
ImageNet
3x3 conv, 128
3x3 conv, 128
3x3 conv, 128
3x3 conv, 128
3x3 conv, 128
3x3 conv, 128, / 2
3x3 conv, 64
3x3 conv, 64
3x3 conv, 64
3x3 conv, 64
3x3 conv, 64
3x3 conv, 64
Pool
7x7 conv, 64, / 2
Input |
| Stanford CS231n 10th Anniversary Lecture 6 - 56 April 17, 2025 |


---
## Page 57
---


Softmax
Case Study: ResNet
FC 1000
Pool
3x3 conv, 64
[He et al., 2015]
3x3 conv, 64
3x3 conv, 64
relu 3x3 conv, 64
Very deep networks using residual
F(x) + x 3x3 conv, 64
connections 3x3 conv, 64
..
.
conv
- 152-layer model for ImageNet 3x3 conv, 128
X 3x3 conv, 128
F(x)
relu
- ILSVRC’15 classification winner
identity 3x3 conv, 128
3x3 conv, 128
(3.57% top 5 error)
conv
3x3 conv, 128
- Swept all classification and 3x3 conv, 128 / 2
3x3 conv, 64
detection competitions in
3x3 conv, 64
X
ILSVRC’15 and COCO’15! 3x3 conv, 64
Residual block
3x3 conv, 64
3x3 conv, 64
3x3 conv, 64
Pool
7x7 conv, 64 / 2
Input
Stanford CS231n 10th Anniversary Lecture 6 - 57 April 17, 2025

[Page contains 2 table(s)]


### Table 1

| Softmax
Case Study: ResNet
FC 1000
Pool
3x3 conv, 64
[He et al., 2015]
3x3 conv, 64
3x3 conv, 64
relu 3x3 conv, 64
Very deep networks using residual
F(x) + x 3x3 conv, 64
connections 3x3 conv, 64
..
.
conv
- 152-layer model for ImageNet 3x3 conv, 128
X 3x3 conv, 128
F(x)
relu
- ILSVRC’15 classification winner
identity 3x3 conv, 128
3x3 conv, 128
(3.57% top 5 error)
conv
3x3 conv, 128
- Swept all classification and 3x3 conv, 128 / 2
3x3 conv, 64
detection competitions in
3x3 conv, 64
X
ILSVRC’15 and COCO’15! 3x3 conv, 64
Residual block
3x3 conv, 64
3x3 conv, 64
3x3 conv, 64
Pool
7x7 conv, 64 / 2
Input |
| Stanford CS231n 10th Anniversary Lecture 6 - 57 April 17, 2025 |


### Table 2

| 3x3 conv, 128 |
| 3x3 conv, 128 |


---
## Page 58
---


Lecture Overview – Two Broad Sets of Topics
Layers in CNNs
Activation Functions
How to build CNNs?
CNN Architectures
Weight Initialization
Data Preprocessing
Data augmentation
How to train CNNs?
Transfer Learning
Hyperparameter Selection
Stanford CS231n 10th Anniversary Lecture 6 - 58 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture Overview – Two Broad Sets of Topics
Layers in CNNs
Activation Functions
How to build CNNs?
CNN Architectures
Weight Initialization
Data Preprocessing
Data augmentation
How to train CNNs?
Transfer Learning
Hyperparameter Selection |
| Stanford CS231n 10th Anniversary Lecture 6 - 58 April 17, 2025 |


---
## Page 59
---


How to initialize weights in neural
network layers?
Stanford CS231n 10th Anniversary Lecture 6 - 59 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| How to initialize weights in neural
network layers? |
| Stanford CS231n 10th Anniversary Lecture 6 - 59 April 17, 2025 |


---
## Page 60
---


Weight Initialization Case: Values too small
Forward pass for a 6-layer
net with hidden size 4096
Stanford CS231n 10th Anniversary Lecture 6 - 60 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Weight Initialization Case: Values too small
Forward pass for a 6-layer
net with hidden size 4096 |
| Stanford CS231n 10th Anniversary Lecture 6 - 60 April 17, 2025 |


[Page contains 1 image(s)]


---
## Page 61
---


Weight Initialization Case: Values too small
All activations tend to zero
for deeper network layers
Stanford CS231n 10th Anniversary Lecture 6 - 61 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Weight Initialization Case: Values too small
All activations tend to zero
for deeper network layers |
| Stanford CS231n 10th Anniversary Lecture 6 - 61 April 17, 2025 |


[Page contains 2 image(s)]


---
## Page 62
---


Weight Initialization Case: Values too large
Increase std of initial
weights from 0.01 to 0.05
Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
62

[Page contains 1 table(s)]


### Table 1

| Weight Initialization Case: Values too large
Increase std of initial
weights from 0.01 to 0.05 |
| Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
62 |


[Page contains 1 image(s)]


---
## Page 63
---


Weight Initialization Case: Values too large
Activations blow up quickly
Increase std of initial
weights from 0.01 to 0.05
Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
63

[Page contains 1 table(s)]


### Table 1

| Weight Initialization Case: Values too large
Activations blow up quickly
Increase std of initial
weights from 0.01 to 0.05 |
| Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
63 |


[Page contains 2 image(s)]


---
## Page 64
---


How to fix this? Depends on the size of the layer
He et al, “Delving Deep into Rectifiers: Surpassing Human-Level Performance on ImageNet Classification”, ICCV 2015
Stanford CS231n 10th Anniversary Lecture 6 - 64 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| How to fix this? Depends on the size of the layer
He et al, “Delving Deep into Rectifiers: Surpassing Human-Level Performance on ImageNet Classification”, ICCV 2015 |
| Stanford CS231n 10th Anniversary Lecture 6 - 64 April 17, 2025 |


[Page contains 1 image(s)]


---
## Page 65
---


One solution: Kaiming / MSRA Initialization
“Just right”: Activations are
ReLU correction: std = sqrt(2 / Din)
nicely scaled for all layers!
He et al, “Delving Deep into Rectifiers: Surpassing Human-Level Performance on ImageNet Classification”, ICCV 2015
Stanford CS231n 10th Anniversary Lecture 6 - 65 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| One solution: Kaiming / MSRA Initialization
“Just right”: Activations are
ReLU correction: std = sqrt(2 / Din)
nicely scaled for all layers!
He et al, “Delving Deep into Rectifiers: Surpassing Human-Level Performance on ImageNet Classification”, ICCV 2015 |
| Stanford CS231n 10th Anniversary Lecture 6 - 65 April 17, 2025 |


[Page contains 2 image(s)]


---
## Page 66
---


Lecture Overview – Two Broad Sets of Topics
Layers in CNNs
Activation Functions
How to build CNNs?
CNN Architectures
Weight Initialization
Data Preprocessing
Data augmentation
How to train CNNs?
Transfer Learning
Hyperparameter Selection
Stanford CS231n 10th Anniversary Lecture 6 - 66 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture Overview – Two Broad Sets of Topics
Layers in CNNs
Activation Functions
How to build CNNs?
CNN Architectures
Weight Initialization
Data Preprocessing
Data augmentation
How to train CNNs?
Transfer Learning
Hyperparameter Selection |
| Stanford CS231n 10th Anniversary Lecture 6 - 66 April 17, 2025 |


---
## Page 67
---


TLDR for Image Normalization: center and scale
for each channel
- Subtract per-channel mean and
Divide by per-channel std
(almost all modern models)
(stats along each channel = 3 numbers)
- Requires pre-computing means and std for each
pixel channel (given your dataset)
Stanford CS231n 10th Anniversary Lecture 6 - 67 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| TLDR for Image Normalization: center and scale
for each channel
- Subtract per-channel mean and
Divide by per-channel std
(almost all modern models)
(stats along each channel = 3 numbers)
- Requires pre-computing means and std for each
pixel channel (given your dataset) |
| Stanford CS231n 10th Anniversary Lecture 6 - 67 April 17, 2025 |


[Page contains 1 image(s)]


---
## Page 68
---


Lecture Overview – Two Broad Sets of Topics
Layers in CNNs
Activation Functions
How to build CNNs?
CNN Architectures
Weight Initialization
Data Preprocessing
Data augmentation
How to train CNNs?
Transfer Learning
Hyperparameter Selection
Stanford CS231n 10th Anniversary Lecture 6 - 68 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture Overview – Two Broad Sets of Topics
Layers in CNNs
Activation Functions
How to build CNNs?
CNN Architectures
Weight Initialization
Data Preprocessing
Data augmentation
How to train CNNs?
Transfer Learning
Hyperparameter Selection |
| Stanford CS231n 10th Anniversary Lecture 6 - 68 April 17, 2025 |


---
## Page 69
---


Regularization: A common pattern
Training: Add some kind of randomness
Testing: Average out randomness (sometimes approximate)
Stanford CS231n 10th Anniversary Lecture 6 - 69 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Regularization: A common pattern
Training: Add some kind of randomness
Testing: Average out randomness (sometimes approximate) |
| Stanford CS231n 10th Anniversary Lecture 6 - 69 April 17, 2025 |


[Page contains 2 image(s)]


---
## Page 70
---


Regularization: A common pattern
Example: Dropout
Training: Add some kind
of randomness
Training:
Randomly drop
activations
Testing: Average out randomness
Testing: Use all
(sometimes approximate)
activations and
average values
with p
Stanford CS231n 10th Anniversary Lecture 6 - 70 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Regularization: A common pattern
Example: Dropout
Training: Add some kind
of randomness
Training:
Randomly drop
activations
Testing: Average out randomness
Testing: Use all
(sometimes approximate)
activations and
average values
with p |
| Stanford CS231n 10th Anniversary Lecture 6 - 70 April 17, 2025 |


[Page contains 2 image(s)]


---
## Page 71
---


Regularization: Data Augmentation
“cat”
Load image
and label
Compute
loss
CNN
Transform image
Stanford CS231n 10th Anniversary Lecture 6 - 71 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Regularization: Data Augmentation
“cat”
Load image
and label
Compute
loss
CNN
Transform image |
| Stanford CS231n 10th Anniversary Lecture 6 - 71 April 17, 2025 |


[Page contains 2 image(s)]


---
## Page 72
---


Data Augmentation
Horizontal Flips
Stanford CS231n 10th Anniversary Lecture 6 - 72 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Data Augmentation
Horizontal Flips |
| Stanford CS231n 10th Anniversary Lecture 6 - 72 April 17, 2025 |


[Page contains 2 image(s)]


---
## Page 73
---


Data Augmentation
Random crops and scales
Training: sample random crops / scales
ResNet:
1. Pick random L in range [256, 480]
2. Resize training image, short side = L
3. Sample random 224 x 224 patch
Test Time Augmentation: average a fixed set of crops
ResNet:
1. Resize image at 5 scales: {224, 256, 384, 480, 640}
2. For each size, use 10 224 x 224 crops: 4 corners + center, + flips
Stanford CS231n 10th Anniversary Lecture 6 - 73 April 17, 2025

[Page contains 2 table(s)]


### Table 1

| Data Augmentation
Random crops and scales
Training: sample random crops / scales
ResNet:
1. Pick random L in range [256, 480]
2. Resize training image, short side = L
3. Sample random 224 x 224 patch
Test Time Augmentation: average a fixed set of crops
ResNet:
1. Resize image at 5 scales: {224, 256, 384, 480, 640}
2. For each size, use 10 224 x 224 crops: 4 corners + center, + flips |
| Stanford CS231n 10th Anniversary Lecture 6 - 73 April 17, 2025 |


### Table 2

|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |


[Page contains 1 image(s)]


---
## Page 74
---


Data Augmentation
Color Jitter
Simple: Randomize
contrast and brightness
Stanford CS231n 10th Anniversary Lecture 6 - 74 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Data Augmentation
Color Jitter
Simple: Randomize
contrast and brightness |
| Stanford CS231n 10th Anniversary Lecture 6 - 74 April 17, 2025 |


[Page contains 2 image(s)]


---
## Page 75
---


Regularization: Cutout
Training: Set random image regions to zero
Testing: Use full image
Examples:
Dropout
Data Augmentation
Cutout / Random Crop
Works very well for small datasets like CIFAR,
DeVries and Taylor, “Improved Regularization of less common for large datasets like ImageNet
Convolutional Neural Networks with Cutout”, arXiv 2017
Stanford CS231n 10th Anniversary Lecture 6 - 75 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Regularization: Cutout
Training: Set random image regions to zero
Testing: Use full image
Examples:
Dropout
Data Augmentation
Cutout / Random Crop
Works very well for small datasets like CIFAR,
DeVries and Taylor, “Improved Regularization of less common for large datasets like ImageNet
Convolutional Neural Networks with Cutout”, arXiv 2017 |
| Stanford CS231n 10th Anniversary Lecture 6 - 75 April 17, 2025 |


[Page contains 4 image(s)]


---
## Page 76
---


Lecture Overview – Two Broad Sets of Topics
Layers in CNNs
Activation Functions
How to build CNNs?
CNN Architectures
Weight Initialization
Data Preprocessing
Data augmentation
How to train CNNs?
Transfer Learning
Hyperparameter Selection
Stanford CS231n 10th Anniversary Lecture 6 - 76 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture Overview – Two Broad Sets of Topics
Layers in CNNs
Activation Functions
How to build CNNs?
CNN Architectures
Weight Initialization
Data Preprocessing
Data augmentation
How to train CNNs?
Transfer Learning
Hyperparameter Selection |
| Stanford CS231n 10th Anniversary Lecture 6 - 76 April 17, 2025 |


---
## Page 77
---


What if you don’t have a lot of data? Can
you still train CNNs?
Stanford CS231n 10th Anniversary Lecture 6 - 77 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| What if you don’t have a lot of data? Can
you still train CNNs? |
| Stanford CS231n 10th Anniversary Lecture 6 - 77 April 17, 2025 |


---
## Page 78
---


Transfer Learning with CNNs
AlexNet:
64 x 3 x 11 x 11
(More on this in Lecture 13)
Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
78

[Page contains 1 table(s)]


### Table 1

| Transfer Learning with CNNs
AlexNet:
64 x 3 x 11 x 11
(More on this in Lecture 13) |
| Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
78 |


[Page contains 2 image(s)]


---
## Page 79
---


Transfer Learning with CNNs
L2 Nearest neighbors in feature space
Test image
(More on this in Lecture 13)
Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
79

[Page contains 1 table(s)]


### Table 1

| Transfer Learning with CNNs
L2 Nearest neighbors in feature space
Test image
(More on this in Lecture 13) |
| Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
79 |


[Page contains 2 image(s)]


---
## Page 80
---


Donahue et al, “DeCAF: A Deep Convolutional Activation
Feature for Generic Visual Recognition”, ICML 2014
Transfer Learning with CNNs
Razavian et al, “CNN Features Off-the-Shelf: An
Astounding Baseline for Recognition”, CVPR Workshops
2014
1. Train on Imagenet (or internet scale data)
FC-1000
FC-4096
FC-4096
MaxPool
Conv-512
Conv-512
MaxPool
Conv-512
Conv-512
MaxPool
Conv-256
Conv-256
MaxPool
Conv-128
Conv-128
MaxPool
Conv-64
Conv-64
Image
Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
80

[Page contains 1 table(s)]


### Table 1

| Donahue et al, “DeCAF: A Deep Convolutional Activation
Feature for Generic Visual Recognition”, ICML 2014
Transfer Learning with CNNs
Razavian et al, “CNN Features Off-the-Shelf: An
Astounding Baseline for Recognition”, CVPR Workshops
2014
1. Train on Imagenet (or internet scale data)
FC-1000
FC-4096
FC-4096
MaxPool
Conv-512
Conv-512
MaxPool
Conv-512
Conv-512
MaxPool
Conv-256
Conv-256
MaxPool
Conv-128
Conv-128
MaxPool
Conv-64
Conv-64
Image |
| Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
80 |


---
## Page 81
---


Donahue et al, “DeCAF: A Deep Convolutional Activation
Feature for Generic Visual Recognition”, ICML 2014
Transfer Learning with CNNs
Razavian et al, “CNN Features Off-the-Shelf: An
Astounding Baseline for Recognition”, CVPR Workshops
2014
1. Train on Imagenet 2. Small Dataset (C classes)
FC-1000 FC-C
FC-4096 FC-4096
Reinitialize
FC-4096 FC-4096
this and train
MaxPool MaxPool
Conv-512 Conv-512
Conv-512 Conv-512
MaxPool MaxPool
Conv-512 Conv-512
Conv-512 Conv-512
MaxPool MaxPool Freeze these from
Conv-256 Conv-256 pretrained model
Conv-256 Conv-256
MaxPool MaxPool
Conv-128 Conv-128
Conv-128 Conv-128
MaxPool MaxPool
Conv-64 Conv-64
Conv-64 Conv-64
Image Image
Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
81

[Page contains 1 table(s)]


### Table 1

| Donahue et al, “DeCAF: A Deep Convolutional Activation
Feature for Generic Visual Recognition”, ICML 2014
Transfer Learning with CNNs
Razavian et al, “CNN Features Off-the-Shelf: An
Astounding Baseline for Recognition”, CVPR Workshops
2014
1. Train on Imagenet 2. Small Dataset (C classes)
FC-1000 FC-C
FC-4096 FC-4096
Reinitialize
FC-4096 FC-4096
this and train
MaxPool MaxPool
Conv-512 Conv-512
Conv-512 Conv-512
MaxPool MaxPool
Conv-512 Conv-512
Conv-512 Conv-512
MaxPool MaxPool Freeze these from
Conv-256 Conv-256 pretrained model
Conv-256 Conv-256
MaxPool MaxPool
Conv-128 Conv-128
Conv-128 Conv-128
MaxPool MaxPool
Conv-64 Conv-64
Conv-64 Conv-64
Image Image |
| Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
81 |


---
## Page 82
---


Donahue et al, “DeCAF: A Deep Convolutional Activation
Feature for Generic Visual Recognition”, ICML 2014
Transfer Learning with CNNs
Razavian et al, “CNN Features Off-the-Shelf: An
Astounding Baseline for Recognition”, CVPR Workshops
2014
1. Train on Imagenet 2. Small Dataset (C classes) 3. Bigger dataset
FC-1000 FC-C FC-C
FC-4096 FC-4096 FC-4096
Reinitialize
FC-4096 FC-4096 FC-4096
this and train
MaxPool MaxPool MaxPool
Initialize from
Conv-512 Conv-512 Conv-512
pretrained
Conv-512 Conv-512 Conv-512
model, then
MaxPool MaxPool MaxPool
Conv-512 Conv-512 Conv-512 finetune
Conv-512 Conv-512 Conv-512
everything
MaxPool MaxPool Freeze these from MaxPool
Conv-256 Conv-256 pretrained model Conv-256
Conv-256 Conv-256 Conv-256
With bigger
MaxPool MaxPool MaxPool
dataset, it’s
Conv-128 Conv-128 Conv-128
better to train
Conv-128 Conv-128 Conv-128
more layers
MaxPool MaxPool MaxPool
Conv-64 Conv-64 Conv-64
Conv-64 Conv-64 Conv-64
Image Image Image
Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
82

[Page contains 1 table(s)]


### Table 1

| Donahue et al, “DeCAF: A Deep Convolutional Activation
Feature for Generic Visual Recognition”, ICML 2014
Transfer Learning with CNNs
Razavian et al, “CNN Features Off-the-Shelf: An
Astounding Baseline for Recognition”, CVPR Workshops
2014
1. Train on Imagenet 2. Small Dataset (C classes) 3. Bigger dataset
FC-1000 FC-C FC-C
FC-4096 FC-4096 FC-4096
Reinitialize
FC-4096 FC-4096 FC-4096
this and train
MaxPool MaxPool MaxPool
Initialize from
Conv-512 Conv-512 Conv-512
pretrained
Conv-512 Conv-512 Conv-512
model, then
MaxPool MaxPool MaxPool
Conv-512 Conv-512 Conv-512 finetune
Conv-512 Conv-512 Conv-512
everything
MaxPool MaxPool Freeze these from MaxPool
Conv-256 Conv-256 pretrained model Conv-256
Conv-256 Conv-256 Conv-256
With bigger
MaxPool MaxPool MaxPool
dataset, it’s
Conv-128 Conv-128 Conv-128
better to train
Conv-128 Conv-128 Conv-128
more layers
MaxPool MaxPool MaxPool
Conv-64 Conv-64 Conv-64
Conv-64 Conv-64 Conv-64
Image Image Image |
| Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
82 |


---
## Page 83
---


very similar very different
FC-1000
FC-4096
dataset dataset
FC-4096
MaxPool
Conv-512
Conv-512 very little data ? ?
MaxPool More specific
Conv-512
Conv-512
MaxPool
Conv-256
More generic
Conv-256
MaxPool
Conv-128
quite a lot of ? ?
Conv-128
MaxPool data
Conv-64
Conv-64
Image
Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
83

[Page contains 2 table(s)]


### Table 1

| very similar very different
FC-1000
FC-4096
dataset dataset
FC-4096
MaxPool
Conv-512
Conv-512 very little data ? ?
MaxPool More specific
Conv-512
Conv-512
MaxPool
Conv-256
More generic
Conv-256
MaxPool
Conv-128
quite a lot of ? ?
Conv-128
MaxPool data
Conv-64
Conv-64
Image |
| Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
83 |


### Table 2

|  | very similar
dataset | very different
dataset |
| very little data | ? | ? |
| quite a lot of
data | ? | ? |


---
## Page 84
---


very similar very different
FC-1000
FC-4096
dataset dataset
FC-4096
MaxPool
Conv-512
Conv-512 very little data Use Linear ?
MaxPool More specific
Classifier on
Conv-512
Conv-512 final layer
MaxPool
Conv-256
More generic
Conv-256
MaxPool
Conv-128
quite a lot of Finetune all ?
Conv-128
MaxPool data model layers
Conv-64
Conv-64
Image
Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
84

[Page contains 2 table(s)]


### Table 1

| very similar very different
FC-1000
FC-4096
dataset dataset
FC-4096
MaxPool
Conv-512
Conv-512 very little data Use Linear ?
MaxPool More specific
Classifier on
Conv-512
Conv-512 final layer
MaxPool
Conv-256
More generic
Conv-256
MaxPool
Conv-128
quite a lot of Finetune all ?
Conv-128
MaxPool data model layers
Conv-64
Conv-64
Image |
| Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
84 |


### Table 2

|  | very similar
dataset | very different
dataset |
| very little data | Use Linear
Classifier on
final layer | ? |
| quite a lot of
data | Finetune all
model layers | ? |


---
## Page 85
---


very similar very different
FC-1000
FC-4096
dataset dataset
FC-4096
MaxPool
Conv-512
Conv-512 very little data Use Linear Try another
MaxPool More specific
Classifier on model or collect
Conv-512
Conv-512 final layer more data L
MaxPool
Conv-256
More generic
Conv-256
MaxPool
Conv-128
quite a lot of Finetune all Either finetune
Conv-128
MaxPool data model layers all model layers
Conv-64
or train from
Conv-64
Image scratch!
Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
85

[Page contains 2 table(s)]


### Table 1

| very similar very different
FC-1000
FC-4096
dataset dataset
FC-4096
MaxPool
Conv-512
Conv-512 very little data Use Linear Try another
MaxPool More specific
Classifier on model or collect
Conv-512
Conv-512 final layer more data L
MaxPool
Conv-256
More generic
Conv-256
MaxPool
Conv-128
quite a lot of Finetune all Either finetune
Conv-128
MaxPool data model layers all model layers
Conv-64
or train from
Conv-64
Image scratch! |
| Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
85 |


### Table 2

|  | very similar
dataset | very different
dataset |
| very little data | Use Linear
Classifier on
final layer | Try another
model or collect
more data L |
| quite a lot of
data | Finetune all
model layers | Either finetune
all model layers
or train from
scratch! |


---
## Page 86
---


Takeaway for your projects and beyond:
Have some dataset of interest but it has < ~1M images?
1. Find a very large dataset that has
similar data, train a big model there
2. Transfer learn to your dataset
Deep learning frameworks provide a “Model Zoo” of pretrained
models so you don’t need to train your own
PyTorch: https://github.com/pytorch/vision
Huggingface: https://github.com/huggingface/pytorch-image-models
Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
86

[Page contains 1 table(s)]


### Table 1

| Takeaway for your projects and beyond:
Have some dataset of interest but it has < ~1M images?
1. Find a very large dataset that has
similar data, train a big model there
2. Transfer learn to your dataset
Deep learning frameworks provide a “Model Zoo” of pretrained
models so you don’t need to train your own
PyTorch: https://github.com/pytorch/vision
Huggingface: https://github.com/huggingface/pytorch-image-models |
| Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
86 |


---
## Page 87
---


Lecture Overview – Two Broad Sets of Topics
Layers in CNNs
Activation Functions
How to build CNNs?
CNN Architectures
Weight Initialization
Data Preprocessing
Data augmentation
How to train CNNs?
Transfer Learning
Hyperparameter Selection
Stanford CS231n 10th Anniversary Lecture 6 - 87 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture Overview – Two Broad Sets of Topics
Layers in CNNs
Activation Functions
How to build CNNs?
CNN Architectures
Weight Initialization
Data Preprocessing
Data augmentation
How to train CNNs?
Transfer Learning
Hyperparameter Selection |
| Stanford CS231n 10th Anniversary Lecture 6 - 87 April 17, 2025 |


---
## Page 88
---


Choosing Hyperparameters
Step 1: Check initial loss
Step 2: Overfit a small sample
Step 3: Find LR that makes loss go down
Use the architecture from the previous step, use all training
data, turn on small weight decay, find a learning rate that
makes the loss drop significantly within ~100 iterations
Good learning rates to try: 1e-1, 1e-2, 1e-3, 1e-4, 1e-5
Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
88

[Page contains 1 table(s)]


### Table 1

| Choosing Hyperparameters
Step 1: Check initial loss
Step 2: Overfit a small sample
Step 3: Find LR that makes loss go down
Use the architecture from the previous step, use all training
data, turn on small weight decay, find a learning rate that
makes the loss drop significantly within ~100 iterations
Good learning rates to try: 1e-1, 1e-2, 1e-3, 1e-4, 1e-5 |
| Stanford CS231n 10th Anniversary Lecture 6 - April 17, 2025
88 |


---
## Page 89
---


Choosing Hyperparameters
Step 1: Check initial loss
Step 2: Overfit a small sample
Step 3: Find LR that makes loss go down
Step 4: Coarse grid of hyperparams, train for ~1-5 epochs
Step 5: Refine grid, train longer
Step 6: Look at loss and accuracy curves (next slides)
Stanford CS231n 10th Anniversary Lecture 6 - 89 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Choosing Hyperparameters
Step 1: Check initial loss
Step 2: Overfit a small sample
Step 3: Find LR that makes loss go down
Step 4: Coarse grid of hyperparams, train for ~1-5 epochs
Step 5: Refine grid, train longer
Step 6: Look at loss and accuracy curves (next slides) |
| Stanford CS231n 10th Anniversary Lecture 6 - 89 April 17, 2025 |


---
## Page 90
---


Accuracy still going up, you
Accuracy
need to train longer
Train
Val
time
Stanford CS231n 10th Anniversary Lecture 6 - 90 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Accuracy still going up, you
Accuracy
need to train longer
Train
Val
time |
| Stanford CS231n 10th Anniversary Lecture 6 - 90 April 17, 2025 |


---
## Page 91
---


Q: What is happening here?
Accuracy
Train
Val
time
Stanford CS231n 10th Anniversary Lecture 6 - 91 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Q: What is happening here?
Accuracy
Train
Val
time |
| Stanford CS231n 10th Anniversary Lecture 6 - 91 April 17, 2025 |


---
## Page 92
---


Huge train / val gap means
Accuracy
overfitting! Increase regularization
or get more data
Train
Val
time
Stanford CS231n 10th Anniversary Lecture 6 - 92 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Huge train / val gap means
Accuracy
overfitting! Increase regularization
or get more data
Train
Val
time |
| Stanford CS231n 10th Anniversary Lecture 6 - 92 April 17, 2025 |


---
## Page 93
---


No gap between train / val means
Accuracy
underfitting: train longer, can
possibly use a bigger model
Train
Val
time
Stanford CS231n 10th Anniversary Lecture 6 - 93 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| No gap between train / val means
Accuracy
underfitting: train longer, can
possibly use a bigger model
Train
Val
time |
| Stanford CS231n 10th Anniversary Lecture 6 - 93 April 17, 2025 |


---
## Page 94
---


Choosing Hyperparameters
Step 1: Check initial loss
Step 2: Overfit a small sample
Step 3: Find LR that makes loss go down
Step 4: Coarse grid, train for ~1-5 epochs
Step 5: Refine grid, train longer
Step 6: Look at loss and accuracy curves
Step 7: GOTO step 5
Stanford CS231n 10th Anniversary Lecture 6 - 94 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Choosing Hyperparameters
Step 1: Check initial loss
Step 2: Overfit a small sample
Step 3: Find LR that makes loss go down
Step 4: Coarse grid, train for ~1-5 epochs
Step 5: Refine grid, train longer
Step 6: Look at loss and accuracy curves
Step 7: GOTO step 5 |
| Stanford CS231n 10th Anniversary Lecture 6 - 94 April 17, 2025 |


---
## Page 95
---


Random Search vs. Grid Search
Important Parameter Important Parameter
Stanford CS231n 10th Anniversary Lecture 6 - 95 April 17, 2025
retemaraP
tnatropminU
retemaraP
tnatropminU
Random Search for Hyper-
Parameter Optimization
Bergstra and Bengio, 2012
Grid Layout Random Layout
Illustration of Bergstra et al., 2012 by Shayne
Longpre, copyright CS231n 2017

[Page contains 3 table(s)]


### Table 1

| Random Search for Hyper-
Random Search vs. Grid Search
Parameter Optimization
Bergstra and Bengio, 2012
Grid Layout Random Layout
retemaraP retemaraP
tnatropminU tnatropminU
Important Parameter Important Parameter
Illustration of Bergstra et al., 2012 by Shayne
Longpre, copyright CS231n 2017 |
| Stanford CS231n 10th Anniversary Lecture 6 - 95 April 17, 2025 |


### Table 2

|  |  |  |  |


### Table 3

|  |  |  |  |


---
## Page 96
---


Summary
We reviewed 8 topics at a high level:
1. Layers in CNNs
(Conv, FC, Norm, Dropout)
2. Activation Functions in NNs
(ReLU, GELU, etc.)
3. CNN Architectures
(VGG, ResNets)
4. Weight Initialization
(Maintain Activation Distribution)
Stanford CS231n 10th Anniversary Lecture 6 - 96 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Summary
We reviewed 8 topics at a high level:
1. Layers in CNNs
(Conv, FC, Norm, Dropout)
2. Activation Functions in NNs
(ReLU, GELU, etc.)
3. CNN Architectures
(VGG, ResNets)
4. Weight Initialization
(Maintain Activation Distribution) |
| Stanford CS231n 10th Anniversary Lecture 6 - 96 April 17, 2025 |


---
## Page 97
---


Summary
We reviewed 8 topics at a high level:
5. Data Preprocessing
(subtract mean, divide std)
6. Data augmentation
(cropping, jitter)
7. Transfer Learning
(train on ImageNet first)
8. Hyperparameter
(Checking Losses + Random Search)
Stanford CS231n 10th Anniversary Lecture 6 - 97 April 17, 2025

[Page contains 1 table(s)]


### Table 1

| Summary
We reviewed 8 topics at a high level:
5. Data Preprocessing
(subtract mean, divide std)
6. Data augmentation
(cropping, jitter)
7. Transfer Learning
(train on ImageNet first)
8. Hyperparameter
(Checking Losses + Random Search) |
| Stanford CS231n 10th Anniversary Lecture 6 - 97 April 17, 2025 |
