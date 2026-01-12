# lecture_17

Extracted using pdfplumber



---
## Page 1
---


Lecture 17:
Robot Learning
Yunzhu Li Lecture 17 - 1 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture 17:
Robot Learning |
| Yunzhu Li Lecture 17 - 1 May 29, 2025 |


---
## Page 2
---


So far: Supervised Learning
Supervised Learning
Classification
Data: (x, y)
x is data, y is label
Goal: Learn a function to map x -> y
Examples: Classification, regression,
Cat
object detection, semantic
segmentation, image captioning, etc.
This image is CC0 public domain
Yunzhu Li Lecture 17 - 2 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| So far: Supervised Learning
Supervised Learning
Classification
Data: (x, y)
x is data, y is label
Goal: Learn a function to map x -> y
Examples: Classification, regression,
Cat
object detection, semantic
segmentation, image captioning, etc.
This image is CC0 public domain |
| Yunzhu Li Lecture 17 - 2 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 3
---


So far: Self-Supervised Learning
Self-Supervised Learning Feature Learning
(e.g., autoencoders)
Data: x
Just data, no labels!
Goal: Learn some underlying hidden
structure of the data
Examples: Clustering, dimensionality
reduction, feature learning, density
estimation, etc.
Yunzhu Li Lecture 17 - 3 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| So far: Self-Supervised Learning
Self-Supervised Learning Feature Learning
(e.g., autoencoders)
Data: x
Just data, no labels!
Goal: Learn some underlying hidden
structure of the data
Examples: Clustering, dimensionality
reduction, feature learning, density
estimation, etc. |
| Yunzhu Li Lecture 17 - 3 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 4
---


Today: Robot Learning
Action
Problems where an agent
Agent Environment
performs actions in the
environment, and receives
rewards
Goal: Learn how to take
actions that maximize reward
Reward
Earth photo is in the public domain
Robot image is in the public domain
Yunzhu Li Lecture 17 - 4 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Today: Robot Learning
Action
Problems where an agent
Agent Environment
performs actions in the
environment, and receives
rewards
Goal: Learn how to take
actions that maximize reward
Reward
Earth photo is in the public domain
Robot image is in the public domain |
| Yunzhu Li Lecture 17 - 4 May 29, 2025 |


[Page contains 2 image(s)]


---
## Page 5
---


Yunzhu Li Lecture 17 - 5 May 29, 2025

[Page contains 1 table(s)]


### Table 1

|  |
| Yunzhu Li Lecture 17 - 5 May 29, 2025 |


[Page contains 4 image(s)]


---
## Page 6
---


A Fast-Growing Field
Yunzhu Li Lecture 17 - 6 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| A Fast-Growing Field |
| Yunzhu Li Lecture 17 - 6 May 29, 2025 |


[Page contains 5 image(s)]


---
## Page 7
---


A Fast-Growing Field
Toyota Research Institute Meta AI Research Google Robotics Nvidia Research
Yunzhu Li Lecture 17 - 7 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| A Fast-Growing Field
Toyota Research Institute Meta AI Research Google Robotics Nvidia Research |
| Yunzhu Li Lecture 17 - 7 May 29, 2025 |


[Page contains 4 image(s)]


---
## Page 8
---


Overview
- Problem formulation
- Robot perception
- Reinforcement learning
- Model learning & model-based planning
- Imitation learning
- Robotic foundation models
- Remaining challenges
Yunzhu Li Lecture 17 - 8 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Overview
- Problem formulation
- Robot perception
- Reinforcement learning
- Model learning & model-based planning
- Imitation learning
- Robotic foundation models
- Remaining challenges |
| Yunzhu Li Lecture 17 - 8 May 29, 2025 |


---
## Page 9
---


Problem Formulation
Yunzhu Li Lecture 17 - 9 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Problem Formulation |
| Yunzhu Li Lecture 17 - 9 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 10
---


Example: Cart-Pole Problem
Goal: Balance a pole on top
of a movable cart
State: angle, angular speed,
position, horizontal velocity
Action: horizontal force
applied to the cart
Reward: 1 at each time step
if the pole is upright
This image is CC0 public domain
Yunzhu Li Lecture 17 - 10 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Example: Cart-Pole Problem
Goal: Balance a pole on top
of a movable cart
State: angle, angular speed,
position, horizontal velocity
Action: horizontal force
applied to the cart
Reward: 1 at each time step
if the pole is upright
This image is CC0 public domain |
| Yunzhu Li Lecture 17 - 10 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 11
---


Example: Robot Locomotion
Goal: Make the robot
move forward
State: Angle, position,
velocity of all joints
Action: Torques applied
to joints
Reward: 1 at each time
step upright + forward
movement
Figure from: Schulman et al, “High-Dimensional Continuous
Control Using Generalized Advantage Estimation”, ICLR 2016
Yunzhu Li Lecture 17 - 11 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Example: Robot Locomotion
Goal: Make the robot
move forward
State: Angle, position,
velocity of all joints
Action: Torques applied
to joints
Reward: 1 at each time
step upright + forward
movement
Figure from: Schulman et al, “High-Dimensional Continuous
Control Using Generalized Advantage Estimation”, ICLR 2016 |
| Yunzhu Li Lecture 17 - 11 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 12
---


Example: Atari Games
Goal: Complete the game with the highest score
State: Raw pixel inputs of the game screen
Action: Game controls e.g. Left, Right, Up, Down
Reward: Score increase/decrease at each time step
Mnih et al, “Playing Atari with Deep Reinforcement Learning”, NeurIPS Deep Learning Workshop, 2013
Yunzhu Li Lecture 17 - 12 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Example: Atari Games
Goal: Complete the game with the highest score
State: Raw pixel inputs of the game screen
Action: Game controls e.g. Left, Right, Up, Down
Reward: Score increase/decrease at each time step
Mnih et al, “Playing Atari with Deep Reinforcement Learning”, NeurIPS Deep Learning Workshop, 2013 |
| Yunzhu Li Lecture 17 - 12 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 13
---


Example: Go
Goal: Win the game!
This image is CC0 public domain
Yunzhu Li Lecture 17 - 13 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Example: Go
Goal: Win the game!
This image is CC0 public domain |
| Yunzhu Li Lecture 17 - 13 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 14
---


Example: Go
Goal: Win the game!
State: Position of all pieces
Action: Where to put the next
piece down
Reward: On last turn: 1 if you
won, 0 if you lost
This image is CC0 public domain
Yunzhu Li Lecture 17 - 14 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Example: Go
Goal: Win the game!
State: Position of all pieces
Action: Where to put the next
piece down
Reward: On last turn: 1 if you
won, 0 if you lost
This image is CC0 public domain |
| Yunzhu Li Lecture 17 - 14 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 15
---


Example: Text Generation
Goal: Predict the next word!
<s> CS231n
midterm
was ___
Yunzhu Li Lecture 17 - 15 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Example: Text Generation
Goal: Predict the next word!
<s> CS231n
midterm
was ___ |
| Yunzhu Li Lecture 17 - 15 May 29, 2025 |


