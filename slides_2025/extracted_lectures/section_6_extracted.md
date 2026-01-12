# section_6

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
SOLUTION:
Note that we have two 2-dimensional tokens as input. W , W and W transforms them into 1-
k q v
dimensional vectors and attention is carried out in that 1-dimensional space. Because of that, the
√
scaling 1/ d with d = 1 won’t have any effect on alignment scores. However, we also gave full credit
√
to answers with 1/ 2 scaling.
√
(cid:20) (cid:21) (cid:20) (cid:21) (cid:20) (cid:21)
−1 2 0.3
We calculate k =XW = , q =XW = √ , and v =XW =
k 1 q − 2 v 0.4
√ √
(cid:20) (cid:21) (cid:20) (cid:21)
− 2 2 0.056 0.944
Alignment, e = kqT = √ √ . Taking softmax, we get attention a = =
2 − 2 0.944 0.056
(cid:20) (cid:21) (cid:20) (cid:21) (cid:20) (cid:21)
h 1−h 0.3944 0.3h+0.4(1−h)
where h= 1 √ . Finally, output y =aTv = = .
1−h h 1+exp(2 2) 0.3056 0.3(1−h)+0.4h
√
We also awarded full credit for answers which (wrongly) scales e with 1/ 2. In that case, alignment
(cid:20) (cid:21) (cid:20) (cid:21) (cid:20) (cid:21)
−1 1 0.12 0.88 h 1−h
e= . Attention a= = where h= 1 . Output y =aTv =
1 −1 0.88 0.12 1−h h 1+exp(2)
(cid:20) (cid:21) (cid:20) (cid:21)
0.388 0.3h+0.4(1−h)
= .
0.312 0.3(1−h)+0.4h
.
(cid:20) (cid:21)
−1 1
2. (4 points) How would you compute the output sequence for input X = , given the answer to
0 1
the above problem?
SOLUTION:
Here, the input tokens have been swapped. Since self-attention is position equivariant, we only need
to swap the positions of the output of previous answer.
(cid:20) (cid:21)
−1 0
3. (4points)NowconsiderincorporatingapositionalencodingwithvaluesP = forthefirsttwo
1 0
positions. Assuming we add the positional encoding to the input, what is the output sequence for the
input from part (a) and the same key weights, query weights, and value weights?
SOLUTION:
(cid:20) (cid:21)
−1 1
Since we add positional encoding, input to the self-attention layer will be X +P = which is
0 1
exactly same as the input in previous question and so is the answer.
4. (3 points) Does your answer to part (b) change in the case of a positional encoding? Explain why or
why not.
1

---
## Page 2
---


SOLUTION:
Yes, adding a positional encoding makes the attention layer variant to ordering.
2

---
## Page 3
---


0.2 Funky 1D ConvNet Backpropagation (16 points)
Consider the following 1-dimensional convolutional neural network, where all variables are scalars:
Figure 1: Computation graph of a 1D ConvNet.
1. (2 point) List the parameters in this network.
SOLUTION:
k ,k ,k ,b,w ,w ,c. One common mistake is that students assumed that the bias term c is a fixed
1 2 3 1 2
constantandthereforedidnotlistitasaparameter. Itisnotstatedintheproblemthatcisaconstant.
3

[Page contains 1 image(s)]


---
## Page 4
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
SOLUTION:
∂L
=−(y−yˆ)ez4
∂z
4
∂L
=−(y−yˆ)ez4w
∂v 1
1
∂L
=−(y−yˆ)ez4w
∂v 2
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
4

---
## Page 5
---


SOLUTION:
∂L
=δ ∗1{z >z }
∂z 1 1 2
1
∂L
=δ ∗1{z >z }+δ ∗1{z >z }
∂z 1 2 1 2 2 3
2
∂L
=δ ∗1{z >z }
∂z 2 3 2
3
Common Errors: For a piece-wise definition of ∂L, an error on one of the four possible cases for
∂z2
the value of z in relation to z and z (ie. missing or incorrect on one of z > z ,z , z > z > z ,
2 1 3 2 1 3 1 2 3
z > z > z , z ,z > z ). Another common error was adding unnecessary constraints z > 0 to the
3 2 1 1 3 2 i
indicator functions.
4. (4 points) Given the gradients of the loss L with respect to z , z , z , derive the gradients of the loss
1 2 3
with respect to k , k , k , and b. More precisely, given
1 2 3
∂L ∂L ∂L
=δ =δ =δ ,
∂z 1 ∂z 2 ∂z 3
1 2 3
determine the following:
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
SOLUTION:
5

---
## Page 6
---


∂L
=δ x +δ x +δ x
∂k 1 1 2 2 3 3
1
∂L
=δ x +δ x +δ x
∂k 1 2 2 3 3 4
2
∂L
=δ x +δ x +δ x
∂k 1 3 2 4 3 5
3
∂L
=δ +δ +δ
∂b 1 2 3
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
SOLUTION:
6

---
## Page 7
---


z =6
4
∂L
=5
∂z
1
∂L
=1
∂z
2
∂L
=0
∂z
3
7