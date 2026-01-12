# lecture_12

Extracted using pdfplumber



---
## Page 1
---


Lecture 12:
Self-Supervised Learning
Stanford CS231n 10th Anniversary Lecture 12 - 1 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture 12:
Self-Supervised Learning |
| Stanford CS231n 10th Anniversary Lecture 12 - 1 May 8, 2025 |


---
## Page 2
---


Administrative
- Midterm next Tuesday (5/13 during lecture time) – Don’t be late;
See this Ed post for logistic details.
- Midterm review section tomorrow, Friday, 5/9 at 12:30 pm.
- Project proposal feedback is available on Gradescope.
Stanford CS231n 10th Anniversary Lecture 12 - 2 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Administrative
- Midterm next Tuesday (5/13 during lecture time) – Don’t be late;
See this Ed post for logistic details.
- Midterm review section tomorrow, Friday, 5/9 at 12:30 pm.
- Project proposal feedback is available on Gradescope. |
| Stanford CS231n 10th Anniversary Lecture 12 - 2 May 8, 2025 |


---
## Page 3
---


Previous Lecture: GPUs and How to Train On Them
A bit about GPU hardware How to train on lots of GPUs
Stanford CS231n 10th Anniversary Lecture 12 - 3 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Previous Lecture: GPUs and How to Train On Them
A bit about GPU hardware How to train on lots of GPUs |
| Stanford CS231n 10th Anniversary Lecture 12 - 3 May 8, 2025 |


[Page contains 2 image(s)]


---
## Page 4
---


Lots of Computer Vision Tasks
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
Stanford CS231n 10th Anniversary Lecture 12 - 4 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Lots of Computer Vision Tasks
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
| Stanford CS231n 10th Anniversary Lecture 12 - 4 May 8, 2025 |


[Page contains 4 image(s)]


---
## Page 5
---


Last Week: Visualizing and Understanding
Stanford CS231n 10th Anniversary Lecture 12 - 5 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Last Week: Visualizing and Understanding |
| Stanford CS231n 10th Anniversary Lecture 12 - 5 May 8, 2025 |


[Page contains 3 image(s)]


---
## Page 6
---


Last Week: Visualizing and Understanding
Test image L2 Nearest neighbors in featurespace 4096-dim vector
Recall: Nearest neighbors in
pixelspace
Krizhevskyet al, “ImageNet Classification with Deep Convolutional Neural Networks”, NIPS 2012.
Figures reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 12 - 6 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Last Week: Visualizing and Understanding
Test image L2 Nearest neighbors in featurespace 4096-dim vector
Recall: Nearest neighbors in
pixelspace
Krizhevskyet al, “ImageNet Classification with Deep Convolutional Neural Networks”, NIPS 2012.
Figures reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 12 - 6 May 8, 2025 |


[Page contains 3 image(s)]


---
## Page 7
---


Learned Representations
Test image L2 Nearest neighbors in featurespace 4096-dim vector
Recall: Nearest neighbors in
pixelspace
Krizhevskyet al, “ImageNet Classification with Deep Convolutional Neural Networks”, NIPS 2012.
Figures reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 12 - 7 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Learned Representations
Test image L2 Nearest neighbors in featurespace 4096-dim vector
Recall: Nearest neighbors in
pixelspace
Krizhevskyet al, “ImageNet Classification with Deep Convolutional Neural Networks”, NIPS 2012.
Figures reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 12 - 7 May 8, 2025 |


[Page contains 3 image(s)]


---
## Page 8
---


Learned Representations
4096-dim vector
Class
Labels
What is the problem withlarge-scale training?
- We need a lot of labeled data
Is there a way we can train neural networks without
the need for huge manually labeled datasets?
Krizhevskyet al, “ImageNet Classification with Deep Convolutional Neural Networks”, NIPS 2012.
Figures reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 12 - 8 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Learned Representations
4096-dim vector
Class
Labels
What is the problem withlarge-scale training?
- We need a lot of labeled data
Is there a way we can train neural networks without
the need for huge manually labeled datasets?
Krizhevskyet al, “ImageNet Classification with Deep Convolutional Neural Networks”, NIPS 2012.
Figures reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 12 - 8 May 8, 2025 |


[Page contains 2 image(s)]


---
## Page 9
---


Self-Supervised Learning
Pretext Task
-Define a task based on
the data itself
-No manual annotation
-Could be considered
Pretext an unsupervisedtask;
Objective -but we learn with
supervised learning
objectives, e.g.,
classification or
Trained Encoder
regression.
Downstream dataset
Downstream Task
Downstream -The application you
Objective care about
-You do not have large
datasets
-The dataset is labeled
Stanford CS231n 10th Anniversary Lecture 12 - 9 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Self-Supervised Learning
Pretext Task
-Define a task based on
the data itself
-No manual annotation
-Could be considered
Pretext an unsupervisedtask;
Objective -but we learn with
supervised learning
objectives, e.g.,
classification or
Trained Encoder
regression.
Downstream dataset
Downstream Task
Downstream -The application you
Objective care about
-You do not have large
datasets
-The dataset is labeled |
| Stanford CS231n 10th Anniversary Lecture 12 - 9 May 8, 2025 |


[Page contains 6 image(s)]


---
## Page 10
---


Self-Supervised Learning – Pretext Task
n
o
it
a t Decoder, Labels/outputs
n
e
s e automatically
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
Stanford CS231n 10th Anniversary Lecture 12 - 10 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Self-Supervised Learning – Pretext Task
n
o
it
a t Decoder, Labels/outputs
n
e
s e automatically
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
| Stanford CS231n 10th Anniversary Lecture 12 - 10 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 11
---


Self-Supervised Learning – Downstream Task
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
Stanford CS231n 10th Anniversary Lecture 12 - 11 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Self-Supervised Learning – Downstream Task
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
| Stanford CS231n 10th Anniversary Lecture 12 - 11 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 12
---


Self-supervised pretext tasks
Example: learn to predict image transformations / complete corrupted images
?
θ=?
image completion rotation prediction “jigsaw puzzle” colorization
1. Solving the pretext tasks allow the model to learn good features.
2. We can automatically generate labels for the pretext tasks.
Stanford CS231n 10th Anniversary Lecture 12 - 12 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Self-supervised pretext tasks
Example: learn to predict image transformations / complete corrupted images
?
θ=?
image completion rotation prediction “jigsaw puzzle” colorization
1. Solving the pretext tasks allow the model to learn good features.
2. We can automatically generate labels for the pretext tasks. |
| Stanford CS231n 10th Anniversary Lecture 12 - 12 May 8, 2025 |


[Page contains 7 image(s)]


---
## Page 13
---


How to evaluate a self-supervised learning method?
● Pretext Task Performance
○ Measure how well the model performs on the task it was trained on without labels.
● Representation Quality
○ Evaluate the quality of the learned representations
■ Linear Evaluation Protocol: Train a linear classifier on the leaernedrepresentations;
■ Clustering: Measure clustering performance;
■ t-SNE: Visualize the representations to assess their separability.)
● Robustness and Generalization
○ Test how well the model generalizes to different datasets and is robust to variations.
● Computational Efficiency
○ Assess the efficiency of the method in terms of training time and resource requirements.
● Transfer Learning and Downstream Task Performance
○ Assess the utility of the learned representations by transferring them to a downstream
supervised task.
Stanford CS231n 10th Anniversary Lecture 12 - 13 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| How to evaluate a self-supervised learning method?
● Pretext Task Performance
○ Measure how well the model performs on the task it was trained on without labels.
● Representation Quality
○ Evaluate the quality of the learned representations
■ Linear Evaluation Protocol: Train a linear classifier on the leaernedrepresentations;
■ Clustering: Measure clustering performance;
■ t-SNE: Visualize the representations to assess their separability.)
● Robustness and Generalization
○ Test how well the model generalizes to different datasets and is robust to variations.
● Computational Efficiency
○ Assess the efficiency of the method in terms of training time and resource requirements.
● Transfer Learning and Downstream Task Performance
○ Assess the utility of the learned representations by transferring them to a downstream
supervised task. |
| Stanford CS231n 10th Anniversary Lecture 12 - 13 May 8, 2025 |


---
## Page 14
---


How to evaluate a self-supervised learning method?
feature
self-supervised extractor
learning (e.g., a
convnet)
lots of
unlabeled
data
90°
conv fc
1. Learn good feature extractors from
self-supervised pretext tasks, e.g.,
predicting image rotations
Stanford CS231n 10th Anniversary Lecture 12 - 14 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| How to evaluate a self-supervised learning method?
feature
self-supervised extractor
learning (e.g., a
convnet)
lots of
unlabeled
data
90°
conv fc
1. Learn good feature extractors from
self-supervised pretext tasks, e.g.,
predicting image rotations |
| Stanford CS231n 10th Anniversary Lecture 12 - 14 May 8, 2025 |


[Page contains 2 image(s)]


---
## Page 15
---


