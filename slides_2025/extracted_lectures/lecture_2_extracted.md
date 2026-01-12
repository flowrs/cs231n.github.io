# lecture_2

Extracted using pdfplumber



---
## Page 1
---


Lecture 2:
Image Classification with Linear Classifiers
Stanford CS231n 10th Anniversary Lecture 2 - 1 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture 2:
Image Classification with Linear Classifiers |
| Stanford CS231n 10th Anniversary Lecture 2 - 1 April 3, 2025 |


---
## Page 2
---


Administrative: Assignment 1
Will be out Wednesday 4/9, due 4/23 by 11:59 PM
- K-Nearest Neighbor
- Linear classifiers: Softmax
- Two-layer neural network
- Image features
- Deep neural network and optimizers
Stanford CS231n 10th Anniversary Lecture 2 - 2 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Administrative: Assignment 1
Will be out Wednesday 4/9, due 4/23 by 11:59 PM
- K-Nearest Neighbor
- Linear classifiers: Softmax
- Two-layer neural network
- Image features
- Deep neural network and optimizers |
| Stanford CS231n 10th Anniversary Lecture 2 - 2 April 3, 2025 |


---
## Page 3
---


Administrative: Course Project
Project proposal due 4/25 (Friday) 11:59 pm
Contact us on Ed, each project team will have a TA assigned to them for future
questions
your assigned TA for initial guidance (Canvas -> People -> Groups)
Use the Google Form to find project partners (will be posted later today)
“Is X a valid project for 231n?” --- Ed private post / TA Office Hours
More info on the website
Stanford CS231n 10th Anniversary Lecture 2 - 3 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Administrative: Course Project
Project proposal due 4/25 (Friday) 11:59 pm
Contact us on Ed, each project team will have a TA assigned to them for future
questions
your assigned TA for initial guidance (Canvas -> People -> Groups)
Use the Google Form to find project partners (will be posted later today)
“Is X a valid project for 231n?” --- Ed private post / TA Office Hours
More info on the website |
| Stanford CS231n 10th Anniversary Lecture 2 - 3 April 3, 2025 |


---
## Page 4
---


Administrative: Discussion Sections
This Friday 12:30 pm-1:20 pm, in person at NVIDIA Auditorium, remote on Zoom
(recording will be made available)
Python / Numpy, Google Colab
Presenter: Emily Jin (TA) with Assistance from Matthew Jin (TA)
Stanford CS231n 10th Anniversary Lecture 2 - 4 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Administrative: Discussion Sections
This Friday 12:30 pm-1:20 pm, in person at NVIDIA Auditorium, remote on Zoom
(recording will be made available)
Python / Numpy, Google Colab
Presenter: Emily Jin (TA) with Assistance from Matthew Jin (TA) |
| Stanford CS231n 10th Anniversary Lecture 2 - 4 April 3, 2025 |


---
## Page 5
---


Syllabus
Perceiving and Understanding Reconstructing and Interacting
Deep Learning Basics the Visual World with the Visual World
Data-driven approaches Transfer Learning Style Transfer
Linear classification Optimizers GenerativeModels
K-Nearest Neighbor Convolutions Self-supervised Learning
Loss Functions PyTorch Image Generation
Optimization RNNs / Attention / Transformers Robotics and Embodied AI
Backpropagation Normalization Layers
Multi-layer Perceptrons Architecture Design
Neural Networks Video Understanding
Activation Functions Vision and Language Human-centered AI
Data Augmentation 3D Vision Fairness & Ethics
ObjectDetectionandSegmentation
Stanford CS231n 10th Anniversary Lecture 2 - 5 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Syllabus
Perceiving and Understanding Reconstructing and Interacting
Deep Learning Basics the Visual World with the Visual World
Data-driven approaches Transfer Learning Style Transfer
Linear classification Optimizers GenerativeModels
K-Nearest Neighbor Convolutions Self-supervised Learning
Loss Functions PyTorch Image Generation
Optimization RNNs / Attention / Transformers Robotics and Embodied AI
Backpropagation Normalization Layers
Multi-layer Perceptrons Architecture Design
Neural Networks Video Understanding
Activation Functions Vision and Language Human-centered AI
Data Augmentation 3D Vision Fairness & Ethics
ObjectDetectionandSegmentation |
| Stanford CS231n 10th Anniversary Lecture 2 - 5 April 3, 2025 |


---
## Page 6
---


Image Classification
A Core Task in Computer Vision
Today:
● The image classification task
● Two basic data-driven approaches to image classification
○ K-nearest neighbor and linear classifier
Stanford CS231n 10th Anniversary Lecture 2 - 6 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Image Classification
A Core Task in Computer Vision
Today:
● The image classification task
● Two basic data-driven approaches to image classification
○ K-nearest neighbor and linear classifier |
| Stanford CS231n 10th Anniversary Lecture 2 - 6 April 3, 2025 |


---
## Page 7
---


Image Classification: A core task in Computer Vision
(assume given a set of possible labels)
{dog, cat, truck, plane, ...}
cat
This imageby Nikitais
licensed under CC-BY 2.0
Stanford CS231n 10th Anniversary Lecture 2 - 7 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Image Classification: A core task in Computer Vision
(assume given a set of possible labels)
{dog, cat, truck, plane, ...}
cat
This imageby Nikitais
licensed under CC-BY 2.0 |
| Stanford CS231n 10th Anniversary Lecture 2 - 7 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 8
---


The Problem: Semantic Gap
What the computer sees
An image is a tensor of integers
between [0, 255]:
This imageby Nikitais e.g. 800 x 600 x 3
licensed under CC-BY 2.0
(3 channels RGB)
Stanford CS231n 10th Anniversary Lecture 2 - 8 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| The Problem: Semantic Gap
What the computer sees
An image is a tensor of integers
between [0, 255]:
This imageby Nikitais e.g. 800 x 600 x 3
licensed under CC-BY 2.0
(3 channels RGB) |
| Stanford CS231n 10th Anniversary Lecture 2 - 8 April 3, 2025 |


[Page contains 2 image(s)]


---
## Page 9
---


Challenges: Viewpoint variation
All pixels change when
the camera moves!
This imageby Nikitais
licensed under CC-BY 2.0
Stanford CS231n 10th Anniversary Lecture 2 - 9 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Challenges: Viewpoint variation
All pixels change when
the camera moves!
This imageby Nikitais
licensed under CC-BY 2.0 |
| Stanford CS231n 10th Anniversary Lecture 2 - 9 April 3, 2025 |


[Page contains 2 image(s)]


---
## Page 10
---


Challenges: Illumination
This imageis CC0 1.0public domain This image is CC0 1.0public domain This image is CC0 1.0public domain This imageis CC0 1.0public domain
Stanford CS231n 10th Anniversary Lecture 2 - 10 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Challenges: Illumination
This imageis CC0 1.0public domain This image is CC0 1.0public domain This image is CC0 1.0public domain This imageis CC0 1.0public domain |
| Stanford CS231n 10th Anniversary Lecture 2 - 10 April 3, 2025 |


[Page contains 4 image(s)]


---
## Page 11
---


Challenges: Background Clutter
This imageis CC0 1.0public domain This imageis CC0 1.0public domain
Stanford CS231n 10th Anniversary Lecture 2 - 11 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Challenges: Background Clutter
This imageis CC0 1.0public domain This imageis CC0 1.0public domain |
| Stanford CS231n 10th Anniversary Lecture 2 - 11 April 3, 2025 |


[Page contains 2 image(s)]


---
## Page 12
---


Challenges: Occlusion
This imageby jonssonis licensed
This imageis CC0 1.0public domain This imageis CC0 1.0public domain
under CC-BY 2.0
Stanford CS231n 10th Anniversary Lecture 2 - 12 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Challenges: Occlusion
This imageby jonssonis licensed
This imageis CC0 1.0public domain This imageis CC0 1.0public domain
under CC-BY 2.0 |
| Stanford CS231n 10th Anniversary Lecture 2 - 12 April 3, 2025 |


[Page contains 3 image(s)]


---
## Page 13
---


Challenges: Deformation
This imageby Umberto Salvagninis This imageby Umberto Salvagninis This imageby sare bearis This imageby Tom Thai is licensed
licensed under CC-BY 2.0 licensed under CC-BY 2.0 licensed under CC-BY 2.0 under CC-BY 2.0
Stanford CS231n 10th Anniversary Lecture 2 - 13 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Challenges: Deformation
This imageby Umberto Salvagninis This imageby Umberto Salvagninis This imageby sare bearis This imageby Tom Thai is licensed
licensed under CC-BY 2.0 licensed under CC-BY 2.0 licensed under CC-BY 2.0 under CC-BY 2.0 |
| Stanford CS231n 10th Anniversary Lecture 2 - 13 April 3, 2025 |


