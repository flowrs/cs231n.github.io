# lecture_7

Extracted using pdfplumber



---
## Page 1
---


Lecture 7:
Recurrent Neural Networks
Stanford CS231n 10th Anniversary Lecture 7 - 1 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture 7:
Recurrent Neural Networks |
| Stanford CS231n 10th Anniversary Lecture 7 - 1 April 22, 2025 |


---
## Page 2
---


Course Logistics
● Assignment 1 is due tomorrow (4/23) at 11:59PM!
● Project proposal deadline is due this Friday (4/25)
Stanford CS231n 10th Anniversary Lecture 7 - 2 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Course Logistics
● Assignment 1 is due tomorrow (4/23) at 11:59PM!
● Project proposal deadline is due this Friday (4/25) |
| Stanford CS231n 10th Anniversary Lecture 7 - 2 April 22, 2025 |


---
## Page 3
---


Clarifications from Last Time
● Dropout, how to scale probabilities at test-time
● Question in class about normalization vs weight initialization
Stanford CS231n 10th Anniversary Lecture 7 - 3 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Clarifications from Last Time
● Dropout, how to scale probabilities at test-time
● Question in class about normalization vs weight initialization |
| Stanford CS231n 10th Anniversary Lecture 7 - 3 April 22, 2025 |


---
## Page 4
---


Regularization: Dropout
In each forward pass, randomly set some neurons to zero
Probability of dropping is a hyperparameter; 0.5 is common
Srivastava et al, “Dropout: A simple way to prevent neural networks from overfitting”, JMLR 2014
Stanford CS231n 10th Anniversary Lecture 7 - 4 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Regularization: Dropout
In each forward pass, randomly set some neurons to zero
Probability of dropping is a hyperparameter; 0.5 is common
Srivastava et al, “Dropout: A simple way to prevent neural networks from overfitting”, JMLR 2014 |
| Stanford CS231n 10th Anniversary Lecture 7 - 4 April 22, 2025 |


---
## Page 5
---


Dropout: Test time
At test time all neurons are active always
=> We must scale the activations so that for each neuron:
output at test time = expected output at training time
Stanford CS231n 10th Anniversary Lecture 7 - 5 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Dropout: Test time
At test time all neurons are active always
=> We must scale the activations so that for each neuron:
output at test time = expected output at training time |
| Stanford CS231n 10th Anniversary Lecture 7 - 5 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 6
---


Dropout Summary
drop in train time
scale at test time
Stanford CS231n 10th Anniversary Lecture 7 - 6 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Dropout Summary
drop in train time
scale at test time |
| Stanford CS231n 10th Anniversary Lecture 7 - 6 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 7
---


Question in class: can normalization resolve the issues that
arise with having weights initialized incorrectly?
Toy setting, 2d input and 2-layer NN w/ ReLU
2 1
3 4
Link to code (colab) Link to Ed Post
Stanford CS231n 10th Anniversary Lecture 7 - 7 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Question in class: can normalization resolve the issues that
arise with having weights initialized incorrectly?
Toy setting, 2d input and 2-layer NN w/ ReLU
2 1
3 4
Link to code (colab) Link to Ed Post |
| Stanford CS231n 10th Anniversary Lecture 7 - 7 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 8
---


Question in class: can normalization resolve the issues that
arise with having weights initialized incorrectly?
Toy setting, 2d input and 2-layer NN w/ ReLU
Significant reduction in error!
2 1
3 4
Link to code (colab) Link to Ed Post
Stanford CS231n 10th Anniversary Lecture 7 - 8 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Question in class: can normalization resolve the issues that
arise with having weights initialized incorrectly?
Toy setting, 2d input and 2-layer NN w/ ReLU
Significant reduction in error!
2 1
3 4
Link to code (colab) Link to Ed Post |
| Stanford CS231n 10th Anniversary Lecture 7 - 8 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 9
---


Question in class: can normalization resolve the issues that
arise with having weights initialized incorrectly?
Performance gap still exists, does not
Toy setting, 2d input and 2-layer NN w/ ReLU
resolve issues entirely, still optimization
issues
2 1
3 4
Link to code (colab) Link to Ed Post
Stanford CS231n 10th Anniversary Lecture 7 - 9 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Question in class: can normalization resolve the issues that
arise with having weights initialized incorrectly?
Performance gap still exists, does not
Toy setting, 2d input and 2-layer NN w/ ReLU
resolve issues entirely, still optimization
issues
2 1
3 4
Link to code (colab) Link to Ed Post |
| Stanford CS231n 10th Anniversary Lecture 7 - 9 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 10
---


Question in class: can normalization resolve the issues that
arise with having weights initialized incorrectly?
Normalization may not always make sense! In
Toy setting, 2d input and 2-layer NN w/ ReLU
this case, easy to see why it’s helpful (LayerNorm
does not change quadrant of inputs)
2 1
3 4
Link to code (colab) Link to Ed Post
Stanford CS231n 10th Anniversary Lecture 7 - 10 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Question in class: can normalization resolve the issues that
arise with having weights initialized incorrectly?
Normalization may not always make sense! In
Toy setting, 2d input and 2-layer NN w/ ReLU
this case, easy to see why it’s helpful (LayerNorm
does not change quadrant of inputs)
2 1
3 4
Link to code (colab) Link to Ed Post |
| Stanford CS231n 10th Anniversary Lecture 7 - 10 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 11
---


Training Non-Recurrent Neural Networks
1. One time setup: activation functions, preprocessing,
weight initialization, normalization, transfer learning
2. Training dynamics: babysitting the learning process,
parameter updates, hyperparameter optimization
3. Evaluation: validation performance, test-time
augmentation
Stanford CS231n 10th Anniversary Lecture 7 - 11 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Training Non-Recurrent Neural Networks
1. One time setup: activation functions, preprocessing,
weight initialization, normalization, transfer learning
2. Training dynamics: babysitting the learning process,
parameter updates, hyperparameter optimization
3. Evaluation: validation performance, test-time
augmentation |
| Stanford CS231n 10th Anniversary Lecture 7 - 11 April 22, 2025 |


---
## Page 12
---


Evaluate models and tune hyperparameters
https://docs.wandb.ai/guides/track/app
Stanford CS231n 10th Anniversary Lecture 7 - 12 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Evaluate models and tune hyperparameters
https://docs.wandb.ai/guides/track/app |
| Stanford CS231n 10th Anniversary Lecture 7 - 12 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 13
---


Rest of Today’s Lecture
Discuss sequence modeling
● (assumed fixed-length inputs so far)
Simple models commonly used before the era of
●
transformers
RNNs and some variants
○
Relation to modern state-space models (e.g. Mamba)
●
Stanford CS231n 10th Anniversary Lecture 7 - 13 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Rest of Today’s Lecture
Discuss sequence modeling
● (assumed fixed-length inputs so far)
Simple models commonly used before the era of
●
transformers
RNNs and some variants
○
Relation to modern state-space models (e.g. Mamba)
● |
| Stanford CS231n 10th Anniversary Lecture 7 - 13 April 22, 2025 |


---
## Page 14
---


“Vanilla” Neural Network
Vanilla Neural Networks
Stanford CS231n 10th Anniversary Lecture 7 - 14 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| “Vanilla” Neural Network
Vanilla Neural Networks |
| Stanford CS231n 10th Anniversary Lecture 7 - 14 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 15
---


Recurrent Neural Networks: Process Sequences
e.g. Image Captioning
image -> sequence of words
Stanford CS231n 10th Anniversary Lecture 7 - 15 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Recurrent Neural Networks: Process Sequences
e.g. Image Captioning
image -> sequence of words |
| Stanford CS231n 10th Anniversary Lecture 7 - 15 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 16
---


Recurrent Neural Networks: Process Sequences
e.g. action prediction
sequence of video frames -> action class
Stanford CS231n 10th Anniversary Lecture 7 - 16 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Recurrent Neural Networks: Process Sequences
e.g. action prediction
sequence of video frames -> action class |
| Stanford CS231n 10th Anniversary Lecture 7 - 16 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 17
---


Recurrent Neural Networks: Process Sequences
E.g. Video Captioning
Sequence of video frames -> caption
Stanford CS231n 10th Anniversary Lecture 7 - 17 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Recurrent Neural Networks: Process Sequences
E.g. Video Captioning
Sequence of video frames -> caption |
| Stanford CS231n 10th Anniversary Lecture 7 - 17 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 18
---


Recurrent Neural Networks: Process Sequences
e.g. Video classification on frame level
Stanford CS231n 10th Anniversary Lecture 7 - 18 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Recurrent Neural Networks: Process Sequences
e.g. Video classification on frame level |
| Stanford CS231n 10th Anniversary Lecture 7 - 18 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 19
---


Recurrent Neural Network
y
RNN
x
Stanford CS231n 10th Anniversary Lecture 7 - 21 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Recurrent Neural Network
y
RNN
x |
| Stanford CS231n 10th Anniversary Lecture 7 - 21 April 22, 2025 |


---
## Page 20
---


Recurrent Neural Network
y
Key idea: RNNs have an
“internal state” that is
updated as a sequence is
RNN
processed
x
Stanford CS231n 10th Anniversary Lecture 7 - 22 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Recurrent Neural Network
y
Key idea: RNNs have an
“internal state” that is
updated as a sequence is
RNN
processed
x |
| Stanford CS231n 10th Anniversary Lecture 7 - 22 April 22, 2025 |


---
## Page 21
---