---
## Page 16
---


Example: Text Generation
Goal: Predict the next word!
State: Current words in the
<s> CS231n
sentence
midterm
Action: Next word
was ___
Reward: 1 if correct, 0 otherwise
Yunzhu Li Lecture 17 - 16 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Example: Text Generation
Goal: Predict the next word!
State: Current words in the
<s> CS231n
sentence
midterm
Action: Next word
was ___
Reward: 1 if correct, 0 otherwise |
| Yunzhu Li Lecture 17 - 16 May 29, 2025 |


---
## Page 17
---


Example: Chatbot
Goal: Be a good companion!
Yunzhu Li Lecture 17 - 17 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Example: Chatbot
Goal: Be a good companion! |
| Yunzhu Li Lecture 17 - 17 May 29, 2025 |


[Page contains 2 image(s)]


---
## Page 18
---


Example: Chatbot
Goal: Be a good companion!
State: Current conversation
Action: Next sentence
Reward: Human evaluation, 1 if
satisfied, -1 if unsatisfied, 0 neutral
Yunzhu Li Lecture 17 - 18 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Example: Chatbot
Goal: Be a good companion!
State: Current conversation
Action: Next sentence
Reward: Human evaluation, 1 if
satisfied, -1 if unsatisfied, 0 neutral |
| Yunzhu Li Lecture 17 - 18 May 29, 2025 |


[Page contains 2 image(s)]


---
## Page 19
---


Example: Cloth folding robot
Goal: Fold the cloth
Yunzhu Li Lecture 17 - 19 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Example: Cloth folding robot
Goal: Fold the cloth |
| Yunzhu Li Lecture 17 - 19 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 20
---


Example: Cloth folding robot
Goal: Fold the cloth
State: Current conversation
Action: Robot end-effector motions
Reward: Human evaluation, 1 if
cloth is folded, 0 otherwise
Yunzhu Li Lecture 17 - 20 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Example: Cloth folding robot
Goal: Fold the cloth
State: Current conversation
Action: Robot end-effector motions
Reward: Human evaluation, 1 if
cloth is folded, 0 otherwise |
| Yunzhu Li Lecture 17 - 20 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 21
---


Overview
- Problem formulation
- Robot perception
- Reinforcement learning
- Model learning & model-based planning
- Imitation learning
- Robotic foundation models
- Remaining challenges
Yunzhu Li Lecture 17 - 21 May 29, 2025

[Page contains 2 table(s)]


### Table 1

| Overview
- Problem formulation
- Robot perception
- Reinforcement learning
- Model learning & model-based planning
- Imitation learning
- Robotic foundation models
- Remaining challenges |
| Yunzhu Li Lecture 17 - 21 May 29, 2025 |


### Table 2

| - Problem formulation |
| - Robot perception |


---
## Page 22
---


What is Robot Perception?
Yunzhu Li Lecture 17 - 22 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| What is Robot Perception? |
| Yunzhu Li Lecture 17 - 22 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 23
---


What is Robot Perception?
Making sense of the unstructured real world …
• Incomplete knowledge of
objects and scenes
• Imperfect actions may lead
to failure
• Environment dynamics and
other agents
Yunzhu Li Lecture 17 - 23 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| What is Robot Perception?
Making sense of the unstructured real world …
• Incomplete knowledge of
objects and scenes
• Imperfect actions may lead
to failure
• Environment dynamics and
other agents |
| Yunzhu Li Lecture 17 - 23 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 24
---


Sensors for Robotics
Understanding the interactions with the world through multimodal senses
Yunzhu Li Lecture 17 - 24 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Sensors for Robotics
Understanding the interactions with the world through multimodal senses |
| Yunzhu Li Lecture 17 - 24 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 25
---


Sensors for Robotics
Understanding the interactions with the world through multimodal senses
[Source: HKU Advanced Robotics Laboratory]
Yunzhu Li Lecture 17 - 25 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Sensors for Robotics
Understanding the interactions with the world through multimodal senses
[Source: HKU Advanced Robotics Laboratory] |
| Yunzhu Li Lecture 17 - 25 May 29, 2025 |


[Page contains 2 image(s)]


---
## Page 26
---


Robot Vision vs. Computer Vision
Robot vision is embodied, active, and environmentally situated.
[Detectron - Facebook AI Research] [Zeng et al., IROS 2018]
Yunzhu Li Lecture 17 - 26 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Robot Vision vs. Computer Vision
Robot vision is embodied, active, and environmentally situated.
[Detectron - Facebook AI Research] [Zeng et al., IROS 2018] |
| Yunzhu Li Lecture 17 - 26 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 27
---


Robot Vision vs. Computer Vision
Robot vision is embodied, active, and environmentally situated.
• Embodied: Robots have physical bodies and experience the world directly.
Their actions are part of a dynamic with the world and have immediate
feedback on their own sensation.
• Active: Robots are active perceivers. It knows why it wishes to sense, and
chooses what to perceive, and determines how, when and where to achieve
that perception.
• Situated: Robots are situated in the world. They do not deal with abstract
descriptions, but with the “here” and “now” of the world directly influencing the
behavior of the system.
Yunzhu Li Lecture 17 - 27 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Robot Vision vs. Computer Vision
Robot vision is embodied, active, and environmentally situated.
• Embodied: Robots have physical bodies and experience the world directly.
Their actions are part of a dynamic with the world and have immediate
feedback on their own sensation.
• Active: Robots are active perceivers. It knows why it wishes to sense, and
chooses what to perceive, and determines how, when and where to achieve
that perception.
• Situated: Robots are situated in the world. They do not deal with abstract
descriptions, but with the “here” and “now” of the world directly influencing the
behavior of the system. |
| Yunzhu Li Lecture 17 - 27 May 29, 2025 |


---
## Page 28
---


The Perception-Action Loop
Yunzhu Li Lecture 17 - 28 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| The Perception-Action Loop |
| Yunzhu Li Lecture 17 - 28 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 29
---


The Perception-Action Loop
Yunzhu Li Lecture 17 - 29 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| The Perception-Action Loop |
| Yunzhu Li Lecture 17 - 29 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 30
---


The Perception-Action Loop
A key challenge in Robot Learning is to close the perception-action loop.
Yunzhu Li Lecture 17 - 30 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| The Perception-Action Loop
A key challenge in Robot Learning is to close the perception-action loop. |
| Yunzhu Li Lecture 17 - 30 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 31
---


Overview
- Problem formulation
- Robot perception
- Reinforcement learning
- Model learning & model-based planning
- Imitation learning
- Robotic foundation models
- Remaining challenges
Yunzhu Li Lecture 17 - 31 May 29, 2025

[Page contains 2 table(s)]


### Table 1

| Overview
- Problem formulation
- Robot perception
- Reinforcement learning
- Model learning & model-based planning
- Imitation learning
- Robotic foundation models
- Remaining challenges |
| Yunzhu Li Lecture 17 - 31 May 29, 2025 |


### Table 2

| - Robot perception |
| - Reinforcement learning |


---
## Page 32
---