[Page contains 4 image(s)]


---
## Page 14
---


Challenges: Intraclass variation
This imageis CC0 1.0public domain
Stanford CS231n 10th Anniversary Lecture 2 - 14 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Challenges: Intraclass variation
This imageis CC0 1.0public domain |
| Stanford CS231n 10th Anniversary Lecture 2 - 14 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 15
---


Challenges: Context
Imagesource:https://www.linkedin.com/posts/ralph-aboujaoude-diaz-40838313_technology-artificialintelligence-computervision-activity-
6912446088364875776-h-Iq?utm_source=linkedin_share&utm_medium=member_desktop_web
Stanford CS231n 10th Anniversary Lecture 2 - 15 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Challenges: Context
Imagesource:https://www.linkedin.com/posts/ralph-aboujaoude-diaz-40838313_technology-artificialintelligence-computervision-activity-
6912446088364875776-h-Iq?utm_source=linkedin_share&utm_medium=member_desktop_web |
| Stanford CS231n 10th Anniversary Lecture 2 - 15 April 3, 2025 |


[Page contains 2 image(s)]


---
## Page 16
---


Modern computer vision algorithms
This imageis CC0 1.0public domain
Stanford CS231n 10th Anniversary Lecture 2 - 16 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Modern computer vision algorithms
This imageis CC0 1.0public domain |
| Stanford CS231n 10th Anniversary Lecture 2 - 16 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 17
---


An image classifier
Unlike e.g. sorting a list of numbers,
no obvious way to hard-code the algorithm for
recognizing a cat, or other classes.
Stanford CS231n 10th Anniversary Lecture 2 - 17 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| An image classifier
Unlike e.g. sorting a list of numbers,
no obvious way to hard-code the algorithm for
recognizing a cat, or other classes. |
| Stanford CS231n 10th Anniversary Lecture 2 - 17 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 18
---


Attempts have been made
Find edges
Find corners
?
John Canny, “A Computational Approach to Edge Detection”, IEEE TPAMI 1986
Stanford CS231n 10th Anniversary Lecture 2 - 18 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Attempts have been made
Find edges
Find corners
?
John Canny, “A Computational Approach to Edge Detection”, IEEE TPAMI 1986 |
| Stanford CS231n 10th Anniversary Lecture 2 - 18 April 3, 2025 |


[Page contains 2 image(s)]


---
## Page 19
---


Machine Learning: Data-Driven Approach
1. Collect a dataset of images and labels
2. Use Machine Learning algorithms to train a classifier
3. Evaluate the classifier on new images
Example training set
Stanford CS231n 10th Anniversary Lecture 2 - 19 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Machine Learning: Data-Driven Approach
1. Collect a dataset of images and labels
2. Use Machine Learning algorithms to train a classifier
3. Evaluate the classifier on new images
Example training set |
| Stanford CS231n 10th Anniversary Lecture 2 - 19 April 3, 2025 |


[Page contains 3 image(s)]


---
## Page 20
---


Nearest Neighbor Classifier
Stanford CS231n 10th Anniversary Lecture 2 - 20 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Nearest Neighbor Classifier |
| Stanford CS231n 10th Anniversary Lecture 2 - 20 April 3, 2025 |


---
## Page 21
---


First classifier: Nearest Neighbor
Memorize all data
and labels
Predict the label of
the most similar
training image
Stanford CS231n 10th Anniversary Lecture 2 - 21 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| First classifier: Nearest Neighbor
Memorize all data
and labels
Predict the label of
the most similar
training image |
| Stanford CS231n 10th Anniversary Lecture 2 - 21 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 22
---


First classifier: Nearest Neighbor
?
deer bird plane cat car
Training data with labels
query data
Distance Metric
Stanford CS231n 10th Anniversary Lecture 2 - 22 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| First classifier: Nearest Neighbor
?
deer bird plane cat car
Training data with labels
query data
Distance Metric |
| Stanford CS231n 10th Anniversary Lecture 2 - 22 April 3, 2025 |


[Page contains 9 image(s)]


---
## Page 23
---


Distance Metric to compare images
L1 distance:
add
Stanford CS231n 10th Anniversary Lecture 2 - 23 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Distance Metric to compare images
L1 distance:
add |
| Stanford CS231n 10th Anniversary Lecture 2 - 23 April 3, 2025 |


[Page contains 2 image(s)]


---
## Page 24
---


Nearest Neighbor classifier
Stanford CS231n 10th Anniversary Lecture 2 - 24 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Nearest Neighbor classifier |
| Stanford CS231n 10th Anniversary Lecture 2 - 24 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 25
---


Nearest Neighbor classifier
Memorize training data
Stanford CS231n 10th Anniversary Lecture 2 - 25 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Nearest Neighbor classifier
Memorize training data |
| Stanford CS231n 10th Anniversary Lecture 2 - 25 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 26
---


Nearest Neighbor classifier
For each test image:
Find closest train image
Predict label of nearest image
Stanford CS231n 10th Anniversary Lecture 2 - 26 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Nearest Neighbor classifier
For each test image:
Find closest train image
Predict label of nearest image |
| Stanford CS231n 10th Anniversary Lecture 2 - 26 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 27
---


Nearest Neighbor classifier
Q: With N examples, how
fast are training and
prediction?
Ans: Train O(1),
predict O(N)
This is bad: we want
classifiers that are fast at
prediction; slow for
training is ok
Stanford CS231n 10th Anniversary Lecture 2 - 27 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Nearest Neighbor classifier
Q: With N examples, how
fast are training and
prediction?
Ans: Train O(1),
predict O(N)
This is bad: we want
classifiers that are fast at
prediction; slow for
training is ok |
| Stanford CS231n 10th Anniversary Lecture 2 - 27 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 28
---


Nearest Neighbor classifier
Many methods exist for fast /
approximate nearest
neighbor (beyond the scope
of 231N!)
A good implementation:
https://github.com/facebookresearch/faiss
Johnson et al, “Billion-scale similarity search with
GPUs”, arXiv2017
Stanford CS231n 10th Anniversary Lecture 2 - 28 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Nearest Neighbor classifier
Many methods exist for fast /
approximate nearest
neighbor (beyond the scope
of 231N!)
A good implementation:
https://github.com/facebookresearch/faiss
Johnson et al, “Billion-scale similarity search with
GPUs”, arXiv2017 |
| Stanford CS231n 10th Anniversary Lecture 2 - 28 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 29
---


What does this look like?
1-nearest neighbor
Stanford CS231n 10th Anniversary Lecture 2 - 29 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| What does this look like?
1-nearest neighbor |
| Stanford CS231n 10th Anniversary Lecture 2 - 29 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 30
---


K-Nearest Neighbors
Instead of copying label from nearest neighbor,
take majority vote from K closest points
K = 1 K = 3 K = 5
Stanford CS231n 10th Anniversary Lecture 2 - 30 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| K-Nearest Neighbors
Instead of copying label from nearest neighbor,
take majority vote from K closest points
K = 1 K = 3 K = 5 |
| Stanford CS231n 10th Anniversary Lecture 2 - 30 April 3, 2025 |


[Page contains 3 image(s)]


---
## Page 31
---


K-Nearest Neighbors: Distance Metric
L1 (Manhattan) distance L2 (Euclidean) distance
Stanford CS231n 10th Anniversary Lecture 2 - 31 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| K-Nearest Neighbors: Distance Metric
L1 (Manhattan) distance L2 (Euclidean) distance |
| Stanford CS231n 10th Anniversary Lecture 2 - 31 April 3, 2025 |


[Page contains 2 image(s)]


---
## Page 32
---