Unrolled RNN
y y y y
1 2 3 t
RNN RNN RNN ... RNN
x x x x
1 2 3 t
Stanford CS231n 10th Anniversary Lecture 7 - 23 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Unrolled RNN
y y y y
1 2 3 t
RNN RNN RNN ... RNN
x x x x
1 2 3 t |
| Stanford CS231n 10th Anniversary Lecture 7 - 23 April 22, 2025 |


---
## Page 22
---


RNN hidden state update
We can process a sequence of vectors x by applying a
recurrence formula at every time step: y
RNN
new state old state input vector at
some time step
some function
x
with parameters W
Stanford CS231n 10th Anniversary Lecture 7 - 24 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| RNN hidden state update
We can process a sequence of vectors x by applying a
recurrence formula at every time step: y
RNN
new state old state input vector at
some time step
some function
x
with parameters W |
| Stanford CS231n 10th Anniversary Lecture 7 - 24 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 23
---


RNN output generation
We can process a sequence of vectors x by applying a
recurrence formula at every time step: y
RNN
new state
output
another function
x
with parameters W
hy
Stanford CS231n 10th Anniversary Lecture 7 - 25 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| RNN output generation
We can process a sequence of vectors x by applying a
recurrence formula at every time step: y
RNN
new state
output
another function
x
with parameters W
hy |
| Stanford CS231n 10th Anniversary Lecture 7 - 25 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 24
---


Recurrent Neural Network
y y y y
1 2 3 t
h h h h
0 1 2 3
RNN RNN RNN ... RNN
x x x x
1 2 3 t
Stanford CS231n 10th Anniversary Lecture 7 - 26 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Recurrent Neural Network
y y y y
1 2 3 t
h h h h
0 1 2 3
RNN RNN RNN ... RNN
x x x x
1 2 3 t |
| Stanford CS231n 10th Anniversary Lecture 7 - 26 April 22, 2025 |


---
## Page 25
---


Recurrent Neural Network
We can process a sequence of vectors x by applying a
recurrence formula at every time step: y
RNN
Notice: the same function and the same set of
x
parameters are used at every time step.
Stanford CS231n 10th Anniversary Lecture 7 - 27 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Recurrent Neural Network
We can process a sequence of vectors x by applying a
recurrence formula at every time step: y
RNN
Notice: the same function and the same set of
x
parameters are used at every time step. |
| Stanford CS231n 10th Anniversary Lecture 7 - 27 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 26
---


(Vanilla) Recurrent Neural Network
The state consists of a single “hidden” vector h:
y
RNN
x
Sometimes called a “Vanilla RNN” or an
Often, we also have an output
“Elman RNN” after Prof. Jeffrey Elman
function:
Stanford CS231n 10th Anniversary Lecture 7 - 28 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| (Vanilla) Recurrent Neural Network
The state consists of a single “hidden” vector h:
y
RNN
x
Sometimes called a “Vanilla RNN” or an
Often, we also have an output
“Elman RNN” after Prof. Jeffrey Elman
function: |
| Stanford CS231n 10th Anniversary Lecture 7 - 28 April 22, 2025 |


[Page contains 4 image(s)]


---
## Page 27
---


Vanilla(-ish) RNN: Concrete Example
Manually creating a recurrent network for detecting repeated 1s
X Y “Many to many” sequence modeling task
RNN
y
0 0
1 0
0 0
RNN 1 0
1 1
1 1
0 0
How could we create an RNN to
x
1 0
do this?
1 1
Q: What information should be
captured in the “hidden” state?
Stanford CS231n 10th Anniversary Lecture 7 - 29 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Vanilla(-ish) RNN: Concrete Example
Manually creating a recurrent network for detecting repeated 1s
X Y “Many to many” sequence modeling task
RNN
y
0 0
1 0
0 0
RNN 1 0
1 1
1 1
0 0
How could we create an RNN to
x
1 0
do this?
1 1
Q: What information should be
captured in the “hidden” state? |
| Stanford CS231n 10th Anniversary Lecture 7 - 29 April 22, 2025 |


[Page contains 2 image(s)]


---
## Page 28
---


Vanilla(-ish) RNN: Concrete Example
Manually creating a recurrent network for detecting repeated 1s
X Y “Many to many” sequence modeling task
RNN
y
0 0
1 0
0 0
RNN 1 0
1 1
1 1
0 0
How could we create an RNN to
x
1 0
do this?
1 1
A: Previous input and current
value for x
Stanford CS231n 10th Anniversary Lecture 7 - 30 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Vanilla(-ish) RNN: Concrete Example
Manually creating a recurrent network for detecting repeated 1s
X Y “Many to many” sequence modeling task
RNN
y
0 0
1 0
0 0
RNN 1 0
1 1
1 1
0 0
How could we create an RNN to
x
1 0
do this?
1 1
A: Previous input and current
value for x |
| Stanford CS231n 10th Anniversary Lecture 7 - 30 April 22, 2025 |


[Page contains 2 image(s)]


---
## Page 29
---


Vanilla(-ish) RNN: Concrete Example
Manually creating a recurrent network for detecting repeated 1s
X Y “Many to many” sequence modeling task
RNN
y
0 0
1 0
0 0
RNN 1 0
1 1
1 1
Set and to
0 0
both be ReLU for
x
simplicity
1 0
Initialize
1 1
h_0 to
(0, 0, 1)
Stanford CS231n 10th Anniversary Lecture 7 - 31 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Vanilla(-ish) RNN: Concrete Example
Manually creating a recurrent network for detecting repeated 1s
X Y “Many to many” sequence modeling task
RNN
y
0 0
1 0
0 0
RNN 1 0
1 1
1 1
Set and to
0 0
both be ReLU for
x
simplicity
1 0
Initialize
1 1
h_0 to
(0, 0, 1) |
| Stanford CS231n 10th Anniversary Lecture 7 - 31 April 22, 2025 |


[Page contains 7 image(s)]


---
## Page 30
---


Vanilla(-ish) RNN: Concrete Example
Manually creating a recurrent network for detecting repeated 1s
X
Y
RNN
0 0
1 0
0 0
1 0
1 1
1 1
0 0
1 0
1 1
* Code is missing parts, for full code see here
Stanford CS231n 10th Anniversary Lecture 7 - 32 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Vanilla(-ish) RNN: Concrete Example
Manually creating a recurrent network for detecting repeated 1s
X
Y
RNN
0 0
1 0
0 0
1 0
1 1
1 1
0 0
1 0
1 1
* Code is missing parts, for full code see here |
| Stanford CS231n 10th Anniversary Lecture 7 - 32 April 22, 2025 |


[Page contains 6 image(s)]


---
## Page 31
---


Vanilla(-ish) RNN: Concrete Example
Manually creating a recurrent network for detecting repeated 1s
Right hand term
X
Y
x=0 à [0, 0, 0]
RNN
X=1 à [1, 0, 0] 0 0
1 0
0 0
1 0
1 1
1 1
0 0
1 0
1 1
* Code is missing parts, for full code see here
Stanford CS231n 10th Anniversary Lecture 7 - 33 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Vanilla(-ish) RNN: Concrete Example
Manually creating a recurrent network for detecting repeated 1s
Right hand term
X
Y
x=0 à [0, 0, 0]
RNN
X=1 à [1, 0, 0] 0 0
1 0
0 0
1 0
1 1
1 1
0 0
1 0
1 1
* Code is missing parts, for full code see here |
| Stanford CS231n 10th Anniversary Lecture 7 - 33 April 22, 2025 |


[Page contains 6 image(s)]


---
## Page 32
---


Vanilla(-ish) RNN: Concrete Example
Manually creating a recurrent network for detecting repeated 1s
0 for top row of left
X
Y
term (only use value
RNN
from right term) 0 0
1 0
0 0
1 0
1 1
1 1
0 0
1 0
1 1
* Code is missing parts, for full code see here
Stanford CS231n 10th Anniversary Lecture 7 - 34 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Vanilla(-ish) RNN: Concrete Example
Manually creating a recurrent network for detecting repeated 1s
0 for top row of left
X
Y
term (only use value
RNN
from right term) 0 0
1 0
0 0
1 0
1 1
1 1
0 0
1 0
1 1
* Code is missing parts, for full code see here |
| Stanford CS231n 10th Anniversary Lecture 7 - 34 April 22, 2025 |


[Page contains 6 image(s)]


---
## Page 33
---


Vanilla(-ish) RNN: Concrete Example
Manually creating a recurrent network for detecting repeated 1s
Copy over “current”
X
Y
value from previous
RNN
hidden state to be 0 0
“previous”
1 0
0 0
1 0
1 1
1 1
0 0
1 0
1 1
* Code is missing parts, for full code see here
Stanford CS231n 10th Anniversary Lecture 7 - 35 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Vanilla(-ish) RNN: Concrete Example
Manually creating a recurrent network for detecting repeated 1s
Copy over “current”
X
Y
value from previous
RNN
hidden state to be 0 0
“previous”
1 0
0 0
1 0
1 1
1 1
0 0
1 0
1 1
* Code is missing parts, for full code see here |
| Stanford CS231n 10th Anniversary Lecture 7 - 35 April 22, 2025 |


[Page contains 6 image(s)]


---
## Page 34
---


