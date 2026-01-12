# lecture_16

Extracted using pdfplumber



---
## Page 1
---


Lecture 16:
Multi-Modal Foundation Models
Ranjay Krishna Lecture 16 - 1 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture 16:
Multi-Modal Foundation Models |
| Ranjay Krishna Lecture 16 - 1 May 27, 2025 |


---
## Page 2
---


How have we been thinking about models in
this class so far?
Train a specialized model for each task
Data Task
Data Task
Model 3
Model 1
Domain 3 3
Domain 1 1
Task
Data Task Data
Model 2 Model 4
4
Domain 2 2 Domain 4
Ranjay Krishna Lecture 16 - 2 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| How have we been thinking about models in
this class so far?
Train a specialized model for each task
Data Task
Data Task
Model 3
Model 1
Domain 3 3
Domain 1 1
Task
Data Task Data
Model 2 Model 4
4
Domain 2 2 Domain 4 |
| Ranjay Krishna Lecture 16 - 2 May 27, 2025 |


---
## Page 3
---


Now, we build Foundation Models
Pre-train one model that acts as the foundation
for many different tasks
Task Task
1 3
Large Scale
Foundation
Diverse
Model
Dataset Task Task
2 4
Pre-training Fine-tuning / zero-shot / few-shot
Ranjay Krishna Lecture 16 - 3 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Now, we build Foundation Models
Pre-train one model that acts as the foundation
for many different tasks
Task Task
1 3
Large Scale
Foundation
Diverse
Model
Dataset Task Task
2 4
Pre-training Fine-tuning / zero-shot / few-shot |
| Ranjay Krishna Lecture 16 - 3 May 27, 2025 |


---
## Page 4
---


Foundation Models
Language
Math Symbolic
Problems Reasoning
Common
GPT
Crawl +
Trivia Translation
Pre-training Fine-tuning / zero-shot / few-shot
Ranjay Krishna Lecture 16 - 4 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Foundation Models
Language
Math Symbolic
Problems Reasoning
Common
GPT
Crawl +
Trivia Translation
Pre-training Fine-tuning / zero-shot / few-shot |
| Ranjay Krishna Lecture 16 - 4 May 27, 2025 |


---
## Page 5
---


There are many classes of Foundation Models
Language Classification LM + Vision And More! Chaining
ELMo CLIP LLaVA Segment Anything LMs + CLIP
BERT CoCa Flamingo Whisper Visual Programming
GPT GPT-4V Dalle
T5 Gemini Stable Diffusion
Molmo Imagen
Ranjay Krishna Lecture 16 - 5 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| There are many classes of Foundation Models
Language Classification LM + Vision And More! Chaining
ELMo CLIP LLaVA Segment Anything LMs + CLIP
BERT CoCa Flamingo Whisper Visual Programming
GPT GPT-4V Dalle
T5 Gemini Stable Diffusion
Molmo Imagen |
| Ranjay Krishna Lecture 16 - 5 May 27, 2025 |


---
## Page 6
---


How do identify a model as a Foundation?
Always see with foundation models:
- general /robust to many different tasks
Often see with foundation models:
- Large # params
- Large amount of data
- Self-supervised pre-training objective
Ranjay Krishna Lecture 16 - 6 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| How do identify a model as a Foundation?
Always see with foundation models:
- general /robust to many different tasks
Often see with foundation models:
- Large # params
- Large amount of data
- Self-supervised pre-training objective |
| Ranjay Krishna Lecture 16 - 6 May 27, 2025 |


---
## Page 7
---


Language models are out of scope for this class
Language Classification LM + Vision And More! Chaining
ELMo CLIP LLaVA Segment Anything LMs + CLIP
BERT CoCa Flamingo Whisper Visual Programming
GPT GPT-4V Dalle
T5 Gemini Stable Diffusion
Molmo Imagen
Ranjay Krishna Lecture 16 - 7 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Language models are out of scope for this class
Language Classification LM + Vision And More! Chaining
ELMo CLIP LLaVA Segment Anything LMs + CLIP
BERT CoCa Flamingo Whisper Visual Programming
GPT GPT-4V Dalle
T5 Gemini Stable Diffusion
Molmo Imagen |
| Ranjay Krishna Lecture 16 - 7 May 27, 2025 |


---
## Page 8
---


We will focus on multimodal (vision) foundation models
Language Classification LM + Vision And More! Chaining
ELMo CLIP LLaVA Segment Anything LMs + CLIP
BERT CoCa Flamingo Whisper Visual Programming
GPT GPT-4V Dalle
T5 Gemini Stable Diffusion
Molmo Imagen
Ranjay Krishna Lecture 16 - 8 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| We will focus on multimodal (vision) foundation models
Language Classification LM + Vision And More! Chaining
ELMo CLIP LLaVA Segment Anything LMs + CLIP
BERT CoCa Flamingo Whisper Visual Programming
GPT GPT-4V Dalle
T5 Gemini Stable Diffusion
Molmo Imagen |
| Ranjay Krishna Lecture 16 - 8 May 27, 2025 |


---
## Page 9
---


Let’s start with the foundation models for
classification
Language Classification LM + Vision And More! Chaining
ELMo CLIP LLaVA Segment Anything LMs + CLIP
BERT CoCa Flamingo Whisper Visual Programming
GPT GPT-4V Dalle
T5 Gemini Stable Diffusion
Molmo Imagen
Ranjay Krishna Lecture 16 - 9 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Let’s start with the foundation models for
classification
Language Classification LM + Vision And More! Chaining
ELMo CLIP LLaVA Segment Anything LMs + CLIP
BERT CoCa Flamingo Whisper Visual Programming
GPT GPT-4V Dalle
T5 Gemini Stable Diffusion
Molmo Imagen |
| Ranjay Krishna Lecture 16 - 9 May 27, 2025 |


---
## Page 10
---


Recall this self-supervised objective from
SimCLR
Use Self Supervised
learning to learn good
image features
Can train small classifiers
on top of these features
using supervised learning
Ranjay Krishna Lecture 16 - 10 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Recall this self-supervised objective from
SimCLR
Use Self Supervised
learning to learn good
image features
Can train small classifiers
on top of these features
using supervised learning |
| Ranjay Krishna Lecture 16 - 10 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 11
---


The main idea was to learning concepts without
labels -> a self-supervised pretraining objective
Push Apart
Pull Together
Ranjay Krishna Lecture 16 - 11 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| The main idea was to learning concepts without
labels -> a self-supervised pretraining objective
Push Apart
Pull Together |
| Ranjay Krishna Lecture 16 - 11 May 27, 2025 |


[Page contains 4 image(s)]


---
## Page 12
---


The hope was that the learned representations
generalize to new instances
Ranjay Krishna Lecture 16 - 12 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| The hope was that the learned representations
generalize to new instances |
| Ranjay Krishna Lecture 16 - 12 May 27, 2025 |


[Page contains 8 image(s)]


---
## Page 13
---


Can we generalize these representations
beyond just images? To language perhaps?
B
A
1. “A cute fluffy cat”
2. “My favorite dog is a golden retriever”
Ranjay Krishna Lecture 16 - 13 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Can we generalize these representations
beyond just images? To language perhaps?
B
A
1. “A cute fluffy cat”
2. “My favorite dog is a golden retriever” |
| Ranjay Krishna Lecture 16 - 13 May 27, 2025 |


[Page contains 8 image(s)]


---
## Page 14
---


What if this representation space could also
embed sentences/phrases?
“My favorite dog is
a golden retriever”
“A cute fluffy cat”
Ranjay Krishna Lecture 16 - 14 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| What if this representation space could also
embed sentences/phrases?
“My favorite dog is
a golden retriever”
“A cute fluffy cat” |
| Ranjay Krishna Lecture 16 - 14 May 27, 2025 |


[Page contains 8 image(s)]


---
## Page 15
---


SimClr
Image Image
Encoder Encoder
Ranjay Krishna Lecture 16 - 15 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| SimClr
Image Image
Encoder Encoder |
| Ranjay Krishna Lecture 16 - 15 May 27, 2025 |


[Page contains 6 image(s)]


---
## Page 16
---


SimClr CLIP
Image Image Image Text
Encoder Encoder Encoder Encoder
“My favorite dog is
a golden retriever”
“A cute fluffy cat”
“Monkeys are my
favorite animal”
Ranjay Krishna Lecture 16 - 16 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| SimClr CLIP
Image Image Image Text
Encoder Encoder Encoder Encoder
“My favorite dog is
a golden retriever”
“A cute fluffy cat”
“Monkeys are my
favorite animal” |
| Ranjay Krishna Lecture 16 - 16 May 27, 2025 |


[Page contains 9 image(s)]


---
## Page 17
---


CLIP is trained with the same
contrastive objective
Image Text
Encoder Encoder
“My favorite dog is
a golden retriever”
“A cute fluffy cat”
“Monkeys are my
favorite animal”
Ranjay Krishna Lecture 16 - 17 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| CLIP is trained with the same
contrastive objective
Image Text
Encoder Encoder
“My favorite dog is
a golden retriever”
“A cute fluffy cat”
“Monkeys are my
favorite animal” |
| Ranjay Krishna Lecture 16 - 17 May 27, 2025 |


[Page contains 8 image(s)]


---
## Page 18
---


CLIP Training Objective
Image Text
Encoder Encoder
“My favorite dog is
a golden retriever”
“A cute fluffy cat”
“Monkeys are my
favorite animal”
Ranjay Krishna Lecture 16 - 18 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| CLIP Training Objective
Image Text
Encoder Encoder
“My favorite dog is
a golden retriever”
“A cute fluffy cat”
“Monkeys are my
favorite animal” |
| Ranjay Krishna Lecture 16 - 18 May 27, 2025 |


[Page contains 8 image(s)]


---
## Page 19
---


