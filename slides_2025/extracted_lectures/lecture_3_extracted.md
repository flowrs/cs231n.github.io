# lecture_3

Extracted using pdfplumber



---
## Page 1
---


Lecture 3:
Regularization and Optimization
Stanford CS231n 10th Anniversary Lecture 3 - 1 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture 3:
Regularization and Optimization |
| Stanford CS231n 10th Anniversary Lecture 3 - 1 April 8, 2025 |


---
## Page 2
---


Administrative: Assignment 1
Will release tomorrow, due Wed 4/23 at 11:59pm
Office hours: help with high-level questions only, no code
debugging. [No Code Show Policy]
Stanford CS231n 10th Anniversary Lecture 3 - 2 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Administrative: Assignment 1
Will release tomorrow, due Wed 4/23 at 11:59pm
Office hours: help with high-level questions only, no code
debugging. [No Code Show Policy] |
| Stanford CS231n 10th Anniversary Lecture 3 - 2 April 8, 2025 |


---
## Page 3
---


Administrative: Project proposal + Office Hours
Due Fri 4/25
TA expertise + Office Hours are posted on the webpage. Mix of in-
person and zoom.
(http://cs231n.stanford.edu/office_hours.html)
Stanford CS231n 10th Anniversary Lecture 3 - 3 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Administrative: Project proposal + Office Hours
Due Fri 4/25
TA expertise + Office Hours are posted on the webpage. Mix of in-
person and zoom.
(http://cs231n.stanford.edu/office_hours.html) |
| Stanford CS231n 10th Anniversary Lecture 3 - 3 April 8, 2025 |


---
## Page 4
---


Administrative: Ed
Please make sure to check and read all pinned Ed posts.
● CGOE: if you would like to take the midterm on-campus, send
us an email: cs231n-staff-spr25@stanford.edu
Stanford CS231n 10th Anniversary Lecture 3 - 4 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Administrative: Ed
Please make sure to check and read all pinned Ed posts.
● CGOE: if you would like to take the midterm on-campus, send
us an email: cs231n-staff-spr25@stanford.edu |
| Stanford CS231n 10th Anniversary Lecture 3 - 4 April 8, 2025 |


---
## Page 5
---


Recap from Last Week
Stanford CS231n 10th Anniversary Lecture 3 - 5 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Recap from Last Week |
| Stanford CS231n 10th Anniversary Lecture 3 - 5 April 8, 2025 |


---
## Page 6
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
Stanford CS231n 10th Anniversary Lecture 3 - 6 April 8, 2025

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
| Stanford CS231n 10th Anniversary Lecture 3 - 6 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 7
---


Recall from last time: Challenges of recognition
Viewpoint Illumination Deformation Occlusion
This imageby Umberto Salvagnin
This imageis CC0 1.0public domain This imageby jonssonis licensed
is licensed under CC-BY 2.0
under CC-BY 2.0
Clutter Intraclass Variation
This imageis CC0 1.0public domain This imageis CC0 1.0public domain
Stanford CS231n 10th Anniversary Lecture 3 - 7 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Recall from last time: Challenges of recognition
Viewpoint Illumination Deformation Occlusion
This imageby Umberto Salvagnin
This imageis CC0 1.0public domain This imageby jonssonis licensed
is licensed under CC-BY 2.0
under CC-BY 2.0
Clutter Intraclass Variation
This imageis CC0 1.0public domain This imageis CC0 1.0public domain |
| Stanford CS231n 10th Anniversary Lecture 3 - 7 April 8, 2025 |


[Page contains 6 image(s)]


---
## Page 8
---


Recall from last time: data-driven approach, kNN
1-NN classifier 5-NN classifier
train test
train validation test
Stanford CS231n 10th Anniversary Lecture 3 - 8 April 8, 2025

[Page contains 3 table(s)]


### Table 1

| Recall from last time: data-driven approach, kNN
1-NN classifier 5-NN classifier
train test
train validation test |
| Stanford CS231n 10th Anniversary Lecture 3 - 8 April 8, 2025 |


### Table 2

| train | test |


### Table 3

| train | validation | test |


[Page contains 4 image(s)]


---
## Page 9
---


Recall from last time: Linear Classifier
f(x,W) = Wx + b
Stanford CS231n 10th Anniversary Lecture 3 - 9 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Recall from last time: Linear Classifier
f(x,W) = Wx + b |
| Stanford CS231n 10th Anniversary Lecture 3 - 9 April 8, 2025 |


[Page contains 3 image(s)]


---
## Page 10
---


Suppose: 3 training examples, 3 classes.
A loss function tells how good
With some W the scores are:
our current classifier is
Given a dataset of examples
Where is image and
cat 3.2 1.3 2.2 is (integer) label
5.1 4.9 2.5 Loss over the dataset is a
car
average of loss over examples:
-1.7 2.0 -3.1
frog
Stanford CS231n 10th Anniversary Lecture 3 - 13 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Suppose: 3 training examples, 3 classes.
A loss function tells how good
With some W the scores are:
our current classifier is
Given a dataset of examples
Where is image and
cat 3.2 1.3 2.2 is (integer) label
5.1 4.9 2.5 Loss over the dataset is a
car
average of loss over examples:
-1.7 2.0 -3.1
frog |
| Stanford CS231n 10th Anniversary Lecture 3 - 13 April 8, 2025 |


[Page contains 8 image(s)]


---
## Page 11
---


Regularization -
Data loss: Model predictions
should match training data
Stanford CS231n 10th Anniversary Lecture 3 - 14 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Regularization -
Data loss: Model predictions
should match training data |
| Stanford CS231n 10th Anniversary Lecture 3 - 14 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 12
---


Regularization
Data loss: Model predictions
Regularization: Prevent the model
should match training data
from doing too well on training data
Stanford CS231n 10th Anniversary Lecture 3 - 15 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Regularization
Data loss: Model predictions
Regularization: Prevent the model
should match training data
from doing too well on training data |
| Stanford CS231n 10th Anniversary Lecture 3 - 15 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 13
---


Regularization intuition: toy example training data
y
x
Stanford CS231n 10th Anniversary Lecture 3 - 16 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Regularization intuition: toy example training data
y
x |
| Stanford CS231n 10th Anniversary Lecture 3 - 16 April 8, 2025 |


---
## Page 14
---


Regularization intuition: Prefer Simpler Models
f
1 f
2
y
x
Stanford CS231n 10th Anniversary Lecture 3 - 17 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Regularization intuition: Prefer Simpler Models
f
1 f
2
y
x |
| Stanford CS231n 10th Anniversary Lecture 3 - 17 April 8, 2025 |


---
## Page 15
---


Regularization: Prefer Simpler Models
f
1 f
2
y
x
Regularization pushes against fitting the data
too well so we don’t fit noise in the data
Stanford CS231n 10th Anniversary Lecture 3 - 18 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Regularization: Prefer Simpler Models
f
1 f
2
y
x
Regularization pushes against fitting the data
too well so we don’t fit noise in the data |
| Stanford CS231n 10th Anniversary Lecture 3 - 18 April 8, 2025 |


---
## Page 16
---


Regularization
Data loss: Model predictions
Regularization: Prevent the model
should match training data
from doing too well on training data
Occam’s Razor: Among multiple
competing hypotheses, the simplest is the
best, William of Ockham 1285-1347
Stanford CS231n 10th Anniversary Lecture 3 - 19 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Regularization
Data loss: Model predictions
Regularization: Prevent the model
should match training data
from doing too well on training data
Occam’s Razor: Among multiple
competing hypotheses, the simplest is the
best, William of Ockham 1285-1347 |
| Stanford CS231n 10th Anniversary Lecture 3 - 19 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 17
---


Regularization
= regularization strength
(hyperparameter)
Data loss: Model predictions
Regularization: Prevent the model
should match training data
from doing too well on training data
Stanford CS231n 10th Anniversary Lecture 3 - 20 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Regularization
= regularization strength
(hyperparameter)
Data loss: Model predictions
Regularization: Prevent the model
should match training data
from doing too well on training data |
| Stanford CS231n 10th Anniversary Lecture 3 - 20 April 8, 2025 |


[Page contains 2 image(s)]


---
## Page 18
---


Regularization
= regularization strength
(hyperparameter)
Data loss: Model predictions
Regularization: Prevent the model
should match training data
from doing too well on training data
Simple examples
L2 regularization:
L1 regularization:
Elastic net (L1 + L2):
Stanford CS231n 10th Anniversary Lecture 3 - 21 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Regularization
= regularization strength
(hyperparameter)
Data loss: Model predictions
Regularization: Prevent the model
should match training data
from doing too well on training data
Simple examples
L2 regularization:
L1 regularization:
Elastic net (L1 + L2): |
| Stanford CS231n 10th Anniversary Lecture 3 - 21 April 8, 2025 |


[Page contains 5 image(s)]


---
## Page 19
---


Regularization
= regularization strength
(hyperparameter)
Data loss: Model predictions
Regularization: Prevent the model
should match training data
from doing too well on training data
Simple examples More complex:
L2 regularization: Dropout
L1 regularization: Batch normalization
Elastic net (L1 + L2): Stochastic depth, fractional pooling, etc
Stanford CS231n 10th Anniversary Lecture 3 - 22 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Regularization
= regularization strength
(hyperparameter)
Data loss: Model predictions
Regularization: Prevent the model
should match training data
from doing too well on training data
Simple examples More complex:
L2 regularization: Dropout
L1 regularization: Batch normalization
Elastic net (L1 + L2): Stochastic depth, fractional pooling, etc |
| Stanford CS231n 10th Anniversary Lecture 3 - 22 April 8, 2025 |


[Page contains 5 image(s)]


---
## Page 20
---


Regularization
= regularization strength
(hyperparameter)
Data loss: Model predictions
Regularization: Prevent the model
should match training data
from doing too well on training data
Why regularize?
- Express preferences over weights
- Make the model simple so it works on test data
- Improve optimization by adding curvature
Stanford CS231n 10th Anniversary Lecture 3 - 23 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Regularization
= regularization strength
(hyperparameter)
Data loss: Model predictions
Regularization: Prevent the model
should match training data
from doing too well on training data
Why regularize?
- Express preferences over weights
- Make the model simple so it works on test data
- Improve optimization by adding curvature |
| Stanford CS231n 10th Anniversary Lecture 3 - 23 April 8, 2025 |


[Page contains 2 image(s)]


---
## Page 21
---


Regularization: Expressing Preferences
L2 Regularization
Which of w1 or w2 will
the L2 regularizer prefer?
Stanford CS231n 10th Anniversary Lecture 3 - 24 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Regularization: Expressing Preferences
L2 Regularization
Which of w1 or w2 will
the L2 regularizer prefer? |
| Stanford CS231n 10th Anniversary Lecture 3 - 24 April 8, 2025 |


[Page contains 5 image(s)]


---
## Page 22
---


Regularization: Expressing Preferences
L2 Regularization
Which of w1 or w2 will
the L2 regularizer prefer?
L2 regularization likes to
“spread out” the weights
Stanford CS231n 10th Anniversary Lecture 3 - 25 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Regularization: Expressing Preferences
L2 Regularization
Which of w1 or w2 will
the L2 regularizer prefer?
L2 regularization likes to
“spread out” the weights |
| Stanford CS231n 10th Anniversary Lecture 3 - 25 April 8, 2025 |


[Page contains 5 image(s)]


---
## Page 23
---


Regularization: Expressing Preferences
L2 Regularization
Which of w1 or w2 will
the L2 regularizer prefer?
L2 regularization likes to
“spread out” the weights
Which one would L1
regularization prefer?
Stanford CS231n 10th Anniversary Lecture 3 - 26 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Regularization: Expressing Preferences
L2 Regularization
Which of w1 or w2 will
the L2 regularizer prefer?
L2 regularization likes to
“spread out” the weights
Which one would L1
regularization prefer? |
| Stanford CS231n 10th Anniversary Lecture 3 - 26 April 8, 2025 |


[Page contains 5 image(s)]


---
## Page 24
---


Recap
- We have some dataset of (x,y)
e.g.
- We have a score function:
- We have a loss function:
Softmax
Full loss
Stanford CS231n 10th Anniversary Lecture 3 - 27 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Recap
- We have some dataset of (x,y)
e.g.
- We have a score function:
- We have a loss function:
Softmax
Full loss |
| Stanford CS231n 10th Anniversary Lecture 3 - 27 April 8, 2025 |


[Page contains 4 image(s)]


---
## Page 25
---


How do we find the best W?
Recap
- We have some dataset of (x,y)
e.g.
- We have a score function:
- We have a loss function:
Softmax
Full loss
Stanford CS231n 10th Anniversary Lecture 3 - 28 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| How do we find the best W?
Recap
- We have some dataset of (x,y)
e.g.
- We have a score function:
- We have a loss function:
Softmax
Full loss |
| Stanford CS231n 10th Anniversary Lecture 3 - 28 April 8, 2025 |


[Page contains 4 image(s)]


---
## Page 26
---


Optimization
Stanford CS231n 10th Anniversary Lecture 3 - 30 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Optimization |
| Stanford CS231n 10th Anniversary Lecture 3 - 30 April 8, 2025 |


---
## Page 27
---


This imageis CC0 1.0public domain
Stanford CS231n 10th Anniversary Lecture 3 - 31 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| This imageis CC0 1.0public domain |
| Stanford CS231n 10th Anniversary Lecture 3 - 31 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 28
---


Walking man image is CC0 1.0public domain
Stanford CS231n 10th Anniversary Lecture 3 - 32 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Walking man image is CC0 1.0public domain |
| Stanford CS231n 10th Anniversary Lecture 3 - 32 April 8, 2025 |


[Page contains 2 image(s)]


---
## Page 29
---


Strategy #1: A first very bad idea solution: Random search
Stanford CS231n 10th Anniversary Lecture 3 - 33 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Strategy #1: A first very bad idea solution: Random search |
| Stanford CS231n 10th Anniversary Lecture 3 - 33 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 30
---


Lets see how well this works on the test set...
15.5% accuracy! not bad!
(SOTA is ~99.7%)
Stanford CS231n 10th Anniversary Lecture 3 - 34 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Lets see how well this works on the test set...
15.5% accuracy! not bad!
(SOTA is ~99.7%) |
| Stanford CS231n 10th Anniversary Lecture 3 - 34 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 31
---


Strategy #2: Follow the slope
Stanford CS231n 10th Anniversary Lecture 3 - 35 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Strategy #2: Follow the slope |
| Stanford CS231n 10th Anniversary Lecture 3 - 35 April 8, 2025 |


[Page contains 2 image(s)]


---
## Page 32
---


Strategy #2: Follow the slope
In 1-dimension, the derivative of a function:
In multiple dimensions, the gradient is the vector of (partial derivatives) along
each dimension
The slope in any direction is the dot product of the direction with the gradient
The direction of steepest descent is the negative gradient
Stanford CS231n 10th Anniversary Lecture 3 - 36 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Strategy #2: Follow the slope
In 1-dimension, the derivative of a function:
In multiple dimensions, the gradient is the vector of (partial derivatives) along
each dimension
The slope in any direction is the dot product of the direction with the gradient
The direction of steepest descent is the negative gradient |
| Stanford CS231n 10th Anniversary Lecture 3 - 36 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 33
---


current W:
gradient dW:
[0.34,
[?,
-1.11,
?,
0.78,
?,
0.12,
?,
0.55,
?,
2.81,
?,
-3.1,
?,
-1.5,
?,
0.33,…]
?,…]
loss 1.25347
Stanford CS231n 10th Anniversary Lecture 3 - 37 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| current W:
gradient dW:
[0.34,
[?,
-1.11,
?,
0.78,
?,
0.12,
?,
0.55,
?,
2.81,
?,
-3.1,
?,
-1.5,
?,
0.33,…]
?,…]
loss 1.25347 |
| Stanford CS231n 10th Anniversary Lecture 3 - 37 April 8, 2025 |


---
## Page 34
---


current W: W + h (first dim):
gradient dW:
[0.34, [0.34 + 0.0001,
[?,
-1.11, -1.11,
?,
0.78, 0.78,
?,
0.12, 0.12,
?,
0.55, 0.55,
?,
2.81, 2.81,
?,
-3.1, -3.1,
?,
-1.5, -1.5,
?,
0.33,…] 0.33,…]
?,…]
loss 1.25347 loss 1.25322
Stanford CS231n 10th Anniversary Lecture 3 - 38 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| current W: W + h (first dim):
gradient dW:
[0.34, [0.34 + 0.0001,
[?,
-1.11, -1.11,
?,
0.78, 0.78,
?,
0.12, 0.12,
?,
0.55, 0.55,
?,
2.81, 2.81,
?,
-3.1, -3.1,
?,
-1.5, -1.5,
?,
0.33,…] 0.33,…]
?,…]
loss 1.25347 loss 1.25322 |
| Stanford CS231n 10th Anniversary Lecture 3 - 38 April 8, 2025 |


---
## Page 35
---


current W: W + h (first dim):
gradient dW:
[0.34, [0.34 + 0.0001,
[-2.5,
-1.11, -1.11,
?,
0.78, 0.78,
?,
0.12, 0.12,
?,
(1.25322 - 1.25347)/0.0001
0.55, 0.55,
= -2.5 ?,
2.81, 2.81,
?,
-3.1, -3.1,
?,
-1.5, -1.5,
?,
0.33,…] 0.33,…]
?,…]
loss 1.25347 loss 1.25322
Stanford CS231n 10th Anniversary Lecture 3 - 39 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| current W: W + h (first dim):
gradient dW:
[0.34, [0.34 + 0.0001,
[-2.5,
-1.11, -1.11,
?,
0.78, 0.78,
?,
0.12, 0.12,
?,
(1.25322 - 1.25347)/0.0001
0.55, 0.55,
= -2.5 ?,
2.81, 2.81,
?,
-3.1, -3.1,
?,
-1.5, -1.5,
?,
0.33,…] 0.33,…]
?,…]
loss 1.25347 loss 1.25322 |
| Stanford CS231n 10th Anniversary Lecture 3 - 39 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 36
---


current W: W + h (second dim):
gradient dW:
[0.34, [0.34,
[-2.5,
-1.11, -1.11 + 0.0001,
?,
0.78, 0.78,
?,
0.12, 0.12,
?,
0.55, 0.55,
?,
2.81, 2.81,
?,
-3.1, -3.1,
?,
-1.5, -1.5,
?,
0.33,…] 0.33,…]
?,…]
loss 1.25347 loss 1.25353
Stanford CS231n 10th Anniversary Lecture 3 - 40 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| current W: W + h (second dim):
gradient dW:
[0.34, [0.34,
[-2.5,
-1.11, -1.11 + 0.0001,
?,
0.78, 0.78,
?,
0.12, 0.12,
?,
0.55, 0.55,
?,
2.81, 2.81,
?,
-3.1, -3.1,
?,
-1.5, -1.5,
?,
0.33,…] 0.33,…]
?,…]
loss 1.25347 loss 1.25353 |
| Stanford CS231n 10th Anniversary Lecture 3 - 40 April 8, 2025 |


---
## Page 37
---


current W: W + h (second dim):
gradient dW:
[0.34, [0.34,
[-2.5,
-1.11, -1.11 + 0.0001,
0.6,
0.78, 0.78,
?,
0.12, 0.12,
?,
0.55, 0.55,
(1.2535?3,- 1.25347)/0.0001
2.81, 2.81, = 0.6
?,
-3.1, -3.1,
?,
-1.5, -1.5,
?,
0.33,…] 0.33,…]
?,…]
loss 1.25347 loss 1.25353
Stanford CS231n 10th Anniversary Lecture 3 - 41 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| current W: W + h (second dim):
gradient dW:
[0.34, [0.34,
[-2.5,
-1.11, -1.11 + 0.0001,
0.6,
0.78, 0.78,
?,
0.12, 0.12,
?,
0.55, 0.55,
(1.2535?3,- 1.25347)/0.0001
2.81, 2.81, = 0.6
?,
-3.1, -3.1,
?,
-1.5, -1.5,
?,
0.33,…] 0.33,…]
?,…]
loss 1.25347 loss 1.25353 |
| Stanford CS231n 10th Anniversary Lecture 3 - 41 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 38
---


current W: W + h (third dim):
gradient dW:
[0.34, [0.34,
[-2.5,
-1.11, -1.11,
0.6,
0.78, 0.78 + 0.0001,
?,
0.12, 0.12,
?,
0.55, 0.55,
?,
2.81, 2.81,
?,
-3.1, -3.1,
?,
-1.5, -1.5,
?,
0.33,…] 0.33,…]
?,…]
loss 1.25347 loss 1.25347
Stanford CS231n 10th Anniversary Lecture 3 - 42 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| current W: W + h (third dim):
gradient dW:
[0.34, [0.34,
[-2.5,
-1.11, -1.11,
0.6,
0.78, 0.78 + 0.0001,
?,
0.12, 0.12,
?,
0.55, 0.55,
?,
2.81, 2.81,
?,
-3.1, -3.1,
?,
-1.5, -1.5,
?,
0.33,…] 0.33,…]
?,…]
loss 1.25347 loss 1.25347 |
| Stanford CS231n 10th Anniversary Lecture 3 - 42 April 8, 2025 |


---
## Page 39
---


current W: W + h (third dim):
gradient dW:
[0.34, [0.34,
[-2.5,
-1.11, -1.11,
0.6,
0.78, 0.78 + 0.0001,
0,
0.12, 0.12,
?,
0.55, 0.55,
?,
(1.25347 - 1.25347)/0.0001
2.81, 2.81,
?,
= 0
-3.1, -3.1,
?,
-1.5, -1.5,
?,
0.33,…] 0.33,…]
?,…]
loss 1.25347 loss 1.25347
Stanford CS231n 10th Anniversary Lecture 3 - 43 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| current W: W + h (third dim):
gradient dW:
[0.34, [0.34,
[-2.5,
-1.11, -1.11,
0.6,
0.78, 0.78 + 0.0001,
0,
0.12, 0.12,
?,
0.55, 0.55,
?,
(1.25347 - 1.25347)/0.0001
2.81, 2.81,
?,
= 0
-3.1, -3.1,
?,
-1.5, -1.5,
?,
0.33,…] 0.33,…]
?,…]
loss 1.25347 loss 1.25347 |
| Stanford CS231n 10th Anniversary Lecture 3 - 43 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 40
---


current W: W + h (third dim):
gradient dW:
[0.34, [0.34,
[-2.5,
-1.11, -1.11,
0.6,
0.78, 0.78 + 0.0001,
0,
0.12, 0.12,
?,
0.55, 0.55,
?,
Numeric Gradient
2.81, 2.81,
?,
- Slow! Need to loop over
-3.1, -3.1,
?,
all dimensions
-1.5, -1.5, - App?ro, ximate
0.33,…] 0.33,…]
?,…]
loss 1.25347 loss 1.25347
Stanford CS231n 10th Anniversary Lecture 3 - 44 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| current W: W + h (third dim):
gradient dW:
[0.34, [0.34,
[-2.5,
-1.11, -1.11,
0.6,
0.78, 0.78 + 0.0001,
0,
0.12, 0.12,
?,
0.55, 0.55,
?,
Numeric Gradient
2.81, 2.81,
?,
- Slow! Need to loop over
-3.1, -3.1,
?,
all dimensions
-1.5, -1.5, - App?ro, ximate
0.33,…] 0.33,…]
?,…]
loss 1.25347 loss 1.25347 |
| Stanford CS231n 10th Anniversary Lecture 3 - 44 April 8, 2025 |


---
## Page 41
---


This is silly. The loss is just a function of W:
want
Stanford CS231n 10th Anniversary Lecture 3 - 45 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| This is silly. The loss is just a function of W:
want |
| Stanford CS231n 10th Anniversary Lecture 3 - 45 April 8, 2025 |


[Page contains 4 image(s)]


---
## Page 42
---


This is silly. The loss is just a function of W:
want
Use calculus to compute an
analytic gradient
This imageis in the public This imageis in the public
domain domain
Stanford CS231n 10th Anniversary Lecture 3 - 46 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| This is silly. The loss is just a function of W:
want
Use calculus to compute an
analytic gradient
This imageis in the public This imageis in the public
domain domain |
| Stanford CS231n 10th Anniversary Lecture 3 - 46 April 8, 2025 |


[Page contains 6 image(s)]


---
## Page 43
---


current W:
gradient dW:
[0.34,
[-2.5,
dW = ...
-1.11,
0.6,
(some function
0.78,
0,
data and W)
0.12,
0.2,
0.55,
0.7,
2.81,
-0.5,
-3.1,
1.1,
-1.5,
1.3,
0.33,…]
-2.1,…]
loss 1.25347
Stanford CS231n 10th Anniversary Lecture 3 - 47 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| current W:
gradient dW:
[0.34,
[-2.5,
dW = ...
-1.11,
0.6,
(some function
0.78,
0,
data and W)
0.12,
0.2,
0.55,
0.7,
2.81,
-0.5,
-3.1,
1.1,
-1.5,
1.3,
0.33,…]
-2.1,…]
loss 1.25347 |
| Stanford CS231n 10th Anniversary Lecture 3 - 47 April 8, 2025 |


---
## Page 44
---


In summary:
- Numerical gradient: approximate, slow, easy to write
- Analytic gradient: exact, fast, error-prone
=>
In practice: Always use analytic gradient, but check
implementation with numerical gradient. This is called a
gradient check.
Stanford CS231n 10th Anniversary Lecture 3 - 48 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| In summary:
- Numerical gradient: approximate, slow, easy to write
- Analytic gradient: exact, fast, error-prone
=>
In practice: Always use analytic gradient, but check
implementation with numerical gradient. This is called a
gradient check. |
| Stanford CS231n 10th Anniversary Lecture 3 - 48 April 8, 2025 |


---
## Page 45
---


Gradient Descent
Stanford CS231n 10th Anniversary Lecture 3 - 49 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Gradient Descent |
| Stanford CS231n 10th Anniversary Lecture 3 - 49 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 46
---


W_2
original W
W_1
negative gradient direction
Stanford CS231n 10th Anniversary Lecture 3 - 50 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| W_2
original W
W_1
negative gradient direction |
| Stanford CS231n 10th Anniversary Lecture 3 - 50 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 47
---


Stanford CS231n 10th Anniversary Lecture 3 - 51 April 8, 2025

[Page contains 1 table(s)]


### Table 1

|  |
| Stanford CS231n 10th Anniversary Lecture 3 - 51 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 48
---


Stochastic Gradient Descent (SGD)
Full sum expensive
when N is large!
Approximate sum
using a minibatch of
examples
32 / 64 / 128 common
Stanford CS231n 10th Anniversary Lecture 3 - 52 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Stochastic Gradient Descent (SGD)
Full sum expensive
when N is large!
Approximate sum
using a minibatch of
examples
32 / 64 / 128 common |
| Stanford CS231n 10th Anniversary Lecture 3 - 52 April 8, 2025 |


[Page contains 3 image(s)]


---
## Page 49
---


Optimization: Problem #1 with SGD
What if loss changes quickly in one direction and slowly in another?
What does gradient descent do?
w2
w1
Stanford CS231n 10th Anniversary Lecture 3 - 53 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Optimization: Problem #1 with SGD
What if loss changes quickly in one direction and slowly in another?
What does gradient descent do?
w2
w1 |
| Stanford CS231n 10th Anniversary Lecture 3 - 53 April 8, 2025 |


---
## Page 50
---


Optimization: Problem #1 with SGD
What if loss changes quickly in one direction and slowly in another?
What does gradient descent do?
Very slow progress along shallow dimension, jitter along steep direction
w2
w1
Stanford CS231n 10th Anniversary Lecture 3 - 54 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Optimization: Problem #1 with SGD
What if loss changes quickly in one direction and slowly in another?
What does gradient descent do?
Very slow progress along shallow dimension, jitter along steep direction
w2
w1 |
| Stanford CS231n 10th Anniversary Lecture 3 - 54 April 8, 2025 |


---
## Page 51
---


Optimization: Problem #1 with SGD
What if loss changes quickly in one direction and slowly in another?
What does gradient descent do?
Very slow progress along shallow dimension, jitter along steep direction
w2
w1
Aside: Loss function has high condition number: ratio of largest to
smallest singular value of the Hessian matrix is large
Stanford CS231n 10th Anniversary Lecture 3 - 55 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Optimization: Problem #1 with SGD
What if loss changes quickly in one direction and slowly in another?
What does gradient descent do?
Very slow progress along shallow dimension, jitter along steep direction
w2
w1
Aside: Loss function has high condition number: ratio of largest to
smallest singular value of the Hessian matrix is large |
| Stanford CS231n 10th Anniversary Lecture 3 - 55 April 8, 2025 |


---
## Page 52
---


Optimization: Problem #2 with SGD
s
s
What if the loss
o
l
function has a
local minima or
saddle point?
w
Stanford CS231n 10th Anniversary Lecture 3 - 56 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Optimization: Problem #2 with SGD
s
s
What if the loss
o
l
function has a
local minima or
saddle point?
w |
| Stanford CS231n 10th Anniversary Lecture 3 - 56 April 8, 2025 |


---
## Page 53
---


Optimization: Problem #2 with SGD
s
s
What if the loss
o
l
function has a
local minima or
saddle point?
Zero gradient,
gradient descent
gets stuck
w
Stanford CS231n 10th Anniversary Lecture 3 - 57 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Optimization: Problem #2 with SGD
s
s
What if the loss
o
l
function has a
local minima or
saddle point?
Zero gradient,
gradient descent
gets stuck
w |
| Stanford CS231n 10th Anniversary Lecture 3 - 57 April 8, 2025 |


---
## Page 54
---


Optimization: Problem #2 with SGD
What if the loss
function has a
local minima or
saddle point?
Saddle points much
more common in
high dimension
Dauphin et al, “Identifying and attacking the saddle point problem in high-dimensional non-convex optimization”, NIPS 2014
Stanford CS231n 10th Anniversary Lecture 3 - 58 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Optimization: Problem #2 with SGD
What if the loss
function has a
local minima or
saddle point?
Saddle points much
more common in
high dimension
Dauphin et al, “Identifying and attacking the saddle point problem in high-dimensional non-convex optimization”, NIPS 2014 |
| Stanford CS231n 10th Anniversary Lecture 3 - 58 April 8, 2025 |


---
## Page 55
---


Optimization: Problem #2 with SGD
saddle point in two dimension
Imagesource:https://en.wikipedia.org/wiki/Saddle_point
Stanford CS231n 10th Anniversary Lecture 3 - 59 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Optimization: Problem #2 with SGD
saddle point in two dimension
Imagesource:https://en.wikipedia.org/wiki/Saddle_point |
| Stanford CS231n 10th Anniversary Lecture 3 - 59 April 8, 2025 |


[Page contains 3 image(s)]


---
## Page 56
---


Optimization: Problem #3 with SGD
Our gradients come from
minibatches so they can be noisy!
Stanford CS231n 10th Anniversary Lecture 3 - 60 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Optimization: Problem #3 with SGD
Our gradients come from
minibatches so they can be noisy! |
| Stanford CS231n 10th Anniversary Lecture 3 - 60 April 8, 2025 |


[Page contains 4 image(s)]


---
## Page 57
---


SGD + Momentum
Gradient Noise
Local Minima Saddle points
Poor Conditioning
SGD SGD+Momentum
Stanford CS231n 10th Anniversary Lecture 3 - 61 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| SGD + Momentum
Gradient Noise
Local Minima Saddle points
Poor Conditioning
SGD SGD+Momentum |
| Stanford CS231n 10th Anniversary Lecture 3 - 61 April 8, 2025 |


[Page contains 2 image(s)]


---
## Page 58
---


SGD: the simple two line update code
SGD
Stanford CS231n 10th Anniversary Lecture 3 - 62 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| SGD: the simple two line update code
SGD |
| Stanford CS231n 10th Anniversary Lecture 3 - 62 April 8, 2025 |


[Page contains 2 image(s)]


---
## Page 59
---


SGD + Momentum:
continue moving in the general direction as the previous iterations
SGD SGD+Momentum
- Build up “velocity” as a running mean of gradients
- Rho gives “friction”; typically rho=0.9 or 0.99
Sutskever et al, “On the importance of initialization and momentum in deep learning”, ICML 2013
Stanford CS231n 10th Anniversary Lecture 3 - 63 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| SGD + Momentum:
continue moving in the general direction as the previous iterations
SGD SGD+Momentum
- Build up “velocity” as a running mean of gradients
- Rho gives “friction”; typically rho=0.9 or 0.99
Sutskever et al, “On the importance of initialization and momentum in deep learning”, ICML 2013 |
| Stanford CS231n 10th Anniversary Lecture 3 - 63 April 8, 2025 |


[Page contains 3 image(s)]


---
## Page 60
---


SGD + Momentum:
continue moving in the general direction as the previous iterations
SGD SGD+Momentum
- Build up “velocity” as a running mean of gradients
- Rho gives “momentum”; typically rho=0.9 or 0.99
Sutskever et al, “On the importance of initialization and momentum in deep learning”, ICML 2013
Stanford CS231n 10th Anniversary Lecture 3 - 64 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| SGD + Momentum:
continue moving in the general direction as the previous iterations
SGD SGD+Momentum
- Build up “velocity” as a running mean of gradients
- Rho gives “momentum”; typically rho=0.9 or 0.99
Sutskever et al, “On the importance of initialization and momentum in deep learning”, ICML 2013 |
| Stanford CS231n 10th Anniversary Lecture 3 - 64 April 8, 2025 |


[Page contains 4 image(s)]


---
## Page 61
---


SGD + Momentum:
alternative equivalent formulation
SGD+Momentum SGD+Momentum
You may see SGD+Momentum formulated different ways,
but they are equivalent - give same sequence of x
Sutskever et al, “On the importance of initialization and momentum in deep learning”, ICML 2013
Stanford CS231n 10th Anniversary Lecture 3 - 65 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| SGD + Momentum:
alternative equivalent formulation
SGD+Momentum SGD+Momentum
You may see SGD+Momentum formulated different ways,
but they are equivalent - give same sequence of x
Sutskever et al, “On the importance of initialization and momentum in deep learning”, ICML 2013 |
| Stanford CS231n 10th Anniversary Lecture 3 - 65 April 8, 2025 |


[Page contains 4 image(s)]


---
## Page 62
---


More Complex Optimizers: RMSProp
Adds element-wise scaling of the
SGD +
gradient based on the historical sum of
Momentum squares in each dimension (with decay)
RMSProp
Tieleman and Hinton, 2012
Stanford CS231n 10th Anniversary Lecture 3 - 66 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| More Complex Optimizers: RMSProp
Adds element-wise scaling of the
SGD +
gradient based on the historical sum of
Momentum squares in each dimension (with decay)
RMSProp
Tieleman and Hinton, 2012 |
| Stanford CS231n 10th Anniversary Lecture 3 - 66 April 8, 2025 |


[Page contains 2 image(s)]


---
## Page 63
---


More Complex Optimizers: RMSProp
“Per-parameter learning rates”
SGD +
or “adaptive learning rates”
Momentum
RMSProp
Tieleman and Hinton, 2012
Stanford CS231n 10th Anniversary Lecture 3 - 67 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| More Complex Optimizers: RMSProp
“Per-parameter learning rates”
SGD +
or “adaptive learning rates”
Momentum
RMSProp
Tieleman and Hinton, 2012 |
| Stanford CS231n 10th Anniversary Lecture 3 - 67 April 8, 2025 |


[Page contains 2 image(s)]


---
## Page 64
---


RMSProp
RMSProp
Q: What happens with RMSProp?
Tieleman and Hinton, 2012
Stanford CS231n 10th Anniversary Lecture 3 - 68 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| RMSProp
RMSProp
Q: What happens with RMSProp?
Tieleman and Hinton, 2012 |
| Stanford CS231n 10th Anniversary Lecture 3 - 68 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 65
---


RMSProp
RMSProp
Q: What happens with RMSProp? Progress along “steep” directions is damped;
progress along “flat” directions is accelerated
Tieleman and Hinton, 2012
Stanford CS231n 10th Anniversary Lecture 3 - 69 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| RMSProp
RMSProp
Q: What happens with RMSProp? Progress along “steep” directions is damped;
progress along “flat” directions is accelerated
Tieleman and Hinton, 2012 |
| Stanford CS231n 10th Anniversary Lecture 3 - 69 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 66
---


RMSProp
SGD
SGD+Momentum
RMSProp
Stanford CS231n 10th Anniversary Lecture 3 - 70 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| RMSProp
SGD
SGD+Momentum
RMSProp |
| Stanford CS231n 10th Anniversary Lecture 3 - 70 April 8, 2025 |


[Page contains 2 image(s)]


---
## Page 67
---


Optimizers: Adam (almost)
Kingma and Ba, “Adam: A method for stochastic optimization”, ICLR 2015
Stanford CS231n 10th Anniversary Lecture 3 - 71 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Optimizers: Adam (almost)
Kingma and Ba, “Adam: A method for stochastic optimization”, ICLR 2015 |
| Stanford CS231n 10th Anniversary Lecture 3 - 71 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 68
---


Adam (almost)
Momentum
RMSProp
Sort of like RMSProp with momentum
Q: What happens at first timestep?
Kingma and Ba, “Adam: A method for stochastic optimization”, ICLR 2015
Stanford CS231n 10th Anniversary Lecture 3 - 72 April 8, 2025

[Page contains 2 table(s)]


### Table 1

| Adam (almost)
Momentum
RMSProp
Sort of like RMSProp with momentum
Q: What happens at first timestep?
Kingma and Ba, “Adam: A method for stochastic optimization”, ICLR 2015 |
| Stanford CS231n 10th Anniversary Lecture 3 - 72 April 8, 2025 |


### Table 2

|  |
|  |


[Page contains 1 image(s)]


---
## Page 69
---


Adam (full form)
Momentum
Bias correction
AdaGrad / RMSProp
Bias correction for the fact that
first and second moment
estimates start at zero
Kingma and Ba, “Adam: A method for stochastic optimization”, ICLR 2015
Stanford CS231n 10th Anniversary Lecture 3 - 73 April 8, 2025

[Page contains 2 table(s)]


### Table 1

| Adam (full form)
Momentum
Bias correction
AdaGrad / RMSProp
Bias correction for the fact that
first and second moment
estimates start at zero
Kingma and Ba, “Adam: A method for stochastic optimization”, ICLR 2015 |
| Stanford CS231n 10th Anniversary Lecture 3 - 73 April 8, 2025 |


### Table 2

|  |
|  |
|  |


[Page contains 2 image(s)]


---
## Page 70
---


Adam (full form)
Momentum
Bias correction
AdaGrad / RMSProp
Bias correction for the fact that
Adam with beta1 = 0.9,
first and second moment
beta2 = 0.999, and learning_rate = 1e-3 or 5e-4
estimates start at zero
is a great starting point for many models!
Kingma and Ba, “Adam: A method for stochastic optimization”, ICLR 2015
Stanford CS231n 10th Anniversary Lecture 3 - 74 April 8, 2025

[Page contains 2 table(s)]


### Table 1

| Adam (full form)
Momentum
Bias correction
AdaGrad / RMSProp
Bias correction for the fact that
Adam with beta1 = 0.9,
first and second moment
beta2 = 0.999, and learning_rate = 1e-3 or 5e-4
estimates start at zero
is a great starting point for many models!
Kingma and Ba, “Adam: A method for stochastic optimization”, ICLR 2015 |
| Stanford CS231n 10th Anniversary Lecture 3 - 74 April 8, 2025 |


### Table 2

|  |
|  |
|  |


[Page contains 1 image(s)]


---
## Page 71
---


Adam
SGD
SGD+Momentum
RMSProp
Adam
Stanford CS231n 10th Anniversary Lecture 3 - 75 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Adam
SGD
SGD+Momentum
RMSProp
Adam |
| Stanford CS231n 10th Anniversary Lecture 3 - 75 April 8, 2025 |


[Page contains 2 image(s)]


---
## Page 72
---


AdamW: Adam Variant with Weight Decay
Q: How does regularization interact
with the optimizer? (e.g., L2)
Stanford CS231n 10th Anniversary Lecture 3 - 76 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| AdamW: Adam Variant with Weight Decay
Q: How does regularization interact
with the optimizer? (e.g., L2) |
| Stanford CS231n 10th Anniversary Lecture 3 - 76 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 73
---


AdamW: Adam Variant with Weight Decay
Q: How does regularization interact
with the optimizer? (e.g., L2)
A: It depends!
Stanford CS231n 10th Anniversary Lecture 3 - 77 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| AdamW: Adam Variant with Weight Decay
Q: How does regularization interact
with the optimizer? (e.g., L2)
A: It depends! |
| Stanford CS231n 10th Anniversary Lecture 3 - 77 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 74
---


AdamW: Adam Variant with Weight Decay
Q: How does regularization interact
with the optimizer? (e.g., L2)
Standard Adam computes L2 here
Used during moment
calculations!
Stanford CS231n 10th Anniversary Lecture 3 - 78 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| AdamW: Adam Variant with Weight Decay
Q: How does regularization interact
with the optimizer? (e.g., L2)
Standard Adam computes L2 here
Used during moment
calculations! |
| Stanford CS231n 10th Anniversary Lecture 3 - 78 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 75
---


AdamW: Adam Variant with Weight Decay
Q: How does regularization interact
with the optimizer? (e.g., L2)
Computed after the
moments!
AdamW(Weight Decay) adds term here
Stanford CS231n 10th Anniversary Lecture 3 - 79 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| AdamW: Adam Variant with Weight Decay
Q: How does regularization interact
with the optimizer? (e.g., L2)
Computed after the
moments!
AdamW(Weight Decay) adds term here |
| Stanford CS231n 10th Anniversary Lecture 3 - 79 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 76
---


AdamW: Adam Variant with Weight Decay
Q: How does regularization interact
with the optimizer? (e.g., L2)
y
c
a
r
u
Standard Adam computes L2 here c
c
A
t
e
N
e
g
a
m
I
Training Epoch
Source: https://www.fast.ai/posts/2018-07-02-
AdamW(Weight Decay) adds term here
adam-weight-decay.html
Stanford CS231n 10th Anniversary Lecture 3 - 80 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| AdamW: Adam Variant with Weight Decay
Q: How does regularization interact
with the optimizer? (e.g., L2)
y
c
a
r
u
Standard Adam computes L2 here c
c
A
t
e
N
e
g
a
m
I
Training Epoch
Source: https://www.fast.ai/posts/2018-07-02-
AdamW(Weight Decay) adds term here
adam-weight-decay.html |
| Stanford CS231n 10th Anniversary Lecture 3 - 80 April 8, 2025 |


[Page contains 2 image(s)]


---
## Page 77
---


Learning rate schedules
Learning rate
Stanford CS231n 10th Anniversary Lecture 3 - 81 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Learning rate schedules
Learning rate |
| Stanford CS231n 10th Anniversary Lecture 3 - 81 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 78
---


SGD, SGD+Momentum, RMSProp, Adam, AdamW all have
learning rate as a hyperparameter.
Q: Which one of these learning
rates is best to use?
Stanford CS231n 10th Anniversary Lecture 3 - 82 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| SGD, SGD+Momentum, RMSProp, Adam, AdamW all have
learning rate as a hyperparameter.
Q: Which one of these learning
rates is best to use? |
| Stanford CS231n 10th Anniversary Lecture 3 - 82 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 79
---


SGD, SGD+Momentum, RMSProp, Adam, AdamW all have
learning rate as a hyperparameter.
Q: Which one of these learning
rates is best to use?
A: In reality, all of these could be
good learning rates.
Stanford CS231n 10th Anniversary Lecture 3 - 83 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| SGD, SGD+Momentum, RMSProp, Adam, AdamW all have
learning rate as a hyperparameter.
Q: Which one of these learning
rates is best to use?
A: In reality, all of these could be
good learning rates. |
| Stanford CS231n 10th Anniversary Lecture 3 - 83 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 80
---


Learning rate decays over time
Step: Reduce learning rate at a few fixed
Reduce learning rate points. E.g. for ResNets, multiply LR by 0.1
after epochs 30, 60, and 90.
Stanford CS231n 10th Anniversary Lecture 3 - 84 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Learning rate decays over time
Step: Reduce learning rate at a few fixed
Reduce learning rate points. E.g. for ResNets, multiply LR by 0.1
after epochs 30, 60, and 90. |
| Stanford CS231n 10th Anniversary Lecture 3 - 84 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 81
---


Learning Rate Decay
Step: Reduce learning rate at a few fixed
points. E.g. for ResNets, multiply LR by 0.1
after epochs 30, 60, and 90.
Cosine:
: Initial learning rate
Loshchilov and Hutter, “SGDR: Stochastic Gradient Descent with Warm Restarts”, ICLR 2017
: Learning rate at epoch t
Radford et al, “Improving Language Understanding by Generative Pre-Training”, 2018
Feichtenhofer et al, “SlowFast Networks for Video Recognition”, arXiv 2018 : Total number of epochs
Child at al, “Generating Long Sequences with Sparse Transformers”, arXiv 2019
Stanford CS231n 10th Anniversary Lecture 3 - 85 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Learning Rate Decay
Step: Reduce learning rate at a few fixed
points. E.g. for ResNets, multiply LR by 0.1
after epochs 30, 60, and 90.
Cosine:
: Initial learning rate
Loshchilov and Hutter, “SGDR: Stochastic Gradient Descent with Warm Restarts”, ICLR 2017
: Learning rate at epoch t
Radford et al, “Improving Language Understanding by Generative Pre-Training”, 2018
Feichtenhofer et al, “SlowFast Networks for Video Recognition”, arXiv 2018 : Total number of epochs
Child at al, “Generating Long Sequences with Sparse Transformers”, arXiv 2019 |
| Stanford CS231n 10th Anniversary Lecture 3 - 85 April 8, 2025 |


[Page contains 5 image(s)]


---
## Page 82
---


Learning Rate Decay
Step: Reduce learning rate at a few fixed
points. E.g. for ResNets, multiply LR by 0.1
after epochs 30, 60, and 90.
Cosine:
: Initial learning rate
Loshchilov and Hutter, “SGDR: Stochastic Gradient Descent with Warm Restarts”, ICLR 2017
: Learning rate at epoch t
Radford et al, “Improving Language Understanding by Generative Pre-Training”, 2018
Feichtenhofer et al, “SlowFast Networks for Video Recognition”, arXiv 2018 : Total number of epochs
Child at al, “Generating Long Sequences with Sparse Transformers”, arXiv 2019
Stanford CS231n 10th Anniversary Lecture 3 - 86 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Learning Rate Decay
Step: Reduce learning rate at a few fixed
points. E.g. for ResNets, multiply LR by 0.1
after epochs 30, 60, and 90.
Cosine:
: Initial learning rate
Loshchilov and Hutter, “SGDR: Stochastic Gradient Descent with Warm Restarts”, ICLR 2017
: Learning rate at epoch t
Radford et al, “Improving Language Understanding by Generative Pre-Training”, 2018
Feichtenhofer et al, “SlowFast Networks for Video Recognition”, arXiv 2018 : Total number of epochs
Child at al, “Generating Long Sequences with Sparse Transformers”, arXiv 2019 |
| Stanford CS231n 10th Anniversary Lecture 3 - 86 April 8, 2025 |


[Page contains 5 image(s)]


---
## Page 83
---


Learning Rate Decay
Step: Reduce learning rate at a few fixed
points. E.g. for ResNets, multiply LR by 0.1
after epochs 30, 60, and 90.
Cosine:
Linear:
: Initial learning rate
: Learning rate at epoch t
: Total number of epochs
Devlin et al, “BERT: Pre-training of Deep Bidirectional Transformers for
Language Understanding”, 2018
Stanford CS231n 10th Anniversary Lecture 3 - 87 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Learning Rate Decay
Step: Reduce learning rate at a few fixed
points. E.g. for ResNets, multiply LR by 0.1
after epochs 30, 60, and 90.
Cosine:
Linear:
: Initial learning rate
: Learning rate at epoch t
: Total number of epochs
Devlin et al, “BERT: Pre-training of Deep Bidirectional Transformers for
Language Understanding”, 2018 |
| Stanford CS231n 10th Anniversary Lecture 3 - 87 April 8, 2025 |


[Page contains 6 image(s)]


---
## Page 84
---


Learning Rate Decay
Step: Reduce learning rate at a few fixed
points. E.g. for ResNets, multiply LR by 0.1
after epochs 30, 60, and 90.
Cosine:
Linear:
Inverse sqrt:
: Initial learning rate
: Learning rate at epoch t
: Total number of epochs
Vaswani et al, “Attention is all you need”, NIPS 2017
Stanford CS231n 10th Anniversary Lecture 3 - 88 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Learning Rate Decay
Step: Reduce learning rate at a few fixed
points. E.g. for ResNets, multiply LR by 0.1
after epochs 30, 60, and 90.
Cosine:
Linear:
Inverse sqrt:
: Initial learning rate
: Learning rate at epoch t
: Total number of epochs
Vaswani et al, “Attention is all you need”, NIPS 2017 |
| Stanford CS231n 10th Anniversary Lecture 3 - 88 April 8, 2025 |


[Page contains 7 image(s)]


---
## Page 85
---


Learning Rate Decay: Linear Warmup
High initial learning rates can make loss
explode; linearly increasing learning rate
from 0 over the first ~5,000 iterations can
prevent this.
Empirical rule of thumb: If you increase the
batch size by N, also scale the initial
learning rate by N
Goyal et al, “Accurate, Large Minibatch SGD: Training ImageNet in 1 Hour”, arXiv 2017
Stanford CS231n 10th Anniversary Lecture 3 - 89 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Learning Rate Decay: Linear Warmup
High initial learning rates can make loss
explode; linearly increasing learning rate
from 0 over the first ~5,000 iterations can
prevent this.
Empirical rule of thumb: If you increase the
batch size by N, also scale the initial
learning rate by N
Goyal et al, “Accurate, Large Minibatch SGD: Training ImageNet in 1 Hour”, arXiv 2017 |
| Stanford CS231n 10th Anniversary Lecture 3 - 89 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 86
---


First-Order Optimization
Loss
w1
Stanford CS231n 10th Anniversary Lecture 3 - 90 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| First-Order Optimization
Loss
w1 |
| Stanford CS231n 10th Anniversary Lecture 3 - 90 April 8, 2025 |


---
## Page 87
---


First-Order Optimization
(1) Use gradient form linear approximation
(2) Step to minimize the approximation
Loss
w1
Stanford CS231n 10th Anniversary Lecture 3 - 91 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| First-Order Optimization
(1) Use gradient form linear approximation
(2) Step to minimize the approximation
Loss
w1 |
| Stanford CS231n 10th Anniversary Lecture 3 - 91 April 8, 2025 |


---
## Page 88
---


Second-Order Optimization
(1) Use gradient and Hessian to form quadratic approximation
(2) Step to the minima of the approximation
Loss
w1
Stanford CS231n 10th Anniversary Lecture 3 - 92 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Second-Order Optimization
(1) Use gradient and Hessian to form quadratic approximation
(2) Step to the minima of the approximation
Loss
w1 |
| Stanford CS231n 10th Anniversary Lecture 3 - 92 April 8, 2025 |


---
## Page 89
---


Second-Order Optimization
second-order Taylor expansion:
Solving for the critical point we obtain the Newton parameter update:
Q: Why is this bad for deep learning?
Stanford CS231n 10th Anniversary Lecture 3 - 93 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Second-Order Optimization
second-order Taylor expansion:
Solving for the critical point we obtain the Newton parameter update:
Q: Why is this bad for deep learning? |
| Stanford CS231n 10th Anniversary Lecture 3 - 93 April 8, 2025 |


[Page contains 2 image(s)]


---
## Page 90
---


Second-Order Optimization
second-order Taylor expansion:
Solving for the critical point we obtain the Newton parameter update:
Hessian has O(N^2) elements
Inverting takes O(N^3)
N = (Tens or Hundreds of) Millions
Q: Why is this bad for deep learning?
Stanford CS231n 10th Anniversary Lecture 3 - 94 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Second-Order Optimization
second-order Taylor expansion:
Solving for the critical point we obtain the Newton parameter update:
Hessian has O(N^2) elements
Inverting takes O(N^3)
N = (Tens or Hundreds of) Millions
Q: Why is this bad for deep learning? |
| Stanford CS231n 10th Anniversary Lecture 3 - 94 April 8, 2025 |


[Page contains 2 image(s)]


---
## Page 91
---


In practice:
- Adam(W) is a good default choice in many cases; it
often works ok even with constant learning rate
- SGD+Momentum can outperform Adam but may
require more tuning of LR and schedule
- If you can afford to do full batch updates then look
beyond 1st order optimization (2nd order and
beyond)
Stanford CS231n 10th Anniversary Lecture 3 - 95 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| In practice:
- Adam(W) is a good default choice in many cases; it
often works ok even with constant learning rate
- SGD+Momentum can outperform Adam but may
require more tuning of LR and schedule
- If you can afford to do full batch updates then look
beyond 1st order optimization (2nd order and
beyond) |
| Stanford CS231n 10th Anniversary Lecture 3 - 95 April 8, 2025 |


---
## Page 92
---


Looking Ahead: How to optimize more complex
functions?
(Currently) Linear score function:
Stanford CS231n 10th Anniversary Lecture 3 - April 8, 2025
96

[Page contains 1 table(s)]


### Table 1

| Looking Ahead: How to optimize more complex
functions?
(Currently) Linear score function: |
| Stanford CS231n 10th Anniversary Lecture 3 - April 8, 2025
96 |


[Page contains 2 image(s)]


---
## Page 93
---


Neural networks: 2 layers
(Currently) Linear score function:
(Next Class) 2-layer Neural Network
(In practice we will usually add a learnable bias at each layer as well)
Stanford CS231n 10th Anniversary Lecture 3 - April 8, 2025
97

[Page contains 1 table(s)]


### Table 1

| Neural networks: 2 layers
(Currently) Linear score function:
(Next Class) 2-layer Neural Network
(In practice we will usually add a learnable bias at each layer as well) |
| Stanford CS231n 10th Anniversary Lecture 3 - April 8, 2025
97 |


[Page contains 3 image(s)]


---
## Page 94
---


Why do we want non-linearity?
y
x
Cannot separate red and
blue points with linear
classifier
Stanford CS231n 10th Anniversary Lecture 3 - April 8, 2025
98

[Page contains 1 table(s)]


### Table 1

| Why do we want non-linearity?
y
x
Cannot separate red and
blue points with linear
classifier |
| Stanford CS231n 10th Anniversary Lecture 3 - April 8, 2025
98 |


---
## Page 95
---


Why do we want non-linearity?
y θ
f(x, y) = (r(x, y), θ(x, y))
x
r
Cannot separate red and After applying feature
blue points with linear transform, points can be
classifier separated by linear
classifier
Stanford CS231n 10th Anniversary Lecture 3 - April 8, 2025
99

[Page contains 1 table(s)]


### Table 1

| Why do we want non-linearity?
y θ
f(x, y) = (r(x, y), θ(x, y))
x
r
Cannot separate red and After applying feature
blue points with linear transform, points can be
classifier separated by linear
classifier |
| Stanford CS231n 10th Anniversary Lecture 3 - April 8, 2025
99 |


---
## Page 96
---


Neural networks: also called fully connected network
(Currently) Linear score function:
(Next Class) 2-layer Neural Network
“Neural Network” is a very broad term; these are more accurately called
“fully-connected networks” or sometimes “multi-layer perceptrons” (MLP)
(In practice we will usually add a learnable bias at each layer as well)
Stanford CS231n 10th Anniversary Lecture 3 - April 8, 2025
100

[Page contains 1 table(s)]


### Table 1

| Neural networks: also called fully connected network
(Currently) Linear score function:
(Next Class) 2-layer Neural Network
“Neural Network” is a very broad term; these are more accurately called
“fully-connected networks” or sometimes “multi-layer perceptrons” (MLP)
(In practice we will usually add a learnable bias at each layer as well) |
| Stanford CS231n 10th Anniversary Lecture 3 - April 8, 2025
100 |


[Page contains 3 image(s)]


---
## Page 97
---


Next time:
Introduction to neural networks
Backpropagation (How do you calculate dx for neural nets?)
Stanford CS231n 10th Anniversary Lecture 3 - 101 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Next time:
Introduction to neural networks
Backpropagation (How do you calculate dx for neural nets?) |
| Stanford CS231n 10th Anniversary Lecture 3 - 101 April 8, 2025 |


---
## Page 98
---


Appendix (Slides from Previous Years)
Stanford CS231n 10th Anniversary Lecture 3 - 102 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Appendix (Slides from Previous Years) |
| Stanford CS231n 10th Anniversary Lecture 3 - 102 April 8, 2025 |


---
## Page 99
---


SGD+Momentum
Momentum update:
Velocity
actual step
Gradient
Combine gradient at current point with
velocity to get step used to update weights
Nesterov, “A method of solving a convex programming problem with convergence rate O(1/k^2)”, 1983
Nesterov, “Introductory lectures on convex optimization: a basic course”, 2004
Sutskever et al, “On the importance of initialization and momentum in deep learning”, ICML 2013
Stanford CS231n 10th Anniversary Lecture 3 - 103 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| SGD+Momentum
Momentum update:
Velocity
actual step
Gradient
Combine gradient at current point with
velocity to get step used to update weights
Nesterov, “A method of solving a convex programming problem with convergence rate O(1/k^2)”, 1983
Nesterov, “Introductory lectures on convex optimization: a basic course”, 2004
Sutskever et al, “On the importance of initialization and momentum in deep learning”, ICML 2013 |
| Stanford CS231n 10th Anniversary Lecture 3 - 103 April 8, 2025 |


---
## Page 100
---


Nesterov Momentum
Momentum update:
Nesterov Momentum
Gradient
Velocity
Velocity
actual step
actual step
Gradient
Combine gradient at current point with “Look ahead” to the point where updating using
velocity to get step used to update weights velocity would take us; compute gradient there and
mix it with velocity to get actual update direction
Nesterov, “A method of solving a convex programming problem with convergence rate O(1/k^2)”, 1983
Nesterov, “Introductory lectures on convex optimization: a basic course”, 2004
Sutskever et al, “On the importance of initialization and momentum in deep learning”, ICML 2013
Stanford CS231n 10th Anniversary Lecture 3 - 104 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Nesterov Momentum
Momentum update:
Nesterov Momentum
Gradient
Velocity
Velocity
actual step
actual step
Gradient
Combine gradient at current point with “Look ahead” to the point where updating using
velocity to get step used to update weights velocity would take us; compute gradient there and
mix it with velocity to get actual update direction
Nesterov, “A method of solving a convex programming problem with convergence rate O(1/k^2)”, 1983
Nesterov, “Introductory lectures on convex optimization: a basic course”, 2004
Sutskever et al, “On the importance of initialization and momentum in deep learning”, ICML 2013 |
| Stanford CS231n 10th Anniversary Lecture 3 - 104 April 8, 2025 |


---
## Page 101
---


Nesterov Momentum
Gradient
Velocity
actual step
“Look ahead” to the point where updating using
velocity would take us; compute gradient there and
mix it with velocity to get actual update direction
Stanford CS231n 10th Anniversary Lecture 3 - 105 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Nesterov Momentum
Gradient
Velocity
actual step
“Look ahead” to the point where updating using
velocity would take us; compute gradient there and
mix it with velocity to get actual update direction |
| Stanford CS231n 10th Anniversary Lecture 3 - 105 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 102
---


Nesterov Momentum
Annoying, usually we want
update in terms of
Gradient
Velocity
actual step
“Look ahead” to the point where updating using
velocity would take us; compute gradient there and
mix it with velocity to get actual update direction
Stanford CS231n 10th Anniversary Lecture 3 - 106 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Nesterov Momentum
Annoying, usually we want
update in terms of
Gradient
Velocity
actual step
“Look ahead” to the point where updating using
velocity would take us; compute gradient there and
mix it with velocity to get actual update direction |
| Stanford CS231n 10th Anniversary Lecture 3 - 106 April 8, 2025 |


[Page contains 2 image(s)]


---
## Page 103
---


Nesterov Momentum
Annoying, usually we want
update in terms of
Gradient
Velocity
Change of variables and
actual step
rearrange:
“Look ahead” to the point where updating using
velocity would take us; compute gradient there and
mix it with velocity to get actual update direction
https://cs231n.github.io/neural-networks-3/
Stanford CS231n 10th Anniversary Lecture 3 - 107 April 8, 2025

[Page contains 2 table(s)]


### Table 1

| Nesterov Momentum
Annoying, usually we want
update in terms of
Gradient
Velocity
Change of variables and
actual step
rearrange:
“Look ahead” to the point where updating using
velocity would take us; compute gradient there and
mix it with velocity to get actual update direction
https://cs231n.github.io/neural-networks-3/ |
| Stanford CS231n 10th Anniversary Lecture 3 - 107 April 8, 2025 |


### Table 2

|  |  |  |


[Page contains 3 image(s)]


---
## Page 104
---


Nesterov Momentum
Annoying, usually we want
update in terms of
Gradient
Velocity
Change of variables and
actual step
rearrange:
“Look ahead” to the point where updating using
velocity would take us; compute gradient there and
mix it with velocity to get actual update direction
https://cs231n.github.io/neural-networks-3/
Stanford CS231n 10th Anniversary Lecture 3 - 108 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Nesterov Momentum
Annoying, usually we want
update in terms of
Gradient
Velocity
Change of variables and
actual step
rearrange:
“Look ahead” to the point where updating using
velocity would take us; compute gradient there and
mix it with velocity to get actual update direction
https://cs231n.github.io/neural-networks-3/ |
| Stanford CS231n 10th Anniversary Lecture 3 - 108 April 8, 2025 |


[Page contains 4 image(s)]


---
## Page 105
---


Nesterov Momentum
SGD
SGD+Momentum
Nesterov
Stanford CS231n 10th Anniversary Lecture 3 - 109 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Nesterov Momentum
SGD
SGD+Momentum
Nesterov |
| Stanford CS231n 10th Anniversary Lecture 3 - 109 April 8, 2025 |


[Page contains 2 image(s)]


---
## Page 106
---


AdaGrad
Added element-wise scaling of the gradient based
on the historical sum of squares in each dimension
“Per-parameter learning rates”
or “adaptive learning rates”
Duchi et al, “Adaptive subgradient methods for online learning and stochastic optimization”, JMLR 2011
Stanford CS231n 10th Anniversary Lecture 3 - 110 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| AdaGrad
Added element-wise scaling of the gradient based
on the historical sum of squares in each dimension
“Per-parameter learning rates”
or “adaptive learning rates”
Duchi et al, “Adaptive subgradient methods for online learning and stochastic optimization”, JMLR 2011 |
| Stanford CS231n 10th Anniversary Lecture 3 - 110 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 107
---


AdaGrad
Q: What happens with AdaGrad?
Stanford CS231n 10th Anniversary Lecture 3 - 111 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| AdaGrad
Q: What happens with AdaGrad? |
| Stanford CS231n 10th Anniversary Lecture 3 - 111 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 108
---


AdaGrad
Q: What happens with AdaGrad? Progress along “steep” directions is damped;
progress along “flat” directions is accelerated
Stanford CS231n 10th Anniversary Lecture 3 - 112 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| AdaGrad
Q: What happens with AdaGrad? Progress along “steep” directions is damped;
progress along “flat” directions is accelerated |
| Stanford CS231n 10th Anniversary Lecture 3 - 112 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 109
---


AdaGrad
Q2: What happens to the step size over long time?
Stanford CS231n 10th Anniversary Lecture 3 - 113 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| AdaGrad
Q2: What happens to the step size over long time? |
| Stanford CS231n 10th Anniversary Lecture 3 - 113 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 110
---


AdaGrad
Q2: What happens to the step size over long time?
Decays to zero
Stanford CS231n 10th Anniversary Lecture 3 - 114 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| AdaGrad
Q2: What happens to the step size over long time?
Decays to zero |
| Stanford CS231n 10th Anniversary Lecture 3 - 114 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 111
---


RMSProp: “Leaky AdaGrad”
AdaGrad
RMSProp
Tieleman and Hinton, 2012
Stanford CS231n 10th Anniversary Lecture 3 - 115 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| RMSProp: “Leaky AdaGrad”
AdaGrad
RMSProp
Tieleman and Hinton, 2012 |
| Stanford CS231n 10th Anniversary Lecture 3 - 115 April 8, 2025 |


[Page contains 2 image(s)]


---
## Page 112
---


Second-Order Optimization
- Quasi-Newton methods (BGFS most popular):
instead of inverting the Hessian (O(n^3)), approximate
inverse Hessian with rank 1 updates over time (O(n^2)
each).
- L-BFGS (Limited memory BFGS):
Does not form/store the full inverse Hessian.
Stanford CS231n 10th Anniversary Lecture 3 - 116 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Second-Order Optimization
- Quasi-Newton methods (BGFS most popular):
instead of inverting the Hessian (O(n^3)), approximate
inverse Hessian with rank 1 updates over time (O(n^2)
each).
- L-BFGS (Limited memory BFGS):
Does not form/store the full inverse Hessian. |
| Stanford CS231n 10th Anniversary Lecture 3 - 116 April 8, 2025 |


[Page contains 1 image(s)]


---
## Page 113
---


L-BFGS
- Usually works very well in full batch, deterministic mode
i.e. if you have a single, deterministic f(x) then L-BFGS will
probably work very nicely
- Does not transfer very well to mini-batch setting. Gives
bad results. Adapting second-order methods to large-scale,
stochastic setting is an active area of research.
Le et al, “On optimization methods for deep learning, ICML 2011”
Ba et al, “Distributed second-order optimization using Kronecker-factored approximations”, ICLR 2017
Stanford CS231n 10th Anniversary Lecture 3 - 117 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| L-BFGS
- Usually works very well in full batch, deterministic mode
i.e. if you have a single, deterministic f(x) then L-BFGS will
probably work very nicely
- Does not transfer very well to mini-batch setting. Gives
bad results. Adapting second-order methods to large-scale,
stochastic setting is an active area of research.
Le et al, “On optimization methods for deep learning, ICML 2011”
Ba et al, “Distributed second-order optimization using Kronecker-factored approximations”, ICLR 2017 |
| Stanford CS231n 10th Anniversary Lecture 3 - 117 April 8, 2025 |


---
## Page 114
---


In practice:
- Adam is a good default choice in many cases; it
often works ok even with constant learning rate
- SGD+Momentum can outperform Adam but may
require more tuning of LR and schedule
- If you can afford to do full batch updates then try out
L-BFGS
(and don’t forget to disable all sources of noise)
Stanford CS231n 10th Anniversary Lecture 3 - 118 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| In practice:
- Adam is a good default choice in many cases; it
often works ok even with constant learning rate
- SGD+Momentum can outperform Adam but may
require more tuning of LR and schedule
- If you can afford to do full batch updates then try out
L-BFGS
(and don’t forget to disable all sources of noise) |
| Stanford CS231n 10th Anniversary Lecture 3 - 118 April 8, 2025 |


---
## Page 115
---


vs.
SSooffttmmaaxx vvss.. SSVVMM
Stanford CS231n 10th Anniversary Lecture 3 - 119 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| vs.
SSooffttmmaaxx vvss.. SSVVMM |
| Stanford CS231n 10th Anniversary Lecture 3 - 119 April 8, 2025 |


[Page contains 3 image(s)]


---
## Page 116
---


Q: Suppose that we found a W such that L = 0.
Is this W unique?
Stanford CS231n 10th Anniversary Lecture 3 - 120 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Q: Suppose that we found a W such that L = 0.
Is this W unique? |
| Stanford CS231n 10th Anniversary Lecture 3 - 120 April 8, 2025 |


[Page contains 2 image(s)]


---
## Page 117
---


Q: Suppose that we found a W such that L = 0.
Is this W unique?
No! 2W is also has L = 0!
Stanford CS231n 10th Anniversary Lecture 3 - 121 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| Q: Suppose that we found a W such that L = 0.
Is this W unique?
No! 2W is also has L = 0! |
| Stanford CS231n 10th Anniversary Lecture 3 - 121 April 8, 2025 |


[Page contains 2 image(s)]


---
## Page 118
---


Suppose: 3 training examples, 3 classes.
With some W the scores are:
Before:
= max(0, 1.3 - 4.9 + 1)
+max(0, 2.0 - 4.9 + 1)
= max(0, -2.6) + max(0, -1.9)
= 0 + 0
= 0
cat 3.2 1.3 2.2
With W twice as large:
= max(0, 2.6 - 9.8 + 1)
5.1 4.9 2.5
car
+max(0, 4.0 - 9.8 + 1)
= max(0, -6.2) + max(0, -4.8)
-1.7 2.0 -3.1
frog
= 0 + 0
2.9 0 = 0
Losses:
Stanford CS231n 10th Anniversary Lecture 3 - 122 April 8, 2025

[Page contains 2 table(s)]


### Table 1

| Suppose: 3 training examples, 3 classes.
With some W the scores are:
Before:
= max(0, 1.3 - 4.9 + 1)
+max(0, 2.0 - 4.9 + 1)
= max(0, -2.6) + max(0, -1.9)
= 0 + 0
= 0
cat 3.2 1.3 2.2
With W twice as large:
= max(0, 2.6 - 9.8 + 1)
5.1 4.9 2.5
car
+max(0, 4.0 - 9.8 + 1)
= max(0, -6.2) + max(0, -4.8)
-1.7 2.0 -3.1
frog
= 0 + 0
2.9 0 = 0
Losses: |
| Stanford CS231n 10th Anniversary Lecture 3 - 122 April 8, 2025 |


### Table 2

| 1.3
4.9
2.0 |
| 0 |


[Page contains 5 image(s)]


---
## Page 119
---


E.g. Suppose that we found a W such that L = 0.
Is this W unique?
No! 2W is also has L = 0!
How do we choose between W and 2W?
Stanford CS231n 10th Anniversary Lecture 3 - 123 April 8, 2025

[Page contains 1 table(s)]


### Table 1

| E.g. Suppose that we found a W such that L = 0.
Is this W unique?
No! 2W is also has L = 0!
How do we choose between W and 2W? |
| Stanford CS231n 10th Anniversary Lecture 3 - 123 April 8, 2025 |


[Page contains 2 image(s)]
