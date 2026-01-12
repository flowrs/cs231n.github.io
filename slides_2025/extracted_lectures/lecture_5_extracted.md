# lecture_5

Extracted using pdfplumber



---
## Page 1
---


Lecture 5:
Image Classification with CNNs
Stanford CS231n 10th Anniversary Lecture 5 - 1 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture 5:
Image Classification with CNNs |
| Stanford CS231n 10th Anniversary Lecture 5 - 1 April 15, 2025 |


---
## Page 2
---


Administrative: Assignment 1
Assignment 1 Due Wednesday 4/23 at 11:59pm
- K-Nearest Neighbor
- Linear classifiers: SVM, Softmax
- Two-layer neural network
- Image features
Stanford CS231n 10th Anniversary Lecture 5 - 2 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Administrative: Assignment 1
Assignment 1 Due Wednesday 4/23 at 11:59pm
- K-Nearest Neighbor
- Linear classifiers: SVM, Softmax
- Two-layer neural network
- Image features |
| Stanford CS231n 10th Anniversary Lecture 5 - 2 April 15, 2025 |


---
## Page 3
---


Administrative: Project Proposal
Due Fri 4/25
TA expertise is posted on the webpage.
http://cs231n.stanford.edu/office_hours.html
Stanford CS231n 10th Anniversary Lecture 5 - 3 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Administrative: Project Proposal
Due Fri 4/25
TA expertise is posted on the webpage.
http://cs231n.stanford.edu/office_hours.html |
| Stanford CS231n 10th Anniversary Lecture 5 - 3 April 15, 2025 |


---
## Page 4
---


Hi I’m Justin
Facebook AI Research World Labs
Stanford, PhD University of Michigan
2010 2015 2020 2025
I taught CS231N at I taught the same course
Stanford from 2015-2018 at Michigan 2019-2022
Stanford CS231n 10th Anniversary Lecture 5 - 4 April 15, 2025

[Page contains 9 table(s)]


### Table 1

| Hi I’m Justin
Facebook AI Research World Labs
Stanford, PhD University of Michigan
2010 2015 2020 2025
I taught CS231N at I taught the same course
Stanford from 2015-2018 at Michigan 2019-2022 |
| Stanford CS231n 10th Anniversary Lecture 5 - 4 April 15, 2025 |


### Table 2

|  |  |
|  |  |


### Table 3

|  |  |
|  |  |


### Table 4

|  |  |
|  |  |


### Table 5

|  |  |
|  |  |


### Table 6

|  |  |
|  |  |


### Table 7

|  |
|  |


### Table 8

|  |
|  |


### Table 9

|  |
|  |


---
## Page 5
---


CS231n: Deep Learning for Computer Vision
● Deep Learning Basics (Lecture 2 – 4)
● Perceiving and Understanding the Visual World (Lecture 5 – 12)
● Generative and Interactive Visual Intelligence (Lecture 13 – 16)
● Human-Centered Applications and Implications (Lecture 17 – 18)
Stanford CS231n 10th Anniversary Lecture 5 - 5 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| CS231n: Deep Learning for Computer Vision
● Deep Learning Basics (Lecture 2 – 4)
● Perceiving and Understanding the Visual World (Lecture 5 – 12)
● Generative and Interactive Visual Intelligence (Lecture 13 – 16)
● Human-Centered Applications and Implications (Lecture 17 – 18) |
| Stanford CS231n 10th Anniversary Lecture 5 - 5 April 15, 2025 |


---
## Page 6
---


Recap: Image Classification with Linear Classifier
f(x,W) = Wx + b
Stanford CS231n 10th Anniversary Lecture 5 - 6 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Recap: Image Classification with Linear Classifier
f(x,W) = Wx + b |
| Stanford CS231n 10th Anniversary Lecture 5 - 6 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 7
---


Recap: Loss Function
- We have some dataset of (x,y)
- We have a score function:
- We have a loss function:
Softmax
Full loss
Stanford CS231n 10th Anniversary Lecture 5 - 7 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Recap: Loss Function
- We have some dataset of (x,y)
- We have a score function:
- We have a loss function:
Softmax
Full loss |
| Stanford CS231n 10th Anniversary Lecture 5 - 7 April 15, 2025 |


[Page contains 4 image(s)]


---
## Page 8
---


Recap: Optimization
SGD
SGD+Momentum
RMSProp
Adam
Stanford CS231n 10th Anniversary Lecture 5 - 8 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Recap: Optimization
SGD
SGD+Momentum
RMSProp
Adam |
| Stanford CS231n 10th Anniversary Lecture 5 - 8 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 9
---


Problem: Linear Classifiers are not very powerful
Visual Viewpoint Geometric Viewpoint
Linear classifiers learn Linear classifiers can
one template per class only draw linear
decision boundaries
Stanford CS231n 10th Anniversary Lecture 5 - 9 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Problem: Linear Classifiers are not very powerful
Visual Viewpoint Geometric Viewpoint
Linear classifiers learn Linear classifiers can
one template per class only draw linear
decision boundaries |
| Stanford CS231n 10th Anniversary Lecture 5 - 9 April 15, 2025 |


[Page contains 3 image(s)]


---
## Page 10
---


Last time: Neural Networks
Linear score function:
2-layer Neural Network
x W1 h W2 s
10
3072 100
Stanford CS231n 10th Anniversary Lecture 5 - 10 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Last time: Neural Networks
Linear score function:
2-layer Neural Network
x W1 h W2 s
10
3072 100 |
| Stanford CS231n 10th Anniversary Lecture 5 - 10 April 15, 2025 |


[Page contains 3 image(s)]


---
## Page 11
---


Last time: Computation Graph
x
s (scores)
* hinge + L
loss
W
R
Stanford CS231n 10th Anniversary Lecture 5 - 11 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Last time: Computation Graph
x
s (scores)
* hinge + L
loss
W
R |
| Stanford CS231n 10th Anniversary Lecture 5 - 11 April 15, 2025 |


[Page contains 3 image(s)]


---
## Page 12
---


Last time: Backpropagation
“local gradient”
f
“Downstream
gradients”
“Upstream
gradient”
Stanford CS231n 10th Anniversary Lecture 5 - 12 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Last time: Backpropagation
“local gradient”
f
“Downstream
gradients”
“Upstream
gradient” |
| Stanford CS231n 10th Anniversary Lecture 5 - 12 April 15, 2025 |


[Page contains 8 image(s)]


---
## Page 13
---


Backprop with Vectors
Loss L still a scalar!
D
“local
x
gradients”
D [D x D ]
x x z D
z
f
“Downstream
Matrix-vector
gradients”
multiply
[D x D ]
y z
D
D z
Jacobian
y
matrices
“Upstream gradient”
D For each element of z, how
y
much does it influence L?
Stanford CS231n 10th Anniversary Lecture 5 - 13 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Vectors
Loss L still a scalar!
D
“local
x
gradients”
D [D x D ]
x x z D
z
f
“Downstream
Matrix-vector
gradients”
multiply
[D x D ]
y z
D
D z
Jacobian
y
matrices
“Upstream gradient”
D For each element of z, how
y
much does it influence L? |
| Stanford CS231n 10th Anniversary Lecture 5 - 13 April 15, 2025 |


[Page contains 8 image(s)]


---
## Page 14
---


Backprop with Matrices (or Tensors)
Loss L still a scalar!
dL/dx always has the
[D ×M ]
x x “local
same shape as x!
gradients”
[D ×M ]
x x [(D ×M )×(D ×M )]
x x z z [D ×M ]
z z
“Downstream
Matrix-vector
gradients” [(D ×M )×(D ×M )]
multiply y y z z
[D ×M ]
[D ×M ]
z z
y y
Jacobian
matrices
“Upstream gradient”
[D ×M ]
y y For each element of z, how
For each element of y, how much does
much does it influence L?
it influence each element of z?
Stanford CS231n 10th Anniversary Lecture 5 - 14 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Matrices (or Tensors)
Loss L still a scalar!
dL/dx always has the
[D ×M ]
x x “local
same shape as x!
gradients”
[D ×M ]
x x [(D ×M )×(D ×M )]
x x z z [D ×M ]
z z
“Downstream
Matrix-vector
gradients” [(D ×M )×(D ×M )]
multiply y y z z
[D ×M ]
[D ×M ]
z z
y y
Jacobian
matrices
“Upstream gradient”
[D ×M ]
y y For each element of z, how
For each element of y, how much does
much does it influence L?
it influence each element of z? |
| Stanford CS231n 10th Anniversary Lecture 5 - 14 April 15, 2025 |


[Page contains 8 image(s)]


---
## Page 15
---


CS231n: Deep Learning for Computer Vision
● Deep Learning Basics (Lecture 2 – 4)
● Perceiving and Understanding the Visual World (Lecture 5 – 12)
● Generative and Interactive Visual Intelligence (Lecture 13 – 16)
● Human-Centered Applications and Implications (Lecture 17 – 18)
Stanford CS231n 10th Anniversary Lecture 5 - 15 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| CS231n: Deep Learning for Computer Vision
● Deep Learning Basics (Lecture 2 – 4)
● Perceiving and Understanding the Visual World (Lecture 5 – 12)
● Generative and Interactive Visual Intelligence (Lecture 13 – 16)
● Human-Centered Applications and Implications (Lecture 17 – 18) |
| Stanford CS231n 10th Anniversary Lecture 5 - 15 April 15, 2025 |


---
## Page 16
---


CS231n: Deep Learning for Computer Vision
● Deep Learning Basics (Lecture 2 – 4)
● Perceiving and Understanding the Visual World (Lecture 5 – 12)
● Generative and Interactive Visual Intelligence (Lecture 13 – 16)
● Human-Centered Applications and Implications (Lecture 17 – 18)
Stanford CS231n 10th Anniversary Lecture 5 - 16 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| CS231n: Deep Learning for Computer Vision
● Deep Learning Basics (Lecture 2 – 4)
● Perceiving and Understanding the Visual World (Lecture 5 – 12)
● Generative and Interactive Visual Intelligence (Lecture 13 – 16)
● Human-Centered Applications and Implications (Lecture 17 – 18) |
| Stanford CS231n 10th Anniversary Lecture 5 - 16 April 15, 2025 |


---
## Page 17
---


Today: Convolutional Networks
Fully-Connected Layer Activation Function
We have
already x h s
seen these
Stanford CS231n 10th Anniversary Lecture 5 - 17 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Today: Convolutional Networks
Fully-Connected Layer Activation Function
We have
already x h s
seen these |
| Stanford CS231n 10th Anniversary Lecture 5 - 17 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 18
---


Today: Convolutional Networks
Fully-Connected Layer Activation Function
We have
already x h s
seen these
Convolution Layer Pooling Layer
Today: Image-
specific
operators
Stanford CS231n 10th Anniversary Lecture 5 - 18 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Today: Convolutional Networks
Fully-Connected Layer Activation Function
We have
already x h s
seen these
Convolution Layer Pooling Layer
Today: Image-
specific
operators |
| Stanford CS231n 10th Anniversary Lecture 5 - 18 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 19
---


Image Classification: A core task in Computer Vision
(assume given a set of labels)
{dog, cat, truck, plane, ...}
cat
dog
bird
deer
This imageby Nikitais truck
licensed under CC-BY 2.0
Stanford CS231n 10th Anniversary Lecture 5 - 19 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Image Classification: A core task in Computer Vision
(assume given a set of labels)
{dog, cat, truck, plane, ...}
cat
dog
bird
deer
This imageby Nikitais truck
licensed under CC-BY 2.0 |
| Stanford CS231n 10th Anniversary Lecture 5 - 19 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 20
---