Lots of image-text data can be found online
CLIP training data was
scraped at scale from
images and their
associated alt-text from
the internet
https://en.wikipedia.org/wiki/Mount_Rainier
Ranjay Krishna Lecture 16 - 19 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Lots of image-text data can be found online
CLIP training data was
scraped at scale from
images and their
associated alt-text from
the internet
https://en.wikipedia.org/wiki/Mount_Rainier |
| Ranjay Krishna Lecture 16 - 19 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 20
---


CLIP Training Objective
At the end of training, you
have a model that will give
you a similarity score
between an image and a
text
Ranjay Krishna Lecture 16 - 20 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| CLIP Training Objective
At the end of training, you
have a model that will give
you a similarity score
between an image and a
text |
| Ranjay Krishna Lecture 16 - 20 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 21
---


Using pre-trained models out of the box
Step 1: Pretrain a
Pre-training tasks:
network on a pretext
Contrastive Objective
task that doesn’t
require supervision
Step 2: Transfer
encoder to
Downstream tasks:
downstream tasks via Image classification,
object detection,
linear classifiers
semantic segmentation
Ranjay Krishna Lecture 16 - 21 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Using pre-trained models out of the box
Step 1: Pretrain a
Pre-training tasks:
network on a pretext
Contrastive Objective
task that doesn’t
require supervision
Step 2: Transfer
encoder to
Downstream tasks:
downstream tasks via Image classification,
object detection,
linear classifiers
semantic segmentation |
| Ranjay Krishna Lecture 16 - 21 May 27, 2025 |


[Page contains 2 image(s)]


---
## Page 22
---


CLIP features w/ linear probe across multiple datasets
Ranjay Krishna Lecture 16 - 22 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| CLIP features w/ linear probe across multiple datasets |
| Ranjay Krishna Lecture 16 - 22 May 27, 2025 |


[Page contains 5 image(s)]


---
## Page 23
---


Big difference with language models: We can use
LLMs zero-shot for new downstream tasks
Step 1: Pretrain a
network on a pretext
“I love ___” “cake”
task that doesn’t
require supervision
“The movie
Step 2: Use the
review ‘I hated “negative”
model out of the box
the movie’ is
in a creative way!
____”
Ranjay Krishna Lecture 16 - 23 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Big difference with language models: We can use
LLMs zero-shot for new downstream tasks
Step 1: Pretrain a
network on a pretext
“I love ___” “cake”
task that doesn’t
require supervision
“The movie
Step 2: Use the
review ‘I hated “negative”
model out of the box
the movie’ is
in a creative way!
____” |
| Ranjay Krishna Lecture 16 - 23 May 27, 2025 |


[Page contains 2 image(s)]


---
## Page 24
---


But how do we use pre-trained vision-language models
in a zero-shot manner?
Step 1: Pretrain a
Pre-training tasks:
network on a pretext
Contrastive Objective
task that doesn’t
require supervision
Step 2: Use the
Out of the box classification
model out of the box
(No fine-tuning)
in a creative way!
Ranjay Krishna Lecture 16 - 24 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| But how do we use pre-trained vision-language models
in a zero-shot manner?
Step 1: Pretrain a
Pre-training tasks:
network on a pretext
Contrastive Objective
task that doesn’t
require supervision
Step 2: Use the
Out of the box classification
model out of the box
(No fine-tuning)
in a creative way! |
| Ranjay Krishna Lecture 16 - 24 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 25
---


Clever trick: we can create a classifier using the
text encoder!
word
redocnE redocnE
Image Text
egamI txeT
Encoder Encoder
0.27
Image vector text vector
matching score
Radford et al “Learning Transferable Visual Models From Natural Language Supervision”
Ranjay Krishna Lecture 16 - 25 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Clever trick: we can create a classifier using the
text encoder!
word
redocnE redocnE
Image Text
egamI txeT
Encoder Encoder
0.27
Image vector text vector
matching score
Radford et al “Learning Transferable Visual Models From Natural Language Supervision” |
| Ranjay Krishna Lecture 16 - 25 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 26
---


Create a vector representation for each category!
plane
dog
bird
redocnE redocnE
Image Text
egamI txeT
Encoder Encoder
“Plane” vector
Image vector
“Dog” vector
“Bird” vector
Radford et al “Learning Transferable Visual Models From Natural Language Supervision”
Ranjay Krishna Lecture 16 - 26 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Create a vector representation for each category!
plane
dog
bird
redocnE redocnE
Image Text
egamI txeT
Encoder Encoder
“Plane” vector
Image vector
“Dog” vector
“Bird” vector
Radford et al “Learning Transferable Visual Models From Natural Language Supervision” |
| Ranjay Krishna Lecture 16 - 26 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 27
---


Match a new image to the most similar vector
plane
dog
bird
redocnE redocnE
Image Text
egamI txeT
Encoder Encoder
0.13
“Plane” vector
Image vector
0.27
“Dog” vector
0.09
“Bird” vector
Radford et al “Learning Transferable Visual Models From Natural Language Supervision”
Ranjay Krishna Lecture 16 - 27 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Match a new image to the most similar vector
plane
dog
bird
redocnE redocnE
Image Text
egamI txeT
Encoder Encoder
0.13
“Plane” vector
Image vector
0.27
“Dog” vector
0.09
“Bird” vector
Radford et al “Learning Transferable Visual Models From Natural Language Supervision” |
| Ranjay Krishna Lecture 16 - 27 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 28
---


You can think of this as a 1-NN algorithm with the
vectors as the training data
plane
dog
bird
redocnE redocnE
Image Text
egamI txeT
Encoder Encoder
0.13
“Plane” vector
Image vector
0.27
“Dog” vector
0.09
“Bird” vector
Radford et al “Learning Transferable Visual Models From Natural Language Supervision”
Ranjay Krishna Lecture 16 - 28 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| You can think of this as a 1-NN algorithm with the
vectors as the training data
plane
dog
bird
redocnE redocnE
Image Text
egamI txeT
Encoder Encoder
0.13
“Plane” vector
Image vector
0.27
“Dog” vector
0.09
“Bird” vector
Radford et al “Learning Transferable Visual Models From Natural Language Supervision” |
| Ranjay Krishna Lecture 16 - 28 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 29
---


Since CLIP was trained with phrases, you can improve
performance by using a phrase “A photo of a [category]”
A photo of a plane
A photo of a dog
A photo of a bird
+1.3% on
redocnE redocnE
Image Text
ImageNet
egamI txeT
Encoder Encoder
0.13
“Plane” vector
Image vector
0.27
“Dog” vector
0.09
“Bird” vector
Radford et al “Learning Transferable Visual Models From Natural Language Supervision”
Ranjay Krishna Lecture 16 - 29 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Since CLIP was trained with phrases, you can improve
performance by using a phrase “A photo of a [category]”
A photo of a plane
A photo of a dog
A photo of a bird
+1.3% on
redocnE redocnE
Image Text
ImageNet
egamI txeT
Encoder Encoder
0.13
“Plane” vector
Image vector
0.27
“Dog” vector
0.09
“Bird” vector
Radford et al “Learning Transferable Visual Models From Natural Language Supervision” |
| Ranjay Krishna Lecture 16 - 29 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 30
---


A single phrase might be too biased.
Solution: Use multiple phrases
A photo of a plane A drawing of a plane …
A photo of a dog A drawing of a dog …
A photo of a bird A drawing of a bird …
redocnE redocnE
Image Text
egamI txeT
Encoder Encoder
“Plane” vector 1 “Plane” vector 2
Image vector
“Dog” vector 1 “Dog” vector 2
“Bird” vector 1 “Bird” vector 2
Radford et al “Learning Transferable Visual Models From Natural Language Supervision”
Ranjay Krishna Lecture 16 - 30 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| A single phrase might be too biased.
Solution: Use multiple phrases
A photo of a plane A drawing of a plane …
A photo of a dog A drawing of a dog …
A photo of a bird A drawing of a bird …
redocnE redocnE
Image Text
egamI txeT
Encoder Encoder
“Plane” vector 1 “Plane” vector 2
Image vector
“Dog” vector 1 “Dog” vector 2
“Bird” vector 1 “Bird” vector 2
Radford et al “Learning Transferable Visual Models From Natural Language Supervision” |
| Ranjay Krishna Lecture 16 - 30 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 31
---


Use the average vector across phrases as the
representation for each category
A photo of a plane A drawing of a plane …
A photo of a dog A drawing of a dog …
A photo of a bird A drawing of a bird …
redocnE redocnE
Image Text +5% on
egamI txeT
Encoder Encoder
ImageNet
0.13
Mean “Plane” vector
Image vector
0.27
Mean “Dog” vector
0.09
Mean “Bird” vector
Radford et al “Learning Transferable Visual Models From Natural Language Supervision”
Ranjay Krishna Lecture 16 - 31 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Use the average vector across phrases as the
representation for each category
A photo of a plane A drawing of a plane …
A photo of a dog A drawing of a dog …
A photo of a bird A drawing of a bird …
redocnE redocnE
Image Text +5% on
egamI txeT
Encoder Encoder
ImageNet
0.13
Mean “Plane” vector
Image vector
0.27
Mean “Dog” vector
0.09
Mean “Bird” vector
Radford et al “Learning Transferable Visual Models From Natural Language Supervision” |
| Ranjay Krishna Lecture 16 - 31 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 32
---


That’s it! Now, you can use CLIP as a foundation
model for image classification for any dataset
Radford et al “Learning Transferable Visual Models From Natural Language Supervision”
Ranjay Krishna Lecture 16 - 32 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| That’s it! Now, you can use CLIP as a foundation
model for image classification for any dataset
Radford et al “Learning Transferable Visual Models From Natural Language Supervision” |
| Ranjay Krishna Lecture 16 - 32 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 33
---