Vanilla(-ish) RNN: Concrete Example
Manually creating a recurrent network for detecting repeated 1s
Keep 1 on the bottom
X
Y
(helpful for output)
RNN
0 0
1 0
0 0
1 0
1 1
1 1
0 0
1 0
1 1
* Code is missing parts, for full code see here
Stanford CS231n 10th Anniversary Lecture 7 - 36 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Vanilla(-ish) RNN: Concrete Example
Manually creating a recurrent network for detecting repeated 1s
Keep 1 on the bottom
X
Y
(helpful for output)
RNN
0 0
1 0
0 0
1 0
1 1
1 1
0 0
1 0
1 1
* Code is missing parts, for full code see here |
| Stanford CS231n 10th Anniversary Lecture 7 - 36 April 22, 2025 |


[Page contains 6 image(s)]


---
## Page 35
---


Vanilla(-ish) RNN: Concrete Example
Manually creating a recurrent network for detecting repeated 1s
X
Max(Current + Previous – 1, 0) Y
RNN
0 0
1 0
0 0
1 0
1 1
1 1
0 0
1 0
1 1
* Code is missing parts, for full code see here
Stanford CS231n 10th Anniversary Lecture 7 - 37 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Vanilla(-ish) RNN: Concrete Example
Manually creating a recurrent network for detecting repeated 1s
X
Max(Current + Previous – 1, 0) Y
RNN
0 0
1 0
0 0
1 0
1 1
1 1
0 0
1 0
1 1
* Code is missing parts, for full code see here |
| Stanford CS231n 10th Anniversary Lecture 7 - 37 April 22, 2025 |


[Page contains 6 image(s)]


---
## Page 36
---


Vanilla(-ish) RNN: Concrete Example
Manually creating a recurrent network for detecting repeated 1s
And it just works! But X Y
how do we find the Ws RNN
0 0
in practice?
1 0
0 0
1 0
1 1
1 1
0 0
1 0
1 1
* Code is missing parts, for full code see here
Stanford CS231n 10th Anniversary Lecture 7 - 38 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Vanilla(-ish) RNN: Concrete Example
Manually creating a recurrent network for detecting repeated 1s
And it just works! But X Y
how do we find the Ws RNN
0 0
in practice?
1 0
0 0
1 0
1 1
1 1
0 0
1 0
1 1
* Code is missing parts, for full code see here |
| Stanford CS231n 10th Anniversary Lecture 7 - 38 April 22, 2025 |


[Page contains 6 image(s)]


---
## Page 37
---


RNN: Computational Graph
f
h h
0 W 1
x
1
Stanford CS231n 10th Anniversary Lecture 7 - 39 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| RNN: Computational Graph
f
h h
0 W 1
x
1 |
| Stanford CS231n 10th Anniversary Lecture 7 - 39 April 22, 2025 |


---
## Page 38
---


RNN: Computational Graph
f f
h h h
0 W 1 W 2
x x
1 2
Stanford CS231n 10th Anniversary Lecture 7 - 40 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| RNN: Computational Graph
f f
h h h
0 W 1 W 2
x x
1 2 |
| Stanford CS231n 10th Anniversary Lecture 7 - 40 April 22, 2025 |


---
## Page 39
---


RNN: Computational Graph
…
f f f
h h h h h
0 W 1 W 2 W 3 T
x x x
1 2 3
Stanford CS231n 10th Anniversary Lecture 7 - 41 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| RNN: Computational Graph
…
f f f
h h h h h
0 W 1 W 2 W 3 T
x x x
1 2 3 |
| Stanford CS231n 10th Anniversary Lecture 7 - 41 April 22, 2025 |


---
## Page 40
---


RNN: Computational Graph
Re-use the same weight matrix at every time-step
…
f f f
h h h h h
0 W 1 W 2 W 3 T
x x x
1 2 3
W
Stanford CS231n 10th Anniversary Lecture 7 - 42 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| RNN: Computational Graph
Re-use the same weight matrix at every time-step
…
f f f
h h h h h
0 W 1 W 2 W 3 T
x x x
1 2 3
W |
| Stanford CS231n 10th Anniversary Lecture 7 - 42 April 22, 2025 |


---
## Page 41
---


RNN: Computational Graph: Many to Many
y y y
y
2 3 T
1
…
f f f
h h h h h
0 W 1 W 2 W 3 T
x x x
1 2 3
W
Stanford CS231n 10th Anniversary Lecture 7 - 43 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| RNN: Computational Graph: Many to Many
y y y
y
2 3 T
1
…
f f f
h h h h h
0 W 1 W 2 W 3 T
x x x
1 2 3
W |
| Stanford CS231n 10th Anniversary Lecture 7 - 43 April 22, 2025 |


---
## Page 42
---


RNN: Computational Graph: Many to Many
y L y L y L
y L
2 2 3 3 T T
1 1
…
f f f
h h h h h
0 W 1 W 2 W 3 T
x x x
1 2 3
W
Stanford CS231n 10th Anniversary Lecture 7 - 44 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| RNN: Computational Graph: Many to Many
y L y L y L
y L
2 2 3 3 T T
1 1
…
f f f
h h h h h
0 W 1 W 2 W 3 T
x x x
1 2 3
W |
| Stanford CS231n 10th Anniversary Lecture 7 - 44 April 22, 2025 |


---
## Page 43
---


L
RNN: Computational Graph: Many to Many
y L y L y L
y L
2 2 3 3 T T
1 1
…
f f f
h h h h h
0 W 1 W 2 W 3 T
x x x
1 2 3
W
Stanford CS231n 10th Anniversary Lecture 7 - 45 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| L
RNN: Computational Graph: Many to Many
y L y L y L
y L
2 2 3 3 T T
1 1
…
f f f
h h h h h
0 W 1 W 2 W 3 T
x x x
1 2 3
W |
| Stanford CS231n 10th Anniversary Lecture 7 - 45 April 22, 2025 |


---
## Page 44
---


RNN: Computational Graph: Many to One
y
…
f f f
h h h h h
0 W 1 W 2 W 3 T
x x x
1 2 3
W
Stanford CS231n 10th Anniversary Lecture 7 - 46 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| RNN: Computational Graph: Many to One
y
…
f f f
h h h h h
0 W 1 W 2 W 3 T
x x x
1 2 3
W |
| Stanford CS231n 10th Anniversary Lecture 7 - 46 April 22, 2025 |


---
## Page 45
---


RNN: Computational Graph: Many to One
y
…
f f f
h h h h h
0 W 1 W 2 W 3 T
x x x
1 2 3
W
Stanford CS231n 10th Anniversary Lecture 7 - 47 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| RNN: Computational Graph: Many to One
y
…
f f f
h h h h h
0 W 1 W 2 W 3 T
x x x
1 2 3
W |
| Stanford CS231n 10th Anniversary Lecture 7 - 47 April 22, 2025 |


---
## Page 46
---


RNN: Computational Graph: One to Many
y y y
y
2 3 T
1
…
f f f
h h h h h
0 W 1 W 2 W 3 T
x
W
Stanford CS231n 10th Anniversary Lecture 7 - 48 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| RNN: Computational Graph: One to Many
y y y
y
2 3 T
1
…
f f f
h h h h h
0 W 1 W 2 W 3 T
x
W |
| Stanford CS231n 10th Anniversary Lecture 7 - 48 April 22, 2025 |


---
## Page 47
---


RNN: Computational Graph: One to Many
y y y
y
2 3 T
1
…
f f f
h h h h h
0 W 1 W 2 W 3 T
x ? ?
?
W
Stanford CS231n 10th Anniversary Lecture 7 - 49 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| RNN: Computational Graph: One to Many
y y y
y
2 3 T
1
…
f f f
h h h h h
0 W 1 W 2 W 3 T
x ? ?
?
W |
| Stanford CS231n 10th Anniversary Lecture 7 - 49 April 22, 2025 |


---
## Page 48
---


RNN: Computational Graph: One to Many
y y y
y
2 3 T
1
…
f f f
h h h h h
0 W 1 W 2 W 3 T
x 0 0
0
W
Stanford CS231n 10th Anniversary Lecture 7 - 50 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| RNN: Computational Graph: One to Many
y y y
y
2 3 T
1
…
f f f
h h h h h
0 W 1 W 2 W 3 T
x 0 0
0
W |
| Stanford CS231n 10th Anniversary Lecture 7 - 50 April 22, 2025 |


---
## Page 49
---


RNN: Computational Graph: One to Many
y y y
y
2 3 T
1
…
f f f
h h h h h
0 W 1 W 2 W 3 T
x y y y
1 2 T-1
W
Stanford CS231n 10th Anniversary Lecture 7 - 51 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| RNN: Computational Graph: One to Many
y y y
y
2 3 T
1
…
f f f
h h h h h
0 W 1 W 2 W 3 T
x y y y
1 2 T-1
W |
| Stanford CS231n 10th Anniversary Lecture 7 - 51 April 22, 2025 |


---
## Page 50
---


Forward through entire sequence to
Backpropagation through time compute loss, then backward through
entire sequence to compute gradient
Loss
Stanford CS231n 10th Anniversary Lecture 7 - 54 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Forward through entire sequence to
Backpropagation through time compute loss, then backward through
entire sequence to compute gradient
Loss |
| Stanford CS231n 10th Anniversary Lecture 7 - 54 April 22, 2025 |


---
## Page 51
---


Truncated Backpropagation through time
Loss
Run forward and backward
through chunks of the
sequence instead of whole
sequence
Stanford CS231n 10th Anniversary Lecture 7 - 55 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Truncated Backpropagation through time
Loss
Run forward and backward
through chunks of the
sequence instead of whole
sequence |
| Stanford CS231n 10th Anniversary Lecture 7 - 55 April 22, 2025 |


---
## Page 52
---