K-Nearest Neighbors: Distance Metric - Example
L1 Distance: Measures distance by moving along L2 Distance: Measures the straight-line
grid lines (like walking in a city with square blocks). distance (as the crow flies).
B(1/√2, 1/√2)
B(0.5, 0.5)
O(0,0)
A(1, 0)
O(0,0) A(1, 0)
d (O,A) = |0-1| + |0-0| = 1
1 d (O,A) = sqrt((0-1)2 + (0-0)2) = sqrt(12) = 1
2
d (O,B) = |0-0.5| + |0-0.5| = 0.5 + 0.5 = 1 d (O,B) = sqrt((0-1/√2)2 + (0-1/√2)2) = sqrt(1/2+1/2) = sqrt(1) = 1
1 2
d (O,A) = d (O,B) = 1 d (O,A) = d (O,A) = 1
1 1 2 2
Stanford CS231n 10th Anniversary Lecture 2 -33 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| K-Nearest Neighbors: Distance Metric - Example
L1 Distance: Measures distance by moving along L2 Distance: Measures the straight-line
grid lines (like walking in a city with square blocks). distance (as the crow flies).
B(1/√2, 1/√2)
B(0.5, 0.5)
O(0,0)
A(1, 0)
O(0,0) A(1, 0)
d (O,A) = |0-1| + |0-0| = 1
1 d (O,A) = sqrt((0-1)2 + (0-0)2) = sqrt(12) = 1
2
d (O,B) = |0-0.5| + |0-0.5| = 0.5 + 0.5 = 1 d (O,B) = sqrt((0-1/√2)2 + (0-1/√2)2) = sqrt(1/2+1/2) = sqrt(1) = 1
1 2
d (O,A) = d (O,B) = 1 d (O,A) = d (O,A) = 1
1 1 2 2 |
| Stanford CS231n 10th Anniversary Lecture 2 -33 April 3, 2025 |


[Page contains 2 image(s)]


---
## Page 33
---


K-Nearest Neighbors: Distance Metric
L1 (Manhattan) distance L2 (Euclidean) distance
K = 1 K = 1
Stanford CS231n 10th Anniversary Lecture 2 - 34 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| K-Nearest Neighbors: Distance Metric
L1 (Manhattan) distance L2 (Euclidean) distance
K = 1 K = 1 |
| Stanford CS231n 10th Anniversary Lecture 2 - 34 April 3, 2025 |


[Page contains 4 image(s)]


---
## Page 34
---


K-Nearest Neighbors: try it yourself!
http://vision.stanford.edu/teaching/cs231n-demos/knn/
Stanford CS231n 10th Anniversary Lecture 2 - 35 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| K-Nearest Neighbors: try it yourself!
http://vision.stanford.edu/teaching/cs231n-demos/knn/ |
| Stanford CS231n 10th Anniversary Lecture 2 - 35 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 35
---


Hyperparameters
What is the best value of k to use?
What is the best distance to use?
These are hyperparameters: choices about the
algorithms themselves.
Very problem/dataset-dependent.
Must try them all out and see what works best.
Stanford CS231n 10th Anniversary Lecture 2 - 36 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Hyperparameters
What is the best value of k to use?
What is the best distance to use?
These are hyperparameters: choices about the
algorithms themselves.
Very problem/dataset-dependent.
Must try them all out and see what works best. |
| Stanford CS231n 10th Anniversary Lecture 2 - 36 April 3, 2025 |


---
## Page 36
---


Setting Hyperparameters
Idea #1: Choose hyperparameters that
work best on the training data
train
Stanford CS231n 10th Anniversary Lecture 2 - 37 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Setting Hyperparameters
Idea #1: Choose hyperparameters that
work best on the training data
train |
| Stanford CS231n 10th Anniversary Lecture 2 - 37 April 3, 2025 |


---
## Page 37
---


Setting Hyperparameters
Idea #1: Choose hyperparameters that BAD: K = 1 always works
work best on the training data perfectly on training data
train
Stanford CS231n 10th Anniversary Lecture 2 - 38 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Setting Hyperparameters
Idea #1: Choose hyperparameters that BAD: K = 1 always works
work best on the training data perfectly on training data
train |
| Stanford CS231n 10th Anniversary Lecture 2 - 38 April 3, 2025 |


---
## Page 38
---


Setting Hyperparameters
Idea #1: Choose hyperparameters that BAD: K = 1 always works
work best on the training data perfectly on training data
train
Idea #2: choose hyperparameters
that work best on test data
train test
Stanford CS231n 10th Anniversary Lecture 2 - 39 April 3, 2025

[Page contains 2 table(s)]


### Table 1

| Setting Hyperparameters
Idea #1: Choose hyperparameters that BAD: K = 1 always works
work best on the training data perfectly on training data
train
Idea #2: choose hyperparameters
that work best on test data
train test |
| Stanford CS231n 10th Anniversary Lecture 2 - 39 April 3, 2025 |


### Table 2

| train | test |


---
## Page 39
---


Setting Hyperparameters
Idea #1: Choose hyperparameters that BAD: K = 1 always works
work best on the training data perfectly on training data
train
Idea #2: choose hyperparameters BAD: No idea how algorithm
that work best on test data will perform on new data
train test
Never do this!
Stanford CS231n 10th Anniversary Lecture 2 - 40 April 3, 2025

[Page contains 2 table(s)]


### Table 1

| Setting Hyperparameters
Idea #1: Choose hyperparameters that BAD: K = 1 always works
work best on the training data perfectly on training data
train
Idea #2: choose hyperparameters BAD: No idea how algorithm
that work best on test data will perform on new data
train test
Never do this! |
| Stanford CS231n 10th Anniversary Lecture 2 - 40 April 3, 2025 |


### Table 2

| train | test |


---
## Page 40
---


Setting Hyperparameters
Idea #1: Choose hyperparameters that BAD: K = 1 always works
work best on the training data perfectly on training data
train
Idea #2: choose hyperparameters BAD: No idea how algorithm
that work best on test data will perform on new data
train test
Idea #3: Split data into train, val; choose
Better!
hyperparameters on val and evaluate on test
train validation test
Stanford CS231n 10th Anniversary Lecture 2 - 41 April 3, 2025

[Page contains 3 table(s)]


### Table 1

| Setting Hyperparameters
Idea #1: Choose hyperparameters that BAD: K = 1 always works
work best on the training data perfectly on training data
train
Idea #2: choose hyperparameters BAD: No idea how algorithm
that work best on test data will perform on new data
train test
Idea #3: Split data into train, val; choose
Better!
hyperparameters on val and evaluate on test
train validation test |
| Stanford CS231n 10th Anniversary Lecture 2 - 41 April 3, 2025 |


### Table 2

| train | test |


### Table 3

| train | validation | test |


---
## Page 41
---


Setting Hyperparameters
train
Idea #4: Cross-Validation: Split data into folds, try
each fold as validation and average the results
fold 1 fold 2 fold 3 fold 4 fold 5
fold 1 fold 2 fold 3 fold 4 fold 5
fold 1 fold 2 fold 3 fold 4 fold 5 test
fold 1 fold 2 fold 3 fold 4 fold 5
fold 1 fold 2 fold 3 fold 4 fold 5
Useful for small datasets, but not used too frequently in deep learning
Stanford CS231n 10th Anniversary Lecture 2 - 42 April 3, 2025

[Page contains 2 table(s)]


### Table 1

| Setting Hyperparameters
train
Idea #4: Cross-Validation: Split data into folds, try
each fold as validation and average the results
fold 1 fold 2 fold 3 fold 4 fold 5
fold 1 fold 2 fold 3 fold 4 fold 5
fold 1 fold 2 fold 3 fold 4 fold 5 test
fold 1 fold 2 fold 3 fold 4 fold 5
fold 1 fold 2 fold 3 fold 4 fold 5
Useful for small datasets, but not used too frequently in deep learning |
| Stanford CS231n 10th Anniversary Lecture 2 - 42 April 3, 2025 |


### Table 2

| fold 1 | fold 2 | fold 3 | fold 4 | fold 5 |
| fold 1 | fold 2 | fold 3 | fold 4 | fold 5 |
| fold 1 | fold 2 | fold 3 | fold 4 | fold 5 |
| fold 1 | fold 2 | fold 3 | fold 4 | fold 5 |
| fold 1 | fold 2 | fold 3 | fold 4 | fold 5 |


---
## Page 42
---


Example Dataset: CIFAR10
10 classes
50,000 training images
10,000 testing images
Alex Krizhevsky, “Learning Multiple Layers of Features from Tiny Images”, Technical Report, 2009.
Stanford CS231n 10th Anniversary Lecture 2 - 43 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Example Dataset: CIFAR10
10 classes
50,000 training images
10,000 testing images
Alex Krizhevsky, “Learning Multiple Layers of Features from Tiny Images”, Technical Report, 2009. |
| Stanford CS231n 10th Anniversary Lecture 2 - 43 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 43
---