Exciting result after training on 400M image-text pairs
Matches the accuracy of of ResNet 101 that has been trained
on ImageNet, except CLIP was trained with no human labels
at all!
Radford et al “Learning Transferable Visual Models From Natural Language Supervision”
Ranjay Krishna Lecture 16 - 33 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Exciting result after training on 400M image-text pairs
Matches the accuracy of of ResNet 101 that has been trained
on ImageNet, except CLIP was trained with no human labels
at all!
Radford et al “Learning Transferable Visual Models From Natural Language Supervision” |
| Ranjay Krishna Lecture 16 - 33 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 34
---


Here’s where things get even more exciting
Radford et al “Learning Transferable Visual Models From Natural Language Supervision”
Ranjay Krishna Lecture 16 - 34 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Here’s where things get even more exciting
Radford et al “Learning Transferable Visual Models From Natural Language Supervision” |
| Ranjay Krishna Lecture 16 - 34 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 35
---


Training on ImageNet doesn’t generalize to other datasets.
ObjectNet contains the same categories but in weird viewpoints
Radford et al “Learning Transferable Visual Models From Natural Language Supervision”
Ranjay Krishna Lecture 16 - 35 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Training on ImageNet doesn’t generalize to other datasets.
ObjectNet contains the same categories but in weird viewpoints
Radford et al “Learning Transferable Visual Models From Natural Language Supervision” |
| Ranjay Krishna Lecture 16 - 35 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 36
---


But CLIP zero-shot does so well!
Q. Why do you think that is?
Radford et al “Learning Transferable Visual Models From Natural Language Supervision”
Ranjay Krishna Lecture 16 - 36 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| But CLIP zero-shot does so well!
Q. Why do you think that is?
Radford et al “Learning Transferable Visual Models From Natural Language Supervision” |
| Ranjay Krishna Lecture 16 - 36 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 37
---


CLIP performance is
great also on graphic
images , sketches,
adversarial datasets,
Radford et al “Learning Transferable Visual Models From Natural Language Supervision”
Ranjay Krishna Lecture 16 - 37 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| CLIP performance is
great also on graphic
images , sketches,
adversarial datasets,
Radford et al “Learning Transferable Visual Models From Natural Language Supervision” |
| Ranjay Krishna Lecture 16 - 37 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 38
---


Difference in performance between
linear probe vs zero-shot
Radford et al “Learning Transferable Visual Models From Natural Language Supervision”
Ranjay Krishna Lecture 16 - 38 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Difference in performance between
linear probe vs zero-shot
Radford et al “Learning Transferable Visual Models From Natural Language Supervision” |
| Ranjay Krishna Lecture 16 - 38 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 39
---


Why does CLIP perform so well?
How can no labels beat labels??
Scale!
Ranjay Krishna Lecture 16 - 39 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Why does CLIP perform so well?
How can no labels beat labels??
Scale! |
| Ranjay Krishna Lecture 16 - 39 May 27, 2025 |


---
## Page 40
---


CLIP scaled up the model parameters with the
transformer architecture
Clip Parameters
(307 Million)
ImageNet ResNet Parameters
(44.5 Million)
Ranjay Krishna Lecture 16 - 40 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| CLIP scaled up the model parameters with the
transformer architecture
Clip Parameters
(307 Million)
ImageNet ResNet Parameters
(44.5 Million) |
| Ranjay Krishna Lecture 16 - 40 May 27, 2025 |


---
## Page 41
---


CLIP Scaled up the
training data by scraping
image-text pairs from the
internet
Clip Training Data
(400 Million images)
ImageNet ResNet Training Data
(1.28 Million)
Ranjay Krishna Lecture 16 - 41 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| CLIP Scaled up the
training data by scraping
image-text pairs from the
internet
Clip Training Data
(400 Million images)
ImageNet ResNet Training Data
(1.28 Million) |
| Ranjay Krishna Lecture 16 - 41 May 27, 2025 |


---
## Page 42
---


CoCa improved upon CLIP by adding a
generation objective
“Contrastive Captioners are Image-Text Foundation Models”, 2022
Ranjay Krishna Lecture 16 - 42 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| CoCa improved upon CLIP by adding a
generation objective
“Contrastive Captioners are Image-Text Foundation Models”, 2022 |
| Ranjay Krishna Lecture 16 - 42 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 43
---


CoCa added a decoder with a captioning loss
“Contrastive Captioners are Image-Text Foundation Models”, 2022
Ranjay Krishna Lecture 16 - 43 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| CoCa added a decoder with a captioning loss
“Contrastive Captioners are Image-Text Foundation Models”, 2022 |
| Ranjay Krishna Lecture 16 - 43 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 44
---


CoCa: Contrastive Captioners are Image-Text
Foundation Models
Ranjay Krishna Lecture 16 - 44 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| CoCa: Contrastive Captioners are Image-Text
Foundation Models |
| Ranjay Krishna Lecture 16 - 44 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 45
---


Classifier foundation models now beat all other
models on ImageNet
Ranjay Krishna Lecture 16 - 45 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Classifier foundation models now beat all other
models on ImageNet |
| Ranjay Krishna Lecture 16 - 45 May 27, 2025 |


[Page contains 2 image(s)]


---
## Page 46
---


Advantages of CLIP-style models
1. Dot product is super efficient
a. Easy to train (enables scaling)
b. Fast inference, e.g., retrieval over 5B images
2. Open-vocabulary (zero-shot generalization)
3. Can be chained with other models (CuPL)
[we will discuss this later today]
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Advantages of CLIP-style models
1. Dot product is super efficient
a. Easy to train (enables scaling)
b. Fast inference, e.g., retrieval over 5B images
2. Open-vocabulary (zero-shot generalization)
3. Can be chained with other models (CuPL)
[we will discuss this later today] |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


---
## Page 47
---


April 2022, Tristan Thrush et al:
CLIP can’t distinguish between:
there is a mug in some grass there is some grass in a mug
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| April 2022, Tristan Thrush et al:
CLIP can’t distinguish between:
there is a mug in some grass there is some grass in a mug |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


[Page contains 3 image(s)]


---
## Page 48
---


Disadvantages of CLIP-style models
1. Rely too heavily on batch size to learn concepts
Increasing batch size helps you understand fine-grained concepts
Batch size: 4 “animal”
Batch size: 100 “dog”
Batch size: 32000 “Welsh Corgi”
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Disadvantages of CLIP-style models
1. Rely too heavily on batch size to learn concepts
Increasing batch size helps you understand fine-grained concepts
Batch size: 4 “animal”
Batch size: 100 “dog”
Batch size: 32000 “Welsh Corgi” |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 49
---


Disadvantages of CLIP-style models
1. Rely too heavily on batch size to learn concepts
Increasing batch size helps you understand fine-grained concepts
But there’s a limit to how fine-grained you can get this way
Even in a batch of 32K, it’s unlikely you see both “a mug in some
grass” and “some grass in a mug”
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Disadvantages of CLIP-style models
1. Rely too heavily on batch size to learn concepts
Increasing batch size helps you understand fine-grained concepts
But there’s a limit to how fine-grained you can get this way
Even in a batch of 32K, it’s unlikely you see both “a mug in some
grass” and “some grass in a mug” |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


---
## Page 50
---


Disadvantages of CLIP-style models
1. Rely too heavily on batch size to learn concepts
Winoground CREPE ARO …
there is a mug in there is some
some grass grass in a mug
“compositionality”
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Disadvantages of CLIP-style models
1. Rely too heavily on batch size to learn concepts
Winoground CREPE ARO …
there is a mug in there is some
some grass grass in a mug
“compositionality” |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


[Page contains 5 image(s)]


---
## Page 51
---


Disadvantages of CLIP-style models
1. Rely too heavily on batch size to learn concepts
Solution? Hard Negative Fine-Tuning
horse eating grass grass eating horse
TODO: Get
NegCLIP
scores for
these
captions now
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Disadvantages of CLIP-style models
1. Rely too heavily on batch size to learn concepts
Solution? Hard Negative Fine-Tuning
horse eating grass grass eating horse
TODO: Get
NegCLIP
scores for
these
captions now |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 52
---


Disadvantages of CLIP-style models
1. Rely too heavily on batch size to learn concepts
But training with hard negatives has its own problems…
A black cat and a brown dog
✓
A brown cat and a black dog
✗
“hard positives”
A brown dog and a black cat
✗
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Disadvantages of CLIP-style models
1. Rely too heavily on batch size to learn concepts
But training with hard negatives has its own problems…
A black cat and a brown dog
✓
A brown cat and a black dog
✗
“hard positives”
A brown dog and a black cat
✗ |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


---
## Page 53
---


Disadvantages of CLIP-style models
1. Rely too heavily on batch size to learn concepts
2. Image-level captions are insufficient supervision
“living room” ✓
“house plants” ✗
“couch” ✗
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Disadvantages of CLIP-style models
1. Rely too heavily on batch size to learn concepts
2. Image-level captions are insufficient supervision
“living room” ✓
“house plants” ✗
“couch” ✗ |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 54
---


Disadvantages of CLIP-style models
1. Rely too heavily on batch size to learn concepts
2. Image-level captions are insufficient supervision
Also train on region captions
with bounding box coordinates
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Disadvantages of CLIP-style models
1. Rely too heavily on batch size to learn concepts
2. Image-level captions are insufficient supervision
Also train on region captions
with bounding box coordinates |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 55
---


Disadvantages of CLIP-style models
1. Rely too heavily on batch size to learn concepts
2. Image-level captions are insufficient supervision
3. You can’t know everything in your 5B dataset
It’s extremely important to be
intentional about data collection
and filtering
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Disadvantages of CLIP-style models
1. Rely too heavily on batch size to learn concepts
2. Image-level captions are insufficient supervision
3. You can’t know everything in your 5B dataset
It’s extremely important to be
intentional about data collection
and filtering |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 56
---