Pixel space
Class
scores
f(x) = Wx
Stanford CS231n 10th Anniversary Lecture 5 - 20 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Pixel space
Class
scores
f(x) = Wx |
| Stanford CS231n 10th Anniversary Lecture 5 - 20 April 15, 2025 |


[Page contains 3 image(s)]


---
## Page 21
---


Image features
f(x) = Wx
Class
scores
Feature Representation
Stanford CS231n 10th Anniversary Lecture 5 - 21 April 15, 2025

[Page contains 3 table(s)]


### Table 1

| Image features
f(x) = Wx
Class
scores
Feature Representation |
| Stanford CS231n 10th Anniversary Lecture 5 - 21 April 15, 2025 |


### Table 2

|  |  |
|  |  |


### Table 3

|  |  |


[Page contains 1 image(s)]


---
## Page 22
---


Example: Color Histogram
+1
Stanford CS231n 10th Anniversary Lecture 5 - 22 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Example: Color Histogram
+1 |
| Stanford CS231n 10th Anniversary Lecture 5 - 22 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 23
---


Example: Histogram of Oriented Gradients (HoG)
Example: 320x240 image gets divided
Divide image into 8x8 pixel regions
into 40x30 bins; in each bin there are 9
Within each region quantize edge
numbers so feature vector has 30*40*9 =
direction into 9 bins
10,800 numbers
Lowe, “Object recognition from local scale-invariant features”, ICCV 1999
Dalaland Triggs, "Histograms of oriented gradients for human detection," CVPR 2005
Stanford CS231n 10th Anniversary Lecture 5 - 23 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Example: Histogram of Oriented Gradients (HoG)
Example: 320x240 image gets divided
Divide image into 8x8 pixel regions
into 40x30 bins; in each bin there are 9
Within each region quantize edge
numbers so feature vector has 30*40*9 =
direction into 9 bins
10,800 numbers
Lowe, “Object recognition from local scale-invariant features”, ICCV 1999
Dalaland Triggs, "Histograms of oriented gradients for human detection," CVPR 2005 |
| Stanford CS231n 10th Anniversary Lecture 5 - 23 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 24
---


Example: Bag of Words
Step 1: Build codebook
Cluster patches to
Extract random form “codebook”
patches of “visual words”
Step 2: Encode images
Fei-Fei and Perona, “A bayesianhierarchical model for learning natural scene categories”, CVPR 2005
Stanford CS231n 10th Anniversary Lecture 5 - 24 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Example: Bag of Words
Step 1: Build codebook
Cluster patches to
Extract random form “codebook”
patches of “visual words”
Step 2: Encode images
Fei-Fei and Perona, “A bayesianhierarchical model for learning natural scene categories”, CVPR 2005 |
| Stanford CS231n 10th Anniversary Lecture 5 - 24 April 15, 2025 |


[Page contains 18 image(s)]


---
## Page 25
---


Image Features
Stanford CS231n 10th Anniversary Lecture 5 - 25 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Image Features |
| Stanford CS231n 10th Anniversary Lecture 5 - 25 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 26
---


Image features vs. ConvNets
f
Feature Extraction
10 numbers giving
scores for classes
training
Krizhevsky, Sutskever, and Hinton, “Imagenet classification
with deep convolutional neural networks”, NIPS 2012.
Figure copyright Krizhevsky, Sutskever, and Hinton, 2012.
Reproduced with permission.
10 numbers giving
scores for classes
training
Stanford CS231n 10th Anniversary Lecture 5 - 26 April 15, 2025

[Page contains 2 table(s)]


### Table 1

| Image features vs. ConvNets
f
Feature Extraction
10 numbers giving
scores for classes
training |
| Krizhevsky, Sutskever, and Hinton, “Imagenet classification
with deep convolutional neural networks”, NIPS 2012.
Figure copyright Krizhevsky, Sutskever, and Hinton, 2012.
Reproduced with permission.
10 numbers giving
scores for classes
training |
| Stanford CS231n 10th Anniversary Lecture 5 - 26 April 15, 2025 |


### Table 2

|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |


[Page contains 3 image(s)]


---
## Page 27
---


Last Time: Neural Networks
Linear score function:
2-layer Neural Network
x W1 h W2 s
10
32x32x3 3072 100
Stanford CS231n 10th Anniversary Lecture 5 - 27 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Last Time: Neural Networks
Linear score function:
2-layer Neural Network
x W1 h W2 s
10
32x32x3 3072 100 |
| Stanford CS231n 10th Anniversary Lecture 5 - 27 April 15, 2025 |


[Page contains 3 image(s)]


---
## Page 28
---


Last Time: Neural Networks
Linear score function:
2-layer Neural Network
Problem: The spatial
structure of images
x W1 h W2 s
is destroyed!
10
32x32x3 3072 100
Stanford CS231n 10th Anniversary Lecture 5 - 28 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Last Time: Neural Networks
Linear score function:
2-layer Neural Network
Problem: The spatial
structure of images
x W1 h W2 s
is destroyed!
10
32x32x3 3072 100 |
| Stanford CS231n 10th Anniversary Lecture 5 - 28 April 15, 2025 |


[Page contains 3 image(s)]


---
## Page 29
---


Next: Convolutional Neural Networks
Illustration of LeCunet al. 1998 from CS231n 2017 Lecture 1
Stanford CS231n 10th Anniversary Lecture 5 - 29 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Next: Convolutional Neural Networks
Illustration of LeCunet al. 1998 from CS231n 2017 Lecture 1 |
| Stanford CS231n 10th Anniversary Lecture 5 - 29 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 30
---


Next: Convolutional Neural Networks
Convolution and pooling operators extract
features while respecting 2D image structure
Illustration of LeCunet al. 1998 from CS231n 2017 Lecture 1
Stanford CS231n 10th Anniversary Lecture 5 - 30 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Next: Convolutional Neural Networks
Convolution and pooling operators extract
features while respecting 2D image structure
Illustration of LeCunet al. 1998 from CS231n 2017 Lecture 1 |
| Stanford CS231n 10th Anniversary Lecture 5 - 30 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 31
---


Next: Convolutional Neural Networks
Convolution and pooling operators extract Fully-Connected layers form an
features while respecting 2D image structure MLP at the end to predict scores
Illustration of LeCunet al. 1998 from CS231n 2017 Lecture 1
Stanford CS231n 10th Anniversary Lecture 5 - 31 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Next: Convolutional Neural Networks
Convolution and pooling operators extract Fully-Connected layers form an
features while respecting 2D image structure MLP at the end to predict scores
Illustration of LeCunet al. 1998 from CS231n 2017 Lecture 1 |
| Stanford CS231n 10th Anniversary Lecture 5 - 31 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 32
---


Next: Convolutional Neural Networks
Trained end-to-end with backprop + gradient descent
Illustration of LeCunet al. 1998 from CS231n 2017 Lecture 1
Stanford CS231n 10th Anniversary Lecture 5 - 32 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Next: Convolutional Neural Networks
Trained end-to-end with backprop + gradient descent
Illustration of LeCunet al. 1998 from CS231n 2017 Lecture 1 |
| Stanford CS231n 10th Anniversary Lecture 5 - 32 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 33
---


A bit of history:
Gradient-based learning applied to
document recognition
[LeCun, Bottou, Bengio, Haffner 1998]
Stanford CS231n 10th Anniversary Lecture 5 - 33 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| A bit of history:
Gradient-based learning applied to
document recognition
[LeCun, Bottou, Bengio, Haffner 1998] |
| Stanford CS231n 10th Anniversary Lecture 5 - 33 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 34
---


A bit of history:
ImageNet Classification with Deep
Convolutional Neural Networks
[Krizhevsky, Sutskever, Hinton, 2012]
Figure copyright Alex Krizhevsky, Ilya Sutskever, and Geoffrey Hinton, 2012. Reproduced with permission.
“AlexNet”
Stanford CS231n 10th Anniversary Lecture 5 - 34 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| A bit of history:
ImageNet Classification with Deep
Convolutional Neural Networks
[Krizhevsky, Sutskever, Hinton, 2012]
Figure copyright Alex Krizhevsky, Ilya Sutskever, and Geoffrey Hinton, 2012. Reproduced with permission.
“AlexNet” |
| Stanford CS231n 10th Anniversary Lecture 5 - 34 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 35
---


~2012 – 2020: ConvNets dominate all vision tasks
Detection Detection
Figures copyright ShaoqingRen, KaimingHe, Ross Girschick, Jian Sun, 2015. Reproduced with permission. Figures copyright Clement Farabet, 2012. Reproduced with permission. [Farabetet al., 2012]
[Faster R-CNN: Ren, He, Girshick, Sun 2015]
Stanford CS231n 10th Anniversary Lecture 5 - 35 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| ~2012 – 2020: ConvNets dominate all vision tasks
Detection Detection
Figures copyright ShaoqingRen, KaimingHe, Ross Girschick, Jian Sun, 2015. Reproduced with permission. Figures copyright Clement Farabet, 2012. Reproduced with permission. [Farabetet al., 2012]
[Faster R-CNN: Ren, He, Girshick, Sun 2015] |
| Stanford CS231n 10th Anniversary Lecture 5 - 35 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 36
---


~2012 – 2020: ConvNets dominate all vision tasks
Image Captioning
A white teddy bear sitting in A man in a baseball A woman is holding a cat
the grass uniform throwing a ball in her hand
All images are CC0 Public domain:
https://pixabay.com/en/luggage-antique-cat-1643010/
https://pixabay.com/en/teddy-plush-bears-cute-teddy-bear-1623436/
https://pixabay.com/en/surf-wave-summer-sport-litoral-1668716/
https://pixabay.com/en/woman-female-model-portrait-adult-983967/
https://pixabay.com/en/handstand-lake-meditation-496008/
https://pixabay.com/en/baseball-player-shortstop-infield-1045263/
Captions generated by Justin Johnson using Neuraltalk2
[Vinyalset al., 2015]
A man riding a wave on top A cat sitting on a suitcase A woman standing on a beach
of a surfboard on the floor holding a surfboard [Karpathyand Fei-Fei, 2015]
Stanford CS231n 10th Anniversary Lecture 5 - 36 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| ~2012 – 2020: ConvNets dominate all vision tasks
Image Captioning
A white teddy bear sitting in A man in a baseball A woman is holding a cat
the grass uniform throwing a ball in her hand
All images are CC0 Public domain:
https://pixabay.com/en/luggage-antique-cat-1643010/
https://pixabay.com/en/teddy-plush-bears-cute-teddy-bear-1623436/
https://pixabay.com/en/surf-wave-summer-sport-litoral-1668716/
https://pixabay.com/en/woman-female-model-portrait-adult-983967/
https://pixabay.com/en/handstand-lake-meditation-496008/
https://pixabay.com/en/baseball-player-shortstop-infield-1045263/
Captions generated by Justin Johnson using Neuraltalk2
[Vinyalset al., 2015]
A man riding a wave on top A cat sitting on a suitcase A woman standing on a beach
of a surfboard on the floor holding a surfboard [Karpathyand Fei-Fei, 2015] |
| Stanford CS231n 10th Anniversary Lecture 5 - 36 April 15, 2025 |


[Page contains 6 image(s)]


---
## Page 37
---