Reinforcement Learning
RL trains agents that interact
with an environment and
learn to maximize reward
(trial and error)
Yunzhu Li Lecture 17 - 32 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Reinforcement Learning
RL trains agents that interact
with an environment and
learn to maximize reward
(trial and error) |
| Yunzhu Li Lecture 17 - 32 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 33
---


Reinforcement Learning vs Supervised Learning
Environment Environment
State Action Reward State Action Reward
s a r s a r
t t t t+1 t+1 t+1
Agent Agent
Yunzhu Li Lecture 17 - 33 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Reinforcement Learning vs Supervised Learning
Environment Environment
State Action Reward State Action Reward
s a r s a r
t t t t+1 t+1 t+1
Agent Agent |
| Yunzhu Li Lecture 17 - 33 May 29, 2025 |


---
## Page 34
---


Reinforcement Learning vs Supervised Learning
Dataset Dataset
Input Prediction Loss Input Prediction Loss
x y L x y L
t t t t+t t+1 t+1
Model Model
Why is RL different from normal supervised learning?
Yunzhu Li Lecture 17 - 34 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Reinforcement Learning vs Supervised Learning
Dataset Dataset
Input Prediction Loss Input Prediction Loss
x y L x y L
t t t t+t t+1 t+1
Model Model
Why is RL different from normal supervised learning? |
| Yunzhu Li Lecture 17 - 34 May 29, 2025 |


---
## Page 35
---


Reinforcement Learning vs Supervised Learning
Environment Environment
State Action Reward State Action Reward
s a r s a r
t t t t+1 t+1 t+1
Agent Agent
Stochasticity: Rewards and state transitions may be random
Yunzhu Li Lecture 17 - 35 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Reinforcement Learning vs Supervised Learning
Environment Environment
State Action Reward State Action Reward
s a r s a r
t t t t+1 t+1 t+1
Agent Agent
Stochasticity: Rewards and state transitions may be random |
| Yunzhu Li Lecture 17 - 35 May 29, 2025 |


---
## Page 36
---


Reinforcement Learning vs Supervised Learning
Environment Environment
State Action Reward State Action Reward
s a r s a r
t t t t+1 t+1 t+1
Agent Agent
Credit assignment: Reward r may not directly depend on action a
t t
Yunzhu Li Lecture 17 - 36 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Reinforcement Learning vs Supervised Learning
Environment Environment
State Action Reward State Action Reward
s a r s a r
t t t t+1 t+1 t+1
Agent Agent
Credit assignment: Reward r may not directly depend on action a
t t |
| Yunzhu Li Lecture 17 - 36 May 29, 2025 |


---
## Page 37
---


Reinforcement Learning vs Supervised Learning
Environment Environment
State Action Reward State Action Reward
s a r s a r
t t t t+1 t+1 t+1
Agent Agent
Nondifferentiable: Can’t backprop through world; can’t compute dr /da
t t
Yunzhu Li Lecture 17 - 37 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Reinforcement Learning vs Supervised Learning
Environment Environment
State Action Reward State Action Reward
s a r s a r
t t t t+1 t+1 t+1
Agent Agent
Nondifferentiable: Can’t backprop through world; can’t compute dr /da
t t |
| Yunzhu Li Lecture 17 - 37 May 29, 2025 |


---
## Page 38
---


Reinforcement Learning vs Supervised Learning
Environment Environment
State Action Reward State Action Reward
s a r s a r
t t t t+1 t+1 t+1
Agent Agent
Nonstationary: What the agent experiences depends on how it acts
Yunzhu Li Lecture 17 - 38 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Reinforcement Learning vs Supervised Learning
Environment Environment
State Action Reward State Action Reward
s a r s a r
t t t t+1 t+1 t+1
Agent Agent
Nonstationary: What the agent experiences depends on how it acts |
| Yunzhu Li Lecture 17 - 38 May 29, 2025 |


---
## Page 39
---


Case Study: Playing Atari Games
Goal: Complete the game with the highest score
State: Raw pixel inputs of the game screen
Action: Game controls e.g. Left, Right, Up, Down
Reward: Score increase/decrease at each time step
Mnih et al, “Playing Atari with Deep Reinforcement Learning”, NeurIPS Deep Learning Workshop, 2013
Yunzhu Li Lecture 17 - 39 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Case Study: Playing Atari Games
Goal: Complete the game with the highest score
State: Raw pixel inputs of the game screen
Action: Game controls e.g. Left, Right, Up, Down
Reward: Score increase/decrease at each time step
Mnih et al, “Playing Atari with Deep Reinforcement Learning”, NeurIPS Deep Learning Workshop, 2013 |
| Yunzhu Li Lecture 17 - 39 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 40
---


Mnih et al, “Playing Atari with Deep
Reinforcement Learning”, NeurIPS
Case Study: Playing Atari Games
Deep Learning Workshop, 2013
Network output:
𝑄 𝑠, 𝑎; 𝜃 With 4 actions: last layer
Q-values for all actions
Neural network with gives values Q(s , a ),
t 1
weights θ FC-A (Q-values) Q(s , a ), Q(s , a ), Q(s ,a )
t 2 t 3 t 4
FC-256
Conv(16->32, 4x4, stride 2)
Conv(4->16, 8x8, stride 4)
Network input: state s : 4x84x84 stack of last 4 frames
t
(after RGB->grayscale conversion, downsampling, and cropping)
Yunzhu Li Lecture 17 - 40 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Mnih et al, “Playing Atari with Deep
Reinforcement Learning”, NeurIPS
Case Study: Playing Atari Games
Deep Learning Workshop, 2013
Network output:
𝑄 𝑠, 𝑎; 𝜃 With 4 actions: last layer
Q-values for all actions
Neural network with gives values Q(s , a ),
t 1
weights θ FC-A (Q-values) Q(s , a ), Q(s , a ), Q(s ,a )
t 2 t 3 t 4
FC-256
Conv(16->32, 4x4, stride 2)
Conv(4->16, 8x8, stride 4)
Network input: state s : 4x84x84 stack of last 4 frames
t
(after RGB->grayscale conversion, downsampling, and cropping) |
| Yunzhu Li Lecture 17 - 40 May 29, 2025 |


[Page contains 4 image(s)]


---
## Page 41
---


https://www.youtube.com/watch?v=V1eYniJ0Rnk
Yunzhu Li Lecture 17 - 41 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| https://www.youtube.com/watch?v=V1eYniJ0Rnk |
| Yunzhu Li Lecture 17 - 41 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 42
---