Example Dataset: CIFAR10
10 classes
50,000 training images
Test images and nearest neighbors
10,000 testing images
Alex Krizhevsky, “Learning Multiple Layers of Features from Tiny Images”, Technical Report, 2009.
Stanford CS231n 10th Anniversary Lecture 2 - 44 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Example Dataset: CIFAR10
10 classes
50,000 training images
Test images and nearest neighbors
10,000 testing images
Alex Krizhevsky, “Learning Multiple Layers of Features from Tiny Images”, Technical Report, 2009. |
| Stanford CS231n 10th Anniversary Lecture 2 - 44 April 3, 2025 |


[Page contains 2 image(s)]


---
## Page 44
---


Setting Hyperparameters
Example of
5-fold cross-validation
for the value of k.
Each point: single
outcome.
The line goes
through the mean, bars
indicated standard
deviation
(Seems that k ~= 7 works best
for this data)
Stanford CS231n 10th Anniversary Lecture 2 - 45 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Setting Hyperparameters
Example of
5-fold cross-validation
for the value of k.
Each point: single
outcome.
The line goes
through the mean, bars
indicated standard
deviation
(Seems that k ~= 7 works best
for this data) |
| Stanford CS231n 10th Anniversary Lecture 2 - 45 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 45
---


What does this look like?
Stanford CS231n 10th Anniversary Lecture 2 - 46 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| What does this look like? |
| Stanford CS231n 10th Anniversary Lecture 2 - 46 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 46
---


What does this look like?
Stanford CS231n 10th Anniversary Lecture 2 - 47 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| What does this look like? |
| Stanford CS231n 10th Anniversary Lecture 2 - 47 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 47
---


k-Nearest Neighbor with pixel distance never used.
- Distance metrics on pixels are not informative
Original Occluded Shifted (1 pixel) Tinted
Original imageis CC0
public domain
(All three images on the right have the same pixel distances to the one on the left)
Stanford CS231n 10th Anniversary Lecture 2 - 48 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| k-Nearest Neighbor with pixel distance never used.
- Distance metrics on pixels are not informative
Original Occluded Shifted (1 pixel) Tinted
Original imageis CC0
public domain
(All three images on the right have the same pixel distances to the one on the left) |
| Stanford CS231n 10th Anniversary Lecture 2 - 48 April 3, 2025 |


[Page contains 4 image(s)]


---
## Page 48
---


K-Nearest Neighbors: Summary
In image classification we start with a training set of images and labels, and must
predict labels on the test set
The K-Nearest Neighbors classifier predicts labels based on the K nearest training
examples
Distance metric and K are hyperparameters
Choose hyperparameters using the validation set
Only run on the test set once at the very end!
Stanford CS231n 10th Anniversary Lecture 2 - 50 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| K-Nearest Neighbors: Summary
In image classification we start with a training set of images and labels, and must
predict labels on the test set
The K-Nearest Neighbors classifier predicts labels based on the K nearest training
examples
Distance metric and K are hyperparameters
Choose hyperparameters using the validation set
Only run on the test set once at the very end! |
| Stanford CS231n 10th Anniversary Lecture 2 - 50 April 3, 2025 |


---
## Page 49
---


Linear Classifier
Stanford CS231n 10th Anniversary Lecture 2 - 51 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Linear Classifier |
| Stanford CS231n 10th Anniversary Lecture 2 - 51 April 3, 2025 |


---
## Page 50
---


Parametric Approach
Image
10 numbers giving
f(x,W)
class scores
Array of 32x32x3 numbers
(3072 numbers total) W
parameters
or weights
Stanford CS231n 10th Anniversary Lecture 2 - 52 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Parametric Approach
Image
10 numbers giving
f(x,W)
class scores
Array of 32x32x3 numbers
(3072 numbers total) W
parameters
or weights |
| Stanford CS231n 10th Anniversary Lecture 2 - 52 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 51
---


Parametric Approach: Linear Classifier
f(x,W) = W x
Image
10 numbers giving
f(x,W)
class scores
Array of 32x32x3 numbers
(3072 numbers total) W
parameters
or weights
Stanford CS231n 10th Anniversary Lecture 2 - 53 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Parametric Approach: Linear Classifier
f(x,W) = W x
Image
10 numbers giving
f(x,W)
class scores
Array of 32x32x3 numbers
(3072 numbers total) W
parameters
or weights |
| Stanford CS231n 10th Anniversary Lecture 2 - 53 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 52
---


Parametric Approach: Linear Classifier
3072x1
f(x,W) = W x
Image
10x1 10x3072
10 numbers giving
f(x,W)
class scores
Array of 32x32x3 numbers
(3072 numbers total) W
parameters
or weights
Stanford CS231n 10th Anniversary Lecture 2 - 54 April 3, 2025

[Page contains 2 table(s)]


### Table 1

| Parametric Approach: Linear Classifier
3072x1
f(x,W) = W x
Image
10x1 10x3072
10 numbers giving
f(x,W)
class scores
Array of 32x32x3 numbers
(3072 numbers total) W
parameters
or weights |
| Stanford CS231n 10th Anniversary Lecture 2 - 54 April 3, 2025 |


### Table 2

| W |  |
|  | x |


[Page contains 1 image(s)]


---
## Page 53
---


Parametric Approach: Linear Classifier
3072x1
f(x,W) = W x + b
10x1
Image
10x1 10x3072
10 numbers giving
f(x,W)
class scores
Array of 32x32x3 numbers
(3072 numbers total) W
parameters
or weights
Stanford CS231n 10th Anniversary Lecture 2 - 55 April 3, 2025

[Page contains 2 table(s)]


### Table 1

| Parametric Approach: Linear Classifier
3072x1
f(x,W) = W x + b
10x1
Image
10x1 10x3072
10 numbers giving
f(x,W)
class scores
Array of 32x32x3 numbers
(3072 numbers total) W
parameters
or weights |
| Stanford CS231n 10th Anniversary Lecture 2 - 55 April 3, 2025 |


### Table 2

| W |  |
|  | x |


[Page contains 1 image(s)]


---
## Page 54
---


Neural Network
Linear
classifiers
This imageis CC0 1.0 public domain
Stanford CS231n 10th Anniversary Lecture 2 - 56 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Neural Network
Linear
classifiers
This imageis CC0 1.0 public domain |
| Stanford CS231n 10th Anniversary Lecture 2 - 56 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 55
---


[Krizhevskyet al. 2012] Linear layers
[He et al. 2015]
Stanford CS231n 10th Anniversary Lecture 2 - 57 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| [Krizhevskyet al. 2012] Linear layers
[He et al. 2015] |
| Stanford CS231n 10th Anniversary Lecture 2 - 57 April 3, 2025 |


[Page contains 2 image(s)]


---
## Page 56
---


Recall CIFAR10
50,000 training images
each image is 32x32x3
10,000 test images.
Stanford CS231n 10th Anniversary Lecture 2 - 58 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Recall CIFAR10
50,000 training images
each image is 32x32x3
10,000 test images. |
| Stanford CS231n 10th Anniversary Lecture 2 - 58 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 57
---


Example with an image with 4 pixels, and 3 classes (cat/dog/ship)
Flatten tensors into a vector
56
56 231
231
24 2
24
Input image
2
Stanford CS231n 10th Anniversary Lecture 2 - 59 April 3, 2025

[Page contains 3 table(s)]


### Table 1

| Example with an image with 4 pixels, and 3 classes (cat/dog/ship)
Flatten tensors into a vector
56
56 231
231
24 2
24
Input image
2 |
| Stanford CS231n 10th Anniversary Lecture 2 - 59 April 3, 2025 |


### Table 2

| 56 |
| 231 |
| 24 |
| 2 |


### Table 3

| 56 | 231 |
| 24 | 2 |


[Page contains 1 image(s)]


---
## Page 58
---


Example with an image with 4 pixels, and 3 classes (cat/dog/ship)
Algebraic Viewpoint
Flatten tensors into a vector
56
0.2 -0.5 0.1 2.0 1.1 -96.8 Cat score
56 231
231
+ =
1.5 1.3 2.1 0.0 3.2 437.9
Dog score
24 2
24
0 0.25 0.2 -0.3 -1.2 61.95 Ship score
Input image
2
W b
Stanford CS231n 10th Anniversary Lecture 2 - 60 April 3, 2025

[Page contains 6 table(s)]