~2012 – 2020: ConvNets dominate all vision tasks
Text-to-Image Generation Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
A watercolor A shirt with the
An image of a half A painting of a
A zombie in the painting of a chair inscription: “I love
mouse half squirrel eating a
style of Picasso that looks like an generative
octopus burger
octopus models!”
Stanford CS231n 10th Anniversary Lecture 5 - 37 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| ~2012 – 2020: ConvNets dominate all vision tasks
Text-to-Image Generation Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
A watercolor A shirt with the
An image of a half A painting of a
A zombie in the painting of a chair inscription: “I love
mouse half squirrel eating a
style of Picasso that looks like an generative
octopus burger
octopus models!” |
| Stanford CS231n 10th Anniversary Lecture 5 - 37 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 38
---


~2012 – 2020: ConvNets dominate all vision tasks
This class used to be focused on ConvNets!
Stanford CS231n 10th Anniversary Lecture 5 - 38 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| ~2012 – 2020: ConvNets dominate all vision tasks
This class used to be focused on ConvNets! |
| Stanford CS231n 10th Anniversary Lecture 5 - 38 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 39
---


2021 - Present: Transformers have taken over
2017: Transformers
for language tasks
Vaswani et al, “Attention is
all you need”, NeurIPS2017
Stanford CS231n 10th Anniversary Lecture 5 - 39 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| 2021 - Present: Transformers have taken over
2017: Transformers
for language tasks
Vaswani et al, “Attention is
all you need”, NeurIPS2017 |
| Stanford CS231n 10th Anniversary Lecture 5 - 39 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 40
---


2021 - Present: Transformers have taken over
2017: Transformers 2021: Transformers
for language tasks for vision tasks
Dosovitskiyet al, “An Image is Worth
Vaswani et al, “Attention is
16x16 Words: Transformers for Image
all you need”, NeurIPS2017
Recognition at Scale”, ICLR 2021
Stanford CS231n 10th Anniversary Lecture 5 - 40 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| 2021 - Present: Transformers have taken over
2017: Transformers 2021: Transformers
for language tasks for vision tasks
Dosovitskiyet al, “An Image is Worth
Vaswani et al, “Attention is
16x16 Words: Transformers for Image
all you need”, NeurIPS2017
Recognition at Scale”, ICLR 2021 |
| Stanford CS231n 10th Anniversary Lecture 5 - 40 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 41
---


2021 - Present: Transformers have taken over
2017: Transformers 2021: Transformers Wait until
for language tasks for vision tasks Lecture 8!
Dosovitskiyet al, “An Image is Worth
Vaswani et al, “Attention is
16x16 Words: Transformers for Image
all you need”, NeurIPS2017
Recognition at Scale”, ICLR 2021
Stanford CS231n 10th Anniversary Lecture 5 - 41 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| 2021 - Present: Transformers have taken over
2017: Transformers 2021: Transformers Wait until
for language tasks for vision tasks Lecture 8!
Dosovitskiyet al, “An Image is Worth
Vaswani et al, “Attention is
16x16 Words: Transformers for Image
all you need”, NeurIPS2017
Recognition at Scale”, ICLR 2021 |
| Stanford CS231n 10th Anniversary Lecture 5 - 41 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 42
---


Convolutional Neural Networks
Stanford CS231n 10th Anniversary Lecture 5 - 42 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Convolutional Neural Networks |
| Stanford CS231n 10th Anniversary Lecture 5 - 42 April 15, 2025 |


---
## Page 43
---


Today: Convolutional Networks
Fully-Connected Layer Activation Function
We have
already x h s
seen these
Stanford CS231n 10th Anniversary Lecture 5 - 43 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Today: Convolutional Networks
Fully-Connected Layer Activation Function
We have
already x h s
seen these |
| Stanford CS231n 10th Anniversary Lecture 5 - 43 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 44
---


Today: Convolutional Networks
Fully-Connected Layer Activation Function
We have
already x h s
seen these
Convolution Layer Pooling Layer
Today: Image-
specific
operators
Stanford CS231n 10th Anniversary Lecture 5 - 44 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Today: Convolutional Networks
Fully-Connected Layer Activation Function
We have
already x h s
seen these
Convolution Layer Pooling Layer
Today: Image-
specific
operators |
| Stanford CS231n 10th Anniversary Lecture 5 - 44 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 45
---


Today: Convolutional Networks
Fully-Connected Layer Activation Function
We have
already x h s
seen these
Convolution Layer Pooling Layer
Today: Image-
specific
operators
Stanford CS231n 10th Anniversary Lecture 5 - 45 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Today: Convolutional Networks
Fully-Connected Layer Activation Function
We have
already x h s
seen these
Convolution Layer Pooling Layer
Today: Image-
specific
operators |
| Stanford CS231n 10th Anniversary Lecture 5 - 45 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 46
---


Recap: Fully Connected Layer
32x32x3 image -> stretch to 3072 x 1
input activation
1 1
10 x 3072
3072 10
weights
Stanford CS231n 10th Anniversary Lecture 5 - 46 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Recap: Fully Connected Layer
32x32x3 image -> stretch to 3072 x 1
input activation
1 1
10 x 3072
3072 10
weights |
| Stanford CS231n 10th Anniversary Lecture 5 - 46 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 47
---


Fully Connected Layer
32x32x3 image -> stretch to 3072 x 1
input activation
1 1
10 x 3072
3072 10
weights
1 number:
the result of taking a dot product
between a row of W and the input (a
3072-dimensional dot product)
Stanford CS231n 10th Anniversary Lecture 5 - 47 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Fully Connected Layer
32x32x3 image -> stretch to 3072 x 1
input activation
1 1
10 x 3072
3072 10
weights
1 number:
the result of taking a dot product
between a row of W and the input (a
3072-dimensional dot product) |
| Stanford CS231n 10th Anniversary Lecture 5 - 47 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 48
---


Convolution Layer
32x32x3 image -> preserve spatial structure
height
32
width
32
depth
3
Stanford CS231n 10th Anniversary Lecture 5 - 48 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Convolution Layer
32x32x3 image -> preserve spatial structure
height
32
width
32
depth
3 |
| Stanford CS231n 10th Anniversary Lecture 5 - 48 April 15, 2025 |


---
## Page 49
---


Convolution Layer
32x32x3 image
5x5x3 filter
32
Convolve the filter with the image
i.e. “slide over the image spatially,
computing dot products”
32
3
Stanford CS231n 10th Anniversary Lecture 5 - 49 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Convolution Layer
32x32x3 image
5x5x3 filter
32
Convolve the filter with the image
i.e. “slide over the image spatially,
computing dot products”
32
3 |
| Stanford CS231n 10th Anniversary Lecture 5 - 49 April 15, 2025 |


---
## Page 50
---


Convolution Layer
Filters always extend the full
depth of the input volume
32x32x3 image
5x5x3 filter
32
Convolve the filter with the image
i.e. “slide over the image spatially,
computing dot products”
32
3
Stanford CS231n 10th Anniversary Lecture 5 - 50 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Convolution Layer
Filters always extend the full
depth of the input volume
32x32x3 image
5x5x3 filter
32
Convolve the filter with the image
i.e. “slide over the image spatially,
computing dot products”
32
3 |
| Stanford CS231n 10th Anniversary Lecture 5 - 50 April 15, 2025 |


---
## Page 51
---


Convolution Layer
32x32x3 image
5x5x3 filter
32
1 number:
the result of taking a dot product between the
filter and a small 5x5x3 chunk of the image
32
(i.e. 5*5*3 = 75-dimensional dot product + bias)
3
Stanford CS231n 10th Anniversary Lecture 5 - 51 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Convolution Layer
32x32x3 image
5x5x3 filter
32
1 number:
the result of taking a dot product between the
filter and a small 5x5x3 chunk of the image
32
(i.e. 5*5*3 = 75-dimensional dot product + bias)
3 |
| Stanford CS231n 10th Anniversary Lecture 5 - 51 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 52
---


Convolution Layer
32
32
3
Stanford CS231n 10th Anniversary Lecture 5 - 52 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Convolution Layer
32
32
3 |
| Stanford CS231n 10th Anniversary Lecture 5 - 52 April 15, 2025 |


---
## Page 53
---


Convolution Layer
32
32
3
Stanford CS231n 10th Anniversary Lecture 5 - 53 April 15, 2025

[Page contains 2 table(s)]


### Table 1

| Convolution Layer
32
32
3 |
| Stanford CS231n 10th Anniversary Lecture 5 - 53 April 15, 2025 |


### Table 2

|  |
|  |


---
## Page 54
---


Convolution Layer
32
32
3
Stanford CS231n 10th Anniversary Lecture 5 - 54 April 15, 2025

[Page contains 2 table(s)]


### Table 1

| Convolution Layer
32
32
3 |
| Stanford CS231n 10th Anniversary Lecture 5 - 54 April 15, 2025 |


### Table 2

|  |
|  |


---
## Page 55
---


Convolution Layer
32
32
3
Stanford CS231n 10th Anniversary Lecture 5 - 55 April 15, 2025

[Page contains 3 table(s)]


### Table 1

| Convolution Layer
32
32
3 |
| Stanford CS231n 10th Anniversary Lecture 5 - 55 April 15, 2025 |


### Table 2

|  |
|  |


### Table 3

|  |
|  |
|  |
|  |


---
## Page 56
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
Stanford CS231n 10th Anniversary Lecture 5 - 56 April 15, 2025

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
| Stanford CS231n 10th Anniversary Lecture 5 - 56 April 15, 2025 |


---
## Page 57
---


consider a second, green filter
Convolution Layer
32x32x3 image activation maps
5x5x3 filter
32
28
convolve (slide) over all spatial
locations
28
32
3 1
Stanford CS231n 10th Anniversary Lecture 5 - 57 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| consider a second, green filter
Convolution Layer
32x32x3 image activation maps
5x5x3 filter
32
28
convolve (slide) over all spatial
locations
28
32
3 1 |
| Stanford CS231n 10th Anniversary Lecture 5 - 57 April 15, 2025 |


---
## Page 58
---


Convolution Layer
6 activation maps,
each 1x28x28
3x32x32 image
Consider 6 filters,
each 3x5x5
Convolution
Layer
32
6x3x5x5
32
Stack activations to get a
filters
3
6x28x28 output image!
Slide inspiration: Justin Johnson
Stanford CS231n 10th Anniversary Lecture 5 - 58 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Convolution Layer
6 activation maps,
each 1x28x28
3x32x32 image
Consider 6 filters,
each 3x5x5
Convolution
Layer
32
6x3x5x5
32
Stack activations to get a
filters
3
6x28x28 output image!
Slide inspiration: Justin Johnson |
| Stanford CS231n 10th Anniversary Lecture 5 - 58 April 15, 2025 |


---
## Page 59
---


Convolution Layer
6 activation maps,
each 1x28x28
3x32x32 image Also 6-dim bias vector:
Convolution
Layer
32
6x3x5x5
32
Stack activations to get a
filters
3
6x28x28 output image!
Slide inspiration: Justin Johnson
Stanford CS231n 10th Anniversary Lecture 5 - 59 April 15, 2025

[Page contains 2 table(s)]


### Table 1

| Convolution Layer
6 activation maps,
each 1x28x28
3x32x32 image Also 6-dim bias vector:
Convolution
Layer
32
6x3x5x5
32
Stack activations to get a
filters
3
6x28x28 output image!
Slide inspiration: Justin Johnson |
| Stanford CS231n 10th Anniversary Lecture 5 - 59 April 15, 2025 |


### Table 2

|  |  |  |  |  |  |


---
## Page 60
---


