# lecture_8

Extracted using pdfplumber



---
## Page 1
---


Lecture 8:
Attention and Transformers
Stanford CS231n 10th Anniversary Lecture 8 - 1 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture 8:
Attention and Transformers |
| Stanford CS231n 10th Anniversary Lecture 8 - 1 April 24, 2025 |


---
## Page 2
---


Administrative
● Assignment 2 released yesterday (4/23)
● Project proposals are due tomorrow (4/25)
Stanford CS231n 10th Anniversary Lecture 8 - 2 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Administrative
● Assignment 2 released yesterday (4/23)
● Project proposals are due tomorrow (4/25) |
| Stanford CS231n 10th Anniversary Lecture 8 - 2 April 24, 2025 |


---
## Page 3
---


Last Time: Recurrent Neural Networks
Stanford CS231n 10th Anniversary Lecture 8 - 3 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Last Time: Recurrent Neural Networks |
| Stanford CS231n 10th Anniversary Lecture 8 - 3 April 24, 2025 |


[Page contains 1 image(s)]


---
## Page 4
---


Today: Attention + Transformers
Attention: A new primitive that Transformer: A neural
operates on sets of vectors network architecture that
uses attention everywhere
Stanford CS231n 10th Anniversary Lecture 8 - 4 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Today: Attention + Transformers
Attention: A new primitive that Transformer: A neural
operates on sets of vectors network architecture that
uses attention everywhere |
| Stanford CS231n 10th Anniversary Lecture 8 - 4 April 24, 2025 |


[Page contains 3 image(s)]


---
## Page 5
---


Today: Attention + Transformers
Attention: A new primitive that Transformer: A neural
operates on sets of vectors network architecture that
uses attention everywhere
Transformers are used
everywhere today!
But they developed as
an offshoot of RNNs
so let’s start there
Stanford CS231n 10th Anniversary Lecture 8 - 5 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Today: Attention + Transformers
Attention: A new primitive that Transformer: A neural
operates on sets of vectors network architecture that
uses attention everywhere
Transformers are used
everywhere today!
But they developed as
an offshoot of RNNs
so let’s start there |
| Stanford CS231n 10th Anniversary Lecture 8 - 5 April 24, 2025 |


[Page contains 3 image(s)]


---
## Page 6
---


Sequence to Sequence with RNNs: Encoder - Decoder
Input: Sequence x , … x A motivating example for today’s discussion –
1 T
machine translation! English → Italian
Output: Sequence y , …, y
1 T’
Encoder: h = f (x , h )
t W t t-1
h h h h
1 2 3 4
x x x x
1 2 3 4
we see the sky
Sutskever et al, “Sequence to sequence learning with neural networks”, NeurIPS 2014
Stanford CS231n 10th Anniversary Lecture 8 - 6 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Sequence to Sequence with RNNs: Encoder - Decoder
Input: Sequence x , … x A motivating example for today’s discussion –
1 T
machine translation! English → Italian
Output: Sequence y , …, y
1 T’
Encoder: h = f (x , h )
t W t t-1
h h h h
1 2 3 4
x x x x
1 2 3 4
we see the sky
Sutskever et al, “Sequence to sequence learning with neural networks”, NeurIPS 2014 |
| Stanford CS231n 10th Anniversary Lecture 8 - 6 April 24, 2025 |


---
## Page 7
---


Sequence to Sequence with RNNs
Input: Sequence x , … x
1 T
Output: Sequence y , …, y
1 T’
From final hidden state predict:
Initial decoder state s
Encoder: h = f (x , h )
0
t W t t-1
Context vector c (often c=h )
T
h h h h s
1 2 3 4 0
x x x x c
1 2 3 4
we see the sky
Sutskever et al, “Sequence to sequence learning with neural networks”, NeurIPS 2014
Stanford CS231n 10th Anniversary Lecture 8 - 7 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Sequence to Sequence with RNNs
Input: Sequence x , … x
1 T
Output: Sequence y , …, y
1 T’
From final hidden state predict:
Initial decoder state s
Encoder: h = f (x , h )
0
t W t t-1
Context vector c (often c=h )
T
h h h h s
1 2 3 4 0
x x x x c
1 2 3 4
we see the sky
Sutskever et al, “Sequence to sequence learning with neural networks”, NeurIPS 2014 |
| Stanford CS231n 10th Anniversary Lecture 8 - 7 April 24, 2025 |


---
## Page 8
---


Sequence to Sequence with RNNs
Decoder: s = g (y , s , c)
Input: Sequence x , … x
t U t-1 t-1
1 T
Output: Sequence y , …, y
1 T’
vediamo
From final hidden state predict:
y
Initial decoder state s 1
Encoder: h = f (x , h )
0
t W t t-1
Context vector c (often c=h )
T
h h h h s s
1 2 3 4 0 1
x x x x c y
1 2 3 4 0
we see the sky [START]
Sutskever et al, “Sequence to sequence learning with neural networks”, NeurIPS 2014
Stanford CS231n 10th Anniversary Lecture 8 - 8 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Sequence to Sequence with RNNs
Decoder: s = g (y , s , c)
Input: Sequence x , … x
t U t-1 t-1
1 T
Output: Sequence y , …, y
1 T’
vediamo
From final hidden state predict:
y
Initial decoder state s 1
Encoder: h = f (x , h )
0
t W t t-1
Context vector c (often c=h )
T
h h h h s s
1 2 3 4 0 1
x x x x c y
1 2 3 4 0
we see the sky [START]
Sutskever et al, “Sequence to sequence learning with neural networks”, NeurIPS 2014 |
| Stanford CS231n 10th Anniversary Lecture 8 - 8 April 24, 2025 |


### Table 2

| s
1 |
|  |


---
## Page 9
---


Sequence to Sequence with RNNs
Decoder: s = g (y , s , c)
Input: Sequence x , … x
t U t-1 t-1
1 T
Output: Sequence y , …, y
1 T’
vediamo il
From final hidden state predict:
y y
Initial decoder state s 1 2
Encoder: h = f (x , h )
0
t W t t-1
Context vector c (often c=h )
T
h h h h s s s
1 2 3 4 0 1 2
x x x x c y y
1 2 3 4 0 1
we see the sky [START] vediamo
Sutskever et al, “Sequence to sequence learning with neural networks”, NeurIPS 2014
Stanford CS231n 10th Anniversary Lecture 8 - 9 April 24, 2025

[Page contains 3 table(s)]


### Table 1

| Sequence to Sequence with RNNs
Decoder: s = g (y , s , c)
Input: Sequence x , … x
t U t-1 t-1
1 T
Output: Sequence y , …, y
1 T’
vediamo il
From final hidden state predict:
y y
Initial decoder state s 1 2
Encoder: h = f (x , h )
0
t W t t-1
Context vector c (often c=h )
T
h h h h s s s
1 2 3 4 0 1 2
x x x x c y y
1 2 3 4 0 1
we see the sky [START] vediamo
Sutskever et al, “Sequence to sequence learning with neural networks”, NeurIPS 2014 |
| Stanford CS231n 10th Anniversary Lecture 8 - 9 April 24, 2025 |


### Table 2

| s
1 |
|  |


### Table 3

| s
2 |
|  |


---
## Page 10
---


Sequence to Sequence with RNNs
Decoder: s = g (y , s , c)
Input: Sequence x , … x
t U t-1 t-1
1 T
Output: Sequence y , …, y
1 T’
vediamo il cielo [STOP]
From final hidden state predict:
y y y y
Initial decoder state s 1 2 3 4
Encoder: h = f (x , h )
0
t W t t-1
Context vector c (often c=h )
T
h h h h s s s s s
1 2 3 4 0 1 2 3 4
x x x x c y y y y
1 2 3 4 0 1 2 3
we see the sky [START] vediamo il cielo
Sutskever et al, “Sequence to sequence learning with neural networks”, NeurIPS 2014
Stanford CS231n 10th Anniversary Lecture 8 - 10 April 24, 2025

[Page contains 4 table(s)]


### Table 1

| Sequence to Sequence with RNNs
Decoder: s = g (y , s , c)
Input: Sequence x , … x
t U t-1 t-1
1 T
Output: Sequence y , …, y
1 T’
vediamo il cielo [STOP]
From final hidden state predict:
y y y y
Initial decoder state s 1 2 3 4
Encoder: h = f (x , h )
0
t W t t-1
Context vector c (often c=h )
T
h h h h s s s s s
1 2 3 4 0 1 2 3 4
x x x x c y y y y
1 2 3 4 0 1 2 3
we see the sky [START] vediamo il cielo
Sutskever et al, “Sequence to sequence learning with neural networks”, NeurIPS 2014 |
| Stanford CS231n 10th Anniversary Lecture 8 - 10 April 24, 2025 |


### Table 2

| s
1 |
|  |


### Table 3

| s
2 |
|  |


### Table 4

| s
3 |
|  |


---
## Page 11
---


Sequence to Sequence with RNNs
Decoder: s = g (y , s , c)
Input: Sequence x , … x
t U t-1 t-1
1 T
Output: Sequence y , …, y
1 T’
vediamo il cielo [STOP]
From final hidden state predict:
y y y y
Initial decoder state s 1 2 3 4
Encoder: h = f (x , h )
0
t W t t-1
Context vector c (often c=h )
T
h h h h s s s s s
1 2 3 4 0 1 2 3 4
x x x x c y y y y
1 2 3 4 0 1 2 3
Problem: Input sequence
we see the sky [START] vediamo il cielo
bottlenecks through fixed
sized c. What if T=1000?
Sutskever et al, “Sequence to sequence learning with neural networks”, NeurIPS 2014
Stanford CS231n 10th Anniversary Lecture 8 - 11 April 24, 2025

[Page contains 4 table(s)]


### Table 1

| Sequence to Sequence with RNNs
Decoder: s = g (y , s , c)
Input: Sequence x , … x
t U t-1 t-1
1 T
Output: Sequence y , …, y
1 T’
vediamo il cielo [STOP]
From final hidden state predict:
y y y y
Initial decoder state s 1 2 3 4
Encoder: h = f (x , h )
0
t W t t-1
Context vector c (often c=h )
T
h h h h s s s s s
1 2 3 4 0 1 2 3 4
x x x x c y y y y
1 2 3 4 0 1 2 3
Problem: Input sequence
we see the sky [START] vediamo il cielo
bottlenecks through fixed
sized c. What if T=1000?
Sutskever et al, “Sequence to sequence learning with neural networks”, NeurIPS 2014 |
| Stanford CS231n 10th Anniversary Lecture 8 - 11 April 24, 2025 |


### Table 2

| s
1 |
|  |


### Table 3

| s
2 |
|  |


### Table 4

| s
3 |
|  |


---
## Page 12
---


Sequence to Sequence with RNNs
Decoder: s = g (y , s , c)
Input: Sequence x , … x
t U t-1 t-1
1 T
Output: Sequence y , …, y
1 T’
vediamo il cielo [STOP]
From final hidden state predict:
y y y y
Initial decoder state s 1 2 3 4
Encoder: h = f (x , h )
0
t W t t-1
Context vector c (often c=h )
T
h h h h s s s s s
1 2 3 4 0 1 2 3 4
x x x x c y y y y
1 2 3 4 0 1 2 3
Solution: Look back at the
we see the sky [START] vediamo il cielo
whole input sequence on
each step of the output
Sutskever et al, “Sequence to sequence learning with neural networks”, NeurIPS 2014
Stanford CS231n 10th Anniversary Lecture 8 - 12 April 24, 2025

[Page contains 4 table(s)]


### Table 1

| Sequence to Sequence with RNNs
Decoder: s = g (y , s , c)
Input: Sequence x , … x
t U t-1 t-1
1 T
Output: Sequence y , …, y
1 T’
vediamo il cielo [STOP]
From final hidden state predict:
y y y y
Initial decoder state s 1 2 3 4
Encoder: h = f (x , h )
0
t W t t-1
Context vector c (often c=h )
T
h h h h s s s s s
1 2 3 4 0 1 2 3 4
x x x x c y y y y
1 2 3 4 0 1 2 3
Solution: Look back at the
we see the sky [START] vediamo il cielo
whole input sequence on
each step of the output
Sutskever et al, “Sequence to sequence learning with neural networks”, NeurIPS 2014 |
| Stanford CS231n 10th Anniversary Lecture 8 - 12 April 24, 2025 |


### Table 2

| s
1 |
|  |


### Table 3

| s
2 |
|  |


### Table 4

| s
3 |
|  |


---
## Page 13
---


Sequence to Sequence with RNNs and Attention
Input: Sequence x , … x
1 T
Output: Sequence y , …, y
1 T’
From final hidden state:
Encoder: h = f (x , h )
t W t t-1 Initial decoder state s
0
h h h h s
1 2 3 4 0
x x x x
1 2 3 4
we see the sky
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015
Stanford CS231n 10th Anniversary Lecture 8 - 13 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Sequence to Sequence with RNNs and Attention
Input: Sequence x , … x
1 T
Output: Sequence y , …, y
1 T’
From final hidden state:
Encoder: h = f (x , h )
t W t t-1 Initial decoder state s
0
h h h h s
1 2 3 4 0
x x x x
1 2 3 4
we see the sky
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015 |
| Stanford CS231n 10th Anniversary Lecture 8 - 13 April 24, 2025 |


---
## Page 14
---


Sequence to Sequence with RNNs and Attention
Compute (scalar) alignment scores
e = f (s , h) (f is a Linear Layer)
t,i att t-1 i att
From final hidden state:
e 11 e 12 e 13 e 14 Initial decoder state s
0
h h h h s
1 2 3 4 0
x x x x
1 2 3 4
we see the sky
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015
Stanford CS231n 10th Anniversary Lecture 8 - 14 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Sequence to Sequence with RNNs and Attention
Compute (scalar) alignment scores
e = f (s , h) (f is a Linear Layer)
t,i att t-1 i att
From final hidden state:
e 11 e 12 e 13 e 14 Initial decoder state s
0
h h h h s
1 2 3 4 0
x x x x
1 2 3 4
we see the sky
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015 |
| Stanford CS231n 10th Anniversary Lecture 8 - 14 April 24, 2025 |


---
## Page 15
---


Sequence to Sequence with RNNs and Attention
Compute (scalar) alignment scores
e = f (s , h) (f is a Linear Layer)
t,i att t-1 i att
a a a a
11 12 13 14
Normalize alignment scores
softmax
to get attention weights
From final hidden state:
0 < a < 1 ∑a = 1
e 11 e 12 e 13 e 14 Initial decoder state s t,i i t,i
0
h h h h s
1 2 3 4 0
x x x x
1 2 3 4
we see the sky
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015
Stanford CS231n 10th Anniversary Lecture 8 - 15 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Sequence to Sequence with RNNs and Attention
Compute (scalar) alignment scores
e = f (s , h) (f is a Linear Layer)
t,i att t-1 i att
a a a a
11 12 13 14
Normalize alignment scores
softmax
to get attention weights
From final hidden state:
0 < a < 1 ∑a = 1
e 11 e 12 e 13 e 14 Initial decoder state s t,i i t,i
0
h h h h s
1 2 3 4 0
x x x x
1 2 3 4
we see the sky
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015 |
| Stanford CS231n 10th Anniversary Lecture 8 - 15 April 24, 2025 |


---
## Page 16
---


Sequence to Sequence with RNNs and Attention
Compute (scalar) alignment scores
e = f (s , h) (f is a Linear Layer)
t,i att t-1 i att
a a a a
11 12 13 14
vediamo
Normalize alignment scores
softmax
to get attention weights
From final hidden state:
0 < a < 1 ∑a = 1
e 11 e 12 e 13 e 14 Initial decoder state s t,i i t,i
0
Compute context vector as
weighted sum of hidden
+ states
h h h h s
1 2 3 4 0
c = ∑a h
t i t,i i
x x x x c
1 2 3 4 1
we see the sky
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015
Stanford CS231n 10th Anniversary Lecture 8 - 16 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Sequence to Sequence with RNNs and Attention
Compute (scalar) alignment scores
e = f (s , h) (f is a Linear Layer)
t,i att t-1 i att
a a a a
11 12 13 14
vediamo
Normalize alignment scores
softmax
to get attention weights
From final hidden state:
0 < a < 1 ∑a = 1
e 11 e 12 e 13 e 14 Initial decoder state s t,i i t,i
0
Compute context vector as
weighted sum of hidden
+ states
h h h h s
1 2 3 4 0
c = ∑a h
t i t,i i
x x x x c
1 2 3 4 1
we see the sky
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015 |
| Stanford CS231n 10th Anniversary Lecture 8 - 16 April 24, 2025 |


[Page contains 4 image(s)]


---
## Page 17
---


Sequence to Sequence with RNNs and Attention
Compute (scalar) alignment scores
e = f (s , h) (f is a Linear Layer)
t,i att t-1 i att
a a a a
11 12 13 14
vediamo
Normalize alignment scores
softmax
to get attention weights
From final hidden state: y
1 0 < a < 1 ∑a = 1
e 11 e 12 e 13 e 14 Initial decoder state s t,i i t,i
0
Compute context vector as
weighted sum of hidden
h h h h s + s states
1 2 3 4 0 1
c = ∑a h
t i t,i i
Use context vector in
decoder: s = g (y , s , c)
t U t-1 t-1 t
x x x x c y
1 2 3 4 1 0
g is an RNN unit
U
we see the sky (e.g. LSTM, GRU)
[START]
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015
Stanford CS231n 10th Anniversary Lecture 8 - 17 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Sequence to Sequence with RNNs and Attention
Compute (scalar) alignment scores
e = f (s , h) (f is a Linear Layer)
t,i att t-1 i att
a a a a
11 12 13 14
vediamo
Normalize alignment scores
softmax
to get attention weights
From final hidden state: y
1 0 < a < 1 ∑a = 1
e 11 e 12 e 13 e 14 Initial decoder state s t,i i t,i
0
Compute context vector as
weighted sum of hidden
h h h h s + s states
1 2 3 4 0 1
c = ∑a h
t i t,i i
Use context vector in
decoder: s = g (y , s , c)
t U t-1 t-1 t
x x x x c y
1 2 3 4 1 0
g is an RNN unit
U
we see the sky (e.g. LSTM, GRU)
[START]
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015 |
| Stanford CS231n 10th Anniversary Lecture 8 - 17 April 24, 2025 |


[Page contains 4 image(s)]


---
## Page 18
---


Sequence to Sequence with RNNs and Attention
Compute (scalar) alignment scores
e = f (s , h) (f is a Linear Layer)
t,i att t-1 i att
a a a a
11 12 13 14
vediamo
Normalize alignment scores
softmax
to get attention weights
From final hidden state: y
1 0 < a < 1 ∑a = 1
e 11 e 12 e 13 e 14 Initial decoder state s t,i i t,i
0
Compute context vector as
weighted sum of hidden
+ states
h h h h s s
1 2 3 4 0 1
c = ∑a h
Intuition: Context t i t,i i
vector attends to the Use context vector in
relevant part of the decoder: s = g (y , s , c)
t U t-1 t-1 t
x x x x c y
1 2 3 4 1 0
input sequence
“vediamo” = “we see”
we see the sky
so maybe a =a =0.45,
11 12 [START]
a =a =0.05
13 14
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015
Stanford CS231n 10th Anniversary Lecture 8 - 18 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Sequence to Sequence with RNNs and Attention
Compute (scalar) alignment scores
e = f (s , h) (f is a Linear Layer)
t,i att t-1 i att
a a a a
11 12 13 14
vediamo
Normalize alignment scores
softmax
to get attention weights
From final hidden state: y
1 0 < a < 1 ∑a = 1
e 11 e 12 e 13 e 14 Initial decoder state s t,i i t,i
0
Compute context vector as
weighted sum of hidden
+ states
h h h h s s
1 2 3 4 0 1
c = ∑a h
Intuition: Context t i t,i i
vector attends to the Use context vector in
relevant part of the decoder: s = g (y , s , c)
t U t-1 t-1 t
x x x x c y
1 2 3 4 1 0
input sequence
“vediamo” = “we see”
we see the sky
so maybe a =a =0.45,
11 12 [START]
a =a =0.05
13 14
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015 |
| Stanford CS231n 10th Anniversary Lecture 8 - 18 April 24, 2025 |


[Page contains 4 image(s)]


---
## Page 19
---


Sequence to Sequence with RNNs and Attention
Compute (scalar) alignment scores
e = f (s , h) (f is a Linear Layer)
t,i att t-1 i att
a a a a
11 12 13 14
vediamo
Normalize alignment scores
softmax
to get attention weights
From final hidden state: y
1 0 < a < 1 ∑a = 1
e 11 e 12 e 13 e 14 Initial decoder state s t,i i t,i
0
Compute context vector as
weighted sum of hidden
+ states
h h h h s s
1 2 3 4 0 1
c = ∑a h
Intuition: Context t i t,i i
vector attends to the Use context vector in
relevant part of the decoder: s = g (y , s , c)
t U t-1 t-1 t
x x x x c y
1 2 3 4 1 0
input sequence
All differentiable! No
“vediamo” = “we see”
supervision on attention
we see the sky
so maybe a =a =0.45,
11 12 [START] weights. Backprop
a =a =0.05
13 14 through everything
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015
Stanford CS231n 10th Anniversary Lecture 8 - 19 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Sequence to Sequence with RNNs and Attention
Compute (scalar) alignment scores
e = f (s , h) (f is a Linear Layer)
t,i att t-1 i att
a a a a
11 12 13 14
vediamo
Normalize alignment scores
softmax
to get attention weights
From final hidden state: y
1 0 < a < 1 ∑a = 1
e 11 e 12 e 13 e 14 Initial decoder state s t,i i t,i
0
Compute context vector as
weighted sum of hidden
+ states
h h h h s s
1 2 3 4 0 1
c = ∑a h
Intuition: Context t i t,i i
vector attends to the Use context vector in
relevant part of the decoder: s = g (y , s , c)
t U t-1 t-1 t
x x x x c y
1 2 3 4 1 0
input sequence
All differentiable! No
“vediamo” = “we see”
supervision on attention
we see the sky
so maybe a =a =0.45,
11 12 [START] weights. Backprop
a =a =0.05
13 14 through everything
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015 |
| Stanford CS231n 10th Anniversary Lecture 8 - 19 April 24, 2025 |


[Page contains 4 image(s)]


---
## Page 20
---


Sequence to Sequence with RNNs and Attention
Repeat: Use s to compute
1
new context vector c
2
a a a a Compute new alignment
21 22 23 24
vediamo
scores e and attention
2,i
softmax
weights a
2,i
y
1
e e e e
21 22 23 24
+
h h h h s s
1 2 3 4 0 1
x x x x c y c
1 2 3 4 1 0 2
we see the sky
[START]
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015
Stanford CS231n 10th Anniversary Lecture 8 - 20 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Sequence to Sequence with RNNs and Attention
Repeat: Use s to compute
1
new context vector c
2
a a a a Compute new alignment
21 22 23 24
vediamo
scores e and attention
2,i
softmax
weights a
2,i
y
1
e e e e
21 22 23 24
+
h h h h s s
1 2 3 4 0 1
x x x x c y c
1 2 3 4 1 0 2
we see the sky
[START]
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015 |
| Stanford CS231n 10th Anniversary Lecture 8 - 20 April 24, 2025 |


### Table 2

| s
1 |
| s |


[Page contains 4 image(s)]


---
## Page 21
---


Sequence to Sequence with RNNs and Attention
Repeat: Use s to compute
1
new context vector c
2
a a a a
21 22 23 24
vediamo il
softmax
y y
1 2
e e e e
21 22 23 24
+ Use context vector
in decoder: s =
t
h h h h s s s g (y , s , c)
1 2 3 4 0 1 2 U t-1 t-1 t
x x x x c y c y
1 2 3 4 1 0 2 1
we see the sky
[START] vediamo
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015
Stanford CS231n 10th Anniversary Lecture 8 - 21 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Sequence to Sequence with RNNs and Attention
Repeat: Use s to compute
1
new context vector c
2
a a a a
21 22 23 24
vediamo il
softmax
y y
1 2
e e e e
21 22 23 24
+ Use context vector
in decoder: s =
t
h h h h s s s g (y , s , c)
1 2 3 4 0 1 2 U t-1 t-1 t
x x x x c y c y
1 2 3 4 1 0 2 1
we see the sky
[START] vediamo
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015 |
| Stanford CS231n 10th Anniversary Lecture 8 - 21 April 24, 2025 |