How to evaluate a self-supervised learning method?
feature
self-supervised extractor supervised evaluate on the
learning (e.g., a learning target task
convnet)
e.g. classification, detection
lots of
unlabeled
data
90° bird
small amount of
labeled data on
conv fc the target task conv linear
classifier
1. Learn good feature extractors from 2. Attach a shallow network on the
self-supervised pretext tasks, e.g., feature extractor; train the shallow
predicting image rotations network on the target task with small
amount of labeled data
Stanford CS231n 10th Anniversary Lecture 12 - 15 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| How to evaluate a self-supervised learning method?
feature
self-supervised extractor supervised evaluate on the
learning (e.g., a learning target task
convnet)
e.g. classification, detection
lots of
unlabeled
data
90° bird
small amount of
labeled data on
conv fc the target task conv linear
classifier
1. Learn good feature extractors from 2. Attach a shallow network on the
self-supervised pretext tasks, e.g., feature extractor; train the shallow
predicting image rotations network on the target task with small
amount of labeled data |
| Stanford CS231n 10th Anniversary Lecture 12 - 15 May 8, 2025 |


[Page contains 4 image(s)]


---
## Page 16
---


Broader picture
Today’s lecture
computer vision language modeling speech synthesis
Wavenet(van den Oord et al.,
Doerschet al., 2015 2016)
robot / reinforcement learning
...
GPT-4 (OpenAI2023)
Dense Object Net (Florence
and Manuelliet al., 2018)
Stanford CS231n 10th Anniversary Lecture 12 - 16 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Broader picture
Today’s lecture
computer vision language modeling speech synthesis
Wavenet(van den Oord et al.,
Doerschet al., 2015 2016)
robot / reinforcement learning
...
GPT-4 (OpenAI2023)
Dense Object Net (Florence
and Manuelliet al., 2018) |
| Stanford CS231n 10th Anniversary Lecture 12 - 16 May 8, 2025 |


[Page contains 4 image(s)]


---
## Page 17
---


Today’s Agenda
Pretext tasks from image transformations
• Rotation, inpainting, rearrangement, coloring
• Reconstruction-based learning (MAE)
Contrastive representation learning
• Intuition and formulation
• Instance contrastive learning: SimCLR and MOCO
• Sequence contrastive learning: CPC
• Self-Distillation Without Labels, DINO
Stanford CS231n 10th Anniversary Lecture 12 - 17 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Today’s Agenda
Pretext tasks from image transformations
• Rotation, inpainting, rearrangement, coloring
• Reconstruction-based learning (MAE)
Contrastive representation learning
• Intuition and formulation
• Instance contrastive learning: SimCLR and MOCO
• Sequence contrastive learning: CPC
• Self-Distillation Without Labels, DINO |
| Stanford CS231n 10th Anniversary Lecture 12 - 17 May 8, 2025 |


---
## Page 18
---


Today’s Agenda
Pretext tasks from image transformations
• Rotation, inpainting, rearrangement, coloring
• Reconstruction-based learning (MAE)
Contrastive representation learning
• Intuition and formulation
• Instance contrastive learning: SimCLR and MOCO
• Sequence contrastive learning: CPC
• Self-Distillation Without Labels, DINO
Stanford CS231n 10th Anniversary Lecture 12 - 18 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Today’s Agenda
Pretext tasks from image transformations
• Rotation, inpainting, rearrangement, coloring
• Reconstruction-based learning (MAE)
Contrastive representation learning
• Intuition and formulation
• Instance contrastive learning: SimCLR and MOCO
• Sequence contrastive learning: CPC
• Self-Distillation Without Labels, DINO |
| Stanford CS231n 10th Anniversary Lecture 12 - 18 May 8, 2025 |


---
## Page 19
---


Pretext task: predict rotations
Hypothesis: a model could recognize the correct rotation of an object only if
it has the “visual commonsense” of what the object should look like
unperturbed.
(Image source: Gidaris et al. 2018)
Stanford CS231n 10th Anniversary Lecture 12 - 19 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Pretext task: predict rotations
Hypothesis: a model could recognize the correct rotation of an object only if
it has the “visual commonsense” of what the object should look like
unperturbed.
(Image source: Gidaris et al. 2018) |
| Stanford CS231n 10th Anniversary Lecture 12 - 19 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 20
---


Pretext task: predict rotations
Self-supervised
learning by rotating
the entire input
images.
The model learns to
predict which rotation
is applied (4-way
classification)
(Image source: Gidaris et al. 2018)
Stanford CS231n 10th Anniversary Lecture 12 - 20 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Pretext task: predict rotations
Self-supervised
learning by rotating
the entire input
images.
The model learns to
predict which rotation
is applied (4-way
classification)
(Image source: Gidaris et al. 2018) |
| Stanford CS231n 10th Anniversary Lecture 12 - 20 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 21
---


Pretext task: predict rotations
Self-supervised
learning by rotating
the entire input
images.
The model learns to
predict which rotation
is applied (4-way
classification)
(Image source: Gidaris et al. 2018)
Stanford CS231n 10th Anniversary Lecture 12 - 21 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Pretext task: predict rotations
Self-supervised
learning by rotating
the entire input
images.
The model learns to
predict which rotation
is applied (4-way
classification)
(Image source: Gidaris et al. 2018) |
| Stanford CS231n 10th Anniversary Lecture 12 - 21 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 22
---


Evaluation on semi-supervised learning
Self-supervised learning on
CIFAR10 (entire training set).
Freeze conv1 + conv2
Learn conv3 + linear layers with
subset of labeled CIFAR10 data
(classification).
(Image source: Gidaris et al. 2018)
Stanford CS231n 10th Anniversary Lecture 12 - 22 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Evaluation on semi-supervised learning
Self-supervised learning on
CIFAR10 (entire training set).
Freeze conv1 + conv2
Learn conv3 + linear layers with
subset of labeled CIFAR10 data
(classification).
(Image source: Gidaris et al. 2018) |
| Stanford CS231n 10th Anniversary Lecture 12 - 22 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 23
---


Transfer learned features to supervised learning
Pretrained with full ImageNet
supervision
No pretraining
Self-supervised learning on
ImageNet (entire training
set) with AlexNet.
Finetune on labeled data
from Pascal VOC 2007.
Self-supervised learning with rotation prediction
source: Gidaris et al. 2018
Stanford CS231n 10th Anniversary Lecture 12 - 23 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Transfer learned features to supervised learning
Pretrained with full ImageNet
supervision
No pretraining
Self-supervised learning on
ImageNet (entire training
set) with AlexNet.
Finetune on labeled data
from Pascal VOC 2007.
Self-supervised learning with rotation prediction
source: Gidaris et al. 2018 |
| Stanford CS231n 10th Anniversary Lecture 12 - 23 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 24
---


Visualize learned visual attentions
(Image source: Gidaris et al. 2018)
Stanford CS231n 10th Anniversary Lecture 12 - 24 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Visualize learned visual attentions
(Image source: Gidaris et al. 2018) |
| Stanford CS231n 10th Anniversary Lecture 12 - 24 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 25
---


Pretext task: predict relative patch locations
(Image source: Doersch et al., 2015)
Stanford CS231n 10th Anniversary Lecture 12 - 25 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Pretext task: predict relative patch locations
(Image source: Doersch et al., 2015) |
| Stanford CS231n 10th Anniversary Lecture 12 - 25 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 26
---


Pretext task: solving “jigsaw puzzles”
(Image source: Noroozi & Favaro, 2016)
Stanford CS231n 10th Anniversary Lecture 12 - 26 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Pretext task: solving “jigsaw puzzles”
(Image source: Noroozi & Favaro, 2016) |
| Stanford CS231n 10th Anniversary Lecture 12 - 26 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 27
---


Transfer learned features to supervised learning
“Ours” is feature learned from solving image Jigsaw puzzles (Noroozi & Favaro,
2016). Doersch et al. is the method with relative patch location
(source: Noroozi & Favaro, 2016)
Stanford CS231n 10th Anniversary Lecture 12 - 27 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Transfer learned features to supervised learning
“Ours” is feature learned from solving image Jigsaw puzzles (Noroozi & Favaro,
2016). Doersch et al. is the method with relative patch location
(source: Noroozi & Favaro, 2016) |
| Stanford CS231n 10th Anniversary Lecture 12 - 27 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 28
---


Pretext task: predict missing pixels (inpainting)
Context Encoders: Feature Learning by Inpainting (Pathak et al., 2016)
Source: Pathak et al., 2016
Stanford CS231n 10th Anniversary Lecture 12 - 28 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Pretext task: predict missing pixels (inpainting)
Context Encoders: Feature Learning by Inpainting (Pathak et al., 2016)
Source: Pathak et al., 2016 |
| Stanford CS231n 10th Anniversary Lecture 12 - 28 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 29
---


