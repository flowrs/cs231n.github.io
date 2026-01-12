# section_2

Extracted using pdfplumber



---
## Page 1
---


An Exercise in Backpropagation
Matthew Jin
Spring 2025

---
## Page 2
---


What, when, and why backpropagation?
What: Backpropagation is one method of calculating gradients of the
output of a chain of operations with respect to each
component in the chain.
When: Used in anything and everything neural networks related.
Why: Because some very smart people have built systems that allow
computers to automatically compute gradients via
backpropagation.

---
## Page 3
---


Definitions
We’ll be exploring a simple neural network for the binary (0 or 1)
classification problem.
▶
Data: (X,y) are the dataset and corresponding labels
▶ X∈RN×2,y∈{0,1}N
▶ Model: f (x) : R2 → [0,1] (probability x is in class 1)
θ
▶
θ represents all the parameters we want to optimize!
▶
Activation functions: ReLU (x ), Sigmoid (σ(x))
+
▶
x =max(0,x)
+
▶ σ(x)= 1
1+e−x
▶
Binary Cross Entropy Loss:
▶
ℓ(p,y)=−(y ·logp +(1−y)·log(1−p))
i i i i i i i
▶ ℓ(p,y)= 1 (cid:80)N ℓ(p,y)
N i=1 i i i

---
## Page 4
---


The Network
b
h3
+
x2
h2 z ypred
+
x1
h1
+
f (x)=σ(max(0,xw )w +b)
θ 1 2
(cid:124) (cid:123)(cid:122) (cid:125)
z
We want to optimize the network’s parameters θ which consist of
w ∈ R2×3, w ∈ R3×1, and b ∈ R1.
1 2

---
## Page 5
---


Gradient Calculations
f (x)=σ(max(0,xw )w +b)
θ 1 2
(cid:124) (cid:123)(cid:122) (cid:125)
z
We want to calculate the gradient of the binary cross entropy loss
applied to the output of the network
N
1 (cid:88)
ℓ(f (X),y) = ℓ (f (x ),y )
θ i θ i i
N
(cid:124)(cid:123)(cid:122)(cid:125)
y i=1
pred
N
1 (cid:88)
= −(y ·logf (x )+(1−y )·log(1−f (x )))
i θ i i θ i
N
i=1
with respect to w , w , and b.
1 2

---
## Page 6
---


Gradient Calculations
f (x)=σ(max(0,xw )w +b)
θ 1 2
(cid:124) (cid:123)(cid:122) (cid:125)
z
From the chain rule, we have
∂ℓ(·) ∂ℓ(·)∂y ∂z
pred
=
∂w ∂y ∂z ∂w
2 pred 2
∂ℓ(·) ∂ℓ(·)∂y ∂z
pred
=
∂b ∂y ∂z ∂b
pred
∂ℓ(·) ∂ℓ(·)∂y ∂z ∂h ∂xw
pred 1
=
∂w ∂y ∂z ∂h∂xw ∂w
1 pred 1 1
where h = max(0,xw ).
1

---
## Page 7
---


h
Gradient Calculations (cid:122) (cid:125)(cid:124) (cid:123)
f (x)=σ(max(0,xw )w +b)
θ 1 2
(cid:124) (cid:123)(cid:122) (cid:125)
z
Note that ℓ(f (X),y) is a scalar value while z ∈ RN, so how is the
θ
gradient calculated?
∂ℓ(·) (cid:104) (cid:105)⊤
∂ℓ(·) ∂ℓ(·)
= ···
∂y ∂y pred1 ∂y predn
pred
What about the derivative of y with respect to z? Both are
pred
vectors of size N. Since y = σ(z) is an element-wise operation,
pred
∂y
pred
= σ(z)·(1−σ(z)) = y ·(1−y )
pred pred
∂z

---
## Page 8
---


h
Gradient Calculations (cid:122) (cid:125)(cid:124) (cid:123)
f (x)=σ(max(0,xw )w +b)
θ 1 2
(cid:124) (cid:123)(cid:122) (cid:125)
z
Next, we want to calculate ∂z. Here z ∈ RN and h ∈ RN×3.
∂h
We have z = hw +b which looks something like
2
   
z 1 h 11 h 12 h 13  w 2,1 
. . . .
  . .   =   . . . . . .   w 2,2
z N h N1 h N2 h N3 w 2,3
Since z = h w +h w +h w , the gradient of z w.r.t.
i i1 2,1 i2 2,2 i3 2,3
each row of h is w⊤.
2
On the other hand, the gradient of z w.r.t. w depends on
2j
h ,...,h .
1j Nj

---
## Page 9
---


h
Gradient Calculations (cid:122) (cid:125)(cid:124) (cid:123)
f (x)=σ(max(0,xw )w +b)
θ 1 2
(cid:124) (cid:123)(cid:122) (cid:125)
z
What about the gradient for the bias b?
b is automatically broadcasted in the equation but can be written
as z = hw +1⊤b where 1 ∈ RN. Thus, the gradient is
2
∂z
= 1⊤
∂b

