# lecture_4

Extracted using pdfplumber



---
## Page 1
---


Lecture 4:
Neural Networks and
Backpropagation
Stanford CS231n 10th Anniversary Lecture 4 - 1 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture 4:
Neural Networks and
Backpropagation |
| Stanford CS231n 10th Anniversary Lecture 4 - 1 April 10, 2025 |


---
## Page 2
---


Administrative: Project Proposal
Due Fri 4/25
TA expertise is posted on the webpage.
(http://cs231n.stanford.edu/office_hours.html)
Stanford CS231n 10th Anniversary Lecture 4 - 3 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Administrative: Project Proposal
Due Fri 4/25
TA expertise is posted on the webpage.
(http://cs231n.stanford.edu/office_hours.html) |
| Stanford CS231n 10th Anniversary Lecture 4 - 3 April 10, 2025 |


---
## Page 3
---


Administrative: Discussion Section
Discussion section tomorrow
(led by Matthew Jin, With Emily Jin’s help):
Backpropagation
Stanford CS231n 10th Anniversary Lecture 4 - 4 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Administrative: Discussion Section
Discussion section tomorrow
(led by Matthew Jin, With Emily Jin’s help):
Backpropagation |
| Stanford CS231n 10th Anniversary Lecture 4 - 4 April 10, 2025 |


---
## Page 4
---


Recap
Stanford CS231n 10th Anniversary Lecture 4 - 5 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Recap |
| Stanford CS231n 10th Anniversary Lecture 4 - 5 April 10, 2025 |


---
## Page 5
---


Recap
- We have some dataset of (x,y)
e.g.
- We have a score function:
- We have a loss function:
Softmax
Full loss
Loss
difference in scores between
correct and incorrect class
SVM/hinge Loss (refer to
Lecture 2 reading assignment )
Stanford CS231n 10th Anniversary Lecture 4 - 6 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Recap
- We have some dataset of (x,y)
e.g.
- We have a score function:
- We have a loss function:
Softmax
Full loss
Loss
difference in scores between
correct and incorrect class
SVM/hinge Loss (refer to
Lecture 2 reading assignment ) |
| Stanford CS231n 10th Anniversary Lecture 4 - 6 April 10, 2025 |


[Page contains 8 image(s)]


---
## Page 6
---


Finding the best W: Optimize with Gradient Descent
Landscape imageis CC0 1.0public domain
Walking man image is CC0 1.0public domain
Stanford CS231n 10th Anniversary Lecture 4 - 7 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Finding the best W: Optimize with Gradient Descent
Landscape imageis CC0 1.0public domain
Walking man image is CC0 1.0public domain |
| Stanford CS231n 10th Anniversary Lecture 4 - 7 April 10, 2025 |


[Page contains 4 image(s)]


---
## Page 7
---


Gradient descent
Numerical gradient: slow , approximate , easy to write ☺
Analytic gradient: fast ☺, exact ☺, error-prone 
In practice: Derive analytic gradient, check your
implementation with numerical gradient
Stanford CS231n 10th Anniversary Lecture 4 - 8 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Gradient descent
Numerical gradient: slow , approximate , easy to write ☺
Analytic gradient: fast ☺, exact ☺, error-prone 
In practice: Derive analytic gradient, check your
implementation with numerical gradient |
| Stanford CS231n 10th Anniversary Lecture 4 - 8 April 10, 2025 |


[Page contains 1 image(s)]


---
## Page 8
---


Stochastic Gradient Descent (SGD)
Full sum is expensive
when N is large!
Approximate sum using
a minibatch of examples
32 / 64 / 128 / 256
Stanford CS231n 10th Anniversary Lecture 4 - 9 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Stochastic Gradient Descent (SGD)
Full sum is expensive
when N is large!
Approximate sum using
a minibatch of examples
32 / 64 / 128 / 256 |
| Stanford CS231n 10th Anniversary Lecture 4 - 9 April 10, 2025 |


[Page contains 3 image(s)]


---
## Page 9
---


Last time: fancy optimizers
SGD
SGD+Momentum
RMSProp
Adam
Stanford CS231n 10th Anniversary Lecture 4 - 10 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Last time: fancy optimizers
SGD
SGD+Momentum
RMSProp
Adam |
| Stanford CS231n 10th Anniversary Lecture 4 - 10 April 10, 2025 |


[Page contains 2 image(s)]


---
## Page 10
---


Last time: learning rate scheduling
Step: Reduce learning rate at a few fixed points.
E.g. for ResNets, multiply LR by 0.1 after epochs
Reduce learning rate
30, 60, and 90.
Cosine:
Linear:
Inverse sqrt:
: Initial learning rate
: Learning rate at epoch t
: Total number of epochs
Stanford CS231n 10th Anniversary Lecture 4 - 11 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Last time: learning rate scheduling
Step: Reduce learning rate at a few fixed points.
E.g. for ResNets, multiply LR by 0.1 after epochs
Reduce learning rate
30, 60, and 90.
Cosine:
Linear:
Inverse sqrt:
: Initial learning rate
: Learning rate at epoch t
: Total number of epochs |
| Stanford CS231n 10th Anniversary Lecture 4 - 11 April 10, 2025 |


[Page contains 7 image(s)]


---
## Page 11
---


Today:
Deep Learning
Stanford CS231n 10th Anniversary Lecture 4 - 12 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Today:
Deep Learning |
| Stanford CS231n 10th Anniversary Lecture 4 - 12 April 10, 2025 |


---
## Page 12
---


DALL-E 2
“Teddy bears working on new AI research on “Rabbits attending a college seminar on “AwisecatmeditatingintheHimalayas
the moon in the 1980s.” human anatomy.” searchingforenlightenment.”
Image source: Sam Altman,https://openai.com/dall-e-2/,https://twitter.com/sama/status/1511724264629678084
Stanford CS231n 10th Anniversary Lecture 4 - 13 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| DALL-E 2
“Teddy bears working on new AI research on “Rabbits attending a college seminar on “AwisecatmeditatingintheHimalayas
the moon in the 1980s.” human anatomy.” searchingforenlightenment.”
Image source: Sam Altman,https://openai.com/dall-e-2/,https://twitter.com/sama/status/1511724264629678084 |
| Stanford CS231n 10th Anniversary Lecture 4 - 13 April 10, 2025 |


[Page contains 3 image(s)]


---
## Page 13
---


Ramesh et al., Hierarchical Text-Conditional Image
Generation with CLIP Latents, 2022.
Stanford CS231n 10th Anniversary Lecture 4 - 14 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Ramesh et al., Hierarchical Text-Conditional Image
Generation with CLIP Latents, 2022. |
| Stanford CS231n 10th Anniversary Lecture 4 - 14 April 10, 2025 |


[Page contains 2 image(s)]


---
## Page 14
---


DALL-E 3
In a fantastical setting, a
highly detailed furry
humanoid skunk with
piercing eyes confidently
poses in a medium shot,
wearing an animal hide
jacket. The artist has
masterfully rendered the
character in digital art,
capturing the intricate details
of fur and clothing texture.
Betker, James, et al. "Improving image generation
with better captions.” Computer Science. https://cdn.
openai. com/papers/dall-e-3. pdf (2023).
Stanford CS231n 10th Anniversary Lecture 4 - 15 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| DALL-E 3
In a fantastical setting, a
highly detailed furry
humanoid skunk with
piercing eyes confidently
poses in a medium shot,
wearing an animal hide
jacket. The artist has
masterfully rendered the
character in digital art,
capturing the intricate details
of fur and clothing texture.
Betker, James, et al. "Improving image generation
with better captions.” Computer Science. https://cdn.
openai. com/papers/dall-e-3. pdf (2023). |
| Stanford CS231n 10th Anniversary Lecture 4 - 15 April 10, 2025 |


[Page contains 1 image(s)]


---
## Page 15
---


DALL-E 3
An illustration from a graphic novel.
A bustling city street under the shine
of a full moon. The sidewalks
bustling with pedestrians enjoying
the nightlife. At the corner stall, a
young woman with fiery red hair,
dressed in a signature velvet cloak, is
haggling with the grumpy old
vendor. The grumpy vendor, a tall,
sophisticated man wearing a sharp
suit, who sports a noteworthy
mustache is animatedly conversing
on his steampunk telephone.
Betker, James, et al. "Improving image generation
with better captions.” Computer Science. https://cdn.
openai. com/papers/dall-e-3. pdf (2023).
Stanford CS231n 10th Anniversary Lecture 4 - 16 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| DALL-E 3
An illustration from a graphic novel.
A bustling city street under the shine
of a full moon. The sidewalks
bustling with pedestrians enjoying
the nightlife. At the corner stall, a
young woman with fiery red hair,
dressed in a signature velvet cloak, is
haggling with the grumpy old
vendor. The grumpy vendor, a tall,
sophisticated man wearing a sharp
suit, who sports a noteworthy
mustache is animatedly conversing
on his steampunk telephone.
Betker, James, et al. "Improving image generation
with better captions.” Computer Science. https://cdn.
openai. com/papers/dall-e-3. pdf (2023). |
| Stanford CS231n 10th Anniversary Lecture 4 - 16 April 10, 2025 |


[Page contains 1 image(s)]


---
## Page 16
---


GPT-4
Image source: https://openai.com/research/gpt-4
Stanford CS231n 10th Anniversary Lecture 4 - 17 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| GPT-4
Image source: https://openai.com/research/gpt-4 |
| Stanford CS231n 10th Anniversary Lecture 4 - 17 April 10, 2025 |


[Page contains 2 image(s)]


---
## Page 17
---


Segment Anything Model (SAM)
Kirillov et al., Segment Anything, 2023
Stanford CS231n 10th Anniversary Lecture 4 - 18 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Segment Anything Model (SAM)
Kirillov et al., Segment Anything, 2023 |
| Stanford CS231n 10th Anniversary Lecture 4 - 18 April 10, 2025 |


[Page contains 1 image(s)]


---
## Page 18
---


Sora
https://openai.com/research/video-generation-models-as-world-simulators
Stanford CS231n 10th Anniversary Lecture 4 - 19 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Sora
https://openai.com/research/video-generation-models-as-world-simulators |
| Stanford CS231n 10th Anniversary Lecture 4 - 19 April 10, 2025 |


[Page contains 1 image(s)]


---
## Page 19
---


Sora
● Animating Images
(generated by DALL-E)
● Video-to-video editing
A Shiba Inudog wearing a beret and black turtleneck.
change the video setting to be different than
put the video in space with a rainbow road
a mountain? perhaps joshuatree
https://openai.com/research/video-generation-models-as-world-simulators
Stanford CS231n 10th Anniversary Lecture 4 - 20 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Sora
● Animating Images
(generated by DALL-E)
● Video-to-video editing
A Shiba Inudog wearing a beret and black turtleneck.
change the video setting to be different than
put the video in space with a rainbow road
a mountain? perhaps joshuatree
https://openai.com/research/video-generation-models-as-world-simulators |
| Stanford CS231n 10th Anniversary Lecture 4 - 20 April 10, 2025 |


[Page contains 5 image(s)]


---
## Page 20
---


Sora
● More compute
Base Compute 4x Compute 32x Compute
https://openai.com/research/video-generation-models-as-world-simulators
Stanford CS231n 10th Anniversary Lecture 4 - 21 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Sora
● More compute
Base Compute 4x Compute 32x Compute
https://openai.com/research/video-generation-models-as-world-simulators |
| Stanford CS231n 10th Anniversary Lecture 4 - 21 April 10, 2025 |


[Page contains 3 image(s)]


---
## Page 21
---


Neural Networks
Stanford CS231n 10th Anniversary Lecture 4 - 22 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Neural Networks |
| Stanford CS231n 10th Anniversary Lecture 4 - 22 April 10, 2025 |


---
## Page 22
---


Neural networks: the original linear classifier
(Before) Linear score function:
Stanford CS231n 10th Anniversary Lecture 4 - 23 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Neural networks: the original linear classifier
(Before) Linear score function: |
| Stanford CS231n 10th Anniversary Lecture 4 - 23 April 10, 2025 |


[Page contains 2 image(s)]


---
## Page 23
---


Neural networks: 2 layers
(Before) Linear score function:
(Now) 2-layer Neural Network
(In practice we will usually add a learnable bias at each layer as well)
Stanford CS231n 10th Anniversary Lecture 4 - 24 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Neural networks: 2 layers
(Before) Linear score function:
(Now) 2-layer Neural Network
(In practice we will usually add a learnable bias at each layer as well) |
| Stanford CS231n 10th Anniversary Lecture 4 - 24 April 10, 2025 |


[Page contains 3 image(s)]


---
## Page 24
---


Why do we want non-linearity?
y
x
Cannot separate red and
blue points with linear
classifier
Stanford CS231n 10th Anniversary Lecture 4 - 25 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Why do we want non-linearity?
y
x
Cannot separate red and
blue points with linear
classifier |
| Stanford CS231n 10th Anniversary Lecture 4 - 25 April 10, 2025 |


---
## Page 25
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
Stanford CS231n 10th Anniversary Lecture 4 - 26 April 10, 2025

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
| Stanford CS231n 10th Anniversary Lecture 4 - 26 April 10, 2025 |


---
## Page 26
---


Neural networks: also called fully connected network
(Before) Linear score function:
(Now) 2-layer Neural Network
“Neural Network” is a very broad term; these are more accurately called
“fully-connected networks” or sometimes “multi-layer perceptrons” (MLP)
(In practice we will usually add a learnable bias at each layer as well)
Stanford CS231n 10th Anniversary Lecture 4 - 27 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Neural networks: also called fully connected network
(Before) Linear score function:
(Now) 2-layer Neural Network
“Neural Network” is a very broad term; these are more accurately called
“fully-connected networks” or sometimes “multi-layer perceptrons” (MLP)
(In practice we will usually add a learnable bias at each layer as well) |
| Stanford CS231n 10th Anniversary Lecture 4 - 27 April 10, 2025 |


[Page contains 3 image(s)]


---
## Page 27
---


Neural networks: 3 layers
(Before) Linear score function:
(Now) 2-layer Neural Network
or 3-layer Neural Network
(In practice we will usually add a learnable bias at each layer as well)
Stanford CS231n 10th Anniversary Lecture 4 - 28 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Neural networks: 3 layers
(Before) Linear score function:
(Now) 2-layer Neural Network
or 3-layer Neural Network
(In practice we will usually add a learnable bias at each layer as well) |
| Stanford CS231n 10th Anniversary Lecture 4 - 28 April 10, 2025 |


[Page contains 4 image(s)]


---
## Page 28
---


Neural networks: hierarchical computation
(Before) Linear score function:
(Now) 2-layer Neural Network
x W1 h W2 s
10
3072 100
Stanford CS231n 10th Anniversary Lecture 4 - 29 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Neural networks: hierarchical computation
(Before) Linear score function:
(Now) 2-layer Neural Network
x W1 h W2 s
10
3072 100 |
| Stanford CS231n 10th Anniversary Lecture 4 - 29 April 10, 2025 |


[Page contains 3 image(s)]


---
## Page 29
---


Neural networks: learning 100s of templates
(Before) Linear score function:
(Now) 2-layer Neural Network
x W1 h W2 s
10
3072 100
Learn 100 templates instead of 10. Share templates between classes
Stanford CS231n 10th Anniversary Lecture 4 - 30 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Neural networks: learning 100s of templates
(Before) Linear score function:
(Now) 2-layer Neural Network
x W1 h W2 s
10
3072 100
Learn 100 templates instead of 10. Share templates between classes |
| Stanford CS231n 10th Anniversary Lecture 4 - 30 April 10, 2025 |


[Page contains 3 image(s)]


---
## Page 30
---


Neural networks: why is max operator important?
(Before) Linear score function:
(Now) 2-layer Neural Network
The function. is called the activation function.
Q: What if we try to build a neural network without one?
Stanford CS231n 10th Anniversary Lecture 4 - 31 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Neural networks: why is max operator important?
(Before) Linear score function:
(Now) 2-layer Neural Network
The function. is called the activation function.
Q: What if we try to build a neural network without one? |
| Stanford CS231n 10th Anniversary Lecture 4 - 31 April 10, 2025 |


[Page contains 4 image(s)]


---
## Page 31
---


Neural networks: why is max operator important?
(Before) Linear score function:
(Now) 2-layer Neural Network
The function is called the activation function.
Q: What if we try to build a neural network without one?
A: We end up with a linear classifier again!
Stanford CS231n 10th Anniversary Lecture 4 - 32 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Neural networks: why is max operator important?
(Before) Linear score function:
(Now) 2-layer Neural Network
The function is called the activation function.
Q: What if we try to build a neural network without one?
A: We end up with a linear classifier again! |
| Stanford CS231n 10th Anniversary Lecture 4 - 32 April 10, 2025 |


[Page contains 5 image(s)]


---
## Page 32
---


ReLU is a good default
Activation functions
choice for most problems
Stanford CS231n 10th Anniversary Lecture 4 - 33 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| ReLU is a good default
Activation functions
choice for most problems |
| Stanford CS231n 10th Anniversary Lecture 4 - 33 April 10, 2025 |


[Page contains 14 image(s)]


---
## Page 33
---


Neural networks: Architectures
“3-layer Neural Net”, or
“2-layer Neural Net”, or “2-hidden-layer Neural Net”
“1-hidden-layer Neural Net”
“Fully-connected” layers
Stanford CS231n 10th Anniversary Lecture 4 - 34 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Neural networks: Architectures
“3-layer Neural Net”, or
“2-layer Neural Net”, or “2-hidden-layer Neural Net”
“1-hidden-layer Neural Net”
“Fully-connected” layers |
| Stanford CS231n 10th Anniversary Lecture 4 - 34 April 10, 2025 |


[Page contains 2 image(s)]


---
## Page 34
---


Example feed-forward computation of a neural network
Stanford CS231n 10th Anniversary Lecture 4 - 35 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Example feed-forward computation of a neural network |
| Stanford CS231n 10th Anniversary Lecture 4 - 35 April 10, 2025 |


[Page contains 2 image(s)]


---
## Page 35
---


Full implementation of training a 2-layer Neural Network needs ~20 lines:
Stanford CS231n 10th Anniversary Lecture 4 - 36 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Full implementation of training a 2-layer Neural Network needs ~20 lines: |
| Stanford CS231n 10th Anniversary Lecture 4 - 36 April 10, 2025 |


[Page contains 1 image(s)]


---
## Page 36
---


Full implementation of training a 2-layer Neural Network needs ~20 lines:
Define the network
Stanford CS231n 10th Anniversary Lecture 4 - 37 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Full implementation of training a 2-layer Neural Network needs ~20 lines:
Define the network |
| Stanford CS231n 10th Anniversary Lecture 4 - 37 April 10, 2025 |


[Page contains 1 image(s)]


---
## Page 37
---


Full implementation of training a 2-layer Neural Network needs ~20 lines:
Define the network
Forward pass
Stanford CS231n 10th Anniversary Lecture 4 - 38 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Full implementation of training a 2-layer Neural Network needs ~20 lines:
Define the network
Forward pass |
| Stanford CS231n 10th Anniversary Lecture 4 - 38 April 10, 2025 |


[Page contains 1 image(s)]


---
## Page 38
---


Full implementation of training a 2-layer Neural Network needs ~20 lines:
Define the network
Forward pass
Calculate the analytical gradients
Stanford CS231n 10th Anniversary Lecture 4 - 39 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Full implementation of training a 2-layer Neural Network needs ~20 lines:
Define the network
Forward pass
Calculate the analytical gradients |
| Stanford CS231n 10th Anniversary Lecture 4 - 39 April 10, 2025 |


[Page contains 1 image(s)]


---
## Page 39
---


Full implementation of training a 2-layer Neural Network needs ~20 lines:
Define the network
Forward pass
Calculate the analytical gradients
Gradient descent
Stanford CS231n 10th Anniversary Lecture 4 - 40 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Full implementation of training a 2-layer Neural Network needs ~20 lines:
Define the network
Forward pass
Calculate the analytical gradients
Gradient descent |
| Stanford CS231n 10th Anniversary Lecture 4 - 40 April 10, 2025 |


[Page contains 1 image(s)]


---
## Page 40
---


Setting the number of layers and their sizes
more neurons = more capacity
Stanford CS231n 10th Anniversary Lecture 4 - 41 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Setting the number of layers and their sizes
more neurons = more capacity |
| Stanford CS231n 10th Anniversary Lecture 4 - 41 April 10, 2025 |


[Page contains 1 image(s)]


---
## Page 41
---


Do not use size of neural network as a regularizer. Use stronger regularization instead:
(Web demo with ConvNetJS:
http://cs.stanford.edu/people/karpathy/convnetjs/demo/classify2d.html)
TensorFlow Play Ground: https://playground.tensorflow.org/
Stanford CS231n 10th Anniversary Lecture 4 - 42 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Do not use size of neural network as a regularizer. Use stronger regularization instead:
(Web demo with ConvNetJS:
http://cs.stanford.edu/people/karpathy/convnetjs/demo/classify2d.html)
TensorFlow Play Ground: https://playground.tensorflow.org/ |
| Stanford CS231n 10th Anniversary Lecture 4 - 42 April 10, 2025 |


[Page contains 2 image(s)]


---
## Page 42
---


This imageby Fotis Bobolasis licensed under CC-BY 2.0
Stanford CS231n 10th Anniversary Lecture 4 - 43 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| This imageby Fotis Bobolasis licensed under CC-BY 2.0 |
| Stanford CS231n 10th Anniversary Lecture 4 - 43 April 10, 2025 |


[Page contains 1 image(s)]


---
## Page 43
---


Impulses carried toward cell body
dendrite
presynaptic
terminal
axon
cell body
Impulses carried away
from cell body
This imageby Felipe Perucho
is licensed under CC-BY 3.0
Stanford CS231n 10th Anniversary Lecture 4 - 44 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Impulses carried toward cell body
dendrite
presynaptic
terminal
axon
cell body
Impulses carried away
from cell body
This imageby Felipe Perucho
is licensed under CC-BY 3.0 |
| Stanford CS231n 10th Anniversary Lecture 4 - 44 April 10, 2025 |


[Page contains 1 image(s)]


---
## Page 44
---


Impulses carried toward cell body
dendrite
presynaptic
terminal
axon
cell body
Impulses carried away
from cell body
This imageby Felipe Perucho
is licensed under CC-BY 3.0
Stanford CS231n 10th Anniversary Lecture 4 - 45 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Impulses carried toward cell body
dendrite
presynaptic
terminal
axon
cell body
Impulses carried away
from cell body
This imageby Felipe Perucho
is licensed under CC-BY 3.0 |
| Stanford CS231n 10th Anniversary Lecture 4 - 45 April 10, 2025 |


[Page contains 2 image(s)]


---
## Page 45
---


Impulses carried toward cell body
dendrite
presynaptic
terminal
axon
cell body
Impulses carried away
from cell body
This imageby Felipe Perucho
is licensed under CC-BY 3.0
sigmoid activation function
Stanford CS231n 10th Anniversary Lecture 4 - 46 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Impulses carried toward cell body
dendrite
presynaptic
terminal
axon
cell body
Impulses carried away
from cell body
This imageby Felipe Perucho
is licensed under CC-BY 3.0
sigmoid activation function |
| Stanford CS231n 10th Anniversary Lecture 4 - 46 April 10, 2025 |


[Page contains 4 image(s)]


---
## Page 46
---


Biological Neurons: Neurons in a neural network:
Complex connectivity patterns Organized into regular layers for
computational efficiency
This imageis CC0 Public Domain
Stanford CS231n 10th Anniversary Lecture 4 - 48 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Biological Neurons: Neurons in a neural network:
Complex connectivity patterns Organized into regular layers for
computational efficiency
This imageis CC0 Public Domain |
| Stanford CS231n 10th Anniversary Lecture 4 - 48 April 10, 2025 |


[Page contains 2 image(s)]


---
## Page 47
---


Biological Neurons: But neural networks with random
Complex connectivity patterns connections can work too!
This imageis CC0 Public Domain
Xieet al, “Exploring Randomly Wired Neural Networks for Image Recognition”, IEEE/CVF
International Conference on Computer Vision2019
Stanford CS231n 10th Anniversary Lecture 4 - 49 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Biological Neurons: But neural networks with random
Complex connectivity patterns connections can work too!
This imageis CC0 Public Domain
Xieet al, “Exploring Randomly Wired Neural Networks for Image Recognition”, IEEE/CVF
International Conference on Computer Vision2019 |
| Stanford CS231n 10th Anniversary Lecture 4 - 49 April 10, 2025 |


[Page contains 2 image(s)]


---
## Page 48
---


Be very careful with your brain analogies!
Biological Neurons:
● Many different types
● Dendrites can perform complex non-linear computations
● Synapses are not a single weight but a complex non-linear dynamical system
[Dendritic Computation. London and Hausser]
Stanford CS231n 10th Anniversary Lecture 4 - 50 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Be very careful with your brain analogies!
Biological Neurons:
● Many different types
● Dendrites can perform complex non-linear computations
● Synapses are not a single weight but a complex non-linear dynamical system
[Dendritic Computation. London and Hausser] |
| Stanford CS231n 10th Anniversary Lecture 4 - 50 April 10, 2025 |


---
## Page 49
---


Plugging in neural networks with loss functions
Nonlinear score function
Hinge Loss on predictions
Regularization
Total loss: data loss + regularization
Stanford CS231n 10th Anniversary Lecture 4 - 51 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Plugging in neural networks with loss functions
Nonlinear score function
Hinge Loss on predictions
Regularization
Total loss: data loss + regularization |
| Stanford CS231n 10th Anniversary Lecture 4 - 51 April 10, 2025 |


[Page contains 1 image(s)]


---
## Page 50
---


Problem: How to compute gradients?
Nonlinear score function
Hinge Loss on predictions
Regularization
Total loss: data loss + regularization
If we can compute then we can learn W and W
1 2
Stanford CS231n 10th Anniversary Lecture 4 - 52 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Problem: How to compute gradients?
Nonlinear score function
Hinge Loss on predictions
Regularization
Total loss: data loss + regularization
If we can compute then we can learn W and W
1 2 |
| Stanford CS231n 10th Anniversary Lecture 4 - 52 April 10, 2025 |


[Page contains 2 image(s)]


---
## Page 51
---


(Bad) Idea: Derive on paper
Problem: Very tedious: Lots of matrix
calculus, need lots of paper
Problem: What if we want to
change loss? E.g. use softmax
instead of hinge? Need to re-derive
everything from scratch!
Problem: Not feasible for very
complex models!
Stanford CS231n 10th Anniversary Lecture 4 - 53 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| (Bad) Idea: Derive on paper
Problem: Very tedious: Lots of matrix
calculus, need lots of paper
Problem: What if we want to
change loss? E.g. use softmax
instead of hinge? Need to re-derive
everything from scratch!
Problem: Not feasible for very
complex models! |
| Stanford CS231n 10th Anniversary Lecture 4 - 53 April 10, 2025 |


[Page contains 2 image(s)]


---
## Page 52
---


Better Idea: Computational graphs + Backpropagation
x
s
(scores)
L
* hinge +
loss
W
R
Stanford CS231n 10th Anniversary Lecture 4 - 54 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Better Idea: Computational graphs + Backpropagation
x
s
(scores)
L
* hinge +
loss
W
R |
| Stanford CS231n 10th Anniversary Lecture 4 - 54 April 10, 2025 |


[Page contains 3 image(s)]


---
## Page 53
---


Convolutional network
(AlexNet)
input image
weights
loss
Figure copyright Alex Krizhevsky, Ilya Sutskever, and
Geoffrey Hinton, 2012. Reproduced with permission.
Stanford CS231n 10th Anniversary Lecture 4 - 55 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Convolutional network
(AlexNet)
input image
weights
loss
Figure copyright Alex Krizhevsky, Ilya Sutskever, and
Geoffrey Hinton, 2012. Reproduced with permission. |
| Stanford CS231n 10th Anniversary Lecture 4 - 55 April 10, 2025 |


[Page contains 1 image(s)]


---
## Page 54
---


Really complex neural
networks!!
input image
loss
Figure reproduced with permission from a Twitter postby Andrej Karpathy.
Stanford CS231n 10th Anniversary Lecture 4 - 56 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Really complex neural
networks!!
input image
loss
Figure reproduced with permission from a Twitter postby Andrej Karpathy. |
| Stanford CS231n 10th Anniversary Lecture 4 - 56 April 10, 2025 |


[Page contains 1 image(s)]


---
## Page 55
---


Neural Turing Machine
Figure reproduced with permission from a Twitter postby Andrej Karpathy.
Stanford CS231n 10th Anniversary Lecture 4 - April 10, 2025

[Page contains 2 table(s)]


### Table 1

| Neural Turing Machine
Figure reproduced with permission from a Twitter postby Andrej Karpathy. |
| Stanford CS231n 10th Anniversary Lecture 4 - April 10, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |  |  | e |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |


[Page contains 17 image(s)]


---
## Page 56
---


Solution: Backpropagation
Stanford CS231n 10th Anniversary Lecture 4 - 58 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Solution: Backpropagation |
| Stanford CS231n 10th Anniversary Lecture 4 - 58 April 10, 2025 |


---
## Page 57
---


Backpropagation: a simple example
Stanford CS231n 10th Anniversary Lecture 4 - 59 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backpropagation: a simple example |
| Stanford CS231n 10th Anniversary Lecture 4 - 59 April 10, 2025 |


[Page contains 1 image(s)]


---
## Page 58
---


Backpropagation: a simple example
Stanford CS231n 10th Anniversary Lecture 4 - 60 April 10, 2025

[Page contains 2 table(s)]


### Table 1

| Backpropagation: a simple example |
| Stanford CS231n 10th Anniversary Lecture 4 - 60 April 10, 2025 |


### Table 2

|  |  |
|  |  |


[Page contains 2 image(s)]


---
## Page 59
---


Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Stanford CS231n 10th Anniversary Lecture 4 - 61 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4 |
| Stanford CS231n 10th Anniversary Lecture 4 - 61 April 10, 2025 |


[Page contains 2 image(s)]


---
## Page 60
---


Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Stanford CS231n 10th Anniversary Lecture 4 - 62 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4 |
| Stanford CS231n 10th Anniversary Lecture 4 - 62 April 10, 2025 |


[Page contains 4 image(s)]


---
## Page 61
---


Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Stanford CS231n 10th Anniversary Lecture 4 - 63 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4 |
| Stanford CS231n 10th Anniversary Lecture 4 - 63 April 10, 2025 |


[Page contains 6 image(s)]


---
## Page 62
---


Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Want:
Stanford CS231n 10th Anniversary Lecture 4 - 64 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Want: |
| Stanford CS231n 10th Anniversary Lecture 4 - 64 April 10, 2025 |


[Page contains 7 image(s)]


---
## Page 63
---


Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Want:
Stanford CS231n 10th Anniversary Lecture 4 - 65 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Want: |
| Stanford CS231n 10th Anniversary Lecture 4 - 65 April 10, 2025 |


[Page contains 8 image(s)]


---
## Page 64
---


Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Want:
Stanford CS231n 10th Anniversary Lecture 4 - 66 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Want: |
| Stanford CS231n 10th Anniversary Lecture 4 - 66 April 10, 2025 |


[Page contains 8 image(s)]


---
## Page 65
---


Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Want:
Stanford CS231n 10th Anniversary Lecture 4 - 67 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Want: |
| Stanford CS231n 10th Anniversary Lecture 4 - 67 April 10, 2025 |


[Page contains 8 image(s)]


---
## Page 66
---


Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Want:
Stanford CS231n 10th Anniversary Lecture 4 - 68 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Want: |
| Stanford CS231n 10th Anniversary Lecture 4 - 68 April 10, 2025 |


[Page contains 8 image(s)]


---
## Page 67
---


Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Want:
Stanford CS231n 10th Anniversary Lecture 4 - 69 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Want: |
| Stanford CS231n 10th Anniversary Lecture 4 - 69 April 10, 2025 |


[Page contains 8 image(s)]


---
## Page 68
---


Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Want:
Stanford CS231n 10th Anniversary Lecture 4 - 70 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Want: |
| Stanford CS231n 10th Anniversary Lecture 4 - 70 April 10, 2025 |


[Page contains 8 image(s)]


---
## Page 69
---


Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Chain rule:
Want:
Upstream Local
gradient gradient
Stanford CS231n 10th Anniversary Lecture 4 - 71 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Chain rule:
Want:
Upstream Local
gradient gradient |
| Stanford CS231n 10th Anniversary Lecture 4 - 71 April 10, 2025 |


[Page contains 11 image(s)]


---
## Page 70
---


Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Chain rule:
Want:
Upstream Local
gradient gradient
Stanford CS231n 10th Anniversary Lecture 4 - 72 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Chain rule:
Want:
Upstream Local
gradient gradient |
| Stanford CS231n 10th Anniversary Lecture 4 - 72 April 10, 2025 |


[Page contains 11 image(s)]


---
## Page 71
---


Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Chain rule:
Want:
Upstream Local
gradient gradient
Stanford CS231n 10th Anniversary Lecture 4 - 73 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Chain rule:
Want:
Upstream Local
gradient gradient |
| Stanford CS231n 10th Anniversary Lecture 4 - 73 April 10, 2025 |


[Page contains 9 image(s)]


---
## Page 72
---


Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Chain rule:
Want:
Upstream Local
gradient gradient
Stanford CS231n 10th Anniversary Lecture 4 - 74 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backpropagation: a simple example
e.g. x = -2, y = 5, z = -4
Chain rule:
Want:
Upstream Local
gradient gradient |
| Stanford CS231n 10th Anniversary Lecture 4 - 74 April 10, 2025 |


[Page contains 9 image(s)]


---
## Page 73
---


f
Stanford CS231n 10th Anniversary Lecture 4 - 75 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| f |
| Stanford CS231n 10th Anniversary Lecture 4 - 75 April 10, 2025 |


[Page contains 3 image(s)]


---
## Page 74
---


“local gradient”
f
Stanford CS231n 10th Anniversary Lecture 4 - 76 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| “local gradient”
f |
| Stanford CS231n 10th Anniversary Lecture 4 - 76 April 10, 2025 |


[Page contains 5 image(s)]


---
## Page 75
---


“local gradient”
f
“Upstream
gradient”
Stanford CS231n 10th Anniversary Lecture 4 - 77 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| “local gradient”
f
“Upstream
gradient” |
| Stanford CS231n 10th Anniversary Lecture 4 - 77 April 10, 2025 |


[Page contains 6 image(s)]


---
## Page 76
---


“local gradient”
f
“Downstream
gradients”
“Upstream
gradient”
Stanford CS231n 10th Anniversary Lecture 4 - 78 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| “local gradient”
f
“Downstream
gradients”
“Upstream
gradient” |
| Stanford CS231n 10th Anniversary Lecture 4 - 78 April 10, 2025 |


[Page contains 7 image(s)]


---
## Page 77
---


“local gradient”
f
“Downstream
gradients”
“Upstream
gradient”
Stanford CS231n 10th Anniversary Lecture 4 - 79 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| “local gradient”
f
“Downstream
gradients”
“Upstream
gradient” |
| Stanford CS231n 10th Anniversary Lecture 4 - 79 April 10, 2025 |


[Page contains 8 image(s)]


---
## Page 78
---


“local gradient”
f
“Downstream
gradients”
“Upstream
gradient”
Stanford CS231n 10th Anniversary Lecture 4 - 80 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| “local gradient”
f
“Downstream
gradients”
“Upstream
gradient” |
| Stanford CS231n 10th Anniversary Lecture 4 - 80 April 10, 2025 |


[Page contains 8 image(s)]


---
## Page 79
---


Another example:
Stanford CS231n 10th Anniversary Lecture 4 - 81 April 10, 2025

[Page contains 4 table(s)]


### Table 1

| Another example: |
| Stanford CS231n 10th Anniversary Lecture 4 - 81 April 10, 2025 |


### Table 2

|  |
|  |
|  |
|  |
|  |


### Table 3

|  |
|  |


### Table 4

|  |
|  |
|  |


[Page contains 2 image(s)]


---
## Page 80
---


Another example:
Stanford CS231n 10th Anniversary Lecture 4 - 82 April 10, 2025

[Page contains 2 table(s)]


### Table 1

| Another example: |
| Stanford CS231n 10th Anniversary Lecture 4 - 82 April 10, 2025 |


### Table 2

|  |
|  |


[Page contains 2 image(s)]


---
## Page 81
---


Another example:
Stanford CS231n 10th Anniversary Lecture 4 - 83 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Another example: |
| Stanford CS231n 10th Anniversary Lecture 4 - 83 April 10, 2025 |


[Page contains 2 image(s)]


---
## Page 82
---


Another example:
Stanford CS231n 10th Anniversary Lecture 4 - 84 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Another example: |
| Stanford CS231n 10th Anniversary Lecture 4 - 84 April 10, 2025 |


[Page contains 4 image(s)]


---
## Page 83
---


Another example:
Stanford CS231n 10th Anniversary Lecture 4 - 85 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Another example: |
| Stanford CS231n 10th Anniversary Lecture 4 - 85 April 10, 2025 |


[Page contains 4 image(s)]


---
## Page 84
---


Another example:
Upstream Local
gradient gradient
Stanford CS231n 10th Anniversary Lecture 4 - 86 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Another example:
Upstream Local
gradient gradient |
| Stanford CS231n 10th Anniversary Lecture 4 - 86 April 10, 2025 |


[Page contains 5 image(s)]


---
## Page 85
---


Another example:
Stanford CS231n 10th Anniversary Lecture 4 - 87 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Another example: |
| Stanford CS231n 10th Anniversary Lecture 4 - 87 April 10, 2025 |


[Page contains 4 image(s)]


---
## Page 86
---


Another example:
Upstream Local
gradient gradient
Stanford CS231n 10th Anniversary Lecture 4 - 88 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Another example:
Upstream Local
gradient gradient |
| Stanford CS231n 10th Anniversary Lecture 4 - 88 April 10, 2025 |


[Page contains 5 image(s)]


---
## Page 87
---


Another example:
Stanford CS231n 10th Anniversary Lecture 4 - 89 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Another example: |
| Stanford CS231n 10th Anniversary Lecture 4 - 89 April 10, 2025 |


[Page contains 4 image(s)]


---
## Page 88
---


Another example:
Upstream Local
gradient gradient
Stanford CS231n 10th Anniversary Lecture 4 - 90 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Another example:
Upstream Local
gradient gradient |
| Stanford CS231n 10th Anniversary Lecture 4 - 90 April 10, 2025 |


[Page contains 5 image(s)]


---
## Page 89
---


Another example:
Stanford CS231n 10th Anniversary Lecture 4 - 91 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Another example: |
| Stanford CS231n 10th Anniversary Lecture 4 - 91 April 10, 2025 |


[Page contains 4 image(s)]


---
## Page 90
---


Another example:
Upstream Local
gradient gradient
Stanford CS231n 10th Anniversary Lecture 4 - 92 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Another example:
Upstream Local
gradient gradient |
| Stanford CS231n 10th Anniversary Lecture 4 - 92 April 10, 2025 |


[Page contains 5 image(s)]


---
## Page 91
---


Another example:
Stanford CS231n 10th Anniversary Lecture 4 - 93 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Another example: |
| Stanford CS231n 10th Anniversary Lecture 4 - 93 April 10, 2025 |


[Page contains 4 image(s)]


---
## Page 92
---


Another example:
[upstream gradient] x [local gradient]
[0.2] x [1] = 0.2
[0.2] x [1] = 0.2 (both inputs!)
Stanford CS231n 10th Anniversary Lecture 4 - 94 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Another example:
[upstream gradient] x [local gradient]
[0.2] x [1] = 0.2
[0.2] x [1] = 0.2 (both inputs!) |
| Stanford CS231n 10th Anniversary Lecture 4 - 94 April 10, 2025 |


[Page contains 4 image(s)]


---
## Page 93
---


Another example:
Stanford CS231n 10th Anniversary Lecture 4 - 95 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Another example: |
| Stanford CS231n 10th Anniversary Lecture 4 - 95 April 10, 2025 |


[Page contains 4 image(s)]


---
## Page 94
---


Another example:
[upstream gradient] x [local gradient]
w0: [0.2] x [-1] = -0.2
x0: [0.2] x [2] = 0.4
Stanford CS231n 10th Anniversary Lecture 4 - 96 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Another example:
[upstream gradient] x [local gradient]
w0: [0.2] x [-1] = -0.2
x0: [0.2] x [2] = 0.4 |
| Stanford CS231n 10th Anniversary Lecture 4 - 96 April 10, 2025 |


[Page contains 4 image(s)]


---
## Page 95
---


Another example: Computational graph
representation may not be
unique. Choose one where
Sigmoid local gradients at each
node can be easily
function
expressed!
Sigmoid
Stanford CS231n 10th Anniversary Lecture 4 - 97 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Another example: Computational graph
representation may not be
unique. Choose one where
Sigmoid local gradients at each
node can be easily
function
expressed!
Sigmoid |
| Stanford CS231n 10th Anniversary Lecture 4 - 97 April 10, 2025 |


[Page contains 3 image(s)]


---
## Page 96
---


Another example: Computational graph
representation may not be
unique. Choose one where
Sigmoid local gradients at each
node can be easily
function
expressed!
Sigmoid
Sigmoid local
gradient:
Stanford CS231n 10th Anniversary Lecture 4 - 98 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Another example: Computational graph
representation may not be
unique. Choose one where
Sigmoid local gradients at each
node can be easily
function
expressed!
Sigmoid
Sigmoid local
gradient: |
| Stanford CS231n 10th Anniversary Lecture 4 - 98 April 10, 2025 |


[Page contains 4 image(s)]


---
## Page 97
---


Another example: Computational graph
representation may not be
unique. Choose one where
Sigmoid local gradients at each
node can be easily
function
expressed!
Sigmoid
[upstream gradient] x [local gradient]
[1.00] x [(1 - 1/(1+e-1)) (1/(1+e-1))] = 0.2
Sigmoid local
gradient:
Stanford CS231n 10th Anniversary Lecture 4 - 99 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Another example: Computational graph
representation may not be
unique. Choose one where
Sigmoid local gradients at each
node can be easily
function
expressed!
Sigmoid
[upstream gradient] x [local gradient]
[1.00] x [(1 - 1/(1+e-1)) (1/(1+e-1))] = 0.2
Sigmoid local
gradient: |
| Stanford CS231n 10th Anniversary Lecture 4 - 99 April 10, 2025 |


[Page contains 4 image(s)]


---
## Page 98
---


Another example: Computational graph
representation may not be
unique. Choose one where
Sigmoid local gradients at each
node can be easily
function
expressed!
Sigmoid
[upstream gradient] x [local gradient]
[1.00] x [(1 - 0.73) (0.73)] = 0.2
Sigmoid local
gradient:
Stanford CS231n 10th Anniversary Lecture 4 - 100 April 10, 2025

[Page contains 2 table(s)]


### Table 1

| Another example: Computational graph
representation may not be
unique. Choose one where
Sigmoid local gradients at each
node can be easily
function
expressed!
Sigmoid
[upstream gradient] x [local gradient]
[1.00] x [(1 - 0.73) (0.73)] = 0.2
Sigmoid local
gradient: |
| Stanford CS231n 10th Anniversary Lecture 4 - 100 April 10, 2025 |


### Table 2

|  |
|  |


[Page contains 4 image(s)]


---
## Page 99
---


Patterns in gradient flow
add gate: gradient distributor
3
2
7
+
2
4
2
Stanford CS231n 10th Anniversary Lecture 4 - 101 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Patterns in gradient flow
add gate: gradient distributor
3
2
7
+
2
4
2 |
| Stanford CS231n 10th Anniversary Lecture 4 - 101 April 10, 2025 |


---
## Page 100
---


Patterns in gradient flow
add gate: gradient distributor mul gate: “swap multiplier”
3 2
2 5*3=15
7 6
+ ×
2 5
4 3
2 2*5=10
Stanford CS231n 10th Anniversary Lecture 4 - 102 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Patterns in gradient flow
add gate: gradient distributor mul gate: “swap multiplier”
3 2
2 5*3=15
7 6
+ ×
2 5
4 3
2 2*5=10 |
| Stanford CS231n 10th Anniversary Lecture 4 - 102 April 10, 2025 |


---
## Page 101
---


Patterns in gradient flow
add gate: gradient distributor mul gate: “swap multiplier”
3 2
2 5*3=15
7 6
+ ×
2 5
4 3
2 2*5=10
copy gate: gradient adder
7
4
7
4+2=6 7
2
Stanford CS231n 10th Anniversary Lecture 4 - 103 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Patterns in gradient flow
add gate: gradient distributor mul gate: “swap multiplier”
3 2
2 5*3=15
7 6
+ ×
2 5
4 3
2 2*5=10
copy gate: gradient adder
7
4
7
4+2=6 7
2 |
| Stanford CS231n 10th Anniversary Lecture 4 - 103 April 10, 2025 |


---
## Page 102
---


Patterns in gradient flow
add gate: gradient distributor mul gate: “swap multiplier”
3 2
2 5*3=15
7 6
+ ×
2 5
4 3
2 2*5=10
copy gate: gradient adder max gate: gradient router
7 4
4 0
7 5
max
4+2=6 7 5 9
2 9
Stanford CS231n 10th Anniversary Lecture 4 - 104 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Patterns in gradient flow
add gate: gradient distributor mul gate: “swap multiplier”
3 2
2 5*3=15
7 6
+ ×
2 5
4 3
2 2*5=10
copy gate: gradient adder max gate: gradient router
7 4
4 0
7 5
max
4+2=6 7 5 9
2 9 |
| Stanford CS231n 10th Anniversary Lecture 4 - 104 April 10, 2025 |


---
## Page 103
---


Backprop Implementation:
“Flat” code
Forward pass:
Compute output
Backward pass:
Compute grads
Stanford CS231n 10th Anniversary Lecture 4 - 105 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop Implementation:
“Flat” code
Forward pass:
Compute output
Backward pass:
Compute grads |
| Stanford CS231n 10th Anniversary Lecture 4 - 105 April 10, 2025 |


[Page contains 3 image(s)]


---
## Page 104
---


Backprop Implementation:
“Flat” code
Forward pass:
Compute output
Base case
Stanford CS231n 10th Anniversary Lecture 4 - 106 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop Implementation:
“Flat” code
Forward pass:
Compute output
Base case |
| Stanford CS231n 10th Anniversary Lecture 4 - 106 April 10, 2025 |


[Page contains 3 image(s)]


---
## Page 105
---


Backprop Implementation:
“Flat” code
Forward pass:
Compute output
Sigmoid
Stanford CS231n 10th Anniversary Lecture 4 - 107 April 10, 2025

[Page contains 2 table(s)]


### Table 1

| Backprop Implementation:
“Flat” code
Forward pass:
Compute output
Sigmoid |
| Stanford CS231n 10th Anniversary Lecture 4 - 107 April 10, 2025 |


### Table 2

|  |
|  |


[Page contains 3 image(s)]


---
## Page 106
---


Backprop Implementation:
“Flat” code
Forward pass:
Compute output
Add gate
Stanford CS231n 10th Anniversary Lecture 4 - 108 April 10, 2025

[Page contains 2 table(s)]


### Table 1

| Backprop Implementation:
“Flat” code
Forward pass:
Compute output
Add gate |
| Stanford CS231n 10th Anniversary Lecture 4 - 108 April 10, 2025 |


### Table 2

|  |  |
|  |  |
|  |  |


[Page contains 3 image(s)]


---
## Page 107
---


Backprop Implementation:
“Flat” code
Forward pass:
Compute output
Add gate
Stanford CS231n 10th Anniversary Lecture 4 - 109 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop Implementation:
“Flat” code
Forward pass:
Compute output
Add gate |
| Stanford CS231n 10th Anniversary Lecture 4 - 109 April 10, 2025 |


[Page contains 3 image(s)]


---
## Page 108
---


Backprop Implementation:
“Flat” code
Forward pass:
Compute output
Multiply gate
Stanford CS231n 10th Anniversary Lecture 4 - 110 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop Implementation:
“Flat” code
Forward pass:
Compute output
Multiply gate |
| Stanford CS231n 10th Anniversary Lecture 4 - 110 April 10, 2025 |


[Page contains 3 image(s)]


---
## Page 109
---


Backprop Implementation:
“Flat” code
Forward pass:
Compute output
Multiply gate
Stanford CS231n 10th Anniversary Lecture 4 - 111 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop Implementation:
“Flat” code
Forward pass:
Compute output
Multiply gate |
| Stanford CS231n 10th Anniversary Lecture 4 - 111 April 10, 2025 |


[Page contains 3 image(s)]


---
## Page 110
---


Modularized implementation: forward / backward API
Gate / Node / Function object: Actual PyTorch code
x
z
Need to cache some
* values for use in
backward
y
(x,y,z are scalars) Upstream
gradient
Multiply upstream
and local gradients
Stanford CS231n 10th Anniversary Lecture 4 - 115 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Modularized implementation: forward / backward API
Gate / Node / Function object: Actual PyTorch code
x
z
Need to cache some
* values for use in
backward
y
(x,y,z are scalars) Upstream
gradient
Multiply upstream
and local gradients |
| Stanford CS231n 10th Anniversary Lecture 4 - 115 April 10, 2025 |


[Page contains 1 image(s)]


---
## Page 111
---


Example: PyTorch operators
Stanford CS231n 10th Anniversary Lecture 4 - 116 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Example: PyTorch operators |
| Stanford CS231n 10th Anniversary Lecture 4 - 116 April 10, 2025 |


[Page contains 2 image(s)]


---
## Page 112
---


PyTorch sigmoid layer
Forward
Source
Stanford CS231n 10th Anniversary Lecture 4 - 117 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| PyTorch sigmoid layer
Forward
Source |
| Stanford CS231n 10th Anniversary Lecture 4 - 117 April 10, 2025 |


[Page contains 2 image(s)]


---
## Page 113
---


PyTorch sigmoid layer
Forward
Forward actually
defined elsewhere...
Source
Stanford CS231n 10th Anniversary Lecture 4 - 118 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| PyTorch sigmoid layer
Forward
Forward actually
defined elsewhere...
Source |
| Stanford CS231n 10th Anniversary Lecture 4 - 118 April 10, 2025 |


[Page contains 4 image(s)]


---
## Page 114
---


PyTorch sigmoid layer
Forward
Forward actually
defined elsewhere...
Backward
Source
Stanford CS231n 10th Anniversary Lecture 4 - 119 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| PyTorch sigmoid layer
Forward
Forward actually
defined elsewhere...
Backward
Source |
| Stanford CS231n 10th Anniversary Lecture 4 - 119 April 10, 2025 |


[Page contains 4 image(s)]


---
## Page 115
---


So far: backprop with scalars
What about vector-valued functions?
Stanford CS231n 10th Anniversary Lecture 4 - 120 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| So far: backprop with scalars
What about vector-valued functions? |
| Stanford CS231n 10th Anniversary Lecture 4 - 120 April 10, 2025 |


---
## Page 116
---


Recap: Vector derivatives
Scalar to Scalar
Regular derivative:
If x changes by a
small amount, how
much will y change?
Stanford CS231n 10th Anniversary Lecture 4 - 121 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Recap: Vector derivatives
Scalar to Scalar
Regular derivative:
If x changes by a
small amount, how
much will y change? |
| Stanford CS231n 10th Anniversary Lecture 4 - 121 April 10, 2025 |


[Page contains 2 image(s)]


---
## Page 117
---


Recap: Vector derivatives
Scalar to Scalar Vector to Scalar
Regular derivative: Derivative is Gradient:
If x changes by a For each element of x, if
small amount, how it changes by a small
much will y change? amount then how much
will y change?
Stanford CS231n 10th Anniversary Lecture 4 - 122 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Recap: Vector derivatives
Scalar to Scalar Vector to Scalar
Regular derivative: Derivative is Gradient:
If x changes by a For each element of x, if
small amount, how it changes by a small
much will y change? amount then how much
will y change? |
| Stanford CS231n 10th Anniversary Lecture 4 - 122 April 10, 2025 |


[Page contains 5 image(s)]


---
## Page 118
---


Recap: Vector derivatives
Scalar to Scalar Vector to Scalar Vector to Vector
Regular derivative: Derivative is Gradient: Derivative is Jacobian:
If x changes by a For each element of x, if For each element of x, if it
small amount, how it changes by a small changes by a small amount
much will y change? amount then how much then how much will each
will y change? element of y change?
Stanford CS231n 10th Anniversary Lecture 4 - 123 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Recap: Vector derivatives
Scalar to Scalar Vector to Scalar Vector to Vector
Regular derivative: Derivative is Gradient: Derivative is Jacobian:
If x changes by a For each element of x, if For each element of x, if it
small amount, how it changes by a small changes by a small amount
much will y change? amount then how much then how much will each
will y change? element of y change? |
| Stanford CS231n 10th Anniversary Lecture 4 - 123 April 10, 2025 |


[Page contains 8 image(s)]


---
## Page 119
---


Backprop with Vectors
Loss L still a scalar!
f
Stanford CS231n 10th Anniversary Lecture 4 - 124 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Vectors
Loss L still a scalar!
f |
| Stanford CS231n 10th Anniversary Lecture 4 - 124 April 10, 2025 |


[Page contains 3 image(s)]


---
## Page 120
---


Backprop with Vectors
Loss L still a scalar!
D
x
D
z
f
D
y
Stanford CS231n 10th Anniversary Lecture 4 - 125 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Vectors
Loss L still a scalar!
D
x
D
z
f
D
y |
| Stanford CS231n 10th Anniversary Lecture 4 - 125 April 10, 2025 |


[Page contains 3 image(s)]


---
## Page 121
---


Backprop with Vectors
Loss L still a scalar!
D
x
D
z
f
D
y
“Upstream gradient”
Stanford CS231n 10th Anniversary Lecture 4 - 126 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Vectors
Loss L still a scalar!
D
x
D
z
f
D
y
“Upstream gradient” |
| Stanford CS231n 10th Anniversary Lecture 4 - 126 April 10, 2025 |


[Page contains 4 image(s)]


---
## Page 122
---


Backprop with Vectors
Loss L still a scalar!
D
x
D
z
f
D
D z
y
“Upstream gradient”
For each element of z, how
much does it influence L?
Stanford CS231n 10th Anniversary Lecture 4 - 127 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Vectors
Loss L still a scalar!
D
x
D
z
f
D
D z
y
“Upstream gradient”
For each element of z, how
much does it influence L? |
| Stanford CS231n 10th Anniversary Lecture 4 - 127 April 10, 2025 |


[Page contains 4 image(s)]


---
## Page 123
---


Backprop with Vectors
Loss L still a scalar!
D
“local
x
gradients”
D
z
f
“Downstream
gradients”
D
D z
y
“Upstream gradient”
For each element of z, how
much does it influence L?
Stanford CS231n 10th Anniversary Lecture 4 - 128 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Vectors
Loss L still a scalar!
D
“local
x
gradients”
D
z
f
“Downstream
gradients”
D
D z
y
“Upstream gradient”
For each element of z, how
much does it influence L? |
| Stanford CS231n 10th Anniversary Lecture 4 - 128 April 10, 2025 |


[Page contains 8 image(s)]


---
## Page 124
---


Backprop with Vectors
Loss L still a scalar!
D
“local
x
gradients”
[D x D ]
D
x z
z
f
“Downstream
gradients”
[D x D ]
y z
D
D z
Jacobian
y
matrices
“Upstream gradient”
For each element of z, how
much does it influence L?
Stanford CS231n 10th Anniversary Lecture 4 - 129 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Vectors
Loss L still a scalar!
D
“local
x
gradients”
[D x D ]
D
x z
z
f
“Downstream
gradients”
[D x D ]
y z
D
D z
Jacobian
y
matrices
“Upstream gradient”
For each element of z, how
much does it influence L? |
| Stanford CS231n 10th Anniversary Lecture 4 - 129 April 10, 2025 |


[Page contains 8 image(s)]


---
## Page 125
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
Stanford CS231n 10th Anniversary Lecture 4 - 130 April 10, 2025

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
| Stanford CS231n 10th Anniversary Lecture 4 - 130 April 10, 2025 |


[Page contains 8 image(s)]


---
## Page 126
---


Gradients of variables wrt loss have same dims as the original variable
Loss L still a scalar!
D
x
D
x D
z
f
D
D z
y
“Upstream gradient”
D For each element of z, how
y
much does it influence L?
Stanford CS231n 10th Anniversary Lecture 4 - 131 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Gradients of variables wrt loss have same dims as the original variable
Loss L still a scalar!
D
x
D
x D
z
f
D
D z
y
“Upstream gradient”
D For each element of z, how
y
much does it influence L? |
| Stanford CS231n 10th Anniversary Lecture 4 - 131 April 10, 2025 |


[Page contains 6 image(s)]


---
## Page 127
---


Backprop with Vectors
4D input x: 4D output z:
[ 1 ] [ 1 ]
[ -2 ] [ 0 ]
f(x) = max(0,x)
[ 3 ] [ 3 ]
(elementwise)
[ -1 ] [ 0 ]
Stanford CS231n 10th Anniversary Lecture 4 - 132 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Vectors
4D input x: 4D output z:
[ 1 ] [ 1 ]
[ -2 ] [ 0 ]
f(x) = max(0,x)
[ 3 ] [ 3 ]
(elementwise)
[ -1 ] [ 0 ] |
| Stanford CS231n 10th Anniversary Lecture 4 - 132 April 10, 2025 |


---
## Page 128
---


Backprop with Vectors
4D input x: 4D output z:
[ 1 ] [ 1 ]
[ -2 ] [ 0 ]
f(x) = max(0,x)
[ 3 ] [ 3 ]
(elementwise)
[ -1 ] [ 0 ]
4D dL/dz:
[ 4 ]
[ -1 ] Upstream
[ 5 ] gradient
[ 9 ]
Stanford CS231n 10th Anniversary Lecture 4 - 133 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Vectors
4D input x: 4D output z:
[ 1 ] [ 1 ]
[ -2 ] [ 0 ]
f(x) = max(0,x)
[ 3 ] [ 3 ]
(elementwise)
[ -1 ] [ 0 ]
4D dL/dz:
[ 4 ]
[ -1 ] Upstream
[ 5 ] gradient
[ 9 ] |
| Stanford CS231n 10th Anniversary Lecture 4 - 133 April 10, 2025 |


---
## Page 129
---


Backprop with Vectors
4D input x: 4D output z:
[ 1 ] [ 1 ]
[ -2 ] [ 0 ]
f(x) = max(0,x)
[ 3 ] [ 3 ]
(elementwise)
[ -1 ] [ 0 ]
Jacobian dz/dx 4D dL/dz:
[ 1 0 0 0 ] [ 4 ]
[ 0 0 0 0 ] [ -1 ] Upstream
[ 0 0 1 0 ] [ 5 ] gradient
[ 0 0 0 0 ] [ 9 ]
Stanford CS231n 10th Anniversary Lecture 4 - 134 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Vectors
4D input x: 4D output z:
[ 1 ] [ 1 ]
[ -2 ] [ 0 ]
f(x) = max(0,x)
[ 3 ] [ 3 ]
(elementwise)
[ -1 ] [ 0 ]
Jacobian dz/dx 4D dL/dz:
[ 1 0 0 0 ] [ 4 ]
[ 0 0 0 0 ] [ -1 ] Upstream
[ 0 0 1 0 ] [ 5 ] gradient
[ 0 0 0 0 ] [ 9 ] |
| Stanford CS231n 10th Anniversary Lecture 4 - 134 April 10, 2025 |


---
## Page 130
---


Backprop with Vectors
4D input x: 4D output z:
[ 1 ] [ 1 ]
[ -2 ] [ 0 ]
f(x) = max(0,x)
[ 3 ] [ 3 ]
(elementwise)
[ -1 ] [ 0 ]
[dz/dx] [dL/dz] 4D dL/dz:
[ 1 0 0 0 ] [ 4 ] [ 4 ]
[ 0 0 0 0 ] [ -1 ] [ -1 ] Upstream
[ 0 0 1 0 ] [ 5 ] [ 5 ] gradient
[ 0 0 0 0 ] [ 9 ] [ 9 ]
Stanford CS231n 10th Anniversary Lecture 4 - 135 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Vectors
4D input x: 4D output z:
[ 1 ] [ 1 ]
[ -2 ] [ 0 ]
f(x) = max(0,x)
[ 3 ] [ 3 ]
(elementwise)
[ -1 ] [ 0 ]
[dz/dx] [dL/dz] 4D dL/dz:
[ 1 0 0 0 ] [ 4 ] [ 4 ]
[ 0 0 0 0 ] [ -1 ] [ -1 ] Upstream
[ 0 0 1 0 ] [ 5 ] [ 5 ] gradient
[ 0 0 0 0 ] [ 9 ] [ 9 ] |
| Stanford CS231n 10th Anniversary Lecture 4 - 135 April 10, 2025 |


---
## Page 131
---


Backprop with Vectors
4D input x: 4D output z:
[ 1 ] [ 1 ]
[ -2 ] [ 0 ]
f(x) = max(0,x)
[ 3 ] [ 3 ]
(elementwise)
[ -1 ] [ 0 ]
4D dL/dx: [dz/dx] [dL/dz] 4D dL/dz:
[ 4 ] [ 1 0 0 0 ] [ 4 ] [ 4 ]
[ 0 ] [ 0 0 0 0 ] [ -1 ] [ -1 ] Upstream
[ 5 ] [ 0 0 1 0 ] [ 5 ] [ 5 ] gradient
[ 0 ] [ 0 0 0 0 ] [ 9 ] [ 9 ]
Stanford CS231n 10th Anniversary Lecture 4 - 136 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Vectors
4D input x: 4D output z:
[ 1 ] [ 1 ]
[ -2 ] [ 0 ]
f(x) = max(0,x)
[ 3 ] [ 3 ]
(elementwise)
[ -1 ] [ 0 ]
4D dL/dx: [dz/dx] [dL/dz] 4D dL/dz:
[ 4 ] [ 1 0 0 0 ] [ 4 ] [ 4 ]
[ 0 ] [ 0 0 0 0 ] [ -1 ] [ -1 ] Upstream
[ 5 ] [ 0 0 1 0 ] [ 5 ] [ 5 ] gradient
[ 0 ] [ 0 0 0 0 ] [ 9 ] [ 9 ] |
| Stanford CS231n 10th Anniversary Lecture 4 - 136 April 10, 2025 |


---
## Page 132
---


Backprop with Vectors
4D input x: 4D output z:
[ 1 ] [ 1 ]
[ -2 ] [ 0 ]
f(x) = max(0,x)
Jacobian is sparse:
[ 3 ] [ 3 ]
(elementwise)
off-diagonal entries
[ -1 ] [ 0 ]
always zero! Never
explicitly form
Jacobian --instead
4D dL/dx: [dz/dx] [dL/dz] 4D dL/dz:
use implicit
multiplication [ 4 ] [ 1 0 0 0 ] [ 4 ] [ 4 ]
[ 0 ] [ 0 0 0 0 ] [ -1 ] [ -1 ] Upstream
[ 5 ] [ 0 0 1 0 ] [ 5 ] [ 5 ] gradient
[ 0 ] [ 0 0 0 0 ] [ 9 ] [ 9 ]
Stanford CS231n 10th Anniversary Lecture 4 - 137 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Vectors
4D input x: 4D output z:
[ 1 ] [ 1 ]
[ -2 ] [ 0 ]
f(x) = max(0,x)
Jacobian is sparse:
[ 3 ] [ 3 ]
(elementwise)
off-diagonal entries
[ -1 ] [ 0 ]
always zero! Never
explicitly form
Jacobian --instead
4D dL/dx: [dz/dx] [dL/dz] 4D dL/dz:
use implicit
multiplication [ 4 ] [ 1 0 0 0 ] [ 4 ] [ 4 ]
[ 0 ] [ 0 0 0 0 ] [ -1 ] [ -1 ] Upstream
[ 5 ] [ 0 0 1 0 ] [ 5 ] [ 5 ] gradient
[ 0 ] [ 0 0 0 0 ] [ 9 ] [ 9 ] |
| Stanford CS231n 10th Anniversary Lecture 4 - 137 April 10, 2025 |


---
## Page 133
---


Backprop with Vectors
4D input x: 4D output z:
[ 1 ] [ 1 ]
[ -2 ] [ 0 ]
f(x) = max(0,x)
Jacobian is sparse:
[ 3 ] [ 3 ]
(elementwise)
off-diagonal entries
[ -1 ] [ 0 ]
always zero! Never
explicitly form
Jacobian --instead
4D dL/dx: [dz/dx] [dL/dz] 4D dL/dz:
use implicit
multiplication [ 4 ] [ 4 ]
[ 0 ] [ -1 ] Upstream
z
[ 5 ] [ 5 ] gradient
[ 0 ] [ 9 ]
Stanford CS231n 10th Anniversary Lecture 4 - 138 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Vectors
4D input x: 4D output z:
[ 1 ] [ 1 ]
[ -2 ] [ 0 ]
f(x) = max(0,x)
Jacobian is sparse:
[ 3 ] [ 3 ]
(elementwise)
off-diagonal entries
[ -1 ] [ 0 ]
always zero! Never
explicitly form
Jacobian --instead
4D dL/dx: [dz/dx] [dL/dz] 4D dL/dz:
use implicit
multiplication [ 4 ] [ 4 ]
[ 0 ] [ -1 ] Upstream
z
[ 5 ] [ 5 ] gradient
[ 0 ] [ 9 ] |
| Stanford CS231n 10th Anniversary Lecture 4 - 138 April 10, 2025 |


[Page contains 1 image(s)]


---
## Page 134
---


Backprop with Matrices (or Tensors)
Loss L still a scalar!
dL/dx always has the
[D ×M ]
x x
same shape as x!
[D ×M ]
z z
f
Matrix-vector
multiply
[D ×M ]
y y
Jacobian
matrices
Stanford CS231n 10th Anniversary Lecture 4 - 139 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Matrices (or Tensors)
Loss L still a scalar!
dL/dx always has the
[D ×M ]
x x
same shape as x!
[D ×M ]
z z
f
Matrix-vector
multiply
[D ×M ]
y y
Jacobian
matrices |
| Stanford CS231n 10th Anniversary Lecture 4 - 139 April 10, 2025 |


[Page contains 3 image(s)]


---
## Page 135
---


Backprop with Matrices (or Tensors)
Loss L still a scalar!
dL/dx always has the
[D ×M ]
x x
same shape as x!
[D ×M ]
x x
[D ×M ]
z z
f
“Downstream
Matrix-vector
gradients”
multiply
[D ×M ]
[D ×M ]
z z
y y
Jacobian
matrices
“Upstream gradient”
[D ×M ]
y y For each element of z, how
much does it influence L?
Stanford CS231n 10th Anniversary Lecture 4 - 140 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Matrices (or Tensors)
Loss L still a scalar!
dL/dx always has the
[D ×M ]
x x
same shape as x!
[D ×M ]
x x
[D ×M ]
z z
f
“Downstream
Matrix-vector
gradients”
multiply
[D ×M ]
[D ×M ]
z z
y y
Jacobian
matrices
“Upstream gradient”
[D ×M ]
y y For each element of z, how
much does it influence L? |
| Stanford CS231n 10th Anniversary Lecture 4 - 140 April 10, 2025 |


[Page contains 6 image(s)]


---
## Page 136
---


Backprop with Matrices (or Tensors)
Loss L still a scalar!
dL/dx always has the
[D ×M ]
x x “local
same shape as x!
gradients”
[D ×M ]
x x
[D ×M ]
z z
“Downstream
Matrix-vector
gradients”
multiply
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
Stanford CS231n 10th Anniversary Lecture 4 - 141 April 10, 2025

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
x x
[D ×M ]
z z
“Downstream
Matrix-vector
gradients”
multiply
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
| Stanford CS231n 10th Anniversary Lecture 4 - 141 April 10, 2025 |


[Page contains 8 image(s)]


---
## Page 137
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
Stanford CS231n 10th Anniversary Lecture 4 - 142 April 10, 2025

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
| Stanford CS231n 10th Anniversary Lecture 4 - 142 April 10, 2025 |


[Page contains 8 image(s)]


---
## Page 138
---


Backprop with Matrices y: [N×M]
[13 9 -2 -6 ]
x: [N×D] Matrix Multiply [ 5 2 17 1 ]
[ 2 1 -3 ]
[ -3 4 2 ]
dL/dy: [N×M]
w: [D×M] [ 2 3 -3 9 ]
[ 3 2 1 -1] [ -8 1 4 6 ]
[ 2 1 3 2]
[ 3 2 1 -2]
Also see derivation in the course notes:
http://cs231n.stanford.edu/handouts/linear-backprop.pdf
Stanford CS231n 10th Anniversary Lecture 4 - 143 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Matrices y: [N×M]
[13 9 -2 -6 ]
x: [N×D] Matrix Multiply [ 5 2 17 1 ]
[ 2 1 -3 ]
[ -3 4 2 ]
dL/dy: [N×M]
w: [D×M] [ 2 3 -3 9 ]
[ 3 2 1 -1] [ -8 1 4 6 ]
[ 2 1 3 2]
[ 3 2 1 -2]
Also see derivation in the course notes:
http://cs231n.stanford.edu/handouts/linear-backprop.pdf |
| Stanford CS231n 10th Anniversary Lecture 4 - 143 April 10, 2025 |


[Page contains 1 image(s)]


---
## Page 139
---


Backprop with Matrices y: [N×M]
[13 9 -2 -6 ]
x: [N×D] Matrix Multiply [ 5 2 17 1 ]
[ 2 1 -3 ]
[ -3 4 2 ]
dL/dy: [N×M]
w: [D×M] [ 2 3 -3 9 ]
[ 3 2 1 -1] [ -8 1 4 6 ]
Jacobians:
[ 2 1 3 2]
dy/dx: [(N×D)×(N×M)]
[ 3 2 1 -2]
dy/dw: [(D×M)×(N×M)]
For a neural net we may have
N=64, D=M=4096
Each Jacobian takes ~256 GB of memory!
Must work with them implicitly!
Stanford CS231n 10th Anniversary Lecture 4 - 144 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Matrices y: [N×M]
[13 9 -2 -6 ]
x: [N×D] Matrix Multiply [ 5 2 17 1 ]
[ 2 1 -3 ]
[ -3 4 2 ]
dL/dy: [N×M]
w: [D×M] [ 2 3 -3 9 ]
[ 3 2 1 -1] [ -8 1 4 6 ]
Jacobians:
[ 2 1 3 2]
dy/dx: [(N×D)×(N×M)]
[ 3 2 1 -2]
dy/dw: [(D×M)×(N×M)]
For a neural net we may have
N=64, D=M=4096
Each Jacobian takes ~256 GB of memory!
Must work with them implicitly! |
| Stanford CS231n 10th Anniversary Lecture 4 - 144 April 10, 2025 |


[Page contains 1 image(s)]


---
## Page 140
---


Backprop with Matrices y: [N×M]
[13 9 -2 -6 ]
x: [N×D] Matrix Multiply [ 5 2 17 1 ]
[ 2 1 -3 ]
[ -3 4 2 ]
dL/dy: [N×M]
w: [D×M] [ 2 3 -3 9 ]
[ 3 2 1 -1] Q: What parts of y are [ -8 1 4 6 ]
[ 2 1 3 2] affected by one
[ 3 2 1 -2] element of x?
Stanford CS231n 10th Anniversary Lecture 4 - 145 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Matrices y: [N×M]
[13 9 -2 -6 ]
x: [N×D] Matrix Multiply [ 5 2 17 1 ]
[ 2 1 -3 ]
[ -3 4 2 ]
dL/dy: [N×M]
w: [D×M] [ 2 3 -3 9 ]
[ 3 2 1 -1] Q: What parts of y are [ -8 1 4 6 ]
[ 2 1 3 2] affected by one
[ 3 2 1 -2] element of x? |
| Stanford CS231n 10th Anniversary Lecture 4 - 145 April 10, 2025 |


[Page contains 1 image(s)]


---
## Page 141
---


Backprop with Matrices y: [N×M]
[13 9 -2 -6 ]
x: [N×D] Matrix Multiply [ 5 2 17 1 ]
[ 2 1 -3 ]
[ -3 4 2 ]
dL/dy: [N×M]
w: [D×M] [ 2 3 -3 9 ]
[ 3 2 1 -1] Q: What parts of y are [ -8 1 4 6 ]
[ 2 1 3 2] affected by one
[ 3 2 1 -2] element of x?
A: affects the
whole row
Stanford CS231n 10th Anniversary Lecture 4 - 146 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Matrices y: [N×M]
[13 9 -2 -6 ]
x: [N×D] Matrix Multiply [ 5 2 17 1 ]
[ 2 1 -3 ]
[ -3 4 2 ]
dL/dy: [N×M]
w: [D×M] [ 2 3 -3 9 ]
[ 3 2 1 -1] Q: What parts of y are [ -8 1 4 6 ]
[ 2 1 3 2] affected by one
[ 3 2 1 -2] element of x?
A: affects the
whole row |
| Stanford CS231n 10th Anniversary Lecture 4 - 146 April 10, 2025 |


[Page contains 4 image(s)]


---
## Page 142
---


Backprop with Matrices y: [N×M]
[13 9 -2 -6 ]
x: [N×D] Matrix Multiply [ 5 2 17 1 ]
[ 2 1 -3 ]
[ -3 4 2 ]
dL/dy: [N×M]
w: [D×M] [ 2 3 -3 9 ]
[ 3 2 1 -1] Q: What parts of y are [ -8 1 4 6 ]
[ 2 1 3 2] affected by one
Q: How much does
[ 3 2 1 -2] element of x?
affect ?
A: affects the
whole row
Stanford CS231n 10th Anniversary Lecture 4 - 147 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Matrices y: [N×M]
[13 9 -2 -6 ]
x: [N×D] Matrix Multiply [ 5 2 17 1 ]
[ 2 1 -3 ]
[ -3 4 2 ]
dL/dy: [N×M]
w: [D×M] [ 2 3 -3 9 ]
[ 3 2 1 -1] Q: What parts of y are [ -8 1 4 6 ]
[ 2 1 3 2] affected by one
Q: How much does
[ 3 2 1 -2] element of x?
affect ?
A: affects the
whole row |
| Stanford CS231n 10th Anniversary Lecture 4 - 147 April 10, 2025 |


[Page contains 6 image(s)]


---
## Page 143
---


Backprop with Matrices y: [N×M]
[13 9 -2 -6 ]
x: [N×D] Matrix Multiply [ 5 2 17 1 ]
[ 2 1 -3 ]
[ -3 4 2 ]
dL/dy: [N×M]
w: [D×M] [ 2 3 -3 9 ]
[ 3 2 1 -1] Q: What parts of y are [ -8 1 4 6 ]
[ 2 1 3 2] affected by one
Q: How much does
[ 3 2 1 -2] element of x?
affect ?
A: affects the
A:
whole row
Stanford CS231n 10th Anniversary Lecture 4 - 148 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Matrices y: [N×M]
[13 9 -2 -6 ]
x: [N×D] Matrix Multiply [ 5 2 17 1 ]
[ 2 1 -3 ]
[ -3 4 2 ]
dL/dy: [N×M]
w: [D×M] [ 2 3 -3 9 ]
[ 3 2 1 -1] Q: What parts of y are [ -8 1 4 6 ]
[ 2 1 3 2] affected by one
Q: How much does
[ 3 2 1 -2] element of x?
affect ?
A: affects the
A:
whole row |
| Stanford CS231n 10th Anniversary Lecture 4 - 148 April 10, 2025 |


[Page contains 8 image(s)]


---
## Page 144
---


Backprop with Matrices y: [N×M]
[13 9 -2 -6 ]
x: [N×D] Matrix Multiply [ 5 2 17 1 ]
[ 2 1 -3 ]
[ -3 4 2 ]
dL/dy: [N×M]
w: [D×M] [ 2 3 -3 9 ]
[ 3 2 1 -1] Q: What parts of y are [ -8 1 4 6 ]
[ 2 1 3 2] affected by one
Q: How much does
[ 3 2 1 -2] element of x?
affect ?
A: affects the
A:
[N×D] [N×M] [M×D]
whole row
Stanford CS231n 10th Anniversary Lecture 4 - 149 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Matrices y: [N×M]
[13 9 -2 -6 ]
x: [N×D] Matrix Multiply [ 5 2 17 1 ]
[ 2 1 -3 ]
[ -3 4 2 ]
dL/dy: [N×M]
w: [D×M] [ 2 3 -3 9 ]
[ 3 2 1 -1] Q: What parts of y are [ -8 1 4 6 ]
[ 2 1 3 2] affected by one
Q: How much does
[ 3 2 1 -2] element of x?
affect ?
A: affects the
A:
[N×D] [N×M] [M×D]
whole row |
| Stanford CS231n 10th Anniversary Lecture 4 - 149 April 10, 2025 |


[Page contains 8 image(s)]


---
## Page 145
---


Backprop with Matrices y: [N×M]
[13 9 -2 -6 ]
x: [N×D] Matrix Multiply [ 5 2 17 1 ]
[ 2 1 -3 ]
[ -3 4 2 ]
dL/dy: [N×M]
w: [D×M] [ 2 3 -3 9 ]
[ 3 2 1 -1] [ -8 1 4 6 ]
[ 2 1 3 2]
By similar logic:
[ 3 2 1 -2]
These formulas are easy
[N×D] [N×M] [M×D] [D×M] [D×N] [N×M]
to remember: they are the
only way to make shapes
match up!
Stanford CS231n 10th Anniversary Lecture 4 - 150 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Backprop with Matrices y: [N×M]
[13 9 -2 -6 ]
x: [N×D] Matrix Multiply [ 5 2 17 1 ]
[ 2 1 -3 ]
[ -3 4 2 ]
dL/dy: [N×M]
w: [D×M] [ 2 3 -3 9 ]
[ 3 2 1 -1] [ -8 1 4 6 ]
[ 2 1 3 2]
By similar logic:
[ 3 2 1 -2]
These formulas are easy
[N×D] [N×M] [M×D] [D×M] [D×N] [N×M]
to remember: they are the
only way to make shapes
match up! |
| Stanford CS231n 10th Anniversary Lecture 4 - 150 April 10, 2025 |


[Page contains 3 image(s)]


---
## Page 146
---


Summary for today:
● (Fully-connected) Neural Networks are stacks of linear functions and nonlinear
activation functions; they have much more representational power than linear classifiers
● backpropagation = recursive application of the chain rule along a computational graph
to compute the gradients of all inputs/parameters/intermediates
● implementations maintain a graph structure, where the nodes implement the forward()
/ backward() API
● forward: compute result of an operation and save any intermediates needed for gradient
computation in memory
● backward: apply the chain rule to compute the gradient of the loss function with respect
to the inputs
Stanford CS231n 10th Anniversary Lecture 4 - 151 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Summary for today:
● (Fully-connected) Neural Networks are stacks of linear functions and nonlinear
activation functions; they have much more representational power than linear classifiers
● backpropagation = recursive application of the chain rule along a computational graph
to compute the gradients of all inputs/parameters/intermediates
● implementations maintain a graph structure, where the nodes implement the forward()
/ backward() API
● forward: compute result of an operation and save any intermediates needed for gradient
computation in memory
● backward: apply the chain rule to compute the gradient of the loss function with respect
to the inputs |
| Stanford CS231n 10th Anniversary Lecture 4 - 151 April 10, 2025 |


---
## Page 147
---


Next Time: Convolutional Neural Networks!
Stanford CS231n 10th Anniversary Lecture 4 - 152 April 10, 2025

[Page contains 1 table(s)]


### Table 1

| Next Time: Convolutional Neural Networks! |
| Stanford CS231n 10th Anniversary Lecture 4 - 152 April 10, 2025 |


[Page contains 1 image(s)]