Learning to inpaint by reconstruction
Auto Encoder
Encoder Decoder
Learning to reconstruct the missing pixels
Source: Pathak et al., 2016
Stanford CS231n 10th Anniversary Lecture 12 - 29 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Learning to inpaint by reconstruction
Auto Encoder
Encoder Decoder
Learning to reconstruct the missing pixels
Source: Pathak et al., 2016 |
| Stanford CS231n 10th Anniversary Lecture 12 - 29 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 30
---


Inpainting evaluation
Input (context) reconstruction
Source: Pathak et al., 2016
Stanford CS231n 10th Anniversary Lecture 12 - 30 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Inpainting evaluation
Input (context) reconstruction
Source: Pathak et al., 2016 |
| Stanford CS231n 10th Anniversary Lecture 12 - 30 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 31
---


Learning to inpaint by reconstruction
(We will talk about adversarial learning in the next lecture)
Loss = reconstruction + adversarial learning
Element wise multiplication
0not masked
𝑀 = ቊ
1 masked
Encoder
Adversarial loss between “real” images and inpainted images
Source: Pathak et al., 2016
Stanford CS231n 10th Anniversary Lecture 12 - 31 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Learning to inpaint by reconstruction
(We will talk about adversarial learning in the next lecture)
Loss = reconstruction + adversarial learning
Element wise multiplication
0not masked
𝑀 = ቊ
1 masked
Encoder
Adversarial loss between “real” images and inpainted images
Source: Pathak et al., 2016 |
| Stanford CS231n 10th Anniversary Lecture 12 - 31 May 8, 2025 |


[Page contains 3 image(s)]


---
## Page 32
---


Inpainting evaluation
Input (context) reconstruction adversarial recon + adv
Source: Pathak et al., 2016
Stanford CS231n 10th Anniversary Lecture 12 - 32 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Inpainting evaluation
Input (context) reconstruction adversarial recon + adv
Source: Pathak et al., 2016 |
| Stanford CS231n 10th Anniversary Lecture 12 - 32 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 33
---


Transfer learned features to supervised learning
Self-supervised learning on ImageNet training set, transfer to classification
(Pascal VOC 2007), detection (Pascal VOC 2007), and semantic
segmentation (Pascal VOC 2012)
Source: Pathak et al., 2016
Stanford CS231n 10th Anniversary Lecture 12 - 33 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Transfer learned features to supervised learning
Self-supervised learning on ImageNet training set, transfer to classification
(Pascal VOC 2007), detection (Pascal VOC 2007), and semantic
segmentation (Pascal VOC 2012)
Source: Pathak et al., 2016 |
| Stanford CS231n 10th Anniversary Lecture 12 - 33 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 34
---


Pretext task: image coloring
Source: Richard Zhang / Phillip Isola
Stanford CS231n 10th Anniversary Lecture 12 - 34 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Pretext task: image coloring
Source: Richard Zhang / Phillip Isola |
| Stanford CS231n 10th Anniversary Lecture 12 - 34 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 35
---


Pretext task: image coloring
Source: Richard Zhang / Phillip Isola
Stanford CS231n 10th Anniversary Lecture 12 - 35 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Pretext task: image coloring
Source: Richard Zhang / Phillip Isola |
| Stanford CS231n 10th Anniversary Lecture 12 - 35 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 36
---


Learning features from colorization:
Split-brain Autoencoder
Source: Richard Zhang / Phillip Isola
Stanford CS231n 10th Anniversary Lecture 12 - 36 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Learning features from colorization:
Split-brain Autoencoder
Source: Richard Zhang / Phillip Isola |
| Stanford CS231n 10th Anniversary Lecture 12 - 36 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 37
---


Learning features from colorization:
Split-brain Autoencoder
Idea: cross-channel predictions
Source: Richard Zhang / Phillip Isola
Stanford CS231n 10th Anniversary Lecture 12 - 37 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Learning features from colorization:
Split-brain Autoencoder
Idea: cross-channel predictions
Source: Richard Zhang / Phillip Isola |
| Stanford CS231n 10th Anniversary Lecture 12 - 37 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 38
---


Learning features from colorization:
Split-brain Autoencoder
Source: Richard Zhang / Phillip Isola
Stanford CS231n 10th Anniversary Lecture 12 - 38 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Learning features from colorization:
Split-brain Autoencoder
Source: Richard Zhang / Phillip Isola |
| Stanford CS231n 10th Anniversary Lecture 12 - 38 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 39
---


Transfer learned features to supervised learning
Self-supervised learning on
ImageNet (entire training set).
supervised
Use concatenated features
from F and F
this paper
1 2
Labeled data is from the
Places (Zhou 2016).
Source: Zhang et al., 2017
Stanford CS231n 10th Anniversary Lecture 12 - 39 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Transfer learned features to supervised learning
Self-supervised learning on
ImageNet (entire training set).
supervised
Use concatenated features
from F and F
this paper
1 2
Labeled data is from the
Places (Zhou 2016).
Source: Zhang et al., 2017 |
| Stanford CS231n 10th Anniversary Lecture 12 - 39 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 40
---


Pretext task: image coloring
Source: Richard Zhang / Phillip Isola
Stanford CS231n 10th Anniversary Lecture 12 - 40 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Pretext task: image coloring
Source: Richard Zhang / Phillip Isola |
| Stanford CS231n 10th Anniversary Lecture 12 - 40 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 41
---


Pretext task: image coloring
Source: Richard Zhang / Phillip Isola
Stanford CS231n 10th Anniversary Lecture 12 - 41 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Pretext task: image coloring
Source: Richard Zhang / Phillip Isola |
| Stanford CS231n 10th Anniversary Lecture 12 - 41 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 42
---


Pretext task: video coloring
Idea: model the temporal coherence of colors in videos
reference frame how should I color these frames?
...
t = 1 t = 2 t = 3
t = 0
Source: Vondrick et al., 2018
Stanford CS231n 10th Anniversary Lecture 12 - 42 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Pretext task: video coloring
Idea: model the temporal coherence of colors in videos
reference frame how should I color these frames?
...
t = 1 t = 2 t = 3
t = 0
Source: Vondrick et al., 2018 |
| Stanford CS231n 10th Anniversary Lecture 12 - 42 May 8, 2025 |


[Page contains 4 image(s)]


---
## Page 43
---


Pretext task: video coloring
Idea: model the temporal coherence of colors in videos
reference frame how should I color these frames?
Should be the same color!
...
t = 1 t = 2 t = 3
t = 0
Hypothesis: learning to color video frames should allow model to learn to
track regions or objects without labels!
Source: Vondrick et al., 2018
Stanford CS231n 10th Anniversary Lecture 12 - 43 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Pretext task: video coloring
Idea: model the temporal coherence of colors in videos
reference frame how should I color these frames?
Should be the same color!
...
t = 1 t = 2 t = 3
t = 0
Hypothesis: learning to color video frames should allow model to learn to
track regions or objects without labels!
Source: Vondrick et al., 2018 |
| Stanford CS231n 10th Anniversary Lecture 12 - 43 May 8, 2025 |


[Page contains 4 image(s)]


---
## Page 44
---


Learning to color videos
Learning objective:
Establish mappings
between reference and
target frames in a
learned feature space.
Use the mapping as
“pointers” to copy the
correct color (LAB).
Source: Vondrick et al., 2018
Stanford CS231n 10th Anniversary Lecture 12 - 44 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Learning to color videos
Learning objective:
Establish mappings
between reference and
target frames in a
learned feature space.
Use the mapping as
“pointers” to copy the
correct color (LAB).
Source: Vondrick et al., 2018 |
| Stanford CS231n 10th Anniversary Lecture 12 - 44 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 45
---


Learning to color videos
attention map on the reference
frame
Source: Vondrick et al., 2018
Stanford CS231n 10th Anniversary Lecture 12 - 45 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Learning to color videos
attention map on the reference
frame
Source: Vondrick et al., 2018 |
| Stanford CS231n 10th Anniversary Lecture 12 - 45 May 8, 2025 |


[Page contains 2 image(s)]


---
## Page 46
---


Learning to color videos
attention map on the reference predicted color = weighted
frame sum of the reference color
Source: Vondrick et al., 2018
Stanford CS231n 10th Anniversary Lecture 12 - 46 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Learning to color videos
attention map on the reference predicted color = weighted
frame sum of the reference color
Source: Vondrick et al., 2018 |
| Stanford CS231n 10th Anniversary Lecture 12 - 46 May 8, 2025 |


[Page contains 3 image(s)]


---
## Page 47
---


Learning to color videos
attention map on the reference predicted color = weighted loss between predicted color
frame sum of the reference color and ground truth color
Source: Vondrick et al., 2018
Stanford CS231n 10th Anniversary Lecture 12 - 47 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Learning to color videos
attention map on the reference predicted color = weighted loss between predicted color
frame sum of the reference color and ground truth color
Source: Vondrick et al., 2018 |
| Stanford CS231n 10th Anniversary Lecture 12 - 47 May 8, 2025 |


[Page contains 4 image(s)]


---
## Page 48
---