Truncated Backpropagation through time
Loss
Carry hidden states
forward in time forever,
but only backpropagate
for some smaller number
of steps
Stanford CS231n 10th Anniversary Lecture 7 - 56 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Truncated Backpropagation through time
Loss
Carry hidden states
forward in time forever,
but only backpropagate
for some smaller number
of steps |
| Stanford CS231n 10th Anniversary Lecture 7 - 56 April 22, 2025 |


---
## Page 53
---


Truncated Backpropagation through time
Loss
Stanford CS231n 10th Anniversary Lecture 7 - 57 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Truncated Backpropagation through time
Loss |
| Stanford CS231n 10th Anniversary Lecture 7 - 57 April 22, 2025 |


---
## Page 54
---


Truncated BPTT: Single Output
Still calculate gradients at each time step, rely on
Loss
upstream gradients (no more loss per time-step)
Stanford CS231n 10th Anniversary Lecture 7 - 58 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Truncated BPTT: Single Output
Still calculate gradients at each time step, rely on
Loss
upstream gradients (no more loss per time-step) |
| Stanford CS231n 10th Anniversary Lecture 7 - 58 April 22, 2025 |


---
## Page 55
---


A more practical
example:
Character-level
Language Model
Vocabulary:
[h,e,l,o]
Example training
sequence:
“hello”
Stanford CS231n 10th Anniversary Lecture 7 - 59 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| A more practical
example:
Character-level
Language Model
Vocabulary:
[h,e,l,o]
Example training
sequence:
“hello” |
| Stanford CS231n 10th Anniversary Lecture 7 - 59 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 56
---


A more practical
example:
Character-level
Language Model
Vocabulary:
[h,e,l,o]
Example training
sequence:
“hello”
Stanford CS231n 10th Anniversary Lecture 7 - 60 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| A more practical
example:
Character-level
Language Model
Vocabulary:
[h,e,l,o]
Example training
sequence:
“hello” |
| Stanford CS231n 10th Anniversary Lecture 7 - 60 April 22, 2025 |


[Page contains 2 image(s)]


---
## Page 57
---


A more practical
example:
Character-level
Language Model
Vocabulary:
[h,e,l,o]
Example training
sequence:
“hello”
Stanford CS231n 10th Anniversary Lecture 7 - 61 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| A more practical
example:
Character-level
Language Model
Vocabulary:
[h,e,l,o]
Example training
sequence:
“hello” |
| Stanford CS231n 10th Anniversary Lecture 7 - 61 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 58
---


Example: Character-level “e “l” “l” “o
Sample
” ”
Language Model
.03 .25 .11 .11
.84 .20 .17 .02
Softmax
Sampling .00 .05 .68 .08
.13 .50 .03 .79
Vocabulary:
[h,e,l,o]
At test-time sample characters
one at a time, feed back to
model
Stanford CS231n 10th Anniversary Lecture 7 - 62 April 22, 2025

[Page contains 3 table(s)]


### Table 1

| Example: Character-level “e “l” “l” “o
Sample
” ”
Language Model
.03 .25 .11 .11
.84 .20 .17 .02
Softmax
Sampling .00 .05 .68 .08
.13 .50 .03 .79
Vocabulary:
[h,e,l,o]
At test-time sample characters
one at a time, feed back to
model |
| Stanford CS231n 10th Anniversary Lecture 7 - 62 April 22, 2025 |


### Table 2

|  |  |  |
| “l”
.25
.20
.05
.50 | “l” “o
”
.11 .11
.17 .02
.68 .08
.03 .79 |  |
|  |  |  |


### Table 3

| .11
.02
.08
.79 |  |


[Page contains 1 image(s)]


---
## Page 59
---


Example: Character-level “e “l” “l” “o
Sample
” ”
Language Model
.03 .25 .11 .11
.84 .20 .17 .02
Softmax
Sampling .00 .05 .68 .08
.13 .50 .03 .79
Vocabulary:
[h,e,l,o]
At test-time sample characters
one at a time, feed back to
model
Stanford CS231n 10th Anniversary Lecture 7 - 63 April 22, 2025

[Page contains 3 table(s)]


### Table 1

| Example: Character-level “e “l” “l” “o
Sample
” ”
Language Model
.03 .25 .11 .11
.84 .20 .17 .02
Softmax
Sampling .00 .05 .68 .08
.13 .50 .03 .79
Vocabulary:
[h,e,l,o]
At test-time sample characters
one at a time, feed back to
model |
| Stanford CS231n 10th Anniversary Lecture 7 - 63 April 22, 2025 |


### Table 2

|  |  |
| “l”
.25
.20
.05
.50 | “l” “o
”
.11 .11
.17 .02
.68 .08
.03 .79 |
|  |  |


### Table 3

| .11
.02
.08
.79 |  |


[Page contains 1 image(s)]


---
## Page 60
---


Example: Character-level “e “l” “l” “o
Sample
” ”
Language Model
.03 .25 .11 .11
.84 .20 .17 .02
Softmax
Sampling .00 .50 .68 .08
.13 .05 .03 .79
Vocabulary:
[h,e,l,o]
At test-time sample characters
one at a time, feed back to
model
Stanford CS231n 10th Anniversary Lecture 7 - 64 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Example: Character-level “e “l” “l” “o
Sample
” ”
Language Model
.03 .25 .11 .11
.84 .20 .17 .02
Softmax
Sampling .00 .50 .68 .08
.13 .05 .03 .79
Vocabulary:
[h,e,l,o]
At test-time sample characters
one at a time, feed back to
model |
| Stanford CS231n 10th Anniversary Lecture 7 - 64 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 61
---


Example: Character-level “e “l” “l” “o
Sample
” ”
Language Model
.03 .25 .11 .11
.84 .20 .17 .02
Softmax
Sampling .00 .50 .68 .08
.13 .05 .03 .79
Vocabulary:
[h,e,l,o]
At test-time sample characters
one at a time, feed back to
model
Stanford CS231n 10th Anniversary Lecture 7 - 65 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Example: Character-level “e “l” “l” “o
Sample
” ”
Language Model
.03 .25 .11 .11
.84 .20 .17 .02
Softmax
Sampling .00 .50 .68 .08
.13 .05 .03 .79
Vocabulary:
[h,e,l,o]
At test-time sample characters
one at a time, feed back to
model |
| Stanford CS231n 10th Anniversary Lecture 7 - 65 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 62
---


Example: Character-level
Language Model
Sampling
[w w w w ] [1] [w ]
11 12 13 14 11
[w w w w ] [0] = [w ]
21 22 23 14 21
[w w w w ] [0] [w ]
.03 .25 .11 .11
31 32 33 14 31
Embedding .13 .20 .17 .17
[w w w w ][0] [w ] layer .00 .05 .68 .68
41 42 43 44 41 .84 .50 .03 .03
Matrix multiplication with a one-hot vector
just extracts a column from the weight matrix.
We often put a separate embedding layer
between the input and hidden layers.
Stanford CS231n 10th Anniversary Lecture 7 - 66 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Example: Character-level
Language Model
Sampling
[w w w w ] [1] [w ]
11 12 13 14 11
[w w w w ] [0] = [w ]
21 22 23 14 21
[w w w w ] [0] [w ]
.03 .25 .11 .11
31 32 33 14 31
Embedding .13 .20 .17 .17
[w w w w ][0] [w ] layer .00 .05 .68 .68
41 42 43 44 41 .84 .50 .03 .03
Matrix multiplication with a one-hot vector
just extracts a column from the weight matrix.
We often put a separate embedding layer
between the input and hidden layers. |
| Stanford CS231n 10th Anniversary Lecture 7 - 66 April 22, 2025 |


[Page contains 2 image(s)]


---
## Page 63
---


min-char-rnn.py gist: 112 lines of Python
(https://gist.github.com/karpathy/d4dee5
66867f8291f086)
Stanford CS231n 10th Anniversary Lecture 7 - 67 April 22, 2025

[Page contains 2 table(s)]


### Table 1

| min-char-rnn.py gist: 112 lines of Python
(https://gist.github.com/karpathy/d4dee5
66867f8291f086) |
| Stanford CS231n 10th Anniversary Lecture 7 - 67 April 22, 2025 |


### Table 2

| min | - | char | - | rnn.py gist: 112 lines of Python |


[Page contains 2 image(s)]


---
## Page 64
---


y
RNN
x
Blogpost from Andrej Karpathy back in 2015!
Stanford CS231n 10th Anniversary Lecture 7 - 68 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| y
RNN
x
Blogpost from Andrej Karpathy back in 2015! |
| Stanford CS231n 10th Anniversary Lecture 7 - 68 April 22, 2025 |


[Page contains 2 image(s)]


---
## Page 65
---


at first:
train more
train more
train more
Stanford CS231n 10th Anniversary Lecture 7 - 69 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| at first:
train more
train more
train more |
| Stanford CS231n 10th Anniversary Lecture 7 - 69 April 22, 2025 |


[Page contains 4 image(s)]


---
## Page 66
---


Stanford CS231n 10th Anniversary Lecture 7 - 70 April 22, 2025

[Page contains 1 table(s)]


### Table 1

|  |
| Stanford CS231n 10th Anniversary Lecture 7 - 70 April 22, 2025 |


[Page contains 2 image(s)]


---
## Page 67
---


Stanford CS231n 10th Anniversary Lecture 7 - 74 April 22, 2025

[Page contains 1 table(s)]


### Table 1

|  |
| Stanford CS231n 10th Anniversary Lecture 7 - 74 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 68
---


Generated
C code
Stanford CS231n 10th Anniversary Lecture 7 - 75 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Generated
C code |
| Stanford CS231n 10th Anniversary Lecture 7 - 75 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 69
---


