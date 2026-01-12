# section_6_sol

Extracted using pdfplumber



---
## Page 1
---


0.1 Calculating Output of Attention Layers (15 points)
(cid:20) (cid:21)
0 1
1. (4points)Consideraself-attentionlayeronaninputsequenceoftworowvectorsX = . Given
−1 1
a key weight matrix W , query weight matrix W and value weight matrix W :
k q v
√
(cid:20) (cid:21) (cid:20) (cid:21) (cid:20) (cid:21)
−2 2 2 −0.1
W = ,W = √ ,W = ,
k −1 q 2 v 0.3
find the output sequence.
1

---
## Page 2
---


.
(cid:20) (cid:21)
−1 1
2. (4 points) How would you compute the output sequence for input X = , given the answer to
0 1
the above problem?
2

---
## Page 3
---


(cid:20) (cid:21)
−1 0
3. (4points)NowconsiderincorporatingapositionalencodingwithvaluesP = forthefirsttwo
1 0
positions. Assuming we add the positional encoding to the input, what is the output sequence for the
input from part (a) and the same key weights, query weights, and value weights?
3

---
## Page 4
---


4. (3 points) Does your answer to part (b) change in the case of a positional encoding? Explain why or
why not.
4

---
## Page 5
---


0.2 Funky 1D ConvNet Backpropagation (16 points)
Consider the following 1-dimensional convolutional neural network, where all variables are scalars:
Figure 1: Computation graph of a 1D ConvNet.
1. (2 point) List the parameters in this network.
5

[Page contains 1 image(s)]


---
## Page 6
---


2. (3 points) Determine the following:
∂L
=
∂z
4
∂L
=
∂v
1
∂L
=
∂v
2
3. (3 points) Given the gradients of the loss L with respect to u and u , derive the gradients of the loss
1 2
with respect to z , z , and z . More precisely, given
1 2 3
∂L ∂L
=δ =δ ,
∂u 1 ∂u 2
1 2
determine the following:
∂L
=
∂z
1
∂L
=
∂z
2
∂L
=
∂z
3
4. (4 points) Given the gradients of the loss L with respect to z , z , z , derive the gradients of the loss
1 2 3
with respect to k , k , k , and b. More precisely, given
1 2 3
∂L ∂L ∂L
=δ =δ =δ ,
∂z 1 ∂z 2 ∂z 3
1 2 3
determine the following:
6

---
## Page 7
---


∂L
=
∂k
1
∂L
=
∂k
2
∂L
=
∂k
3
∂L
=
∂b
5. (4 points) Suppose that we know the exact numeric values of some intermediate variables/derivatives
in the computation graph:
∂L
z =1 z =−2 z =−3 w =5 w =10 c=3 =1.
1 2 3 1 2 ∂z
4
Given these values, what are the numeric values of z , ∂L, ∂L, ∂L?
4 ∂z1 ∂z2 ∂z3
(Your answers should be numbers rather than expressions containing variables).
z =
4
∂L
=
∂z
1
∂L
=
∂z
2
∂L
=
∂z
3
7