Convolution Layer
28x28 grid, at each
point a 6-dim vector
3x32x32 image Also 6-dim bias vector:
Convolution
Layer
32
6x3x5x5
32
Stack activations to get a
filters
3
6x28x28 output image!
Slide inspiration: Justin Johnson
Stanford CS231n 10th Anniversary Lecture 5 - 60 April 15, 2025

[Page contains 2 table(s)]


### Table 1

| Convolution Layer
28x28 grid, at each
point a 6-dim vector
3x32x32 image Also 6-dim bias vector:
Convolution
Layer
32
6x3x5x5
32
Stack activations to get a
filters
3
6x28x28 output image!
Slide inspiration: Justin Johnson |
| Stanford CS231n 10th Anniversary Lecture 5 - 60 April 15, 2025 |


### Table 2

|  |  |  |  |  |  |


---
## Page 61
---


Convolution Layer
2x6x28x28
Batch of outputs
2x3x32x32
Also 6-dim bias vector:
Batch of images
Convolution
Layer
32
6x3x5x5
32
filters
3
Slide inspiration: Justin Johnson
Stanford CS231n 10th Anniversary Lecture 5 - 61 April 15, 2025

[Page contains 2 table(s)]


### Table 1

| Convolution Layer
2x6x28x28
Batch of outputs
2x3x32x32
Also 6-dim bias vector:
Batch of images
Convolution
Layer
32
6x3x5x5
32
filters
3
Slide inspiration: Justin Johnson |
| Stanford CS231n 10th Anniversary Lecture 5 - 61 April 15, 2025 |


### Table 2

|  |  |  |  |  |  |


---
## Page 62
---


Convolution Layer
N x C x H’ x W’
out
Batch of outputs
N x C x H x W
in
Also C -dim bias vector:
Batch of images
out
Convolution
Layer
H
W
C x C x K x K
out in w h
C
filters out
C
in
Slide inspiration: Justin Johnson
Stanford CS231n 10th Anniversary Lecture 5 - 62 April 15, 2025

[Page contains 2 table(s)]


### Table 1

| Convolution Layer
N x C x H’ x W’
out
Batch of outputs
N x C x H x W
in
Also C -dim bias vector:
Batch of images
out
Convolution
Layer
H
W
C x C x K x K
out in w h
C
filters out
C
in
Slide inspiration: Justin Johnson |
| Stanford CS231n 10th Anniversary Lecture 5 - 62 April 15, 2025 |


### Table 2

|  |  |  |  |  |  |


---
## Page 63
---


A ConvNet is a neural network with Conv layers
32 28
CONV
e.g. 6
5x5x3
32 28
filters
3 6
Stanford CS231n 10th Anniversary Lecture 5 - 63 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| A ConvNet is a neural network with Conv layers
32 28
CONV
e.g. 6
5x5x3
32 28
filters
3 6 |
| Stanford CS231n 10th Anniversary Lecture 5 - 63 April 15, 2025 |


---
## Page 64
---


A ConvNet is a neural network with Conv layers
32 28
24
….
CONV
CONV CONV
e.g. 6
e.g. 10
5x5x3
5x5x6
32 28
filters 24
filters
3 6
10
Stanford CS231n 10th Anniversary Lecture 5 - 64 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| A ConvNet is a neural network with Conv layers
32 28
24
….
CONV
CONV CONV
e.g. 6
e.g. 10
5x5x3
5x5x6
32 28
filters 24
filters
3 6
10 |
| Stanford CS231n 10th Anniversary Lecture 5 - 64 April 15, 2025 |


---
## Page 65
---


A ConvNet is a neural network with Conv layers
with activation functions!
32 28
24
….
CONV
CONV CONV
ReLU
ReLU ReLU
e.g. 6
e.g. 10
5x5x3
5x5x6
32 28
filters 24
filters
3 6
10
Stanford CS231n 10th Anniversary Lecture 5 - 65 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| A ConvNet is a neural network with Conv layers
with activation functions!
32 28
24
….
CONV
CONV CONV
ReLU
ReLU ReLU
e.g. 6
e.g. 10
5x5x3
5x5x6
32 28
filters 24
filters
3 6
10 |
| Stanford CS231n 10th Anniversary Lecture 5 - 65 April 15, 2025 |


---
## Page 66
---


What do Conv filters learn?
28
32
Linear classifier: One template per class
Conv ReLU
28
32
3
Stanford CS231n 10th Anniversary Lecture 5 - 66 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| What do Conv filters learn?
28
32
Linear classifier: One template per class
Conv ReLU
28
32
3 |
| Stanford CS231n 10th Anniversary Lecture 5 - 66 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 67
---


What do Conv filters learn?
MLP: Bank of whole-image templates
28
32
Conv ReLU
28
32
3
Stanford CS231n 10th Anniversary Lecture 5 - 67 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| What do Conv filters learn?
MLP: Bank of whole-image templates
28
32
Conv ReLU
28
32
3 |
| Stanford CS231n 10th Anniversary Lecture 5 - 67 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 68
---


What do Conv filters learn?
First-layer conv filters: local image templates
(Often learns oriented edges, opposing colors)
28
32
Conv ReLU
28
32
3
AlexNet: 64 filters, each 3x11x11
Stanford CS231n 10th Anniversary Lecture 5 - 68 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| What do Conv filters learn?
First-layer conv filters: local image templates
(Often learns oriented edges, opposing colors)
28
32
Conv ReLU
28
32
3
AlexNet: 64 filters, each 3x11x11 |
| Stanford CS231n 10th Anniversary Lecture 5 - 68 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 69
---


What do Conv filters learn?
Deeper conv layers: Harder to visualize
Tend to learn larger structures e.g. eyes, letters
32
Conv ReLU
28
32
3
6th layer conv layer from an ImageNet model
Visualization from [Springenberg et al, ICLR 2015]
Stanford CS231n 10th Anniversary Lecture 5 - 69 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| What do Conv filters learn?
Deeper conv layers: Harder to visualize
Tend to learn larger structures e.g. eyes, letters
32
Conv ReLU
28
32
3
6th layer conv layer from an ImageNet model
Visualization from [Springenberg et al, ICLR 2015] |
| Stanford CS231n 10th Anniversary Lecture 5 - 69 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 70
---


Convolution: Spatial Dimensions
32
Conv ReLU
W : 6x3x5x5
1
28
b : 6
32
1
3
Stanford CS231n 10th Anniversary Lecture 5 - 70 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Convolution: Spatial Dimensions
32
Conv ReLU
W : 6x3x5x5
1
28
b : 6
32
1
3 |
| Stanford CS231n 10th Anniversary Lecture 5 - 70 April 15, 2025 |


---
## Page 71
---


Convolution: Spatial Dimensions
Input: 7x7
Filter: 3x3
7
7
Stanford CS231n 10th Anniversary Lecture 5 - 71 April 15, 2025

[Page contains 2 table(s)]


### Table 1

| Convolution: Spatial Dimensions
Input: 7x7
Filter: 3x3
7
7 |
| Stanford CS231n 10th Anniversary Lecture 5 - 71 April 15, 2025 |


### Table 2

|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |


---
## Page 72
---


Convolution: Spatial Dimensions
Input: 7x7
Filter: 3x3
7
7
Stanford CS231n 10th Anniversary Lecture 5 - 72 April 15, 2025

[Page contains 2 table(s)]


### Table 1

| Convolution: Spatial Dimensions
Input: 7x7
Filter: 3x3
7
7 |
| Stanford CS231n 10th Anniversary Lecture 5 - 72 April 15, 2025 |


### Table 2

|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |


---
## Page 73
---


Convolution: Spatial Dimensions
Input: 7x7
Filter: 3x3
7
7
Stanford CS231n 10th Anniversary Lecture 5 - 73 April 15, 2025

[Page contains 2 table(s)]


### Table 1

| Convolution: Spatial Dimensions
Input: 7x7
Filter: 3x3
7
7 |
| Stanford CS231n 10th Anniversary Lecture 5 - 73 April 15, 2025 |


### Table 2

|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |


---
## Page 74
---


Convolution: Spatial Dimensions
Input: 7x7
Filter: 3x3
7
7
Stanford CS231n 10th Anniversary Lecture 5 - 74 April 15, 2025

[Page contains 2 table(s)]


### Table 1

| Convolution: Spatial Dimensions
Input: 7x7
Filter: 3x3
7
7 |
| Stanford CS231n 10th Anniversary Lecture 5 - 74 April 15, 2025 |


### Table 2

|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |


---
## Page 75
---


Convolution: Spatial Dimensions
Input: 7x7
Filter: 3x3
Output: 5x5
7
7
Stanford CS231n 10th Anniversary Lecture 5 - 75 April 15, 2025

[Page contains 2 table(s)]


### Table 1

| Convolution: Spatial Dimensions
Input: 7x7
Filter: 3x3
Output: 5x5
7
7 |
| Stanford CS231n 10th Anniversary Lecture 5 - 75 April 15, 2025 |


### Table 2

|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |


---
## Page 76
---


Convolution: Spatial Dimensions
Input: 7x7
Filter: 3x3
Output: 5x5
7
In general
Input: W
Filter: K
Output: W – K + 1
7
Stanford CS231n 10th Anniversary Lecture 5 - 76 April 15, 2025

[Page contains 2 table(s)]


### Table 1

| Convolution: Spatial Dimensions
Input: 7x7
Filter: 3x3
Output: 5x5
7
In general
Input: W
Filter: K
Output: W – K + 1
7 |
| Stanford CS231n 10th Anniversary Lecture 5 - 76 April 15, 2025 |


### Table 2

|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |


---
## Page 77
---


Convolution: Spatial Dimensions
Input: 7x7 Problem: Feature
Filter: 3x3 maps shrink with
Output: 5x5 each layer!
7
In general
Input: W
Filter: K
Output: W – K + 1
7
Stanford CS231n 10th Anniversary Lecture 5 - 77 April 15, 2025

[Page contains 2 table(s)]


### Table 1

| Convolution: Spatial Dimensions
Input: 7x7 Problem: Feature
Filter: 3x3 maps shrink with
Output: 5x5 each layer!
7
In general
Input: W
Filter: K
Output: W – K + 1
7 |
| Stanford CS231n 10th Anniversary Lecture 5 - 77 April 15, 2025 |


### Table 2

|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |


---
## Page 78
---


Convolution: Spatial Dimensions
0 0 0 0 0 0 0 0 0
Input: 7x7 Problem: Feature
0 0 Filter: 3x3 maps shrink with
0 0 Output: 5x5 each layer!
0 0
Solution: Add
0 0
In general padding around
0 0
Input: W the input before
0 0
Filter: K sliding the filter
0 0
Padding: P
0 0 0 0 0 0 0 0 0 Output: W – K + 1 + 2P
Stanford CS231n 10th Anniversary Lecture 5 - 78 April 15, 2025

[Page contains 2 table(s)]


### Table 1

| Convolution: Spatial Dimensions
0 0 0 0 0 0 0 0 0
Input: 7x7 Problem: Feature
0 0 Filter: 3x3 maps shrink with
0 0 Output: 5x5 each layer!
0 0
Solution: Add
0 0
In general padding around
0 0
Input: W the input before
0 0
Filter: K sliding the filter
0 0
Padding: P
0 0 0 0 0 0 0 0 0 Output: W – K + 1 + 2P |
| Stanford CS231n 10th Anniversary Lecture 5 - 78 April 15, 2025 |


### Table 2

| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 |  |  |  |  |  |  |  | 0 |
| 0 |  |  |  |  |  |  |  | 0 |
| 0 |  |  |  |  |  |  |  | 0 |
| 0 |  |  |  |  |  |  |  | 0 |
| 0 |  |  |  |  |  |  |  | 0 |
| 0 |  |  |  |  |  |  |  | 0 |
| 0 |  |  |  |  |  |  |  | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |


---
## Page 79
---


Convolution: Spatial Dimensions
0 0 0 0 0 0 0 0 0
Input: 7x7
0 0 Filter: 3x3
0 0 Output: 5x5
0 0
Common setting:
0 0
In general P = (K – 1) / 2
0 0
Input: W Means output has
0 0
Filter: K same size as input
0 0
Padding: P
0 0 0 0 0 0 0 0 0 Output: W – K + 1 + 2P
Stanford CS231n 10th Anniversary Lecture 5 - 79 April 15, 2025

[Page contains 2 table(s)]


### Table 1

| Convolution: Spatial Dimensions
0 0 0 0 0 0 0 0 0
Input: 7x7
0 0 Filter: 3x3
0 0 Output: 5x5
0 0
Common setting:
0 0
In general P = (K – 1) / 2
0 0
Input: W Means output has
0 0
Filter: K same size as input
0 0
Padding: P
0 0 0 0 0 0 0 0 0 Output: W – K + 1 + 2P |
| Stanford CS231n 10th Anniversary Lecture 5 - 79 April 15, 2025 |


### Table 2

| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 |  |  |  |  |  |  |  | 0 |
| 0 |  |  |  |  |  |  |  | 0 |
| 0 |  |  |  |  |  |  |  | 0 |
| 0 |  |  |  |  |  |  |  | 0 |
| 0 |  |  |  |  |  |  |  | 0 |
| 0 |  |  |  |  |  |  |  | 0 |
| 0 |  |  |  |  |  |  |  | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |


---
## Page 80
---


Receptive Fields
For convolution with kernel size K, each element in the
output depends on a K x K receptive field in the input
Input Output
Slide inspiration: Justin Johnson
Stanford CS231n 10th Anniversary Lecture 5 - 80 April 15, 2025

[Page contains 3 table(s)]


### Table 1

| Receptive Fields
For convolution with kernel size K, each element in the
output depends on a K x K receptive field in the input
Input Output
Slide inspiration: Justin Johnson |
| Stanford CS231n 10th Anniversary Lecture 5 - 80 April 15, 2025 |


### Table 2

|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |


### Table 3

|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |


---
## Page 81
---


Receptive Fields
Each successive convolution adds K – 1 to the receptive field size
With L layers the receptive field size is 1 + L * (K – 1)
Input Output
Be careful – “receptive field in the input” vs. “receptive field in the previous layer”
Slide inspiration: Justin Johnson
Stanford CS231n 10th Anniversary Lecture 5 - 81 April 15, 2025

[Page contains 5 table(s)]


### Table 1

| Receptive Fields
Each successive convolution adds K – 1 to the receptive field size
With L layers the receptive field size is 1 + L * (K – 1)
Input Output
Be careful – “receptive field in the input” vs. “receptive field in the previous layer”
Slide inspiration: Justin Johnson |
| Stanford CS231n 10th Anniversary Lecture 5 - 81 April 15, 2025 |


### Table 2

|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |


### Table 3

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


### Table 5

|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |


---
## Page 82
---


Receptive Fields
Each successive convolution adds K – 1 to the receptive field size
With L layers the receptive field size is 1 + L * (K – 1)
Input Output
Problem: For large images we need many layers for
each output to “see” the whole image image
Slide inspiration: Justin Johnson
Stanford CS231n 10th Anniversary Lecture 5 - 82 April 15, 2025

[Page contains 5 table(s)]


### Table 1

| Receptive Fields
Each successive convolution adds K – 1 to the receptive field size
With L layers the receptive field size is 1 + L * (K – 1)
Input Output
Problem: For large images we need many layers for
each output to “see” the whole image image
Slide inspiration: Justin Johnson |
| Stanford CS231n 10th Anniversary Lecture 5 - 82 April 15, 2025 |


### Table 2

|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |


### Table 3

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


### Table 5

|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |


---
## Page 83
---


Receptive Fields
Each successive convolution adds K – 1 to the receptive field size
With L layers the receptive field size is 1 + L * (K – 1)
Input Output
Problem: For large images we need many layers for
each output to “see” the whole image image
Solution: Downsample inside the network
Slide inspiration: Justin Johnson
Stanford CS231n 10th Anniversary Lecture 5 - 83 April 15, 2025

[Page contains 5 table(s)]


### Table 1

| Receptive Fields
Each successive convolution adds K – 1 to the receptive field size
With L layers the receptive field size is 1 + L * (K – 1)
Input Output
Problem: For large images we need many layers for
each output to “see” the whole image image
Solution: Downsample inside the network
Slide inspiration: Justin Johnson |
| Stanford CS231n 10th Anniversary Lecture 5 - 83 April 15, 2025 |


### Table 2

|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |


### Table 3

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


### Table 5

|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |


---
## Page 84
---


Strided Convolution
7
Input: 7x7
Filter: 3x3
Stride: 2
7
Stanford CS231n 10th Anniversary Lecture 5 - 84 April 15, 2025

[Page contains 2 table(s)]


### Table 1

| Strided Convolution
7
Input: 7x7
Filter: 3x3
Stride: 2
7 |
| Stanford CS231n 10th Anniversary Lecture 5 - 84 April 15, 2025 |


### Table 2

|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |


---
## Page 85
---


Strided Convolution
7
Input: 7x7
Filter: 3x3
Stride: 2
7
Stanford CS231n 10th Anniversary Lecture 5 - 85 April 15, 2025

[Page contains 2 table(s)]


### Table 1

| Strided Convolution
7
Input: 7x7
Filter: 3x3
Stride: 2
7 |
| Stanford CS231n 10th Anniversary Lecture 5 - 85 April 15, 2025 |


### Table 2

|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |


---
## Page 86
---


Strided Convolution
7
Input: 7x7
Filter: 3x3
Stride: 2
Output: 3x3
7
Stanford CS231n 10th Anniversary Lecture 5 - 86 April 15, 2025

[Page contains 2 table(s)]


### Table 1

| Strided Convolution
7
Input: 7x7
Filter: 3x3
Stride: 2
Output: 3x3
7 |
| Stanford CS231n 10th Anniversary Lecture 5 - 86 April 15, 2025 |


### Table 2

|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |


---
## Page 87
---


Strided Convolution
7
Input: 7x7
Filter: 3x3
Stride: 2
Output: 3x3
In general:
7
Input: W
Output:
Filter: K
(W – K + 2P) / S + 1
Padding: P
Stride: S
Stanford CS231n 10th Anniversary Lecture 5 - 87 April 15, 2025

[Page contains 2 table(s)]


### Table 1

| Strided Convolution
7
Input: 7x7
Filter: 3x3
Stride: 2
Output: 3x3
In general:
7
Input: W
Output:
Filter: K
(W – K + 2P) / S + 1
Padding: P
Stride: S |
| Stanford CS231n 10th Anniversary Lecture 5 - 87 April 15, 2025 |


### Table 2

|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |


---
## Page 88
---


Convolution Example
Input volume: 3 x 32 x 32
10 5x5 filters with stride 1, pad 2
Output volume size: ?
Stanford CS231n 10th Anniversary Lecture 5 - 88 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Convolution Example
Input volume: 3 x 32 x 32
10 5x5 filters with stride 1, pad 2
Output volume size: ? |
| Stanford CS231n 10th Anniversary Lecture 5 - 88 April 15, 2025 |


---
## Page 89
---


Convolution Example
Input volume: 3 x 32 x 32
10 5x5 filters with stride 1, pad 2
Output volume size: 10 x 32 x 32
32 = (32+2*2-5)/1+1
Stanford CS231n 10th Anniversary Lecture 5 - 89 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Convolution Example
Input volume: 3 x 32 x 32
10 5x5 filters with stride 1, pad 2
Output volume size: 10 x 32 x 32
32 = (32+2*2-5)/1+1 |
| Stanford CS231n 10th Anniversary Lecture 5 - 89 April 15, 2025 |


---
## Page 90
---


Convolution Example
Input volume: 3 x 32 x 32
10 5x5 filters with stride 1, pad 2
Output volume size: 10 x 32 x 32
Number of learnable parameters: ?
Stanford CS231n 10th Anniversary Lecture 5 - 90 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Convolution Example
Input volume: 3 x 32 x 32
10 5x5 filters with stride 1, pad 2
Output volume size: 10 x 32 x 32
Number of learnable parameters: ? |
| Stanford CS231n 10th Anniversary Lecture 5 - 90 April 15, 2025 |


---
## Page 91
---


Convolution Example
Input volume: 3 x 32 x 32
10 5x5 filters with stride 1, pad 2
Output volume size: 10 x 32 x 32
Number of learnable parameters: 760
Parameters per filter: 3*5*5 + 1 (for bias) = 76
10 filters, so total is 10 * 76 = 760
Stanford CS231n 10th Anniversary Lecture 5 - 91 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Convolution Example
Input volume: 3 x 32 x 32
10 5x5 filters with stride 1, pad 2
Output volume size: 10 x 32 x 32
Number of learnable parameters: 760
Parameters per filter: 3*5*5 + 1 (for bias) = 76
10 filters, so total is 10 * 76 = 760 |
| Stanford CS231n 10th Anniversary Lecture 5 - 91 April 15, 2025 |


---
## Page 92
---


Convolution Example
Input volume: 3 x 32 x 32
10 5x5 filters with stride 1, pad 2
Output volume size: 10 x 32 x 32
Number of learnable parameters: 760
Number of multiply-add operations?
Stanford CS231n 10th Anniversary Lecture 5 - 92 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Convolution Example
Input volume: 3 x 32 x 32
10 5x5 filters with stride 1, pad 2
Output volume size: 10 x 32 x 32
Number of learnable parameters: 760
Number of multiply-add operations? |
| Stanford CS231n 10th Anniversary Lecture 5 - 92 April 15, 2025 |


---
## Page 93
---


Convolution Example
Input volume: 3 x 32 x 32
10 5x5 filters with stride 1, pad 2
Output volume size: 10 x 32 x 32
Number of learnable parameters: 760
Number of multiply-add operations: 768,000
10*32*32 = 10,240 outputs
Each output is the inner product of two 3x5x5 tensors (75 elems)
Total = 75*10240 = 768K
Stanford CS231n 10th Anniversary Lecture 5 - 93 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Convolution Example
Input volume: 3 x 32 x 32
10 5x5 filters with stride 1, pad 2
Output volume size: 10 x 32 x 32
Number of learnable parameters: 760
Number of multiply-add operations: 768,000
10*32*32 = 10,240 outputs
Each output is the inner product of two 3x5x5 tensors (75 elems)
Total = 75*10240 = 768K |
| Stanford CS231n 10th Anniversary Lecture 5 - 93 April 15, 2025 |


---
## Page 94
---