### Table 1

| Example with an image with 4 pixels, and 3 classes (cat/dog/ship)
Algebraic Viewpoint
Flatten tensors into a vector
56
0.2 -0.5 0.1 2.0 1.1 -96.8 Cat score
56 231
231
+ =
1.5 1.3 2.1 0.0 3.2 437.9
Dog score
24 2
24
0 0.25 0.2 -0.3 -1.2 61.95 Ship score
Input image
2
W b |
| Stanford CS231n 10th Anniversary Lecture 2 - 60 April 3, 2025 |


### Table 2

| 56 |
| 231 |
| 24 |
| 2 |


### Table 3

| 0.2 | -0.5 | 0.1 | 2.0 |
| 1.5 | 1.3 | 2.1 | 0.0 |
| 0 | 0.25 | 0.2 | -0.3 |


### Table 4

| 1.1 |
| 3.2 |
| -1.2 |


### Table 5

| -96.8 |
| 437.9 |
| 61.95 |


### Table 6

| 56 | 231 |
| 24 | 2 |


[Page contains 1 image(s)]


---
## Page 59
---


Interpreting a Linear Classifier
Stanford CS231n 10th Anniversary Lecture 2 - 61 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Interpreting a Linear Classifier |
| Stanford CS231n 10th Anniversary Lecture 2 - 61 April 3, 2025 |


[Page contains 2 image(s)]


---
## Page 60
---


Interpreting a Linear Classifier: Visual Viewpoint
Stanford CS231n 10th Anniversary Lecture 2 - 62 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Interpreting a Linear Classifier: Visual Viewpoint |
| Stanford CS231n 10th Anniversary Lecture 2 - 62 April 3, 2025 |


[Page contains 3 image(s)]


---
## Page 61
---


Interpreting a Linear Classifier: Geometric Viewpoint
f(x,W) = Wx + b
Array of 32x32x3 numbers
(3072 numbers total)
Plot created using Wolfram Cloud Cat imageby Nikitais licensed under CC-BY 2.0
Stanford CS231n 10th Anniversary Lecture 2 - 63 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Interpreting a Linear Classifier: Geometric Viewpoint
f(x,W) = Wx + b
Array of 32x32x3 numbers
(3072 numbers total)
Plot created using Wolfram Cloud Cat imageby Nikitais licensed under CC-BY 2.0 |
| Stanford CS231n 10th Anniversary Lecture 2 - 63 April 3, 2025 |


[Page contains 6 image(s)]


---
## Page 62
---


Hard cases for a linear classifier
Class 1: Class 1: Class 1:
First and third quadrants 1 <= L2 norm <= 2 Three modes
Class 2: Class 2:
Class 2:
Everything else Everything else
Second and fourth quadrants
Stanford CS231n 10th Anniversary Lecture 2 - 64 April 3, 2025

[Page contains 4 table(s)]


### Table 1

| Hard cases for a linear classifier
Class 1: Class 1: Class 1:
First and third quadrants 1 <= L2 norm <= 2 Three modes
Class 2: Class 2:
Class 2:
Everything else Everything else
Second and fourth quadrants |
| Stanford CS231n 10th Anniversary Lecture 2 - 64 April 3, 2025 |


### Table 2

|  |  |
|  |  |


### Table 3

|  |  |
|  |  |


### Table 4

|  |  |
|  |  |


---
## Page 63
---


Linear Classifier – Choose a good W
1. Define a loss function that quantifies
our unhappiness with the scores
across the training data.
2. Come up with a way of efficiently
finding the parameters that minimize
the loss function. (optimization)
Cat imageby Nikitais licensed under CC-BY 2.0; Car imageis CC0 1.0public domain; Frog imageis in the public domain
Stanford CS231n 10th Anniversary Lecture 2 - 65 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Linear Classifier – Choose a good W
1. Define a loss function that quantifies
our unhappiness with the scores
across the training data.
2. Come up with a way of efficiently
finding the parameters that minimize
the loss function. (optimization)
Cat imageby Nikitais licensed under CC-BY 2.0; Car imageis CC0 1.0public domain; Frog imageis in the public domain |
| Stanford CS231n 10th Anniversary Lecture 2 - 65 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 64
---


Suppose: 3 training examples, 3 classes.
With some W the scores are:
cat 3.2 1.3 2.2
5.1 4.9 2.5
car
-1.7 2.0 -3.1
frog
Stanford CS231n 10th Anniversary Lecture 2 - 66 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Suppose: 3 training examples, 3 classes.
With some W the scores are:
cat 3.2 1.3 2.2
5.1 4.9 2.5
car
-1.7 2.0 -3.1
frog |
| Stanford CS231n 10th Anniversary Lecture 2 - 66 April 3, 2025 |


[Page contains 4 image(s)]


---
## Page 65
---


Suppose: 3 training examples, 3 classes.
A loss function tells how good
With some W the scores are:
our current classifier is
cat 3.2 1.3 2.2
5.1 4.9 2.5
car
-1.7 2.0 -3.1
frog
Stanford CS231n 10th Anniversary Lecture 2 -67 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Suppose: 3 training examples, 3 classes.
A loss function tells how good
With some W the scores are:
our current classifier is
cat 3.2 1.3 2.2
5.1 4.9 2.5
car
-1.7 2.0 -3.1
frog |
| Stanford CS231n 10th Anniversary Lecture 2 -67 April 3, 2025 |


[Page contains 4 image(s)]


---
## Page 66
---


Suppose: 3 training examples, 3 classes.
A loss function tells how good
With some W the scores are:
our current classifier is
Given a dataset of examples
Where is image and
cat 3.2 1.3 2.2 is (integer) label
5.1 4.9 2.5
car
-1.7 2.0 -3.1
frog
Stanford CS231n 10th Anniversary Lecture 2 -68 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Suppose: 3 training examples, 3 classes.
A loss function tells how good
With some W the scores are:
our current classifier is
Given a dataset of examples
Where is image and
cat 3.2 1.3 2.2 is (integer) label
5.1 4.9 2.5
car
-1.7 2.0 -3.1
frog |
| Stanford CS231n 10th Anniversary Lecture 2 -68 April 3, 2025 |


[Page contains 7 image(s)]


---
## Page 67
---


Suppose: 3 training examples, 3 classes.
A loss function tells how good
With some W the scores are:
our current classifier is
Given a dataset of examples
Where is image and
cat 3.2 1.3 2.2 is (integer) label
5.1 4.9 2.5 Loss over the dataset is a average
car
of loss over examples:
-1.7 2.0 -3.1
frog
Stanford CS231n 10th Anniversary Lecture 2 -69 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Suppose: 3 training examples, 3 classes.
A loss function tells how good
With some W the scores are:
our current classifier is
Given a dataset of examples
Where is image and
cat 3.2 1.3 2.2 is (integer) label
5.1 4.9 2.5 Loss over the dataset is a average
car
of loss over examples:
-1.7 2.0 -3.1
frog |
| Stanford CS231n 10th Anniversary Lecture 2 -69 April 3, 2025 |


[Page contains 8 image(s)]


---
## Page 68
---


Softmax classifier
Stanford CS231n 10th Anniversary Lecture 2 - 70 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Softmax classifier |
| Stanford CS231n 10th Anniversary Lecture 2 - 70 April 3, 2025 |


---
## Page 69
---


Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
cat 3.2
5.1
car
-1.7
frog
Stanford CS231n 10th Anniversary Lecture 2 - 71 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
cat 3.2
5.1
car
-1.7
frog |
| Stanford CS231n 10th Anniversary Lecture 2 - 71 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 70
---


Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
cat 3.2
5.1
car
-1.7
frog
Stanford CS231n 10th Anniversary Lecture 2 - 72 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
cat 3.2
5.1
car
-1.7
frog |
| Stanford CS231n 10th Anniversary Lecture 2 - 72 April 3, 2025 |


[Page contains 3 image(s)]


---
## Page 71
---


Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
Probabilities
must be >= 0
cat 3.2 24.5
exp
5.1 164.0
car
-1.7 0.18
frog
unnormalized
probabilities
Stanford CS231n 10th Anniversary Lecture 2 - 73 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
Probabilities
must be >= 0
cat 3.2 24.5
exp
5.1 164.0
car
-1.7 0.18
frog
unnormalized
probabilities |
| Stanford CS231n 10th Anniversary Lecture 2 - 73 April 3, 2025 |


[Page contains 3 image(s)]