OpenAI Codex, GitHub Copilot, Cursor IDE
https://openai.com/blog/openai-codex/
Stanford CS231n 10th Anniversary Lecture 7 - 76 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| OpenAI Codex, GitHub Copilot, Cursor IDE
https://openai.com/blog/openai-codex/ |
| Stanford CS231n 10th Anniversary Lecture 7 - 76 April 22, 2025 |


[Page contains 3 image(s)]


---
## Page 70
---


Searching for interpretable cells
Stanford CS231n 10th Anniversary Lecture 7 - 77 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Searching for interpretable cells |
| Stanford CS231n 10th Anniversary Lecture 7 - 77 April 22, 2025 |


---
## Page 71
---


Searching for interpretable cells
Karpathy, Johnson, and Fei-Fei: Visualizing and Understanding Recurrent Networks, ICLR Workshop 2016
Figures copyright Karpathy, Johnson, and Fei-Fei, 2015; reproduced with permission
Stanford CS231n 10th Anniversary Lecture 7 - 78 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Searching for interpretable cells
Karpathy, Johnson, and Fei-Fei: Visualizing and Understanding Recurrent Networks, ICLR Workshop 2016
Figures copyright Karpathy, Johnson, and Fei-Fei, 2015; reproduced with permission |
| Stanford CS231n 10th Anniversary Lecture 7 - 78 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 72
---


Searching for interpretable cells
quote detection cell
Karpathy, Johnson, and Fei-Fei: Visualizing and Understanding Recurrent Networks, ICLR Workshop 2016
Figures copyright Karpathy, Johnson, and Fei-Fei, 2015; reproduced with permission
Stanford CS231n 10th Anniversary Lecture 7 - 79 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Searching for interpretable cells
quote detection cell
Karpathy, Johnson, and Fei-Fei: Visualizing and Understanding Recurrent Networks, ICLR Workshop 2016
Figures copyright Karpathy, Johnson, and Fei-Fei, 2015; reproduced with permission |
| Stanford CS231n 10th Anniversary Lecture 7 - 79 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 73
---


Searching for interpretable cells
line length tracking cell
Karpathy, Johnson, and Fei-Fei: Visualizing and Understanding Recurrent Networks, ICLR Workshop 2016
Figures copyright Karpathy, Johnson, and Fei-Fei, 2015; reproduced with permission
Stanford CS231n 10th Anniversary Lecture 7 - 80 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Searching for interpretable cells
line length tracking cell
Karpathy, Johnson, and Fei-Fei: Visualizing and Understanding Recurrent Networks, ICLR Workshop 2016
Figures copyright Karpathy, Johnson, and Fei-Fei, 2015; reproduced with permission |
| Stanford CS231n 10th Anniversary Lecture 7 - 80 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 74
---


Searching for interpretable cells
if statement cell
Karpathy, Johnson, and Fei-Fei: Visualizing and Understanding Recurrent Networks, ICLR Workshop 2016
Figures copyright Karpathy, Johnson, and Fei-Fei, 2015; reproduced with permission
Stanford CS231n 10th Anniversary Lecture 7 - 81 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Searching for interpretable cells
if statement cell
Karpathy, Johnson, and Fei-Fei: Visualizing and Understanding Recurrent Networks, ICLR Workshop 2016
Figures copyright Karpathy, Johnson, and Fei-Fei, 2015; reproduced with permission |
| Stanford CS231n 10th Anniversary Lecture 7 - 81 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 75
---


Searching for interpretable cells
quote/comment cell
Karpathy, Johnson, and Fei-Fei: Visualizing and Understanding Recurrent Networks, ICLR Workshop 2016
Figures copyright Karpathy, Johnson, and Fei-Fei, 2015; reproduced with permission
Stanford CS231n 10th Anniversary Lecture 7 - 82 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Searching for interpretable cells
quote/comment cell
Karpathy, Johnson, and Fei-Fei: Visualizing and Understanding Recurrent Networks, ICLR Workshop 2016
Figures copyright Karpathy, Johnson, and Fei-Fei, 2015; reproduced with permission |
| Stanford CS231n 10th Anniversary Lecture 7 - 82 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 76
---


Searching for interpretable cells
code depth cell
Karpathy, Johnson, and Fei-Fei: Visualizing and Understanding Recurrent Networks, ICLR Workshop 2016
Figures copyright Karpathy, Johnson, and Fei-Fei, 2015; reproduced with permission
Stanford CS231n 10th Anniversary Lecture 7 - 83 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Searching for interpretable cells
code depth cell
Karpathy, Johnson, and Fei-Fei: Visualizing and Understanding Recurrent Networks, ICLR Workshop 2016
Figures copyright Karpathy, Johnson, and Fei-Fei, 2015; reproduced with permission |
| Stanford CS231n 10th Anniversary Lecture 7 - 83 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 77
---


RNN tradeoffs
RNN Advantages:
- Can process any length of the input (no context length)
- Computation for step t can (in theory) use information from many steps back
- Model size does not increase for longer input
- The same weights are applied on every timestep, so there is symmetry in
how inputs are processed.
RNN Disadvantages:
- Recurrent computation is slow
- In practice, difficult to access information from many steps back
Stanford CS231n 10th Anniversary Lecture 7 - 84 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| RNN tradeoffs
RNN Advantages:
- Can process any length of the input (no context length)
- Computation for step t can (in theory) use information from many steps back
- Model size does not increase for longer input
- The same weights are applied on every timestep, so there is symmetry in
how inputs are processed.
RNN Disadvantages:
- Recurrent computation is slow
- In practice, difficult to access information from many steps back |
| Stanford CS231n 10th Anniversary Lecture 7 - 84 April 22, 2025 |


---
## Page 78
---


Image Captioning
Figure from Karpathyet a, “Deep Visual-
Semantic Alignments for Generating Image
Descriptions”, CVPR 2015; figure copyright
IEEE, 2015.
Reproduced for educational purposes.
Explain Images with Multimodal Recurrent Neural Networks, Mao et al.
Deep Visual-Semantic Alignments for Generating Image Descriptions, Karpathy and Fei-Fei
Show and Tell: A Neural Image Caption Generator, Vinyals et al.
Long-term Recurrent Convolutional Networks for Visual Recognition and Description, Donahue et al.
Learning a Recurrent Visual Representation for Image Caption Generation, Chen and Zitnick
Stanford CS231n 10th Anniversary Lecture 7 - 85 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Image Captioning
Figure from Karpathyet a, “Deep Visual-
Semantic Alignments for Generating Image
Descriptions”, CVPR 2015; figure copyright
IEEE, 2015.
Reproduced for educational purposes.
Explain Images with Multimodal Recurrent Neural Networks, Mao et al.
Deep Visual-Semantic Alignments for Generating Image Descriptions, Karpathy and Fei-Fei
Show and Tell: A Neural Image Caption Generator, Vinyals et al.
Long-term Recurrent Convolutional Networks for Visual Recognition and Description, Donahue et al.
Learning a Recurrent Visual Representation for Image Caption Generation, Chen and Zitnick |
| Stanford CS231n 10th Anniversary Lecture 7 - 85 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 79
---


Recurrent Neural Network
Convolutional Neural Network
Stanford CS231n 10th Anniversary Lecture 7 - 86 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Recurrent Neural Network
Convolutional Neural Network |
| Stanford CS231n 10th Anniversary Lecture 7 - 86 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 80
---


test image
This imageis CC0 public domain
Stanford CS231n 10th Anniversary Lecture 7 - 87 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| test image
This imageis CC0 public domain |
| Stanford CS231n 10th Anniversary Lecture 7 - 87 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 81
---


test image
Stanford CS231n 10th Anniversary Lecture 7 - 88 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| test image |
| Stanford CS231n 10th Anniversary Lecture 7 - 88 April 22, 2025 |


[Page contains 2 image(s)]


---
## Page 82
---


test image
X
Stanford CS231n 10th Anniversary Lecture 7 - 89 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| test image
X |
| Stanford CS231n 10th Anniversary Lecture 7 - 89 April 22, 2025 |


[Page contains 2 image(s)]


---
## Page 83
---


test image
x0
<START>
Stanford CS231n 10th Anniversary Lecture 7 - 90 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| test image
x0
<START> |
| Stanford CS231n 10th Anniversary Lecture 7 - 90 April 22, 2025 |


[Page contains 2 image(s)]


---
## Page 84
---


test image
y0
before:
h = tanh(W * x + W * h)
xh hh
h0
Wih
now:
h = tanh(W * x + W * h + W * v)
xh hh ih
x0
<START>
Stanford CS231n 10th Anniversary Lecture 7 - 91 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| test image
y0
before:
h = tanh(W * x + W * h)
xh hh
h0
Wih
now:
h = tanh(W * x + W * h + W * v)
xh hh ih
x0
<START> |
| Stanford CS231n 10th Anniversary Lecture 7 - 91 April 22, 2025 |


[Page contains 2 image(s)]


---
## Page 85
---


test image
y0
sample!
h0
x0
straw
<START>
Stanford CS231n 10th Anniversary Lecture 7 - 92 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| test image
y0
sample!
h0
x0
straw
<START> |
| Stanford CS231n 10th Anniversary Lecture 7 - 92 April 22, 2025 |


[Page contains 2 image(s)]


---
## Page 86
---