Foundation Models
Language Classification LM + Vision And More! Chaining
ELMo CLIP LLaVA Segment Anything LMs + CLIP
BERT CoCa Flamingo Whisper Visual Programming
GPT GPT-4V Dalle
T5 Gemini Stable Diffusion
Molmo Imagen
Ranjay Krishna Lecture 16 - 56 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Foundation Models
Language Classification LM + Vision And More! Chaining
ELMo CLIP LLaVA Segment Anything LMs + CLIP
BERT CoCa Flamingo Whisper Visual Programming
GPT GPT-4V Dalle
T5 Gemini Stable Diffusion
Molmo Imagen |
| Ranjay Krishna Lecture 16 - 56 May 27, 2025 |


---
## Page 57
---


LLaVA
Motivation: Language models which do next token prediction
can be applied to a wide variety of tasks at inference (Math,
sentiment analysis, symbolic reasoning)
Can we build a model that can accept images and text as
input, and then output text?
→ Vision-Language Models
Ranjay Krishna Lecture 16 - 57 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| LLaVA
Motivation: Language models which do next token prediction
can be applied to a wide variety of tasks at inference (Math,
sentiment analysis, symbolic reasoning)
Can we build a model that can accept images and text as
input, and then output text?
→ Vision-Language Models |
| Ranjay Krishna Lecture 16 - 57 May 27, 2025 |


---
## Page 58
---


First, some historical context
Vision-Language Models didn’t start with LLaVA!
They go as far back as 2019 → ViLBERT
Ranjay Krishna Lecture 16 - 58 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| First, some historical context
Vision-Language Models didn’t start with LLaVA!
They go as far back as 2019 → ViLBERT |
| Ranjay Krishna Lecture 16 - 58 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 59
---


Historical context
Vision-Language Models didn’t start with LLaVA!
They go as far back as 2019 → ViLBERT
BUT, they had to finetune for each task separately,
with non-trivial task-specific methods (e.g., Mask-RCNN
bounding box re-ranking for RefCOCO)
→
Same paradigm as we discussed right at the beginning of this lecture:
very task-specific
Ranjay Krishna Lecture 16 - 59 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Historical context
Vision-Language Models didn’t start with LLaVA!
They go as far back as 2019 → ViLBERT
BUT, they had to finetune for each task separately,
with non-trivial task-specific methods (e.g., Mask-RCNN
bounding box re-ranking for RefCOCO)
→
Same paradigm as we discussed right at the beginning of this lecture:
very task-specific |
| Ranjay Krishna Lecture 16 - 59 May 27, 2025 |


---
## Page 60
---


LLaVA uses the
autoregressive nature
of LLMs
mul(→) + add (↑)
Ranjay Krishna Lecture 16 - 60 May 27, 2025
tnemngilA
q
0
noitnettA
cute
y y y
0 1 2
v 0 a 0 0, a 1 0, a 2 0,
v 1 a 0 1, a 1 1, a 2 1,
v 2 a 0 2, a 1 2, a 2 2,
(↑)
softmax
CaIts k e0, e0, e0,
0 0 1 2
Laorvee k e1, e1, e1,
1 0 1 2
so k e2, e2, e2,
2 0 1 2
q q
1 2

[Page contains 7 table(s)]


### Table 1

| LLaVA uses the
autoregressive nature cute
y y y
of LLMs 0 1 2
mul(→) + add (↑)
noitnettA
v 0 a 0 0, a 1 0, a 2 0,
v 1 a 0 1, a 1 1, a 2 1,
v 2 a 0 2, a 1 2, a 2 2,
(↑)
softmax
tnemngilA
CaIts k e0, e0, e0,
0 0 1 2
Laorvee k e1, e1, e1,
1 0 1 2
so k e2, e2, e2,
2 0 1 2
q q q
0 1 2 |
| Ranjay Krishna Lecture 16 - 60 May 27, 2025 |


### Table 2

| v
0 |
| v
1 |
| v
2 |


### Table 3

| a0,
0 | a0,
1 | a0,
2 |
| a1,
0 | a1,
1 | a1,
2 |
| a2,
0 | a2,
1 | a2,
2 |


### Table 4

| CaIts |
| Laorvee |
| so |


### Table 5

| k
0 |
| k
1 |
| k
2 |


### Table 6

| e0,
0 | e0,
1 | e0,
2 |
| e1,
0 | e1,
1 | e1,
2 |
| e2,
0 | e2,
1 | e2,
2 |


### Table 7

| q
0 | q
1 | q
2 |


---
## Page 61
---


Recall how transformers
decode language
Cute
Transformer block
Transformer block
Transformer block
Cats are so
Input Text
Ranjay Krishna Lecture 16 - 61 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Recall how transformers
decode language
Cute
Transformer block
Transformer block
Transformer block
Cats are so
Input Text |
| Ranjay Krishna Lecture 16 - 61 May 27, 2025 |


---
## Page 62
---


Key idea behind LLaVA – add visual
information to the LLM
Cute
Transformer block
Transformer block
Transformer block
V V … V Cats are so
1 2 N
Which image tokens
Input image tokens
Input Text
work best here?
Ranjay Krishna Lecture 16 - 62 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Key idea behind LLaVA – add visual
information to the LLM
Cute
Transformer block
Transformer block
Transformer block
V V … V Cats are so
1 2 N
Which image tokens
Input image tokens
Input Text
work best here? |
| Ranjay Krishna Lecture 16 - 62 May 27, 2025 |


---
## Page 63
---


The CLIP encoder is a good option!
At the end of training, you
have a model that will give
you a similarity score
between an image and a
text
Ranjay Krishna Lecture 16 - 63 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| The CLIP encoder is a good option!
At the end of training, you
have a model that will give
you a similarity score
between an image and a
text |
| Ranjay Krishna Lecture 16 - 63 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 64
---


What features should we use
from CLIP? Extract Image Features from CLS
token for contrastive learning
Pooling token
CLS CLS
… …
…
Patchify
Flatten + Linear proj +
2D pos embed Vision Transformer
[Image source]
Ranjay Krishna Lecture 16 - 64 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| What features should we use
from CLIP? Extract Image Features from CLS
token for contrastive learning
Pooling token
CLS CLS
… …
…
Patchify
Flatten + Linear proj +
2D pos embed Vision Transformer
[Image source] |
| Ranjay Krishna Lecture 16 - 64 May 27, 2025 |


[Page contains 5 image(s)]


---
## Page 65
---


What features should we use
from CLIP?
Pooling token
CLS CLS
… …
…
Patchify
Flatten + Linear proj +
But these tokens are not
2D pos embed Vision Transformer
supervised! (Could be random
and loss will not change)
Ranjay Krishna Lecture 16 - 65 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| What features should we use
from CLIP?
Pooling token
CLS CLS
… …
…
Patchify
Flatten + Linear proj +
But these tokens are not
2D pos embed Vision Transformer
supervised! (Could be random
and loss will not change) |
| Ranjay Krishna Lecture 16 - 65 May 27, 2025 |


[Page contains 5 image(s)]


---
## Page 66
---


Use Penultimate Layer!
Vision Transformer
Pooling token
CLS CLS CLS
… …
…
Patchify
Flatten + Linear proj +
L – 1 Layers Final Layer
2D pos embed
In practice, these tokens preserve spatial and linguistic
information best for LLMs. Can drop CLS for slight gains.
Ranjay Krishna Lecture 16 - 66 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Use Penultimate Layer!
Vision Transformer
Pooling token
CLS CLS CLS
… …
…
Patchify
Flatten + Linear proj +
L – 1 Layers Final Layer
2D pos embed
In practice, these tokens preserve spatial and linguistic
information best for LLMs. Can drop CLS for slight gains. |
| Ranjay Krishna Lecture 16 - 66 May 27, 2025 |


[Page contains 5 image(s)]


---
## Page 67
---


LLaVA – Overall Architecture + Training Recipe
1. Initialize with pretrained Language Model Cute
for LLM Decoder (e.g. LLaMA) and
pretrained image encoder (e.g. CLIP)
Transformer block
2. Train a new linear layer to bridge CLIP
LLM
features to LLM input space Transformer block
Decoder
3. Finetune LLM + linear layer together
Transformer block
V V … V Cats are so
1 2 N
Vision
Encoder Linear Layer Input Text
(CLIP)
Can get reasonable performance with >100,000 samples
containing an input image, input instruction, and output text.
Ranjay Krishna Lecture 16 - 67 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| LLaVA – Overall Architecture + Training Recipe
1. Initialize with pretrained Language Model Cute
for LLM Decoder (e.g. LLaMA) and
pretrained image encoder (e.g. CLIP)
Transformer block
2. Train a new linear layer to bridge CLIP
LLM
features to LLM input space Transformer block
Decoder
3. Finetune LLM + linear layer together
Transformer block
V V … V Cats are so
1 2 N
Vision
Encoder Linear Layer Input Text
(CLIP)
Can get reasonable performance with >100,000 samples
containing an input image, input instruction, and output text. |
| Ranjay Krishna Lecture 16 - 67 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 68
---


Flamingo followed up with a new way to fuse
visual features
Cute
Transformer block
Vision Transformer block
encoder
Transformer block
<Image> This cat is so
Ranjay Krishna Lecture 16 - 68 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Flamingo followed up with a new way to fuse
visual features
Cute
Transformer block
Vision Transformer block
encoder
Transformer block
<Image> This cat is so |
| Ranjay Krishna Lecture 16 - 68 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 69
---


Pre-trained parts of Flamingo
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022.
Ranjay Krishna Lecture 16 - 69 May 27, 2025
”

[Page contains 5 table(s)]


### Table 1

| Pre-trained parts of Flamingo
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022. |
| Ranjay Krishna Lecture 16 - 69 May 27, 2025
” |


### Table 2

|  |  |  |


### Table 3

|  |  |


### Table 4

|  |  |


### Table 5

| - | Shot Learning. 2022. |


[Page contains 1 image(s)]


---
## Page 70
---


There are 2 learned parts in Flamingo
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022.
Ranjay Krishna Lecture 16 - 70 May 27, 2025
”

[Page contains 3 table(s)]


### Table 1

| There are 2 learned parts in Flamingo
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022. |
| Ranjay Krishna Lecture 16 - 70 May 27, 2025
” |