---
## Page 10
---


h
Gradient Calculations (cid:122) (cid:125)(cid:124) (cid:123)
f (x)=σ(max(0,xw )w +b)
θ 1 2
(cid:124) (cid:123)(cid:122) (cid:125)
z
To calculate the gradient of w , we need ∂h and ∂xw1.
1 ∂xw ∂w
1 1
For ∂h , we have
∂xw
1
(cid:40)
∂ max(0,xw ) 1 if (xw ) > 0
1 ij 1 ij
=
∂xw 0 otherwise
1
For ∂xw1, we have
∂w
1
    
h h h x x
11 12 13 11 12 (cid:20) (cid:21)
  . . . . . . . . .   =     . . . . . .   w w 1,11 w w 1,12 w w 1,13  
1,21 1,22 1,23
h h h x x
N1 N2 N3 N1 N2 +
Similar to w , the gradient for each column of w depends on x.
2 1

---
## Page 11
---


Additional Resources
▶
CS231N page on backpropagation
▶
Justin Johnson’s notes on matrix gradient calculations
▶
Erik Learned-Miller’s notes on vector/matrix/tensor
derivatives
▶
The Matrix Cookbook
▶
Gregory Gundersen’s notes on the reparameterization trick

---
## Page 12
---


Appendix
Batched Linear Gradients
Consider the equation Y = XW where Y ∈ RN×Dy, X ∈ RN×Dx,
and W ∈ RDx×Dy. On the forward pass, the matrix multiplication
can be rewritten as
(cid:88)
Dx
Y = X W
ij ik kj
k=1
Given this formula, how do we calculate the gradients ∂Y and
∂W
∂Y? What if we add a loss function ℓ(Y) : RN×Dy → R? How do
∂X
∂ℓ(Y) ∂ℓ(Y)
we calculate and ?
∂W ∂X

---
## Page 13
---


Appendix
Batched Linear Gradients Y =
(cid:80)Dx
X W
ij k=1 ik kj
First, let us focus on the gradient with respect to one element in
the weight matrix ∂Y which should have the same shape as
∂W
kj
Y ∈ RN×Dy.
 
0 ··· ∂Y1j ··· 0  
∂ ∂ W Y =    . . . ... ∂W . . . kj ... . . .    =   0 . . . · .. · . · X . . . 1k · .. · . · 0 . . .  
kj  0 ··· ∂Y Nj ··· 0  0 ··· X Nk ··· 0
∂W
kj

---
## Page 14
---


Appendix
Batched Linear Gradients Y =
(cid:80)Dx
X W
ij k=1 ik kj
Thelossgradient ∂ℓ(Y) alsohasshapeRN×Dy sinceℓ(Y)isascalarandcanbe
∂Y
written as
∂ℓ(Y)
···
∂ℓ(Y)
∂Y ∂Y
∂
∂
ℓ(
Y
Y) =  

. .
.
11
... . .
.
1Dy
 

 
∂ℓ(Y) ··· ∂ℓ(Y)
∂Y ∂Y
N1 NDy
For a specific W , we have
kj
∂ℓ(Y) = (cid:88)∂ℓ(Y) · ∂Y ij = (cid:88) N X · ∂ℓ(Y) = (cid:18) X⊤ ∂ℓ(Y) (cid:19)
∂W ∂Y ∂W ik ∂Y ∂Y
kj ij ij kj i=1 ij kj
Thus, ∂ℓ(Y) =X⊤∂ℓ(Y). Intuitively, this makes sense since the gradients of
∂W ∂Y
each weight should be aggregated across the batch of inputs.

---
## Page 15
---


Appendix
Batched Linear Gradients Y =
(cid:80)Dx
X W
ij k=1 ik kj
Similarly, for ∂Y ∈RN×Dy,
∂X
ik
 0 ··· 0   0 ··· 0 
∂ ∂ X Y ik =          ∂ ∂X Y . . . . . . i i k 1 · . . · . . . . · ∂ ∂ Y X . . . . . . iD ik y          =         W . . . . . . k1 · . . · . . . . · W k . . . . . . Dy        
0 ··· 0 0 ··· 0
which gives us
∂ℓ(Y) = (cid:88)∂ℓ(Y) · ∂Y ij = (cid:88)
Dy
W · ∂ℓ(Y) =
(cid:18)
∂ℓ(Y) W⊤
(cid:19)
∂X ∂Y ∂X kj ∂Y ∂Y
ik ij ij ik j=1 ij ik
Thus, ∂ℓ(Y) = ∂ℓ(Y)W⊤. This indicates that the gradient of the k-th
∂X ∂Y
component of a single input X depends on the corresponding row W in the
i k
weight matrix.