Case Study: Playing Games
AlphaGo: (January 2016)
- Used imitation learning + tree search + RL
- Beat 18-time world champion Lee Sedol
AlphaGo Zero (October 2017)
- Simplified version of AlphaGo
- No longer using imitation learning
- Beat (at the time) #1 ranked Ke Jie
Alpha Zero (December 2018)
- Generalized to other games: Chess and Shogi
MuZero (November 2019)
- Plans through a learned model of the game
Silver et al, “Mastering the game of Go with deep neural networks and tree search”, Nature 2016
Silver et al, “Mastering the game of Go without human knowledge”, Nature 2017
Silver et al, “A general reinforcement learning algorithm that masters chess, shogi, and go through self-play”, Science 2018
Schrittwieser et al, “Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model”, arXiv 2019 This image is CC0 public domain
Yunzhu Li Lecture 17 - 42 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Case Study: Playing Games
AlphaGo: (January 2016)
- Used imitation learning + tree search + RL
- Beat 18-time world champion Lee Sedol
AlphaGo Zero (October 2017)
- Simplified version of AlphaGo
- No longer using imitation learning
- Beat (at the time) #1 ranked Ke Jie
Alpha Zero (December 2018)
- Generalized to other games: Chess and Shogi
MuZero (November 2019)
- Plans through a learned model of the game
Silver et al, “Mastering the game of Go with deep neural networks and tree search”, Nature 2016
Silver et al, “Mastering the game of Go without human knowledge”, Nature 2017
Silver et al, “A general reinforcement learning algorithm that masters chess, shogi, and go through self-play”, Science 2018
Schrittwieser et al, “Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model”, arXiv 2019 This image is CC0 public domain |
| Yunzhu Li Lecture 17 - 42 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 43
---


Case Study: Playing Games
AlphaGo: (January 2016)
- Used imitation learning + tree search + RL
- Beat 18-time world champion Lee Sedol
AlphaGo Zero (October 2017)
- Simplified version of AlphaGo
- No longer using imitation learning
- Beat (at the time) #1 ranked Ke Jie
Alpha Zero (December 2018)
- Generalized to other games: Chess and Shogi
MuZero (November 2019)
- Plans through a learned model of the game
Silver et al, “Mastering the game of Go with deep neural networks and tree search”, Nature 2016
Silver et al, “Mastering the game of Go without human knowledge”, Nature 2017
Silver et al, “A general reinforcement learning algorithm that masters chess, shogi, and go through self-play”, Science 2018
Schrittwieser et al, “Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model”, arXiv 2019 This image is CC0 public domain
Yunzhu Li Lecture 17 - 43 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Case Study: Playing Games
AlphaGo: (January 2016)
- Used imitation learning + tree search + RL
- Beat 18-time world champion Lee Sedol
AlphaGo Zero (October 2017)
- Simplified version of AlphaGo
- No longer using imitation learning
- Beat (at the time) #1 ranked Ke Jie
Alpha Zero (December 2018)
- Generalized to other games: Chess and Shogi
MuZero (November 2019)
- Plans through a learned model of the game
Silver et al, “Mastering the game of Go with deep neural networks and tree search”, Nature 2016
Silver et al, “Mastering the game of Go without human knowledge”, Nature 2017
Silver et al, “A general reinforcement learning algorithm that masters chess, shogi, and go through self-play”, Science 2018
Schrittwieser et al, “Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model”, arXiv 2019 This image is CC0 public domain |
| Yunzhu Li Lecture 17 - 43 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 44
---


Case Study: Playing Games
AlphaGo: (January 2016)
- Used imitation learning + tree search + RL
- Beat 18-time world champion Lee Sedol
AlphaGo Zero (October 2017)
- Simplified version of AlphaGo
- No longer using imitation learning
- Beat (at the time) #1 ranked Ke Jie
Alpha Zero (December 2018)
- Generalized to other games: Chess and Shogi
MuZero (November 2019)
- Plans through a learned model of the game
Silver et al, “Mastering the game of Go with deep neural networks and tree search”, Nature 2016
Silver et al, “Mastering the game of Go without human knowledge”, Nature 2017
Silver et al, “A general reinforcement learning algorithm that masters chess, shogi, and go through self-play”, Science 2018
Schrittwieser et al, “Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model”, arXiv 2019 This image is CC0 public domain
Yunzhu Li Lecture 17 - 44 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Case Study: Playing Games
AlphaGo: (January 2016)
- Used imitation learning + tree search + RL
- Beat 18-time world champion Lee Sedol
AlphaGo Zero (October 2017)
- Simplified version of AlphaGo
- No longer using imitation learning
- Beat (at the time) #1 ranked Ke Jie
Alpha Zero (December 2018)
- Generalized to other games: Chess and Shogi
MuZero (November 2019)
- Plans through a learned model of the game
Silver et al, “Mastering the game of Go with deep neural networks and tree search”, Nature 2016
Silver et al, “Mastering the game of Go without human knowledge”, Nature 2017
Silver et al, “A general reinforcement learning algorithm that masters chess, shogi, and go through self-play”, Science 2018
Schrittwieser et al, “Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model”, arXiv 2019 This image is CC0 public domain |
| Yunzhu Li Lecture 17 - 44 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 45
---


Case Study: Playing Games
AlphaGo: (January 2016)
- Used imitation learning + tree search + RL
- Beat 18-time world champion Lee Sedol
AlphaGo Zero (October 2017)
- Simplified version of AlphaGo
- No longer using imitation learning
- Beat (at the time) #1 ranked Ke Jie
Alpha Zero (December 2018)
- Generalized to other games: Chess and Shogi
MuZero (November 2019)
- Plans through a learned model of the game
Silver et al, “Mastering the game of Go with deep neural networks and tree search”, Nature 2016
Silver et al, “Mastering the game of Go without human knowledge”, Nature 2017
Silver et al, “A general reinforcement learning algorithm that masters chess, shogi, and go through self-play”, Science 2018
Schrittwieser et al, “Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model”, arXiv 2019
Yunzhu Li Lecture 17 - 45 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Case Study: Playing Games
AlphaGo: (January 2016)
- Used imitation learning + tree search + RL
- Beat 18-time world champion Lee Sedol
AlphaGo Zero (October 2017)
- Simplified version of AlphaGo
- No longer using imitation learning
- Beat (at the time) #1 ranked Ke Jie
Alpha Zero (December 2018)
- Generalized to other games: Chess and Shogi
MuZero (November 2019)
- Plans through a learned model of the game
Silver et al, “Mastering the game of Go with deep neural networks and tree search”, Nature 2016
Silver et al, “Mastering the game of Go without human knowledge”, Nature 2017
Silver et al, “A general reinforcement learning algorithm that masters chess, shogi, and go through self-play”, Science 2018
Schrittwieser et al, “Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model”, arXiv 2019 |
| Yunzhu Li Lecture 17 - 45 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 46
---