Convolution Summary
Input: C x H x W
in
Hyperparameters:
Common settings:
- Kernel size: K x K
H W
K = K (Small square filters)
- Number filters: C H W
out
P = (K – 1) / 2 (”Same” padding)
- Padding: P
C , C = 32, 64, 128, 256 (powers of 2)
- Stride: S in out
K = 3, P = 1, S = 1 (3x3 conv)
Weight matrix: C x C x K x K
out in H W
K = 5, P = 2, S = 1 (5x5 conv)
giving C filters of size C x K x K
out in H W
K = 1, P = 0, S = 1 (1x1 conv)
Bias vector: C
out
K = 3, P = 1, S = 2 (Downsample by 2)
Output size: C x H’ x W’ where:
out
- H’ = (H – K + 2P) / S + 1
- W’ = (W – K + 2P) / S + 1
Stanford CS231n 10th Anniversary Lecture 5 - 94 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Convolution Summary
Input: C x H x W
in
Hyperparameters:
Common settings:
- Kernel size: K x K
H W
K = K (Small square filters)
- Number filters: C H W
out
P = (K – 1) / 2 (”Same” padding)
- Padding: P
C , C = 32, 64, 128, 256 (powers of 2)
- Stride: S in out
K = 3, P = 1, S = 1 (3x3 conv)
Weight matrix: C x C x K x K
out in H W
K = 5, P = 2, S = 1 (5x5 conv)
giving C filters of size C x K x K
out in H W
K = 1, P = 0, S = 1 (1x1 conv)
Bias vector: C
out
K = 3, P = 1, S = 2 (Downsample by 2)
Output size: C x H’ x W’ where:
out
- H’ = (H – K + 2P) / S + 1
- W’ = (W – K + 2P) / S + 1 |
| Stanford CS231n 10th Anniversary Lecture 5 - 94 April 15, 2025 |


---
## Page 95
---


PyTorch Convolution Layer
We didn’t talk about groups or dilation…
Stanford CS231n 10th Anniversary Lecture 5 - 95 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| PyTorch Convolution Layer
We didn’t talk about groups or dilation… |
| Stanford CS231n 10th Anniversary Lecture 5 - 95 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 96
---


Other Types of Convolution
So far: 2D Convolution
Input: C x H x W
in
Weights: C x C x K x K
out in
H
W
C
in
Stanford CS231n 10th Anniversary Lecture 5 - 96 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Other Types of Convolution
So far: 2D Convolution
Input: C x H x W
in
Weights: C x C x K x K
out in
H
W
C
in |
| Stanford CS231n 10th Anniversary Lecture 5 - 96 April 15, 2025 |


---
## Page 97
---


Other Types of Convolution
So far: 2D Convolution 1D Convolution
Input: C x H x W Input: C x W
in in
Weights: C x C x K x K Weights: C x C x K
out in out in
H C
in
W
W
C
in
Stanford CS231n 10th Anniversary Lecture 5 - 97 April 15, 2025

[Page contains 2 table(s)]


### Table 1

| Other Types of Convolution
So far: 2D Convolution 1D Convolution
Input: C x H x W Input: C x W
in in
Weights: C x C x K x K Weights: C x C x K
out in out in
H C
in
W
W
C
in |
| Stanford CS231n 10th Anniversary Lecture 5 - 97 April 15, 2025 |


### Table 2

|  |  |  |


---
## Page 98
---


Other Types of Convolution
So far: 2D Convolution 3D Convolution
Input: C x H x W Input: C x H x W x D
in in
Weights: C x C x K x K Weights: C x C x K x K x K
out in out in
H
H C -dim vector
in
at each point
in the volume
W D
C
W
in
Stanford CS231n 10th Anniversary Lecture 5 - 98 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Other Types of Convolution
So far: 2D Convolution 3D Convolution
Input: C x H x W Input: C x H x W x D
in in
Weights: C x C x K x K Weights: C x C x K x K x K
out in out in
H
H C -dim vector
in
at each point
in the volume
W D
C
W
in |
| Stanford CS231n 10th Anniversary Lecture 5 - 98 April 15, 2025 |


---
## Page 99
---


Convolutional Networks
Fully-Connected Layer Activation Function
We have
already x h s
seen these
Convolution Layer Pooling Layer
Today: Image-
specific
operators
Stanford CS231n 10th Anniversary Lecture 5 - 99 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Convolutional Networks
Fully-Connected Layer Activation Function
We have
already x h s
seen these
Convolution Layer Pooling Layer
Today: Image-
specific
operators |
| Stanford CS231n 10th Anniversary Lecture 5 - 99 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 100
---


Convolutional Networks
Fully-Connected Layer Activation Function
We have
already x h s
seen these
Convolution Layer Pooling Layer
Today: Image-
specific
operators
Stanford CS231n 10th Anniversary Lecture 5 - 100 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Convolutional Networks
Fully-Connected Layer Activation Function
We have
already x h s
seen these
Convolution Layer Pooling Layer
Today: Image-
specific
operators |
| Stanford CS231n 10th Anniversary Lecture 5 - 100 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 101
---


Pooling Layers: Another way to downsample
64 x 112 x 112
Given an input C x H x W,
64 x 224 x 224
downsample each 1 x H x W plane
Hyperparameters:
Kernel Size
Stride
Pooling function
Stanford CS231n 10th Anniversary Lecture 5 - 101 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Pooling Layers: Another way to downsample
64 x 112 x 112
Given an input C x H x W,
64 x 224 x 224
downsample each 1 x H x W plane
Hyperparameters:
Kernel Size
Stride
Pooling function |
| Stanford CS231n 10th Anniversary Lecture 5 - 101 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 102
---


Pooling Layers: Another way to downsample
64 x 224 x 224
Single depth slice
1 1 2 4
x
Max pooling with 2x2
6 8
5 6 7 8 kernel size and stride 2
3 4
3 2 1 0
1 2 3 4
Gives invariance to small spatial
shifts. No learnable parameters.
y
Stanford CS231n 10th Anniversary Lecture 5 - 102 April 15, 2025

[Page contains 3 table(s)]


### Table 1

| Pooling Layers: Another way to downsample
64 x 224 x 224
Single depth slice
1 1 2 4
x
Max pooling with 2x2
6 8
5 6 7 8 kernel size and stride 2
3 4
3 2 1 0
1 2 3 4
Gives invariance to small spatial
shifts. No learnable parameters.
y |
| Stanford CS231n 10th Anniversary Lecture 5 - 102 April 15, 2025 |


### Table 2

| 1 | 1 | 2 | 4 |
| 5 | 6 | 7 | 8 |
| 3 | 2 | 1 | 0 |
| 1 | 2 | 3 | 4 |


### Table 3

| 6 | 8 |
| 3 | 4 |


[Page contains 1 image(s)]


---
## Page 103
---


Pooling Summary
Common setting:
Input: C x H x W
max, K=2, S=2 => Gives 2x downsampling
Hyperparameters:
- Kernel size: K
- Stride: S
- Pooling function: max, avg
Output size: C x H’ x W’ where:
- H’ = (H – K) / S + 1
- W’ = (W – K) / S + 1
No learnable parameters
Stanford CS231n 10th Anniversary Lecture 5 - 103 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Pooling Summary
Common setting:
Input: C x H x W
max, K=2, S=2 => Gives 2x downsampling
Hyperparameters:
- Kernel size: K
- Stride: S
- Pooling function: max, avg
Output size: C x H’ x W’ where:
- H’ = (H – K) / S + 1
- W’ = (W – K) / S + 1
No learnable parameters |
| Stanford CS231n 10th Anniversary Lecture 5 - 103 April 15, 2025 |


---
## Page 104
---


Convolution and Pooling: Translation Equivariance
H x W x C H’ x W’ x C’
Conv or Pool
Translate
Stanford CS231n 10th Anniversary Lecture 5 - 104 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Convolution and Pooling: Translation Equivariance
H x W x C H’ x W’ x C’
Conv or Pool
Translate |
| Stanford CS231n 10th Anniversary Lecture 5 - 104 April 15, 2025 |


[Page contains 3 image(s)]


---
## Page 105
---


Convolution and Pooling: Translation Equivariance
H x W x C H’ x W’ x C’
Conv or Pool
Conv(Translate(X))
Translate
Translate
= Translate(Conv(X))
Conv or Pool
Stanford CS231n 10th Anniversary Lecture 5 - 105 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Convolution and Pooling: Translation Equivariance
H x W x C H’ x W’ x C’
Conv or Pool
Conv(Translate(X))
Translate
Translate
= Translate(Conv(X))
Conv or Pool |
| Stanford CS231n 10th Anniversary Lecture 5 - 105 April 15, 2025 |


[Page contains 4 image(s)]


---
## Page 106
---


Convolution and Pooling: Translation Equivariance
H x W x C H’ x W’ x C’
Conv or Pool
Conv(Translate(X))
Translate
Translate
= Translate(Conv(X))
Conv or Pool
Intuition: Features of images don’t depend on their location in the image
Stanford CS231n 10th Anniversary Lecture 5 - 106 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Convolution and Pooling: Translation Equivariance
H x W x C H’ x W’ x C’
Conv or Pool
Conv(Translate(X))
Translate
Translate
= Translate(Conv(X))
Conv or Pool
Intuition: Features of images don’t depend on their location in the image |
| Stanford CS231n 10th Anniversary Lecture 5 - 106 April 15, 2025 |


[Page contains 4 image(s)]


---
## Page 107
---


Summary: Convolutional Networks
Fully-Connected Layer Activation Function
x h s
Convolution Layer Pooling Layer
Stanford CS231n 10th Anniversary Lecture 5 - 107 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Summary: Convolutional Networks
Fully-Connected Layer Activation Function
x h s
Convolution Layer Pooling Layer |
| Stanford CS231n 10th Anniversary Lecture 5 - 107 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 108
---


Next time: CNN Architectures
Stanford CS231n 10th Anniversary Lecture 5 - 108 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Next time: CNN Architectures |
| Stanford CS231n 10th Anniversary Lecture 5 - 108 April 15, 2025 |


[Page contains 4 image(s)]


---
## Page 109
---


Appendix (Slides from Previous Years)
Stanford CS231n 10th Anniversary Lecture 5 - 109 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Appendix (Slides from Previous Years) |
| Stanford CS231n 10th Anniversary Lecture 5 - 109 April 15, 2025 |


---
## Page 110
---


Today: Convolutional Networks
Fully-Connected Layer Activation Function
We have
already x h s
seen these
Convolution Layer Pooling Layer
Today: Image-
specific
operators
Stanford CS231n 10th Anniversary Lecture 5 - 110 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Today: Convolutional Networks
Fully-Connected Layer Activation Function
We have
already x h s
seen these
Convolution Layer Pooling Layer
Today: Image-
specific
operators |
| Stanford CS231n 10th Anniversary Lecture 5 - 110 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 111
---


Convolution layer: summary
Let’s assume input is W x H x C
1 1
Conv layer needs 4 hyperparameters:
- Number of filters K
- The filter size F
- The stride S
- The zero padding P
This will produce an output of W x H x K
2 2
where:
- W = (W - F + 2P)/S + 1
2 1
- H = (H - F + 2P)/S + 1
2 1
Number of parameters: F2CK and K biases
Stanford CS231n 10th Anniversary Lecture 5 - 111 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Convolution layer: summary
Let’s assume input is W x H x C
1 1
Conv layer needs 4 hyperparameters:
- Number of filters K
- The filter size F
- The stride S
- The zero padding P
This will produce an output of W x H x K
2 2
where:
- W = (W - F + 2P)/S + 1
2 1
- H = (H - F + 2P)/S + 1
2 1
Number of parameters: F2CK and K biases |
| Stanford CS231n 10th Anniversary Lecture 5 - 111 April 15, 2025 |


---
## Page 112
---