Colorizing videos (qualitative)
reference frame target frames (gray) predicted color
Source: Google AI blog post
Stanford CS231n 10th Anniversary Lecture 12 - 48 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Colorizing videos (qualitative)
reference frame target frames (gray) predicted color
Source: Google AI blog post |
| Stanford CS231n 10th Anniversary Lecture 12 - 48 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 49
---


Colorizing videos (qualitative)
reference frame target frames (gray) predicted color
Source: Google AI blog post
Stanford CS231n 10th Anniversary Lecture 12 - 49 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Colorizing videos (qualitative)
reference frame target frames (gray) predicted color
Source: Google AI blog post |
| Stanford CS231n 10th Anniversary Lecture 12 - 49 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 50
---


Tracking emerges from colorization
Propagate segmentation masks using learned attention
Source: Google AI blog post
Stanford CS231n 10th Anniversary Lecture 12 - 50 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Tracking emerges from colorization
Propagate segmentation masks using learned attention
Source: Google AI blog post |
| Stanford CS231n 10th Anniversary Lecture 12 - 50 May 8, 2025 |


[Page contains 3 image(s)]


---
## Page 51
---


Tracking emerges from colorization
Propagate pose keypoints using learned attention
Source: Google AI blog post
Stanford CS231n 10th Anniversary Lecture 12 - 51 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Tracking emerges from colorization
Propagate pose keypoints using learned attention
Source: Google AI blog post |
| Stanford CS231n 10th Anniversary Lecture 12 - 51 May 8, 2025 |


[Page contains 3 image(s)]


---
## Page 52
---


Masked Auto Encoders (MAE)
Reconstruction with a larger masked portion
50% masking ratio
75% masking ratio He et al., 2021 Masked Autoencoders
Are Scalable Vision Learners
Stanford CS231n 10th Anniversary Lecture 12 - 52 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Masked Auto Encoders (MAE)
Reconstruction with a larger masked portion
50% masking ratio
75% masking ratio He et al., 2021 Masked Autoencoders
Are Scalable Vision Learners |
| Stanford CS231n 10th Anniversary Lecture 12 - 52 May 8, 2025 |


[Page contains 2 image(s)]


---
## Page 53
---


Masked Auto Encoders (MAE)
He et al., 2021 Masked Autoencoders
Are Scalable Vision Learners
Stanford CS231n 10th Anniversary Lecture 12 - 53 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Masked Auto Encoders (MAE)
He et al., 2021 Masked Autoencoders
Are Scalable Vision Learners |
| Stanford CS231n 10th Anniversary Lecture 12 - 53 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 54
---


Masking Methos
• Similar to the original ViT,
divide the input into non-overlapping patches.
• Uniformly sample a very large proportion (75%) of
these patches and mask them
Figure 6. MAE architecture
from the paper
• Masking a high ratio makes predicting the task
challenging and meaningful.
• Also, not using mask tokens and picking a high
sampling ratio (masking most of the image, e.g.,
75%, and sampling a small visible portion, e.g.,
25%, to feed into the encoder) enables the
encoder to be very large.
He et al., 2021 Masked Autoencoders
Are Scalable Vision Learners
Stanford CS231n 10th Anniversary Lecture 12 - 54 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Masking Methos
• Similar to the original ViT,
divide the input into non-overlapping patches.
• Uniformly sample a very large proportion (75%) of
these patches and mask them
Figure 6. MAE architecture
from the paper
• Masking a high ratio makes predicting the task
challenging and meaningful.
• Also, not using mask tokens and picking a high
sampling ratio (masking most of the image, e.g.,
75%, and sampling a small visible portion, e.g.,
25%, to feed into the encoder) enables the
encoder to be very large.
He et al., 2021 Masked Autoencoders
Are Scalable Vision Learners |
| Stanford CS231n 10th Anniversary Lecture 12 - 54 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 55
---


MAE Encoder
• The encoder only operates
on unmasked patches (25%)
Figure 6. MAE architecture
• Embeds the patches by linear projection
from the paper
and add positional embeddings
• Uses transformer blocks
• Since the input patches are a small part of the input, the encoder is
chosen to be very large. (encoder has over 9 times computations per
token vs decoder) He et al., 2021 Masked Autoencoders
Are Scalable Vision Learners
Stanford CS231n 10th Anniversary Lecture 12 - 55 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| MAE Encoder
• The encoder only operates
on unmasked patches (25%)
Figure 6. MAE architecture
• Embeds the patches by linear projection
from the paper
and add positional embeddings
• Uses transformer blocks
• Since the input patches are a small part of the input, the encoder is
chosen to be very large. (encoder has over 9 times computations per
token vs decoder) He et al., 2021 Masked Autoencoders
Are Scalable Vision Learners |
| Stanford CS231n 10th Anniversary Lecture 12 - 55 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 56
---


MAE Decoder
• Merges the encoder outputs with the shared
mask tokens in previously masked places,
adding positional encodings to them.
• Uses transformer blocks, followed Figure 6. MAE architecture
from the paper
by a linear projection for finalizing pixel reconstruction.
• Is solely responsible for reconstruction, meaning it is not used post-
training. Hence, it is independent of the encoder design, making it flexible
(unlike traditional AEs or UNet). This is an
asymmetrical autoencoder design.
He et al., 2021 Masked Autoencoders
Are Scalable Vision Learners
Stanford CS231n 10th Anniversary Lecture 12 - 56 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| MAE Decoder
• Merges the encoder outputs with the shared
mask tokens in previously masked places,
adding positional encodings to them.
• Uses transformer blocks, followed Figure 6. MAE architecture
from the paper
by a linear projection for finalizing pixel reconstruction.
• Is solely responsible for reconstruction, meaning it is not used post-
training. Hence, it is independent of the encoder design, making it flexible
(unlike traditional AEs or UNet). This is an
asymmetrical autoencoder design.
He et al., 2021 Masked Autoencoders
Are Scalable Vision Learners |
| Stanford CS231n 10th Anniversary Lecture 12 - 56 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 57
---


Reconstruction
• The MSE (mean squared error loss) in the pixel space between the
input image and the reconstructed image is adopted.
• Loss is only computed for masked patches
He et al., 2021 Masked Autoencoders
Are Scalable Vision Learners
Stanford CS231n 10th Anniversary Lecture 12 - 57 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Reconstruction
• The MSE (mean squared error loss) in the pixel space between the
input image and the reconstructed image is adopted.
• Loss is only computed for masked patches
He et al., 2021 Masked Autoencoders
Are Scalable Vision Learners |
| Stanford CS231n 10th Anniversary Lecture 12 - 57 May 8, 2025 |


---
## Page 58
---


Linear Probing vs Full Fine-tuning
n
• In linear probing, the pre-trained model is fixed, and only one o
it
a
t
linear layer is added at the end, to predict the labels (or produce n
e
s
e
the output). This method is used to assess the quality of Encoder r p Linear
e
R
representations from a pre-trained feature extraction model. d
e
n
r
a
e
L
• In fine-tuning, pre-trained model is further trained (not fixed), n
o
it
and one or more layers, possibly with non-linearities are added. a
t
n
e
s
e Linear
Encoder r p
• linear probing: provides a measure of representation quality of a e R /FC
d
e
pre-training in restricted conditions n
r
a
• fine-tuning: exploits models near-true potential to adopt for new e L
tasks
He et al., 2021 Masked Autoencoders
Are Scalable Vision Learners
Stanford CS231n 10th Anniversary Lecture 12 - 58 May 8, 2025

[Page contains 2 table(s)]


### Table 1

| Linear Probing vs Full Fine-tuning
n
• In linear probing, the pre-trained model is fixed, and only one o
it
a
t
linear layer is added at the end, to predict the labels (or produce n
e
s
e
the output). This method is used to assess the quality of Encoder r p Linear
e
R
representations from a pre-trained feature extraction model. d
e
n
r
a
e
L
• In fine-tuning, pre-trained model is further trained (not fixed), n
o
it
and one or more layers, possibly with non-linearities are added. a
t
n
e
s
e Linear
Encoder r p
• linear probing: provides a measure of representation quality of a e R /FC
d
e
pre-training in restricted conditions n
r
a
• fine-tuning: exploits models near-true potential to adopt for new e L
tasks
He et al., 2021 Masked Autoencoders
Are Scalable Vision Learners |
| Stanford CS231n 10th Anniversary Lecture 12 - 58 May 8, 2025 |


### Table 2

|  | n
o
it
a
t
n
e
s
e
Encoder r p Linear
e
R
d
e
n
r
a
e
L |
| In fine-tuning, pre-trained model is further trained (not fixed),
and one or more layers, possibly with non-linearities are added. | n
o
it
a
t
n
e
s
e Linear
Encoder r p
e /FC
R
d
e
n
r
a
e
L |


[Page contains 4 image(s)]


---
## Page 59
---