Case Study: Playing Games
November 2019: Lee Sedol
announces retirement
AlphaGo: (January 2016)
- Used imitation learning + tree search + RL
“With the debut of AI in
- Beat 18-time world champion Lee Sedol
Go games, I've
AlphaGo Zero (October 2017)
realized that I'm not at
- Simplified version of AlphaGo
the top even if I
- No longer using imitation learning
become the number
- Beat (at the time) #1 ranked Ke Jie
one through frantic
Alpha Zero (December 2018)
efforts”
- Generalized to other games: Chess and Shogi
“Even if I become the
MuZero (November 2019)
number one, there is
- Plans through a learned model of the game
an entity that cannot
be defeated”
Silver et al, “Mastering the game of Go with deep neural networks and tree search”, Nature 2016
Silver et al, “Mastering the game of Go without human knowledge”, Nature 2017
Quotes from: https://en.yna.co.kr/view/AEN20191127004800315
Silver et al, “A general reinforcement learning algorithm that masters chess, shogi, and go through self-play”, Science 2018
Image of Lee Sedol is licensed under CC BY 2.0
Schrittwieser et al, “Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model”, arXiv 2019
Yunzhu Li Lecture 17 - 46 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Case Study: Playing Games
November 2019: Lee Sedol
announces retirement
AlphaGo: (January 2016)
- Used imitation learning + tree search + RL
“With the debut of AI in
- Beat 18-time world champion Lee Sedol
Go games, I've
AlphaGo Zero (October 2017)
realized that I'm not at
- Simplified version of AlphaGo
the top even if I
- No longer using imitation learning
become the number
- Beat (at the time) #1 ranked Ke Jie
one through frantic
Alpha Zero (December 2018)
efforts”
- Generalized to other games: Chess and Shogi
“Even if I become the
MuZero (November 2019)
number one, there is
- Plans through a learned model of the game
an entity that cannot
be defeated”
Silver et al, “Mastering the game of Go with deep neural networks and tree search”, Nature 2016
Silver et al, “Mastering the game of Go without human knowledge”, Nature 2017
Quotes from: https://en.yna.co.kr/view/AEN20191127004800315
Silver et al, “A general reinforcement learning algorithm that masters chess, shogi, and go through self-play”, Science 2018
Image of Lee Sedol is licensed under CC BY 2.0
Schrittwieser et al, “Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model”, arXiv 2019 |
| Yunzhu Li Lecture 17 - 46 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 47
---


More Complex Games
StarCraft II: AlphaStar
Dota 2: OpenAI Five (April 2019)
(October 2019)
No paper, only a blog post:
Vinyals et al, “Grandmaster
https://openai.com/five/#how-
level in StarCraft II using multi-
openai-five-works
agent reinforcement learning”,
Science 2018
Yunzhu Li Lecture 17 - 47 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| More Complex Games
StarCraft II: AlphaStar
Dota 2: OpenAI Five (April 2019)
(October 2019)
No paper, only a blog post:
Vinyals et al, “Grandmaster
https://openai.com/five/#how-
level in StarCraft II using multi-
openai-five-works
agent reinforcement learning”,
Science 2018 |
| Yunzhu Li Lecture 17 - 47 May 29, 2025 |


---
## Page 48
---


In Robotics: Locomotion
Learning Quadrupedal Locomotion over Challenging Terrain Unitree, Dec. 2024
Science Robotics 2020
Yunzhu Li Lecture 17 - 48 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| In Robotics: Locomotion
Learning Quadrupedal Locomotion over Challenging Terrain Unitree, Dec. 2024
Science Robotics 2020 |
| Yunzhu Li Lecture 17 - 48 May 29, 2025 |


[Page contains 2 image(s)]


---
## Page 49
---


In Robotics: Dexterous Manipulation
Solving Rubik's Cube with a Robot Hand Visual Dexterity: In-Hand Reorientation of Novel and Complex Object
OpenAI 2019 Shapes, Science Robotics 2023
Yunzhu Li Lecture 17 - 49 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| In Robotics: Dexterous Manipulation
Solving Rubik's Cube with a Robot Hand Visual Dexterity: In-Hand Reorientation of Novel and Complex Object
OpenAI 2019 Shapes, Science Robotics 2023 |
| Yunzhu Li Lecture 17 - 49 May 29, 2025 |


[Page contains 2 image(s)]


---
## Page 50
---


Problems of Model-Free RL
• Learns from trial and error
• Require extensive interactions
Yunzhu Li Lecture 17 - 50 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Problems of Model-Free RL
• Learns from trial and error
• Require extensive interactions |
| Yunzhu Li Lecture 17 - 50 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 51
---


Problems of Model-Free RL
• Learns from trial and error
• Require extensive interactions
• Safety concerns
• Limited interpretability
• What if things go wrong?
Yunzhu Li Lecture 17 - 51 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Problems of Model-Free RL
• Learns from trial and error
• Require extensive interactions
• Safety concerns
• Limited interpretability
• What if things go wrong? |
| Yunzhu Li Lecture 17 - 51 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 52
---


Problems of (Model-Free) RL
• Learns from trial and error
• Require extensive interactions
• Safety concerns
• Limited interpretability
• What if things go wrong?
• Humans maintain an intuitive
model of the world
• Widely applicable
• Sample efficient
Yunzhu Li Lecture 17 - 52 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Problems of (Model-Free) RL
• Learns from trial and error
• Require extensive interactions
• Safety concerns
• Limited interpretability
• What if things go wrong?
• Humans maintain an intuitive
model of the world
• Widely applicable
• Sample efficient |
| Yunzhu Li Lecture 17 - 52 May 29, 2025 |


[Page contains 2 image(s)]


---
## Page 53
---


Overview
- Problem formulation
- Robot perception
- Reinforcement learning
- Model learning & model-based planning
- Imitation learning
- Robotic foundation models
- Remaining challenges
Yunzhu Li Lecture 17 - 53 May 29, 2025

[Page contains 2 table(s)]


### Table 1

| Overview
- Problem formulation
- Robot perception
- Reinforcement learning
- Model learning & model-based planning
- Imitation learning
- Robotic foundation models
- Remaining challenges |
| Yunzhu Li Lecture 17 - 53 May 29, 2025 |


### Table 2

| - Reinforcement learning |
| - Model learning & model-based planning |


---
## Page 54
---


Model Learning & Model-Based Planning
Yunzhu Li Lecture 17 - 54 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Model Learning & Model-Based Planning |
| Yunzhu Li Lecture 17 - 54 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 55
---


Model Learning & Model-Based Planning
Learn a model of the world’s state transition function 𝑃(𝑠 |𝑠 , 𝑎 ) and then use
𝑡+1 𝑡 𝑡
planning through the model to make decisions
Model might not be accurate enough.
1. Execute the first action
2. Obtain new state
3. Re-optimize the action sequence using gradient
descent
Key: GPU for parallel sampling / gradient descent
Key question: what should be the form of 𝑠 ?
𝑡
Yunzhu Li Lecture 17 - 55 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Model Learning & Model-Based Planning
Learn a model of the world’s state transition function 𝑃(𝑠 |𝑠 , 𝑎 ) and then use
𝑡+1 𝑡 𝑡
planning through the model to make decisions
Model might not be accurate enough.
1. Execute the first action
2. Obtain new state
3. Re-optimize the action sequence using gradient
descent
Key: GPU for parallel sampling / gradient descent
Key question: what should be the form of 𝑠 ?
𝑡 |
| Yunzhu Li Lecture 17 - 55 May 29, 2025 |


---
## Page 56
---


Pixel Dynamics - Deep Visual Foresight
Finn and Levine, “Deep Visual Foresight for Planning Robot Motion”, ICRA 2017
Yunzhu Li Lecture 17 - 56 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Pixel Dynamics - Deep Visual Foresight
Finn and Levine, “Deep Visual Foresight for Planning Robot Motion”, ICRA 2017 |
| Yunzhu Li Lecture 17 - 56 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 57
---