test image
y0 y1
h0 h1
x0
straw
<START>
Stanford CS231n 10th Anniversary Lecture 7 - 93 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| test image
y0 y1
h0 h1
x0
straw
<START> |
| Stanford CS231n 10th Anniversary Lecture 7 - 93 April 22, 2025 |


[Page contains 2 image(s)]


---
## Page 87
---


test image
y0 y1
sample!
h0 h1
x0
straw hat
<START>
Stanford CS231n 10th Anniversary Lecture 7 - 94 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| test image
y0 y1
sample!
h0 h1
x0
straw hat
<START> |
| Stanford CS231n 10th Anniversary Lecture 7 - 94 April 22, 2025 |


[Page contains 2 image(s)]


---
## Page 88
---


test image
y0 y1 y2
h0 h1 h2
x0
straw hat
<START>
Stanford CS231n 10th Anniversary Lecture 7 - 95 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| test image
y0 y1 y2
h0 h1 h2
x0
straw hat
<START> |
| Stanford CS231n 10th Anniversary Lecture 7 - 95 April 22, 2025 |


[Page contains 2 image(s)]


---
## Page 89
---


test image
y0 y1 y2
sample
<END> token
=> finish.
h0 h1 h2
x0
straw hat
<START>
Stanford CS231n 10th Anniversary Lecture 7 - 96 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| test image
y0 y1 y2
sample
<END> token
=> finish.
h0 h1 h2
x0
straw hat
<START> |
| Stanford CS231n 10th Anniversary Lecture 7 - 96 April 22, 2025 |


[Page contains 2 image(s)]


---
## Page 90
---


Captions generated using neuraltalk2
Image Captioning: Example Results All images areCC0 Public domain: cat
suitcase, cat tree, dog, bear, surfers,
tennis, giraffe, motorcycle
A cat sitting on a suitcase A cat is sitting on a tree A dog is running in the grass A white teddy bear sitting in
on the floor branch with a frisbee the grass
Two people walking on the Two giraffes standing in a A man riding a dirt bike on a
A tennis player in action
beach with surfboards grassy field dirt track
on the court
Stanford CS231n 10th Anniversary Lecture 7 - 97 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Captions generated using neuraltalk2
Image Captioning: Example Results All images areCC0 Public domain: cat
suitcase, cat tree, dog, bear, surfers,
tennis, giraffe, motorcycle
A cat sitting on a suitcase A cat is sitting on a tree A dog is running in the grass A white teddy bear sitting in
on the floor branch with a frisbee the grass
Two people walking on the Two giraffes standing in a A man riding a dirt bike on a
A tennis player in action
beach with surfboards grassy field dirt track
on the court |
| Stanford CS231n 10th Anniversary Lecture 7 - 97 April 22, 2025 |


[Page contains 8 image(s)]


---
## Page 91
---


Captions generated using neuraltalk2
Image Captioning: Failure Cases All images areCC0 Public domain: fur coat,
handstand, spider web, baseball
A bird is perched on a
tree branch
A woman is holding a cat
in her hand
A man in a
baseball uniform
throwing a ball
A woman standing on a beach
holding a surfboard
A person holding a computer
mouse on a desk
Stanford CS231n 10th Anniversary Lecture 7 - 98 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Captions generated using neuraltalk2
Image Captioning: Failure Cases All images areCC0 Public domain: fur coat,
handstand, spider web, baseball
A bird is perched on a
tree branch
A woman is holding a cat
in her hand
A man in a
baseball uniform
throwing a ball
A woman standing on a beach
holding a surfboard
A person holding a computer
mouse on a desk |
| Stanford CS231n 10th Anniversary Lecture 7 - 98 April 22, 2025 |


[Page contains 5 image(s)]


---
## Page 92
---


Visual Question Answering (VQA)
Agrawal et al, “VQA: Visual Question Answering”, ICCV 2015
Zhu et al, “Visual 7W: Grounded Question Answering in Images”, CVPR 2016
Figure from Zhu et al, copyright IEEE 2016. Reproduced for educational purposes.
Stanford CS231n 10th Anniversary Lecture 7 - 99 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Visual Question Answering (VQA)
Agrawal et al, “VQA: Visual Question Answering”, ICCV 2015
Zhu et al, “Visual 7W: Grounded Question Answering in Images”, CVPR 2016
Figure from Zhu et al, copyright IEEE 2016. Reproduced for educational purposes. |
| Stanford CS231n 10th Anniversary Lecture 7 - 99 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 93
---


Visual Dialog: Conversations about images
Das et al, “Visual Dialog”, CVPR 2017
Figures from Das et al, copyright IEEE 2017. Reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 7 - 101 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Visual Dialog: Conversations about images
Das et al, “Visual Dialog”, CVPR 2017
Figures from Das et al, copyright IEEE 2017. Reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 7 - 101 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 94
---


Visual Language Navigation: Go to the living room
Agent encodes instructions in language
and uses an RNN to generate a series of
movements as the visual input changes
after each move.
Wang et al, “Reinforced Cross-Modal Matching and Self-Supervised Imitation
Learning for Vision-Language Navigation”, CVPR 2018
Figures from Wang et al, copyright IEEE 2017. Reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 7 - 102 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Visual Language Navigation: Go to the living room
Agent encodes instructions in language
and uses an RNN to generate a series of
movements as the visual input changes
after each move.
Wang et al, “Reinforced Cross-Modal Matching and Self-Supervised Imitation
Learning for Vision-Language Navigation”, CVPR 2018
Figures from Wang et al, copyright IEEE 2017. Reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 7 - 102 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 95
---


Multilayer RNNs
depth
time
Stanford CS231n 10th Anniversary Lecture 7 - 104 April 22, 2025

[Page contains 22 table(s)]


### Table 1

| Multilayer RNNs
depth
time |
| Stanford CS231n 10th Anniversary Lecture 7 - 104 April 22, 2025 |


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

|  |  |
|  |  |


### Table 8

|  |  |
|  |  |


### Table 9

|  |  |
|  |  |


### Table 10

|  |  |
|  |  |


### Table 11

|  |  |
|  |  |


### Table 12

|  |  |
|  |  |


### Table 13

|  |  |
|  |  |


### Table 14

|  |  |
|  |  |


### Table 15

|  |  |
|  |  |


### Table 16

|  |  |
|  |  |


### Table 17

|  |  |
|  |  |


### Table 18

|  |  |
|  |  |


### Table 19

|  |  |
|  |  |


### Table 20

|  |  |
|  |  |


### Table 21

|  |  |
|  |  |


### Table 22

|  |  |
|  |  |


---
## Page 96
---


RNN Variants: Long Short Term Memory (LSTM)
Vanilla RNN LSTM
Hochreiter and Schmidhuber, “Long Short Term Memory”, Neural Computation 1997
Stanford CS231n 10th Anniversary Lecture 7 - 105 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| RNN Variants: Long Short Term Memory (LSTM)
Vanilla RNN LSTM
Hochreiter and Schmidhuber, “Long Short Term Memory”, Neural Computation 1997 |
| Stanford CS231n 10th Anniversary Lecture 7 - 105 April 22, 2025 |


[Page contains 2 image(s)]


---
## Page 97
---


Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
y
t
W
tanh
h h
stack
t-1 t
x
t
Stanford CS231n 10th Anniversary Lecture 7 - 106 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
y
t
W
tanh
h h
stack
t-1 t
x
t |
| Stanford CS231n 10th Anniversary Lecture 7 - 106 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 98
---


Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
Backpropagation from h
t
y
to h multiplies by W
t-1 t
(actually W T)
hh
W
tanh
h h
stack
t-1 t
x
t
Stanford CS231n 10th Anniversary Lecture 7 - 107 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
Backpropagation from h
t
y
to h multiplies by W
t-1 t
(actually W T)
hh
W
tanh
h h
stack
t-1 t
x
t |
| Stanford CS231n 10th Anniversary Lecture 7 - 107 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 99
---


Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
Backpropagation from h
t
y
to h multiplies by W
t-1 t
(actually W T)
hh
W
tanh
h h
stack
t-1 t
x
t
Stanford CS231n 10th Anniversary Lecture 7 - 108 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
Backpropagation from h
t
y
to h multiplies by W
t-1 t
(actually W T)
hh
W
tanh
h h
stack
t-1 t
x
t |
| Stanford CS231n 10th Anniversary Lecture 7 - 108 April 22, 2025 |


[Page contains 2 image(s)]


---
## Page 100
---


Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
y y y y
1 2 3 4
h h h h h
0 1 2 3 4
x x x x
1 2 3 4
Stanford CS231n 10th Anniversary Lecture 7 - 109 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
y y y y
1 2 3 4
h h h h h
0 1 2 3 4
x x x x
1 2 3 4 |
| Stanford CS231n 10th Anniversary Lecture 7 - 109 April 22, 2025 |


[Page contains 5 image(s)]


---
## Page 101
---


Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
Gradients over multiple time steps:
y y y y
1 2 3 4
h h h h h
0 1 2 3 4
x x x x
1 2 3 4
Stanford CS231n 10th Anniversary Lecture 7 - 110 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
Gradients over multiple time steps:
y y y y
1 2 3 4
h h h h h
0 1 2 3 4
x x x x
1 2 3 4 |
| Stanford CS231n 10th Anniversary Lecture 7 - 110 April 22, 2025 |


[Page contains 6 image(s)]


---
## Page 102
---


Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
Gradients over multiple time steps:
y y y y
1 2 3 4
h h h h h
0 1 2 3 4
x x x x
1 2 3 4
Stanford CS231n 10th Anniversary Lecture 7 - 111 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
Gradients over multiple time steps:
y y y y
1 2 3 4
h h h h h
0 1 2 3 4
x x x x
1 2 3 4 |
| Stanford CS231n 10th Anniversary Lecture 7 - 111 April 22, 2025 |