### Table 2

|  |  |  |


### Table 3

| - | Shot Learning. 2022. |


[Page contains 1 image(s)]


---
## Page 71
---


Perceiver sampler converts variable
sized image tokens to fixed sized
ones
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022.
Ranjay Krishna Lecture 16 - 71 May 27, 2025
”

[Page contains 2 table(s)]


### Table 1

| Perceiver sampler converts variable
sized image tokens to fixed sized
ones
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022. |
| Ranjay Krishna Lecture 16 - 71 May 27, 2025
” |


### Table 2

| - | Shot Learning. 2022. |


[Page contains 1 image(s)]


---
## Page 72
---


Flamingo full architecture
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022.
Ranjay Krishna Lecture 16 - 72 May 27, 2025
”

[Page contains 2 table(s)]


### Table 1

| Flamingo full architecture
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022. |
| Ranjay Krishna Lecture 16 - 72 May 27, 2025
” |


### Table 2

| - | Shot Learning. 2022. |


[Page contains 1 image(s)]


---
## Page 73
---


Flamingo full architecture
Learned method of
down-sampling
image/video
representations
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022.
Ranjay Krishna Lecture 16 - 73 May 27, 2025
”

[Page contains 2 table(s)]


### Table 1

| Flamingo full architecture
Learned method of
down-sampling
image/video
representations
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022. |
| Ranjay Krishna Lecture 16 - 73 May 27, 2025
” |


### Table 2

| - | Shot Learning. 2022. |


[Page contains 1 image(s)]


---
## Page 74
---


Flamingo full architecture
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022.
Ranjay Krishna Lecture 16 - 74 May 27, 2025
”

[Page contains 2 table(s)]


### Table 1

| Flamingo full architecture
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022. |
| Ranjay Krishna Lecture 16 - 74 May 27, 2025
” |


### Table 2

| - | Shot Learning. 2022. |


[Page contains 1 image(s)]


---
## Page 75
---


Flamingo gated cross-attention
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022.
Ranjay Krishna Lecture 16 - 75 May 27, 2025
”

[Page contains 2 table(s)]


### Table 1

| Flamingo gated cross-attention
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022. |
| Ranjay Krishna Lecture 16 - 75 May 27, 2025
” |


### Table 2

| - | Shot Learning. 2022. |


[Page contains 1 image(s)]


---
## Page 76
---


Flamingo gated cross-attention
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022.
Ranjay Krishna Lecture 16 - 76 May 27, 2025
”

[Page contains 2 table(s)]


### Table 1

| Flamingo gated cross-attention
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022. |
| Ranjay Krishna Lecture 16 - 76 May 27, 2025
” |


### Table 2

| - | Shot Learning. 2022. |


[Page contains 1 image(s)]


---
## Page 77
---


Flamingo arranges its training data
similar to language modeling,
with special tags <image>, <eos> to indicate when a
new image shows up or the text ends.
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022.
Ranjay Krishna Lecture 16 - 77 May 27, 2025
”

[Page contains 3 table(s)]


### Table 1

| Flamingo arranges its training data
similar to language modeling,
with special tags <image>, <eos> to indicate when a
new image shows up or the text ends.
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022. |
| Ranjay Krishna Lecture 16 - 77 May 27, 2025
” |


### Table 2

|  |  |  |
|  |  |  |


### Table 3

| - | Shot Learning. 2022. |


[Page contains 1 image(s)]


---
## Page 78
---


Flamingo masked attention
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022.
Ranjay Krishna Lecture 16 - 78 May 27, 2025
”

[Page contains 2 table(s)]


### Table 1

| Flamingo masked attention
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022. |
| Ranjay Krishna Lecture 16 - 78 May 27, 2025
” |


### Table 2

| - | Shot Learning. 2022. |


[Page contains 1 image(s)]


---
## Page 79
---


Flamingo masked attention
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022.
Ranjay Krishna Lecture 16 - 79 May 27, 2025
”

[Page contains 2 table(s)]


### Table 1

| Flamingo masked attention
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022. |
| Ranjay Krishna Lecture 16 - 79 May 27, 2025
” |


### Table 2

| - | Shot Learning. 2022. |


[Page contains 1 image(s)]


---
## Page 80
---


Flamingo full architecture
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022.
Ranjay Krishna Lecture 16 - 80 May 27, 2025
”

[Page contains 2 table(s)]


### Table 1

| Flamingo full architecture
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022. |
| Ranjay Krishna Lecture 16 - 80 May 27, 2025
” |


### Table 2

| - | Shot Learning. 2022. |


[Page contains 1 image(s)]


---
## Page 81
---


Flamingo results
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022.
Ranjay Krishna Lecture 16 - 81 May 27, 2025
”

[Page contains 2 table(s)]


### Table 1

| Flamingo results
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022. |
| Ranjay Krishna Lecture 16 - 81 May 27, 2025
” |


### Table 2

| - | Shot Learning. 2022. |


[Page contains 1 image(s)]


---
## Page 82
---


Flaming enables in-context learning
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022.
Ranjay Krishna Lecture 16 - 82 May 27, 2025
”

[Page contains 2 table(s)]


### Table 1

| Flaming enables in-context learning
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022. |
| Ranjay Krishna Lecture 16 - 82 May 27, 2025
” |


### Table 2

| - | Shot Learning. 2022. |


[Page contains 1 image(s)]


---
## Page 83
---


Flamingo results
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022.
Ranjay Krishna Lecture 16 - 83 May 27, 2025
”

[Page contains 2 table(s)]


### Table 1

| Flamingo results
Alayrac et al “Flamingo: a Visual Language Model for Few-Shot Learning. 2022. |
| Ranjay Krishna Lecture 16 - 83 May 27, 2025
” |


### Table 2

| - | Shot Learning. 2022. |


[Page contains 1 image(s)]


---
## Page 84
---


Results: zero & few shot
Ranjay Krishna Lecture 16 - 84 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Results: zero & few shot |
| Ranjay Krishna Lecture 16 - 84 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 85
---


Results: zero & few shot
Ranjay Krishna Lecture 16 - 85 May 27, 2025

[Page contains 4 table(s)]


### Table 1

| Results: zero & few shot |
| Ranjay Krishna Lecture 16 - 85 May 27, 2025 |


### Table 2

|  |
|  |


### Table 3

|  |
|  |


### Table 4

|  |
|  |


[Page contains 1 image(s)]


---
## Page 86
---


Today, average performance across
11 visual understanding benchmarks
API Only
Open
Weights
Distilled
Open
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

|  | Today, average performance across
11 visual understanding benchmarks
API Only
Open
Weights
Distilled |  |
|  | Open
Weights
Distilled |  |
|  |  |  |
|  |  |  |
|  | Open | Krishna |


[Page contains 8 image(s)]


---
## Page 87
---


There are open-weight models
but they are all distilled from GPT
API Only
Open
Weights
Distilled
Open
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 2 table(s)]


### Table 1

|  | There are open-weight models
but they are all distilled from GPT
API Only
Open
Weights
Distilled |
|  |  |
|  | Open |


### Table 2

|  |
| Krishna |


[Page contains 8 image(s)]


---
## Page 88
---


How do we close the gap without relying
on proprietary models?
88
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| How do we close the gap without relying
on proprietary models? |
| 88
Ranjay Krishna Lecture 16 - May 27, 2025 |


---
## Page 89
---


There are open-weight models
but they are all distilled from GPT
API Only
Open
Weights
Distilled
Open
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 2 table(s)]


### Table 1

|  | There are open-weight models
but they are all distilled from GPT
API Only
Open
Weights
Distilled |
|  |  |
|  | Open |


### Table 2

|  |
| Krishna |


[Page contains 8 image(s)]


---
## Page 90
---


Open
Weights
Data
Code
Evals
API Only
Completely
Open
Open Weights
Open Data
Open
Weights
Open Code
Open Evals
Distilled
Open
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

|  | Open
Weights
Data
Code
Evals
API Only
Completely
Open
Open Weights
Open Data
Open
Weights
Open Code
Open Evals
Distilled |
|  |  |
|  | Open |


[Page contains 1 image(s)]


---
## Page 91
---


Open
Weights
Data
Code
Evals
API Only
Open
Weights
Distilled
Open
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

|  | Open
Weights
Data
Code
Evals
API Only
Open
Weights
Distilled |
|  |  |
|  | Open |


[Page contains 1 image(s)]


---
## Page 92
---


One of the largest human
preference evaluations for VLMs
with 325k pairwise comparisons
and 870 human annotators
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| One of the largest human
preference evaluations for VLMs
with 325k pairwise comparisons
and 870 human annotators |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 93
---


Molmo – 72B model ranks second for vision
tasks
Barely second to GPT-4o
Outperforming Gemini 1.5 Pro and Claude-3.5
with 325k pairwise comparisons
and 870 human annotators
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Molmo – 72B model ranks second for vision
tasks
Barely second to GPT-4o
Outperforming Gemini 1.5 Pro and Claude-3.5
with 325k pairwise comparisons
and 870 human annotators |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 94
---


Molmo-7B outperforms
- Gemini 1.5 Flash
- LLAVA OneVision 72B
- GPT-4V
- QwenVL2 72B
- and many others
with 325k pairwise comparisons
and 870 human annotators
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 2 table(s)]


### Table 1

| Molmo-7B outperforms
- Gemini 1.5 Flash
- LLAVA OneVision 72B
- GPT-4V
- QwenVL2 72B
- and many others
with 325k pairwise comparisons
and 870 human annotators |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


### Table 2

|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |


[Page contains 1 image(s)]


---
## Page 95
---


Reaction online – released Sep 25, 2024
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Reaction online – released Sep 25, 2024 |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


[Page contains 5 image(s)]


---
## Page 96
---


Never bet against
open-source
software!
96
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Never bet against
open-source
software! |
| 96
Ranjay Krishna Lecture 16 - May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 97
---