Pixel Dynamics - Deep Visual Foresight
Finn and Levine, “Deep Visual Foresight for Planning Robot Motion”, ICRA 2017
Yunzhu Li Lecture 17 - 57 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Pixel Dynamics - Deep Visual Foresight
Finn and Levine, “Deep Visual Foresight for Planning Robot Motion”, ICRA 2017 |
| Yunzhu Li Lecture 17 - 57 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 58
---


Keypoint Dynamics
Manuelli, Li, Florence, Tedrake, “Keypoints into the Future: Self-Supervised Correspondence in Model-Based Reinforcement Learning”, CoRL 2020
Yunzhu Li Lecture 17 - 58 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Keypoint Dynamics
Manuelli, Li, Florence, Tedrake, “Keypoints into the Future: Self-Supervised Correspondence in Model-Based Reinforcement Learning”, CoRL 2020 |
| Yunzhu Li Lecture 17 - 58 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 59
---


Yunzhu Li Lecture 17 - 59 May 29, 2025

[Page contains 1 table(s)]


### Table 1

|  |
| Yunzhu Li Lecture 17 - 59 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 60
---


Particle Dynamics
Wang, Li, Driggs-Campbell, Fei-Fei, Wu, “Dynamic-Resolution Model Learning for Object Pile Manipulation”, RSS 2023
Yunzhu Li Lecture 17 - 60 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Particle Dynamics
Wang, Li, Driggs-Campbell, Fei-Fei, Wu, “Dynamic-Resolution Model Learning for Object Pile Manipulation”, RSS 2023 |
| Yunzhu Li Lecture 17 - 60 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 61
---


Granola Rice
Carrot Candy
Yunzhu Li Lecture 17 - May 29, 2025
24x speed

[Page contains 1 table(s)]


### Table 1

| Granola Rice |
| Carrot Candy
Yunzhu Li Lecture 17 - May 29, 2025
24x speed |


[Page contains 5 image(s)]


---
## Page 62
---


Push to all letters
24x speed
Yunzhu Li Lecture 17 - May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Push to all letters
24x speed |
| Yunzhu Li Lecture 17 - May 29, 2025 |


[Page contains 4 image(s)]


---
## Page 63
---


Haochen Shi*, Huazhe Xu*, Samuel Clarke, Yunzhu Li, and Jiajun Wu
Particle Dynamics
RoboCook: Long-Horizon Elasto-Plastic Object Manipulation with Diverse Tools
Conference on Robot Learning (CoRL) 2023 – Best Systems Paper Award
1 6 11
2 7 12
z
3 8 13
11
y 12
13
10
x
14 15 4 9 14
1 6 7
2 5 8
3 4 9
5 10 15
Yunzhu Li Lecture 17 - 63 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Haochen Shi*, Huazhe Xu*, Samuel Clarke, Yunzhu Li, and Jiajun Wu
Particle Dynamics
RoboCook: Long-Horizon Elasto-Plastic Object Manipulation with Diverse Tools
Conference on Robot Learning (CoRL) 2023 – Best Systems Paper Award
1 6 11
2 7 12
z
3 8 13
11
y 12
13
10
x
14 15 4 9 14
1 6 7
2 5 8
3 4 9
5 10 15 |
| Yunzhu Li Lecture 17 - 63 May 29, 2025 |


[Page contains 16 image(s)]


---
## Page 64
---


Particle Dynamics – Future Prediction
n
o
i
t
c
i
d
e
r
Top P
g
n
i
p
p
i
r
G Side
d
n h
u t
u
o
r
r T
G
Pers.
Yunzhu Li Lecture 17 - 64 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Particle Dynamics – Future Prediction
n
o
i
t
c
i
d
e
r
Top P
g
n
i
p
p
i
r
G Side
d
n h
u t
u
o
r
r T
G
Pers. |
| Yunzhu Li Lecture 17 - 64 May 29, 2025 |


[Page contains 19 image(s)]


---
## Page 65
---


Particle Dynamics – Future Prediction
n
o
i
t
c
i
Top d
e
r
P
g
n
i
s
s
e
r
P Side
d
n h
u t
u
o
r
r T
G
Pers.
Yunzhu Li Lecture 17 - 65 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Particle Dynamics – Future Prediction
n
o
i
t
c
i
Top d
e
r
P
g
n
i
s
s
e
r
P Side
d
n h
u t
u
o
r
r T
G
Pers. |
| Yunzhu Li Lecture 17 - 65 May 29, 2025 |


[Page contains 19 image(s)]


---
## Page 66
---


Particle Dynamics – Future Prediction
n
o
i
t
c
i
Top d
e
r
P
g
n
i
s
s
e
r
P Side
d
n h
u t
u
o
r
r T
G
Pers.
Yunzhu Li Lecture 17 - 66 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Particle Dynamics – Future Prediction
n
o
i
t
c
i
Top d
e
r
P
g
n
i
s
s
e
r
P Side
d
n h
u t
u
o
r
r T
G
Pers. |
| Yunzhu Li Lecture 17 - 66 May 29, 2025 |


[Page contains 19 image(s)]


---
## Page 67
---


Yunzhu Li Lecture 17 - 67 May 29, 2025

[Page contains 1 table(s)]


### Table 1

|  |
| Yunzhu Li Lecture 17 - 67 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 68
---


Overview
- Problem formulation
- Robot perception
- Reinforcement learning
- Model learning & model-based planning
- Imitation learning
- Robotic foundation models
- Remaining challenges
Yunzhu Li Lecture 17 - 68 May 29, 2025

[Page contains 2 table(s)]


### Table 1

| Overview
- Problem formulation
- Robot perception
- Reinforcement learning
- Model learning & model-based planning
- Imitation learning
- Robotic foundation models
- Remaining challenges |
| Yunzhu Li Lecture 17 - 68 May 29, 2025 |


### Table 2

| - Model learning & model-based planning |
| - Imitation learning |


---
## Page 69
---


Imitation Learning
Supervised learning from a
demonstration dataset
Yunzhu Li Lecture 17 - 69 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Imitation Learning
Supervised learning from a
demonstration dataset |
| Yunzhu Li Lecture 17 - 69 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 70
---


Learning from Demonstrations
Yunzhu Li Lecture 17 - 70 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Learning from Demonstrations |
| Yunzhu Li Lecture 17 - 70 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 71
---


Behavior Cloning (BC)
Yunzhu Li Lecture 17 - 71 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Behavior Cloning (BC) |
| Yunzhu Li Lecture 17 - 71 May 29, 2025 |


[Page contains 2 image(s)]


---
## Page 72
---


Iterative Collection of Expert Demonstrations
Yunzhu Li Lecture 17 - 72 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Iterative Collection of Expert Demonstrations |
| Yunzhu Li Lecture 17 - 72 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 73
---