Convolution layer: summary
Common settings:
K = (powers of 2, e.g. 32, 64, 128, 512)
Let’s assume input is W x H x C
1 1
- F = 3, S = 1, P = 1
Conv layer needs 4 hyperparameters:
- F = 5, S = 1, P = 2
- Number of filters K
- F = 5, S = 2, P = ? (whatever fits)
- The filter size F - F = 1, S = 1, P = 0
- The stride S
- The zero padding P
This will produce an output of W x H x K
2 2
where:
- W = (W - F + 2P)/S + 1
2 1
- H = (H - F + 2P)/S + 1
2 1
Number of parameters: F2CK and K biases
Stanford CS231n 10th Anniversary Lecture 5 - 112 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Convolution layer: summary
Common settings:
K = (powers of 2, e.g. 32, 64, 128, 512)
Let’s assume input is W x H x C
1 1
- F = 3, S = 1, P = 1
Conv layer needs 4 hyperparameters:
- F = 5, S = 1, P = 2
- Number of filters K
- F = 5, S = 2, P = ? (whatever fits)
- The filter size F - F = 1, S = 1, P = 0
- The stride S
- The zero padding P
This will produce an output of W x H x K
2 2
where:
- W = (W - F + 2P)/S + 1
2 1
- H = (H - F + 2P)/S + 1
2 1
Number of parameters: F2CK and K biases |
| Stanford CS231n 10th Anniversary Lecture 5 - 112 April 15, 2025 |


---
## Page 113
---


(btw, 1x1 convolution layers make perfect sense)
1x1 CONV
56 with 32 filters
56
(each filter has size 1x1x64,
and performs a 64-
dimensional dot product)
56
56
64 32
Stanford CS231n 10th Anniversary Lecture 5 - 113 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| (btw, 1x1 convolution layers make perfect sense)
1x1 CONV
56 with 32 filters
56
(each filter has size 1x1x64,
and performs a 64-
dimensional dot product)
56
56
64 32 |
| Stanford CS231n 10th Anniversary Lecture 5 - 113 April 15, 2025 |


---
## Page 114
---


(btw, 1x1 convolution layers make perfect sense)
1x1 CONV
56 with 32 filters
56
(each filter has size 1x1x64,
and performs a 64-
dimensional dot product)
56
56
64 32
Stanford CS231n 10th Anniversary Lecture 5 - 114 April 15, 2025

[Page contains 3 table(s)]


### Table 1

| (btw, 1x1 convolution layers make perfect sense)
1x1 CONV
56 with 32 filters
56
(each filter has size 1x1x64,
and performs a 64-
dimensional dot product)
56
56
64 32 |
| Stanford CS231n 10th Anniversary Lecture 5 - 114 April 15, 2025 |


### Table 2

|  |
|  |


### Table 3

|  |
|  |


---
## Page 115
---


Example: CONV
layer in PyTorch
Conv layer needs 4 hyperparameters:
- Number of filters K
- The filter size F
- The stride S
- The zero padding P
PyTorchis licensed under BSD 3-clause.
Stanford CS231n 10th Anniversary Lecture 5 - 115 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Example: CONV
layer in PyTorch
Conv layer needs 4 hyperparameters:
- Number of filters K
- The filter size F
- The stride S
- The zero padding P
PyTorchis licensed under BSD 3-clause. |
| Stanford CS231n 10th Anniversary Lecture 5 - 115 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 116
---


The brain/neuron view of CONV Layer
32x32x3 image
5x5x3 filter
32
1 number:
32 the result of taking a dot product between the
filter and this part of the image
3
(i.e. 5*5*3 = 75-dimensional dot product)
Stanford CS231n 10th Anniversary Lecture 5 - 116 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| The brain/neuron view of CONV Layer
32x32x3 image
5x5x3 filter
32
1 number:
32 the result of taking a dot product between the
filter and this part of the image
3
(i.e. 5*5*3 = 75-dimensional dot product) |
| Stanford CS231n 10th Anniversary Lecture 5 - 116 April 15, 2025 |


---
## Page 117
---


The brain/neuron view of CONV Layer
32x32x3 image
5x5x3 filter
32
It’s just a neuron with local
connectivity...
1 number:
32 the result of taking a dot product between the
filter and this part of the image
3
(i.e. 5*5*3 = 75-dimensional dot product)
Stanford CS231n 10th Anniversary Lecture 5 - 117 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| The brain/neuron view of CONV Layer
32x32x3 image
5x5x3 filter
32
It’s just a neuron with local
connectivity...
1 number:
32 the result of taking a dot product between the
filter and this part of the image
3
(i.e. 5*5*3 = 75-dimensional dot product) |
| Stanford CS231n 10th Anniversary Lecture 5 - 117 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 118
---


The brain/neuron view of CONV Layer
32
E.g. with 5 filters,
28
CONV layer consists of neurons
arranged in a 3D grid
(28x28x5)
There will be 5 different neurons
32 28
all looking at the same region in
the input volume
3
5
Stanford CS231n 10th Anniversary Lecture 5 - 118 April 15, 2025

[Page contains 2 table(s)]


### Table 1

| The brain/neuron view of CONV Layer
32
E.g. with 5 filters,
28
CONV layer consists of neurons
arranged in a 3D grid
(28x28x5)
There will be 5 different neurons
32 28
all looking at the same region in
the input volume
3
5 |
| Stanford CS231n 10th Anniversary Lecture 5 - 118 April 15, 2025 |


### Table 2

|  |  |


[Page contains 1 image(s)]


---
## Page 119
---


Reminder: Fully Connected Layer
Each neuron
looks at the full
32x32x3 image -> stretch to 3072 x 1
input volume
input activation
1 1
10 x 3072
3072 10
weights
1 number:
the result of taking a dot product
between a row of W and the input (a
3072-dimensional dot product)
Stanford CS231n 10th Anniversary Lecture 5 - 119 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Reminder: Fully Connected Layer
Each neuron
looks at the full
32x32x3 image -> stretch to 3072 x 1
input volume
input activation
1 1
10 x 3072
3072 10
weights
1 number:
the result of taking a dot product
between a row of W and the input (a
3072-dimensional dot product) |
| Stanford CS231n 10th Anniversary Lecture 5 - 119 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 120
---


Stanford CS231n 10th Anniversary Lecture 5 - 120 April 15, 2025

[Page contains 1 table(s)]


### Table 1

|  |
| Stanford CS231n 10th Anniversary Lecture 5 - 120 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 121
---


Pooling layer
- makes the representations smaller and more manageable
- operates over each activation map independently
Stanford CS231n 10th Anniversary Lecture 5 - 121 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Pooling layer
- makes the representations smaller and more manageable
- operates over each activation map independently |
| Stanford CS231n 10th Anniversary Lecture 5 - 121 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 122
---


MAX POOLING
Single depth slice
1 1 2 4
x
max pool with 2x2 filters
6 8
5 6 7 8 and stride 2
3 4
3 2 1 0
1 2 3 4
y
Stanford CS231n 10th Anniversary Lecture 5 - 122 April 15, 2025

[Page contains 3 table(s)]


### Table 1

| MAX POOLING
Single depth slice
1 1 2 4
x
max pool with 2x2 filters
6 8
5 6 7 8 and stride 2
3 4
3 2 1 0
1 2 3 4
y |
| Stanford CS231n 10th Anniversary Lecture 5 - 122 April 15, 2025 |


### Table 2

| 1 | 1 | 2 | 4 |
| 5 | 6 | 7 | 8 |
| 3 | 2 | 1 | 0 |
| 1 | 2 | 3 | 4 |


### Table 3

| 6 | 8 |
| 3 | 4 |


---
## Page 123
---


MAX POOLING
Single depth slice
1 1 2 4
x
max pool with 2x2 filters
6 8
5 6 7 8 and stride 2
3 4
3 2 1 0
1 2 3 4
• No learnable parameters
• Introduces spatial invariance
y
Stanford CS231n 10th Anniversary Lecture 5 - 123 April 15, 2025

[Page contains 3 table(s)]


### Table 1

| MAX POOLING
Single depth slice
1 1 2 4
x
max pool with 2x2 filters
6 8
5 6 7 8 and stride 2
3 4
3 2 1 0
1 2 3 4
• No learnable parameters
• Introduces spatial invariance
y |
| Stanford CS231n 10th Anniversary Lecture 5 - 123 April 15, 2025 |


### Table 2

| 1 | 1 | 2 | 4 |
| 5 | 6 | 7 | 8 |
| 3 | 2 | 1 | 0 |
| 1 | 2 | 3 | 4 |


### Table 3

| 6 | 8 |
| 3 | 4 |


---
## Page 124
---


Pooling layer: summary
Let’s assume input is W x H x C
1 1
Conv layer needs 2 hyperparameters:
- The spatial extent F
- The stride S
This will produce an output of W x H x C where:
2 2
- W = (W - F )/S + 1
2 1
- H = (H - F)/S + 1
2 1
Number of parameters: 0
Stanford CS231n 10th Anniversary Lecture 5 - 124 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Pooling layer: summary
Let’s assume input is W x H x C
1 1
Conv layer needs 2 hyperparameters:
- The spatial extent F
- The stride S
This will produce an output of W x H x C where:
2 2
- W = (W - F )/S + 1
2 1
- H = (H - F)/S + 1
2 1
Number of parameters: 0 |
| Stanford CS231n 10th Anniversary Lecture 5 - 124 April 15, 2025 |


---
## Page 125
---


Summary
- ConvNets stack CONV,POOL,FC layers
- Trend towards smaller filters and deeper architectures
- Trend towards getting rid of POOL/FC layers (just CONV)
- Historically architectures looked like
[(CONV-RELU)*N-POOL?]*M-(FC-RELU)*K,SOFTMAX
where N is usually up to ~5, M is large, 0 <= K <= 2.
- But recent advances such as ResNet/GoogLeNet have
challenged this paradigm
Stanford CS231n 10th Anniversary Lecture 5 - 125 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Summary
- ConvNets stack CONV,POOL,FC layers
- Trend towards smaller filters and deeper architectures
- Trend towards getting rid of POOL/FC layers (just CONV)
- Historically architectures looked like
[(CONV-RELU)*N-POOL?]*M-(FC-RELU)*K,SOFTMAX
where N is usually up to ~5, M is large, 0 <= K <= 2.
- But recent advances such as ResNet/GoogLeNet have
challenged this paradigm |
| Stanford CS231n 10th Anniversary Lecture 5 - 125 April 15, 2025 |


---
## Page 126
---


Fully Connected Layer (FC layer)
- Contains neurons that connect to the entire input volume, as in ordinary Neural
Networks
Stanford CS231n 10th Anniversary Lecture 5 - 126 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Fully Connected Layer (FC layer)
- Contains neurons that connect to the entire input volume, as in ordinary Neural
Networks |
| Stanford CS231n 10th Anniversary Lecture 5 - 126 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 127
---


[ConvNetJS demo: training on CIFAR-10]
http://cs.stanford.edu/people/karpathy/convnetjs/demo/cifar10.html
Stanford CS231n 10th Anniversary Lecture 5 - 127 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| [ConvNetJS demo: training on CIFAR-10]
http://cs.stanford.edu/people/karpathy/convnetjs/demo/cifar10.html |
| Stanford CS231n 10th Anniversary Lecture 5 - 127 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 128
---