[Page contains 7 image(s)]


---
## Page 103
---


Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
Gradients over multiple time steps:
y y y y
1 2 3 4
h h h h h
0 1 2 3 4
x x x x
1 2 3 4
Stanford CS231n 10th Anniversary Lecture 7 - 112 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
Gradients over multiple time steps:
y y y y
1 2 3 4
h h h h h
0 1 2 3 4
x x x x
1 2 3 4 |
| Stanford CS231n 10th Anniversary Lecture 7 - 112 April 22, 2025 |


[Page contains 8 image(s)]


---
## Page 104
---


Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
Gradients over multiple time steps:
y y y y
1 2 3 4
h h h h h
0 1 2 3 4
x x x x
1 2 3 4
Almost always < 1
Vanishing gradients
Stanford CS231n 10th Anniversary Lecture 7 - 113 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
Gradients over multiple time steps:
y y y y
1 2 3 4
h h h h h
0 1 2 3 4
x x x x
1 2 3 4
Almost always < 1
Vanishing gradients |
| Stanford CS231n 10th Anniversary Lecture 7 - 113 April 22, 2025 |


[Page contains 7 image(s)]


---
## Page 105
---


Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
Gradients over multiple time steps:
y y y y
1 2 3 4
h h h h h
0 1 2 3 4
x x x x
1 2 3 4
What if we assumed no non-linearity?
Stanford CS231n 10th Anniversary Lecture 7 - 114 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
Gradients over multiple time steps:
y y y y
1 2 3 4
h h h h h
0 1 2 3 4
x x x x
1 2 3 4
What if we assumed no non-linearity? |
| Stanford CS231n 10th Anniversary Lecture 7 - 114 April 22, 2025 |


[Page contains 5 image(s)]


---
## Page 106
---


Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
Gradients over multiple time steps:
y y y y
1 2 3 4
h h h h h
0 1 2 3 4
x x x x
1 2 3 4
What if we assumed no non-linearity?
Largest singular value > 1:
Exploding gradients
Largest singular value < 1:
Vanishing gradients
Stanford CS231n 10th Anniversary Lecture 7 - 115 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
Gradients over multiple time steps:
y y y y
1 2 3 4
h h h h h
0 1 2 3 4
x x x x
1 2 3 4
What if we assumed no non-linearity?
Largest singular value > 1:
Exploding gradients
Largest singular value < 1:
Vanishing gradients |
| Stanford CS231n 10th Anniversary Lecture 7 - 115 April 22, 2025 |


[Page contains 6 image(s)]


---
## Page 107
---


Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
Gradients over multiple time steps:
y y y y
1 2 3 4
h h h h h
0 1 2 3 4
x x x x
1 2 3 4
What if we assumed no non-linearity?
Largest singular value > 1: Gradient clipping: Scale
Exploding gradients gradient if its norm is too
big
Largest singular value < 1:
Vanishing gradients
Stanford CS231n 10th Anniversary Lecture 7 - 116 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
Gradients over multiple time steps:
y y y y
1 2 3 4
h h h h h
0 1 2 3 4
x x x x
1 2 3 4
What if we assumed no non-linearity?
Largest singular value > 1: Gradient clipping: Scale
Exploding gradients gradient if its norm is too
big
Largest singular value < 1:
Vanishing gradients |
| Stanford CS231n 10th Anniversary Lecture 7 - 116 April 22, 2025 |


[Page contains 7 image(s)]


---
## Page 108
---


Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
Gradients over multiple time steps:
y y y y
1 2 3 4
h h h h h
0 1 2 3 4
x x x x
1 2 3 4
What if we assumed no non-linearity?
Largest singular value > 1:
Exploding gradients
Largest singular value < 1: Change RNN
Vanishing gradients architecture
Stanford CS231n 10th Anniversary Lecture 7 - 117 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Vanilla RNN Gradient Flow Bengioet al, “Learning long-term dependencies with gradient descent is
difficult”, IEEE Transactions on Neural Networks, 1994
Pascanuet al, “On the difficulty of training recurrent neural networks”,
ICML 2013
Gradients over multiple time steps:
y y y y
1 2 3 4
h h h h h
0 1 2 3 4
x x x x
1 2 3 4
What if we assumed no non-linearity?
Largest singular value > 1:
Exploding gradients
Largest singular value < 1: Change RNN
Vanishing gradients architecture |
| Stanford CS231n 10th Anniversary Lecture 7 - 117 April 22, 2025 |


[Page contains 6 image(s)]


---
## Page 109
---


Long Short Term Memory (LSTM) – A Historical Note
Vanilla RNN LSTM
Hochreiter and Schmidhuber, “Long Short Term Memory”, Neural Computation 1997
Stanford CS231n 10th Anniversary Lecture 7 - 118 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Long Short Term Memory (LSTM) – A Historical Note
Vanilla RNN LSTM
Hochreiter and Schmidhuber, “Long Short Term Memory”, Neural Computation 1997 |
| Stanford CS231n 10th Anniversary Lecture 7 - 118 April 22, 2025 |


[Page contains 2 image(s)]


---
## Page 110
---


Long Short Term Memory (LSTM)
Vanilla RNN LSTM
Four gates
Cell state
Hidden state
Hochreiter and Schmidhuber, “Long Short Term Memory”, Neural Computation 1997
Stanford CS231n 10th Anniversary Lecture 7 - 119 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Long Short Term Memory (LSTM)
Vanilla RNN LSTM
Four gates
Cell state
Hidden state
Hochreiter and Schmidhuber, “Long Short Term Memory”, Neural Computation 1997 |
| Stanford CS231n 10th Anniversary Lecture 7 - 119 April 22, 2025 |


[Page contains 2 image(s)]


---
## Page 111
---


Long Short Term Memory (LSTM)
[Hochreiter et al., 1997]
vector from
below (x)
x sigmoid i
h sigmoid f
W
vector from
sigmoid o
before (h)
tanh g
4h 4*h
4h x 2h
Stanford CS231n 10th Anniversary Lecture 7 - 120 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Long Short Term Memory (LSTM)
[Hochreiter et al., 1997]
vector from
below (x)
x sigmoid i
h sigmoid f
W
vector from
sigmoid o
before (h)
tanh g
4h 4*h
4h x 2h |
| Stanford CS231n 10th Anniversary Lecture 7 - 120 April 22, 2025 |


---
## Page 112
---


Long Short Term Memory (LSTM)
i: Input gate, whether to write to cell
[Hochreiter et al., 1997]
f: Forget gate, Whether to erase cell
o: Output gate, How much to reveal cell
vector from
g: Gate gate (?), How much to write to cell
below (x)
x sigmoid i
h sigmoid f
W
vector from
sigmoid o
before (h)
tanh g
4h 4*h
4h x 2h
Stanford CS231n 10th Anniversary Lecture 7 - 121 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Long Short Term Memory (LSTM)
i: Input gate, whether to write to cell
[Hochreiter et al., 1997]
f: Forget gate, Whether to erase cell
o: Output gate, How much to reveal cell
vector from
g: Gate gate (?), How much to write to cell
below (x)
x sigmoid i
h sigmoid f
W
vector from
sigmoid o
before (h)
tanh g
4h 4*h
4h x 2h |
| Stanford CS231n 10th Anniversary Lecture 7 - 121 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 113
---


Long Short Term Memory (LSTM)
i: Input gate, whether to write to cell
[Hochreiter et al., 1997]
f: Forget gate, Whether to erase cell
o: Output gate, How much to reveal cell
vector from
g: Gate gate (?), How much to write to cell
below (x)
x sigmoid i
h sigmoid f
W
vector from
sigmoid o
before (h)
tanh g
4h 4*h
4h x 2h
Stanford CS231n 10th Anniversary Lecture 7 - 122 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Long Short Term Memory (LSTM)
i: Input gate, whether to write to cell
[Hochreiter et al., 1997]
f: Forget gate, Whether to erase cell
o: Output gate, How much to reveal cell
vector from
g: Gate gate (?), How much to write to cell
below (x)
x sigmoid i
h sigmoid f
W
vector from
sigmoid o
before (h)
tanh g
4h 4*h
4h x 2h |
| Stanford CS231n 10th Anniversary Lecture 7 - 122 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 114
---


Long Short Term Memory (LSTM)
i: Input gate, whether to write to cell
[Hochreiter et al., 1997]
f: Forget gate, Whether to erase cell
o: Output gate, How much to reveal cell
vector from
g: Gate gate (?), How much to write to cell
below (x)
x sigmoid i
h sigmoid f
W
vector from
sigmoid o
before (h)
tanh g
4h 4*h
4h x 2h
Stanford CS231n 10th Anniversary Lecture 7 - 123 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Long Short Term Memory (LSTM)
i: Input gate, whether to write to cell
[Hochreiter et al., 1997]
f: Forget gate, Whether to erase cell
o: Output gate, How much to reveal cell
vector from
g: Gate gate (?), How much to write to cell
below (x)
x sigmoid i
h sigmoid f
W
vector from
sigmoid o
before (h)
tanh g
4h 4*h
4h x 2h |
| Stanford CS231n 10th Anniversary Lecture 7 - 123 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 115
---


