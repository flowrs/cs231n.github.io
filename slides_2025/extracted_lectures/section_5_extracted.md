# section_5

Extracted using pdfplumber



---
## Page 1
---


CS231N Review Session:
RNNs and Transformers
Emily Jin
May 2nd, 2025

---
## Page 2
---


Agenda
- Motivation
- RNNs
- Transformers
- RNNs vs Transformers
- Colab Notebook

---
## Page 3
---


Motivation
Before RNNs and Transformers, we assume fixed-size inputs and outputs.
But many vision tasks require sequential processing.

---
## Page 4
---


Motivation
Example: Image Captioning (one to many)
A dog is standing
Model
on the beach.

[Page contains 1 image(s)]


---
## Page 5
---


Motivation
Example: Activity Recognition (many to one)
Model Dancing

[Page contains 1 image(s)]


---
## Page 6
---


Motivation
Example: Video Captioning (many to many)
A man and woman
Model
are dancing.

[Page contains 1 image(s)]


---
## Page 7
---


Motivation
To solve these kinds of tasks, we need models that can:
● Handle variable-length input and output sequences
● Preserve temporal structure and order
● Capture long-range dependencies
Some considerations include:
● Long-Range Dependencies: How do models learn which past inputs are relevant?
● Parallelizability: Can the model be parallelized across time steps?
● Compute & Memory Use: How do compute/memory scale with sequence length?
● Inductive Bias: How well do models capture temporal/locality structure?

---
## Page 8
---


RNNs
Key Idea: RNNs process sequences one step at a time, maintaining a “internal state”
that summarizes past inputs & is updated as the sequence is processed

[Page contains 1 table(s)]


### Table 1

|  |
|  |


[Page contains 1 image(s)]


---
## Page 9
---


RNNs
At every time step, we use the same function / parameters to update the hidden state,
which allows us to process input sequences of arbitrary length.
We use another function / parameters to decode the hidden state into an output, to
generate output sequences.

[Page contains 1 table(s)]


### Table 1

|  |
|  |


[Page contains 2 image(s)]


---
## Page 10
---


RNNs
(Truncated) Backpropagation Through Time
Key Idea: Instead of backpropping through the entire sequence, we carry hidden states
forward in time forever, but only backpropagate for a chunk

[Page contains 1 table(s)]


### Table 1

|  |
|  |


[Page contains 1 image(s)]


---
## Page 11
---


RNNs
Advantages
● Can process inputs of any length
● Each step can use information from previous steps (in theory)
● Model size is fixed, regardless of sequence length
● Shared weights across time → enforces temporal consistency
Disadvantages
● Slow training due to sequential / recurrent computation
● Hard to capture long-term dependencies
● Vanishing/exploding gradients
● Gradient clipping (clip norm of gradient to a threshold)
● LSTM / GRU (gating mechanisms help preserve / regulate flow of info over time)

[Page contains 1 table(s)]


### Table 1

| Advantages
● Can process inputs of any length
● Each step can use information from previous steps (in theory)
● Model size is fixed, regardless of sequence length
● Shared weights across time → enforces temporal consistency
Disadvantages
● Slow training due to sequential / recurrent computation
● Hard to capture long-term dependencies
● Vanishing/exploding gradients
● Gradient clipping (clip norm of gradient to a threshold)
● LSTM / GRU (gating mechanisms help preserve / regulate flow of info over time) |
|  |


---
## Page 12
---


Transformers
Key Idea: use self-attention to process all elements in parallel and let the model attend
to most relevant parts of the input
Add + Norm
MLP
Add + Norm
Self-Attention
Vaswani et al, “Attention is All You Need” NeurIPS 2017

[Page contains 2 table(s)]


### Table 1

|  |
|  |


### Table 2

| Add + Norm |
| Self-Attention |


[Page contains 1 image(s)]


---
## Page 13
---


Transformers
Self-Attention
Input Vectors: X
Queries: Q – what each token is looking for
Keys: K – what each token offers
Values: V – information of each token
Compute attention scores by computing dot product between
each query and the keys of all tokens + passing through softmax
Attention scores determine how much each token should pay
attention to other tokensʼ values
Final Output: weighted sum of all values, based on attention

[Page contains 1 image(s)]


---
## Page 14
---


RNNs vs Transformers
RNNs Transformers
Long-Range Good in theory, but hard in Good in practice, through
Dependencies practice self-attention over full input
Parallelizability No – sequential computation Yes – process tokens in
across timesteps parallel
Compute & Memory O(N), O(N) O(N^2), O(N)
Use
Inductive Bias Strong – inherent temporal Weak – needs to learn from
structure data

[Page contains 1 table(s)]


### Table 1

|  | RNNs | Transformers |
| Long-Range
Dependencies | Good in theory, but hard in
practice | Good in practice, through
self-attention over full input |
| Parallelizability | No – sequential computation
across timesteps | Yes – process tokens in
parallel |
| Compute & Memory
Use | O(N), O(N) | O(N^2), O(N) |
| Inductive Bias | Strong – inherent temporal
structure | Weak – needs to learn from
data |


---
## Page 15
---


Vision Transformers
Key Idea: treat images like sequences of patches, and apply the Transformer directly to
those patches, using self-attention to model relationships between parts of the image.
Dosovitskiy et al, “An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale”, ICLR 2021

[Page contains 1 table(s)]


### Table 1

|  |  |
|  |  |
|  |  |


[Page contains 2 image(s)]


---
## Page 16
---


Colab Notebook
https://colab.research.google.com/drive/1mC5CWwekbZ2NrYv6Zfpuv55z8DuOZXVP?us
p=sharing