---
## Page 72
---


Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
Probabilities Probabilities
must be >= 0 must sum to 1
cat 3.2 24.5 0.13
exp
normalize
5.1 164.0 0.87
car
-1.7 0.18 0.00
frog
unnormalized probabilities
probabilities
Stanford CS231n 10th Anniversary Lecture 2 - 74 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
Probabilities Probabilities
must be >= 0 must sum to 1
cat 3.2 24.5 0.13
exp
normalize
5.1 164.0 0.87
car
-1.7 0.18 0.00
frog
unnormalized probabilities
probabilities |
| Stanford CS231n 10th Anniversary Lecture 2 - 74 April 3, 2025 |


[Page contains 3 image(s)]


---
## Page 73
---


Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
Probabilities Probabilities
must be >= 0 must sum to 1
cat 3.2 24.5 0.13
exp
normalize
5.1 164.0 0.87
car
-1.7 0.18 0.00
frog
Unnormalized log- unnormalized probabilities
probabilities / logits probabilities
Stanford CS231n 10th Anniversary Lecture 2 - 75 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
Probabilities Probabilities
must be >= 0 must sum to 1
cat 3.2 24.5 0.13
exp
normalize
5.1 164.0 0.87
car
-1.7 0.18 0.00
frog
Unnormalized log- unnormalized probabilities
probabilities / logits probabilities |
| Stanford CS231n 10th Anniversary Lecture 2 - 75 April 3, 2025 |


[Page contains 3 image(s)]


---
## Page 74
---


Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
Probabilities Probabilities
must be >= 0 must sum to 1
cat 3.2 24.5 0.13
L = -log(0.13)
i
exp = 2.04
normalize
5.1 164.0 0.87
car
-1.7 0.18 0.00
frog
Unnormalized log- unnormalized probabilities
probabilities / logits probabilities
Stanford CS231n 10th Anniversary Lecture 2 - 76 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
Probabilities Probabilities
must be >= 0 must sum to 1
cat 3.2 24.5 0.13
L = -log(0.13)
i
exp = 2.04
normalize
5.1 164.0 0.87
car
-1.7 0.18 0.00
frog
Unnormalized log- unnormalized probabilities
probabilities / logits probabilities |
| Stanford CS231n 10th Anniversary Lecture 2 - 76 April 3, 2025 |


[Page contains 4 image(s)]


---
## Page 75
---


Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
Probabilities Probabilities
must be >= 0 must sum to 1
cat 3.2 24.5 0.13
L = -log(0.13)
i
exp = 2.04
normalize
5.1 164.0 0.87
car
Maximum Likelihood Estimation
-1.7 0.18 0.00
frog Choose weights to maximize the
likelihood of the observed data
Unnormalized log- unnormalized probabilities (See CS 229 for details)
probabilities / logits probabilities
Stanford CS231n 10th Anniversary Lecture 2 - 77 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
Probabilities Probabilities
must be >= 0 must sum to 1
cat 3.2 24.5 0.13
L = -log(0.13)
i
exp = 2.04
normalize
5.1 164.0 0.87
car
Maximum Likelihood Estimation
-1.7 0.18 0.00
frog Choose weights to maximize the
likelihood of the observed data
Unnormalized log- unnormalized probabilities (See CS 229 for details)
probabilities / logits probabilities |
| Stanford CS231n 10th Anniversary Lecture 2 - 77 April 3, 2025 |


[Page contains 4 image(s)]


---
## Page 76
---


Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
Probabilities Probabilities
must be >= 0 must sum to 1
cat 3.2 24.5 0.13 compare 1.00
exp
normalize
5.1 164.0 0.87 0.00
car
-1.7 0.18 0.00 0.00
frog
Unnormalized log- unnormalized probabilities Correct
probabilities / logits probabilities
probs
Stanford CS231n 10th Anniversary Lecture 2 - 78 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
Probabilities Probabilities
must be >= 0 must sum to 1
cat 3.2 24.5 0.13 compare 1.00
exp
normalize
5.1 164.0 0.87 0.00
car
-1.7 0.18 0.00 0.00
frog
Unnormalized log- unnormalized probabilities Correct
probabilities / logits probabilities
probs |
| Stanford CS231n 10th Anniversary Lecture 2 - 78 April 3, 2025 |


[Page contains 4 image(s)]


---
## Page 77
---


Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
Probabilities Probabilities
must be >= 0 must sum to 1
cat 3.2 24.5 0.13 compare 1.00
exp
normalize Kullback–Leibler
5.1 164.0 0.87 0.00
car
divergence
-1.7 0.18 0.00 0.00
frog
Unnormalized log- unnormalized probabilities Correct
probabilities / logits probabilities
probs
Stanford CS231n 10th Anniversary Lecture 2 - 79 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
Probabilities Probabilities
must be >= 0 must sum to 1
cat 3.2 24.5 0.13 compare 1.00
exp
normalize Kullback–Leibler
5.1 164.0 0.87 0.00
car
divergence
-1.7 0.18 0.00 0.00
frog
Unnormalized log- unnormalized probabilities Correct
probabilities / logits probabilities
probs |
| Stanford CS231n 10th Anniversary Lecture 2 - 79 April 3, 2025 |


[Page contains 6 image(s)]


---
## Page 78
---


Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
Probabilities Probabilities
must be >= 0 must sum to 1
cat 3.2 24.5 0.13 compare 1.00
exp
normalize
5.1 164.0 0.87 0.00
car Cross Entropy
-1.7 0.18 0.00 0.00
frog
Unnormalized log- unnormalized probabilities Correct
probabilities / logits probabilities
probs
Stanford CS231n 10th Anniversary Lecture 2 - 80 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
Probabilities Probabilities
must be >= 0 must sum to 1
cat 3.2 24.5 0.13 compare 1.00
exp
normalize
5.1 164.0 0.87 0.00
car Cross Entropy
-1.7 0.18 0.00 0.00
frog
Unnormalized log- unnormalized probabilities Correct
probabilities / logits probabilities
probs |
| Stanford CS231n 10th Anniversary Lecture 2 - 80 April 3, 2025 |


[Page contains 6 image(s)]


---
## Page 79
---


Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
Maximize probability of correct class Putting it all together:
cat 3.2
5.1
car
-1.7
frog
Stanford CS231n 10th Anniversary Lecture 2 - 81 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
Maximize probability of correct class Putting it all together:
cat 3.2
5.1
car
-1.7
frog |
| Stanford CS231n 10th Anniversary Lecture 2 - 81 April 3, 2025 |


[Page contains 5 image(s)]


---
## Page 80
---


Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
Maximize probability of correct class Putting it all together:
cat 3.2
Q1: What is the min/max possible softmax loss L ?
car 5.1 i
-1.7 Q2: At initialization all s will be approximately equal;
frog j
what is the softmax loss L , assuming C classes?
i
Stanford CS231n 10th Anniversary Lecture 2 - 82 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
Maximize probability of correct class Putting it all together:
cat 3.2
Q1: What is the min/max possible softmax loss L ?
car 5.1 i
-1.7 Q2: At initialization all s will be approximately equal;
frog j
what is the softmax loss L , assuming C classes?
i |
| Stanford CS231n 10th Anniversary Lecture 2 - 82 April 3, 2025 |


[Page contains 5 image(s)]


---
## Page 81
---


Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
Maximize probability of correct class Putting it all together:
cat 3.2
Q2: At initialization all s will be
5.1
car
approximately equal; what is the loss?
-1.7
A: -log(1/C) = log(C),
frog
If C = 10, then L = log(10) ≈ 2.3
i
Stanford CS231n 10th Anniversary Lecture 2 - 83 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Softmax Classifier (Multinomial Logistic Regression)
Want to interpret raw classifier scores as probabilities
Softmax
Function
Maximize probability of correct class Putting it all together:
cat 3.2
Q2: At initialization all s will be
5.1
car
approximately equal; what is the loss?
-1.7
A: -log(1/C) = log(C),
frog
If C = 10, then L = log(10) ≈ 2.3
i |
| Stanford CS231n 10th Anniversary Lecture 2 - 83 April 3, 2025 |


[Page contains 5 image(s)]


---
## Page 82
---


Coming up: f(x,W) = Wx + b
- Regularization
- Optimization
Stanford CS231n 10th Anniversary Lecture 2 - 84 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Coming up: f(x,W) = Wx + b
- Regularization
- Optimization |
| Stanford CS231n 10th Anniversary Lecture 2 - 84 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 83
---