Inverse Reinforcement Learning (IRL)
Yunzhu Li Lecture 17 - 73 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Inverse Reinforcement Learning (IRL) |
| Yunzhu Li Lecture 17 - 73 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 74
---


Inverse Reinforcement Learning (IRL)
Yunzhu Li Lecture 17 - 74 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Inverse Reinforcement Learning (IRL) |
| Yunzhu Li Lecture 17 - 74 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 75
---


Implicit Behavior Cloning (IBC)
Yunzhu Li Lecture 17 - 75 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Implicit Behavior Cloning (IBC) |
| Yunzhu Li Lecture 17 - 75 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 76
---


Implicit Behavior Cloning (IBC)
Yunzhu Li Lecture 17 - 76 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Implicit Behavior Cloning (IBC) |
| Yunzhu Li Lecture 17 - 76 May 29, 2025 |


[Page contains 2 image(s)]


---
## Page 77
---


Diffusion Policies
Yunzhu Li Lecture 17 - 77 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Diffusion Policies |
| Yunzhu Li Lecture 17 - 77 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 78
---


Yunzhu Li Lecture 17 - 78 May 29, 2025

[Page contains 1 table(s)]


### Table 1

|  |
| Yunzhu Li Lecture 17 - 78 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 79
---


Overview
- Problem formulation
- Robot perception
- Reinforcement learning
- Model learning & model-based planning
- Imitation learning
- Robotic foundation models
- Remaining challenges
Yunzhu Li Lecture 17 - 79 May 29, 2025

[Page contains 2 table(s)]


### Table 1

| Overview
- Problem formulation
- Robot perception
- Reinforcement learning
- Model learning & model-based planning
- Imitation learning
- Robotic foundation models
- Remaining challenges |
| Yunzhu Li Lecture 17 - 79 May 29, 2025 |


### Table 2

| - Imitation learning |
| - Robotic foundation models |


---
## Page 80
---


Robotic Foundation Models
What is a Robotic Foundation Model?
❑
No explicit representation of states / transition functions
◻
A policy that maps (observation/state, goal) to action
◻
Yunzhu Li Lecture 17 - 80 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Robotic Foundation Models
What is a Robotic Foundation Model?
❑
No explicit representation of states / transition functions
◻
A policy that maps (observation/state, goal) to action
◻ |
| Yunzhu Li Lecture 17 - 80 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 81
---


Robotic Foundation Models
What is a Robotic Foundation Model?
❑
No explicit representation of states / transition functions
◻
A policy that maps (observation/state, goal) to action
◻
Imitation Learning Reinforcement Learning
(Chi et al., Diffusion Policy) (OpenAI, Solving Rubik’s Cube)
Yunzhu Li Lecture 17 - 81 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Robotic Foundation Models
What is a Robotic Foundation Model?
❑
No explicit representation of states / transition functions
◻
A policy that maps (observation/state, goal) to action
◻
Imitation Learning Reinforcement Learning
(Chi et al., Diffusion Policy) (OpenAI, Solving Rubik’s Cube) |
| Yunzhu Li Lecture 17 - 81 May 29, 2025 |


[Page contains 2 image(s)]


---
## Page 82
---


Robotic Foundation Models
What is a Robotic Foundation Model?
❑
No explicit representation of states / transition functions
◻
A policy that maps (observation/state, goal) to action
◻
Current Foundational Vision-and-Language Models
❑
The output may not always be perfect.
◻
It will always generate something reasonable.
◻
Robotic Foundation Models
❑
The synthesized action may not always be optimal.
◻
The generated trajectory will always be beautiful and reasonable.
◻
Different names
❑
Vision-Language-Action Models (VLAs), Large behavior models (LBMs)
◻
Yunzhu Li Lecture 17 - 82 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Robotic Foundation Models
What is a Robotic Foundation Model?
❑
No explicit representation of states / transition functions
◻
A policy that maps (observation/state, goal) to action
◻
Current Foundational Vision-and-Language Models
❑
The output may not always be perfect.
◻
It will always generate something reasonable.
◻
Robotic Foundation Models
❑
The synthesized action may not always be optimal.
◻
The generated trajectory will always be beautiful and reasonable.
◻
Different names
❑
Vision-Language-Action Models (VLAs), Large behavior models (LBMs)
◻ |
| Yunzhu Li Lecture 17 - 82 May 29, 2025 |


---
## Page 83
---


Robotic Foundation Models
RT-1 (Dec. 2022) RT-X (Oct. 2023) Pi-Zero (Oct. 2024)
RT-2 (Jul. 2023) OpenVLA (Jun. 2024) Helix (Figure)
Hi-Robot (PI)
Gemini Robotics
Pi-0.5 (PI)
GR00T (Nvidia)
DYNA-1
…
Yunzhu Li Lecture 17 - 83 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Robotic Foundation Models
RT-1 (Dec. 2022) RT-X (Oct. 2023) Pi-Zero (Oct. 2024)
RT-2 (Jul. 2023) OpenVLA (Jun. 2024) Helix (Figure)
Hi-Robot (PI)
Gemini Robotics
Pi-0.5 (PI)
GR00T (Nvidia)
DYNA-1
… |
| Yunzhu Li Lecture 17 - 83 May 29, 2025 |


[Page contains 5 image(s)]


---
## Page 84
---


Pi-Zero by Physical Intelligence
First released in October 2024
❑
Yunzhu Li Lecture 17 - 84 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Pi-Zero by Physical Intelligence
First released in October 2024
❑ |
| Yunzhu Li Lecture 17 - 84 May 29, 2025 |


[Page contains 6 image(s)]


---
## Page 85
---


Pi-Zero by Physical Intelligence
Cross-Embodiment Dataset
Yunzhu Li Lecture 17 - 85 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Pi-Zero by Physical Intelligence
Cross-Embodiment Dataset |
| Yunzhu Li Lecture 17 - 85 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 86
---


Pi-Zero by Physical Intelligence
Pre-Training
Yunzhu Li Lecture 17 - 86 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Pi-Zero by Physical Intelligence
Pre-Training |
| Yunzhu Li Lecture 17 - 86 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 87
---


Pi-Zero by Physical Intelligence
Post-Training
Yunzhu Li Lecture 17 - 87 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Pi-Zero by Physical Intelligence
Post-Training |
| Yunzhu Li Lecture 17 - 87 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 88
---


Pi-Zero by Physical Intelligence
Simple in-distribution tasks
Yunzhu Li Lecture 17 - 88 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Pi-Zero by Physical Intelligence
Simple in-distribution tasks |
| Yunzhu Li Lecture 17 - 88 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 89
---


Pi-Zero by Physical Intelligence
Complicated in-distribution tasks
Yunzhu Li Lecture 17 - 89 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Pi-Zero by Physical Intelligence
Complicated in-distribution tasks |
| Yunzhu Li Lecture 17 - 89 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 90
---


Pi-Zero by Physical Intelligence
Unseen tasks
Yunzhu Li Lecture 17 - 90 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Pi-Zero by Physical Intelligence
Unseen tasks |
| Yunzhu Li Lecture 17 - 90 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 91
---