### Table 2

| s
1 |
| s |


[Page contains 4 image(s)]


---
## Page 22
---


Sequence to Sequence with RNNs and Attention
Repeat: Use s to compute
1
new context vector c
2
a a a a
21 22 23 24
vediamo il
softmax
y y
1 2
e e e e
21 22 23 24
+ Use context vector
in decoder: s =
t
h h h h s s s g (y , s , c)
1 2 3 4 0 1 2 U t-1 t-1 t
Intuition: Context vector
attends to the relevant
x x x x part of the input sequence c y c y
1 2 3 4 1 0 2 1
“il” = “the”
we see the sky so maybe a =a =0.05,
21 22
a =0.1, a =0.8 [START] vediamo
24 23
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015
Stanford CS231n 10th Anniversary Lecture 8 - 22 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Sequence to Sequence with RNNs and Attention
Repeat: Use s to compute
1
new context vector c
2
a a a a
21 22 23 24
vediamo il
softmax
y y
1 2
e e e e
21 22 23 24
+ Use context vector
in decoder: s =
t
h h h h s s s g (y , s , c)
1 2 3 4 0 1 2 U t-1 t-1 t
Intuition: Context vector
attends to the relevant
x x x x part of the input sequence c y c y
1 2 3 4 1 0 2 1
“il” = “the”
we see the sky so maybe a =a =0.05,
21 22
a =0.1, a =0.8 [START] vediamo
24 23
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015 |
| Stanford CS231n 10th Anniversary Lecture 8 - 22 April 24, 2025 |


### Table 2

| s
1 |
| s |


[Page contains 4 image(s)]


---
## Page 23
---


Sequence to Sequence with RNNs and Attention
Use a different context vector in each timestep of decoder
- Input sequence not bottlenecked through single vector
vediamo il cielo [STOP]
- At each timestep of decoder, context vector “looks at”
different parts of the input sequence
y y y y
1 2 3 4
h h h h s s s s s
1 2 3 4 0 1 2 3 4
x x x x c y c y c y c y
1 2 3 4 1 0 2 1 3 2 4 3
we see the sky
[START] vediamo il cielo
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015
Stanford CS231n 10th Anniversary Lecture 8 - 23 April 24, 2025

[Page contains 3 table(s)]


### Table 1

| Sequence to Sequence with RNNs and Attention
Use a different context vector in each timestep of decoder
- Input sequence not bottlenecked through single vector
vediamo il cielo [STOP]
- At each timestep of decoder, context vector “looks at”
different parts of the input sequence
y y y y
1 2 3 4
h h h h s s s s s
1 2 3 4 0 1 2 3 4
x x x x c y c y c y c y
1 2 3 4 1 0 2 1 3 2 4 3
we see the sky
[START] vediamo il cielo
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015 |
| Stanford CS231n 10th Anniversary Lecture 8 - 23 April 24, 2025 |


### Table 2

| s
1 |
| s |


### Table 3

| s
3 |
|  |


---
## Page 24
---


Sequence to Sequence with RNNs and Attention
Example: English to
Visualize attention weights a
t,i
French translation
a a a a
21 22 23 24
softmax
e e e e
21 22 23 24
h h h h
1 2 3 4
x x x x
1 2 3 4
we see the sky
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015
Stanford CS231n 10th Anniversary Lecture 8 - 24 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Sequence to Sequence with RNNs and Attention
Example: English to
Visualize attention weights a
t,i
French translation
a a a a
21 22 23 24
softmax
e e e e
21 22 23 24
h h h h
1 2 3 4
x x x x
1 2 3 4
we see the sky
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015 |
| Stanford CS231n 10th Anniversary Lecture 8 - 24 April 24, 2025 |


[Page contains 5 image(s)]


---
## Page 25
---


Sequence to Sequence with RNNs and Attention
Example: English to
Visualize attention weights a
t,i
French translation
Input: “The agreement on the
European Economic Area was
signed in August 1992.”
Output: “L’accord sur la zone
économique européenne a été
signé en août 1992.”
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015
Stanford CS231n 10th Anniversary Lecture 8 - 25 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Sequence to Sequence with RNNs and Attention
Example: English to
Visualize attention weights a
t,i
French translation
Input: “The agreement on the
European Economic Area was
signed in August 1992.”
Output: “L’accord sur la zone
économique européenne a été
signé en août 1992.”
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015 |
| Stanford CS231n 10th Anniversary Lecture 8 - 25 April 24, 2025 |


[Page contains 1 image(s)]


---
## Page 26
---


Sequence to Sequence with RNNs and Attention
Example: English to
Visualize attention weights a
French translation t,i
Input: “The agreement on the
Diagonal attention
European Economic Area was
means words
signed in August 1992.”
correspond in order
Output: “L’accord sur la zone
économique européenne a été
signé en août 1992.”
Diagonal attention
means words
correspond in order
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015
Stanford CS231n 10th Anniversary Lecture 8 - 26 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Sequence to Sequence with RNNs and Attention
Example: English to
Visualize attention weights a
French translation t,i
Input: “The agreement on the
Diagonal attention
European Economic Area was
means words
signed in August 1992.”
correspond in order
Output: “L’accord sur la zone
économique européenne a été
signé en août 1992.”
Diagonal attention
means words
correspond in order
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015 |
| Stanford CS231n 10th Anniversary Lecture 8 - 26 April 24, 2025 |


### Table 2

|  |  |
|  |  |


[Page contains 1 image(s)]


---
## Page 27
---


Sequence to Sequence with RNNs and Attention
Example: English to
Visualize attention weights a
French translation t,i
Input: “The agreement on the
Diagonal attention
European Economic Area was
means words
signed in August 1992.”
correspond in order
Attention figures
Output: “L’accord sur la zone
out other word
économique européenne a été
orders
signé en août 1992.”
Diagonal attention
means words
correspond in order
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015
Stanford CS231n 10th Anniversary Lecture 8 - 27 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Sequence to Sequence with RNNs and Attention
Example: English to
Visualize attention weights a
French translation t,i
Input: “The agreement on the
Diagonal attention
European Economic Area was
means words
signed in August 1992.”
correspond in order
Attention figures
Output: “L’accord sur la zone
out other word
économique européenne a été
orders
signé en août 1992.”
Diagonal attention
means words
correspond in order
Bahdanau et al, “Neural machine translation by jointly learning to align and translate”, ICLR 2015 |
| Stanford CS231n 10th Anniversary Lecture 8 - 27 April 24, 2025 |


### Table 2

|  |  |  |  |
|  |  |  |  |
|  |  |  |  |


[Page contains 1 image(s)]


---
## Page 28
---


Sequence to Sequence with RNNs and Attention
There’s a general
operator hiding here:
a a a a
21 22 23 24
vediamo il cielo [STOP]
softmax
y y y y
1 2 3 4
e e e e
21 22 23 24
+
h h h h s s s s s
1 2 3 4 0 1 2 3 4
x x x x c y c y c y c y
1 2 3 4 1 0 2 1 3 2 4 3
we see the sky
[START] vediamo il cielo
Stanford CS231n 10th Anniversary Lecture 8 - 28 April 24, 2025

[Page contains 3 table(s)]


### Table 1

| Sequence to Sequence with RNNs and Attention
There’s a general
operator hiding here:
a a a a
21 22 23 24
vediamo il cielo [STOP]
softmax
y y y y
1 2 3 4
e e e e
21 22 23 24
+
h h h h s s s s s
1 2 3 4 0 1 2 3 4
x x x x c y c y c y c y
1 2 3 4 1 0 2 1 3 2 4 3
we see the sky
[START] vediamo il cielo |
| Stanford CS231n 10th Anniversary Lecture 8 - 28 April 24, 2025 |


### Table 2

| s
1 |
| s |


### Table 3

| s
3 |
|  |


[Page contains 4 image(s)]


---
## Page 29
---


Sequence to Sequence with RNNs and Attention
Query vectors (decoder RNN states) and There’s a general
data vectors (encoder RNN states) operator hiding here:
get transformed to
vediamo il cielo [STOP]
output vectors (Context states).
Each query attends to all data vectors and
gives one output vector y 1 y 2 y 3 y 4
h h h h s s s s s
1 2 3 4 0 1 2 3 4
x x x x c y c y c y c y
1 2 3 4 1 0 2 1 3 2 4 3
we see the sky
[START] vediamo il cielo
Stanford CS231n 10th Anniversary Lecture 8 - 29 April 24, 2025

[Page contains 3 table(s)]


### Table 1

| Sequence to Sequence with RNNs and Attention
Query vectors (decoder RNN states) and There’s a general
data vectors (encoder RNN states) operator hiding here:
get transformed to
vediamo il cielo [STOP]
output vectors (Context states).
Each query attends to all data vectors and
gives one output vector y 1 y 2 y 3 y 4
h h h h s s s s s
1 2 3 4 0 1 2 3 4
x x x x c y c y c y c y
1 2 3 4 1 0 2 1 3 2 4 3
we see the sky
[START] vediamo il cielo |
| Stanford CS231n 10th Anniversary Lecture 8 - 29 April 24, 2025 |


### Table 2

| s
1 |
| s |


### Table 3

| s
3 |
|  |


---
## Page 30
---


Attention Layer
Inputs:
Query vector: q [D ]
Q
Stanford CS231n 10th Anniversary Lecture 8 - 30 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Attention Layer
Inputs:
Query vector: q [D ]
Q |
| Stanford CS231n 10th Anniversary Lecture 8 - 30 April 24, 2025 |


[Page contains 1 image(s)]


---
## Page 31
---


Attention Layer
Inputs:
Query vector: q [D ]
Q
Data vectors: X [N x D ]
X X
Stanford CS231n 10th Anniversary Lecture 8 - 31 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Attention Layer
Inputs:
Query vector: q [D ]
Q
Data vectors: X [N x D ]
X X |
| Stanford CS231n 10th Anniversary Lecture 8 - 31 April 24, 2025 |


[Page contains 1 image(s)]


---
## Page 32
---


Attention Layer
Inputs:
Query vector: q [D ]
Q
Data vectors: X [N x D ]
X X
Computation:
Similarities: e [N ] e = f (q, X )
X i att i
Stanford CS231n 10th Anniversary Lecture 8 - 32 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Attention Layer
Inputs:
Query vector: q [D ]
Q
Data vectors: X [N x D ]
X X
Computation:
Similarities: e [N ] e = f (q, X )
X i att i |
| Stanford CS231n 10th Anniversary Lecture 8 - 32 April 24, 2025 |


[Page contains 1 image(s)]


---
## Page 33
---


Attention Layer
Inputs:
Query vector: q [D ]
Q
Data vectors: X [N x D ]
X X
Computation:
Similarities: e [N ] e = f (q, X )
X i att i
Attention weights: a = softmax(e) [N ]
X
Stanford CS231n 10th Anniversary Lecture 8 - 33 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Attention Layer
Inputs:
Query vector: q [D ]
Q
Data vectors: X [N x D ]
X X
Computation:
Similarities: e [N ] e = f (q, X )
X i att i
Attention weights: a = softmax(e) [N ]
X |
| Stanford CS231n 10th Anniversary Lecture 8 - 33 April 24, 2025 |


[Page contains 1 image(s)]


---
## Page 34
---


Attention Layer
Inputs:
Query vector: q [D ]
Q
Data vectors: X [N x D ]
X X
Computation:
Similarities: e [N ] e = f (q, X )
X i att i
Attention weights: a = softmax(e) [N ]
X
Output vector: y = ∑aX [D ]
i i i X
Stanford CS231n 10th Anniversary Lecture 8 - 34 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Attention Layer
Inputs:
Query vector: q [D ]
Q
Data vectors: X [N x D ]
X X
Computation:
Similarities: e [N ] e = f (q, X )
X i att i
Attention weights: a = softmax(e) [N ]
X
Output vector: y = ∑aX [D ]
i i i X |
| Stanford CS231n 10th Anniversary Lecture 8 - 34 April 24, 2025 |


[Page contains 1 image(s)]


---
## Page 35
---


Attention Layer
Inputs:
Query vector: q [D ]
Q
Data vectors: X [N x D ]
X X
Computation:
Similarities: e [N ] e = f (q, X )
X i att i
Attention weights: a = softmax(e) [N ]
X
Let’s generalize this!
Output vector: y = ∑aX [D ]
i i i X
Stanford CS231n 10th Anniversary Lecture 8 - 35 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Attention Layer
Inputs:
Query vector: q [D ]
Q
Data vectors: X [N x D ]
X X
Computation:
Similarities: e [N ] e = f (q, X )
X i att i
Attention weights: a = softmax(e) [N ]
X
Let’s generalize this!
Output vector: y = ∑aX [D ]
i i i X |
| Stanford CS231n 10th Anniversary Lecture 8 - 35 April 24, 2025 |


[Page contains 1 image(s)]


---
## Page 36
---


Attention Layer
Inputs:
Query vector: q [D ]
X
Data vectors: X [N x D ]
X X
Computation:
Similarities: e [N ] e = q · X
X i i Changes
Attention weights: a = softmax(e) [N ]
X - Use dot product for similarity
Output vector: y = ∑aX [D ]
i i i X
Stanford CS231n 10th Anniversary Lecture 8 - 36 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Attention Layer
Inputs:
Query vector: q [D ]
X
Data vectors: X [N x D ]
X X
Computation:
Similarities: e [N ] e = q · X
X i i Changes
Attention weights: a = softmax(e) [N ]
X - Use dot product for similarity
Output vector: y = ∑aX [D ]
i i i X |
| Stanford CS231n 10th Anniversary Lecture 8 - 36 April 24, 2025 |


[Page contains 1 image(s)]


---
## Page 37
---


Attention Layer
Inputs:
Query vector: q [D ]
X
Data vectors: X [N x D ]
X X
Computation:
Similarities: e [N ] e = q · X / 𝐷
X i i 𝑋 Changes
Attention weights: a = softmax(e) [N ]
X - Use scaled dot product for similarity
Output vector: y = ∑aX [D ]
i i i X
Stanford CS231n 10th Anniversary Lecture 8 - 37 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Attention Layer
Inputs:
Query vector: q [D ]
X
Data vectors: X [N x D ]
X X
Computation:
Similarities: e [N ] e = q · X / 𝐷
X i i 𝑋 Changes
Attention weights: a = softmax(e) [N ]
X - Use scaled dot product for similarity
Output vector: y = ∑aX [D ]
i i i X |
| Stanford CS231n 10th Anniversary Lecture 8 - 37 April 24, 2025 |


[Page contains 1 image(s)]


---
## Page 38
---


Attention Layer
Inputs:
Query vector: q [D ]
X
Data vectors: X [N x D ]
X X
Large similarities will cause softmax to
saturate and give vanishing gradients
Recall a · b = |a||b| cos(angle)
Suppose that a and b are constant
vectors of dimension D
Then |a| = (∑a2)1/2 = a 𝐷
i
Computation:
Similarities: e [N ] e = q · X / 𝐷
X i i 𝑋 Changes
Attention weights: a = softmax(e) [N ]
X - Use scaled dot product for similarity
Output vector: y = ∑aX [D ]
i i i X
Stanford CS231n 10th Anniversary Lecture 8 - 38 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Attention Layer
Inputs:
Query vector: q [D ]
X
Data vectors: X [N x D ]
X X
Large similarities will cause softmax to
saturate and give vanishing gradients
Recall a · b = |a||b| cos(angle)
Suppose that a and b are constant
vectors of dimension D
Then |a| = (∑a2)1/2 = a 𝐷
i
Computation:
Similarities: e [N ] e = q · X / 𝐷
X i i 𝑋 Changes
Attention weights: a = softmax(e) [N ]
X - Use scaled dot product for similarity
Output vector: y = ∑aX [D ]
i i i X |
| Stanford CS231n 10th Anniversary Lecture 8 - 38 April 24, 2025 |


[Page contains 1 image(s)]


---
## Page 39
---


Attention Layer
Inputs:
Query vector: Q [N x D ]
Q X
Data vectors: X [N x D ]
X X
Computation:
Similarities: E = QXT / 𝐷 [N x N ]
Changes
𝑋 Q X
E = Q ·X / 𝐷 - Use scaled dot product for similarity
ij i j 𝑋
Attention weights: A = softmax(E, dim=1) [N x N ] - Multiple query vectors
Q X
Output vector: Y = AX [N x D ]
Q X
Y = ∑A X
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 39 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Attention Layer
Inputs:
Query vector: Q [N x D ]
Q X
Data vectors: X [N x D ]
X X
Computation:
Similarities: E = QXT / 𝐷 [N x N ]
Changes
𝑋 Q X
E = Q ·X / 𝐷 - Use scaled dot product for similarity
ij i j 𝑋
Attention weights: A = softmax(E, dim=1) [N x N ] - Multiple query vectors
Q X
Output vector: Y = AX [N x D ]
Q X
Y = ∑A X
i j ij j |
| Inputs:
Query vector: Q [N x D ]
Q X
Data vectors: X [N x D ]
X X
Computation:
Similarities: E = QXT / 𝐷 [N x N ]
Chang
𝑋 Q X
E = Q ·X / 𝐷 - Use
ij i j 𝑋
Attention weights: A = softmax(E, dim=1) [N x N ] - Mul
Q X
Output vector: Y = AX [N x D ]
Q X
Y = ∑A X
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 39 April 24, 2025 |


[Page contains 1 image(s)]


---
## Page 40
---


Attention Layer
Inputs:
Query vector: Q [N x D ]
Q Q
Data vectors: X [N x D ]
X X
Key matrix: W [D x D ]
K X Q
Value matrix: W [D x D ]
V X V
Computation:
Keys: K = XW [N x D ]
K X Q
Values: V = XW [N x D ]
V X V
Similarities: E = QKT / 𝐷 [N x N ]
𝑄 Q X Changes
E = Q ·K / 𝐷 - Use scaled dot product for similarity
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N ] - Multiple query vectors
Q X
Output vector: Y = AV [N x D ] - Separate key and value
Q V
Y = ∑A V
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 40 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Attention Layer
Inputs:
Query vector: Q [N x D ]
Q Q
Data vectors: X [N x D ]
X X
Key matrix: W [D x D ]
K X Q
Value matrix: W [D x D ]
V X V
Computation:
Keys: K = XW [N x D ]
K X Q
Values: V = XW [N x D ]
V X V
Similarities: E = QKT / 𝐷 [N x N ]
𝑄 Q X Changes
E = Q ·K / 𝐷 - Use scaled dot product for similarity
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N ] - Multiple query vectors
Q X
Output vector: Y = AV [N x D ] - Separate key and value
Q V
Y = ∑A V
i j ij j |
| Inputs:
Query vector: Q [N x D ]
Q Q
Data vectors: X [N x D ]
X X
Key matrix: W [D x D ]
K X Q
Value matrix: W [D x D ]
V X V
Computation:
Keys: K = XW [N x D ]
K X Q
Values: V = XW [N x D ]
V X V
Similarities: E = QKT / 𝐷 [N x N ]
𝑄 Q X Chang
E = Q ·K / 𝐷 - Use
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N ] - Mul
Q X
Output vector: Y = AV [N x D ] - Sep
Q V
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 40 April 24, 2025 |


[Page contains 1 image(s)]


---
## Page 41
---


Attention Layer
Inputs:
Query vector: Q [N x D ]
Q Q
Data vectors: X [N x D ]
X X
Key matrix: W [D x D ]
K X Q
Value matrix: W [D x D ]
V X V
Computation:
Keys: K = XW [N x D ] X
K X Q 1
Values: V = XW [N x D ]
V X V
X
Similarities: E = QKT / 𝐷 [N x N ] 2
𝑄 Q X
E = Q ·K / 𝐷 X
ij i j 𝑄 3
Attention weights: A = softmax(E, dim=1) [N x N ]
Q X
Output vector: Y = AV [N x D ]
Q V
Q Q Q Q
Y = ∑A V 1 2 3 4
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 41 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Attention Layer
Inputs:
Query vector: Q [N x D ]
Q Q
Data vectors: X [N x D ]
X X
Key matrix: W [D x D ]
K X Q
Value matrix: W [D x D ]
V X V
Computation:
Keys: K = XW [N x D ] X
K X Q 1
Values: V = XW [N x D ]
V X V
X
Similarities: E = QKT / 𝐷 [N x N ] 2
𝑄 Q X
E = Q ·K / 𝐷 X
ij i j 𝑄 3
Attention weights: A = softmax(E, dim=1) [N x N ]
Q X
Output vector: Y = AV [N x D ]
Q V
Q Q Q Q
Y = ∑A V 1 2 3 4
i j ij j |
| Inputs:
Query vector: Q [N x D ]
Q Q
Data vectors: X [N x D ]
X X
Key matrix: W [D x D ]
K X Q
Value matrix: W [D x D ]
V X V
Computation:
Keys: K = XW [N x D ] X
K X Q 1
Values: V = XW [N x D ]
V X V
X
Similarities: E = QKT / 𝐷 [N x N ] 2
𝑄 Q X
E = Q ·K / 𝐷 X
ij i j 𝑄 3
Attention weights: A = softmax(E, dim=1) [N x N ]
Q X
Output vector: Y = AV [N x D ]
Q V
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 41 April 24, 2025 |


---
## Page 42
---


Attention Layer
Inputs:
Query vector: Q [N x D ]
Q Q
Data vectors: X [N x D ]
X X V
1
Key matrix: W [D x D ]
K X Q
Value matrix: W [D x D ] V
V X V 2
V
3
Computation:
Keys: K = XW [N x D ] X K
K X Q 1 1
Values: V = XW [N x D ]
V X V
X K
Similarities: E = QKT / 𝐷 [N x N ] 2 2
𝑄 Q X
E = Q ·K / 𝐷 X K
ij i j 𝑄 3 3
Attention weights: A = softmax(E, dim=1) [N x N ]
Q X
Output vector: Y = AV [N x D ]
Q V
Q Q Q Q
Y = ∑A V 1 2 3 4
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 42 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Attention Layer
Inputs:
Query vector: Q [N x D ]
Q Q
Data vectors: X [N x D ]
X X V
1
Key matrix: W [D x D ]
K X Q
Value matrix: W [D x D ] V
V X V 2
V
3
Computation:
Keys: K = XW [N x D ] X K
K X Q 1 1
Values: V = XW [N x D ]
V X V
X K
Similarities: E = QKT / 𝐷 [N x N ] 2 2
𝑄 Q X
E = Q ·K / 𝐷 X K
ij i j 𝑄 3 3
Attention weights: A = softmax(E, dim=1) [N x N ]
Q X
Output vector: Y = AV [N x D ]
Q V
Q Q Q Q
Y = ∑A V 1 2 3 4
i j ij j |
| Inputs:
Query vector: Q [N x D ]
Q Q
Data vectors: X [N x D ]
X X
Key matrix: W [D x D ]
K X Q
Value matrix: W [D x D ]
V X V
Computation:
Keys: K = XW [N x D ] X
K X Q 1
Values: V = XW [N x D ]
V X V
X
Similarities: E = QKT / 𝐷 [N x N ] 2
𝑄 Q X
E = Q ·K / 𝐷 X
ij i j 𝑄 3
Attention weights: A = softmax(E, dim=1) [N x N ]
Q X
Output vector: Y = AV [N x D ]
Q V
Y = ∑A V
i j ij j |
| Similarities: E = QKT / 𝐷 [N x N ]
𝑄 Q X
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N ]
Q X
Output vector: Y = AV [N x D ]
Q V
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 42 April 24, 2025 |


### Table 2

|  |  |
|  |  |


---
## Page 43
---