Reading Assignment – SVM Loss
Stanford CS231n 10th Anniversary Lecture 2 - 85 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Reading Assignment – SVM Loss |
| Stanford CS231n 10th Anniversary Lecture 2 - 85 April 3, 2025 |


---
## Page 84
---


Suppose: 3 training examples, 3 classes.
Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
where is the (integer) label,
and using the shorthand for the scores
vector:
the SVM loss has the form:
cat 3.2 1.3 2.2
5.1 4.9 2.5
car
-1.7 2.0 -3.1
frog
Stanford CS231n 10th Anniversary Lecture 2 -86 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Suppose: 3 training examples, 3 classes.
Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
where is the (integer) label,
and using the shorthand for the scores
vector:
the SVM loss has the form:
cat 3.2 1.3 2.2
5.1 4.9 2.5
car
-1.7 2.0 -3.1
frog |
| Stanford CS231n 10th Anniversary Lecture 2 -86 April 3, 2025 |


[Page contains 9 image(s)]


---
## Page 85
---


Suppose: 3 training examples, 3 classes.
Interpreting Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
Loss
where is the (integer) label,
and using the shorthand for the scores
vector:
difference in
scores between
correct and
the SVM loss has the form:
cat 3.2 1.3 2.2 incorrect class
5.1 4.9 2.5
car
-1.7 2.0 -3.1
frog
Stanford CS231n 10th Anniversary Lecture 2 -87 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Suppose: 3 training examples, 3 classes.
Interpreting Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
Loss
where is the (integer) label,
and using the shorthand for the scores
vector:
difference in
scores between
correct and
the SVM loss has the form:
cat 3.2 1.3 2.2 incorrect class
5.1 4.9 2.5
car
-1.7 2.0 -3.1
frog |
| Stanford CS231n 10th Anniversary Lecture 2 -87 April 3, 2025 |


[Page contains 12 image(s)]


---
## Page 86
---


Suppose: 3 training examples, 3 classes.
Interpreting Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
Loss
where is the (integer) label,
and using the shorthand for the scores
vector:
difference in
scores between
correct and
the SVM loss has the form:
cat 3.2 1.3 2.2 incorrect class
5.1 4.9 2.5
car
-1.7 2.0 -3.1
frog
Stanford CS231n 10th Anniversary Lecture 2 -88 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Suppose: 3 training examples, 3 classes.
Interpreting Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
Loss
where is the (integer) label,
and using the shorthand for the scores
vector:
difference in
scores between
correct and
the SVM loss has the form:
cat 3.2 1.3 2.2 incorrect class
5.1 4.9 2.5
car
-1.7 2.0 -3.1
frog |
| Stanford CS231n 10th Anniversary Lecture 2 -88 April 3, 2025 |


[Page contains 12 image(s)]


---
## Page 87
---


Suppose: 3 training examples, 3 classes.
Interpreting Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
Loss
where is the (integer) label,
and using the shorthand for the scores
vector:
difference in
scores between
correct and
the SVM loss has the form:
cat 3.2 1.3 2.2 incorrect class
5.1 4.9 2.5
car
-1.7 2.0 -3.1
frog
Stanford CS231n 10th Anniversary Lecture 2 -89 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Suppose: 3 training examples, 3 classes.
Interpreting Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
Loss
where is the (integer) label,
and using the shorthand for the scores
vector:
difference in
scores between
correct and
the SVM loss has the form:
cat 3.2 1.3 2.2 incorrect class
5.1 4.9 2.5
car
-1.7 2.0 -3.1
frog |
| Stanford CS231n 10th Anniversary Lecture 2 -89 April 3, 2025 |


[Page contains 12 image(s)]


---
## Page 88
---


Suppose: 3 training examples, 3 classes.
Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
where is the (integer) label,
and using the shorthand for the scores
vector:
the SVM loss has the form:
cat 3.2 1.3 2.2
5.1 4.9 2.5
car
-1.7 2.0 -3.1
frog
Stanford CS231n 10th Anniversary Lecture 2 -90 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Suppose: 3 training examples, 3 classes.
Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
where is the (integer) label,
and using the shorthand for the scores
vector:
the SVM loss has the form:
cat 3.2 1.3 2.2
5.1 4.9 2.5
car
-1.7 2.0 -3.1
frog |
| Stanford CS231n 10th Anniversary Lecture 2 -90 April 3, 2025 |


[Page contains 9 image(s)]


---
## Page 89
---


Suppose: 3 training examples, 3 classes.
Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
where is the (integer) label,
and using the shorthand for the scores
vector:
the SVM loss has the form:
cat 3.2 1.3 2.2
5.1 4.9 2.5
car
= max(0, 5.1 - 3.2 + 1)
+max(0, -1.7 - 3.2 + 1)
-1.7 2.0 -3.1
frog
= max(0, 2.9) + max(0, -3.9)
= 2.9 + 0
2.9
Losses:
= 2.9
Stanford CS231n 10th Anniversary Lecture 2 -91 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Suppose: 3 training examples, 3 classes.
Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
where is the (integer) label,
and using the shorthand for the scores
vector:
the SVM loss has the form:
cat 3.2 1.3 2.2
5.1 4.9 2.5
car
= max(0, 5.1 - 3.2 + 1)
+max(0, -1.7 - 3.2 + 1)
-1.7 2.0 -3.1
frog
= max(0, 2.9) + max(0, -3.9)
= 2.9 + 0
2.9
Losses:
= 2.9 |
| Stanford CS231n 10th Anniversary Lecture 2 -91 April 3, 2025 |


[Page contains 9 image(s)]


---
## Page 90
---


Suppose: 3 training examples, 3 classes.
Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
where is the (integer) label,
and using the shorthand for the scores
vector:
the SVM loss has the form:
cat 3.2 1.3 2.2
5.1 4.9 2.5
car
= max(0, 1.3 - 4.9 + 1)
+max(0, 2.0 - 4.9 + 1)
-1.7 2.0 -3.1
frog
= max(0, -2.6) + max(0, -1.9)
= 0 + 0
2.9 0
Losses:
= 0
Stanford CS231n 10th Anniversary Lecture 2 -92 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Suppose: 3 training examples, 3 classes.
Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
where is the (integer) label,
and using the shorthand for the scores
vector:
the SVM loss has the form:
cat 3.2 1.3 2.2
5.1 4.9 2.5
car
= max(0, 1.3 - 4.9 + 1)
+max(0, 2.0 - 4.9 + 1)
-1.7 2.0 -3.1
frog
= max(0, -2.6) + max(0, -1.9)
= 0 + 0
2.9 0
Losses:
= 0 |
| Stanford CS231n 10th Anniversary Lecture 2 -92 April 3, 2025 |


[Page contains 9 image(s)]


---
## Page 91
---


Suppose: 3 training examples, 3 classes.
Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
where is the (integer) label,
and using the shorthand for the scores
vector:
the SVM loss has the form:
cat 3.2 1.3 2.2
5.1 4.9 2.5
car
= max(0, 2.2 - (-3.1) + 1)
+max(0, 2.5 - (-3.1) + 1)
-1.7 2.0 -3.1
frog
= max(0, 6.3) + max(0, 6.6)
= 6.3 + 6.6
2.9 0 12.9
Losses:
= 12.9
Stanford CS231n 10th Anniversary Lecture 2 -93 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Suppose: 3 training examples, 3 classes.
Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
where is the (integer) label,
and using the shorthand for the scores
vector:
the SVM loss has the form:
cat 3.2 1.3 2.2
5.1 4.9 2.5
car
= max(0, 2.2 - (-3.1) + 1)
+max(0, 2.5 - (-3.1) + 1)
-1.7 2.0 -3.1
frog
= max(0, 6.3) + max(0, 6.6)
= 6.3 + 6.6
2.9 0 12.9
Losses:
= 12.9 |
| Stanford CS231n 10th Anniversary Lecture 2 -93 April 3, 2025 |


[Page contains 9 image(s)]


---
## Page 92
---


Suppose: 3 training examples, 3 classes.
Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
where is the (integer) label,
and using the shorthand for the scores
vector:
the SVM loss has the form:
cat 3.2 1.3 2.2
5.1 4.9 2.5
car
Loss over full dataset is average:
-1.7 2.0 -3.1
frog
L = (2.9 + 0 + 12.9)/3
2.9 0 12.9
Losses:
= 5.27
Stanford CS231n 10th Anniversary Lecture 2 -94 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Suppose: 3 training examples, 3 classes.
Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
where is the (integer) label,
and using the shorthand for the scores
vector:
the SVM loss has the form:
cat 3.2 1.3 2.2
5.1 4.9 2.5
car
Loss over full dataset is average:
-1.7 2.0 -3.1
frog
L = (2.9 + 0 + 12.9)/3
2.9 0 12.9
Losses:
= 5.27 |
| Stanford CS231n 10th Anniversary Lecture 2 -94 April 3, 2025 |