Ablation Studies
So many modeling/hyperparameter choices:
• Masking ratio
• Decoder depth
• Decoder width
• Mask token (used or not in encoder)
• Reconstruction target
• Data augmentation
• Mask sampling method
• Training schedule
He et al., 2021 Masked Autoencoders
Are Scalable Vision Learners
Stanford CS231n 10th Anniversary Lecture 12 - 59 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Ablation Studies
So many modeling/hyperparameter choices:
• Masking ratio
• Decoder depth
• Decoder width
• Mask token (used or not in encoder)
• Reconstruction target
• Data augmentation
• Mask sampling method
• Training schedule
He et al., 2021 Masked Autoencoders
Are Scalable Vision Learners |
| Stanford CS231n 10th Anniversary Lecture 12 - 59 May 8, 2025 |


[Page contains 3 image(s)]


---
## Page 60
---


Masked Autoencoder – Comparisons
He et al., 2021 Masked Autoencoders
Are Scalable Vision Learners
Stanford CS231n 10th Anniversary Lecture 12 - 60 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Masked Autoencoder – Comparisons
He et al., 2021 Masked Autoencoders
Are Scalable Vision Learners |
| Stanford CS231n 10th Anniversary Lecture 12 - 60 May 8, 2025 |


[Page contains 2 image(s)]


---
## Page 61
---


Summary: pretext tasks from image
transformations
● Pretext tasks focus on “visual common sense”, e.g., predict rotations,
inpainting, rearrangement, and colorization.
● The models are forced learn good features about natural images, e.g.,
semantic representation of an object category, in order to solve the pretext
tasks.
● We often do not care about the performance of these pretext tasks, but
rather how useful the learned features are for downstream tasks
(classification, detection, segmentation).
Stanford CS231n 10th Anniversary Lecture 12 - 61 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Summary: pretext tasks from image
transformations
● Pretext tasks focus on “visual common sense”, e.g., predict rotations,
inpainting, rearrangement, and colorization.
● The models are forced learn good features about natural images, e.g.,
semantic representation of an object category, in order to solve the pretext
tasks.
● We often do not care about the performance of these pretext tasks, but
rather how useful the learned features are for downstream tasks
(classification, detection, segmentation). |
| Stanford CS231n 10th Anniversary Lecture 12 - 61 May 8, 2025 |


---
## Page 62
---


Summary: pretext tasks from image
transformations
● Pretext tasks focus on “visual common sense”, e.g., predict rotations,
inpainting, rearrangement, and colorization.
● The models are forced learn good features about natural images, e.g.,
semantic representation of an object category, in order to solve the pretext
tasks.
● We often do not care about the performance of these pretext tasks, but
rather how useful the learned features are for downstream tasks
(classification, detection, segmentation).
● Problems: 1) coming up with individual pretext tasks is tedious, and 2) the
learned representations may not be general.
Stanford CS231n 10th Anniversary Lecture 12 - 62 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Summary: pretext tasks from image
transformations
● Pretext tasks focus on “visual common sense”, e.g., predict rotations,
inpainting, rearrangement, and colorization.
● The models are forced learn good features about natural images, e.g.,
semantic representation of an object category, in order to solve the pretext
tasks.
● We often do not care about the performance of these pretext tasks, but
rather how useful the learned features are for downstream tasks
(classification, detection, segmentation).
● Problems: 1) coming up with individual pretext tasks is tedious, and 2) the
learned representations may not be general. |
| Stanford CS231n 10th Anniversary Lecture 12 - 62 May 8, 2025 |


---
## Page 63
---


Pretext tasks from image transformations
?
θ=?
image completion rotation prediction “jigsaw puzzle” colorization
Learned representations may be tied to a specific pretext task!
Can we come up with a more general pretext task?
Stanford CS231n 10th Anniversary Lecture 12 - 63 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Pretext tasks from image transformations
?
θ=?
image completion rotation prediction “jigsaw puzzle” colorization
Learned representations may be tied to a specific pretext task!
Can we come up with a more general pretext task? |
| Stanford CS231n 10th Anniversary Lecture 12 - 63 May 8, 2025 |


[Page contains 7 image(s)]


---
## Page 64
---


A more general pretext task?
?
θ=?
same object
Stanford CS231n 10th Anniversary Lecture 12 - 64 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| A more general pretext task?
?
θ=?
same object |
| Stanford CS231n 10th Anniversary Lecture 12 - 64 May 8, 2025 |


[Page contains 8 image(s)]


---
## Page 65
---


A more general pretext task?
?
θ=?
same object
different object
Stanford CS231n 10th Anniversary Lecture 12 - 65 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| A more general pretext task?
?
θ=?
same object
different object |
| Stanford CS231n 10th Anniversary Lecture 12 - 65 May 8, 2025 |


[Page contains 9 image(s)]


---
## Page 66
---


Contrastive Representation Learning
?
θ=?
attract
repel
Stanford CS231n 10th Anniversary Lecture 12 - 66 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Contrastive Representation Learning
?
θ=?
attract
repel |
| Stanford CS231n 10th Anniversary Lecture 12 - 66 May 8, 2025 |


[Page contains 9 image(s)]


---
## Page 67
---


Today’s Agenda
Pretext tasks from image transformations
• Rotation, inpainting, rearrangement, coloring
• Reconstruction-based learning (MAE)
Contrastive representation learning
• Intuition and formulation
• Instance contrastive learning: SimCLR and MOCO
• Sequence contrastive learning: CPC
• Self-Distillation Without Labels, DINO
Stanford CS231n 10th Anniversary Lecture 12 - 67 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Today’s Agenda
Pretext tasks from image transformations
• Rotation, inpainting, rearrangement, coloring
• Reconstruction-based learning (MAE)
Contrastive representation learning
• Intuition and formulation
• Instance contrastive learning: SimCLR and MOCO
• Sequence contrastive learning: CPC
• Self-Distillation Without Labels, DINO |
| Stanford CS231n 10th Anniversary Lecture 12 - 67 May 8, 2025 |


---
## Page 68
---


Contrastive Representation Learning
?
θ=?
attract
repel
Stanford CS231n 10th Anniversary Lecture 12 - 68 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Contrastive Representation Learning
?
θ=?
attract
repel |
| Stanford CS231n 10th Anniversary Lecture 12 - 68 May 8, 2025 |


[Page contains 9 image(s)]


---
## Page 69
---


Contrastive Representation Learning
?
θ=?
reference
positive
negative
Stanford CS231n 10th Anniversary Lecture 12 - 69 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Contrastive Representation Learning
?
θ=?
reference
positive
negative |
| Stanford CS231n 10th Anniversary Lecture 12 - 69 May 8, 2025 |


[Page contains 18 image(s)]


---
## Page 70
---


A formulation of contrastive learning
What we want:
x: reference sample; x+ positive sample; x- negative sample
Given a chosen score function, we aim to learn an encoder
function f that yields high score for positive pairs (x, x+) and low
scores for negative pairs (x, x-).
Stanford CS231n 10th Anniversary Lecture 12 - 70 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| A formulation of contrastive learning
What we want:
x: reference sample; x+ positive sample; x- negative sample
Given a chosen score function, we aim to learn an encoder
function f that yields high score for positive pairs (x, x+) and low
scores for negative pairs (x, x-). |
| Stanford CS231n 10th Anniversary Lecture 12 - 70 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 71
---


A formulation of contrastive learning
Loss function given 1 positive sample and N - 1 negative samples:
Stanford CS231n 10th Anniversary Lecture 12 - 71 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| A formulation of contrastive learning
Loss function given 1 positive sample and N - 1 negative samples: |
| Stanford CS231n 10th Anniversary Lecture 12 - 71 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 72
---


A formulation of contrastive learning
Loss function given 1 positive sample and N - 1 negative samples:
...
Stanford CS231n 10th Anniversary Lecture 12 - 72 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| A formulation of contrastive learning
Loss function given 1 positive sample and N - 1 negative samples:
... |
| Stanford CS231n 10th Anniversary Lecture 12 - 72 May 8, 2025 |


[Page contains 13 image(s)]


---
## Page 73
---


A formulation of contrastive learning
Loss function given 1 positive sample and N - 1 negative samples:
score for the positive score for the N-1 negative
pair pairs
This seems familiar …
Stanford CS231n 10th Anniversary Lecture 12 - 73 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| A formulation of contrastive learning
Loss function given 1 positive sample and N - 1 negative samples:
score for the positive score for the N-1 negative
pair pairs
This seems familiar … |
| Stanford CS231n 10th Anniversary Lecture 12 - 73 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 74
---


A formulation of contrastive learning
Loss function given 1 positive sample and N - 1 negative samples:
score for the positive score for the N-1 negative
pair pairs
This seems familiar …
Cross entropy loss for a N-way softmax classifier!
I.e., learn to find the positive sample from the N samples
Stanford CS231n 10th Anniversary Lecture 12 - 74 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| A formulation of contrastive learning
Loss function given 1 positive sample and N - 1 negative samples:
score for the positive score for the N-1 negative
pair pairs
This seems familiar …
Cross entropy loss for a N-way softmax classifier!
I.e., learn to find the positive sample from the N samples |
| Stanford CS231n 10th Anniversary Lecture 12 - 74 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 75
---