Attention Layer
Inputs:
Query vector: Q [N x D ]
Q Q
Data vectors: X [N x D ]
X X V
1
Key matrix: W [D x D ]
K X Q
Value matrix: W [D x D ] V
V X V 2
V
3
Computation:
Keys: K = XW [N x D ] X K E E E E
K X Q 1 1 1,1 2,1 3,1 4,1
Values: V = XW [N x D ]
V X V
X K E E E E
Similarities: E = QKT / 𝐷 [N x N ] 2 2 1,2 2,2 3,2 4,2
𝑄 Q X
E = Q ·K / 𝐷 X K E E E E
ij i j 𝑄 3 3 1,3 2,3 3,3 4,3
Attention weights: A = softmax(E, dim=1) [N x N ]
Q X
Output vector: Y = AV [N x D ]
Q V
Q Q Q Q
Y = ∑A V 1 2 3 4
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 43 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Attention Layer
Inputs:
Query vector: Q [N x D ]
Q Q
Data vectors: X [N x D ]
X X V
1
Key matrix: W [D x D ]
K X Q
Value matrix: W [D x D ] V
V X V 2
V
3
Computation:
Keys: K = XW [N x D ] X K E E E E
K X Q 1 1 1,1 2,1 3,1 4,1
Values: V = XW [N x D ]
V X V
X K E E E E
Similarities: E = QKT / 𝐷 [N x N ] 2 2 1,2 2,2 3,2 4,2
𝑄 Q X
E = Q ·K / 𝐷 X K E E E E
ij i j 𝑄 3 3 1,3 2,3 3,3 4,3
Attention weights: A = softmax(E, dim=1) [N x N ]
Q X
Output vector: Y = AV [N x D ]
Q V
Q Q Q Q
Y = ∑A V 1 2 3 4
i j ij j |
| Inputs:
Query vector: Q [N x D ]
Q Q
Data vectors: X [N x D ]
X X
Key matrix: W [D x D ]
K X Q
Value matrix: W [D x D ]
V X V
Computation:
Keys: K = XW [N x D ] X
K X Q 1
Values: V = XW [N x D ]
V X V
X
Similarities: E = QKT / 𝐷 [N x N ] 2
𝑄 Q X
E = Q ·K / 𝐷 X
ij i j 𝑄 3
Attention weights: A = softmax(E, dim=1) [N x N ]
Q X
Output vector: Y = AV [N x D ]
Q V
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 43 April 24, 2025 |


### Table 2

|  |  |
|  |  |


---
## Page 44
---


Attention Layer Softmax normalizes each
column: each query predicts
Inputs: a distribution over the keys
Query vector: Q [N x D ]
Q Q
Data vectors: X [N x D ]
X X V A A A A
1 1,1 2,1 3,1 4,1
Key matrix: W [D x D ]
K X Q
Value matrix: W V [D X x D V ] V 2 A 1,2 A 2,2 A 3,2 A 4,2
V A A A A
3 1,3 2,3 3,3 4,3
Softmax( )
Computation:
Keys: K = XW [N x D ] X K E E E E
K X Q 1 1 1,1 2,1 3,1 4,1
Values: V = XW [N x D ]
V X V
X K E E E E
Similarities: E = QKT / 𝐷 [N x N ] 2 2 1,2 2,2 3,2 4,2
𝑄 Q X
E = Q ·K / 𝐷 X K E E E E
ij i j 𝑄 3 3 1,3 2,3 3,3 4,3
Attention weights: A = softmax(E, dim=1) [N x N ]
Q X
Output vector: Y = AV [N x D ]
Q V
Q Q Q Q
Y = ∑A V 1 2 3 4
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 44 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Attention Layer Softmax normalizes each
column: each query predicts
Inputs: a distribution over the keys
Query vector: Q [N x D ]
Q Q
Data vectors: X [N x D ]
X X V A A A A
1 1,1 2,1 3,1 4,1
Key matrix: W [D x D ]
K X Q
Value matrix: W V [D X x D V ] V 2 A 1,2 A 2,2 A 3,2 A 4,2
V A A A A
3 1,3 2,3 3,3 4,3
Softmax( )
Computation:
Keys: K = XW [N x D ] X K E E E E
K X Q 1 1 1,1 2,1 3,1 4,1
Values: V = XW [N x D ]
V X V
X K E E E E
Similarities: E = QKT / 𝐷 [N x N ] 2 2 1,2 2,2 3,2 4,2
𝑄 Q X
E = Q ·K / 𝐷 X K E E E E
ij i j 𝑄 3 3 1,3 2,3 3,3 4,3
Attention weights: A = softmax(E, dim=1) [N x N ]
Q X
Output vector: Y = AV [N x D ]
Q V
Q Q Q Q
Y = ∑A V 1 2 3 4
i j ij j |
| Inputs:
Query vector: Q [N x D ]
Q Q
Data vectors: X [N x D ]
X X
Key matrix: W [D x D ]
K X Q
Value matrix: W [D x D ]
V X V
Computation:
Keys: K = XW [N x D ] X
K X Q 1
Values: V = XW [N x D ]
V X V
X
Similarities: E = QKT / 𝐷 [N x N ] 2
𝑄 Q X
E = Q ·K / 𝐷 X
ij i j 𝑄 3
Attention weights: A = softmax(E, dim=1) [N x N ]
Q X
Output vector: Y = AV [N x D ]
Q V
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 44 April 24, 2025 |


### Table 2

|  |  |
|  |  |


---
## Page 45
---


Y Y Y Y
Attention Layer Each output is a linear 1 2 3 4
combination of all values,
Inputs: weighted by attention weights
Product( ), Sum( )
Query vector: Q [N x D ]
Q Q
Data vectors: X [N x D ]
X X V A A A A
1 1,1 2,1 3,1 4,1
Key matrix: W [D x D ]
K X Q
Value matrix: W V [D X x D V ] V 2 A 1,2 A 2,2 A 3,2 A 4,2
V A A A A
3 1,3 2,3 3,3 4,3
Softmax( )
Computation:
Keys: K = XW [N x D ] X K E E E E
K X Q 1 1 1,1 2,1 3,1 4,1
Values: V = XW [N x D ]
V X V
X K E E E E
Similarities: E = QKT / 𝐷 [N x N ] 2 2 1,2 2,2 3,2 4,2
𝑄 Q X
E = Q ·K / 𝐷 X K E E E E
ij i j 𝑄 3 3 1,3 2,3 3,3 4,3
Attention weights: A = softmax(E, dim=1) [N x N ]
Q X
Output vector: Y = AV [N x D ]
Q V
Q Q Q Q
Y = ∑A V 1 2 3 4
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 45 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Y Y Y Y
Attention Layer Each output is a linear 1 2 3 4
combination of all values,
Inputs: weighted by attention weights
Product( ), Sum( )
Query vector: Q [N x D ]
Q Q
Data vectors: X [N x D ]
X X V A A A A
1 1,1 2,1 3,1 4,1
Key matrix: W [D x D ]
K X Q
Value matrix: W V [D X x D V ] V 2 A 1,2 A 2,2 A 3,2 A 4,2
V A A A A
3 1,3 2,3 3,3 4,3
Softmax( )
Computation:
Keys: K = XW [N x D ] X K E E E E
K X Q 1 1 1,1 2,1 3,1 4,1
Values: V = XW [N x D ]
V X V
X K E E E E
Similarities: E = QKT / 𝐷 [N x N ] 2 2 1,2 2,2 3,2 4,2
𝑄 Q X
E = Q ·K / 𝐷 X K E E E E
ij i j 𝑄 3 3 1,3 2,3 3,3 4,3
Attention weights: A = softmax(E, dim=1) [N x N ]
Q X
Output vector: Y = AV [N x D ]
Q V
Q Q Q Q
Y = ∑A V 1 2 3 4
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 45 April 24, 2025 |


### Table 2

|  |  |
|  |  |


---
## Page 46
---


Y Y Y Y
Cross-Attention Layer 1 2 3 4
Inputs:
Product( ), Sum( )
Query vector: Q [N x D ] Each query produces
Q Q
Data vectors: X [N x D ] one output, which is a
X X V A A A A
mix of information in 1 1,1 2,1 3,1 4,1
Key matrix: W [D x D ]
K X Q
the data vectors
Value matrix: W V [D X x D V ] V 2 A 1,2 A 2,2 A 3,2 A 4,2
V A A A A
3 1,3 2,3 3,3 4,3
Softmax( )
Computation:
Keys: K = XW [N x D ] X K E E E E
K X Q 1 1 1,1 2,1 3,1 4,1
Values: V = XW [N x D ]
V X V
X K E E E E
Similarities: E = QKT / 𝐷 [N x N ] 2 2 1,2 2,2 3,2 4,2
𝑄 Q X
E = Q ·K / 𝐷 X K E E E E
ij i j 𝑄 3 3 1,3 2,3 3,3 4,3
Attention weights: A = softmax(E, dim=1) [N x N ]
Q X
Output vector: Y = AV [N x D ]
Q V
Q Q Q Q
Y = ∑A V 1 2 3 4
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 46 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Y Y Y Y
Cross-Attention Layer 1 2 3 4
Inputs:
Product( ), Sum( )
Query vector: Q [N x D ] Each query produces
Q Q
Data vectors: X [N x D ] one output, which is a
X X V A A A A
mix of information in 1 1,1 2,1 3,1 4,1
Key matrix: W [D x D ]
K X Q
the data vectors
Value matrix: W V [D X x D V ] V 2 A 1,2 A 2,2 A 3,2 A 4,2
V A A A A
3 1,3 2,3 3,3 4,3
Softmax( )
Computation:
Keys: K = XW [N x D ] X K E E E E
K X Q 1 1 1,1 2,1 3,1 4,1
Values: V = XW [N x D ]
V X V
X K E E E E
Similarities: E = QKT / 𝐷 [N x N ] 2 2 1,2 2,2 3,2 4,2
𝑄 Q X
E = Q ·K / 𝐷 X K E E E E
ij i j 𝑄 3 3 1,3 2,3 3,3 4,3
Attention weights: A = softmax(E, dim=1) [N x N ]
Q X
Output vector: Y = AV [N x D ]
Q V
Q Q Q Q
Y = ∑A V 1 2 3 4
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 46 April 24, 2025 |


### Table 2

|  |  |
|  |  |


---
## Page 47
---