Molmo grounds reasoning
directly in the pixels
Example, it points when it
counts
97
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Molmo grounds reasoning
directly in the pixels
Example, it points when it
counts |
| 97
Ranjay Krishna Lecture 16 - May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 98
---


Data matters! Quality over quantity even for pretraining
Molmo is trained with
PixMo
LLAMA 3.1V
700k Image-Text pairs
6 Billion Image-Text pairs
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Data matters! Quality over quantity even for pretraining
Molmo is trained with
PixMo
LLAMA 3.1V
700k Image-Text pairs
6 Billion Image-Text pairs |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 99
---


Internet data is incidental
Human annotated data is intentional
pink, japan,
aesthetic image
love this winter picture by
person
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Internet data is incidental
Human annotated data is intentional
pink, japan,
aesthetic image
love this winter picture by
person |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


[Page contains 2 image(s)]


---
## Page 100
---


PixMo data is intentional:
This photograph captures a well-organized work desk set prominently
in the middle of the frame. The desk is large and rectangular, made
from a polished, rich wood that spans horizontally across the image. Its
structure is supported by four distinctive A-shaped legs, adding an
elegant touch. On the desk, a striking dual-monitor setup is noticeable:
a tall, vertical screen placed behind and to the right of a wider,
horizontal computer monitor.
To the right of these monitors, a black mouse rests on a mouse pad.
Scattered around the mouse pad, some white papers or letters are
strewn across the far right side. On the left side of the desk, a black
desk lamp with an extended arm hangs down, illuminating the
workspace. Nearby, a stack of books is neatly placed in the upper left
corner of the table.
The background wall is painted a subtle beige-white, complementing
the refined ambiance of the space. The floor below the desk features
elegant pinkish marble tiles, enhancing the room’s sophisticated look.
To the far right of the image, a large window or patio door allows natural
light to pour in, with clear glass that offers a glimpse into the outside
area. This exterior view includes part of a rustic brick wall and a metal
pail, hinting at an adjacent patio.
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| PixMo data is intentional:
This photograph captures a well-organized work desk set prominently
in the middle of the frame. The desk is large and rectangular, made
from a polished, rich wood that spans horizontally across the image. Its
structure is supported by four distinctive A-shaped legs, adding an
elegant touch. On the desk, a striking dual-monitor setup is noticeable:
a tall, vertical screen placed behind and to the right of a wider,
horizontal computer monitor.
To the right of these monitors, a black mouse rests on a mouse pad.
Scattered around the mouse pad, some white papers or letters are
strewn across the far right side. On the left side of the desk, a black
desk lamp with an extended arm hangs down, illuminating the
workspace. Nearby, a stack of books is neatly placed in the upper left
corner of the table.
The background wall is painted a subtle beige-white, complementing
the refined ambiance of the space. The floor below the desk features
elegant pinkish marble tiles, enhancing the room’s sophisticated look.
To the far right of the image, a large window or patio door allows natural
light to pour in, with clear glass that offers a glimpse into the outside
area. This exterior view includes part of a rustic brick wall and a metal
pail, hinting at an adjacent patio. |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 101
---


Collecting dense captions is hard!!!
This image features a screenshot taken from a tablet device. At the top-right corner, the time is displayed as 11:48,
alongside a battery icon indicating 67% power remaining. The device also shows a telephony signal strength of four out of
five bars and roughly three-quarters Wi-Fi connectivity. Additionally, a clock alarm icon is present, as well as an icon
resembling a white rectangle with a blue letter "N" in it, whose specific function is unclear.
The main portion of the screen, approximately 80% of it, is a solid medium blue color devoid of any content. At the bottom of
the screen, there are several folders and icons representing various apps and functionalities:
1. The first folder contains three icons:
- An icon likely for contacts.
- An icon probably for telephone.
- An icon that seems to represent a text messaging app.
2. The second folder houses four apps:
- A Gmail app icon indicated by a red "M" on a white background.
- A YouTube app icon characterized by a red play button.
- A map app icon depicting a map.
- An unidentified app icon represented by a blue folder with its top corner bent down on the right.
3. The third icon is a white oval with six dots, arranged in two rows of three, likely representing an app drawer or menu.
4. The fourth icon resembles a red, yellow, and green shutter with a blue dot in the middle, suggesting it might be for a
camera or photo viewing app.
5. Next to it, there is a silver colored camera icon with a black lens and a blue spot in the center, hinting at a camera
application.
At the very bottom of the screen, there are three navigational icons:
- A left arrow triangle in white at the bottom-left corner.
- A white oval in the center, indicative of a home button.
- A white rectangle on the bottom-right corner, likely for accessing recent apps or multitasking.
Ranjay Krishna Overall, this image captures the hLomee csctreuenr oef a t1ab6let, p-roviding an overview of available functionMalitiaes yan d2 co7nn,ec t2ivit0y 25
status.

[Page contains 1 table(s)]


### Table 1

| Collecting dense captions is hard!!!
This image features a screenshot taken from a tablet device. At the top-right corner, the time is displayed as 11:48,
alongside a battery icon indicating 67% power remaining. The device also shows a telephony signal strength of four out of
five bars and roughly three-quarters Wi-Fi connectivity. Additionally, a clock alarm icon is present, as well as an icon
resembling a white rectangle with a blue letter "N" in it, whose specific function is unclear.
The main portion of the screen, approximately 80% of it, is a solid medium blue color devoid of any content. At the bottom of
the screen, there are several folders and icons representing various apps and functionalities:
1. The first folder contains three icons:
- An icon likely for contacts.
- An icon probably for telephone.
- An icon that seems to represent a text messaging app.
2. The second folder houses four apps:
- A Gmail app icon indicated by a red "M" on a white background.
- A YouTube app icon characterized by a red play button.
- A map app icon depicting a map.
- An unidentified app icon represented by a blue folder with its top corner bent down on the right.
3. The third icon is a white oval with six dots, arranged in two rows of three, likely representing an app drawer or menu.
4. The fourth icon resembles a red, yellow, and green shutter with a blue dot in the middle, suggesting it might be for a
camera or photo viewing app.
5. Next to it, there is a silver colored camera icon with a black lens and a blue spot in the center, hinting at a camera
application.
At the very bottom of the screen, there are three navigational icons:
- A left arrow triangle in white at the bottom-left corner.
- A white oval in the center, indicative of a home button.
- A white rectangle on the bottom-right corner, likely for accessing recent apps or multitasking. |
| Ranjay Krishna Overall, this image captures the hLomee csctreuenr oef a t1ab6let, p-roviding an overview of available functionMalitiaes yan d2 co7nn,ec t2ivit0y 25
status. |


[Page contains 1 image(s)]


---
## Page 102
---


Questions designed to extract meaningful visual information
from annotators
• What is the image at first glance?
• What are the objects and their counts?
• What does the text say?
• What are the positions of the objects?
• What subtle details are noticeable?
• What is in the background?
• What is the style and color?
102
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Questions designed to extract meaningful visual information
from annotators
• What is the image at first glance?
• What are the objects and their counts?
• What does the text say?
• What are the positions of the objects?
• What subtle details are noticeable?
• What is in the background?
• What is the style and color? |
| 102
Ranjay Krishna Lecture 16 - May 27, 2025 |


---
## Page 103
---


People don’t like to type
… but they love to talk
We ask annotators to speak for 60 to 90
seconds about an image
We automatically convert speech into
text for pretraining
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| People don’t like to type
… but they love to talk
We ask annotators to speak for 60 to 90
seconds about an image
We automatically convert speech into
text for pretraining |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


---
## Page 104
---


Start with off-the-self
Large Language Model
& Visual Encoder
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Start with off-the-self
Large Language Model
& Visual Encoder |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


[Page contains 2 image(s)]


---
## Page 105
---


From perception To action
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| From perception To action |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 106
---


Pointing to count, pointing to ground
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Pointing to count, pointing to ground |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


[Page contains 2 image(s)]


---
## Page 107
---


Pointing examples
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Pointing examples |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


[Page contains 6 image(s)]


---
## Page 108
---


Chaining Molmo + SAM 2
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Chaining Molmo + SAM 2 |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


[Page contains 2 image(s)]


---
## Page 109
---


Future: Embodied AI for Navigation & Manipulation
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Future: Embodied AI for Navigation & Manipulation |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 110
---


Demo
molmo.allenai.org
Ranjay Krishna Lecture 16 - May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Demo
molmo.allenai.org |
| Ranjay Krishna Lecture 16 - May 27, 2025 |


---
## Page 111
---


Foundation Models
Language Classification LM + Vision And More! Chaining
ELMo CLIP LLaVA Segment Anything LMs + CLIP
BERT CoCa Flamingo Whisper Visual Programming
GPT GPT-4V Dalle
T5 Gemini Stable Diffusion
Molmo Imagen
Ranjay Krishna Lecture 16 - 111 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Foundation Models
Language Classification LM + Vision And More! Chaining
ELMo CLIP LLaVA Segment Anything LMs + CLIP
BERT CoCa Flamingo Whisper Visual Programming
GPT GPT-4V Dalle
T5 Gemini Stable Diffusion
Molmo Imagen |
| Ranjay Krishna Lecture 16 - 111 May 27, 2025 |


---
## Page 112
---


Segment Anything Model (SAM)
What does it mean to have a segmentation foundation model?
Masking model trained on
dataset of specific number of
objects (80 in COCO)
Model outputs masks of all
objects in that image that is one
of the categories of interest
Images: He et al. Mask R-CNN. 2017
Ranjay Krishna Lecture 16 - 112 May 27, 2025

[Page contains 2 table(s)]


### Table 1

| Segment Anything Model (SAM)
What does it mean to have a segmentation foundation model?
Masking model trained on
dataset of specific number of
objects (80 in COCO)
Model outputs masks of all
objects in that image that is one
of the categories of interest
Images: He et al. Mask R-CNN. 2017 |
| Ranjay Krishna Lecture 16 - 112 May 27, 2025 |