A formulation of contrastive learning
Loss function given 1 positive sample and N - 1 negative samples:
Commonly known as the InfoNCE loss ( )
van den Oord et al., 2018
A lower bound on the mutual information between f(x) and f(x+)
The larger the negative sample size (N), the tighter the bound
Detailed derivation: Poole et al., 2019
Stanford CS231n 10th Anniversary Lecture 12 - 75 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| A formulation of contrastive learning
Loss function given 1 positive sample and N - 1 negative samples:
Commonly known as the InfoNCE loss ( )
van den Oord et al., 2018
A lower bound on the mutual information between f(x) and f(x+)
The larger the negative sample size (N), the tighter the bound
Detailed derivation: Poole et al., 2019 |
| Stanford CS231n 10th Anniversary Lecture 12 - 75 May 8, 2025 |


[Page contains 2 image(s)]


---
## Page 76
---


SimCLR: A Simple Framework for Contrastive Learning
Cosine similarity as the score function:
Use a projection network g(·) to project
features to a space where contrastive
learning is applied
Generate positive samples through data
augmentation:
● random cropping, random color
distortion, and random blur.
Source: Chen et al., 2020
Stanford CS231n 10th Anniversary Lecture 12 - 76 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| SimCLR: A Simple Framework for Contrastive Learning
Cosine similarity as the score function:
Use a projection network g(·) to project
features to a space where contrastive
learning is applied
Generate positive samples through data
augmentation:
● random cropping, random color
distortion, and random blur.
Source: Chen et al., 2020 |
| Stanford CS231n 10th Anniversary Lecture 12 - 76 May 8, 2025 |


[Page contains 2 image(s)]


---
## Page 77
---


SimCLR: generating positive samples from data
augmentation
Source: Chen et al., 2020
Stanford CS231n 10th Anniversary Lecture 12 - 77 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| SimCLR: generating positive samples from data
augmentation
Source: Chen et al., 2020 |
| Stanford CS231n 10th Anniversary Lecture 12 - 77 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 78
---


*We use a slightly different
formulation in the
SimCLR
assignment. You should follow
the assignment instructions.
Generate a positive pair
by sampling data
augmentation functions
Source: Chen et al., 2020
Stanford CS231n 10th Anniversary Lecture 12 - 78 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| *We use a slightly different
formulation in the
SimCLR
assignment. You should follow
the assignment instructions.
Generate a positive pair
by sampling data
augmentation functions
Source: Chen et al., 2020 |
| Stanford CS231n 10th Anniversary Lecture 12 - 78 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 79
---


*We use a slightly different
formulation in the
SimCLR
assignment. You should follow
the assignment instructions.
Generate a positive pair
by sampling data
augmentation functions
InfoNCE loss:
Use all non-positive
samples in the batch
as x-
Source: Chen et al., 2020
Stanford CS231n 10th Anniversary Lecture 12 - 79 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| *We use a slightly different
formulation in the
SimCLR
assignment. You should follow
the assignment instructions.
Generate a positive pair
by sampling data
augmentation functions
InfoNCE loss:
Use all non-positive
samples in the batch
as x-
Source: Chen et al., 2020 |
| Stanford CS231n 10th Anniversary Lecture 12 - 79 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 80
---


*We use a slightly different
formulation in the
SimCLR
assignment. You should follow
the assignment instructions.
Generate a positive pair
by sampling data
augmentation functions
InfoNCE loss:
Use all non-positive
Iterate through and use
samples in the batch
each of the 2N sample
as x-
as reference, compute
average loss
Source: Chen et al., 2020
Stanford CS231n 10th Anniversary Lecture 12 - 80 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| *We use a slightly different
formulation in the
SimCLR
assignment. You should follow
the assignment instructions.
Generate a positive pair
by sampling data
augmentation functions
InfoNCE loss:
Use all non-positive
Iterate through and use
samples in the batch
each of the 2N sample
as x-
as reference, compute
average loss
Source: Chen et al., 2020 |
| Stanford CS231n 10th Anniversary Lecture 12 - 80 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 81
---


SimCLR: mini-batch training
“Affinity matrix”
list of positive pairs
Each 2k and 2k + 1 element is
a positive pair
*We use a slightly different formulation in the assignment.
You should follow the assignment instructions.
Stanford CS231n 10th Anniversary Lecture 12 - 81 May 8, 2025

[Page contains 3 table(s)]


### Table 1

| SimCLR: mini-batch training
“Affinity matrix”
list of positive pairs
Each 2k and 2k + 1 element is
a positive pair
*We use a slightly different formulation in the assignment.
You should follow the assignment instructions. |
| Stanford CS231n 10th Anniversary Lecture 12 - 81 May 8, 2025 |


### Table 2

|  |  |  |  |  |  |
|  |  |  |  |  |  |
|  |  |  |  |  |  |
|  |  |  |  |  |  |
|  |  |  |  |  |  |
|  |  |  |  |  |  |


### Table 3

|  |  |  |  |  |  |  |  |  |  |


[Page contains 6 image(s)]


---
## Page 82
---


SimCLR: mini-batch training
“Affinity matrix”
list of positive pairs
Each 2k and 2k + 1 element is
a positive pair
*We use a slightly different formulation in the assignment. = classification label for each row
You should follow the assignment instructions.
Stanford CS231n 10th Anniversary Lecture 12 - 82 May 8, 2025

[Page contains 3 table(s)]


### Table 1

| SimCLR: mini-batch training
“Affinity matrix”
list of positive pairs
Each 2k and 2k + 1 element is
a positive pair
*We use a slightly different formulation in the assignment. = classification label for each row
You should follow the assignment instructions. |
| Stanford CS231n 10th Anniversary Lecture 12 - 82 May 8, 2025 |


### Table 2

|  |  |  |  |  |  |
|  |  |  |  |  |  |
|  |  |  |  |  |  |
|  |  |  |  |  |  |
|  |  |  |  |  |  |
|  |  |  |  |  |  |


### Table 3

|  |  |  |  |  |  |  |  |  |  |


[Page contains 6 image(s)]


---
## Page 83
---


Training linear classifier on SimCLR features
Train feature encoder on ImageNet
(entire training set) using SimCLR.
Freeze feature encoder, train a
linear classifier on top with labeled
data.
Source: Chen et al., 2020
Stanford CS231n 10th Anniversary Lecture 12 - 83 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Training linear classifier on SimCLR features
Train feature encoder on ImageNet
(entire training set) using SimCLR.
Freeze feature encoder, train a
linear classifier on top with labeled
data.
Source: Chen et al., 2020 |
| Stanford CS231n 10th Anniversary Lecture 12 - 83 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 84
---


Semi-supervised learning on SimCLR features
Train feature encoder on ImageNet
(entire training set) using SimCLR.
Finetune the encoder with 1% / 10%
of labeled data on ImageNet.
Source: Chen et al., 2020
Stanford CS231n 10th Anniversary Lecture 12 - 84 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Semi-supervised learning on SimCLR features
Train feature encoder on ImageNet
(entire training set) using SimCLR.
Finetune the encoder with 1% / 10%
of labeled data on ImageNet.
Source: Chen et al., 2020 |
| Stanford CS231n 10th Anniversary Lecture 12 - 84 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 85
---


SimCLR design choices: projection head
Linear / non-linear projection heads improve
representation learning.
A possible explanation:
● contrastive learning objective may discard
useful information for downstream tasks
● representation space z is trained to be
invariant to data transformation.
● by leveraging the projection head g(ᐧ), more
information can be preserved in the h
representation space
Source: Chen et al., 2020
Stanford CS231n 10th Anniversary Lecture 12 - 85 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| SimCLR design choices: projection head
Linear / non-linear projection heads improve
representation learning.
A possible explanation:
● contrastive learning objective may discard
useful information for downstream tasks
● representation space z is trained to be
invariant to data transformation.
● by leveraging the projection head g(ᐧ), more
information can be preserved in the h
representation space
Source: Chen et al., 2020 |
| Stanford CS231n 10th Anniversary Lecture 12 - 85 May 8, 2025 |


[Page contains 2 image(s)]


---
## Page 86
---


SimCLR design choices: large batch size
Large training batch size is crucial for
SimCLR!
Large batch size causes large memory
footprint during backpropagation:
requires distributed training on TPUs
(ImageNet experiments)
Source: Chen et al., 2020
Stanford CS231n 10th Anniversary Lecture 12 - 86 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| SimCLR design choices: large batch size
Large training batch size is crucial for
SimCLR!
Large batch size causes large memory
footprint during backpropagation:
requires distributed training on TPUs
(ImageNet experiments)
Source: Chen et al., 2020 |
| Stanford CS231n 10th Anniversary Lecture 12 - 86 May 8, 2025 |


[Page contains 2 image(s)]


---
## Page 87
---