[Page contains 10 image(s)]


---
## Page 93
---


Suppose: 3 training examples, 3 classes.
Multiclass SVM loss:
With some W the scores are:
Q1: What happens to loss if car
scores decrease by 0.5 for this
training example?
Q2: what is the min/max possible
cat 1.3
SVM loss L ?
i
4.9
car
Q3: At initialization W is small so all
2.0
frog
s ≈ 0. What is the loss L , assuming N
i
0 examples and C classes?
Losses:
Stanford CS231n 10th Anniversary Lecture 2 -95 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Suppose: 3 training examples, 3 classes.
Multiclass SVM loss:
With some W the scores are:
Q1: What happens to loss if car
scores decrease by 0.5 for this
training example?
Q2: what is the min/max possible
cat 1.3
SVM loss L ?
i
4.9
car
Q3: At initialization W is small so all
2.0
frog
s ≈ 0. What is the loss L , assuming N
i
0 examples and C classes?
Losses: |
| Stanford CS231n 10th Anniversary Lecture 2 -95 April 3, 2025 |


[Page contains 3 image(s)]


---
## Page 94
---


Suppose: 3 training examples, 3 classes.
Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
where is the (integer) label,
and using the shorthand for the scores
vector:
the SVM loss has the form:
cat 3.2 1.3 2.2
5.1 4.9 2.5
car
Q4: What if the sum
-1.7 2.0 -3.1
frog was over all classes?
(including j = y_i)
2.9 0 12.9
Losses:
Stanford CS231n 10th Anniversary Lecture 2 -96 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Suppose: 3 training examples, 3 classes.
Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
where is the (integer) label,
and using the shorthand for the scores
vector:
the SVM loss has the form:
cat 3.2 1.3 2.2
5.1 4.9 2.5
car
Q4: What if the sum
-1.7 2.0 -3.1
frog was over all classes?
(including j = y_i)
2.9 0 12.9
Losses: |
| Stanford CS231n 10th Anniversary Lecture 2 -96 April 3, 2025 |


[Page contains 9 image(s)]


---
## Page 95
---


Suppose: 3 training examples, 3 classes.
Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
where is the (integer) label,
and using the shorthand for the scores
vector:
the SVM loss has the form:
cat 3.2 1.3 2.2
5.1 4.9 2.5
car
Q5: What if we used
-1.7 2.0 -3.1
frog mean instead of sum?
2.9 0 12.9
Losses:
Stanford CS231n 10th Anniversary Lecture 2 -97 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Suppose: 3 training examples, 3 classes.
Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
where is the (integer) label,
and using the shorthand for the scores
vector:
the SVM loss has the form:
cat 3.2 1.3 2.2
5.1 4.9 2.5
car
Q5: What if we used
-1.7 2.0 -3.1
frog mean instead of sum?
2.9 0 12.9
Losses: |
| Stanford CS231n 10th Anniversary Lecture 2 -97 April 3, 2025 |


[Page contains 9 image(s)]


---
## Page 96
---


Suppose: 3 training examples, 3 classes.
Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
where is the (integer) label,
and using the shorthand for the scores
vector:
the SVM loss has the form:
cat 3.2 1.3 2.2
5.1 4.9 2.5
car
Q6: What if we used
-1.7 2.0 -3.1
frog
2.9 0 12.9
Losses:
Stanford CS231n 10th Anniversary Lecture 2 -98 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Suppose: 3 training examples, 3 classes.
Multiclass SVM loss:
With some W the scores are:
Given an example
where is the image and
where is the (integer) label,
and using the shorthand for the scores
vector:
the SVM loss has the form:
cat 3.2 1.3 2.2
5.1 4.9 2.5
car
Q6: What if we used
-1.7 2.0 -3.1
frog
2.9 0 12.9
Losses: |
| Stanford CS231n 10th Anniversary Lecture 2 -98 April 3, 2025 |


[Page contains 10 image(s)]


---
## Page 97
---


Suppose: 3 training examples, 3 classes.
Multiclass SVM loss:
With some W the scores are:
GGiivveenn aann eexxaammppllee
wwhheerree iiss tthhee iimmaaggee aanndd
Loss
wwhheerree iiss tthhee ((iinntteeggeerr)) llaabbeell,,
aanndd uussiinngg tthhee sshhoorrtthhaanndd ffoorr tthhee ssccoorreess
vveeccttoorr::
difference in
scores between
correct and
tthhee SSVVMM lloossss hhaass tthhee ffoorrmm::
cat 3.2 1.3 2.2 incorrect class
5.1 4.9 2.5
car
Q6: What if we used
-1.7 2.0 -3.1
frog
2.9 0 12.9
Losses:
Stanford CS231n 10th Anniversary Lecture 2 -99 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Suppose: 3 training examples, 3 classes.
Multiclass SVM loss:
With some W the scores are:
GGiivveenn aann eexxaammppllee
wwhheerree iiss tthhee iimmaaggee aanndd
Loss
wwhheerree iiss tthhee ((iinntteeggeerr)) llaabbeell,,
aanndd uussiinngg tthhee sshhoorrtthhaanndd ffoorr tthhee ssccoorreess
vveeccttoorr::
difference in
scores between
correct and
tthhee SSVVMM lloossss hhaass tthhee ffoorrmm::
cat 3.2 1.3 2.2 incorrect class
5.1 4.9 2.5
car
Q6: What if we used
-1.7 2.0 -3.1
frog
2.9 0 12.9
Losses: |
| Stanford CS231n 10th Anniversary Lecture 2 -99 April 3, 2025 |


[Page contains 16 image(s)]


---
## Page 98
---


Multiclass SVM Loss: Example code
# First calculate scores
# Then calculate the margins s -s + 1
j yi
# only sum j is not y, so when j = y, set to zero.
i i
# sum across all j
Stanford CS231n 10th Anniversary Lecture 2 - 100 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Multiclass SVM Loss: Example code
# First calculate scores
# Then calculate the margins s -s + 1
j yi
# only sum j is not y, so when j = y, set to zero.
i i
# sum across all j |
| Stanford CS231n 10th Anniversary Lecture 2 - 100 April 3, 2025 |


[Page contains 2 image(s)]


---
## Page 99
---


Softmax vs. SVM
Stanford CS231n 10th Anniversary Lecture 2 - 101 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Softmax vs. SVM |
| Stanford CS231n 10th Anniversary Lecture 2 - 101 April 3, 2025 |


[Page contains 1 image(s)]


---
## Page 100
---


Softmax vs. SVM
Stanford CS231n 10th Anniversary Lecture 2 - 102 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Softmax vs. SVM |
| Stanford CS231n 10th Anniversary Lecture 2 - 102 April 3, 2025 |


[Page contains 2 image(s)]


---
## Page 101
---


Softmax vs. SVM
assume scores: Q: What is the softmax loss and the
SVM loss?
[10, -2, 3]
[10, 9, 9]
[10, -100, -100]
and
Stanford CS231n 10th Anniversary Lecture 2 - 103 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Softmax vs. SVM |
| assume scores: Q: What is the softmax loss and the
SVM loss?
[10, -2, 3]
[10, 9, 9]
[10, -100, -100]
and |
| Stanford CS231n 10th Anniversary Lecture 2 - 103 April 3, 2025 |


[Page contains 3 image(s)]


---
## Page 102
---


Softmax vs. SVM
assume scores: Q: What is the softmax loss and the
SVM loss if I double the correct
[20, -2, 3]
class score from 10 -> 20?
[20, 9, 9]
[20, -100, -100]
and
Stanford CS231n 10th Anniversary Lecture 2 - 104 April 3, 2025

[Page contains 1 table(s)]


### Table 1

| Softmax vs. SVM |
| assume scores: Q: What is the softmax loss and the
SVM loss if I double the correct
[20, -2, 3]
class score from 10 -> 20?
[20, 9, 9]
[20, -100, -100]
and |
| Stanford CS231n 10th Anniversary Lecture 2 - 104 April 3, 2025 |


[Page contains 3 image(s)]