### Table 2

| Images: He et al. Mask R | - | CNN. 2017 |
|  |  |  |


[Page contains 1 image(s)]


---
## Page 113
---


Segment Anything Model (SAM)
What does it mean to have a segmentation foundation model?
Masking model trained on a
dataset of a huge number of
categories
Model outputs mask of any
objects that the user cares
about
Images: Kirillov et al. Segment Anything. 2023.
Ranjay Krishna Lecture 16 - 113 May 27, 2025

[Page contains 2 table(s)]


### Table 1

| Segment Anything Model (SAM)
What does it mean to have a segmentation foundation model?
Masking model trained on a
dataset of a huge number of
categories
Model outputs mask of any
objects that the user cares
about
Images: Kirillov et al. Segment Anything. 2023. |
| Ranjay Krishna Lecture 16 - 113 May 27, 2025 |


### Table 2

| Images: Kirillov et al. Segment Anything. 2023. |
|  |


[Page contains 1 image(s)]


---
## Page 114
---


Segment Anything Model (SAM)
What does it mean to have a segmentation foundation model?
Masking model trained on a
dataset of a huge number of
categories
How to get this?
Model outputs mask of any
objects that the user cares
about
How to know this?
Images: Kirillov et al. Segment Anything. 2023.
Ranjay Krishna Lecture 16 - 114 May 27, 2025

[Page contains 2 table(s)]


### Table 1

| Segment Anything Model (SAM)
What does it mean to have a segmentation foundation model?
Masking model trained on a
dataset of a huge number of
categories
How to get this?
Model outputs mask of any
objects that the user cares
about
How to know this?
Images: Kirillov et al. Segment Anything. 2023. |
| Ranjay Krishna Lecture 16 - 114 May 27, 2025 |


### Table 2

| Images: Kirillov et al. Segment Anything. 2023. |
|  |


[Page contains 1 image(s)]


---
## Page 115
---


How to know what to mask?
“Cats”
Ranjay Krishna Lecture 16 - 115 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| How to know what to mask?
“Cats” |
| Ranjay Krishna Lecture 16 - 115 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 116
---


Basic SAM Architecture
Images: Kirillov et al. Segment Anything. 2023.
Ranjay Krishna Lecture 16 - 116 May 27, 2025

[Page contains 2 table(s)]


### Table 1

| Basic SAM Architecture
Images: Kirillov et al. Segment Anything. 2023. |
| Ranjay Krishna Lecture 16 - 116 May 27, 2025 |


### Table 2

| Images: Kirillov et al. Segment Anything. 2023. |
|  |


[Page contains 1 image(s)]


---
## Page 117
---


SAM Architecture
Images: Kirillov et al. Segment Anything. 2023.
Ranjay Krishna Lecture 16 - 117 May 27, 2025

[Page contains 2 table(s)]


### Table 1

| SAM Architecture
Images: Kirillov et al. Segment Anything. 2023. |
| Ranjay Krishna Lecture 16 - 117 May 27, 2025 |


### Table 2

| Images: Kirillov et al. Segment Anything. 2023. |
|  |


[Page contains 2 image(s)]


---
## Page 118
---


Ambiguity in correct prompt
Images: Kirillov et al. Segment Anything. 2023.
Ranjay Krishna Lecture 16 - 118 May 27, 2025

[Page contains 2 table(s)]


### Table 1

| Ambiguity in correct prompt
Images: Kirillov et al. Segment Anything. 2023. |
| Ranjay Krishna Lecture 16 - 118 May 27, 2025 |


### Table 2

| Images: Kirillov et al. Segment Anything. 2023. |
|  |


[Page contains 1 image(s)]


---
## Page 119
---


Ambiguity in correct prompt
Images: Kirillov et al. Segment Anything. 2023.
Ranjay Krishna Lecture 16 - 119 May 27, 2025

[Page contains 2 table(s)]


### Table 1

| Ambiguity in correct prompt
Images: Kirillov et al. Segment Anything. 2023. |
| Ranjay Krishna Lecture 16 - 119 May 27, 2025 |


### Table 2

| Images: Kirillov et al. Segment Anything. 2023. |
|  |


[Page contains 4 image(s)]


---
## Page 120
---


SAM Architecture
Images: Kirillov et al. Segment Anything. 2023.
Ranjay Krishna Lecture 16 - 120 May 27, 2025

[Page contains 2 table(s)]


### Table 1

| SAM Architecture
Images: Kirillov et al. Segment Anything. 2023. |
| Ranjay Krishna Lecture 16 - 120 May 27, 2025 |


### Table 2

| Images: Kirillov et al. Segment Anything. 2023. |
|  |


[Page contains 2 image(s)]


---
## Page 121
---


Basic SAM Architecture
1. Loss only calculated with respect to best mask
2. Model also trained to output confidence score for each mask
Images: Kirillov et al. Segment Anything. 2023.
Ranjay Krishna Lecture 16 - 121 May 27, 2025

[Page contains 2 table(s)]


### Table 1

| Basic SAM Architecture
1. Loss only calculated with respect to best mask
2. Model also trained to output confidence score for each mask
Images: Kirillov et al. Segment Anything. 2023. |
| Ranjay Krishna Lecture 16 - 121 May 27, 2025 |


### Table 2

| Images: Kirillov et al. Segment Anything. 2023. |
|  |


[Page contains 1 image(s)]


---
## Page 122
---


Segment Anything Model (SAM)
What does it mean to have a segmentation foundation model?
Masking model trained on a
dataset of a huge number of
categories
How to get this?
Model outputs mask of any
objects that the user cares
about
How to know this?
Images: Kirillov et al. Segment Anything. 2023.
Ranjay Krishna Lecture 16 - 122 May 27, 2025

[Page contains 2 table(s)]


### Table 1

| Segment Anything Model (SAM)
What does it mean to have a segmentation foundation model?
Masking model trained on a
dataset of a huge number of
categories
How to get this?
Model outputs mask of any
objects that the user cares
about
How to know this?
Images: Kirillov et al. Segment Anything. 2023. |
| Ranjay Krishna Lecture 16 - 122 May 27, 2025 |


### Table 2

| Images: Kirillov et al. Segment Anything. 2023. |
|  |


[Page contains 1 image(s)]


---
## Page 123
---


Segment Anything Model (SAM)
Image Source: https://segment-anything.com/
Ranjay Krishna Lecture 16 - 123 May 27, 2025

[Page contains 2 table(s)]


### Table 1

| Segment Anything Model (SAM)
Image Source: https://segment-anything.com/ |
| Ranjay Krishna Lecture 16 - 123 May 27, 2025 |


### Table 2

| Image Source: https://segment | - | anything.com/ |


[Page contains 2 image(s)]


---
## Page 124
---


Segment Anything Model (SAM)
Images: Kirillov et al. Segment Anything. 2023.
Ranjay Krishna Lecture 16 - 124 May 27, 2025

[Page contains 2 table(s)]


### Table 1

| Segment Anything Model (SAM)
Images: Kirillov et al. Segment Anything. 2023. |
| Ranjay Krishna Lecture 16 - 124 May 27, 2025 |


### Table 2

| Images: Kirillov et al. Segment Anything. 2023. |
|  |


[Page contains 1 image(s)]


---
## Page 125
---


SAM Results
Image Source: Kirillov et al. Segment Anything. 2023
Ranjay Krishna Lecture 16 - 128 May 27, 2025

[Page contains 2 table(s)]


### Table 1

| SAM Results
Image Source: Kirillov et al. Segment Anything. 2023 |
| Ranjay Krishna Lecture 16 - 128 May 27, 2025 |


### Table 2

| Image Source: | Kirillov et al. Segment Anything. 2023 |


[Page contains 1 image(s)]


---
## Page 126
---


SAM Results
Image Source: Kirillov et al. Segment Anything. 2023
Ranjay Krishna Lecture 16 - 129 May 27, 2025

[Page contains 2 table(s)]


### Table 1

| SAM Results
Image Source: Kirillov et al. Segment Anything. 2023 |
| Ranjay Krishna Lecture 16 - 129 May 27, 2025 |


### Table 2

| Image Source: | Kirillov et al. Segment Anything. 2023 |


[Page contains 1 image(s)]


---
## Page 127
---


Zero-Shot with SAM
Image Source: https://segment-anything.com/
Ranjay Krishna Lecture 16 - 130 May 27, 2025

[Page contains 2 table(s)]


### Table 1

| Zero-Shot with SAM
Image Source: https://segment-anything.com/ |
| Ranjay Krishna Lecture 16 - 130 May 27, 2025 |


### Table 2

| Image Source: https://segment | - | anything.com/ |


[Page contains 2 image(s)]


---
## Page 128
---


Zero-Shot with SAM
Image Source: https://segment-anything.com/
Ranjay Krishna Lecture 16 - 131 May 27, 2025

[Page contains 2 table(s)]


### Table 1

| Zero-Shot with SAM
Image Source: https://segment-anything.com/ |
| Ranjay Krishna Lecture 16 - 131 May 27, 2025 |


### Table 2

| Image Source: https://segment | - | anything.com/ |


[Page contains 2 image(s)]


---
## Page 129
---


Foundation Models
Language Classification LM + Vision And More! Chaining
ELMo CLIP LLaVA Segment Anything LMs + CLIP
BERT CoCa Flamingo Whisper Visual Programming
GPT GPT-4V Dalle
T5 Gemini Stable Diffusion
Molmo Imagen
Ranjay Krishna Lecture 16 - 132 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Foundation Models
Language Classification LM + Vision And More! Chaining
ELMo CLIP LLaVA Segment Anything LMs + CLIP
BERT CoCa Flamingo Whisper Visual Programming
GPT GPT-4V Dalle
T5 Gemini Stable Diffusion
Molmo Imagen |
| Ranjay Krishna Lecture 16 - 132 May 27, 2025 |


---
## Page 130
---