Momentum Contrastive Learning (MoCo)
Key differences to SimCLR:
no_grad
● Keep a running queue of keys (negative
samples).
● Compute gradients and update the
encoder only through the queries.
● Decouple min-batch size with the
number of keys: can support a large
number of negative samples.
Source: He et al., 2020
Stanford CS231n 10th Anniversary Lecture 12 - 87 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Momentum Contrastive Learning (MoCo)
Key differences to SimCLR:
no_grad
● Keep a running queue of keys (negative
samples).
● Compute gradients and update the
encoder only through the queries.
● Decouple min-batch size with the
number of keys: can support a large
number of negative samples.
Source: He et al., 2020 |
| Stanford CS231n 10th Anniversary Lecture 12 - 87 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 88
---


Momentum Contrastive Learning (MoCo)
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
Source: He et al., 2020
Stanford CS231n 10th Anniversary Lecture 12 - 88 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Momentum Contrastive Learning (MoCo)
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
Source: He et al., 2020 |
| Stanford CS231n 10th Anniversary Lecture 12 - 88 May 8, 2025 |


[Page contains 2 image(s)]


---
## Page 89
---


MoCo
Generate a positive pair
by sampling data
augmentation functions
Use the running
No gradient through
queue of keys as the
the key
negative samples
InfoNCE loss
Update f_k through
momentum
Update the FIFO negative
sample queue
Source: He et al., 2020
Stanford CS231n 10th Anniversary Lecture 12 - 89 May 8, 2025

[Page contains 2 table(s)]


### Table 1

| MoCo
Generate a positive pair
by sampling data
augmentation functions
Use the running
No gradient through
queue of keys as the
the key
negative samples
InfoNCE loss
Update f_k through
momentum
Update the FIFO negative
sample queue
Source: He et al., 2020 |
| Stanford CS231n 10th Anniversary Lecture 12 - 89 May 8, 2025 |


### Table 2

|  |
|  |


[Page contains 1 image(s)]


---
## Page 90
---


“MoCo V2”
A hybrid of ideas from SimCLR and MoCo:
● From SimCLR: non-linear projection head and strong data
augmentation.
● From MoCo: momentum-updated queues that allow training on
a large number of negative samples (no TPU required!).
Source: Chen et al., 2020
Stanford CS231n 10th Anniversary Lecture 12 - 90 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| “MoCo V2”
A hybrid of ideas from SimCLR and MoCo:
● From SimCLR: non-linear projection head and strong data
augmentation.
● From MoCo: momentum-updated queues that allow training on
a large number of negative samples (no TPU required!).
Source: Chen et al., 2020 |
| Stanford CS231n 10th Anniversary Lecture 12 - 90 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 91
---


MoCo vs. SimCLR vs. MoCo V2
Key takeaways:
● Non-linear projection head and strong
data augmentation are crucial for
contrastive learning.
Source: Chen et al., 2020
Stanford CS231n 10th Anniversary Lecture 12 - 91 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| MoCo vs. SimCLR vs. MoCo V2
Key takeaways:
● Non-linear projection head and strong
data augmentation are crucial for
contrastive learning.
Source: Chen et al., 2020 |
| Stanford CS231n 10th Anniversary Lecture 12 - 91 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 92
---


MoCo vs. SimCLR vs. MoCo V2
Key takeaways:
● Non-linear projection head and strong
data augmentation are crucial for
contrastive learning.
● Decoupling mini-batch size with
negative sample size allows MoCo-V2 to
outperform SimCLR with smaller batch
size (256 vs. 8192).
Source: Chen et al., 2020
Stanford CS231n 10th Anniversary Lecture 12 - 92 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| MoCo vs. SimCLR vs. MoCo V2
Key takeaways:
● Non-linear projection head and strong
data augmentation are crucial for
contrastive learning.
● Decoupling mini-batch size with
negative sample size allows MoCo-V2 to
outperform SimCLR with smaller batch
size (256 vs. 8192).
Source: Chen et al., 2020 |
| Stanford CS231n 10th Anniversary Lecture 12 - 92 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 93
---


MoCo vs. SimCLR vs. MoCo V2
Key takeaways:
● Non-linear projection head and strong
data augmentation are crucial for
contrastive learning.
● Decoupling mini-batch size with
negative sample size allows MoCo-V2 to
outperform SimCLR with smaller batch
size (256 vs. 8192).
● … all with much smaller memory
footprint! (“end-to-end” means SimCLR
here)
Source: Chen et al., 2020
Stanford CS231n 10th Anniversary Lecture 12 - 93 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| MoCo vs. SimCLR vs. MoCo V2
Key takeaways:
● Non-linear projection head and strong
data augmentation are crucial for
contrastive learning.
● Decoupling mini-batch size with
negative sample size allows MoCo-V2 to
outperform SimCLR with smaller batch
size (256 vs. 8192).
● … all with much smaller memory
footprint! (“end-to-end” means SimCLR
here)
Source: Chen et al., 2020 |
| Stanford CS231n 10th Anniversary Lecture 12 - 93 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 94
---


Instance vs. Sequence Contrastive Learning
Source: van den Oord et al., 2018
Instance-level contrastive learning: Sequence-level contrastive learning:
contrastive learning based on contrastive learning based on
positive & negative instances. sequential / temporal orders.
Examples: SimCLR, MoCo Example: Contrastive Predictive Coding (CPC)
Stanford CS231n 10th Anniversary Lecture 12 - 94 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Instance vs. Sequence Contrastive Learning
Source: van den Oord et al., 2018
Instance-level contrastive learning: Sequence-level contrastive learning:
contrastive learning based on contrastive learning based on
positive & negative instances. sequential / temporal orders.
Examples: SimCLR, MoCo Example: Contrastive Predictive Coding (CPC) |
| Stanford CS231n 10th Anniversary Lecture 12 - 94 May 8, 2025 |


[Page contains 2 image(s)]


---
## Page 95
---


Contrastive Predictive Coding (CPC)
Contrastive: contrast between “right”
and “wrong” sequences using
contrastive learning.
Predictive: the model has to predict
future patterns given the current
context.
Coding: the model learns useful
positive
feature vectors, or “code”, for
downstream tasks, similar to other
context
self-supervised methods.
negative
Figure source Source: van den Oord et al., 2018,
Stanford CS231n 10th Anniversary Lecture 12 - 95 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Contrastive Predictive Coding (CPC)
Contrastive: contrast between “right”
and “wrong” sequences using
contrastive learning.
Predictive: the model has to predict
future patterns given the current
context.
Coding: the model learns useful
positive
feature vectors, or “code”, for
downstream tasks, similar to other
context
self-supervised methods.
negative
Figure source Source: van den Oord et al., 2018, |
| Stanford CS231n 10th Anniversary Lecture 12 - 95 May 8, 2025 |


[Page contains 4 image(s)]


---
## Page 96
---


Contrastive Predictive Coding (CPC)
1. Encode all samples in a sequence into
vectors z = g (x )
t enc t
positive
context
negative
Figure source Source: van den Oord et al., 2018,
Stanford CS231n 10th Anniversary Lecture 12 - 96 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Contrastive Predictive Coding (CPC)
1. Encode all samples in a sequence into
vectors z = g (x )
t enc t
positive
context
negative
Figure source Source: van den Oord et al., 2018, |
| Stanford CS231n 10th Anniversary Lecture 12 - 96 May 8, 2025 |


[Page contains 4 image(s)]


---
## Page 97
---


Contrastive Predictive Coding (CPC)
1. Encode all samples in a sequence into
vectors z = g (x )
t enc t
2. Summarize context (e.g., half of a
sequence) into a context code c using an
t
auto-regressive model (g ). The original
ar
paper uses GRU-RNN here.
positive
context
negative
Figure source Source: van den Oord et al., 2018,
Stanford CS231n 10th Anniversary Lecture 12 - 97 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Contrastive Predictive Coding (CPC)
1. Encode all samples in a sequence into
vectors z = g (x )
t enc t
2. Summarize context (e.g., half of a
sequence) into a context code c using an
t
auto-regressive model (g ). The original
ar
paper uses GRU-RNN here.
positive
context
negative
Figure source Source: van den Oord et al., 2018, |
| Stanford CS231n 10th Anniversary Lecture 12 - 97 May 8, 2025 |


[Page contains 4 image(s)]


---
## Page 98
---


Contrastive Predictive Coding (CPC)
1. Encode all samples in a sequence into
vectors z = g (x )
t enc t
2. Summarize context (e.g., half of a
sequence) into a context code c using an
t
auto-regressive model (g )
ar
3. Compute InfoNCEloss between the
context c and future code z using the
t t+k
following time-dependent score
function:
positive
context
where W is a trainable matrix.
k
negative
Figure source Source: van den Oord et al., 2018,
Stanford CS231n 10th Anniversary Lecture 12 - 98 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Contrastive Predictive Coding (CPC)
1. Encode all samples in a sequence into
vectors z = g (x )
t enc t
2. Summarize context (e.g., half of a
sequence) into a context code c using an
t
auto-regressive model (g )
ar
3. Compute InfoNCEloss between the
context c and future code z using the
t t+k
following time-dependent score
function:
positive
context
where W is a trainable matrix.
k
negative
Figure source Source: van den Oord et al., 2018, |
| Stanford CS231n 10th Anniversary Lecture 12 - 98 May 8, 2025 |