Deep Learning Overview
Image Classification
1. Encode your problem as y = f(x)
where x and y are grids of numbers.
Get a dataset of (x, y) pairs.
Image: x Scores: y
Scores for
each class
[32 x 32 x 3] [10]
Stanford CS231n 10th Anniversary Lecture 5 - 128 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Deep Learning Overview
Image Classification
1. Encode your problem as y = f(x)
where x and y are grids of numbers.
Get a dataset of (x, y) pairs.
Image: x Scores: y
Scores for
each class
[32 x 32 x 3] [10] |
| Stanford CS231n 10th Anniversary Lecture 5 - 128 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 129
---


Deep Learning Overview
Softmax Loss
1. Encode your problem as y = f(x)
where x and y are grids of numbers.
s: vector of n scores
Get a dataset of (x, y) pairs.
2. Define a loss function L(y , y ) y: int in [0, n)
pred gt
that measures the correctness of
𝑒
−𝑠𝑦
𝐿(𝑠, 𝑦) = − log
predictions with a single number −𝑠
σ 𝑒 𝑖
𝑖
Scores for y should be +inf
s
Others should be -inf
Stanford CS231n 10th Anniversary Lecture 5 - 129 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Deep Learning Overview
Softmax Loss
1. Encode your problem as y = f(x)
where x and y are grids of numbers.
s: vector of n scores
Get a dataset of (x, y) pairs.
2. Define a loss function L(y , y ) y: int in [0, n)
pred gt
that measures the correctness of −𝑠𝑦
𝑒
𝐿(𝑠, 𝑦) = − log
predictions with a single number −𝑠
σ 𝑒 𝑖
𝑖
Scores for y should be +inf
s
Others should be -inf |
| Stanford CS231n 10th Anniversary Lecture 5 - 129 April 15, 2025 |


---
## Page 130
---


Deep Learning Overview
Linear Classifiers
1. Encode your problem as y = f(x)
where x and y are grids of numbers.
𝑓 𝑥, 𝑤, 𝑏 = 𝑊𝑥 + 𝑏
Get a dataset of (x, y) pairs.
2. Define a loss function L(y , y )
pred gt
that measures the correctness of
predictions with a single number
3. Define a computational graph that
predicts y from x using learnable
weights w
Stanford CS231n 10th Anniversary Lecture 5 - 130 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Deep Learning Overview
Linear Classifiers
1. Encode your problem as y = f(x)
where x and y are grids of numbers.
𝑓 𝑥, 𝑤, 𝑏 = 𝑊𝑥 + 𝑏
Get a dataset of (x, y) pairs.
2. Define a loss function L(y , y )
pred gt
that measures the correctness of
predictions with a single number
3. Define a computational graph that
predicts y from x using learnable
weights w |
| Stanford CS231n 10th Anniversary Lecture 5 - 130 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 131
---


Deep Learning Overview
Linear Classifiers
1. Encode your problem as y = f(x)
where x and y are grids of numbers.
𝑓 𝑥, 𝑤, 𝑏 = 𝑊𝑥 + 𝑏
Get a dataset of (x, y) pairs.
2. Define a loss function L(y , y )
pred gt
that measures the correctness of
predictions with a single number
3. Define a computational graph that
predicts y from x using learnable
weights w
Stanford CS231n 10th Anniversary Lecture 5 - 131 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Deep Learning Overview
Linear Classifiers
1. Encode your problem as y = f(x)
where x and y are grids of numbers.
𝑓 𝑥, 𝑤, 𝑏 = 𝑊𝑥 + 𝑏
Get a dataset of (x, y) pairs.
2. Define a loss function L(y , y )
pred gt
that measures the correctness of
predictions with a single number
3. Define a computational graph that
predicts y from x using learnable
weights w |
| Stanford CS231n 10th Anniversary Lecture 5 - 131 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 132
---


Deep Learning Overview
1. Encode your problem as y = f(x)
where x and y are grids of numbers.
Get a dataset of (x, y) pairs.
2. Define a loss function L(y , y )
pred gt
that measures the correctness of
predictions with a single number
3. Define a computational graph that
predicts y from x using learnable
weights w
4. Compute gradients dL/dw using
backpropagation
5. Find w that minimizes the loss using
optimization algorithms
Stanford CS231n 10th Anniversary Lecture 5 - 132 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Deep Learning Overview
1. Encode your problem as y = f(x)
where x and y are grids of numbers.
Get a dataset of (x, y) pairs.
2. Define a loss function L(y , y )
pred gt
that measures the correctness of
predictions with a single number
3. Define a computational graph that
predicts y from x using learnable
weights w
4. Compute gradients dL/dw using
backpropagation
5. Find w that minimizes the loss using
optimization algorithms |
| Stanford CS231n 10th Anniversary Lecture 5 - 132 April 15, 2025 |


---
## Page 133
---


A bit of history...
The Mark I Perceptron machine was the first
implementation of the perceptron algorithm.
The machine was connected to a camera that used 20×20
cadmium sulfide photocells to produce a 400-pixel image.
recognized
letters of the alphabet
update rule:
Frank Rosenblatt, ~1957: Perceptron
This imageby Rocky Acosta is licensed under CC-BY 3.0
Stanford CS231n 10th Anniversary Lecture 5 - 133 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| A bit of history...
The Mark I Perceptron machine was the first
implementation of the perceptron algorithm.
The machine was connected to a camera that used 20×20
cadmium sulfide photocells to produce a 400-pixel image.
recognized
letters of the alphabet
update rule:
Frank Rosenblatt, ~1957: Perceptron
This imageby Rocky Acosta is licensed under CC-BY 3.0 |
| Stanford CS231n 10th Anniversary Lecture 5 - 133 April 15, 2025 |


[Page contains 4 image(s)]


---
## Page 134
---


A bit of history...
Widrow and Hoff, ~1960: Adaline/Madaline These figures are reproduced from Widrow 1960, Stanford Electronics Laboratories Technical
Reportwith permission from Stanford University Special Collections.
Stanford CS231n 10th Anniversary Lecture 5 - 134 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| A bit of history...
Widrow and Hoff, ~1960: Adaline/Madaline These figures are reproduced from Widrow 1960, Stanford Electronics Laboratories Technical
Reportwith permission from Stanford University Special Collections. |
| Stanford CS231n 10th Anniversary Lecture 5 - 134 April 15, 2025 |


[Page contains 3 image(s)]


---
## Page 135
---


A bit of history...
recognizable math
Illustration of Rumelhartet al., 1986 by Lane McIntosh,
copyright CS231n 2017
Rumelhart et al., 1986: First time back-propagation became popular
Stanford CS231n 10th Anniversary Lecture 5 - 135 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| A bit of history...
recognizable math
Illustration of Rumelhartet al., 1986 by Lane McIntosh,
copyright CS231n 2017
Rumelhart et al., 1986: First time back-propagation became popular |
| Stanford CS231n 10th Anniversary Lecture 5 - 135 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 136
---


A bit of history...
[Hinton and Salakhutdinov 2006]
Reinvigorated research in
Deep Learning
Illustration of Hinton and Salakhutdinov2006 by Lane
McIntosh, copyright CS231n 2017
Stanford CS231n 10th Anniversary Lecture 5 - 136 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| A bit of history...
[Hinton and Salakhutdinov 2006]
Reinvigorated research in
Deep Learning
Illustration of Hinton and Salakhutdinov2006 by Lane
McIntosh, copyright CS231n 2017 |
| Stanford CS231n 10th Anniversary Lecture 5 - 136 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 137
---


First strong results
Acoustic Modeling using Deep Belief Networks
Abdel-rahmanMohamed, George Dahl, Geoffrey Hinton, 2010
Context-Dependent Pre-trained Deep Neural Networks
for Large Vocabulary Speech Recognition
George Dahl, Dong Yu, Li Deng, Alex Acero, 2012
Imagenetclassification with deep convolutional
neural networks Illustration of Dahl et al. 2012 by Lane McIntosh, copyright
CS231n 2017
Alex Krizhevsky, Ilya Sutskever, Geoffrey E Hinton, 2012
Figures copyright Alex Krizhevsky, Ilya Sutskever, and Geoffrey Hinton, 2012. Reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 5 - 137 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| First strong results
Acoustic Modeling using Deep Belief Networks
Abdel-rahmanMohamed, George Dahl, Geoffrey Hinton, 2010
Context-Dependent Pre-trained Deep Neural Networks
for Large Vocabulary Speech Recognition
George Dahl, Dong Yu, Li Deng, Alex Acero, 2012
Imagenetclassification with deep convolutional
neural networks Illustration of Dahl et al. 2012 by Lane McIntosh, copyright
CS231n 2017
Alex Krizhevsky, Ilya Sutskever, Geoffrey E Hinton, 2012
Figures copyright Alex Krizhevsky, Ilya Sutskever, and Geoffrey Hinton, 2012. Reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 5 - 137 April 15, 2025 |


[Page contains 3 image(s)]


---
## Page 138
---


A bit of history:
Hubel & Wiesel,
1959
RECEPTIVE FIELDS OF SINGLE NEURONES IN
THE CAT'S STRIATE CORTEX
1962
RECEPTIVE FIELDS, BINOCULAR INTERACTION
AND FUNCTIONAL ARCHITECTURE IN
THE CAT'S VISUAL CORTEX
1968...
Cat imageby CNX OpenStax is licensed
under CC BY 4.0; changes made
Stanford CS231n 10th Anniversary Lecture 5 - 138 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| A bit of history:
Hubel & Wiesel,
1959
RECEPTIVE FIELDS OF SINGLE NEURONES IN
THE CAT'S STRIATE CORTEX
1962
RECEPTIVE FIELDS, BINOCULAR INTERACTION
AND FUNCTIONAL ARCHITECTURE IN
THE CAT'S VISUAL CORTEX
1968...
Cat imageby CNX OpenStax is licensed
under CC BY 4.0; changes made |
| Stanford CS231n 10th Anniversary Lecture 5 - 138 April 15, 2025 |


[Page contains 1 image(s)]


---
## Page 139
---


A bit of history
Human brain
Topographical mapping in the cortex:
nearby cells in cortex represent
nearby regions in the visual field
Visual
cortex
Retinotopy images courtesy of Jesse Gomez in the
Stanford Vision & Perception Neuroscience Lab.
Stanford CS231n 10th Anniversary Lecture 5 - 139 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| A bit of history
Human brain
Topographical mapping in the cortex:
nearby cells in cortex represent
nearby regions in the visual field
Visual
cortex
Retinotopy images courtesy of Jesse Gomez in the
Stanford Vision & Perception Neuroscience Lab. |
| Stanford CS231n 10th Anniversary Lecture 5 - 139 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 140
---


Hierarchical organization
Illustration of hierarchical organization in early visual
pathways by Lane McIntosh, copyright CS231n 2017
Stanford CS231n 10th Anniversary Lecture 5 - 140 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| Hierarchical organization
Illustration of hierarchical organization in early visual
pathways by Lane McIntosh, copyright CS231n 2017 |
| Stanford CS231n 10th Anniversary Lecture 5 - 140 April 15, 2025 |


[Page contains 2 image(s)]


---
## Page 141
---


A bit of history:
Neocognitron
[Fukushima 1980]
“sandwich” architecture (SCSCSC…)
simple cells: modifiable parameters
complex cells: perform pooling
Stanford CS231n 10th Anniversary Lecture 5 - 141 April 15, 2025

[Page contains 1 table(s)]


### Table 1

| A bit of history:
Neocognitron
[Fukushima 1980]
“sandwich” architecture (SCSCSC…)
simple cells: modifiable parameters
complex cells: perform pooling |
| Stanford CS231n 10th Anniversary Lecture 5 - 141 April 15, 2025 |