Video I recorded yesterday at PI
Yunzhu Li Lecture 17 - 91 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Video I recorded yesterday at PI |
| Yunzhu Li Lecture 17 - 91 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 92
---


Pi-Zero by Physical Intelligence
Yunzhu Li Lecture 17 - 92 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Pi-Zero by Physical Intelligence |
| Yunzhu Li Lecture 17 - 92 May 29, 2025 |


[Page contains 2 image(s)]


---
## Page 93
---


Overview
- Problem formulation
- Robot perception
- Reinforcement learning
- Model learning & model-based planning
- Imitation learning
- Robotic foundation models
- Remaining challenges
Yunzhu Li Lecture 17 - 93 May 29, 2025

[Page contains 2 table(s)]


### Table 1

| Overview
- Problem formulation
- Robot perception
- Reinforcement learning
- Model learning & model-based planning
- Imitation learning
- Robotic foundation models
- Remaining challenges |
| Yunzhu Li Lecture 17 - 93 May 29, 2025 |


### Table 2

| - Robotic foundation models |
| - Remaining challenges |


---
## Page 94
---


Evaluation of the Robot Learning Models
Evaluation is primarily conducted in the real world
❑
Real-world evaluation is costly and noisy
◻
“We have large enough budget such that we can still make progress.”
■
Weak correlation between training loss and real-world success rate.
◻
Training objectives vs task-specific metrics, training vs testing horizons
■
ALOHA 2
Yunzhu Li Lecture 17 - 94 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Evaluation of the Robot Learning Models
Evaluation is primarily conducted in the real world
❑
Real-world evaluation is costly and noisy
◻
“We have large enough budget such that we can still make progress.”
■
Weak correlation between training loss and real-world success rate.
◻
Training objectives vs task-specific metrics, training vs testing horizons
■
ALOHA 2 |
| Yunzhu Li Lecture 17 - 94 May 29, 2025 |


[Page contains 1 image(s)]


---
## Page 95
---


Evaluation of the Robot Learning Models
What about evaluation in simulation?
❑
Sim-to-real gap: rigid / deformable / cloth
◻ ImageNet in
Efficient asset generation
◻ Embodied AI?
Digitalization of the real world
◻
Procedural generation of realistic and diverse scenes
◻
Correlation between sim and real
◻
Habitat 3.0
Yunzhu Li Lecture 17 - 95 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Evaluation of the Robot Learning Models
What about evaluation in simulation?
❑
Sim-to-real gap: rigid / deformable / cloth
◻ ImageNet in
Efficient asset generation
◻ Embodied AI?
Digitalization of the real world
◻
Procedural generation of realistic and diverse scenes
◻
Correlation between sim and real
◻
Habitat 3.0 |
| Yunzhu Li Lecture 17 - 95 May 29, 2025 |


[Page contains 2 image(s)]


---
## Page 96
---


Foundation Policy → Foundation World Models
My definition of world models: action-conditioned future prediction
❑
Action-Conditioned
Robot Interaction Data
Foundation Foundation
Policy World Models
Yunzhu Li Lecture 17 - 96 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Foundation Policy → Foundation World Models
My definition of world models: action-conditioned future prediction
❑
Action-Conditioned
Robot Interaction Data
Foundation Foundation
Policy World Models |
| Yunzhu Li Lecture 17 - 96 May 29, 2025 |


---
## Page 97
---


Foundation Policy → Foundation World Models
World Models 1X World Models
3D?
❑
Structural Prior?
❑
Learning + Physics?
❑
Corr. w/ Real World
❑
DayDreamer Nvidia Cosmos - World Foundation Model
Yunzhu Li Lecture 17 - 97 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Foundation Policy → Foundation World Models
World Models 1X World Models
3D?
❑
Structural Prior?
❑
Learning + Physics?
❑
Corr. w/ Real World
❑
DayDreamer Nvidia Cosmos - World Foundation Model |
| Yunzhu Li Lecture 17 - 97 May 29, 2025 |


[Page contains 4 image(s)]


---
## Page 98
---


Foundation Models for Embodied Agents
Current foundation models are not tailored for embodied agents
❑
LLM/VLM can fail in embodied-related tasks
◻
Limited understanding of geometric / embodied / physical interactions
◻
Reinforcement learning (RL) from human feedback → RL from
◻
Embodied Feedback
GPT Segment Anything DINOv2
Yunzhu Li Lecture 17 - 98 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Foundation Models for Embodied Agents
Current foundation models are not tailored for embodied agents
❑
LLM/VLM can fail in embodied-related tasks
◻
Limited understanding of geometric / embodied / physical interactions
◻
Reinforcement learning (RL) from human feedback → RL from
◻
Embodied Feedback
GPT Segment Anything DINOv2 |
| Yunzhu Li Lecture 17 - 98 May 29, 2025 |


[Page contains 3 image(s)]


---
## Page 99
---


Adaptation / Life-Long Learning
Adapt to new scenarios
❑
Adapt to human preferences
❑
Self improve / life-long learning
❑
Adapt to new scenarios Adapt to human preferences Improve through experience
Yunzhu Li Lecture 17 - 99 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Adaptation / Life-Long Learning
Adapt to new scenarios
❑
Adapt to human preferences
❑
Self improve / life-long learning
❑
Adapt to new scenarios Adapt to human preferences Improve through experience |
| Yunzhu Li Lecture 17 - 99 May 29, 2025 |


[Page contains 3 image(s)]


---
## Page 100
---


Practical Considerations of Foundation Models
Every robotics work is a system work
❑
System-level considerations: delays / computing / modules talking
❑
to each other
Figure AI: Helix
Physical Intelligence: Hi-Robot
Yunzhu Li Lecture 17 - 100 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Practical Considerations of Foundation Models
Every robotics work is a system work
❑
System-level considerations: delays / computing / modules talking
❑
to each other
Figure AI: Helix
Physical Intelligence: Hi-Robot |
| Yunzhu Li Lecture 17 - 100 May 29, 2025 |


[Page contains 2 image(s)]


---
## Page 101
---


Overview
- Problem formulation
- Robot perception
- Reinforcement learning
- Model learning & model-based planning
- Imitation learning
- Robotic foundation models
- Remaining challenges
Yunzhu Li Lecture 17 - 101 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Overview
- Problem formulation
- Robot perception
- Reinforcement learning
- Model learning & model-based planning
- Imitation learning
- Robotic foundation models
- Remaining challenges |
| Yunzhu Li Lecture 17 - 101 May 29, 2025 |


---
## Page 102
---


Towards foundational robotic models
Images generated using AI
Yunzhu Li Lecture 17 - 102 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Towards foundational robotic models
Images generated using AI |
| Yunzhu Li Lecture 17 - 102 May 29, 2025 |


[Page contains 8 image(s)]


---
## Page 103
---


Next time: Human-Centered AI
Yunzhu Li Lecture 17 - 103 May 29, 2025

[Page contains 1 table(s)]


### Table 1

| Next time: Human-Centered AI |
| Yunzhu Li Lecture 17 - 103 May 29, 2025 |