[Page contains 5 image(s)]


---
## Page 99
---


CPC example: modeling audio sequences
Source: van den Oord et al., 2018,
Stanford CS231n 10th Anniversary Lecture 12 - 99 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| CPC example: modeling audio sequences
Source: van den Oord et al., 2018, |
| Stanford CS231n 10th Anniversary Lecture 12 - 99 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 100
---


CPC example: modeling audio sequences
Linear classification on trained
representations (LibriSpeechdataset)
Source: van den Oord et al., 2018,
Stanford CS231n 10th Anniversary Lecture 12 - 100 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| CPC example: modeling audio sequences
Linear classification on trained
representations (LibriSpeechdataset)
Source: van den Oord et al., 2018, |
| Stanford CS231n 10th Anniversary Lecture 12 - 100 May 8, 2025 |


[Page contains 2 image(s)]


---
## Page 101
---


CPC example: modeling visual context
Idea: split image into patches, model rows of patches from top to bottom as a
sequence. I.e., use top rows as context to predict bottom rows.
Source: van den Oord et al., 2018,
Stanford CS231n 10th Anniversary Lecture 12 - 101 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| CPC example: modeling visual context
Idea: split image into patches, model rows of patches from top to bottom as a
sequence. I.e., use top rows as context to predict bottom rows.
Source: van den Oord et al., 2018, |
| Stanford CS231n 10th Anniversary Lecture 12 - 101 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 102
---


Other examples: MoCo v3
“This paper does not describe a
novel method.”
Chen et al., An Empirical Study of Training Self-Supervised Vision Transformers, FAIR
Stanford CS231n 10th Anniversary Lecture 12 - 102 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Other examples: MoCo v3
“This paper does not describe a
novel method.”
Chen et al., An Empirical Study of Training Self-Supervised Vision Transformers, FAIR |
| Stanford CS231n 10th Anniversary Lecture 12 - 102 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 103
---


DINO: Self-Distillation with No Labels
Caron et al. 2021 Emerging Properties in
Self-Supervised Vision Transformers
Stanford CS231n 10th Anniversary Lecture 12 - 103 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| DINO: Self-Distillation with No Labels
Caron et al. 2021 Emerging Properties in
Self-Supervised Vision Transformers |
| Stanford CS231n 10th Anniversary Lecture 12 - 103 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 104
---


DINO
Caron et al. 2021 Emerging Properties in
Self-Supervised Vision Transformers
Stanford CS231n 10th Anniversary Lecture 12 - 104 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| DINO
Caron et al. 2021 Emerging Properties in
Self-Supervised Vision Transformers |
| Stanford CS231n 10th Anniversary Lecture 12 - 104 May 8, 2025 |


[Page contains 3 image(s)]


---
## Page 105
---


DINO
Caron et al. 2021 Emerging Properties in
Self-Supervised Vision Transformers
Stanford CS231n 10th Anniversary Lecture 12 - 105 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| DINO
Caron et al. 2021 Emerging Properties in
Self-Supervised Vision Transformers |
| Stanford CS231n 10th Anniversary Lecture 12 - 105 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 106
---


DINO v2
Caron et al. 2021 Emerging Properties in
Self-Supervised Vision Transformers
Stanford CS231n 10th Anniversary Lecture 12 - 106 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| DINO v2
Caron et al. 2021 Emerging Properties in
Self-Supervised Vision Transformers |
| Stanford CS231n 10th Anniversary Lecture 12 - 106 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 107
---


Summary: Contrastive Representation Learning
A general formulation for contrastive learning:
InfoNCE loss: N-way classification among positive and negative samples
Commonly known as the InfoNCE loss ( )
van den Oord et al., 2018
A lower bound on the mutual information between f(x) and f(x+)
Stanford CS231n 10th Anniversary Lecture 12 - 107 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Summary: Contrastive Representation Learning
A general formulation for contrastive learning:
InfoNCE loss: N-way classification among positive and negative samples
Commonly known as the InfoNCE loss ( )
van den Oord et al., 2018
A lower bound on the mutual information between f(x) and f(x+) |
| Stanford CS231n 10th Anniversary Lecture 12 - 107 May 8, 2025 |


[Page contains 3 image(s)]


---
## Page 108
---


Summary: Contrastive Representation Learning
SimCLR: a simple framework for contrastive
representation learning
● Key ideas: non-linear projection head to allow
flexible representation learning
● Simple to implement, effective in learning visual
representation
● Requires large training batch size to be effective;
large memory footprint
Stanford CS231n 10th Anniversary Lecture 12 - 108 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Summary: Contrastive Representation Learning
SimCLR: a simple framework for contrastive
representation learning
● Key ideas: non-linear projection head to allow
flexible representation learning
● Simple to implement, effective in learning visual
representation
● Requires large training batch size to be effective;
large memory footprint |
| Stanford CS231n 10th Anniversary Lecture 12 - 108 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 109
---


Summary: Contrastive Representation Learning
MoCo (v1, v2): contrastive learning using momentum
sample encoder
● Decouples negative sample size from minibatch
size; allows large batch training without TPU
● MoCo-v2 combines the key ideas from SimCLR,
i.e., nonlinear projection head, strong data
augmentation, with momentum contrastive
learning
Stanford CS231n 10th Anniversary Lecture 12 - 109 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Summary: Contrastive Representation Learning
MoCo (v1, v2): contrastive learning using momentum
sample encoder
● Decouples negative sample size from minibatch
size; allows large batch training without TPU
● MoCo-v2 combines the key ideas from SimCLR,
i.e., nonlinear projection head, strong data
augmentation, with momentum contrastive
learning |
| Stanford CS231n 10th Anniversary Lecture 12 - 109 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 110
---


Summary: Contrastive Representation Learning
CPC: sequence-level contrastive learning
● Contrast “right” sequence with “wrong”
sequence.
● InfoNCE loss with a time-dependent score
function.
● Can be applied to a variety of learning
problems, but not as effective in learning
image representations compared to instance-
level methods.
Stanford CS231n 10th Anniversary Lecture 12 - 110 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Summary: Contrastive Representation Learning
CPC: sequence-level contrastive learning
● Contrast “right” sequence with “wrong”
sequence.
● InfoNCE loss with a time-dependent score
function.
● Can be applied to a variety of learning
problems, but not as effective in learning
image representations compared to instance-
level methods. |
| Stanford CS231n 10th Anniversary Lecture 12 - 110 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 111
---


Next time: Generative Models
Stanford CS231n 10th Anniversary Lecture 12 - 111 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Next time: Generative Models |
| Stanford CS231n 10th Anniversary Lecture 12 - 111 May 8, 2025 |


---
## Page 112
---


CPC example: modeling visual context
● Compares favorably with other pretext task-
based self-supervised learning method.
● Doesn’t do as well compared to newer
instance-based contrastive learning methods
on image feature learning.
Source: van den Oord et al., 2018,
Stanford CS231n 10th Anniversary Lecture 12 - 114 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| CPC example: modeling visual context
● Compares favorably with other pretext task-
based self-supervised learning method.
● Doesn’t do as well compared to newer
instance-based contrastive learning methods
on image feature learning.
Source: van den Oord et al., 2018, |
| Stanford CS231n 10th Anniversary Lecture 12 - 114 May 8, 2025 |


[Page contains 2 image(s)]


---
## Page 113
---


Other examples: Dense Object Net
Contrastive learning on pixel-wise feature descriptors
Dense Object Net, Florence et al., 2018
Stanford CS231n 10th Anniversary Lecture 12 - 115 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Other examples: Dense Object Net
Contrastive learning on pixel-wise feature descriptors
Dense Object Net, Florence et al., 2018 |
| Stanford CS231n 10th Anniversary Lecture 12 - 115 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 114
---


Other examples: Dense Object Net
Dense Object Net, Florence et al., 2018
Stanford CS231n 10th Anniversary Lecture 12 - 116 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Other examples: Dense Object Net
Dense Object Net, Florence et al., 2018 |
| Stanford CS231n 10th Anniversary Lecture 12 - 116 May 8, 2025 |


[Page contains 1 image(s)]


---
## Page 115
---


Other examples: Dense Object Net
Dense Object Net, Florence et al., 2018
Stanford CS231n 10th Anniversary Lecture 12 - 117 May 8, 2025

[Page contains 1 table(s)]


### Table 1

| Other examples: Dense Object Net
Dense Object Net, Florence et al., 2018 |
| Stanford CS231n 10th Anniversary Lecture 12 - 117 May 8, 2025 |


[Page contains 1 image(s)]