What happens when a model is asked to classify
a concept it has never seen?
A photo of a marimba
A photo of a viaduct
A photo of a papillon
A photo of a lorikeet
Pratt et al “What does a platypus look like? Generating customized prompts for zero-shot image classification”. 2023.
Ranjay Krishna Lecture 16 - 133 May 27, 2025
”

[Page contains 2 table(s)]


### Table 1

| What happens when a model is asked to classify
a concept it has never seen?
A photo of a marimba
A photo of a viaduct
A photo of a papillon
A photo of a lorikeet
Pratt et al “What does a platypus look like? Generating customized prompts for zero-shot image classification”. 2023. |
| Ranjay Krishna Lecture 16 - 133 May 27, 2025
” |


### Table 2

| What does a platypus look like? Generating customized prompts for zero | - | shot image classification”. 2023. |


[Page contains 1 image(s)]


---
## Page 131
---


Solution: chaining
1. Get an LLM to generate a description.
2. Classify using the description
Pratt et al “What does a platypus look like? Generating customized prompts for zero-shot image classification”. 2023.
Ranjay Krishna Lecture 16 - 134 May 27, 2025
”

[Page contains 2 table(s)]


### Table 1

| Solution: chaining
1. Get an LLM to generate a description.
2. Classify using the description
Pratt et al “What does a platypus look like? Generating customized prompts for zero-shot image classification”. 2023. |
| Ranjay Krishna Lecture 16 - 134 May 27, 2025
” |


### Table 2

| What does a platypus look like? Generating customized prompts for zero | - | shot image classification”. 2023. |


[Page contains 3 image(s)]


---
## Page 132
---


CuPL (CUstomized Prompts via Language models)
Pratt et al “What does a platypus look like? Generating customized prompts for zero-shot image classification”. 2023.
Ranjay Krishna Lecture 16 - 135 May 27, 2025
”

[Page contains 2 table(s)]


### Table 1

| CuPL (CUstomized Prompts via Language models)
Pratt et al “What does a platypus look like? Generating customized prompts for zero-shot image classification”. 2023. |
| Ranjay Krishna Lecture 16 - 135 May 27, 2025
” |


### Table 2

| What does a platypus look like? Generating customized prompts for zero | - | shot image classification”. 2023. |


[Page contains 1 image(s)]


---
## Page 133
---


CuPL (CUstomized Prompts via Language models)
Pratt et al “What does a platypus look like? Generating customized prompts for zero-shot image classification”. 2023.
Ranjay Krishna Lecture 16 - 136 May 27, 2025
”

[Page contains 2 table(s)]


### Table 1

| CuPL (CUstomized Prompts via Language models)
Pratt et al “What does a platypus look like? Generating customized prompts for zero-shot image classification”. 2023. |
| Ranjay Krishna Lecture 16 - 136 May 27, 2025
” |


### Table 2

| What does a platypus look like? Generating customized prompts for zero | - | shot image classification”. 2023. |


[Page contains 1 image(s)]


---
## Page 134
---


Can we generalize the idea of chaining to all
vision tasks?
Many Visual Question
Answering models which
have been trained to do
this type of task
Are there 3 people in the boat?
Gupta et al “Visual Programming: Compositional visual reasoning without training”. 2023.
Ranjay Krishna Lecture 16 - 137 May 27, 2025
”

[Page contains 1 table(s)]


### Table 1

| Can we generalize the idea of chaining to all
vision tasks?
Many Visual Question
Answering models which
have been trained to do
this type of task
Are there 3 people in the boat?
Gupta et al “Visual Programming: Compositional visual reasoning without training”. 2023. |
| Ranjay Krishna Lecture 16 - 137 May 27, 2025
” |


[Page contains 1 image(s)]


---
## Page 135
---


VisProg (visual programming)
Gupta et al “Visual Programming: Compositional visual reasoning without training”. 2023.
Ranjay Krishna Lecture 16 - 138 May 27, 2025
”

[Page contains 1 table(s)]


### Table 1

| VisProg (visual programming)
Gupta et al “Visual Programming: Compositional visual reasoning without training”. 2023. |
| Ranjay Krishna Lecture 16 - 138 May 27, 2025
” |


[Page contains 1 image(s)]


---
## Page 136
---


VisProg (visual programming)
Train a new model for
Write a python script with the
your task
models you have
output
Class MyMultiImageVQA():
Multi-image
Def ProcessIms():
VQA model
Ans1 = VQA(Image1)
Ans2 = VQA(Image2)
Return Ans1 + Ans2
General to 2 images now, but not beyond that
Gupta et al “Visual Programming: Compositional visual reasoning without training”. 2023.
Ranjay Krishna Lecture 16 - 139 May 27, 2025
”

[Page contains 1 table(s)]


### Table 1

| VisProg (visual programming)
Train a new model for
Write a python script with the
your task
models you have
output
Class MyMultiImageVQA():
Multi-image
Def ProcessIms():
VQA model
Ans1 = VQA(Image1)
Ans2 = VQA(Image2)
Return Ans1 + Ans2
General to 2 images now, but not beyond that
Gupta et al “Visual Programming: Compositional visual reasoning without training”. 2023. |
| Ranjay Krishna Lecture 16 - 139 May 27, 2025
” |


[Page contains 1 image(s)]


---
## Page 137
---


VisProg (visual programming)
Class MyMultiImageVQA():
GPT
Def ProcessIms():
False
Ans1 = VQA(Image1)
Ans2 = VQA(Image2)
Return Ans1 + Ans2
Gupta et al “Visual Programming: Compositional visual reasoning without training”. 2023.
Ranjay Krishna Lecture 16 - 140 May 27, 2025
”

[Page contains 1 table(s)]


### Table 1

| VisProg (visual programming)
Class MyMultiImageVQA():
GPT
Def ProcessIms():
False
Ans1 = VQA(Image1)
Ans2 = VQA(Image2)
Return Ans1 + Ans2
Gupta et al “Visual Programming: Compositional visual reasoning without training”. 2023. |
| Ranjay Krishna Lecture 16 - 140 May 27, 2025
” |


[Page contains 1 image(s)]


---
## Page 138
---


VisProg (visual programming)
Gupta et al “Visual Programming: Compositional visual reasoning without training”. 2023.
Ranjay Krishna Lecture 16 - 141 May 27, 2025
”

[Page contains 1 table(s)]


### Table 1

| VisProg (visual programming)
Gupta et al “Visual Programming: Compositional visual reasoning without training”. 2023. |
| Ranjay Krishna Lecture 16 - 141 May 27, 2025
” |


[Page contains 1 image(s)]


---
## Page 139
---


VisProg (visual programming)
Gupta et al “Visual Programming: Compositional visual reasoning without training”. 2023.
Ranjay Krishna Lecture 16 - 142 May 27, 2025
”

[Page contains 1 table(s)]


### Table 1

| VisProg (visual programming)
Gupta et al “Visual Programming: Compositional visual reasoning without training”. 2023. |
| Ranjay Krishna Lecture 16 - 142 May 27, 2025
” |


[Page contains 1 image(s)]


---
## Page 140
---


VisProg (visual programming)
Gupta et al “Visual Programming: Compositional visual reasoning without training”. 2023.
Ranjay Krishna Lecture 16 - 143 May 27, 2025
”

[Page contains 1 table(s)]


### Table 1

| VisProg (visual programming)
Gupta et al “Visual Programming: Compositional visual reasoning without training”. 2023. |
| Ranjay Krishna Lecture 16 - 143 May 27, 2025
” |


[Page contains 1 image(s)]


---
## Page 141
---


VisProg (visual programming)
Gupta et al “Visual Programming: Compositional visual reasoning without training”. 2023.
Ranjay Krishna Lecture 16 - 144 May 27, 2025
”

[Page contains 1 table(s)]


### Table 1

| VisProg (visual programming)
Gupta et al “Visual Programming: Compositional visual reasoning without training”. 2023. |
| Ranjay Krishna Lecture 16 - 144 May 27, 2025
” |


[Page contains 1 image(s)]


---
## Page 142
---


VisProg (visual programming)
Gupta et al “Visual Programming: Compositional visual reasoning without training”. 2023.
Ranjay Krishna Lecture 16 - 145 May 27, 2025
”

[Page contains 1 table(s)]


### Table 1

| VisProg (visual programming)
Gupta et al “Visual Programming: Compositional visual reasoning without training”. 2023. |
| Ranjay Krishna Lecture 16 - 145 May 27, 2025
” |


[Page contains 1 image(s)]


---
## Page 143
---


Summary
Task Task
1 3
Large Scale
Foundation
Diverse
Model
Dataset Task Task
2 4
Ranjay Krishna Lecture 16 - 146 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Summary
Task Task
1 3
Large Scale
Foundation
Diverse
Model
Dataset Task Task
2 4 |
| Ranjay Krishna Lecture 16 - 146 May 27, 2025 |


---
## Page 144
---


Summary
Ranjay Krishna Lecture 16 - 147 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Summary |
| Ranjay Krishna Lecture 16 - 147 May 27, 2025 |


[Page contains 2 image(s)]


---
## Page 145
---


Summary
Ranjay Krishna Lecture 16 - 148 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Summary |
| Ranjay Krishna Lecture 16 - 148 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 146
---


Summary
Ranjay Krishna Lecture 16 - 149 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Summary |
| Ranjay Krishna Lecture 16 - 149 May 27, 2025 |


[Page contains 1 image(s)]


---
## Page 147
---


Summary
Ranjay Krishna Lecture 16 - 150 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Summary |
| Ranjay Krishna Lecture 16 - 150 May 27, 2025 |


[Page contains 2 image(s)]


---
## Page 148
---


Next time: Robot Learning
Ranjay Krishna Lecture 16 - 151 May 27, 2025

[Page contains 1 table(s)]


### Table 1

| Next time: Robot Learning |
| Ranjay Krishna Lecture 16 - 151 May 27, 2025 |