Y Y Y
1 2 3
Self-Attention Layer
Product( ), Sum( )
Inputs:
V A A A
Input vectors: X [N x D ] Each input produces 1 1,1 2,1 3,1
in
Key matrix: W [D x D ] one output, which is V A A A
K in out 2 1,2 2,2 3,2
Value matrix: W [D x D ] a mix of information
V in out
Query matrix: W [D x D ] from all inputs V 3 A 1,3 A 2,3 A 3,3
Q in out
Softmax( )
Shapes get a little simpler:
Computation:
- N input vectors, each D
Queries: Q = XW Q [N x D out ] - Almost always D = D i = n D K 1 E 1,1 E 2,1 E 3,1
Q V out
Keys: K = XW [N x D ]
K out K E E E
2 1,2 2,2 3,2
Values: V = XW [N x D ]
V out
K E E E
Similarities: E = QKT / 𝐷 [N x N] 3 1,3 2,3 3,3
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 1 2 3
Output vector: Y = AV [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 47 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Y Y Y
1 2 3
Self-Attention Layer
Product( ), Sum( )
Inputs:
V A A A
Input vectors: X [N x D ] Each input produces 1 1,1 2,1 3,1
in
Key matrix: W [D x D ] one output, which is V A A A
K in out 2 1,2 2,2 3,2
Value matrix: W [D x D ] a mix of information
V in out
Query matrix: W [D x D ] from all inputs V 3 A 1,3 A 2,3 A 3,3
Q in out
Softmax( )
Shapes get a little simpler:
Computation:
- N input vectors, each D
Queries: Q = XW Q [N x D out ] - Almost always D = D i = n D K 1 E 1,1 E 2,1 E 3,1
Q V out
Keys: K = XW [N x D ]
K out K E E E
2 1,2 2,2 3,2
Values: V = XW [N x D ]
V out
K E E E
Similarities: E = QKT / 𝐷 [N x N] 3 1,3 2,3 3,3
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 1 2 3
Output vector: Y = AV [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j |
| Inputs:
Input vectors: X [N x D ] Each input produces
in
Key matrix: W [D x D ] one output, which is
K in out
Value matrix: W [D x D ] a mix of information
V in out
from all inputs
Query matrix: W [D x D ]
Q in out
Shapes get a little simpler:
Computation:
- N input vectors, each D
in
Queries: Q = XW [N x D ]
Q out - Almost always D = D = D
Q V out
Keys: K = XW [N x D ]
K out
Values: V = XW [N x D ]
V out
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AV [N x D ]
out
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 47 April 24, 2025 |


### Table 2

|  |  |
|  |  |
|  |  |


---
## Page 48
---


Self-Attention Layer
Inputs:
V
Input vectors: X [N x D ] Each input produces 1 From each input:
in
compute a query,
Key matrix: W [D x D ] one output, which is V
K in out 2 key, and value vector
Value matrix: W [D x D ] a mix of information
V in out
V
from all inputs
Query matrix: W [D x D ] 3
Q in out
Often fused to one matmul:
Computation:
K
Queries: Q = XW [N x D ]
Q out 1 [Q K V] = X[W W W ]
Q K V
Keys: K = XW [N x D ]
K out K [N x 3Dout] = [N x Din] [Din x 3Dout]
2
Values: V = XW [N x D ]
V out
K
Similarities: E = QKT / 𝐷 [N x N] 3
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 1 2 3
Output vector: Y = AV [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 48 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Self-Attention Layer
Inputs:
V
Input vectors: X [N x D ] Each input produces 1 From each input:
in
compute a query,
Key matrix: W [D x D ] one output, which is V
K in out 2 key, and value vector
Value matrix: W [D x D ] a mix of information
V in out
V
from all inputs
Query matrix: W [D x D ] 3
Q in out
Often fused to one matmul:
Computation:
K
Queries: Q = XW [N x D ]
Q out 1 [Q K V] = X[W W W ]
Q K V
Keys: K = XW [N x D ]
K out K [N x 3Dout] = [N x Din] [Din x 3Dout]
2
Values: V = XW [N x D ]
V out
K
Similarities: E = QKT / 𝐷 [N x N] 3
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 1 2 3
Output vector: Y = AV [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j |
| Inputs:
Input vectors: X [N x D ] Each input produces
in
Key matrix: W [D x D ] one output, which is
K in out
Value matrix: W [D x D ] a mix of information
V in out
from all inputs
Query matrix: W [D x D ]
Q in out
Computation:
Queries: Q = XW [N x D ]
Q out
Keys: K = XW [N x D ]
K out
Values: V = XW [N x D ]
V out
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AV [N x D ]
out
Y = ∑A V
i j ij j |
| Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AV [N x D ]
out
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 48 April 24, 2025 |


### Table 2

|  |  |
|  |  |
|  |  |


---
## Page 49
---


Self-Attention Layer
Inputs:
V
Input vectors: X [N x D in ] Each input produces 1 Compute similarity
Key matrix: W [D x D ] one output, which is V between each query
K in out 2
Value matrix: W [D x D ] a mix of information and each key
V in out
V
from all inputs
Query matrix: W [D x D ] 3
Q in out
Computation:
Queries: Q = XW [N x D ] K 1 E 1,1 E 2,1 E 3,1
Q out
Keys: K = XW [N x D ]
K out K E E E
2 1,2 2,2 3,2
Values: V = XW [N x D ]
V out
K E E E
Similarities: E = QKT / 𝐷 [N x N] 3 1,3 2,3 3,3
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 1 2 3
Output vector: Y = AV [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 49 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Self-Attention Layer
Inputs:
V
Input vectors: X [N x D in ] Each input produces 1 Compute similarity
Key matrix: W [D x D ] one output, which is V between each query
K in out 2
Value matrix: W [D x D ] a mix of information and each key
V in out
V
from all inputs
Query matrix: W [D x D ] 3
Q in out
Computation:
Queries: Q = XW [N x D ] K 1 E 1,1 E 2,1 E 3,1
Q out
Keys: K = XW [N x D ]
K out K E E E
2 1,2 2,2 3,2
Values: V = XW [N x D ]
V out
K E E E
Similarities: E = QKT / 𝐷 [N x N] 3 1,3 2,3 3,3
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 1 2 3
Output vector: Y = AV [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j |
| Inputs:
Input vectors: X [N x D ] Each input produces
in
Key matrix: W [D x D ] one output, which is
K in out
Value matrix: W [D x D ] a mix of information
V in out
from all inputs
Query matrix: W [D x D ]
Q in out
Computation:
Queries: Q = XW [N x D ]
Q out
Keys: K = XW [N x D ]
K out
Values: V = XW [N x D ]
V out
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AV [N x D ]
out
Y = ∑A V
i j ij j |
| Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AV [N x D ]
out
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 49 April 24, 2025 |


### Table 2

|  |  |
|  |  |
|  |  |


---
## Page 50
---


Normalize over each column:
Self-Attention Layer
each query computes a
distribution over keys
Inputs:
V A A A
Input vectors: X [N x D ] Each input produces 1 1,1 2,1 3,1
in
Key matrix: W [D x D ] one output, which is V A A A
K in out 2 1,2 2,2 3,2
Value matrix: W [D x D ] a mix of information
V in out
Query matrix: W [D x D ] from all inputs V 3 A 1,3 A 2,3 A 3,3
Q in out
Softmax( )
Computation:
Queries: Q = XW [N x D ] K 1 E 1,1 E 2,1 E 3,1
Q out
Keys: K = XW [N x D ]
K out K E E E
2 1,2 2,2 3,2
Values: V = XW [N x D ]
V out
K E E E
Similarities: E = QKT / 𝐷 [N x N] 3 1,3 2,3 3,3
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 1 2 3
Output vector: Y = AV [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 50 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Normalize over each column:
Self-Attention Layer
each query computes a
distribution over keys
Inputs:
V A A A
Input vectors: X [N x D ] Each input produces 1 1,1 2,1 3,1
in
Key matrix: W [D x D ] one output, which is V A A A
K in out 2 1,2 2,2 3,2
Value matrix: W [D x D ] a mix of information
V in out
Query matrix: W [D x D ] from all inputs V 3 A 1,3 A 2,3 A 3,3
Q in out
Softmax( )
Computation:
Queries: Q = XW [N x D ] K 1 E 1,1 E 2,1 E 3,1
Q out
Keys: K = XW [N x D ]
K out K E E E
2 1,2 2,2 3,2
Values: V = XW [N x D ]
V out
K E E E
Similarities: E = QKT / 𝐷 [N x N] 3 1,3 2,3 3,3
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 1 2 3
Output vector: Y = AV [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j |
| Inputs:
Input vectors: X [N x D ] Each input produces
in
Key matrix: W [D x D ] one output, which is
K in out
Value matrix: W [D x D ] a mix of information
V in out
from all inputs
Query matrix: W [D x D ]
Q in out
Computation:
Queries: Q = XW [N x D ]
Q out
Keys: K = XW [N x D ]
K out
Values: V = XW [N x D ]
V out
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AV [N x D ]
out
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 50 April 24, 2025 |


### Table 2

|  |  |
|  |  |
|  |  |


---
## Page 51
---


Compute output Y Y Y
1 2 3
Self-Attention Layer
vectors as linear
combinations of Product( ), Sum( )
value vectors
Inputs:
V A A A
Input vectors: X [N x D ] Each input produces 1 1,1 2,1 3,1
in
Key matrix: W [D x D ] one output, which is V A A A
K in out 2 1,2 2,2 3,2
Value matrix: W [D x D ] a mix of information
V in out
Query matrix: W [D x D ] from all inputs V 3 A 1,3 A 2,3 A 3,3
Q in out
Softmax( )
Computation:
Queries: Q = XW [N x D ] K 1 E 1,1 E 2,1 E 3,1
Q out
Keys: K = XW [N x D ]
K out K E E E
2 1,2 2,2 3,2
Values: V = XW [N x D ]
V out
K E E E
Similarities: E = QKT / 𝐷 [N x N] 3 1,3 2,3 3,3
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 1 2 3
Output vector: Y = AV [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 51 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Compute output Y Y Y
1 2 3
Self-Attention Layer
vectors as linear
combinations of Product( ), Sum( )
value vectors
Inputs:
V A A A
Input vectors: X [N x D ] Each input produces 1 1,1 2,1 3,1
in
Key matrix: W [D x D ] one output, which is V A A A
K in out 2 1,2 2,2 3,2
Value matrix: W [D x D ] a mix of information
V in out
Query matrix: W [D x D ] from all inputs V 3 A 1,3 A 2,3 A 3,3
Q in out
Softmax( )
Computation:
Queries: Q = XW [N x D ] K 1 E 1,1 E 2,1 E 3,1
Q out
Keys: K = XW [N x D ]
K out K E E E
2 1,2 2,2 3,2
Values: V = XW [N x D ]
V out
K E E E
Similarities: E = QKT / 𝐷 [N x N] 3 1,3 2,3 3,3
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 1 2 3
Output vector: Y = AV [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j |
| com
valu
Inputs:
Input vectors: X [N x D ] Each input produces
in
Key matrix: W [D x D ] one output, which is
K in out
Value matrix: W [D x D ] a mix of information
V in out
from all inputs
Query matrix: W [D x D ]
Q in out
Computation:
Queries: Q = XW [N x D ]
Q out
Keys: K = XW [N x D ]
K out
Values: V = XW [N x D ]
V out
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AV [N x D ]
out
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 51 April 24, 2025 |


### Table 2

|  |  |
|  |  |
|  |  |


---
## Page 52
---


Self-Attention Layer
Product( ), Sum( )
Consider permuting inputs:
Inputs:
Input vectors: X [N x D ]
in
Key matrix: W [D x D ]
K in out
Value matrix: W [D x D ]
V in out
Query matrix: W [D x D ]
Q in out
Softmax( )
Computation:
Queries: Q = XW [N x D ]
Q out
Keys: K = XW [N x D ]
K out
Values: V = XW [N x D ]
V out
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AV [N x D ] X X X
out 3 1 2
Y = ∑A V
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 52 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Self-Attention Layer
Product( ), Sum( )
Consider permuting inputs:
Inputs:
Input vectors: X [N x D ]
in
Key matrix: W [D x D ]
K in out
Value matrix: W [D x D ]
V in out
Query matrix: W [D x D ]
Q in out
Softmax( )
Computation:
Queries: Q = XW [N x D ]
Q out
Keys: K = XW [N x D ]
K out
Values: V = XW [N x D ]
V out
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AV [N x D ] X X X
out 3 1 2
Y = ∑A V
i j ij j |
| Consider permuting inputs:
Inputs:
Input vectors: X [N x D ]
in
Key matrix: W [D x D ]
K in out
Value matrix: W [D x D ]
V in out
Query matrix: W [D x D ]
Q in out
Computation:
Queries: Q = XW [N x D ]
Q out
Keys: K = XW [N x D ]
K out
Values: V = XW [N x D ]
V out
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AV [N x D ]
out
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 52 April 24, 2025 |


### Table 2

|  |  |
|  |  |
|  |  |


---
## Page 53
---


Self-Attention Layer
Product( ), Sum( )
Consider permuting inputs:
Inputs:
V
Input vectors: X [N x D ] Queries, keys, and values 3
in
will be the same but permuted
Key matrix: W [D x D ] V
K in out 1
Value matrix: W [D x D ]
V in out
V
Query matrix: W [D x D ] 2
Q in out
Softmax( )
Computation:
K
Queries: Q = XW [N x D ]
3
Q out
Keys: K = XW [N x D ]
K out K
1
Values: V = XW [N x D ]
V out
K
Similarities: E = QKT / 𝐷 [N x N] 2
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 3 1 2
Output vector: Y = AV [N x D ] X X X
out 3 1 2
Y = ∑A V
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 53 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Self-Attention Layer
Product( ), Sum( )
Consider permuting inputs:
Inputs:
V
Input vectors: X [N x D ] Queries, keys, and values 3
in
will be the same but permuted
Key matrix: W [D x D ] V
K in out 1
Value matrix: W [D x D ]
V in out
V
Query matrix: W [D x D ] 2
Q in out
Softmax( )
Computation:
K
Queries: Q = XW [N x D ]
3
Q out
Keys: K = XW [N x D ]
K out K
1
Values: V = XW [N x D ]
V out
K
Similarities: E = QKT / 𝐷 [N x N] 2
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 3 1 2
Output vector: Y = AV [N x D ] X X X
out 3 1 2
Y = ∑A V
i j ij j |
| Consider permuting inputs:
Inputs:
Input vectors: X [N x D ] Queries, keys, and values
in
will be the same but permuted
Key matrix: W [D x D ]
K in out
Value matrix: W [D x D ]
V in out
Query matrix: W [D x D ]
Q in out
Computation:
Queries: Q = XW [N x D ]
Q out
Keys: K = XW [N x D ]
K out
Values: V = XW [N x D ]
V out
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AV [N x D ]
out
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 53 April 24, 2025 |


### Table 2

|  |  |
|  |  |
|  |  |


---
## Page 54
---


Self-Attention Layer
Product( ), Sum( )
Consider permuting inputs:
Inputs:
V
Input vectors: X [N x D ] Queries, keys, and values 3
in
will be the same but permuted
Key matrix: W [D x D ] V
K in out 1
Value matrix: W [D x D ]
V in out
Similarities are the same but V
Query matrix: W [D x D ] 2
Q in out permuted
Softmax( )
Computation:
Queries: Q = XW [N x D ] K 3 E 3,3 E 1,3 E 2,3
Q out
Keys: K = XW [N x D ]
K out K E E E
1 3,1 1,1 2,1
Values: V = XW [N x D ]
V out
K E E E
Similarities: E = QKT / 𝐷 [N x N] 2 3,2 1,2 2,2
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 3 1 2
Output vector: Y = AV [N x D ] X X X
out 3 1 2
Y = ∑A V
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 54 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Self-Attention Layer
Product( ), Sum( )
Consider permuting inputs:
Inputs:
V
Input vectors: X [N x D ] Queries, keys, and values 3
in
will be the same but permuted
Key matrix: W [D x D ] V
K in out 1
Value matrix: W [D x D ]
V in out
Similarities are the same but V
Query matrix: W [D x D ] 2
Q in out permuted
Softmax( )
Computation:
Queries: Q = XW [N x D ] K 3 E 3,3 E 1,3 E 2,3
Q out
Keys: K = XW [N x D ]
K out K E E E
1 3,1 1,1 2,1
Values: V = XW [N x D ]
V out
K E E E
Similarities: E = QKT / 𝐷 [N x N] 2 3,2 1,2 2,2
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 3 1 2
Output vector: Y = AV [N x D ] X X X
out 3 1 2
Y = ∑A V
i j ij j |
| Consider permuting inputs:
Inputs:
Input vectors: X [N x D ] Queries, keys, and values
in
will be the same but permuted
Key matrix: W [D x D ]
K in out
Value matrix: W [D x D ]
V in out
Similarities are the same but
Query matrix: W [D x D ]
Q in out permuted
Computation:
Queries: Q = XW [N x D ]
Q out
Keys: K = XW [N x D ]
K out
Values: V = XW [N x D ]
V out
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AV [N x D ]
out
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 54 April 24, 2025 |


### Table 2

|  |  |
|  |  |
|  |  |


---
## Page 55
---


Self-Attention Layer
Product( ), Sum( )
Consider permuting inputs:
Inputs:
V A A A
Input vectors: X [N x D ] Queries, keys, and values 3 3,3 1,3 2,3
in
will be the same but permuted
Key matrix: W [D x D ] V A A A
K in out 1 3,1 1,1 2,1
Value matrix: W [D x D ]
V in out
Similarities are the same but V A A A
Query matrix: W [D x D ] 2 3,2 1,2 2,2
Q in out permuted
Softmax( )
Computation:
Attention weights are the
Queries: Q = XW [N x D ] same but permuted K 3 E 3,3 E 1,3 E 2,3
Q out
Keys: K = XW [N x D ]
K out K E E E
1 3,1 1,1 2,1
Values: V = XW [N x D ]
V out
K E E E
Similarities: E = QKT / 𝐷 [N x N] 2 3,2 1,2 2,2
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 3 1 2
Output vector: Y = AV [N x D ] X X X
out 3 1 2
Y = ∑A V
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 55 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Self-Attention Layer
Product( ), Sum( )
Consider permuting inputs:
Inputs:
V A A A
Input vectors: X [N x D ] Queries, keys, and values 3 3,3 1,3 2,3
in
will be the same but permuted
Key matrix: W [D x D ] V A A A
K in out 1 3,1 1,1 2,1
Value matrix: W [D x D ]
V in out
Similarities are the same but V A A A
Query matrix: W [D x D ] 2 3,2 1,2 2,2
Q in out permuted
Softmax( )
Computation:
Attention weights are the
Queries: Q = XW [N x D ] same but permuted K 3 E 3,3 E 1,3 E 2,3
Q out
Keys: K = XW [N x D ]
K out K E E E
1 3,1 1,1 2,1
Values: V = XW [N x D ]
V out
K E E E
Similarities: E = QKT / 𝐷 [N x N] 2 3,2 1,2 2,2
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 3 1 2
Output vector: Y = AV [N x D ] X X X
out 3 1 2
Y = ∑A V
i j ij j |
| Consider permuting inputs:
Inputs:
Input vectors: X [N x D ] Queries, keys, and values
in
will be the same but permuted
Key matrix: W [D x D ]
K in out
Value matrix: W [D x D ]
V in out
Similarities are the same but
Query matrix: W [D x D ]
Q in out permuted
Computation:
Attention weights are the
Queries: Q = XW [N x D ] same but permuted
Q out
Keys: K = XW [N x D ]
K out
Values: V = XW [N x D ]
V out
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AV [N x D ]
out
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 55 April 24, 2025 |


### Table 2

|  |  |
|  |  |
|  |  |


---
## Page 56
---


Y Y Y
3 1 2
Self-Attention Layer
Product( ), Sum( )
Consider permuting inputs:
Inputs:
V A A A
Input vectors: X [N x D ] Queries, keys, and values 3 3,3 1,3 2,3
in
will be the same but permuted
Key matrix: W [D x D ] V A A A
K in out 1 3,1 1,1 2,1
Value matrix: W [D x D ]
V in out
Similarities are the same but V A A A
Query matrix: W [D x D ] 2 3,2 1,2 2,2
Q in out permuted
Softmax( )
Computation:
Attention weights are the
Queries: Q = XW [N x D ] same but permuted K 3 E 3,3 E 1,3 E 2,3
Q out
Keys: K = XW [N x D ]
K out K E E E
1 3,1 1,1 2,1
Values: V = XW [N x D ] Outputs are the same but
V out
permuted K E E E
Similarities: E = QKT / 𝐷 [N x N] 2 3,2 1,2 2,2
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 3 1 2
Output vector: Y = AV [N x D ] X X X
out 3 1 2
Y = ∑A V
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 56 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Y Y Y
3 1 2
Self-Attention Layer
Product( ), Sum( )
Consider permuting inputs:
Inputs:
V A A A
Input vectors: X [N x D ] Queries, keys, and values 3 3,3 1,3 2,3
in
will be the same but permuted
Key matrix: W [D x D ] V A A A
K in out 1 3,1 1,1 2,1
Value matrix: W [D x D ]
V in out
Similarities are the same but V A A A
Query matrix: W [D x D ] 2 3,2 1,2 2,2
Q in out permuted
Softmax( )
Computation:
Attention weights are the
Queries: Q = XW [N x D ] same but permuted K 3 E 3,3 E 1,3 E 2,3
Q out
Keys: K = XW [N x D ]
K out K E E E
1 3,1 1,1 2,1
Values: V = XW [N x D ] Outputs are the same but
V out
permuted K E E E
Similarities: E = QKT / 𝐷 [N x N] 2 3,2 1,2 2,2
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 3 1 2
Output vector: Y = AV [N x D ] X X X
out 3 1 2
Y = ∑A V
i j ij j |
| Consider permuting inputs:
Inputs:
Input vectors: X [N x D ] Queries, keys, and values
in
will be the same but permuted
Key matrix: W [D x D ]
K in out
Value matrix: W [D x D ]
V in out
Similarities are the same but
Query matrix: W [D x D ]
Q in out permuted
Computation:
Attention weights are the
Queries: Q = XW [N x D ] same but permuted
Q out
Keys: K = XW [N x D ]
K out
Values: V = XW [N x D ] Outputs are the same but
V out
permuted
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AV [N x D ]
out
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 56 April 24, 2025 |


### Table 2

|  |  |
|  |  |
|  |  |


---
## Page 57
---


Y Y Y
3 1 2
Self-Attention Layer
Product( ), Sum( )
Inputs:
V A A A
Input vectors: X [N x D ] 3 3,3 1,3 2,3
in
Key matrix: W [D x D ] Self-Attention is V A A A
K in out 1 3,1 1,1 2,1
Value matrix: W [D x D ] permutation equivariant:
V in out
V A A A
Query matrix: W [D x D ] F(σ(X)) = σ(F(X)) 2 3,2 1,2 2,2
Q in out
Softmax( )
Computation: This means that Self-Attention
Queries: Q = XW [N x D ] works on sets of vectors K 3 E 3,3 E 1,3 E 2,3
Q out
Keys: K = XW [N x D ]
K out K E E E
1 3,1 1,1 2,1
Values: V = XW [N x D ]
V out
K E E E
Similarities: E = QKT / 𝐷 [N x N] 2 3,2 1,2 2,2
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 3 1 2
Output vector: Y = AV [N x D ] X X X
out 3 1 2
Y = ∑A V
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 57 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Y Y Y
3 1 2
Self-Attention Layer
Product( ), Sum( )
Inputs:
V A A A
Input vectors: X [N x D ] 3 3,3 1,3 2,3
in
Key matrix: W [D x D ] Self-Attention is V A A A
K in out 1 3,1 1,1 2,1
Value matrix: W [D x D ] permutation equivariant:
V in out
V A A A
Query matrix: W [D x D ] F(σ(X)) = σ(F(X)) 2 3,2 1,2 2,2
Q in out
Softmax( )
Computation: This means that Self-Attention
Queries: Q = XW [N x D ] works on sets of vectors K 3 E 3,3 E 1,3 E 2,3
Q out
Keys: K = XW [N x D ]
K out K E E E
1 3,1 1,1 2,1
Values: V = XW [N x D ]
V out
K E E E
Similarities: E = QKT / 𝐷 [N x N] 2 3,2 1,2 2,2
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 3 1 2
Output vector: Y = AV [N x D ] X X X
out 3 1 2
Y = ∑A V
i j ij j |
| Inputs:
Input vectors: X [N x D ]
in
Key matrix: W [D x D ] Self-Attention is
K in out
Value matrix: W [D x D ] permutation equivariant:
V in out
Query matrix: W [D x D ] F(σ(X)) = σ(F(X))
Q in out
Computation: This means that Self-Attention
Queries: Q = XW [N x D ] works on sets of vectors
Q out
Keys: K = XW [N x D ]
K out
Values: V = XW [N x D ]
V out
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AV [N x D ]
out
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 57 April 24, 2025 |


### Table 2

|  |  |
|  |  |
|  |  |


---
## Page 58
---


Y Y Y
1 2 3
Self-Attention Layer
Product( ), Sum( )
Inputs:
V A A A
Input vectors: X [N x D ] Problem: Self-Attention 1 1,1 2,1 3,1
in
Key matrix: W [D x D ] does not know the order of V A A A
K in out 2 1,2 2,2 3,2
Value matrix: W [D x D ] the sequence
V in out
V A A A
Query matrix: W [D x D ] 3 1,3 2,3 3,3
Q in out
Softmax( )
Computation:
Queries: Q = XW [N x D ] K 1 E 1,1 E 2,1 E 3,1
Q out
Keys: K = XW [N x D ]
K out K E E E
2 1,2 2,2 3,2
Values: V = XW [N x D ]
V out
K E E E
Similarities: E = QKT / 𝐷 [N x N] 3 1,3 2,3 3,3
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 1 2 3
Output vector: Y = AV [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 58 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Y Y Y
1 2 3
Self-Attention Layer
Product( ), Sum( )
Inputs:
V A A A
Input vectors: X [N x D ] Problem: Self-Attention 1 1,1 2,1 3,1
in
Key matrix: W [D x D ] does not know the order of V A A A
K in out 2 1,2 2,2 3,2
Value matrix: W [D x D ] the sequence
V in out
V A A A
Query matrix: W [D x D ] 3 1,3 2,3 3,3
Q in out
Softmax( )
Computation:
Queries: Q = XW [N x D ] K 1 E 1,1 E 2,1 E 3,1
Q out
Keys: K = XW [N x D ]
K out K E E E
2 1,2 2,2 3,2
Values: V = XW [N x D ]
V out
K E E E
Similarities: E = QKT / 𝐷 [N x N] 3 1,3 2,3 3,3
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 1 2 3
Output vector: Y = AV [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j |
| Inputs:
Input vectors: X [N x D ] Problem: Self-Attention
in
Key matrix: W [D x D ] does not know the order of
K in out
Value matrix: W [D x D ] the sequence
V in out
Query matrix: W [D x D ]
Q in out
Computation:
Queries: Q = XW [N x D ]
Q out
Keys: K = XW [N x D ]
K out
Values: V = XW [N x D ]
V out
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AV [N x D ]
out
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 58 April 24, 2025 |


---
## Page 59
---


Y Y Y
1 2 3
Self-Attention Layer
Product( ), Sum( )
Inputs:
V A A A
Input vectors: X [N x D ] Problem: Self-Attention 1 1,1 2,1 3,1
in
Key matrix: W [D x D ] does not know the order of V A A A
K in out 2 1,2 2,2 3,2
Value matrix: W [D x D ] the sequence
V in out
V A A A
Query matrix: W [D x D ] 3 1,3 2,3 3,3
Q in out
Solution: Add positional
Softmax( )
Computation: encoding to each input; this
Queries: Q = XW [N x D ] is a vector that is a fixed K 1 E 1,1 E 2,1 E 3,1
Q out
Keys: K = XW [N x D ] function of the index
K out K E E E
2 1,2 2,2 3,2
Values: V = XW [N x D ]
V out
K E E E
Similarities: E = QKT / 𝐷 [N x N] 3 1,3 2,3 3,3
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 1 2 3
Output vector: Y = AV [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j E(1) E(2) E(3)
Stanford CS231n 10th Anniversary Lecture 8 - 59 April 24, 2025

[Page contains 4 table(s)]


### Table 1

| Y Y Y
1 2 3
Self-Attention Layer
Product( ), Sum( )
Inputs:
V A A A
Input vectors: X [N x D ] Problem: Self-Attention 1 1,1 2,1 3,1
in
Key matrix: W [D x D ] does not know the order of V A A A
K in out 2 1,2 2,2 3,2
Value matrix: W [D x D ] the sequence
V in out
V A A A
Query matrix: W [D x D ] 3 1,3 2,3 3,3
Q in out
Solution: Add positional
Softmax( )
Computation: encoding to each input; this
Queries: Q = XW [N x D ] is a vector that is a fixed K 1 E 1,1 E 2,1 E 3,1
Q out
Keys: K = XW [N x D ] function of the index
K out K E E E
2 1,2 2,2 3,2
Values: V = XW [N x D ]
V out
K E E E
Similarities: E = QKT / 𝐷 [N x N] 3 1,3 2,3 3,3
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 1 2 3
Output vector: Y = AV [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j E(1) E(2) E(3) |
| Inputs:
Input vectors: X [N x D ] Problem: Self-Attention
in
Key matrix: W [D x D ] does not know the order of
K in out
Value matrix: W [D x D ] the sequence
V in out
Query matrix: W [D x D ]
Q in out
Solution: Add positional
Computation: encoding to each input; this
Queries: Q = XW [N x D ] is a vector that is a fixed
Q out
Keys: K = XW [N x D ] function of the index
K out
Values: V = XW [N x D ]
V out
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AV [N x D ]
out
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 59 April 24, 2025 |


### Table 2

| X
1 |
| E(1) |


### Table 3

| X
2 |
| E(2) |


### Table 4

| X
3 |
| E(3) |


---
## Page 60
---


Y Y Y
1 2 3
Masked Self-Attention Layer
Product( ), Sum( )
Don’t let vectors “look ahead” in the sequence
Inputs:
V A A A
Input vectors: X [N x D ] 1 1,1 2,1 3,1
in
Override similarities with -inf;
Key matrix: W [D x D ] V 0 A A
K in out this controls which inputs each 2 2,2 3,2
Value matrix: W [D x D ]
V in out
vector is allowed to look at. V 0 0 A
Query matrix: W [D x D ] 3 3,3
Q in out
Softmax( )
Computation:
Queries: Q = XW [N x D ] K 1 E 1,1 E 2,1 E 3,1
Q out
Keys: K = XW [N x D ]
K out K -∞ E E
2 2,2 3,2
Values: V = XW [N x D ]
V out
K -∞ -∞ E
Similarities: E = QKT / 𝐷 [N x N] 3 3,3
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 1 2 3
Output vector: Y = AV [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 60 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Y Y Y
1 2 3
Masked Self-Attention Layer
Product( ), Sum( )
Don’t let vectors “look ahead” in the sequence
Inputs:
V A A A
Input vectors: X [N x D ] 1 1,1 2,1 3,1
in
Override similarities with -inf;
Key matrix: W [D x D ] V 0 A A
K in out this controls which inputs each 2 2,2 3,2
Value matrix: W [D x D ]
V in out
vector is allowed to look at. V 0 0 A
Query matrix: W [D x D ] 3 3,3
Q in out
Softmax( )
Computation:
Queries: Q = XW [N x D ] K 1 E 1,1 E 2,1 E 3,1
Q out
Keys: K = XW [N x D ]
K out K -∞ E E
2 2,2 3,2
Values: V = XW [N x D ]
V out
K -∞ -∞ E
Similarities: E = QKT / 𝐷 [N x N] 3 3,3
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 1 2 3
Output vector: Y = AV [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j |
| Don’t let vectors “look ahead” in the sequence
Inputs:
Input vectors: X [N x D ]
in
Override similarities with -inf;
Key matrix: W [D x D ]
K in out this controls which inputs eac
Value matrix: W [D x D ]
V in out
vector is allowed to look at.
Query matrix: W [D x D ]
Q in out
Computation:
Queries: Q = XW [N x D ]
Q out
Keys: K = XW [N x D ]
K out
Values: V = XW [N x D ]
V out
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AV [N x D ]
out
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 60 April 24, 2025 |


---
## Page 61
---


is very cool
Masked Self-Attention Layer
Product( ), Sum( )
Don’t let vectors “look ahead” in the sequence
Inputs:
V A A A
Input vectors: X [N x D ] 1 1,1 2,1 3,1
in
Override similarities with -inf;
Key matrix: W [D x D ] V 0 A A
K in out this controls which inputs each 2 2,2 3,2
Value matrix: W [D x D ]
V in out
vector is allowed to look at. V 0 0 A
Query matrix: W [D x D ] 3 3,3
Q in out
Softmax( )
Used for language modeling
Computation:
where you want to predict the
Queries: Q = XW [N x D ] K 1 E 1,1 E 2,1 E 3,1
Q out next word
Keys: K = XW [N x D ]
K out K -∞ E E
2 2,2 3,2
Values: V = XW [N x D ]
V out
K -∞ -∞ E
Similarities: E = QKT / 𝐷 [N x N] 3 3,3
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 1 2 3
Output vector: Y = AV [N x D ]
out Attention is very
Y = ∑A V
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 61 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| is very cool
Masked Self-Attention Layer
Product( ), Sum( )
Don’t let vectors “look ahead” in the sequence
Inputs:
V A A A
Input vectors: X [N x D ] 1 1,1 2,1 3,1
in
Override similarities with -inf;
Key matrix: W [D x D ] V 0 A A
K in out this controls which inputs each 2 2,2 3,2
Value matrix: W [D x D ]
V in out
vector is allowed to look at. V 0 0 A
Query matrix: W [D x D ] 3 3,3
Q in out
Softmax( )
Used for language modeling
Computation:
where you want to predict the
Queries: Q = XW [N x D ] K 1 E 1,1 E 2,1 E 3,1
Q out next word
Keys: K = XW [N x D ]
K out K -∞ E E
2 2,2 3,2
Values: V = XW [N x D ]
V out
K -∞ -∞ E
Similarities: E = QKT / 𝐷 [N x N] 3 3,3
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Q Q Q
Attention weights: A = softmax(E, dim=1) [N x N] 1 2 3
Output vector: Y = AV [N x D ]
out Attention is very
Y = ∑A V
i j ij j |
| Don’t let vectors “look ahead” in the sequence
Inputs:
Input vectors: X [N x D ]
in
Override similarities with -inf;
Key matrix: W [D x D ]
K in out this controls which inputs eac
Value matrix: W [D x D ]
V in out
vector is allowed to look at.
Query matrix: W [D x D ]
Q in out
Used for language modeling
Computation:
where you want to predict the
Queries: Q = XW [N x D ]
Q out next word
Keys: K = XW [N x D ]
K out
Values: V = XW [N x D ]
V out
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AV [N x D ]
out
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 61 April 24, 2025 |


---
## Page 62
---


Multiheaded Self-Attention Layer
Run H copies of Self-Attention in parallel
Inputs:
Input vectors: X [N x D ]
in
Key matrix: W [D x D ]
K in out
Value matrix: W [D x D ]
V in out
Query matrix: W [D x D ]
Q in out
Computation:
Queries: Q = XW [N x D ]
Q out
Keys: K = XW [N x D ]
K out
Values: V = XW [N x D ]
V out
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AX [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 62 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Multiheaded Self-Attention Layer
Run H copies of Self-Attention in parallel
Inputs:
Input vectors: X [N x D ]
in
Key matrix: W [D x D ]
K in out
Value matrix: W [D x D ]
V in out
Query matrix: W [D x D ]
Q in out
Computation:
Queries: Q = XW [N x D ]
Q out
Keys: K = XW [N x D ]
K out
Values: V = XW [N x D ]
V out
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AX [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j |
| Run H copies of Self-Attention in parallel
Inputs:
Input vectors: X [N x D ]
in
Key matrix: W [D x D ]
K in out
Value matrix: W [D x D ]
V in out
Query matrix: W [D x D ]
Q in out
Computation:
Queries: Q = XW [N x D ]
Q out
Keys: K = XW [N x D ]
K out
Values: V = XW [N x D ]
V out
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AX [N x D ]
out
Y = ∑A V
i j ij j |
| Inputs:
Input vectors: X [N x D ]
in
Key matrix: W [D x D ]
K in out
Value matrix: W [D x D ]
V in out
Query matrix: W [D x D ]
Q in out
Computation:
Queries: Q = XW [N x D ]
Q out
Keys: K = XW [N x D ]
K out
Values: V = XW [N x D ]
V out
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E,
Output vector: Y = AX [N x D ]
out
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 62 April 24, 2025 |


---
## Page 63
---


Multiheaded Self-Attention Layer
Run H copies of Self-Attention in parallel
Inputs:
Input vectors: X [N x D ]
in
Key matrix: W [D x D ]
K in out
Value matrix: W [D x D ]
V in out
Query matrix: W [D x D ]
Q in out
Computation:
Queries: Q = XW [N x D ]
Q out H = 3 independent
Keys: K = XW [N x D ]
K out self-attention layers
Values: V = XW [N x D ]
V out (called heads), each
Similarities: E = QKT / 𝐷 [N x N]
𝑄 with their own weights
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AX [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 63 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Multiheaded Self-Attention Layer
Run H copies of Self-Attention in parallel
Inputs:
Input vectors: X [N x D ]
in
Key matrix: W [D x D ]
K in out
Value matrix: W [D x D ]
V in out
Query matrix: W [D x D ]
Q in out
Computation:
Queries: Q = XW [N x D ]
Q out H = 3 independent
Keys: K = XW [N x D ]
K out self-attention layers
Values: V = XW [N x D ]
V out (called heads), each
Similarities: E = QKT / 𝐷 [N x N]
𝑄 with their own weights
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AX [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j |
| Run H copies of Self-Attention in parallel
Inputs:
Input vectors: X [N x D ]
in
Key matrix: W [D x D ]
K in out
Value matrix: W [D x D ]
V in out
Query matrix: W [D x D ]
Q in out
Computation:
Queries: Q = XW [N x D ]
Q out H = 3 independent
Keys: K = XW [N x D ]
K out self-attention layers
Values: V = XW [N x D ]
V out (called heads), each
Similarities: E = QKT / 𝐷 [N x N]
𝑄 with their own weights
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AX [N x D ]
out
Y = ∑A V
i j ij j |
| Inputs:
Input vectors: X [N x D ]
in
Key matrix: W [D x D ]
K in out
Value matrix: W [D x D ]
V in out
Query matrix: W [D x D ]
Q in out
Computation:
Queries: Q = XW [N x D ]
Q out
Keys: K = XW [N x D ]
K out
Values: V = XW [N x D ]
V out
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E,
Output vector: Y = AX [N x D ]
out
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 63 April 24, 2025 |


[Page contains 3 image(s)]


---
## Page 64
---


Multiheaded Self-Attention Layer
Run H copies of Self-Attention in parallel
Inputs:
Input vectors: X [N x D ]
in
Key matrix: W [D x D ]
K in out
Value matrix: W [D x D ]
Stack up the H
V in out Y Y Y
1,1 2,1 3,1
Query matrix: W [D x D ]
Q in out independent outputs Y Y Y
1,2 2,2 3,2
for each input X Y Y Y
1,3 2,3 3,3
Computation:
Queries: Q = XW [N x D ]
Q out H = 3 independent
Keys: K = XW [N x D ]
K out self-attention layers
Values: V = XW [N x D ]
V out (called heads), each
Similarities: E = QKT / 𝐷 [N x N]
𝑄 with their own weights
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AX [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 64 April 24, 2025

[Page contains 4 table(s)]


### Table 1

| Multiheaded Self-Attention Layer
Run H copies of Self-Attention in parallel
Inputs:
Input vectors: X [N x D ]
in
Key matrix: W [D x D ]
K in out
Value matrix: W [D x D ]
Stack up the H
V in out Y Y Y
1,1 2,1 3,1
Query matrix: W [D x D ]
Q in out independent outputs Y Y Y
1,2 2,2 3,2
for each input X Y Y Y
1,3 2,3 3,3
Computation:
Queries: Q = XW [N x D ]
Q out H = 3 independent
Keys: K = XW [N x D ]
K out self-attention layers
Values: V = XW [N x D ]
V out (called heads), each
Similarities: E = QKT / 𝐷 [N x N]
𝑄 with their own weights
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AX [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j |
| Run H copies of Self-Attention in parallel
Inputs:
Input vectors: X [N x D ]
in
Key matrix: W [D x D ]
K in out
Value matrix: W [D x D ]
Stack up the H
V in out
Query matrix: W [D x D ]
independent outputs
Q in out
for each input X
Computation:
Queries: Q = XW [N x D ]
Q out H = 3 independent
Keys: K = XW [N x D ]
K out self-attention layers
Values: V = XW [N x D ]
V out (called heads), each
Similarities: E = QKT / 𝐷 [N x N]
𝑄 with their own weights
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AX [N x D ]
out
Y = ∑A V
i j ij j |
| Inputs:
Input vectors: X [N x D ]
in
Key matrix: W [D x D ]
K in out
Value matrix: W [D x D ]
V in out
Query matrix: W [D x D ]
Q in out
Computation:
Queries: Q = XW [N x D ]
Q out
Keys: K = XW [N x D ]
K out
Values: V = XW [N x D ]
V out
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E,
Output vector: Y = AX [N x D ]
out
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 64 April 24, 2025 |


### Table 2

| Y
1,1 |
| Y
1,2 |
| Y
1,3 |


### Table 3

| Y
2,1 |
| Y
2,2 |
| Y
2,3 |


### Table 4

| Y
3,1 |
| Y
3,2 |
| Y
3,3 |


[Page contains 3 image(s)]


---
## Page 65
---


Multiheaded Self-Attention Layer
Run H copies of Self-Attention in parallel
O O O
Inputs: Output projection fuses 1 2 3
Input vectors: X [N x D ] data from each head
in
Key matrix: W [D x D ]
K in out
Value matrix: W [D x D ]
Stack up the H
V in out Y Y Y
1,1 2,1 3,1
Query matrix: W [D x D ]
Q in out independent outputs Y Y Y
1,2 2,2 3,2
for each input X Y Y Y
1,3 2,3 3,3
Computation:
Queries: Q = XW [N x D ]
Q out H = 3 independent
Keys: K = XW [N x D ]
K out self-attention layers
Values: V = XW [N x D ]
V out (called heads), each
Similarities: E = QKT / 𝐷 [N x N]
𝑄 with their own weights
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AX [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j
Stanford CS231n 10th Anniversary Lecture 8 - 65 April 24, 2025

[Page contains 4 table(s)]


### Table 1

| Multiheaded Self-Attention Layer
Run H copies of Self-Attention in parallel
O O O
Inputs: Output projection fuses 1 2 3
Input vectors: X [N x D ] data from each head
in
Key matrix: W [D x D ]
K in out
Value matrix: W [D x D ]
Stack up the H
V in out Y Y Y
1,1 2,1 3,1
Query matrix: W [D x D ]
Q in out independent outputs Y Y Y
1,2 2,2 3,2
for each input X Y Y Y
1,3 2,3 3,3
Computation:
Queries: Q = XW [N x D ]
Q out H = 3 independent
Keys: K = XW [N x D ]
K out self-attention layers
Values: V = XW [N x D ]
V out (called heads), each
Similarities: E = QKT / 𝐷 [N x N]
𝑄 with their own weights
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AX [N x D ] X X X
out 1 2 3
Y = ∑A V
i j ij j |
| Run H copies of Self-Attention in parallel
Inputs: Output projection fuses
Input vectors: X [N x D ] data from each head
in
Key matrix: W [D x D ]
K in out
Value matrix: W [D x D ]
Stack up the H
V in out
Query matrix: W [D x D ]
independent outputs
Q in out
for each input X
Computation:
Queries: Q = XW [N x D ]
Q out H = 3 independent
Keys: K = XW [N x D ]
K out self-attention layers
Values: V = XW [N x D ]
V out (called heads), each
Similarities: E = QKT / 𝐷 [N x N]
𝑄 with their own weights
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E, dim=1) [N x N]
Output vector: Y = AX [N x D ]
out
Y = ∑A V
i j ij j |
| Inputs:
Input vectors: X [N x D ]
in
Key matrix: W [D x D ]
K in out
Value matrix: W [D x D ]
V in out
Query matrix: W [D x D ]
Q in out
Computation:
Queries: Q = XW [N x D ]
Q out
Keys: K = XW [N x D ]
K out
Values: V = XW [N x D ]
V out
Similarities: E = QKT / 𝐷 [N x N]
𝑄
E = Q ·K / 𝐷
ij i j 𝑄
Attention weights: A = softmax(E,
Output vector: Y = AX [N x D ]
out
Y = ∑A V
i j ij j |
| Stanford CS231n 10th Anniversary Lecture 8 - 65 April 24, 2025 |


### Table 2

| Y
1,1 |
| Y
1,2 |
| Y
1,3 |


### Table 3

| Y
2,1 |
| Y
2,2 |
| Y
2,3 |


### Table 4

| Y
3,1 |
| Y
3,2 |
| Y
3,3 |


[Page contains 3 image(s)]


---
## Page 66
---


Multiheaded Self-Attention Layer
Run H copies of Self-Attention in parallel
O O O
Inputs: 1 2 3
Input vectors: X [N x D] Each of the H parallel
Key matrix: W [D x HD ] layers use a qkv dim of
K H
Value matrix: W [D x HD ] D = “head dim”
V H H
Y Y Y
1,1 2,1 3,1
Query matrix: W [D x HD ]
Q H Y Y Y
1,2 2,2 3,2
Output matrix: W [HD x D] Usually D = D / H, so
O H H Y Y Y
1,3 2,3 3,3
inputs and outputs have
Computation: the same dimension
Queries: Q = XW [H x N x D ]
Q H
Keys: K = XW [H x N x D ]
K H
Values: V = XW [H x N x D ]
V H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Attention weights: A = softmax(E, dim=2) [H x N x N]
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H X X X
1 2 3
Outputs: O = YW [N x D]
O
Stanford CS231n 10th Anniversary Lecture 8 - 66 April 24, 2025

[Page contains 4 table(s)]


### Table 1

| Multiheaded Self-Attention Layer
Run H copies of Self-Attention in parallel
O O O
Inputs: 1 2 3
Input vectors: X [N x D] Each of the H parallel
Key matrix: W [D x HD ] layers use a qkv dim of
K H
Value matrix: W [D x HD ] D = “head dim”
V H H
Y Y Y
1,1 2,1 3,1
Query matrix: W [D x HD ]
Q H Y Y Y
1,2 2,2 3,2
Output matrix: W [HD x D] Usually D = D / H, so
O H H Y Y Y
1,3 2,3 3,3
inputs and outputs have
Computation: the same dimension
Queries: Q = XW [H x N x D ]
Q H
Keys: K = XW [H x N x D ]
K H
Values: V = XW [H x N x D ]
V H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Attention weights: A = softmax(E, dim=2) [H x N x N]
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H X X X
1 2 3
Outputs: O = YW [N x D]
O |
| Run H copies of Self-Attention in parallel
Inputs:
Input vectors: X [N x D] Each of the H parallel
Key matrix: W [D x HD ] layers use a qkv dim of
K H
Value matrix: W [D x HD ] D = “head dim”
V H H
Query matrix: W [D x HD ]
Q H
Output matrix: W [HD x D] Usually D = D / H, so
O H H
inputs and outputs have
Computation: the same dimension
Queries: Q = XW [H x N x D ]
Q H
Keys: K = XW [H x N x D ]
K H
Values: V = XW [H x N x D ]
V H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Attention weights: A = softmax(E, dim=2) [H x N x N]
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H
Outputs: O = YW [N x D]
O |
| Stanford CS231n 10th Anniversary Lecture 8 - 66 April 24, 2025 |


### Table 2

| Y
1,1 |
| Y
1,2 |
| Y
1,3 |


### Table 3

| Y
2,1 |
| Y
2,2 |
| Y
2,3 |


### Table 4

| Y
3,1 |
| Y
3,2 |
| Y
3,3 |


[Page contains 3 image(s)]


---
## Page 67
---


Multiheaded Self-Attention Layer
Run H copies of Self-Attention in parallel
O O O
Inputs: 1 2 3
Input vectors: X [N x D]
In practice, compute
Key matrix: W [D x HD ]
K H
all H heads in parallel
Value matrix: W [D x HD ]
V H
using batched matrix Y 1,1 Y 2,1 Y 3,1
Query matrix: W [D x HD ]
Q H Y Y Y
multiply operations. 1,2 2,2 3,2
Output matrix: W [HD x D]
O H Y Y Y
1,3 2,3 3,3
Used everywhere in
Computation:
practice.
Queries: Q = XW [H x N x D ]
Q H
Keys: K = XW [H x N x D ]
K H
Values: V = XW [H x N x D ]
V H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Attention weights: A = softmax(E, dim=2) [H x N x N]
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H X X X
1 2 3
Outputs: O = YW [N x D]
O
Stanford CS231n 10th Anniversary Lecture 8 - 67 April 24, 2025

[Page contains 4 table(s)]


### Table 1

| Multiheaded Self-Attention Layer
Run H copies of Self-Attention in parallel
O O O
Inputs: 1 2 3
Input vectors: X [N x D]
In practice, compute
Key matrix: W [D x HD ]
K H
all H heads in parallel
Value matrix: W [D x HD ]
V H
using batched matrix Y 1,1 Y 2,1 Y 3,1
Query matrix: W [D x HD ]
Q H Y Y Y
multiply operations. 1,2 2,2 3,2
Output matrix: W [HD x D]
O H Y Y Y
1,3 2,3 3,3
Used everywhere in
Computation:
practice.
Queries: Q = XW [H x N x D ]
Q H
Keys: K = XW [H x N x D ]
K H
Values: V = XW [H x N x D ]
V H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Attention weights: A = softmax(E, dim=2) [H x N x N]
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H X X X
1 2 3
Outputs: O = YW [N x D]
O |
| Run H copies of Self-Attention in parallel
Inputs:
Input vectors: X [N x D]
In practice, compute
Key matrix: W [D x HD ]
K H
all H heads in parallel
Value matrix: W [D x HD ]
V H
using batched matrix
Query matrix: W [D x HD ]
Q H
multiply operations.
Output matrix: W [HD x D]
O H
Used everywhere in
Computation:
practice.
Queries: Q = XW [H x N x D ]
Q H
Keys: K = XW [H x N x D ]
K H
Values: V = XW [H x N x D ]
V H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Attention weights: A = softmax(E, dim=2) [H x N x N]
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H
Outputs: O = YW [N x D]
O |
| Stanford CS231n 10th Anniversary Lecture 8 - 67 April 24, 2025 |


### Table 2

| Y
1,1 |
| Y
1,2 |
| Y
1,3 |


### Table 3

| Y
2,1 |
| Y
2,2 |
| Y
2,3 |


### Table 4

| Y
3,1 |
| Y
3,2 |
| Y
3,3 |


[Page contains 3 image(s)]


---
## Page 68
---


Self-Attention is Four Matrix Multiplies!
Inputs:
Input vectors: X [N x D]
Key matrix: W [D x HD ]
K H
Value matrix: W [D x HD ]
V H
Query matrix: W [D x HD ]
Q H
Output matrix: W [HD x D]
O H
Computation:
Queries: Q = XW [H x N x D ]
Q H
Keys: K = XW [H x N x D ]
K H
Values: V = XW [H x N x D ]
V H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Attention weights: A = softmax(E, dim=2) [H x N x N]
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H
Outputs: O = YW [N x D]
O
Stanford CS231n 10th Anniversary Lecture 8 - 68 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Self-Attention is Four Matrix Multiplies!
Inputs:
Input vectors: X [N x D]
Key matrix: W [D x HD ]
K H
Value matrix: W [D x HD ]
V H
Query matrix: W [D x HD ]
Q H
Output matrix: W [HD x D]
O H
Computation:
Queries: Q = XW [H x N x D ]
Q H
Keys: K = XW [H x N x D ]
K H
Values: V = XW [H x N x D ]
V H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Attention weights: A = softmax(E, dim=2) [H x N x N]
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H
Outputs: O = YW [N x D]
O |
| Inputs:
Input vectors: X [N x D]
Key matrix: W [D x HD ]
K H
Value matrix: W [D x HD ]
V H
Query matrix: W [D x HD ]
Q H
Output matrix: W [HD x D]
O H
Computation:
Queries: Q = XW [H x N x D ]
Q H
Keys: K = XW [H x N x D ]
K H
Values: V = XW [H x N x D ]
V H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Attention weights: A = softmax(E, dim=2) [H x N x N]
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H
Outputs: O = YW [N x D]
O |
| Stanford CS231n 10th Anniversary Lecture 8 - 68 April 24, 2025 |


---
## Page 69
---


Self-Attention is Four Matrix Multiplies!
Inputs: 1. QKV Projection
Input vectors: X [N x D] [N x D] [D x 3HD ] => [N x 3HD ]
H H
Key matrix: W [D x HD ] Split and reshape to get Q, K, V each of
K H
Value matrix: W [D x HD ] shape [H x N x D ]
V H H
Query matrix: W [D x HD ]
Q H
Output matrix: W [HD x D]
O H
Computation:
Queries: Q = XW [H x N x D ]
Q H
Keys: K = XW [H x N x D ]
K H
Values: V = XW [H x N x D ]
V H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Attention weights: A = softmax(E, dim=2) [H x N x N]
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H
Outputs: O = YW [N x D]
O
Stanford CS231n 10th Anniversary Lecture 8 - 69 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Self-Attention is Four Matrix Multiplies!
Inputs: 1. QKV Projection
Input vectors: X [N x D] [N x D] [D x 3HD ] => [N x 3HD ]
H H
Key matrix: W [D x HD ] Split and reshape to get Q, K, V each of
K H
Value matrix: W [D x HD ] shape [H x N x D ]
V H H
Query matrix: W [D x HD ]
Q H
Output matrix: W [HD x D]
O H
Computation:
Queries: Q = XW [H x N x D ]
Q H
Keys: K = XW [H x N x D ]
K H
Values: V = XW [H x N x D ]
V H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Attention weights: A = softmax(E, dim=2) [H x N x N]
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H
Outputs: O = YW [N x D]
O |
| Inputs: 1. QKV Pro
Input vectors: X [N x D] [N x D] [
Key matrix: W [D x HD ] Split and
K H
Value matrix: W [D x HD ] shape [H
V H
Query matrix: W [D x HD ]
Q H
Output matrix: W [HD x D]
O H
Computation:
Queries: Q = XW [H x N x D ]
Q H
Keys: K = XW [H x N x D ]
K H
Values: V = XW [H x N x D ]
V H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Attention weights: A = softmax(E, dim=2) [H x N x N]
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H
Outputs: O = YW [N x D]
O |
| Stanford CS231n 10th Anniversary Lecture 8 - 69 April 24, 2025 |


---
## Page 70
---


Self-Attention is Four Matrix Multiplies!
Inputs: 1. QKV Projection
Input vectors: X [N x D] [N x D] [D x 3HD ] => [N x 3HD ]
H H
Key matrix: W [D x HD ] Split and reshape to get Q, K, V each of
K H
Value matrix: W [D x HD ] shape [H x N x D ]
V H H
Query matrix: W [D x HD ] 2. QK Similarity
Q H
Output matrix: W [HD x D] [H x N x D ] [H x D x N] => [H x N x N]
O H H H
Computation:
Queries: Q = XW [H x N x D ]
Q H
Keys: K = XW [H x N x D ]
K H
Values: V = XW [H x N x D ]
V H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Attention weights: A = softmax(E, dim=2) [H x N x N]
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H
Outputs: O = YW [N x D]
O
Stanford CS231n 10th Anniversary Lecture 8 - 70 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Self-Attention is Four Matrix Multiplies!
Inputs: 1. QKV Projection
Input vectors: X [N x D] [N x D] [D x 3HD ] => [N x 3HD ]
H H
Key matrix: W [D x HD ] Split and reshape to get Q, K, V each of
K H
Value matrix: W [D x HD ] shape [H x N x D ]
V H H
Query matrix: W [D x HD ] 2. QK Similarity
Q H
Output matrix: W [HD x D] [H x N x D ] [H x D x N] => [H x N x N]
O H H H
Computation:
Queries: Q = XW [H x N x D ]
Q H
Keys: K = XW [H x N x D ]
K H
Values: V = XW [H x N x D ]
V H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Attention weights: A = softmax(E, dim=2) [H x N x N]
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H
Outputs: O = YW [N x D]
O |
| Inputs: 1. QKV Pro
Input vectors: X [N x D] [N x D] [
Key matrix: W [D x HD ] Split and
K H
Value matrix: W [D x HD ] shape [H
V H
Query matrix: W [D x HD ] 2. QK Simil
Q H
Output matrix: W [HD x D] [H x N x
O H
Computation:
Queries: Q = XW [H x N x D ]
Q H
Keys: K = XW [H x N x D ]
K H
Values: V = XW [H x N x D ]
V H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Attention weights: A = softmax(E, dim=2) [H x N x N]
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H
Outputs: O = YW [N x D]
O |
| Stanford CS231n 10th Anniversary Lecture 8 - 70 April 24, 2025 |


---
## Page 71
---


Self-Attention is Four Matrix Multiplies!
Inputs: 1. QKV Projection
Input vectors: X [N x D] [N x D] [D x 3HD ] => [N x 3HD ]
H H
Key matrix: W [D x HD ] Split and reshape to get Q, K, V each of
K H
Value matrix: W [D x HD ] shape [H x N x D ]
V H H
Query matrix: W [D x HD ] 2. QK Similarity
Q H
Output matrix: W [HD x D] [H x N x D ] [H x D x N] => [H x N x N]
O H H H
3. V-Weighting
Computation: [H x N x N] [H x N x D ] => [H x N x D ]
H H
Queries: Q = XW [H x N x D ] Reshape to [N x HD ]
Q H H
Keys: K = XW [H x N x D ]
K H
Values: V = XW [H x N x D ]
V H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Attention weights: A = softmax(E, dim=2) [H x N x N]
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H
Outputs: O = YW [N x D]
O
Stanford CS231n 10th Anniversary Lecture 8 - 71 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Self-Attention is Four Matrix Multiplies!
Inputs: 1. QKV Projection
Input vectors: X [N x D] [N x D] [D x 3HD ] => [N x 3HD ]
H H
Key matrix: W [D x HD ] Split and reshape to get Q, K, V each of
K H
Value matrix: W [D x HD ] shape [H x N x D ]
V H H
Query matrix: W [D x HD ] 2. QK Similarity
Q H
Output matrix: W [HD x D] [H x N x D ] [H x D x N] => [H x N x N]
O H H H
3. V-Weighting
Computation: [H x N x N] [H x N x D ] => [H x N x D ]
H H
Queries: Q = XW [H x N x D ] Reshape to [N x HD ]
Q H H
Keys: K = XW [H x N x D ]
K H
Values: V = XW [H x N x D ]
V H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Attention weights: A = softmax(E, dim=2) [H x N x N]
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H
Outputs: O = YW [N x D]
O |
| Inputs: 1. QKV Pro
Input vectors: X [N x D] [N x D] [
Key matrix: W [D x HD ] Split and
K H
Value matrix: W [D x HD ] shape [H
V H
Query matrix: W [D x HD ] 2. QK Simil
Q H
Output matrix: W [HD x D] [H x N x
O H
3. V-Weight
Computation: [H x N x
Queries: Q = XW [H x N x D ] Reshape
Q H
Keys: K = XW [H x N x D ]
K H
Values: V = XW [H x N x D ]
V H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Attention weights: A = softmax(E, dim=2) [H x N x N]
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H
Outputs: O = YW [N x D]
O |
| Stanford CS231n 10th Anniversary Lecture 8 - 71 April 24, 2025 |


---
## Page 72
---


Self-Attention is Four Matrix Multiplies!
Inputs: 1. QKV Projection
Input vectors: X [N x D] [N x D] [D x 3HD ] => [N x 3HD ]
H H
Key matrix: W [D x HD ] Split and reshape to get Q, K, V each of
K H
Value matrix: W [D x HD ] shape [H x N x D ]
V H H
Query matrix: W [D x HD ] 2. QK Similarity
Q H
Output matrix: W [HD x D] [H x N x D ] [H x D x N] => [H x N x N]
O H H H
3. V-Weighting
Computation: [H x N x N] [H x N x D ] => [H x N x D ]
H H
Queries: Q = XW [H x N x D ] Reshape to [N x HD ]
Q H H
Keys: K = XW [H x N x D ] 4. Output Projection
K H
Values: V = XW [H x N x D ] [N x HD ] [HD x D] => [N x D]
V H H H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Attention weights: A = softmax(E, dim=2) [H x N x N]
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H
Outputs: O = YW [N x D]
O
Stanford CS231n 10th Anniversary Lecture 8 - 72 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Self-Attention is Four Matrix Multiplies!
Inputs: 1. QKV Projection
Input vectors: X [N x D] [N x D] [D x 3HD ] => [N x 3HD ]
H H
Key matrix: W [D x HD ] Split and reshape to get Q, K, V each of
K H
Value matrix: W [D x HD ] shape [H x N x D ]
V H H
Query matrix: W [D x HD ] 2. QK Similarity
Q H
Output matrix: W [HD x D] [H x N x D ] [H x D x N] => [H x N x N]
O H H H
3. V-Weighting
Computation: [H x N x N] [H x N x D ] => [H x N x D ]
H H
Queries: Q = XW [H x N x D ] Reshape to [N x HD ]
Q H H
Keys: K = XW [H x N x D ] 4. Output Projection
K H
Values: V = XW [H x N x D ] [N x HD ] [HD x D] => [N x D]
V H H H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Attention weights: A = softmax(E, dim=2) [H x N x N]
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H
Outputs: O = YW [N x D]
O |
| Inputs: 1. QKV Pro
Input vectors: X [N x D] [N x D] [
Key matrix: W [D x HD ] Split and
K H
Value matrix: W [D x HD ] shape [H
V H
Query matrix: W [D x HD ] 2. QK Simil
Q H
Output matrix: W [HD x D] [H x N x
O H
3. V-Weight
Computation: [H x N x
Queries: Q = XW [H x N x D ] Reshape
Q H
Keys: K = XW [H x N x D ] 4. Output P
K H
Values: V = XW [H x N x D ] [N x HD
V H H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Attention weights: A = softmax(E, dim=2) [H x N x N]
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H
Outputs: O = YW [N x D]
O |
| Outputs: O = YW [N x D]
O |
| Stanford CS231n 10th Anniversary Lecture 8 - 72 April 24, 2025 |


---
## Page 73
---


Self-Attention is Four Matrix Multiplies!
Inputs: 1. QKV Projection
Input vectors: X [N x D] [N x D] [D x 3HD ] => [N x 3HD ]
H H
Key matrix: W [D x HD ] Split and reshape to get Q, K, V each of
K H
Value matrix: W [D x HD ] shape [H x N x D ]
V H H
Query matrix: W [D x HD ] 2. QK Similarity
Q H
Output matrix: W [HD x D] [H x N x D ] [H x D x N] => [H x N x N]
O H H H
3. V-Weighting
Computation: [H x N x N] [H x N x D ] => [H x N x D ]
H H
Queries: Q = XW [H x N x D ] Reshape to [N x HD ]
Q H H
Keys: K = XW [H x N x D ] 4. Output Projection
K H
Values: V = XW [H x N x D ] [N x HD ] [HD x D] => [N x D]
V H H H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Q: How much compute does this take
Attention weights: A = softmax(E, dim=2) [H x N x N]
as the number of vectors N increases?
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H
Outputs: O = YW [N x D]
O
Stanford CS231n 10th Anniversary Lecture 8 - 73 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Self-Attention is Four Matrix Multiplies!
Inputs: 1. QKV Projection
Input vectors: X [N x D] [N x D] [D x 3HD ] => [N x 3HD ]
H H
Key matrix: W [D x HD ] Split and reshape to get Q, K, V each of
K H
Value matrix: W [D x HD ] shape [H x N x D ]
V H H
Query matrix: W [D x HD ] 2. QK Similarity
Q H
Output matrix: W [HD x D] [H x N x D ] [H x D x N] => [H x N x N]
O H H H
3. V-Weighting
Computation: [H x N x N] [H x N x D ] => [H x N x D ]
H H
Queries: Q = XW [H x N x D ] Reshape to [N x HD ]
Q H H
Keys: K = XW [H x N x D ] 4. Output Projection
K H
Values: V = XW [H x N x D ] [N x HD ] [HD x D] => [N x D]
V H H H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Q: How much compute does this take
Attention weights: A = softmax(E, dim=2) [H x N x N]
as the number of vectors N increases?
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H
Outputs: O = YW [N x D]
O |
| Inputs: 1. QKV Pro
Input vectors: X [N x D] [N x D] [
Key matrix: W [D x HD ] Split and
K H
Value matrix: W [D x HD ] shape [H
V H
Query matrix: W [D x HD ] 2. QK Simil
Q H
Output matrix: W [HD x D] [H x N x
O H
3. V-Weight
Computation: [H x N x
Queries: Q = XW [H x N x D ] Reshape
Q H
Keys: K = XW [H x N x D ] 4. Output P
K H
Values: V = XW [H x N x D ] [N x HD
V H H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Q: H
Attention weights: A = softmax(E, dim=2) [H x N x N]
as th
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H
Outputs: O = YW [N x D]
O |
| Stanford CS231n 10th Anniversary Lecture 8 - 73 April 24, 2025 |


---
## Page 74
---


Self-Attention is Four Matrix Multiplies!
Inputs: 1. QKV Projection
Input vectors: X [N x D] [N x D] [D x 3HD ] => [N x 3HD ]
H H
Key matrix: W [D x HD ] Split and reshape to get Q, K, V each of
K H
Value matrix: W [D x HD ] shape [H x N x D ]
V H H
Query matrix: W [D x HD ] 2. QK Similarity
Q H
Output matrix: W [HD x D] [H x N x D ] [H x D x N] => [H x N x N]
O H H H
3. V-Weighting
Computation: [H x N x N] [H x N x D ] => [H x N x D ]
H H
Queries: Q = XW [H x N x D ] Reshape to [N x HD ]
Q H H
Keys: K = XW [H x N x D ] 4. Output Projection
K H
Values: V = XW [H x N x D ] [N x HD ] [HD x D] => [N x D]
V H H H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Q: How much compute does this take
Attention weights: A = softmax(E, dim=2) [H x N x N]
as the number of vectors N increases?
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H A: O(N2)
Outputs: O = YW [N x D]
O
Stanford CS231n 10th Anniversary Lecture 8 - 74 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Self-Attention is Four Matrix Multiplies!
Inputs: 1. QKV Projection
Input vectors: X [N x D] [N x D] [D x 3HD ] => [N x 3HD ]
H H
Key matrix: W [D x HD ] Split and reshape to get Q, K, V each of
K H
Value matrix: W [D x HD ] shape [H x N x D ]
V H H
Query matrix: W [D x HD ] 2. QK Similarity
Q H
Output matrix: W [HD x D] [H x N x D ] [H x D x N] => [H x N x N]
O H H H
3. V-Weighting
Computation: [H x N x N] [H x N x D ] => [H x N x D ]
H H
Queries: Q = XW [H x N x D ] Reshape to [N x HD ]
Q H H
Keys: K = XW [H x N x D ] 4. Output Projection
K H
Values: V = XW [H x N x D ] [N x HD ] [HD x D] => [N x D]
V H H H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Q: How much compute does this take
Attention weights: A = softmax(E, dim=2) [H x N x N]
as the number of vectors N increases?
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H A: O(N2)
Outputs: O = YW [N x D]
O |
| Inputs: 1. QKV Pro
Input vectors: X [N x D] [N x D] [
Key matrix: W [D x HD ] Split and
K H
Value matrix: W [D x HD ] shape [H
V H
Query matrix: W [D x HD ] 2. QK Simil
Q H
Output matrix: W [HD x D] [H x N x
O H
3. V-Weight
Computation: [H x N x
Queries: Q = XW [H x N x D ] Reshape
Q H
Keys: K = XW [H x N x D ] 4. Output P
K H
Values: V = XW [H x N x D ] [N x HD
V H H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Q: H
Attention weights: A = softmax(E, dim=2) [H x N x N]
as th
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H A: O
Outputs: O = YW [N x D]
O |
| Stanford CS231n 10th Anniversary Lecture 8 - 74 April 24, 2025 |


### Table 2

| 2. QK Simil
[H x N x
3. V-Weight
[H x N x
Reshape | arity
D ] [H x D x N] => [H x N x N]
H H
ing
N] [H x N x D ] => [H x N x D ]
H H
to [N x HD ]
H |


---
## Page 75
---


Self-Attention is Four Matrix Multiplies!
Inputs: 1. QKV Projection
Input vectors: X [N x D] [N x D] [D x 3HD ] => [N x 3HD ]
H H
Key matrix: W [D x HD ] Split and reshape to get Q, K, V each of
K H
Value matrix: W [D x HD ] shape [H x N x D ]
V H H
Query matrix: W [D x HD ] 2. QK Similarity
Q H
Output matrix: W [HD x D] [H x N x D ] [H x D x N] => [H x N x N]
O H H H
3. V-Weighting
Computation: [H x N x N] [H x N x D ] => [H x N x D ]
H H
Queries: Q = XW [H x N x D ] Reshape to [N x HD ]
Q H H
Keys: K = XW [H x N x D ] 4. Output Projection
K H
Values: V = XW [H x N x D ] [N x HD ] [HD x D] => [N x D]
V H H H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Q: How much memory does this take
Attention weights: A = softmax(E, dim=2) [H x N x N]
as the number of vectors N increases?
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H
Outputs: O = YW [N x D]
O
Stanford CS231n 10th Anniversary Lecture 8 - 75 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Self-Attention is Four Matrix Multiplies!
Inputs: 1. QKV Projection
Input vectors: X [N x D] [N x D] [D x 3HD ] => [N x 3HD ]
H H
Key matrix: W [D x HD ] Split and reshape to get Q, K, V each of
K H
Value matrix: W [D x HD ] shape [H x N x D ]
V H H
Query matrix: W [D x HD ] 2. QK Similarity
Q H
Output matrix: W [HD x D] [H x N x D ] [H x D x N] => [H x N x N]
O H H H
3. V-Weighting
Computation: [H x N x N] [H x N x D ] => [H x N x D ]
H H
Queries: Q = XW [H x N x D ] Reshape to [N x HD ]
Q H H
Keys: K = XW [H x N x D ] 4. Output Projection
K H
Values: V = XW [H x N x D ] [N x HD ] [HD x D] => [N x D]
V H H H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Q: How much memory does this take
Attention weights: A = softmax(E, dim=2) [H x N x N]
as the number of vectors N increases?
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H
Outputs: O = YW [N x D]
O |
| Inputs: 1. QKV Pro
Input vectors: X [N x D] [N x D] [
Key matrix: W [D x HD ] Split and
K H
Value matrix: W [D x HD ] shape [H
V H
Query matrix: W [D x HD ] 2. QK Simil
Q H
Output matrix: W [HD x D] [H x N x
O H
3. V-Weight
Computation: [H x N x
Queries: Q = XW [H x N x D ] Reshape
Q H
Keys: K = XW [H x N x D ] 4. Output P
K H
Values: V = XW [H x N x D ] [N x HD
V H H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Q: H
Attention weights: A = softmax(E, dim=2) [H x N x N]
as th
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H
Outputs: O = YW [N x D]
O |
| Stanford CS231n 10th Anniversary Lecture 8 - 75 April 24, 2025 |


---
## Page 76
---


Self-Attention is Four Matrix Multiplies!
Inputs: 1. QKV Projection
Input vectors: X [N x D] [N x D] [D x 3HD ] => [N x 3HD ]
H H
Key matrix: W [D x HD ] Split and reshape to get Q, K, V each of
K H
Value matrix: W [D x HD ] shape [H x N x D ]
V H H
Query matrix: W [D x HD ] 2. QK Similarity
Q H
Output matrix: W [HD x D] [H x N x D ] [H x D x N] => [H x N x N]
O H H H
3. V-Weighting
Computation: [H x N x N] [H x N x D ] => [H x N x D ]
H H
Queries: Q = XW [H x N x D ] Reshape to [N x HD ]
Q H H
Keys: K = XW [H x N x D ] 4. Output Projection
K H
Values: V = XW [H x N x D ] [N x HD ] [HD x D] => [N x D]
V H H H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Q: How much memory does this take
Attention weights: A = softmax(E, dim=2) [H x N x N]
as the number of vectors N increases?
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H A: O(N2)
Outputs: O = YW [N x D]
O
Stanford CS231n 10th Anniversary Lecture 8 - 76 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Self-Attention is Four Matrix Multiplies!
Inputs: 1. QKV Projection
Input vectors: X [N x D] [N x D] [D x 3HD ] => [N x 3HD ]
H H
Key matrix: W [D x HD ] Split and reshape to get Q, K, V each of
K H
Value matrix: W [D x HD ] shape [H x N x D ]
V H H
Query matrix: W [D x HD ] 2. QK Similarity
Q H
Output matrix: W [HD x D] [H x N x D ] [H x D x N] => [H x N x N]
O H H H
3. V-Weighting
Computation: [H x N x N] [H x N x D ] => [H x N x D ]
H H
Queries: Q = XW [H x N x D ] Reshape to [N x HD ]
Q H H
Keys: K = XW [H x N x D ] 4. Output Projection
K H
Values: V = XW [H x N x D ] [N x HD ] [HD x D] => [N x D]
V H H H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Q: How much memory does this take
Attention weights: A = softmax(E, dim=2) [H x N x N]
as the number of vectors N increases?
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H A: O(N2)
Outputs: O = YW [N x D]
O |
| Inputs: 1. QKV Pro
Input vectors: X [N x D] [N x D] [
Key matrix: W [D x HD ] Split and
K H
Value matrix: W [D x HD ] shape [H
V H
Query matrix: W [D x HD ] 2. QK Simil
Q H
Output matrix: W [HD x D] [H x N x
O H
3. V-Weight
Computation: [H x N x
Queries: Q = XW [H x N x D ] Reshape
Q H
Keys: K = XW [H x N x D ] 4. Output P
K H
Values: V = XW [H x N x D ] [N x HD
V H H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Q: H
Attention weights: A = softmax(E, dim=2) [H x N x N]
as th
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H A: O
Outputs: O = YW [N x D]
O |
| Stanford CS231n 10th Anniversary Lecture 8 - 76 April 24, 2025 |


### Table 2

| 2. QK Simil
[H x N x
3. V-Weight
[H x N x
Reshape | arity
D ] [H x D x N] => [H x N x N]
H H
ing
N] [H x N x D ] => [H x N x D ]
H H
to [N x HD ]
H |


---
## Page 77
---


If N=100K, H=64 then
Self-Attention is Four Matrix Multiplies!
HxNxN attention weights
take 1.192 TB! GPUs don’t
have that much memory…
Inputs: 1. QKV Projection
Input vectors: X [N x D] [N x D] [D x 3HD ] => [N x 3HD ]
H H
Key matrix: W [D x HD ] Split and reshape to get Q, K, V each of
K H
Value matrix: W [D x HD ] shape [H x N x D ]
V H H
Query matrix: W [D x HD ] 2. QK Similarity
Q H
Output matrix: W [HD x D] [H x N x D ] [H x D x N] => [H x N x N]
O H H H
3. V-Weighting
Computation: [H x N x N] [H x N x D ] => [H x N x D ]
H H
Queries: Q = XW [H x N x D ] Reshape to [N x HD ]
Q H H
Keys: K = XW [H x N x D ] 4. Output Projection
K H
Values: V = XW [H x N x D ] [N x HD ] [HD x D] => [N x D]
V H H H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Q: How much memory does this take
Attention weights: A = softmax(E, dim=2) [H x N x N]
as the number of vectors N increases?
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H A: O(N2)
Outputs: O = YW [N x D]
O
Stanford CS231n 10th Anniversary Lecture 8 - 77 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| If N=100K, H=64 then
Self-Attention is Four Matrix Multiplies!
HxNxN attention weights
take 1.192 TB! GPUs don’t
have that much memory…
Inputs: 1. QKV Projection
Input vectors: X [N x D] [N x D] [D x 3HD ] => [N x 3HD ]
H H
Key matrix: W [D x HD ] Split and reshape to get Q, K, V each of
K H
Value matrix: W [D x HD ] shape [H x N x D ]
V H H
Query matrix: W [D x HD ] 2. QK Similarity
Q H
Output matrix: W [HD x D] [H x N x D ] [H x D x N] => [H x N x N]
O H H H
3. V-Weighting
Computation: [H x N x N] [H x N x D ] => [H x N x D ]
H H
Queries: Q = XW [H x N x D ] Reshape to [N x HD ]
Q H H
Keys: K = XW [H x N x D ] 4. Output Projection
K H
Values: V = XW [H x N x D ] [N x HD ] [HD x D] => [N x D]
V H H H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Q: How much memory does this take
Attention weights: A = softmax(E, dim=2) [H x N x N]
as the number of vectors N increases?
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H A: O(N2)
Outputs: O = YW [N x D]
O |
| Inputs: 1. QKV Pro
Input vectors: X [N x D] [N x D] [
Key matrix: W [D x HD ] Split and
K H
Value matrix: W [D x HD ] shape [H
V H
Query matrix: W [D x HD ] 2. QK Simil
Q H
Output matrix: W [HD x D] [H x N x
O H
3. V-Weight
Computation: [H x N x
Queries: Q = XW [H x N x D ] Reshape
Q H
Keys: K = XW [H x N x D ] 4. Output P
K H
Values: V = XW [H x N x D ] [N x HD
V H H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Q: H
Attention weights: A = softmax(E, dim=2) [H x N x N]
as th
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H A: O
Outputs: O = YW [N x D]
O |
| Stanford CS231n 10th Anniversary Lecture 8 - 77 April 24, 2025 |


### Table 2

| 2. QK Simil
[H x N x
3. V-Weight
[H x N x
Reshape | arity
D ] [H x D x N] => [H x N x N]
H H
ing
N] [H x N x D ] => [H x N x D ]
H H
to [N x HD ]
H |


---
## Page 78
---


If N=100K, H=64 then
Self-Attention is Four Matrix Multiplies!
HxNxN attention weights
take 1.192 TB! GPUs don’t
Flash Attention
have that much memory…
Inputs: algorithm computes 1. QKV Projection
2+3 at the same time
Input vectors: X [N x D] [N x D] [D x 3HD ] => [N x 3HD ]
H H
without storing the
Key matrix: W [D x HD ] Split and reshape to get Q, K, V each of
K H full attention matrix!
Value matrix: W [D x HD ] shape [H x N x D ]
V H H
Query matrix: W [D x HD ] 2. QK Similarity
Makes large N
Q H
Output matrix: W [HD x D] possible [H x N x D ] [H x D x N] => [H x N x N]
O H H H
3. V-Weighting
Computation: [H x N x N] [H x N x D ] => [H x N x D ]
H H
Queries: Q = XW [H x N x D ] Reshape to [N x HD ]
Q H H
Keys: K = XW [H x N x D ] 4. Output Projection
K H
Values: V = XW [H x N x D ] [N x HD ] [HD x D] => [N x D]
V H H H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Q: How much memory does this take
Attention weights: A = softmax(E, dim=2) [H x N x N]
as the number of vectors N increases?
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H A: O(N) with Flash Attention
Outputs: O = YW [N x D]
O
Dao et al, “FlashAttention: Fast and Memory-Efficient Exact Attention with IO-Awareness”, 2022
Stanford CS231n 10th Anniversary Lecture 8 - 78 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| If N=100K, H=64 then
Self-Attention is Four Matrix Multiplies!
HxNxN attention weights
take 1.192 TB! GPUs don’t
Flash Attention
have that much memory…
Inputs: algorithm computes 1. QKV Projection
2+3 at the same time
Input vectors: X [N x D] [N x D] [D x 3HD ] => [N x 3HD ]
H H
without storing the
Key matrix: W [D x HD ] Split and reshape to get Q, K, V each of
K H full attention matrix!
Value matrix: W [D x HD ] shape [H x N x D ]
V H H
Query matrix: W [D x HD ] 2. QK Similarity
Makes large N
Q H
Output matrix: W [HD x D] possible [H x N x D ] [H x D x N] => [H x N x N]
O H H H
3. V-Weighting
Computation: [H x N x N] [H x N x D ] => [H x N x D ]
H H
Queries: Q = XW [H x N x D ] Reshape to [N x HD ]
Q H H
Keys: K = XW [H x N x D ] 4. Output Projection
K H
Values: V = XW [H x N x D ] [N x HD ] [HD x D] => [N x D]
V H H H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Q: How much memory does this take
Attention weights: A = softmax(E, dim=2) [H x N x N]
as the number of vectors N increases?
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H A: O(N) with Flash Attention
Outputs: O = YW [N x D]
O
Dao et al, “FlashAttention: Fast and Memory-Efficient Exact Attention with IO-Awareness”, 2022 |
| Flash Attention
Inputs: algorithm computes 1. QKV Pro
2+3 at the same time
Input vectors: X [N x D] [N x D] [
without storing the
Key matrix: W [D x HD ] Split and
K H full attention matrix!
Value matrix: W [D x HD ] shape [H
V H
Query matrix: W [D x HD ] 2. QK Simil
Makes large N
Q H
Output matrix: W [HD x D] possible [H x N x
O H
3. V-Weight
Computation: [H x N x
Queries: Q = XW [H x N x D ] Reshape
Q H
Keys: K = XW [H x N x D ] 4. Output P
K H
Values: V = XW [H x N x D ] [N x HD
V H H
Similarities: E = QKT / 𝐷 [H x N x N]
𝑄
Q: H
Attention weights: A = softmax(E, dim=2) [H x N x N]
as th
Head outputs: Y = AV [H x N x D ] => [N x HD ]
H H A: O
Outputs: O = YW [N x D]
O
Dao et al, “Flas |
| Stanford CS231n 10th Anniversary Lecture 8 - 78 April 24, 2025 |


### Table 2

| 2. QK Simil
[H x N x
3. V-Weight
[H x N x
Reshape | arity
D ] [H x D x N] => [H x N x N]
H H
ing
N] [H x N x D ] => [H x N x D ]
H H
to [N x HD ]
H |


---
## Page 79
---


Three Ways of Processing Sequences
Stanford CS231n 10th Anniversary Lecture 8 - 79 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Three Ways of Processing Sequences |
| Stanford CS231n 10th Anniversary Lecture 8 - 79 April 24, 2025 |


---
## Page 80
---


Three Ways of Processing Sequences
Recurrent Neural Network
y y y y
1 2 3 4
x x x x
1 2 3 4
Works on 1D ordered sequences
(+) Theoretically good at long
sequences: O(N) compute and
memory for a sequence of length N
(-) Not parallelizable. Need to
compute hidden states sequentially
Stanford CS231n 10th Anniversary Lecture 8 - 80 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Three Ways of Processing Sequences
Recurrent Neural Network
y y y y
1 2 3 4
x x x x
1 2 3 4
Works on 1D ordered sequences
(+) Theoretically good at long
sequences: O(N) compute and
memory for a sequence of length N
(-) Not parallelizable. Need to
compute hidden states sequentially |
| Stanford CS231n 10th Anniversary Lecture 8 - 80 April 24, 2025 |


---
## Page 81
---


Three Ways of Processing Sequences
Recurrent Neural Network Convolution
y y y y
y y y y
1 2 3 4
1 2 3 4
x x x x
x x x x
1 2 3 4
1 2 3 4
Works on 1D ordered sequences Works on N-dimensional grids
(+) Theoretically good at long (-) Bad for long sequences: need to
sequences: O(N) compute and stack many layers to build up large
memory for a sequence of length N receptive fields
(-) Not parallelizable. Need to (+) Parallelizable, outputs can be
compute hidden states sequentially computed in parallel
Stanford CS231n 10th Anniversary Lecture 8 - 81 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Three Ways of Processing Sequences
Recurrent Neural Network Convolution
y y y y
y y y y
1 2 3 4
1 2 3 4
x x x x
x x x x
1 2 3 4
1 2 3 4
Works on 1D ordered sequences Works on N-dimensional grids
(+) Theoretically good at long (-) Bad for long sequences: need to
sequences: O(N) compute and stack many layers to build up large
memory for a sequence of length N receptive fields
(-) Not parallelizable. Need to (+) Parallelizable, outputs can be
compute hidden states sequentially computed in parallel |
| Stanford CS231n 10th Anniversary Lecture 8 - 81 April 24, 2025 |


---
## Page 82
---


Three Ways of Processing Sequences
Recurrent Neural Network Convolution Self-Attention
Y1 Y2 Y3
Product(→),(cid:9)(cid:9)(cid:9)Sum(↑)
y y y y
1 2 3 4
y y y y V3 A1,3 A2,3 A3,3
1 2 3 4 V2 A1,2 A2,2 A3,2
V1 A1,1 A2,1 A3,1
Softmax(↑)
K3 E1,3 E2,3 E3,3
K2 E1,2 E2,2 E3,2
K1 E1,1 E2,1 E3,1
x x x x x x x x Q1 Q2 Q3
1 2 3 4
1 2 3 4 X1 X2 X3
Works on 1D ordered sequences Works on N-dimensional grids Works on sets of vectors
(+) Theoretically good at long (-) Bad for long sequences: need to (+) Great for long sequences; each
sequences: O(N) compute and stack many layers to build up large output depends directly on all inputs
memory for a sequence of length N receptive fields (+) Highly parallel, it’s just 4 matmuls
(-) Not parallelizable. Need to (+) Parallelizable, outputs can be (-) Expensive: O(N2) compute, O(N)
compute hidden states sequentially computed in parallel memory for sequence of length N
Stanford CS231n 10th Anniversary Lecture 8 - 82 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Three Ways of Processing Sequences
Recurrent Neural Network Convolution Self-Attention
Y1 Y2 Y3
Product(→),(cid:9)(cid:9)(cid:9)Sum(↑)
y y y y
y y y y V3 A1,3 A2,3 A3,3
1 2 3 4
1 2 3 4 V2 A1,2 A2,2 A3,2
V1 A1,1 A2,1 A3,1
Softmax(↑)
K3 E1,3 E2,3 E3,3
K2 E1,2 E2,2 E3,2
K1 E1,1 E2,1 E3,1
x x x x x x x x Q1 Q2 Q3
1 2 3 4
1 2 3 4 X1 X2 X3
Works on 1D ordered sequences Works on N-dimensional grids Works on sets of vectors
(+) Theoretically good at long (-) Bad for long sequences: need to (+) Great for long sequences; each
sequences: O(N) compute and stack many layers to build up large output depends directly on all inputs
memory for a sequence of length N receptive fields (+) Highly parallel, it’s just 4 matmuls
(-) Not parallelizable. Need to (+) Parallelizable, outputs can be (-) Expensive: O(N2) compute, O(N)
compute hidden states sequentially computed in parallel memory for sequence of length N |
| Stanford CS231n 10th Anniversary Lecture 8 - 82 April 24, 2025 |


---
## Page 83
---


Three Ways of Processing Sequences
Recurrent Neural Network Convolution Self-Attention
Y1 Y2 Y3
Product(→),(cid:9)(cid:9)(cid:9)Sum(↑)
y y y y
1 2 3 4
y y y y V3 A1,3 A2,3 A3,3
1 2 3 4 V2 A1,2 A2,2 A3,2
V1 A1,1 A2,1 A3,1
Softmax(↑)
K3 E1,3 E2,3 E3,3
Attention is All You NeeK2 dE1,2 E2,2 E3,2
K1 E1,1 E2,1 E3,1
x x x x x x x x Q1 Q2 Q3
1 2 3 4
1 2 3 4 X1 X2 X3
Vaswani et al, NeurIPS 2017
Works on 1D ordered sequences Works on N-dimensional grids Works on sets of vectors
(+) Theoretically good at long (-) Bad for long sequences: need to (+) Great for long sequences; each
sequences: O(N) compute and stack many layers to build up large output depends directly on all inputs
memory for a sequence of length N receptive fields (+) Highly parallel, it’s just 4 matmuls
(-) Not parallelizable. Need to (+) Parallelizable, outputs can be (-) Expensive: O(N2) compute, O(N)
compute hidden states sequentially computed in parallel memory for sequence of length N
Stanford CS231n 10th Anniversary Lecture 8 - 83 April 24, 2025

[Page contains 9 table(s)]


### Table 1

| Three Ways of Processing Sequences
Recurrent Neural Network Convolution Self-Attention
Y1 Y2 Y3
Product(→),(cid:9)(cid:9)(cid:9)Sum(↑)
y y y y
y y y y V3 A1,3 A2,3 A3,3
1 2 3 4
1 2 3 4 V2 A1,2 A2,2 A3,2
V1 A1,1 A2,1 A3,1
Softmax(↑)
K3 E1,3 E2,3 E3,3
Attention is All You NeeK2 dE1,2 E2,2 E3,2
K1 E1,1 E2,1 E3,1
x x x x x x x x Q1 Q2 Q3
1 2 3 4
1 2 3 4 X1 X2 X3
Vaswani et al, NeurIPS 2017
Works on 1D ordered sequences Works on N-dimensional grids Works on sets of vectors
(+) Theoretically good at long (-) Bad for long sequences: need to (+) Great for long sequences; each
sequences: O(N) compute and stack many layers to build up large output depends directly on all inputs
memory for a sequence of length N receptive fields (+) Highly parallel, it’s just 4 matmuls
(-) Not parallelizable. Need to (+) Parallelizable, outputs can be (-) Expensive: O(N2) compute, O(N)
compute hidden states sequentially computed in parallel memory for sequence of length N |
| Stanford CS231n 10th Anniversary Lecture 8 - 83 April 24, 2025 |


### Table 2

|  |
| y
1 |


### Table 3

|  |
| y
2 |


### Table 4

|  |
| y
3 |


### Table 5

|  |
| y
4 |


### Table 6

|  |
| y
1 |


### Table 7

|  |
| y
2 |


### Table 8

|  |
| y
3 |


### Table 9

|  |
| y
4 |


---
## Page 84
---


The Transformer
Transformer Block
Input: Set of vectors x
x x x x
1 2 3 4
Vaswani et al, “Attention is all you need,” NeurIPS2017
Stanford CS231n 10th Anniversary Lecture 8 - 84 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| The Transformer
Transformer Block
Input: Set of vectors x
x x x x
1 2 3 4
Vaswani et al, “Attention is all you need,” NeurIPS2017 |
| Stanford CS231n 10th Anniversary Lecture 8 - 84 April 24, 2025 |


---
## Page 85
---


The Transformer
Transformer Block
Input: Set of vectors x
Self-Attention
All vectors interact through
(multiheaded) Self-Attention
x x x x
1 2 3 4
Vaswani et al, “Attention is all you need,” NeurIPS2017
Stanford CS231n 10th Anniversary Lecture 8 - 85 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| The Transformer
Transformer Block
Input: Set of vectors x
Self-Attention
All vectors interact through
(multiheaded) Self-Attention
x x x x
1 2 3 4
Vaswani et al, “Attention is all you need,” NeurIPS2017 |
| Stanford CS231n 10th Anniversary Lecture 8 - 85 April 24, 2025 |


---
## Page 86
---


The Transformer
Transformer Block
Input: Set of vectors x
+
Residual connection
Self-Attention
All vectors interact through
(multiheaded) Self-Attention
x x x x
1 2 3 4
Vaswani et al, “Attention is all you need,” NeurIPS2017
Stanford CS231n 10th Anniversary Lecture 8 - 86 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| The Transformer
Transformer Block
Input: Set of vectors x
+
Residual connection
Self-Attention
All vectors interact through
(multiheaded) Self-Attention
x x x x
1 2 3 4
Vaswani et al, “Attention is all you need,” NeurIPS2017 |
| Stanford CS231n 10th Anniversary Lecture 8 - 86 April 24, 2025 |


---
## Page 87
---


Recall Layer Normalization:
The Transformer
Given h , …, h (Shape: D)
1 N
scale: 𝛾 (Shape: D)
Transformer Block shift: 𝛽 (Shape: D)
𝜇 = (∑ h )/D (scalar)
i j i,j
Input: Set of vectors x 𝜎 = (∑ (h - 𝜇)2/D)1/2 (scalar)
i j i,j i
z = (h - 𝜇) / 𝜎
i i i i
y = 𝛾 * z + 𝛽
i i
Ba et al, 2016
Layer normalization
Layer Normalization
normalizes all vectors
+
Residual connection
Self-Attention
All vectors interact through
(multiheaded) Self-Attention
x x x x
1 2 3 4
Vaswani et al, “Attention is all you need,” NeurIPS2017
Stanford CS231n 10th Anniversary Lecture 8 - 87 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Recall Layer Normalization:
The Transformer
Given h , …, h (Shape: D)
1 N
scale: 𝛾 (Shape: D)
Transformer Block shift: 𝛽 (Shape: D)
𝜇 = (∑ h )/D (scalar)
i j i,j
Input: Set of vectors x 𝜎 = (∑ (h - 𝜇)2/D)1/2 (scalar)
i j i,j i
z = (h - 𝜇) / 𝜎
i i i i
y = 𝛾 * z + 𝛽
i i
Ba et al, 2016
Layer normalization
Layer Normalization
normalizes all vectors
+
Residual connection
Self-Attention
All vectors interact through
(multiheaded) Self-Attention
x x x x
1 2 3 4
Vaswani et al, “Attention is all you need,” NeurIPS2017 |
| Stanford CS231n 10th Anniversary Lecture 8 - 87 April 24, 2025 |


---
## Page 88
---


The Transformer Usually a two-layer MLP;
classic setup is
D => 4D => D
Transformer Block
Also sometimes called FFN
Input: Set of vectors x
(Feed-Forward Network)
MLP independently
MLP MLP MLP MLP
on each vector
Layer normalization
Layer Normalization
normalizes all vectors
+
Residual connection
Self-Attention
All vectors interact through
(multiheaded) Self-Attention
x x x x
1 2 3 4
Vaswani et al, “Attention is all you need,” NeurIPS2017
Stanford CS231n 10th Anniversary Lecture 8 - 88 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| The Transformer Usually a two-layer MLP;
classic setup is
D => 4D => D
Transformer Block
Also sometimes called FFN
Input: Set of vectors x
(Feed-Forward Network)
MLP independently
MLP MLP MLP MLP
on each vector
Layer normalization
Layer Normalization
normalizes all vectors
+
Residual connection
Self-Attention
All vectors interact through
(multiheaded) Self-Attention
x x x x
1 2 3 4
Vaswani et al, “Attention is all you need,” NeurIPS2017 |
| Stanford CS231n 10th Anniversary Lecture 8 - 88 April 24, 2025 |


### Table 2

| MLP | MLP |


---
## Page 89
---


The Transformer
Transformer Block
Input: Set of vectors x Residual connection +
MLP independently
MLP MLP MLP MLP
on each vector
Layer normalization
Layer Normalization
normalizes all vectors
+
Residual connection
Self-Attention
All vectors interact through
(multiheaded) Self-Attention
x x x x
1 2 3 4
Vaswani et al, “Attention is all you need,” NeurIPS2017
Stanford CS231n 10th Anniversary Lecture 8 - 89 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| The Transformer
Transformer Block
Input: Set of vectors x Residual connection +
MLP independently
MLP MLP MLP MLP
on each vector
Layer normalization
Layer Normalization
normalizes all vectors
+
Residual connection
Self-Attention
All vectors interact through
(multiheaded) Self-Attention
x x x x
1 2 3 4
Vaswani et al, “Attention is all you need,” NeurIPS2017 |
| Stanford CS231n 10th Anniversary Lecture 8 - 89 April 24, 2025 |


---
## Page 90
---


The Transformer
y y y y
1 2 3 4
Transformer Block
Another Layer Norm Layer Normalization
Input: Set of vectors x Residual connection +
MLP independently
MLP MLP MLP MLP
on each vector
Layer normalization
Layer Normalization
normalizes all vectors
+
Residual connection
Self-Attention
All vectors interact through
(multiheaded) Self-Attention
x x x x
1 2 3 4
Vaswani et al, “Attention is all you need,” NeurIPS2017
Stanford CS231n 10th Anniversary Lecture 8 - 90 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| The Transformer
y y y y
1 2 3 4
Transformer Block
Another Layer Norm Layer Normalization
Input: Set of vectors x Residual connection +
MLP independently
MLP MLP MLP MLP
on each vector
Layer normalization
Layer Normalization
normalizes all vectors
+
Residual connection
Self-Attention
All vectors interact through
(multiheaded) Self-Attention
x x x x
1 2 3 4
Vaswani et al, “Attention is all you need,” NeurIPS2017 |
| Stanford CS231n 10th Anniversary Lecture 8 - 90 April 24, 2025 |


---
## Page 91
---


The Transformer
y y y y
1 2 3 4
Transformer Block
Layer Normalization
Input: Set of vectors x +
Output: Set of vectors y
MLP MLP MLP MLP
Self-Attention is the only
interaction between vectors
LayerNorm and MLP work on
Layer Normalization
each vector independently
+
Highly scalable and
Self-Attention
parallelizable, most of the
compute is just 6 matmuls:
4 from Self-Attention
2 from MLP x x x x
1 2 3 4
Vaswani et al, “Attention is all you need,” NeurIPS2017
Stanford CS231n 10th Anniversary Lecture 8 - 91 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| The Transformer
y y y y
1 2 3 4
Transformer Block
Layer Normalization
Input: Set of vectors x +
Output: Set of vectors y
MLP MLP MLP MLP
Self-Attention is the only
interaction between vectors
LayerNorm and MLP work on
Layer Normalization
each vector independently
+
Highly scalable and
Self-Attention
parallelizable, most of the
compute is just 6 matmuls:
4 from Self-Attention
2 from MLP x x x x
1 2 3 4
Vaswani et al, “Attention is all you need,” NeurIPS2017 |
| Stanford CS231n 10th Anniversary Lecture 8 - 91 April 24, 2025 |


### Table 2

|  |  |  |


---
## Page 92
---


The Transformer
Transformer Block A Transformer is just a stack of
identical Transformer blocks!
Input: Set of vectors x
Output: Set of vectors y They have not changed much since
2017… but have gotten a lot bigger
Self-Attention is the only
interaction between vectors
LayerNorm and MLP work on
each vector independently
Highly scalable and
parallelizable, most of the
compute is just 6 matmuls:
4 from Self-Attention
2 from MLP
Vaswani et al, “Attention is all you need,” NeurIPS2017
Stanford CS231n 10th Anniversary Lecture 8 - 92 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| The Transformer
Transformer Block A Transformer is just a stack of
identical Transformer blocks!
Input: Set of vectors x
Output: Set of vectors y They have not changed much since
2017… but have gotten a lot bigger
Self-Attention is the only
interaction between vectors
LayerNorm and MLP work on
each vector independently
Highly scalable and
parallelizable, most of the
compute is just 6 matmuls:
4 from Self-Attention
2 from MLP
Vaswani et al, “Attention is all you need,” NeurIPS2017 |
| Stanford CS231n 10th Anniversary Lecture 8 - 92 April 24, 2025 |


[Page contains 3 image(s)]


---
## Page 93
---


The Transformer
Transformer Block A Transformer is just a stack of
identical Transformer blocks!
Input: Set of vectors x
Output: Set of vectors y They have not changed much since
2017… but have gotten a lot bigger
Self-Attention is the only
interaction between vectors Original: [Vaswani et al, 2017]
12 blocks, D=1024, H=16, N=512
LayerNorm and MLP work on 213M params
each vector independently
Highly scalable and
parallelizable, most of the
compute is just 6 matmuls:
4 from Self-Attention
2 from MLP
Vaswani et al, “Attention is all you need,” NeurIPS2017
Stanford CS231n 10th Anniversary Lecture 8 - 93 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| The Transformer
Transformer Block A Transformer is just a stack of
identical Transformer blocks!
Input: Set of vectors x
Output: Set of vectors y They have not changed much since
2017… but have gotten a lot bigger
Self-Attention is the only
interaction between vectors Original: [Vaswani et al, 2017]
12 blocks, D=1024, H=16, N=512
LayerNorm and MLP work on 213M params
each vector independently
Highly scalable and
parallelizable, most of the
compute is just 6 matmuls:
4 from Self-Attention
2 from MLP
Vaswani et al, “Attention is all you need,” NeurIPS2017 |
| Stanford CS231n 10th Anniversary Lecture 8 - 93 April 24, 2025 |


[Page contains 3 image(s)]


---
## Page 94
---


The Transformer
Transformer Block A Transformer is just a stack of
identical Transformer blocks!
Input: Set of vectors x
Output: Set of vectors y They have not changed much since
2017… but have gotten a lot bigger
Self-Attention is the only
interaction between vectors Original: [Vaswani et al, 2017]
12 blocks, D=1024, H=16, N=512
LayerNorm and MLP work on 213M params
each vector independently
GPT-2: [Radford et al, 2019]
Highly scalable and 48 blocks, D=1600, H=25, N=1024
parallelizable, most of the 1.5B params
compute is just 6 matmuls:
4 from Self-Attention
2 from MLP
Vaswani et al, “Attention is all you need,” NeurIPS2017
Stanford CS231n 10th Anniversary Lecture 8 - 94 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| The Transformer
Transformer Block A Transformer is just a stack of
identical Transformer blocks!
Input: Set of vectors x
Output: Set of vectors y They have not changed much since
2017… but have gotten a lot bigger
Self-Attention is the only
interaction between vectors Original: [Vaswani et al, 2017]
12 blocks, D=1024, H=16, N=512
LayerNorm and MLP work on 213M params
each vector independently
GPT-2: [Radford et al, 2019]
Highly scalable and 48 blocks, D=1600, H=25, N=1024
parallelizable, most of the 1.5B params
compute is just 6 matmuls:
4 from Self-Attention
2 from MLP
Vaswani et al, “Attention is all you need,” NeurIPS2017 |
| Stanford CS231n 10th Anniversary Lecture 8 - 94 April 24, 2025 |


[Page contains 3 image(s)]


---
## Page 95
---


The Transformer
Transformer Block A Transformer is just a stack of
identical Transformer blocks!
Input: Set of vectors x
Output: Set of vectors y They have not changed much since
2017… but have gotten a lot bigger
Self-Attention is the only
interaction between vectors Original: [Vaswani et al, 2017]
12 blocks, D=1024, H=16, N=512
LayerNorm and MLP work on 213M params
each vector independently
GPT-2: [Radford et al, 2019]
Highly scalable and 48 blocks, D=1600, H=25, N=1024
parallelizable, most of the 1.5B params
compute is just 6 matmuls:
GPT-3: [Brown et al, 2020]
4 from Self-Attention 96 blocks, D=12288, H=96, N=2048
2 from MLP 175B params
Vaswani et al, “Attention is all you need,” NeurIPS2017
Stanford CS231n 10th Anniversary Lecture 8 - 95 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| The Transformer
Transformer Block A Transformer is just a stack of
identical Transformer blocks!
Input: Set of vectors x
Output: Set of vectors y They have not changed much since
2017… but have gotten a lot bigger
Self-Attention is the only
interaction between vectors Original: [Vaswani et al, 2017]
12 blocks, D=1024, H=16, N=512
LayerNorm and MLP work on 213M params
each vector independently
GPT-2: [Radford et al, 2019]
Highly scalable and 48 blocks, D=1600, H=25, N=1024
parallelizable, most of the 1.5B params
compute is just 6 matmuls:
GPT-3: [Brown et al, 2020]
4 from Self-Attention 96 blocks, D=12288, H=96, N=2048
2 from MLP 175B params
Vaswani et al, “Attention is all you need,” NeurIPS2017 |
| Stanford CS231n 10th Anniversary Lecture 8 - 95 April 24, 2025 |


[Page contains 3 image(s)]


---
## Page 96
---


Transformers for Language Modeling (LLM)
Learn an embedding matrix at the start of
the model to convert words into vectors.
Given vocab size V and model dimension
D, it’s a lookup table of shape [V x D]
Embedding Matrix
[V x D]
Attention is all you
Stanford CS231n 10th Anniversary Lecture 8 - 96 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Transformers for Language Modeling (LLM)
Learn an embedding matrix at the start of
the model to convert words into vectors.
Given vocab size V and model dimension
D, it’s a lookup table of shape [V x D]
Embedding Matrix
[V x D]
Attention is all you |
| Stanford CS231n 10th Anniversary Lecture 8 - 96 April 24, 2025 |


[Page contains 2 image(s)]


---
## Page 97
---


Transformers for Language Modeling (LLM)
Learn an embedding matrix at the start of
the model to convert words into vectors.
Given vocab size V and model dimension
D, it’s a lookup table of shape [V x D]
Use masked attention inside each
transformer block so each token can only
see the ones before it
Embedding Matrix
[V x D]
Attention is all you
Stanford CS231n 10th Anniversary Lecture 8 - 97 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Transformers for Language Modeling (LLM)
Learn an embedding matrix at the start of
the model to convert words into vectors.
Given vocab size V and model dimension
D, it’s a lookup table of shape [V x D]
Use masked attention inside each
transformer block so each token can only
see the ones before it
Embedding Matrix
[V x D]
Attention is all you |
| Stanford CS231n 10th Anniversary Lecture 8 - 97 April 24, 2025 |


[Page contains 2 image(s)]


---
## Page 98
---


Transformers for Language Modeling (LLM)
is all you need
Learn an embedding matrix at the start of
the model to convert words into vectors.
Projection Matrix
[D x V]
Given vocab size V and model dimension
D, it’s a lookup table of shape [V x D]
Use masked attention inside each
transformer block so each token can only
see the ones before it
At the end, learn a projection matrix of
shape [D x V] to project each D-dim
vector to a V-dim vector of scores for
each element of the vocabulary.
Embedding Matrix
[V x D]
Attention is all you
Stanford CS231n 10th Anniversary Lecture 8 - 98 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Transformers for Language Modeling (LLM)
is all you need
Learn an embedding matrix at the start of
the model to convert words into vectors.
Projection Matrix
[D x V]
Given vocab size V and model dimension
D, it’s a lookup table of shape [V x D]
Use masked attention inside each
transformer block so each token can only
see the ones before it
At the end, learn a projection matrix of
shape [D x V] to project each D-dim
vector to a V-dim vector of scores for
each element of the vocabulary.
Embedding Matrix
[V x D]
Attention is all you |
| Stanford CS231n 10th Anniversary Lecture 8 - 98 April 24, 2025 |


[Page contains 2 image(s)]


---
## Page 99
---


Transformers for Language Modeling (LLM)
is all you need
Learn an embedding matrix at the start of
the model to convert words into vectors.
Projection Matrix
[D x V]
Given vocab size V and model dimension
D, it’s a lookup table of shape [V x D]
Use masked attention inside each
transformer block so each token can only
see the ones before it
At the end, learn a projection matrix of
shape [D x V] to project each D-dim
vector to a V-dim vector of scores for
each element of the vocabulary.
Train to predict next token using softmax Embedding Matrix
[V x D]
+ cross-entropy loss
Attention is all you
Stanford CS231n 10th Anniversary Lecture 8 - 99 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Transformers for Language Modeling (LLM)
is all you need
Learn an embedding matrix at the start of
the model to convert words into vectors.
Projection Matrix
[D x V]
Given vocab size V and model dimension
D, it’s a lookup table of shape [V x D]
Use masked attention inside each
transformer block so each token can only
see the ones before it
At the end, learn a projection matrix of
shape [D x V] to project each D-dim
vector to a V-dim vector of scores for
each element of the vocabulary.
Train to predict next token using softmax Embedding Matrix
[V x D]
+ cross-entropy loss
Attention is all you |
| Stanford CS231n 10th Anniversary Lecture 8 - 99 April 24, 2025 |


[Page contains 2 image(s)]


---
## Page 100
---


Vision Transformers (ViT)
Input image:
e.g. 224x224x3
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image
Recognition at Scale”, ICLR 2021
Stanford CS231n 10th Anniversary Lecture 8 - 100 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Vision Transformers (ViT)
Input image:
e.g. 224x224x3
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image
Recognition at Scale”, ICLR 2021 |
| Stanford CS231n 10th Anniversary Lecture 8 - 100 April 24, 2025 |


[Page contains 9 image(s)]


---
## Page 101
---


Vision Transformers (ViT)
Input image:
e.g. 224x224x3
Break into patches
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3
Recognition at Scale”, ICLR 2021
Stanford CS231n 10th Anniversary Lecture 8 - 101 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Vision Transformers (ViT)
Input image:
e.g. 224x224x3
Break into patches
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3
Recognition at Scale”, ICLR 2021 |
| Stanford CS231n 10th Anniversary Lecture 8 - 101 April 24, 2025 |


[Page contains 18 image(s)]


---
## Page 102
---


Vision Transformers (ViT)
Input image:
e.g. 224x224x3
Break into patches Flatten and apply a linear
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D
Recognition at Scale”, ICLR 2021
Stanford CS231n 10th Anniversary Lecture 8 - 102 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Vision Transformers (ViT)
Input image:
e.g. 224x224x3
Break into patches Flatten and apply a linear
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D
Recognition at Scale”, ICLR 2021 |
| Stanford CS231n 10th Anniversary Lecture 8 - 102 April 24, 2025 |


[Page contains 18 image(s)]


---
## Page 103
---


Vision Transformers (ViT)
Q: Any other way to
describe this operation?
Input image:
e.g. 224x224x3
Break into patches Flatten and apply a linear
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D
Recognition at Scale”, ICLR 2021
Stanford CS231n 10th Anniversary Lecture 8 - 103 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Vision Transformers (ViT)
Q: Any other way to
describe this operation?
Input image:
e.g. 224x224x3
Break into patches Flatten and apply a linear
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D
Recognition at Scale”, ICLR 2021 |
| Stanford CS231n 10th Anniversary Lecture 8 - 103 April 24, 2025 |


[Page contains 18 image(s)]


---
## Page 104
---


Vision Transformers (ViT)
Q: Any other way to
describe this operation?
A: 16x16 conv with stride
16, 3 input channels, D
output channels
Input image:
e.g. 224x224x3
Break into patches Flatten and apply a linear
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D
Recognition at Scale”, ICLR 2021
Stanford CS231n 10th Anniversary Lecture 8 - 104 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Vision Transformers (ViT)
Q: Any other way to
describe this operation?
A: 16x16 conv with stride
16, 3 input channels, D
output channels
Input image:
e.g. 224x224x3
Break into patches Flatten and apply a linear
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D
Recognition at Scale”, ICLR 2021 |
| Stanford CS231n 10th Anniversary Lecture 8 - 104 April 24, 2025 |


[Page contains 18 image(s)]


---
## Page 105
---


Vision Transformers (ViT)
Input image:
e.g. 224x224x3
D-dim vector per patch
Break into patches Flatten and apply a linear are the input vectors to
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D the Transformer
Recognition at Scale”, ICLR 2021
Stanford CS231n 10th Anniversary Lecture 8 - 105 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Vision Transformers (ViT)
Input image:
e.g. 224x224x3
D-dim vector per patch
Break into patches Flatten and apply a linear are the input vectors to
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D the Transformer
Recognition at Scale”, ICLR 2021 |
| Stanford CS231n 10th Anniversary Lecture 8 - 105 April 24, 2025 |


[Page contains 20 image(s)]


---
## Page 106
---


Vision Transformers (ViT)
Use positional
encoding to tell
the transformer
the 2D position
of each patch
Input image:
e.g. 224x224x3
D-dim vector per patch
Break into patches Flatten and apply a linear are the input vectors to
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D the Transformer
Recognition at Scale”, ICLR 2021
Stanford CS231n 10th Anniversary Lecture 8 - 106 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Vision Transformers (ViT)
Use positional
encoding to tell
the transformer
the 2D position
of each patch
Input image:
e.g. 224x224x3
D-dim vector per patch
Break into patches Flatten and apply a linear are the input vectors to
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D the Transformer
Recognition at Scale”, ICLR 2021 |
| Stanford CS231n 10th Anniversary Lecture 8 - 106 April 24, 2025 |


[Page contains 20 image(s)]


---
## Page 107
---


Vision Transformers (ViT)
Don’t use any
masking; each
image patch can
look at all other
image patches
Use positional
encoding to tell
the transformer
the 2D position
of each patch
Input image:
e.g. 224x224x3
D-dim vector per patch
Break into patches Flatten and apply a linear are the input vectors to
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D the Transformer
Recognition at Scale”, ICLR 2021
Stanford CS231n 10th Anniversary Lecture 8 - 107 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Vision Transformers (ViT)
Don’t use any
masking; each
image patch can
look at all other
image patches
Use positional
encoding to tell
the transformer
the 2D position
of each patch
Input image:
e.g. 224x224x3
D-dim vector per patch
Break into patches Flatten and apply a linear are the input vectors to
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D the Transformer
Recognition at Scale”, ICLR 2021 |
| Stanford CS231n 10th Anniversary Lecture 8 - 107 April 24, 2025 |


[Page contains 20 image(s)]


---
## Page 108
---


Vision Transformers (ViT)
Transformer
gives an output
vector per patch
Don’t use any
masking; each
image patch can
look at all other
image patches
Use positional
encoding to tell
the transformer
the 2D position
of each patch
Input image:
e.g. 224x224x3
D-dim vector per patch
Break into patches Flatten and apply a linear are the input vectors to
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D the Transformer
Recognition at Scale”, ICLR 2021
Stanford CS231n 10th Anniversary Lecture 8 - 108 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Vision Transformers (ViT)
Transformer
gives an output
vector per patch
Don’t use any
masking; each
image patch can
look at all other
image patches
Use positional
encoding to tell
the transformer
the 2D position
of each patch
Input image:
e.g. 224x224x3
D-dim vector per patch
Break into patches Flatten and apply a linear are the input vectors to
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D the Transformer
Recognition at Scale”, ICLR 2021 |
| Stanford CS231n 10th Anniversary Lecture 8 - 108 April 24, 2025 |


[Page contains 20 image(s)]


---
## Page 109
---


Average pool NxD vectors to
Vision Transformers (ViT) 1xD, apply a linear layer Transformer
D=>C to predict class scores
gives an output
vector per patch
Pooling
Don’t use any
masking; each
image patch can
look at all other
image patches
Use positional
encoding to tell
the transformer
the 2D position
of each patch
Input image:
e.g. 224x224x3
D-dim vector per patch
Break into patches Flatten and apply a linear are the input vectors to
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D the Transformer
Recognition at Scale”, ICLR 2021
Stanford CS231n 10th Anniversary Lecture 8 - 109 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Average pool NxD vectors to
Vision Transformers (ViT) 1xD, apply a linear layer Transformer
D=>C to predict class scores
gives an output
vector per patch
Pooling
Don’t use any
masking; each
image patch can
look at all other
image patches
Use positional
encoding to tell
the transformer
the 2D position
of each patch
Input image:
e.g. 224x224x3
D-dim vector per patch
Break into patches Flatten and apply a linear are the input vectors to
Dosovitskiyet al, “An Image is Worth
16x16 Words: Transformers for Image e.g. 16x16x3 transform 768 => D the Transformer
Recognition at Scale”, ICLR 2021 |
| Stanford CS231n 10th Anniversary Lecture 8 - 109 April 24, 2025 |


[Page contains 20 image(s)]


---
## Page 110
---


Tweaking Transformers
y y y y
1 2 3 4
The Transformer architecture has not
Layer Normalization
changed much since 2017.
+
But a few changes have become common:
MLP MLP MLP MLP
Layer Normalization
+
Self-Attention
x x x x
1 2 3 4
Stanford CS231n 10th Anniversary Lecture 8 - 110 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Tweaking Transformers
y y y y
1 2 3 4
The Transformer architecture has not
Layer Normalization
changed much since 2017.
+
But a few changes have become common:
MLP MLP MLP MLP
Layer Normalization
+
Self-Attention
x x x x
1 2 3 4 |
| Stanford CS231n 10th Anniversary Lecture 8 - 110 April 24, 2025 |


### Table 2

|  |  |  |


---
## Page 111
---


Pre-Norm Transformer
y y y y
1 2 3 4
Layer Normalization
+
Layer normalization is outside
the residual connections
MLP MLP MLP MLP
Kind of weird, the model can’t
actually learn the identify function
Layer Normalization
+
Self-Attention
x x x x
1 2 3 4
Baevski& Auli, “Adaptive Input Representations for Neural Language Modeling”, arXiv2018
Stanford CS231n 10th Anniversary Lecture 8 - 111 April 24, 2025

[Page contains 2 table(s)]


### Table 1

| Pre-Norm Transformer
y y y y
1 2 3 4
Layer Normalization
+
Layer normalization is outside
the residual connections
MLP MLP MLP MLP
Kind of weird, the model can’t
actually learn the identify function
Layer Normalization
+
Self-Attention
x x x x
1 2 3 4
Baevski& Auli, “Adaptive Input Representations for Neural Language Modeling”, arXiv2018 |
| Stanford CS231n 10th Anniversary Lecture 8 - 111 April 24, 2025 |


### Table 2

|  |  |  |


---
## Page 112
---


Pre-Norm Transformer
y y y y
1 2 3 4
+
Layer normalization is outside
the residual connections MLP MLP MLP MLP
Kind of weird, the model can’t
Layer Normalization
actually learn the identify function
+
Solution: Move layer
normalization before the Self-
Self-Attention
Attention and MLP, inside the
residual connections. Training is Layer Normalization
more stable.
x x x x
1 2 3 4
Baevski& Auli, “Adaptive Input Representations for Neural Language Modeling”, arXiv2018
Stanford CS231n 10th Anniversary Lecture 8 - 112 April 24, 2025

[Page contains 3 table(s)]


### Table 1

| Pre-Norm Transformer
y y y y
1 2 3 4
+
Layer normalization is outside
the residual connections MLP MLP MLP MLP
Kind of weird, the model can’t
Layer Normalization
actually learn the identify function
+
Solution: Move layer
normalization before the Self-
Self-Attention
Attention and MLP, inside the
residual connections. Training is Layer Normalization
more stable.
x x x x
1 2 3 4
Baevski& Auli, “Adaptive Input Representations for Neural Language Modeling”, arXiv2018 |
| Stanford CS231n 10th Anniversary Lecture 8 - 112 April 24, 2025 |


### Table 2

|  |  |  |


### Table 3

|  |
|  |


---
## Page 113
---


RMSNorm
y y y y
1 2 3 4
Replace Layer Normalization
with Root-Mean-Square +
Normalization (RMSNorm)
MLP MLP MLP MLP
Input: x [shape D]
Output: y [shape D]
Weight: 𝛾 [shape D] RMSNorm
𝑥 +
𝑖
𝑦 = ∗ 𝛾
𝑖 𝑖
𝑅𝑀𝑆(𝑥)
Self-Attention
1 𝑁
𝑅𝑀𝑆 𝑥 = 𝜀 + ෍ 𝑥2 RMSNorm
𝑁 𝑖
𝑖=1
Training is a bit more stable
x x x x
1 2 3 4
Zhang and Sennrich, “Root Mean Square Layer Normalization”, NeurIPS2019
Stanford CS231n 10th Anniversary Lecture 8 - 113 April 24, 2025

[Page contains 4 table(s)]


### Table 1

| RMSNorm
y y y y
1 2 3 4
Replace Layer Normalization
with Root-Mean-Square +
Normalization (RMSNorm)
MLP MLP MLP MLP
Input: x [shape D]
Output: y [shape D]
Weight: 𝛾 [shape D] RMSNorm
𝑥 +
𝑖
𝑦 = ∗ 𝛾
𝑖 𝑖
𝑅𝑀𝑆(𝑥)
Self-Attention
1 𝑁
𝑅𝑀𝑆 𝑥 = 𝜀 + ෍ 𝑥2 RMSNorm
𝑁 𝑖
𝑖=1
Training is a bit more stable
x x x x
1 2 3 4
Zhang and Sennrich, “Root Mean Square Layer Normalization”, NeurIPS2019 |
| Stanford CS231n 10th Anniversary Lecture 8 - 113 April 24, 2025 |


### Table 2

| Replace Layer Normalization
with Root-Mean-Square
Normalization (RMSNorm)
Input: x [shape D]
Output: y [shape D]
Weight: 𝛾 [shape D]
𝑥
𝑖
𝑦 = ∗ 𝛾
𝑖 𝑖
𝑅𝑀𝑆(𝑥)
1 𝑁
𝑅𝑀𝑆 𝑥 = 𝜀 + ෍ 𝑥2
𝑁 𝑖
𝑖=1
Training is a bit more stable
g and Sennrich, “Root Mean Square Layer Normalizatio |
|  |


### Table 3

|  |  |  |


### Table 4

|  |
|  |


---
## Page 114
---


SwiGLU MLP
y y y y
1 2 3 4
Classic MLP:
+
Input: X [N x D]
Weights: W [D x 4D]
1 MLP MLP MLP MLP
W [4D x D]
2
Output: Y = σ(XW )W [N x D]
1 2
RMSNorm
+
Self-Attention
RMSNorm
x x x x
1 2 3 4
Shazeer, “GLU Variants Improve Transformers”, 2020
Stanford CS231n 10th Anniversary Lecture 8 - 114 April 24, 2025

[Page contains 3 table(s)]


### Table 1

| SwiGLU MLP
y y y y
1 2 3 4
Classic MLP:
+
Input: X [N x D]
Weights: W [D x 4D]
1 MLP MLP MLP MLP
W [4D x D]
2
Output: Y = σ(XW )W [N x D]
1 2
RMSNorm
+
Self-Attention
RMSNorm
x x x x
1 2 3 4
Shazeer, “GLU Variants Improve Transformers”, 2020 |
| Stanford CS231n 10th Anniversary Lecture 8 - 114 April 24, 2025 |


### Table 2

|  |  |  |


### Table 3

|  |
|  |


---
## Page 115
---


SwiGLU MLP
y y y y
1 2 3 4
Classic MLP:
+
Input: X [N x D]
Weights: W [D x 4D]
1 MLP MLP MLP MLP
W [4D x D]
2
Output: Y = σ(XW )W [N x D]
1 2
RMSNorm
SwiGLU MLP:
+
Input: X [N x D]
Self-Attention
Weights: W , W [D x H]
1 2
W [H x D]
RMSNorm
3
Output:
𝑌 = 𝜎 𝑋𝑊 ⊙𝑋𝑊 𝑊
1 2 3
Setting H = 8D/3 keeps
x x x x
same total params
1 2 3 4
Shazeer, “GLU Variants Improve Transformers”, 2020
Stanford CS231n 10th Anniversary Lecture 8 - 115 April 24, 2025

[Page contains 3 table(s)]


### Table 1

| SwiGLU MLP
y y y y
1 2 3 4
Classic MLP:
+
Input: X [N x D]
Weights: W [D x 4D]
1 MLP MLP MLP MLP
W [4D x D]
2
Output: Y = σ(XW )W [N x D]
1 2
RMSNorm
SwiGLU MLP:
+
Input: X [N x D]
Self-Attention
Weights: W , W [D x H]
1 2
W [H x D]
RMSNorm
3
Output:
𝑌 = 𝜎 𝑋𝑊 ⊙𝑋𝑊 𝑊
1 2 3
Setting H = 8D/3 keeps
x x x x
same total params
1 2 3 4
Shazeer, “GLU Variants Improve Transformers”, 2020 |
| Stanford CS231n 10th Anniversary Lecture 8 - 115 April 24, 2025 |


### Table 2

|  |  |  |


### Table 3

|  |
|  |


---
## Page 116
---


SwiGLU MLP
y y y y
1 2 3 4
Classic MLP:
+
Input: X [N x D]
Weights: W [D x 4D]
1 MLP MLP MLP MLP
W [4D x D]
2
Output: Y = σ(XW )W [N x D]
1 2
RMSNorm
SwiGLU MLP:
+
We offer no explanation as
Input: X [N x D] to why these architectures
Self-Attention
Weights: W , W [D x H] seem to work; we attribute
1 2
W [H x D] their success, as all else,
RMSNorm
3
Output: to divine benevolence.
𝑌 = 𝜎 𝑋𝑊 ⊙𝑋𝑊 𝑊
1 2 3
Setting H = 8D/3 keeps
x x x x
same total params
1 2 3 4
Shazeer, “GLU Variants Improve Transformers”, 2020
Stanford CS231n 10th Anniversary Lecture 8 - 116 April 24, 2025

[Page contains 3 table(s)]


### Table 1

| SwiGLU MLP
y y y y
1 2 3 4
Classic MLP:
+
Input: X [N x D]
Weights: W [D x 4D]
1 MLP MLP MLP MLP
W [4D x D]
2
Output: Y = σ(XW )W [N x D]
1 2
RMSNorm
SwiGLU MLP:
+
We offer no explanation as
Input: X [N x D] to why these architectures
Self-Attention
Weights: W , W [D x H] seem to work; we attribute
1 2
W [H x D] their success, as all else,
RMSNorm
3
Output: to divine benevolence.
𝑌 = 𝜎 𝑋𝑊 ⊙𝑋𝑊 𝑊
1 2 3
Setting H = 8D/3 keeps
x x x x
same total params
1 2 3 4
Shazeer, “GLU Variants Improve Transformers”, 2020 |
| Stanford CS231n 10th Anniversary Lecture 8 - 116 April 24, 2025 |


### Table 2

|  |  |  |


### Table 3

|  |
|  |


---
## Page 117
---


Mixture of Experts (MoE)
y y y y
1 2 3 4
Learn E separate sets of MLP weights in
each block; each MLP is an expert +
W : [D x 4D] => [E x D x 4D]
1 MLP MLP MLP MLP
W : [4D x D] => [E x 4D x D]
2
RMSNorm
+
Self-Attention
RMSNorm
x x x x
1 2 3 4
Shazeeret al, “Outrageously Large Neural Networks: The Sparsely-Gated Mixture-of-Experts Layer”, 2017
Stanford CS231n 10th Anniversary Lecture 8 - 117 April 24, 2025

[Page contains 4 table(s)]


### Table 1

| Mixture of Experts (MoE)
y y y y
1 2 3 4
Learn E separate sets of MLP weights in
each block; each MLP is an expert +
W : [D x 4D] => [E x D x 4D]
1 MLP MLP MLP MLP
W : [4D x D] => [E x 4D x D]
2
RMSNorm
+
Self-Attention
RMSNorm
x x x x
1 2 3 4
Shazeeret al, “Outrageously Large Neural Networks: The Sparsely-Gated Mixture-of-Experts Layer”, 2017 |
| Stanford CS231n 10th Anniversary Lecture 8 - 117 April 24, 2025 |


### Table 2

|  |  |  |


### Table 3

|  |
|  |


### Table 4

| Outrageously Large Neural Networks: The Sparsely | -Gated Mixture | -of | -Experts Layer |


---
## Page 118
---


Mixture of Experts (MoE)
y y y y
1 2 3 4
Learn E separate sets of MLP weights in
each block; each MLP is an expert +
W : [D x 4D] => [E x D x 4D]
1 MLP MLP MLP MLP
W : [4D x D] => [E x 4D x D]
2
Each token gets routed to A < E of the RMSNorm
experts. These are the active experts.
+
Increases params by E,
Self-Attention
But only increases compute by A
RMSNorm
x x x x
1 2 3 4
Shazeeret al, “Outrageously Large Neural Networks: The Sparsely-Gated Mixture-of-Experts Layer”, 2017
Stanford CS231n 10th Anniversary Lecture 8 - 118 April 24, 2025

[Page contains 4 table(s)]


### Table 1

| Mixture of Experts (MoE)
y y y y
1 2 3 4
Learn E separate sets of MLP weights in
each block; each MLP is an expert +
W : [D x 4D] => [E x D x 4D]
1 MLP MLP MLP MLP
W : [4D x D] => [E x 4D x D]
2
Each token gets routed to A < E of the RMSNorm
experts. These are the active experts.
+
Increases params by E,
Self-Attention
But only increases compute by A
RMSNorm
x x x x
1 2 3 4
Shazeeret al, “Outrageously Large Neural Networks: The Sparsely-Gated Mixture-of-Experts Layer”, 2017 |
| Stanford CS231n 10th Anniversary Lecture 8 - 118 April 24, 2025 |


### Table 2

|  |  |  |


### Table 3

|  |
|  |


### Table 4

| Outrageously Large Neural Networks: The Sparsely | -Gated Mixture | -of | -Experts Layer |


---
## Page 119
---


Mixture of Experts (MoE)
y y y y
1 2 3 4
Learn E separate sets of MLP weights in
each block; each MLP is an expert +
W : [D x 4D] => [E x D x 4D]
1 MLP MLP MLP MLP
W : [4D x D] => [E x 4D x D]
2
Each token gets routed to A < E of the RMSNorm
experts. These are the active experts.
+
Increases params by E,
Self-Attention
But only increases compute by A
RMSNorm
All of the biggest LLMs today (e.g.
GPT4o, GPT4.5, Claude 3.7, Gemini 2.5
Pro, etc) almost certainly use MoE and
have > 1T params; but they don’t publish
x x x x
details anymore
1 2 3 4
Stanford CS231n 10th Anniversary Lecture 8 - 119 April 24, 2025

[Page contains 3 table(s)]


### Table 1

| Mixture of Experts (MoE)
y y y y
1 2 3 4
Learn E separate sets of MLP weights in
each block; each MLP is an expert +
W : [D x 4D] => [E x D x 4D]
1 MLP MLP MLP MLP
W : [4D x D] => [E x 4D x D]
2
Each token gets routed to A < E of the RMSNorm
experts. These are the active experts.
+
Increases params by E,
Self-Attention
But only increases compute by A
RMSNorm
All of the biggest LLMs today (e.g.
GPT4o, GPT4.5, Claude 3.7, Gemini 2.5
Pro, etc) almost certainly use MoE and
have > 1T params; but they don’t publish
x x x x
details anymore
1 2 3 4 |
| Stanford CS231n 10th Anniversary Lecture 8 - 119 April 24, 2025 |


### Table 2

|  |  |  |


### Table 3

|  |
|  |


---
## Page 120
---


Tweaking Transformers
y y y y
1 2 3 4
The Transformer architecture has not
changed much since 2017. +
But a few changes have become common:
MLP MLP MLP MLP
- Pre-Norm: Move normalization inside
residual
- RMSNorm: Different normalization layer
RMSNorm
- SwiGLU: Different MLP architecture
- Mixture of Experts (MoE): Learn E +
different MLPs, use A < E of them per
Self-Attention
token. Massively increase params,
modest increase to compute cost.
RMSNorm
x x x x
1 2 3 4
Stanford CS231n 10th Anniversary Lecture 8 - 120 April 24, 2025

[Page contains 3 table(s)]


### Table 1

| Tweaking Transformers
y y y y
1 2 3 4
The Transformer architecture has not
changed much since 2017. +
But a few changes have become common:
MLP MLP MLP MLP
- Pre-Norm: Move normalization inside
residual
- RMSNorm: Different normalization layer
RMSNorm
- SwiGLU: Different MLP architecture
- Mixture of Experts (MoE): Learn E +
different MLPs, use A < E of them per
Self-Attention
token. Massively increase params,
modest increase to compute cost.
RMSNorm
x x x x
1 2 3 4 |
| Stanford CS231n 10th Anniversary Lecture 8 - 120 April 24, 2025 |


### Table 2

|  |  |  |


### Table 3

|  |
|  |


---
## Page 121
---


Summary: Attention + Transformers
Attention: A new primitive that Transformer: A neural
operates on sets of vectors network architecture that
uses attention everywhere
Transformers are the
backbone of all large
AI models today!
Used for language,
vision, speech, …
Stanford CS231n 10th Anniversary Lecture 8 - 121 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Summary: Attention + Transformers
Attention: A new primitive that Transformer: A neural
operates on sets of vectors network architecture that
uses attention everywhere
Transformers are the
backbone of all large
AI models today!
Used for language,
vision, speech, … |
| Stanford CS231n 10th Anniversary Lecture 8 - 121 April 24, 2025 |


[Page contains 3 image(s)]


---
## Page 122
---


Next Time:
Detection, Segmentation,
Visualization
Stanford CS231n 10th Anniversary Lecture 8 - 122 April 24, 2025

[Page contains 1 table(s)]


### Table 1

| Next Time:
Detection, Segmentation,
Visualization |
| Stanford CS231n 10th Anniversary Lecture 8 - 122 April 24, 2025 |