Long Short Term Memory (LSTM)
i: Input gate, whether to write to cell
[Hochreiter et al., 1997]
f: Forget gate, Whether to erase cell
o: Output gate, How much to reveal cell
vector from
g: Gate gate (?), How much to write to cell
below (x)
x sigmoid i
h sigmoid f
W
vector from
sigmoid o
before (h)
tanh g
4h 4*h
4h x 2h
Stanford CS231n 10th Anniversary Lecture 7 - 124 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Long Short Term Memory (LSTM)
i: Input gate, whether to write to cell
[Hochreiter et al., 1997]
f: Forget gate, Whether to erase cell
o: Output gate, How much to reveal cell
vector from
g: Gate gate (?), How much to write to cell
below (x)
x sigmoid i
h sigmoid f
W
vector from
sigmoid o
before (h)
tanh g
4h 4*h
4h x 2h |
| Stanford CS231n 10th Anniversary Lecture 7 - 124 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 116
---


Long Short Term Memory (LSTM)
[Hochreiter et al., 1997]
c
c
☉ +
t
t-1
f
i
W
☉
tanh
g
h
stack
o h
t-1 ☉
t
x
t
Stanford CS231n 10th Anniversary Lecture 7 - 125 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Long Short Term Memory (LSTM)
[Hochreiter et al., 1997]
c
c
☉ +
t
t-1
f
i
W
☉
tanh
g
h
stack
o h
t-1 ☉
t
x
t |
| Stanford CS231n 10th Anniversary Lecture 7 - 125 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 117
---


Long Short Term Memory (LSTM): Gradient Flow
[Hochreiter et al., 1997]
Backpropagation from c to
t
c only elementwise
t-1
multiplication by f, no matrix
c
c
☉ +
t
t-1
multiply by W
f
i
W
☉
tanh
g
h
stack
o h
t-1 ☉
t
x
t
Stanford CS231n 10th Anniversary Lecture 7 - 126 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Long Short Term Memory (LSTM): Gradient Flow
[Hochreiter et al., 1997]
Backpropagation from c to
t
c only elementwise
t-1
multiplication by f, no matrix
c
c
☉ +
t
t-1
multiply by W
f
i
W
☉
tanh
g
h
stack
o h
t-1 ☉
t
x
t |
| Stanford CS231n 10th Anniversary Lecture 7 - 126 April 22, 2025 |


[Page contains 1 image(s)]


---
## Page 118
---


Long Short Term Memory (LSTM): Gradient Flow
[Hochreiter et al., 1997]
Uninterrupted gradient flow!
c c c c
0 1 2 3
Stanford CS231n 10th Anniversary Lecture 7 - April 22, 2025
127

[Page contains 1 table(s)]


### Table 1

| Long Short Term Memory (LSTM): Gradient Flow
[Hochreiter et al., 1997]
Uninterrupted gradient flow!
c c c c
0 1 2 3 |
| Stanford CS231n 10th Anniversary Lecture 7 - April 22, 2025 |


[Page contains 3 image(s)]


---
## Page 119
---


Do LSTMs solve the vanishing gradient problem?
The LSTM architecture makes it easier for the RNN to preserve information
over many timesteps
- e.g. if the f = 1 and the i = 0, then the information of that cell is preserved
indefinitely.
- By contrast, it’s harder for vanilla RNN to learn a recurrent weight matrix
Wh that preserves info in hidden state
LSTM doesn’t guarantee that there is no vanishing/exploding gradient, but it
does provide an easier way for the model to learn long-distance dependencies
Stanford CS231n 10th Anniversary Lecture 7 - 128 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Do LSTMs solve the vanishing gradient problem?
The LSTM architecture makes it easier for the RNN to preserve information
over many timesteps
- e.g. if the f = 1 and the i = 0, then the information of that cell is preserved
indefinitely.
- By contrast, it’s harder for vanilla RNN to learn a recurrent weight matrix
Wh that preserves info in hidden state
LSTM doesn’t guarantee that there is no vanishing/exploding gradient, but it
does provide an easier way for the model to learn long-distance dependencies |
| Stanford CS231n 10th Anniversary Lecture 7 - 128 April 22, 2025 |


---
## Page 120
---


Long Short Term Memory (LSTM): Gradient Flow
[Hochreiter et al., 1997]
Uninterrupted gradient flow!
c c c c
0 1 2 3
Stanford CS231n 10th Anniversary Lecture 7 - 129 April 22, 2025
Input
7x7
conv,
64
/
2
Pool
3x3
conv,
64
3x3
conv,
64
3x3
conv,
64
3x3
conv,
64
3x3
conv,
64
3x3
conv,
64
3x3
conv,
128
/
2
3x3
conv,
128
3x3
conv,
128
3x3
conv,
128
3x3
conv,
128
3x3
conv,
128
...
3x3
conv,
64
3x3
conv,
64
3x3
conv,
64
3x3
conv,
64
3x3
conv,
64
3x3
conv,
64
Pool
FC
1000
Softmax
Similar to ResNet!

[Page contains 1 table(s)]


### Table 1

| Long Short Term Memory (LSTM): Gradient Flow
[Hochreiter et al., 1997]
Uninterrupted gradient flow!
c c c c
0 1 2 3
7x7 3x3
3x3 3x3 3x3 3x3 3x3 3x3 3x3 3x3 3x3 3x3 3x3 3x3 3x3 3x3 3x3 3x3 3x3 Similar to ResNet!
conv, conv, FC Softmax
Input Pool conv, conv, conv, conv, conv, conv, conv, conv, conv, conv, conv, conv, conv, conv, conv, conv, conv, Pool
... 1000
64 128
64 64 64 64 64 64 128 128 128 128 128 64 64 64 64 64 64
/ /
2 2 |
| Stanford CS231n 10th Anniversary Lecture 7 - 129 April 22, 2025 |


[Page contains 3 image(s)]


---
## Page 121
---


Long Short Term Memory (LSTM): Gradient Flow
[Hochreiter et al., 1997]
Uninterrupted gradient flow!
c c c c
0 1 2 3
Stanford CS231n 10th Anniversary Lecture 7 - 130 April 22, 2025
Input
7x7
conv,
64
/
2
Pool
3x3
conv,
64
3x3
conv,
64
3x3
conv,
64
3x3
conv,
64
3x3
conv,
64
3x3
conv,
64
3x3
conv,
128
/
2
3x3
conv,
128
3x3
conv,
128
3x3
conv,
128
3x3
conv,
128
3x3
conv,
128
...
3x3
conv,
64
3x3
conv,
64
3x3
conv,
64
3x3
conv,
64
3x3
conv,
64
3x3
conv,
64
Pool
FC
1000
Softmax
In between:
Highway Networks
Similar to ResNet!
Srivastava et al, “Highway Networks”,
ICML DL Workshop 2015

[Page contains 1 table(s)]


### Table 1

| Long Short Term Memory (LSTM): Gradient Flow
[Hochreiter et al., 1997]
Uninterrupted gradient flow!
c c c c
0 1 2 3
In between:
Highway Networks
7x7 3x3
3x3 3x3 3x3 3x3 3x3 3x3 3x3 3x3 3x3 3x3 3x3 3x3 3x3 3x3 3x3 3x3 3x3 Similar to ResNet!
conv, conv, FC Softmax
Input Pool conv, conv, conv, conv, conv, conv, conv, conv, conv, conv, conv, conv, conv, conv, conv, conv, conv, Pool
... 1000
64 128
64 64 64 64 64 64 128 128 128 128 128 64 64 64 64 64 64
/ / Srivastava et al, “Highway Networks”,
2 2
ICML DL Workshop 2015 |
| Stanford CS231n 10th Anniversary Lecture 7 - 130 April 22, 2025 |


[Page contains 4 image(s)]


---
## Page 122
---


Modern RNNs
● Sometimes called “state space models”
○ Hidden state
● Main advantages:
○ Unlimited context length
○ Compute scales linearly with sequence length
RWKV Scaling (arXiv)
Stanford CS231n 10th Anniversary Lecture 7 - 131 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Modern RNNs
● Sometimes called “state space models”
○ Hidden state
● Main advantages:
○ Unlimited context length
○ Compute scales linearly with sequence length
RWKV Scaling (arXiv) |
| Stanford CS231n 10th Anniversary Lecture 7 - 131 April 22, 2025 |


[Page contains 3 image(s)]


---
## Page 123
---


Summary
- RNNs allow a lot of flexibility in architecture design
- Vanilla RNNs are simple but don’t work very well
- More complex variants (e.g. LSTMs, Mamba) can introduce ways to
selectively pass information forward
- Backward flow of gradients in RNN can explode or vanish. Exploding
is controlled with gradient clipping. Backpropagation through time
is often needed.
- Better/simpler architectures are a hot topic of current research, as
well as new paradigms for reasoning over sequences
Stanford CS231n 10th Anniversary Lecture 7 - 132 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Summary
- RNNs allow a lot of flexibility in architecture design
- Vanilla RNNs are simple but don’t work very well
- More complex variants (e.g. LSTMs, Mamba) can introduce ways to
selectively pass information forward
- Backward flow of gradients in RNN can explode or vanish. Exploding
is controlled with gradient clipping. Backpropagation through time
is often needed.
- Better/simpler architectures are a hot topic of current research, as
well as new paradigms for reasoning over sequences |
| Stanford CS231n 10th Anniversary Lecture 7 - 132 April 22, 2025 |


---
## Page 124
---


Next time: Attention and Transformers
Stanford CS231n 10th Anniversary Lecture 7 - 133 April 22, 2025

[Page contains 1 table(s)]


### Table 1

| Next time: Attention and Transformers |
| Stanford CS231n 10th Anniversary Lecture 7 - 133 April 22, 2025 |
