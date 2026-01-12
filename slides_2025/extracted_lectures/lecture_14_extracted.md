# lecture_14

Extracted using pdfplumber



---
## Page 1
---


Lecture 14:
Generative Models (part 2)
Stanford CS231n 10th Anniversary Lecture 14 - 1 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture 14:
Generative Models (part 2) |
| Stanford CS231n 10th Anniversary Lecture 14 - 1 May 20, 2025 |


---
## Page 2
---


Administrative
● Assignment 3 due on 5/30
● Project Report due on 6/4
Stanford CS231n 10th Anniversary Lecture 14 - 2 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Administrative
● Assignment 3 due on 5/30
● Project Report due on 6/4 |
| Stanford CS231n 10th Anniversary Lecture 14 - 2 May 20, 2025 |


---
## Page 3
---


Last Time: Generative vs Discriminative Models
Density Function
Discriminative Model:
Data: x
p(x) assigns a positive
Learn a probability
number to each possible
distribution p(y|x)
x; higher numbers mean
x is more likely.
Generative Model: Density functions are
Learn a probability normalized:
distribution p(x)
න 𝑝 𝑥 𝑑𝑥 = 1
𝑋
Label: y
Conditional Generative
Cat Different values of x
Model: Learn p(x|y)
compete for density
Stanford CS231n 10th Anniversary Lecture 14 - 3 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Last Time: Generative vs Discriminative Models
Density Function
Discriminative Model:
Data: x
p(x) assigns a positive
Learn a probability
number to each possible
distribution p(y|x)
x; higher numbers mean
x is more likely.
Generative Model: Density functions are
Learn a probability normalized:
distribution p(x)
න 𝑝 𝑥 𝑑𝑥 = 1
𝑋
Label: y
Conditional Generative
Cat Different values of x
Model: Learn p(x|y)
compete for density |  |  |
|  | x; higher numbers m
x is more likely.
Density functions are
normalized:
න 𝑝 𝑥 𝑑𝑥 = 1
𝑋
Different values of x
compete for density |  |
| Stanford CS231n 10th Anniversary Lect | ure 14 - 3 May 20, 20 | 25 |
|  |  |  |


[Page contains 1 image(s)]


---
## Page 4
---


Figure adapted from Ian
Goodfellow, Tutorial on
Last Time: Generative Models Generative Adversarial
Networks, 2017
Model can Generative models Cannot compute p(x) but
compute P(x) can sample from P(x)
Iterative
Explicit density Implicit density
procedure to
Really Can directly approximate
Approximate
compute sample samples
P(x)
P(x) from P(x) from P(x)
Tractable density Approximate density Direct Indirect
Variational Autoencoder Generative Adversarial
Autoregressive Diffusion Models
(VAE) Network (GAN)
Stanford CS231n 10th Anniversary Lecture 14 - 4 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Figure adapted from Ian
Goodfellow, Tutorial on
Last Time: Generative Models Generative Adversarial
Networks, 2017
Model can Generative models Cannot compute p(x) but
compute P(x) can sample from P(x)
Iterative
Explicit density Implicit density
procedure to
Really Can directly approximate
Approximate
compute sample samples
P(x)
P(x) from P(x) from P(x)
Tractable density Approximate density Direct Indirect
Variational Autoencoder Generative Adversarial
Autoregressive Diffusion Models
(VAE) Network (GAN) |
| Stanford CS231n 10th Anniversary Lecture 14 - 4 May 20, 2025 |


---
## Page 5
---


Last Time: Autoregressive Models
Treat data as a sequence
(e.g. image as sequence of pixels)
𝑝 𝑥 = 𝑝 𝑥 , 𝑥 , … , 𝑥
1 2 𝑁
= 𝑝 𝑥 𝑝 𝑥 𝑥 )𝑝 𝑥 𝑥 , 𝑥 ) …
…
1 2 1 3 1 2
= ς𝑇 𝑝 𝑥 𝑥 , … , 𝑥 )
𝑡=1 𝑡 1 𝑡−1
Model with an RNN or Transformer
…
… … …
Stanford CS231n 10th Anniversary Lecture 14 - 5 May 20, 2025

[Page contains 7 table(s)]


### Table 1

| Last Time: Autoregressive Models
Treat data as a sequence
(e.g. image as sequence of pixels)
𝑝 𝑥 = 𝑝 𝑥 , 𝑥 , … , 𝑥
1 2 𝑁
= 𝑝 𝑥 𝑝 𝑥 𝑥 )𝑝 𝑥 𝑥 , 𝑥 ) …
…
1 2 1 3 1 2
= ς𝑇 𝑝 𝑥 𝑥 , … , 𝑥 )
𝑡=1 𝑡 1 𝑡−1
Model with an RNN or Transformer
…
… … … |
| Stanford CS231n 10th Anniversary Lecture 14 - 5 May 20, 2025 |


### Table 2

|  |  |
|  |  |
|  |  |


### Table 3

|  |  |
|  |  |
|  |  |


### Table 4

|  |  |
|  |  |
|  |  |


### Table 5

|  |  |
|  |  |
|  |  |


### Table 6

|  |  |
|  |  |
|  |  |


### Table 7

|  |  |
|  |  |
|  |  |


[Page contains 1 image(s)]


---
## Page 6
---


Last Time: Variational Autoencoders
Jointly train encoder q and decoder p to maximize
the variational lower bound on the data likelihood
Also called Evidence Lower Bound (ELBo)
log 𝑝 (𝑥) ≥ 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝜃 𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙
Encoder Network Decoder Network
𝑞 𝑧 | 𝑥 = 𝑁(𝜇 , Σ ) 𝑝 𝑥 | 𝑧 = 𝑁(𝜇 , 𝜎2)
𝜙 𝑧|𝑥 𝑧|𝑥 𝜃 𝑥|𝑧
𝜇 Σ 𝜇
𝑧|𝑥 𝑧|𝑥 𝑥|𝑧
𝑥 𝑧
Stanford CS231n 10th Anniversary Lecture 14 - 6 May 20, 2025

[Page contains 4 table(s)]


### Table 1

| Last Time: Variational Autoencoders
Jointly train encoder q and decoder p to maximize
the variational lower bound on the data likelihood
Also called Evidence Lower Bound (ELBo)
log 𝑝 (𝑥) ≥ 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝜃 𝑧~𝑞 (𝑧|𝑥) 𝜃 𝐾𝐿 𝜙
𝜙
Encoder Network Decoder Network
𝑞 𝑧 | 𝑥 = 𝑁(𝜇 , Σ ) 𝑝 𝑥 | 𝑧 = 𝑁(𝜇 , 𝜎2)
𝜙 𝑧|𝑥 𝑧|𝑥 𝜃 𝑥|𝑧
𝜇 Σ 𝜇
𝑧|𝑥 𝑧|𝑥 𝑥|𝑧
𝑥 𝑧 |
| Stanford CS231n 10th Anniversary Lecture 14 - 6 May 20, 2025 |


### Table 2

|  |
| 𝜇
𝑧|𝑥 |


### Table 3

|  |
| Σ
𝑧|𝑥 |


### Table 4

|  |
| 𝜇
𝑥|𝑧 |


---
## Page 7
---


Figure adapted from Ian
Goodfellow, Tutorial on
Today: More Generative Models Generative Adversarial
Networks, 2017
Model can Generative models Cannot compute p(x) but
compute P(x) can sample from P(x)
Iterative
Explicit density Implicit density
procedure to
Really Can directly approximate
Approximate
compute sample samples
P(x)
P(x) from P(x) from P(x)
Tractable density Approximate density Direct Indirect
Variational Autoencoder Generative Adversarial
Autoregressive Diffusion Models
(VAE) Network (GAN)
Last Time Today
Stanford CS231n 10th Anniversary Lecture 14 - 7 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Figure adapted from Ian
Goodfellow, Tutorial on
Today: More Generative Models Generative Adversarial
Networks, 2017
Model can Generative models Cannot compute p(x) but
compute P(x) can sample from P(x)
Iterative
Explicit density Implicit density
procedure to
Really Can directly approximate
Approximate
compute sample samples
P(x)
P(x) from P(x) from P(x)
Tractable density Approximate density Direct Indirect
Variational Autoencoder Generative Adversarial
Autoregressive Diffusion Models
(VAE) Network (GAN)
Last Time Today |
| Stanford CS231n 10th Anniversary Lecture 14 - 7 May 20, 2025 |


---
## Page 8
---


Generative Adversarial Networks
(GANs)
Stanford CS231n 10th Anniversary Lecture 14 - 8 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Generative Adversarial Networks
(GANs) |
| Stanford CS231n 10th Anniversary Lecture 14 - 8 May 20, 2025 |


---
## Page 9
---


Generative Models So Far
Autoregressive Models directly maximize likelihood of training data:
𝑁
𝑝 𝑥 = ෑ 𝑝 (𝑥 |𝑥 , …, 𝑥 )
𝜃 𝜃 𝑖 1 𝑖−1
𝑖=1
Variational Autoencoders introduce a latent z, and maximize a lower bound:
𝑝 𝑥 = න 𝑝 𝑥 𝑧 𝑝 𝑧 𝑑𝑧 ≥ 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧 𝑥
𝜃 𝜃 𝑧~𝑞 𝜃 𝐾𝐿 𝜙
𝜙
𝑍
Stanford CS231n 10th Anniversary Lecture 14 - 9 May 20, 2025

[Page contains 2 table(s)]


### Table 1

| Generative Models So Far
Autoregressive Models directly maximize likelihood of training data:
𝑁
𝑝 𝑥 = ෑ 𝑝 (𝑥 |𝑥 , …, 𝑥 )
𝜃 𝜃 𝑖 1 𝑖−1
𝑖=1
Variational Autoencoders introduce a latent z, and maximize a lower bound:
𝑝 𝑥 = න 𝑝 𝑥 𝑧 𝑝 𝑧 𝑑𝑧 ≥ 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧 𝑥
𝜃 𝜃 𝑧~𝑞 𝜃 𝐾𝐿 𝜙
𝜙
𝑍 |
| Stanford CS231n 10th Anniversary Lecture 14 - 9 May 20, 2025 |


### Table 2

| Autoregressive Models directly maximize likelihood of training data:
𝑁
𝑝 𝑥 = ෑ 𝑝 (𝑥 |𝑥 , …, 𝑥 )
𝜃 𝜃 𝑖 1 𝑖−1
𝑖=1
Variational Autoencoders introduce a latent z, and maximize a lower bound:
𝑝 𝑥 = න 𝑝 𝑥 𝑧 𝑝 𝑧 𝑑𝑧 ≥ 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧 𝑥
𝜃 𝜃 𝑧~𝑞 𝜃 𝐾𝐿 𝜙
𝜙
𝑍 |
| nford CS231n 10th Anniversary Lecture 14 - 9 May 20, 202 |


---
## Page 10
---


Generative Models So Far
Autoregressive Models directly maximize likelihood of training data:
𝑁
𝑝 𝑥 = ෑ 𝑝 (𝑥 |𝑥 , …, 𝑥 )
𝜃 𝜃 𝑖 1 𝑖−1
𝑖=1
Variational Autoencoders introduce a latent z, and maximize a lower bound:
𝑝 𝑥 = න 𝑝 𝑥 𝑧 𝑝 𝑧 𝑑𝑧 ≥ 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧 𝑥
𝜃 𝜃 𝑧~𝑞 𝜃 𝐾𝐿 𝜙
𝜙
𝑍
Generative Adversarial Networks give up on modeling p(x), but allow us to
draw samples from p(x)
Stanford CS231n 10th Anniversary Lecture 14 - 10 May 20, 2025

[Page contains 2 table(s)]


### Table 1

| Generative Models So Far
Autoregressive Models directly maximize likelihood of training data:
𝑁
𝑝 𝑥 = ෑ 𝑝 (𝑥 |𝑥 , …, 𝑥 )
𝜃 𝜃 𝑖 1 𝑖−1
𝑖=1
Variational Autoencoders introduce a latent z, and maximize a lower bound:
𝑝 𝑥 = න 𝑝 𝑥 𝑧 𝑝 𝑧 𝑑𝑧 ≥ 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧 𝑥
𝜃 𝜃 𝑧~𝑞 𝜃 𝐾𝐿 𝜙
𝜙
𝑍
Generative Adversarial Networks give up on modeling p(x), but allow us to
draw samples from p(x) |
| Stanford CS231n 10th Anniversary Lecture 14 - 10 May 20, 2025 |


### Table 2

| Autoregressive Models directly maximize likelihood of training data:
𝑁
𝑝 𝑥 = ෑ 𝑝 (𝑥 |𝑥 , …, 𝑥 )
𝜃 𝜃 𝑖 1 𝑖−1
𝑖=1
Variational Autoencoders introduce a latent z, and maximize a lower bound:
𝑝 𝑥 = න 𝑝 𝑥 𝑧 𝑝 𝑧 𝑑𝑧 ≥ 𝐸 [log 𝑝 (𝑥|𝑧)] − 𝐷 𝑞 𝑧 𝑥 , 𝑝 𝑧
𝑧 𝑥
𝜃 𝜃 𝑧~𝑞 𝜃 𝐾𝐿 𝜙
𝜙
𝑍
Generative Adversarial Networks give up on modeling p(x), but allow us to
draw samples from p(x) |
| nford CS231n 10th Anniversary Lecture 14 - 10 May 20, 202 |


---
## Page 11
---


Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Generative Adversarial Networks
Setup: Have data x drawn from distribution p (x). Want to sample from p
i data data
Stanford CS231n 10th Anniversary Lecture 14 - 11 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Generative Adversarial Networks
Setup: Have data x drawn from distribution p (x). Want to sample from p
i data data |
| Stanford CS231n 10th Anniversary Lecture 14 - 11 May 20, 2025 |


---
## Page 12
---


Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Generative Adversarial Networks
Setup: Have data x drawn from distribution p (x). Want to sample from p
i data data
Idea: Introduce a latent variable z with simple prior p(z) (e.g. unit Gaussian)
Sample 𝑧 ∼ 𝑝(𝑧) and pass to a Generator Network x = G(z)
Then x is a sample from the Generator distribution p . Want p = p !
G G data
Stanford CS231n 10th Anniversary Lecture 14 - 12 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Generative Adversarial Networks
Setup: Have data x drawn from distribution p (x). Want to sample from p
i data data
Idea: Introduce a latent variable z with simple prior p(z) (e.g. unit Gaussian)
Sample 𝑧 ∼ 𝑝(𝑧) and pass to a Generator Network x = G(z)
Then x is a sample from the Generator distribution p . Want p = p !
G G data |
| Stanford CS231n 10th Anniversary Lecture 14 - 12 May 20, 2025 |


---
## Page 13
---


Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Generative Adversarial Networks
Setup: Have data x drawn from distribution p (x). Want to sample from p
i data data
Idea: Introduce a latent variable z with simple prior p(z) (e.g. unit Gaussian)
Sample 𝑧 ∼ 𝑝(𝑧) and pass to a Generator Network x = G(z)
Then x is a sample from the Generator distribution p . Want p = p !
G G data
Generated
Generator
image
Network
Sample
z G
z from p
z
Train Generator Network G to convert
z into fake data x sampled from p
G
Stanford CS231n 10th Anniversary Lecture 14 - 13 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Generative Adversarial Networks
Setup: Have data x drawn from distribution p (x). Want to sample from p
i data data
Idea: Introduce a latent variable z with simple prior p(z) (e.g. unit Gaussian)
Sample 𝑧 ∼ 𝑝(𝑧) and pass to a Generator Network x = G(z)
Then x is a sample from the Generator distribution p . Want p = p !
G G data
Generated
Generator
image
Network
Sample
z G
z from p
z
Train Generator Network G to convert
z into fake data x sampled from p
G |
| Stanford CS231n 10th Anniversary Lecture 14 - 13 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 14
---


Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Generative Adversarial Networks
Setup: Have data x drawn from distribution p (x). Want to sample from p
i data data
Idea: Introduce a latent variable z with simple prior p(z) (e.g. unit Gaussian)
Sample 𝑧 ∼ 𝑝(𝑧) and pass to a Generator Network x = G(z)
Then x is a sample from the Generator distribution p . Want p = p !
G G data
Generated
Generator
Network image Discriminator
Sample Network
z G
Fake
z from p
z
D
Real
Train Generator Network G to convert
z into fake data x sampled from p Train Discriminator Network D
G Real
By fooling the discriminator D to classify data as real or fake
image
Stanford CS231n 10th Anniversary Lecture 14 - 14 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Generative Adversarial Networks
Setup: Have data x drawn from distribution p (x). Want to sample from p
i data data
Idea: Introduce a latent variable z with simple prior p(z) (e.g. unit Gaussian)
Sample 𝑧 ∼ 𝑝(𝑧) and pass to a Generator Network x = G(z)
Then x is a sample from the Generator distribution p . Want p = p !
G G data
Generated
Generator
Network image Discriminator
Sample Network
z G
Fake
z from p
z
D
Real
Train Generator Network G to convert
z into fake data x sampled from p Train Discriminator Network D
G Real
By fooling the discriminator D to classify data as real or fake
image |
| Stanford CS231n 10th Anniversary Lecture 14 - 14 May 20, 2025 |


[Page contains 2 image(s)]


---
## Page 15
---


Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Generative Adversarial Networks
Setup: Have data x drawn from distribution p (x). Want to sample from p
i data data
Idea: Introduce a latent variable z with simple prior p(z) (e.g. unit Gaussian)
Sample 𝑧 ∼ 𝑝(𝑧) and pass to a Generator Network x = G(z)
Then x is a sample from the Generator distribution p . Want p = p !
G G data
Generated Jointly train G and
Generator
D. Hopefully p
Network image Discriminator G
converges to p
Sample Network data
z G
Fake
z from p
z
D
Real
Train Generator Network G to convert
z into fake data x sampled from p Train Discriminator Network D
G Real
By fooling the discriminator D to classify data as real or fake
image
Stanford CS231n 10th Anniversary Lecture 14 - 15 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Generative Adversarial Networks
Setup: Have data x drawn from distribution p (x). Want to sample from p
i data data
Idea: Introduce a latent variable z with simple prior p(z) (e.g. unit Gaussian)
Sample 𝑧 ∼ 𝑝(𝑧) and pass to a Generator Network x = G(z)
Then x is a sample from the Generator distribution p . Want p = p !
G G data
Generated Jointly train G and
Generator
D. Hopefully p
Network image Discriminator G
converges to p
Sample Network data
z G
Fake
z from p
z
D
Real
Train Generator Network G to convert
z into fake data x sampled from p Train Discriminator Network D
G Real
By fooling the discriminator D to classify data as real or fake
image |
| Stanford CS231n 10th Anniversary Lecture 14 - 15 May 20, 2025 |


[Page contains 2 image(s)]


---
## Page 16
---


Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝐺 𝐷
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Stanford CS231n 10th Anniversary Lecture 14 - 16 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝐺 𝐷
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014 |
| Stanford CS231n 10th Anniversary Lecture 14 - 16 May 20, 2025 |


---
## Page 17
---


Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
D(x) = P(x is real)
D(x) = 0 => fake
D(x) = 1 => real
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Stanford CS231n 10th Anniversary Lecture 14 - 17 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
D(x) = P(x is real)
D(x) = 0 => fake
D(x) = 1 => real
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014 |
| Stanford CS231n 10th Anniversary Lecture 14 - 17 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 18
---


Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
Discriminator wants Discriminator wants
D(x) = 1 for real data D(x) = 0 for fake data
Imagine
fixing G
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
D(x) = P(x is real)
D(x) = 0 => fake
D(x) = 1 => real
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Stanford CS231n 10th Anniversary Lecture 14 - 18 May 20, 2025

[Page contains 2 table(s)]


### Table 1

| Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
Discriminator wants Discriminator wants
D(x) = 1 for real data D(x) = 0 for fake data
Imagine
fixing G
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
D(x) = P(x is real)
D(x) = 0 => fake
D(x) = 1 => real
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014 |
| Stanford CS231n 10th Anniversary Lecture 14 - 18 May 20, 2025 |


### Table 2

| min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫 |
| min
𝑮 |


[Page contains 1 image(s)]


---
## Page 19
---


Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
This term does not Generator wants
depend on G D(x) = 1 for fake data
Imagine
fixing D
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
D(x) = P(x is real)
D(x) = 0 => fake
D(x) = 1 => real
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Stanford CS231n 10th Anniversary Lecture 14 - 19 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
This term does not Generator wants
depend on G D(x) = 1 for fake data
Imagine
fixing D
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
D(x) = P(x is real)
D(x) = 0 => fake
D(x) = 1 => real
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014 |
| Stanford CS231n 10th Anniversary Lecture 14 - 19 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 20
---


Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
Train G and D using alternating gradient updates
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
= min max 𝑉(𝐺, 𝐷)
𝑮 𝑫
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Stanford CS231n 10th Anniversary Lecture 14 - 20 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
Train G and D using alternating gradient updates
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
= min max 𝑉(𝐺, 𝐷)
𝑮 𝑫
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014 |
| Stanford CS231n 10th Anniversary Lecture 14 - 20 May 20, 2025 |


---
## Page 21
---


Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
Train G and D using alternating gradient updates
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
While True:
= min max 𝑉(𝐺, 𝐷)
𝑮 𝑫 𝑑𝑉
𝐷 = 𝐷 + 𝛼
𝐷
𝑑𝐷
𝑑𝑉
𝐺 = 𝐺 − 𝛼
𝐺
𝑑𝐺
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Stanford CS231n 10th Anniversary Lecture 14 - 21 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
Train G and D using alternating gradient updates
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
While True:
= min max 𝑉(𝐺, 𝐷)
𝑮 𝑫 𝑑𝑉
𝐷 = 𝐷 + 𝛼
𝐷
𝑑𝐷
𝑑𝑉
𝐺 = 𝐺 − 𝛼
𝐺
𝑑𝐺
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014 |
| Stanford CS231n 10th Anniversary Lecture 14 - 21 May 20, 2025 |


---
## Page 22
---


Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
Train G and D using alternating gradient updates
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
While True:
= min max 𝑉(𝐺, 𝐷)
𝑮 𝑫 𝑑𝑉
𝐷 = 𝐷 + 𝛼
𝐷
We are not minimizing any overall 𝑑𝐷
𝑑𝑉
loss! No training curves to look at!
𝐺 = 𝐺 − 𝛼
𝐺
𝑑𝐺
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Stanford CS231n 10th Anniversary Lecture 14 - 22 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
Train G and D using alternating gradient updates
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
While True:
= min max 𝑉(𝐺, 𝐷)
𝑮 𝑫 𝑑𝑉
𝐷 = 𝐷 + 𝛼
𝐷
We are not minimizing any overall 𝑑𝐷
𝑑𝑉
loss! No training curves to look at!
𝐺 = 𝐺 − 𝛼
𝐺
𝑑𝐺
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014 |
| Stanford CS231n 10th Anniversary Lecture 14 - 22 May 20, 2025 |


---
## Page 23
---


Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
At start of training, generator is very
bad and discriminator can easily tell apart
real/fake, so D(G(z)) close to 0
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Stanford CS231n 10th Anniversary Lecture 14 - 23 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
At start of training, generator is very
bad and discriminator can easily tell apart
real/fake, so D(G(z)) close to 0
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014 |
| Stanford CS231n 10th Anniversary Lecture 14 - 23 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 24
---


Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
At start of training, generator is very
bad and discriminator can easily tell apart
real/fake, so D(G(z)) close to 0
Problem: Gradients for G are close to 0
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Stanford CS231n 10th Anniversary Lecture 14 - 24 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
At start of training, generator is very
bad and discriminator can easily tell apart
real/fake, so D(G(z)) close to 0
Problem: Gradients for G are close to 0
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014 |
| Stanford CS231n 10th Anniversary Lecture 14 - 24 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 25
---


Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
At start of training, generator is very
bad and discriminator can easily tell apart
real/fake, so D(G(z)) close to 0
Problem: Gradients for G are close to 0
Solution: Generator wants D(G(z)) = 1.
Train generator to minimize –log(D(G(z))
and discriminator to maximize log(1-D(G(z))
so generator gets strong gradients at start
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Stanford CS231n 10th Anniversary Lecture 14 - 25 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
At start of training, generator is very
bad and discriminator can easily tell apart
real/fake, so D(G(z)) close to 0
Problem: Gradients for G are close to 0
Solution: Generator wants D(G(z)) = 1.
Train generator to minimize –log(D(G(z))
and discriminator to maximize log(1-D(G(z))
so generator gets strong gradients at start
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014 |
| Stanford CS231n 10th Anniversary Lecture 14 - 25 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 26
---


Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
Why is this a good objective?
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Stanford CS231n 10th Anniversary Lecture 14 - 26 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
Why is this a good objective?
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014 |
| Stanford CS231n 10th Anniversary Lecture 14 - 26 May 20, 2025 |


---
## Page 27
---


Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
Why is this a good objective?
Inner objective is maximized by
𝑝 𝑥
∗ 𝑑𝑎𝑡𝑎
𝐷 𝑥 =
𝐺
𝑝 𝑥 + 𝑝 (𝑥)
𝑑𝑎𝑡𝑎 𝐺
(for any p )
G
(Proof omitted)
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Stanford CS231n 10th Anniversary Lecture 14 - 27 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
Why is this a good objective?
Inner objective is maximized by
𝑝 𝑥
∗ 𝑑𝑎𝑡𝑎
𝐷 𝑥 =
𝐺
𝑝 𝑥 + 𝑝 (𝑥)
𝑑𝑎𝑡𝑎 𝐺
(for any p )
G
(Proof omitted)
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014 |
| Stanford CS231n 10th Anniversary Lecture 14 - 27 May 20, 2025 |


---
## Page 28
---


Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
Why is this a good objective?
Inner objective is maximized by Outer objective is
𝑝 𝑥 then minimized by
∗ 𝑑𝑎𝑡𝑎
𝐷 𝑥 =
𝐺 𝑝 𝑥 + 𝑝 (𝑥) 𝑝 𝑥 = 𝑝 𝑥
𝑑𝑎𝑡𝑎 𝐺 𝐺 𝑑𝑎𝑡𝑎
(for any p )
G
(Proof omitted)
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Stanford CS231n 10th Anniversary Lecture 14 - 28 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
Why is this a good objective?
Inner objective is maximized by Outer objective is
𝑝 𝑥 then minimized by
∗ 𝑑𝑎𝑡𝑎
𝐷 𝑥 =
𝐺 𝑝 𝑥 + 𝑝 (𝑥) 𝑝 𝑥 = 𝑝 𝑥
𝑑𝑎𝑡𝑎 𝐺 𝐺 𝑑𝑎𝑡𝑎
(for any p )
G
(Proof omitted)
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014 |
| Stanford CS231n 10th Anniversary Lecture 14 - 28 May 20, 2025 |


---
## Page 29
---


Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
Why is this a good objective?
Inner objective is maximized by Outer objective is
𝑝 𝑥 then minimized by
∗ 𝑑𝑎𝑡𝑎
𝐷 𝑥 =
𝐺 𝑝 𝑥 + 𝑝 (𝑥) 𝑝 𝑥 = 𝑝 𝑥
𝑑𝑎𝑡𝑎 𝐺 𝐺 𝑑𝑎𝑡𝑎
(for any p )
G
Caveats:
1. Neural nets with fixed capacity may not
be able to represent optimal D and G
(Proof omitted)
2. This tells us nothing about convergence
to the solution with finite data
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014
Stanford CS231n 10th Anniversary Lecture 14 - 29 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Generative Adversarial Networks: Training Objective
Jointly train generator G and discriminator D with a minimax game
min max 𝐸 log 𝐷 𝑥 + 𝐸 log 1 − 𝐷 𝐺 𝑧
𝑥~𝑝 𝑧~𝑝(𝑧)
𝑑𝑎𝑡𝑎
𝑮 𝑫
Why is this a good objective?
Inner objective is maximized by Outer objective is
𝑝 𝑥 then minimized by
∗ 𝑑𝑎𝑡𝑎
𝐷 𝑥 =
𝐺 𝑝 𝑥 + 𝑝 (𝑥) 𝑝 𝑥 = 𝑝 𝑥
𝑑𝑎𝑡𝑎 𝐺 𝐺 𝑑𝑎𝑡𝑎
(for any p )
G
Caveats:
1. Neural nets with fixed capacity may not
be able to represent optimal D and G
(Proof omitted)
2. This tells us nothing about convergence
to the solution with finite data
Goodfellow et al, “Generative
Adversarial Nets”, NeurIPS2014 |
| Stanford CS231n 10th Anniversary Lecture 14 - 29 May 20, 2025 |


---
## Page 30
---


GAN Architectures: DC-GAN
Generator G and discriminator D
are both neural networks
Usually CNNs … GANs fell out of
favor before ViT became popular
DC-GAN was the first GAN
architecture that worked on non-
toy data
Radford et al, ICLR 2016
Stanford CS231n 10th Anniversary Lecture 14 - 30 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| GAN Architectures: DC-GAN
Generator G and discriminator D
are both neural networks
Usually CNNs … GANs fell out of
favor before ViT became popular
DC-GAN was the first GAN
architecture that worked on non-
toy data
Radford et al, ICLR 2016 |
| Stanford CS231n 10th Anniversary Lecture 14 - 30 May 20, 2025 |


[Page contains 2 image(s)]


---
## Page 31
---


GAN Architectures: DC-GAN
GPT-1 Paper (2018)
Generator G and discriminator D
are both neural networks
Usually CNNs … GANs fell out of
favor before ViT became popular
DC-GAN was the first GAN
GPT-2 Paper (2019)
architecture that worked on non-
toy data
Radford et al, ICLR 2016
Stanford CS231n 10th Anniversary Lecture 14 - 31 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| GAN Architectures: DC-GAN
GPT-1 Paper (2018)
Generator G and discriminator D
are both neural networks
Usually CNNs … GANs fell out of
favor before ViT became popular
DC-GAN was the first GAN
GPT-2 Paper (2019)
architecture that worked on non-
toy data
Radford et al, ICLR 2016 |
| Stanford CS231n 10th Anniversary Lecture 14 - 31 May 20, 2025 |


[Page contains 4 image(s)]


---
## Page 32
---


GAN Architectures: StyleGAN
Generator G and discriminator D
are both neural networks
StyleGAN uses a more complex
architecture that injects noise via
adaptive normalization.
At each layer predict a scale w
and shift b the same shape as x:
𝑥 − 𝜇(𝑥)
𝑖
𝐴𝑑𝑎𝐼𝑁 𝑥, 𝑤, 𝑏 = 𝑤 + 𝑏
𝑖 𝑖 𝑖
𝜎(𝑥)
Karras et al, ”A Stye-Based Generator Architecture
for Generative Adversarial Networks”, CVPR 2019
Stanford CS231n 10th Anniversary Lecture 14 - 32 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| GAN Architectures: StyleGAN
Generator G and discriminator D
are both neural networks
StyleGAN uses a more complex
architecture that injects noise via
adaptive normalization.
At each layer predict a scale w
and shift b the same shape as x:
𝑥 − 𝜇(𝑥)
𝑖
𝐴𝑑𝑎𝐼𝑁 𝑥, 𝑤, 𝑏 = 𝑤 + 𝑏
𝑖 𝑖 𝑖
𝜎(𝑥)
Karras et al, ”A Stye-Based Generator Architecture
for Generative Adversarial Networks”, CVPR 2019 |
| Stanford CS231n 10th Anniversary Lecture 14 - 32 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 33
---


GANs: Latent Space Interpolation
Latent space is smooth.
Given latent vectors z and z , we
0 1
can interpolate between them:
𝑧 = 𝑡𝑧 + 1 − 𝑡 𝑧
𝑡 𝑜 1
𝑥 = 𝐺 𝑧
𝑡 𝑡
The resulting image x smoothly
t
interpolate between samples!
Stanford CS231n 10th Anniversary Lecture 14 - 33 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| GANs: Latent Space Interpolation
Latent space is smooth.
Given latent vectors z and z , we
0 1
can interpolate between them:
𝑧 = 𝑡𝑧 + 1 − 𝑡 𝑧
𝑡 𝑜 1
𝑥 = 𝐺 𝑧
𝑡 𝑡
The resulting image x smoothly
t
interpolate between samples! |
| Stanford CS231n 10th Anniversary Lecture 14 - 33 May 20, 2025 |


---
## Page 34
---


GANs: Latent Space Interpolation
Latent space is smooth.
Given latent vectors z and z , we
0 1
can interpolate between them:
𝑧 = 𝑡𝑧 + 1 − 𝑡 𝑧
𝑡 𝑜 1
𝑥 = 𝐺 𝑧
𝑡 𝑡
The resulting image x smoothly
t
interpolate between samples!
Karras et al, ”Alias-Free Generative Adversarial Networks”, NeurIPS 2021
Stanford CS231n 10th Anniversary Lecture 14 - 34 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| GANs: Latent Space Interpolation
Latent space is smooth.
Given latent vectors z and z , we
0 1
can interpolate between them:
𝑧 = 𝑡𝑧 + 1 − 𝑡 𝑧
𝑡 𝑜 1
𝑥 = 𝐺 𝑧
𝑡 𝑡
The resulting image x smoothly
t
interpolate between samples!
Karras et al, ”Alias-Free Generative Adversarial Networks”, NeurIPS 2021 |
| Stanford CS231n 10th Anniversary Lecture 14 - 34 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 35
---


Generative Adversarial Networks: Summary
Jointly train Generator and
Discriminator with a minimax game
Pros:
- Simple formulation
- Very good image quality
Cons: These were the go-to generative
- No loss curve to look at models from ~2016 – 2021
- Unstable training
- Hard to scale to big models + data
Stanford CS231n 10th Anniversary Lecture 14 - 35 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Generative Adversarial Networks: Summary
Jointly train Generator and
Discriminator with a minimax game
Pros:
- Simple formulation
- Very good image quality
Cons: These were the go-to generative
- No loss curve to look at models from ~2016 – 2021
- Unstable training
- Hard to scale to big models + data |
| Stanford CS231n 10th Anniversary Lecture 14 - 35 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 36
---


Diffusion Models
Sohl-Dickstein et al, “Deep Unsupervised Learning using noneuilibriumthermodynamics”, ICML 2015
Song and Ermon, “Generative modeling by estimnatinggradients of the data distribution”, NaurIPS2019
Ho et al, “Denoising Diffusion ProbabalisticModels”, NeurIPS2020
Song et al, “Score-Based Generative Modeling through Stochastic Differential Equations”, ICLR 2021
Song et al, “Denoising Diffusion Implicit Models”, ICLR 2021
Stanford CS231n 10th Anniversary Lecture 14 - 36 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Diffusion Models
Sohl-Dickstein et al, “Deep Unsupervised Learning using noneuilibriumthermodynamics”, ICML 2015
Song and Ermon, “Generative modeling by estimnatinggradients of the data distribution”, NaurIPS2019
Ho et al, “Denoising Diffusion ProbabalisticModels”, NeurIPS2020
Song et al, “Score-Based Generative Modeling through Stochastic Differential Equations”, ICLR 2021
Song et al, “Denoising Diffusion Implicit Models”, ICLR 2021 |
| Stanford CS231n 10th Anniversary Lecture 14 - 36 May 20, 2025 |


---
## Page 37
---


Warning: Terminology and
notation in this area is a mess!
There are many different
mathematical formalisms; tons
Diffusion Models
of variance in terminology and
notation between papers.
We’ll just cover the basics of a
modern “clean” implementation
(Rectified Flow)
Stanford CS231n 10th Anniversary Lecture 14 - 37 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Warning: Terminology and
notation in this area is a mess!
There are many different
mathematical formalisms; tons
Diffusion Models
of variance in terminology and
notation between papers.
We’ll just cover the basics of a
modern “clean” implementation
(Rectified Flow) |
| Stanford CS231n 10th Anniversary Lecture 14 - 37 May 20, 2025 |


---
## Page 38
---


Diffusion Models: Intuition
Pick a noise distribution 𝑧 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
(Usually unit Gaussian)
Stanford CS231n 10th Anniversary Lecture 14 - 38 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Diffusion Models: Intuition
Pick a noise distribution 𝑧 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
(Usually unit Gaussian) |
| Stanford CS231n 10th Anniversary Lecture 14 - 38 May 20, 2025 |


---
## Page 39
---


Diffusion Models: Intuition
t = 0
No noise
Pick a noise distribution 𝑧 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
(Usually unit Gaussian)
Consider data x corrupted under varying
noise levels t to give noisy data x
t
t = 1
Full noise
Stanford CS231n 10th Anniversary Lecture 14 - 39 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Diffusion Models: Intuition
t = 0
No noise
Pick a noise distribution 𝑧 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
(Usually unit Gaussian)
Consider data x corrupted under varying
noise levels t to give noisy data x
t
t = 1
Full noise |
| Stanford CS231n 10th Anniversary Lecture 14 - 39 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 40
---


Diffusion Models: Intuition
t = 0
No noise
Pick a noise distribution 𝑧 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
(Usually unit Gaussian)
Consider data x corrupted under varying
noise levels t to give noisy data x
t
Train a neural network to remove a little
bit of noise: 𝑓 (𝑥 , 𝑡)
𝜃 𝑡
t = 1
Full noise
Stanford CS231n 10th Anniversary Lecture 14 - 40 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Diffusion Models: Intuition
t = 0
No noise
Pick a noise distribution 𝑧 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
(Usually unit Gaussian)
Consider data x corrupted under varying
noise levels t to give noisy data x
t
Train a neural network to remove a little
bit of noise: 𝑓 (𝑥 , 𝑡)
𝜃 𝑡
t = 1
Full noise |
| Stanford CS231n 10th Anniversary Lecture 14 - 40 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 41
---


Diffusion Models: Intuition
t = 0
No noise
Pick a noise distribution 𝑧 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
(Usually unit Gaussian)
Consider data x corrupted under varying
noise levels t to give noisy data x
t
Train a neural network to remove a little
bit of noise: 𝑓 (𝑥 , 𝑡)
𝜃 𝑡
At inference time, sample 𝑥 ∼ 𝑝 and
1 𝑛𝑜𝑖𝑠𝑒
t = 1
apply 𝑓 many times in sequence to
𝜃
Full noise
generate a noiseless sample x
0
Stanford CS231n 10th Anniversary Lecture 14 - 41 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Diffusion Models: Intuition
t = 0
No noise
Pick a noise distribution 𝑧 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
(Usually unit Gaussian)
Consider data x corrupted under varying
noise levels t to give noisy data x
t
Train a neural network to remove a little
bit of noise: 𝑓 (𝑥 , 𝑡)
𝜃 𝑡
At inference time, sample 𝑥 ∼ 𝑝 and
1 𝑛𝑜𝑖𝑠𝑒
t = 1
apply 𝑓 many times in sequence to
𝜃
Full noise
generate a noiseless sample x
0 |
| Stanford CS231n 10th Anniversary Lecture 14 - 41 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 42
---


Diffusion Models: Rectified Flow
𝑝
𝑛𝑜𝑖𝑠𝑒
Suppose we have a simple p
noise
(e.g. Gaussian) and samples from p
data
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022
Stanford CS231n 10th Anniversary Lecture 14 - 42 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Diffusion Models: Rectified Flow
𝑝
𝑛𝑜𝑖𝑠𝑒
Suppose we have a simple p
noise
(e.g. Gaussian) and samples from p
data
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 42 May 20, 2025 |


---
## Page 43
---


Diffusion Models: Rectified Flow
𝑝
𝑛𝑜𝑖𝑠𝑒
Suppose we have a simple p
noise
(e.g. Gaussian) and samples from p
data
𝑧
On each training iteration, sample:
𝑧 ∼ 𝑝 𝑥 ∼ 𝑝 𝑡 ∼ 𝑈𝑛𝑖𝑓𝑜𝑟𝑚 0, 1
𝑛𝑜𝑖𝑠𝑒 𝑑𝑎𝑡𝑎
𝑥
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022
Stanford CS231n 10th Anniversary Lecture 14 - 43 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Diffusion Models: Rectified Flow
𝑝
𝑛𝑜𝑖𝑠𝑒
Suppose we have a simple p
noise
(e.g. Gaussian) and samples from p
data
𝑧
On each training iteration, sample:
𝑧 ∼ 𝑝 𝑥 ∼ 𝑝 𝑡 ∼ 𝑈𝑛𝑖𝑓𝑜𝑟𝑚 0, 1
𝑛𝑜𝑖𝑠𝑒 𝑑𝑎𝑡𝑎
𝑥
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 43 May 20, 2025 |


---
## Page 44
---


Diffusion Models: Rectified Flow
𝑝
𝑛𝑜𝑖𝑠𝑒
Suppose we have a simple p
noise
(e.g. Gaussian) and samples from p
data
𝑧
On each training iteration, sample:
𝑣
𝑧 ∼ 𝑝 𝑥 ∼ 𝑝 𝑡 ∼ 𝑈𝑛𝑖𝑓𝑜𝑟𝑚 0, 1
𝑛𝑜𝑖𝑠𝑒 𝑑𝑎𝑡𝑎
Set 𝑥 = 1 − 𝑡 𝑥 + 𝑡𝑧, 𝑣 = 𝑧 − 𝑥
𝑡
𝑥
𝑡
𝑥
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022
Stanford CS231n 10th Anniversary Lecture 14 - 44 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Diffusion Models: Rectified Flow
𝑝
𝑛𝑜𝑖𝑠𝑒
Suppose we have a simple p
noise
(e.g. Gaussian) and samples from p
data
𝑧
On each training iteration, sample:
𝑣
𝑧 ∼ 𝑝 𝑥 ∼ 𝑝 𝑡 ∼ 𝑈𝑛𝑖𝑓𝑜𝑟𝑚 0, 1
𝑛𝑜𝑖𝑠𝑒 𝑑𝑎𝑡𝑎
Set 𝑥 = 1 − 𝑡 𝑥 + 𝑡𝑧, 𝑣 = 𝑧 − 𝑥
𝑡
𝑥
𝑡
𝑥
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 44 May 20, 2025 |


---
## Page 45
---


Diffusion Models: Rectified Flow
𝑝
𝑛𝑜𝑖𝑠𝑒
Suppose we have a simple p
noise
(e.g. Gaussian) and samples from p
data
𝑧
On each training iteration, sample:
𝑣
𝑧 ∼ 𝑝 𝑥 ∼ 𝑝 𝑡 ∼ 𝑈𝑛𝑖𝑓𝑜𝑟𝑚 0, 1
𝑛𝑜𝑖𝑠𝑒 𝑑𝑎𝑡𝑎
Set 𝑥 = 1 − 𝑡 𝑥 + 𝑡𝑧, 𝑣 = 𝑧 − 𝑥
𝑡
𝑥
𝑡
𝑥
Train a neural network to predict v:
2
𝐿 = 𝑓 𝑥 , 𝑡 − 𝑣 𝑝
𝜃 𝑡 2
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022
Stanford CS231n 10th Anniversary Lecture 14 - 45 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Diffusion Models: Rectified Flow
𝑝
𝑛𝑜𝑖𝑠𝑒
Suppose we have a simple p
noise
(e.g. Gaussian) and samples from p
data
𝑧
On each training iteration, sample:
𝑣
𝑧 ∼ 𝑝 𝑥 ∼ 𝑝 𝑡 ∼ 𝑈𝑛𝑖𝑓𝑜𝑟𝑚 0, 1
𝑛𝑜𝑖𝑠𝑒 𝑑𝑎𝑡𝑎
Set 𝑥 = 1 − 𝑡 𝑥 + 𝑡𝑧, 𝑣 = 𝑧 − 𝑥
𝑡
𝑥
𝑡
𝑥
Train a neural network to predict v:
2
𝐿 = 𝑓 𝑥 , 𝑡 − 𝑣 𝑝
𝜃 𝑡 2
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 45 May 20, 2025 |


---
## Page 46
---


Diffusion Models: Rectified Flow
𝑝
𝑛𝑜𝑖𝑠𝑒
Core training loop is just
a few lines of code!
𝑧
𝑣
𝑥
𝑡
𝑥
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022
Stanford CS231n 10th Anniversary Lecture 14 - 46 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Diffusion Models: Rectified Flow
𝑝
𝑛𝑜𝑖𝑠𝑒
Core training loop is just
a few lines of code!
𝑧
𝑣
𝑥
𝑡
𝑥
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 46 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 47
---


Rectified Flow: Sampling
𝑝
𝑛𝑜𝑖𝑠𝑒
Choose number of steps T (often T=50)
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022
Stanford CS231n 10th Anniversary Lecture 14 - 47 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Rectified Flow: Sampling
𝑝
𝑛𝑜𝑖𝑠𝑒
Choose number of steps T (often T=50)
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 47 May 20, 2025 |


---
## Page 48
---


Rectified Flow: Sampling
𝑝
𝑛𝑜𝑖𝑠𝑒
Choose number of steps T (often T=50)
𝑥
1
Sample 𝑥 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022
Stanford CS231n 10th Anniversary Lecture 14 - 48 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Rectified Flow: Sampling
𝑝
𝑛𝑜𝑖𝑠𝑒
Choose number of steps T (often T=50)
𝑥
1
Sample 𝑥 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 48 May 20, 2025 |


---
## Page 49
---


Rectified Flow: Sampling
𝑝
𝑛𝑜𝑖𝑠𝑒
Choose number of steps T (often T=50)
𝑥
1
Sample 𝑥 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
1 2
For t in [1, 1 − , 1 − , … , 0]: 𝑣
1
𝑇 𝑇
Evaluate 𝑣 = 𝑓 (𝑥 , 𝑡)
𝑡 𝜃 𝑡
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022
Stanford CS231n 10th Anniversary Lecture 14 - 49 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Rectified Flow: Sampling
𝑝
𝑛𝑜𝑖𝑠𝑒
Choose number of steps T (often T=50)
𝑥
1
Sample 𝑥 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
1 2
For t in [1, 1 − , 1 − , … , 0]: 𝑣
1
𝑇 𝑇
Evaluate 𝑣 = 𝑓 (𝑥 , 𝑡)
𝑡 𝜃 𝑡
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 49 May 20, 2025 |


---
## Page 50
---


Rectified Flow: Sampling
𝑝
𝑛𝑜𝑖𝑠𝑒
Choose number of steps T (often T=50)
𝑥
1
Sample 𝑥 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
1 2 𝑥
For t in [1, 1 − , 1 − , … , 0]: 𝑣 2/3
1
𝑇 𝑇
Evaluate 𝑣 = 𝑓 (𝑥 , 𝑡)
𝑡 𝜃 𝑡
Step 𝑥 = 𝑥 − 𝑣 /𝑇
𝑡
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022
Stanford CS231n 10th Anniversary Lecture 14 - 50 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Rectified Flow: Sampling
𝑝
𝑛𝑜𝑖𝑠𝑒
Choose number of steps T (often T=50)
𝑥
1
Sample 𝑥 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
1 2 𝑥
For t in [1, 1 − , 1 − , … , 0]: 𝑣 2/3
1
𝑇 𝑇
Evaluate 𝑣 = 𝑓 (𝑥 , 𝑡)
𝑡 𝜃 𝑡
Step 𝑥 = 𝑥 − 𝑣 /𝑇
𝑡
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 50 May 20, 2025 |


---
## Page 51
---


Rectified Flow: Sampling
𝑝
𝑛𝑜𝑖𝑠𝑒
Choose number of steps T (often T=50)
𝑥
1
Sample 𝑥 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
1 2 𝑥
For t in [1, 1 − , 1 − , … , 0]: 2/3
𝑇 𝑇
Evaluate 𝑣 = 𝑓 (𝑥 , 𝑡)
𝑡 𝜃 𝑡
Step 𝑥 = 𝑥 − 𝑣 /𝑇 𝑣
𝑡 2/3
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022
Stanford CS231n 10th Anniversary Lecture 14 - 51 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Rectified Flow: Sampling
𝑝
𝑛𝑜𝑖𝑠𝑒
Choose number of steps T (often T=50)
𝑥
1
Sample 𝑥 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
1 2 𝑥
For t in [1, 1 − , 1 − , … , 0]: 2/3
𝑇 𝑇
Evaluate 𝑣 = 𝑓 (𝑥 , 𝑡)
𝑡 𝜃 𝑡
Step 𝑥 = 𝑥 − 𝑣 /𝑇 𝑣
𝑡 2/3
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 51 May 20, 2025 |


---
## Page 52
---


Rectified Flow: Sampling
𝑝
𝑛𝑜𝑖𝑠𝑒
Choose number of steps T (often T=50)
𝑥
1
Sample 𝑥 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
1 2 𝑥
For t in [1, 1 − , 1 − , … , 0]: 2/3
𝑇 𝑇
Evaluate 𝑣 = 𝑓 (𝑥 , 𝑡)
𝑡 𝜃 𝑡
Step 𝑥 = 𝑥 − 𝑣 /𝑇 𝑣
𝑡 2/3 𝑥
1/3
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022
Stanford CS231n 10th Anniversary Lecture 14 - 52 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Rectified Flow: Sampling
𝑝
𝑛𝑜𝑖𝑠𝑒
Choose number of steps T (often T=50)
𝑥
1
Sample 𝑥 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
1 2 𝑥
For t in [1, 1 − , 1 − , … , 0]: 2/3
𝑇 𝑇
Evaluate 𝑣 = 𝑓 (𝑥 , 𝑡)
𝑡 𝜃 𝑡
Step 𝑥 = 𝑥 − 𝑣 /𝑇 𝑣
𝑡 2/3 𝑥
1/3
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 52 May 20, 2025 |


---
## Page 53
---


Rectified Flow: Sampling
𝑝
𝑛𝑜𝑖𝑠𝑒
Choose number of steps T (often T=50)
𝑥
1
Sample 𝑥 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
1 2 𝑥
For t in [1, 1 − , 1 − , … , 0]: 2/3
𝑇 𝑇
Evaluate 𝑣 = 𝑓 (𝑥 , 𝑡)
𝑡 𝜃 𝑡
Step 𝑥 = 𝑥 − 𝑣 /𝑇 𝑣
𝑡 1/3
𝑥
1/3
𝑥
0
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022
Stanford CS231n 10th Anniversary Lecture 14 - 53 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Rectified Flow: Sampling
𝑝
𝑛𝑜𝑖𝑠𝑒
Choose number of steps T (often T=50)
𝑥
1
Sample 𝑥 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
1 2 𝑥
For t in [1, 1 − , 1 − , … , 0]: 2/3
𝑇 𝑇
Evaluate 𝑣 = 𝑓 (𝑥 , 𝑡)
𝑡 𝜃 𝑡
Step 𝑥 = 𝑥 − 𝑣 /𝑇 𝑣
𝑡 1/3
𝑥
1/3
𝑥
0
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 53 May 20, 2025 |


---
## Page 54
---


Rectified Flow: Sampling
𝑝
𝑛𝑜𝑖𝑠𝑒
Choose number of steps T (often T=50)
𝑥
1
Sample 𝑥 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
1 2 𝑥
For t in [1, 1 − , 1 − , … , 0]: 2/3
𝑇 𝑇
Evaluate 𝑣 = 𝑓 (𝑥 , 𝑡)
𝑡 𝜃 𝑡
Step 𝑥 = 𝑥 − 𝑣 /𝑇 𝑣
𝑡 1/3
𝑥
1/3
𝑥
0
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022
Stanford CS231n 10th Anniversary Lecture 14 - 54 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Rectified Flow: Sampling
𝑝
𝑛𝑜𝑖𝑠𝑒
Choose number of steps T (often T=50)
𝑥
1
Sample 𝑥 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
1 2 𝑥
For t in [1, 1 − , 1 − , … , 0]: 2/3
𝑇 𝑇
Evaluate 𝑣 = 𝑓 (𝑥 , 𝑡)
𝑡 𝜃 𝑡
Step 𝑥 = 𝑥 − 𝑣 /𝑇 𝑣
𝑡 1/3
𝑥
1/3
𝑥
0
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 54 May 20, 2025 |


---
## Page 55
---


Rectified Flow: Sampling
𝑝
𝑛𝑜𝑖𝑠𝑒
Choose number of steps T (often T=50)
𝑥
1
Sample 𝑥 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
1 2 𝑥
For t in [1, 1 − , 1 − , … , 0]: 2/3
𝑇 𝑇
Evaluate 𝑣 = 𝑓 (𝑥 , 𝑡)
𝑡 𝜃 𝑡
Step 𝑥 = 𝑥 − 𝑣 /𝑇
𝑡
𝑥
Return x 1/3
𝑥
0
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022
Stanford CS231n 10th Anniversary Lecture 14 - 55 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Rectified Flow: Sampling
𝑝
𝑛𝑜𝑖𝑠𝑒
Choose number of steps T (often T=50)
𝑥
1
Sample 𝑥 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
1 2 𝑥
For t in [1, 1 − , 1 − , … , 0]: 2/3
𝑇 𝑇
Evaluate 𝑣 = 𝑓 (𝑥 , 𝑡)
𝑡 𝜃 𝑡
Step 𝑥 = 𝑥 − 𝑣 /𝑇
𝑡
𝑥
Return x 1/3
𝑥
0
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 55 May 20, 2025 |


---
## Page 56
---


Rectified Flow: Sampling
𝑝
𝑛𝑜𝑖𝑠𝑒
Choose number of steps T (often T=50)
𝑥
1
Sample 𝑥 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
1 2 𝑥
For t in [1, 1 − , 1 − , … , 0]: 2/3
𝑇 𝑇
Evaluate 𝑣 = 𝑓 (𝑥 , 𝑡)
𝑡 𝜃 𝑡
Step 𝑥 = 𝑥 − 𝑣 /𝑇
𝑡
𝑥
Return x 1/3
𝑥
0
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022
Stanford CS231n 10th Anniversary Lecture 14 - 56 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Rectified Flow: Sampling
𝑝
𝑛𝑜𝑖𝑠𝑒
Choose number of steps T (often T=50)
𝑥
1
Sample 𝑥 ∼ 𝑝
𝑛𝑜𝑖𝑠𝑒
1 2 𝑥
For t in [1, 1 − , 1 − , … , 0]: 2/3
𝑇 𝑇
Evaluate 𝑣 = 𝑓 (𝑥 , 𝑡)
𝑡 𝜃 𝑡
Step 𝑥 = 𝑥 − 𝑣 /𝑇
𝑡
𝑥
Return x 1/3
𝑥
0
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 56 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 57
---


Rectified Flow: Summary
𝑝
𝑛𝑜𝑖𝑠𝑒
Training
𝑧
𝑣
Sampling
𝑥
𝑡
𝑥
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022
Stanford CS231n 10th Anniversary Lecture 14 - 57 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Rectified Flow: Summary
𝑝
𝑛𝑜𝑖𝑠𝑒
Training
𝑧
𝑣
Sampling
𝑥
𝑡
𝑥
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 57 May 20, 2025 |


[Page contains 2 image(s)]


---
## Page 58
---


Conditional Rectified Flow
𝑝
𝑛𝑜𝑖𝑠𝑒
Training
𝑧
𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Sampling
𝑥
𝑡
𝑥
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022
Stanford CS231n 10th Anniversary Lecture 14 - 58 May 20, 2025

[Page contains 2 table(s)]


### Table 1

| Conditional Rectified Flow
𝑝
𝑛𝑜𝑖𝑠𝑒
Training
𝑧
𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Sampling
𝑥
𝑡
𝑥
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 58 May 20, 2025 |


### Table 2

| 𝑥 |  |  |
|  | 𝑥 |  |
|  |  |  |


[Page contains 2 image(s)]


---
## Page 59
---


Conditional Rectified Flow
𝑝
𝑛𝑜𝑖𝑠𝑒
Training
𝑧
𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Sampling
𝑥
𝑡
𝑥
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022
Stanford CS231n 10th Anniversary Lecture 14 - 59 May 20, 2025

[Page contains 2 table(s)]


### Table 1

| Conditional Rectified Flow
𝑝
𝑛𝑜𝑖𝑠𝑒
Training
𝑧
𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Sampling
𝑥
𝑡
𝑥
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 59 May 20, 2025 |


### Table 2

| 𝑥 |  |  |
|  | 𝑥 |  |
|  |  |  |


[Page contains 2 image(s)]


---
## Page 60
---


Conditional Rectified Flow
𝑝
𝑛𝑜𝑖𝑠𝑒
Training
𝑧
𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Sampling
𝑥
𝑡
𝑥
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022
Stanford CS231n 10th Anniversary Lecture 14 - 60 May 20, 2025

[Page contains 2 table(s)]


### Table 1

| Conditional Rectified Flow
𝑝
𝑛𝑜𝑖𝑠𝑒
Training
𝑧
𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Sampling
𝑥
𝑡
𝑥
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 60 May 20, 2025 |


### Table 2

| 𝑥 |  |  |
|  | 𝑥 |  |
|  |  |  |


[Page contains 2 image(s)]


---
## Page 61
---


Conditional Rectified Flow
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training
much we “emphasize”
the conditioning y?
𝑧
𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Sampling
𝑥
𝑡
𝑥
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022
Stanford CS231n 10th Anniversary Lecture 14 - 61 May 20, 2025

[Page contains 2 table(s)]


### Table 1

| Conditional Rectified Flow
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training
much we “emphasize”
the conditioning y?
𝑧
𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Sampling
𝑥
𝑡
𝑥
𝑝
𝑑𝑎𝑡𝑎
Liu et al, “Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow”, 2022
Lipman et al, “Flow Matching for Generative Modeling”, 2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 61 May 20, 2025 |


### Table 2

| 𝑥 |  |  |
|  | 𝑥 |  |
|  |  |  |


[Page contains 2 image(s)]


---
## Page 62
---


Classifier-Free Guidance (CFG)
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training
much we “emphasize”
the conditioning y?
𝑧
𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Randomly drop y during training.
𝑥
𝑡
Now the same model is conditional and unconditional!
𝑥
𝑝
𝑑𝑎𝑡𝑎
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 14 - 62 May 20, 2025

[Page contains 2 table(s)]


### Table 1

| Classifier-Free Guidance (CFG)
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training
much we “emphasize”
the conditioning y?
𝑧
𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Randomly drop y during training.
𝑥
𝑡
Now the same model is conditional and unconditional!
𝑥
𝑝
𝑑𝑎𝑡𝑎
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 62 May 20, 2025 |


### Table 2

| 𝑥 |  |  |
|  | 𝑥 |  |
|  |  |  |


[Page contains 1 image(s)]


---
## Page 63
---


Classifier-Free Guidance (CFG)
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training
much we “emphasize”
the conditioning y? 𝑥
𝑡
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Randomly drop y during training.
Now the same model is conditional and unconditional!
Consider a noisy 𝑥 :
𝑡
𝑝
𝑑𝑎𝑡𝑎
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 14 - 63 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Classifier-Free Guidance (CFG)
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training
much we “emphasize”
the conditioning y? 𝑥
𝑡
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Randomly drop y during training.
Now the same model is conditional and unconditional!
Consider a noisy 𝑥 :
𝑡
𝑝
𝑑𝑎𝑡𝑎
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 63 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 64
---


Classifier-Free Guidance (CFG)
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training
∅
𝑣
much we “emphasize”
the conditioning y? 𝑥
𝑡
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Randomly drop y during training.
Now the same model is conditional and unconditional!
Consider a noisy 𝑥 :
𝑡
𝑣∅ = 𝑓 (𝑥 ,𝑦 ,𝑡) points toward 𝑝(𝑥) 𝑝
𝜃 𝑡 ∅
𝑑𝑎𝑡𝑎
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 14 - 64 May 20, 2025

[Page contains 2 table(s)]


### Table 1

| Classifier-Free Guidance (CFG)
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training
∅
𝑣
much we “emphasize”
the conditioning y? 𝑥
𝑡
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Randomly drop y during training.
Now the same model is conditional and unconditional!
Consider a noisy 𝑥 :
𝑡
𝑣∅ = 𝑓 (𝑥 ,𝑦 ,𝑡) points toward 𝑝(𝑥) 𝑝
𝜃 𝑡 ∅
𝑑𝑎𝑡𝑎
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 64 May 20, 2025 |


### Table 2

| ∅
𝑣 |  |
|  |  |
|  | 𝑥
𝑡 |


[Page contains 1 image(s)]


---
## Page 65
---


Classifier-Free Guidance (CFG)
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training ∅ 𝑣 𝑦
𝑣
much we “emphasize”
the conditioning y? 𝑥
𝑡
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Randomly drop y during training.
Now the same model is conditional and unconditional!
Consider a noisy 𝑥 :
𝑡
𝑣∅ = 𝑓 (𝑥 ,𝑦 ,𝑡) points toward 𝑝(𝑥) 𝑝
𝜃 𝑡 ∅
𝑑𝑎𝑡𝑎
𝑣𝑦 = 𝑓 (𝑥 ,𝑦,𝑡) points toward 𝑝 𝑥 𝑦
𝜃 𝑡
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 14 - 65 May 20, 2025

[Page contains 2 table(s)]


### Table 1

| Classifier-Free Guidance (CFG)
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training ∅ 𝑣 𝑦
𝑣
much we “emphasize”
the conditioning y? 𝑥
𝑡
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Randomly drop y during training.
Now the same model is conditional and unconditional!
Consider a noisy 𝑥 :
𝑡
𝑣∅ = 𝑓 (𝑥 ,𝑦 ,𝑡) points toward 𝑝(𝑥) 𝑝
𝜃 𝑡 ∅
𝑑𝑎𝑡𝑎
𝑣𝑦 = 𝑓 (𝑥 ,𝑦,𝑡) points toward 𝑝 𝑥 𝑦
𝜃 𝑡
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 65 May 20, 2025 |


### Table 2

|  | 𝑝
𝑛𝑜𝑖𝑠𝑒 |  |  |
|  |  |  | 𝑦
𝑣 |
| ∅
𝑣 |  |  |  |
|  |  |  |  |
|  |  | 𝑥
𝑡 |  |


[Page contains 1 image(s)]


---
## Page 66
---


Classifier-Free Guidance (CFG)
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training ∅ 𝑣 𝑦
𝑣
much we “emphasize”
the conditioning y? 𝑥
𝑐𝑓𝑔
𝑡 𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Randomly drop y during training.
Now the same model is conditional and unconditional!
Consider a noisy 𝑥 :
𝑡
𝑣∅ = 𝑓 (𝑥 ,𝑦 ,𝑡) points toward 𝑝(𝑥) 𝑝
𝜃 𝑡 ∅
𝑑𝑎𝑡𝑎
𝑣𝑦 = 𝑓 (𝑥 ,𝑦,𝑡) points toward 𝑝 𝑥 𝑦
𝜃 𝑡
𝑣𝑐𝑓𝑔 = 1 + 𝑤 𝑣𝑦 − 𝑤𝑣∅ points more toward 𝑝 𝑥 𝑦
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 14 - 66 May 20, 2025

[Page contains 2 table(s)]


### Table 1

| Classifier-Free Guidance (CFG)
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training ∅ 𝑣 𝑦
𝑣
much we “emphasize”
the conditioning y? 𝑥
𝑐𝑓𝑔
𝑡 𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Randomly drop y during training.
Now the same model is conditional and unconditional!
Consider a noisy 𝑥 :
𝑡
𝑣∅ = 𝑓 (𝑥 ,𝑦 ,𝑡) points toward 𝑝(𝑥) 𝑝
𝜃 𝑡 ∅
𝑑𝑎𝑡𝑎
𝑣𝑦 = 𝑓 (𝑥 ,𝑦,𝑡) points toward 𝑝 𝑥 𝑦
𝜃 𝑡
𝑣𝑐𝑓𝑔 = 1 + 𝑤 𝑣𝑦 − 𝑤𝑣∅ points more toward 𝑝 𝑥 𝑦
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 66 May 20, 2025 |


### Table 2

|  | 𝑝
𝑛𝑜𝑖𝑠𝑒 |  |  |
|  |  |  | 𝑦
𝑣 |
| ∅
𝑣 |  |  |  |
|  |  |  |  |
|  |  | 𝑥
𝑡 |  |


[Page contains 1 image(s)]


---
## Page 67
---


Classifier-Free Guidance (CFG)
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training ∅ 𝑣 𝑦
𝑣
much we “emphasize”
the conditioning y? 𝑥
𝑐𝑓𝑔
𝑡 𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Randomly drop y during training.
Now the same model is conditional and unconditional!
Consider a noisy 𝑥 :
𝑡
𝑣∅ = 𝑓 (𝑥 ,𝑦 ,𝑡) points toward 𝑝(𝑥) 𝑝
𝜃 𝑡 ∅
𝑑𝑎𝑡𝑎
𝑣𝑦 = 𝑓 (𝑥 ,𝑦,𝑡) points toward 𝑝 𝑥 𝑦
𝜃 𝑡
𝑣𝑐𝑓𝑔 = 1 + 𝑤 𝑣𝑦 − 𝑤𝑣∅ points more toward 𝑝 𝑥 𝑦
During sampling, step according to 𝑣𝑐𝑓𝑔
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 14 - 67 May 20, 2025

[Page contains 2 table(s)]


### Table 1

| Classifier-Free Guidance (CFG)
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training ∅ 𝑣 𝑦
𝑣
much we “emphasize”
the conditioning y? 𝑥
𝑐𝑓𝑔
𝑡 𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Randomly drop y during training.
Now the same model is conditional and unconditional!
Consider a noisy 𝑥 :
𝑡
𝑣∅ = 𝑓 (𝑥 ,𝑦 ,𝑡) points toward 𝑝(𝑥) 𝑝
𝜃 𝑡 ∅
𝑑𝑎𝑡𝑎
𝑣𝑦 = 𝑓 (𝑥 ,𝑦,𝑡) points toward 𝑝 𝑥 𝑦
𝜃 𝑡
𝑣𝑐𝑓𝑔 = 1 + 𝑤 𝑣𝑦 − 𝑤𝑣∅ points more toward 𝑝 𝑥 𝑦
During sampling, step according to 𝑣𝑐𝑓𝑔
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 67 May 20, 2025 |


### Table 2

|  | 𝑝
𝑛𝑜𝑖𝑠𝑒 |  |  |
|  |  |  | 𝑦
𝑣 |
| ∅
𝑣 |  |  |  |
|  |  |  |  |
|  |  | 𝑥
𝑡 |  |


[Page contains 1 image(s)]


---
## Page 68
---


Classifier-Free Guidance (CFG)
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training ∅ 𝑣 𝑦
𝑣
much we “emphasize”
the conditioning y? 𝑥
𝑐𝑓𝑔
𝑡 𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Sampling
𝑝
𝑑𝑎𝑡𝑎
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 14 - 68 May 20, 2025

[Page contains 2 table(s)]


### Table 1

| Classifier-Free Guidance (CFG)
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training ∅ 𝑣 𝑦
𝑣
much we “emphasize”
the conditioning y? 𝑥
𝑐𝑓𝑔
𝑡 𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Sampling
𝑝
𝑑𝑎𝑡𝑎
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 68 May 20, 2025 |


### Table 2

|  | 𝑝
𝑛𝑜𝑖𝑠𝑒 |  |  |
|  |  |  | 𝑦
𝑣 |
| ∅
𝑣 |  |  |  |
|  |  |  |  |
|  |  | 𝑥
𝑡 |  |


[Page contains 2 image(s)]


---
## Page 69
---


Classifier-Free Guidance (CFG)
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training ∅ 𝑣 𝑦
𝑣
much we “emphasize”
the conditioning y? 𝑥
𝑐𝑓𝑔
𝑡 𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Sampling
𝑝
𝑑𝑎𝑡𝑎
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 14 - 69 May 20, 2025

[Page contains 2 table(s)]


### Table 1

| Classifier-Free Guidance (CFG)
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training ∅ 𝑣 𝑦
𝑣
much we “emphasize”
the conditioning y? 𝑥
𝑐𝑓𝑔
𝑡 𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Sampling
𝑝
𝑑𝑎𝑡𝑎
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 69 May 20, 2025 |


### Table 2

|  | 𝑝
𝑛𝑜𝑖𝑠𝑒 |  |  |
|  |  |  | 𝑦
𝑣 |
| ∅
𝑣 |  |  |  |
|  |  |  |  |
|  |  | 𝑥
𝑡 |  |


[Page contains 2 image(s)]


---
## Page 70
---


Classifier-Free Guidance (CFG)
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training ∅ 𝑣 𝑦
𝑣
much we “emphasize”
the conditioning y? 𝑥
𝑐𝑓𝑔
𝑡 𝑣
”Classifier-Free” because
earlier methods used a
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
separate discriminative
model 𝑝(𝑦 ∣ 𝑥) to compute
Sampling 𝜕
step direction log 𝑝(𝑦 ∣ 𝑥)
𝜕𝑥
𝑝
𝑑𝑎𝑡𝑎
Dhariwaland Nichol, “Diffusion Models beat GANs on Image Synthesis”, arXiv2021
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 14 - 70 May 20, 2025

[Page contains 4 table(s)]


### Table 1

| Classifier-Free Guidance (CFG)
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training ∅ 𝑣 𝑦
𝑣
much we “emphasize”
the conditioning y? 𝑥
𝑐𝑓𝑔
𝑡 𝑣
”Classifier-Free” because
earlier methods used a
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
separate discriminative
model 𝑝(𝑦 ∣ 𝑥) to compute
Sampling 𝜕
step direction log 𝑝(𝑦 ∣ 𝑥)
𝜕𝑥
𝑝
𝑑𝑎𝑡𝑎
Dhariwaland Nichol, “Diffusion Models beat GANs on Image Synthesis”, arXiv2021
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 70 May 20, 2025 |


### Table 2

|  | 𝑝
𝑛𝑜𝑖𝑠𝑒 |  |  |
|  |  |  | 𝑦
𝑣 |
| ∅
𝑣 |  |  |  |
|  |  |  |  |
|  |  | 𝑥 |  |
|  |  | 𝑡 |  |


### Table 3

|  |
| 𝑐𝑓𝑔
𝑣
e” beca |


### Table 4

| 𝑐𝑓𝑔
𝑡 𝑣
”Classifier-Free” because
earlier methods used a
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
separate discriminative
model 𝑝(𝑦 ∣ 𝑥) to compute
𝜕
step direction log 𝑝(𝑦 ∣ 𝑥)
𝜕𝑥 |
| model 𝑝
step dire |
|  |


[Page contains 2 image(s)]


---
## Page 71
---


Classifier-Free Guidance (CFG)
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training ∅ 𝑣 𝑦
𝑣
much we “emphasize”
the conditioning y? 𝑥
𝑐𝑓𝑔
𝑡 𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Used everywhere in
Sampling
practice! Very important
for high-quality outputs
𝑝
𝑑𝑎𝑡𝑎
Dhariwaland Nichol, “Diffusion Models beat GANs on Image Synthesis”, arXiv2021
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 14 - 71 May 20, 2025

[Page contains 2 table(s)]


### Table 1

| Classifier-Free Guidance (CFG)
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training ∅ 𝑣 𝑦
𝑣
much we “emphasize”
the conditioning y? 𝑥
𝑐𝑓𝑔
𝑡 𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Used everywhere in
Sampling
practice! Very important
for high-quality outputs
𝑝
𝑑𝑎𝑡𝑎
Dhariwaland Nichol, “Diffusion Models beat GANs on Image Synthesis”, arXiv2021
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 71 May 20, 2025 |


### Table 2

|  | 𝑝
𝑛𝑜𝑖𝑠𝑒 |  |  |
|  |  |  | 𝑦
𝑣 |
| ∅
𝑣 |  |  |  |
|  |  |  |  |
|  |  | 𝑥
𝑡 |  |


[Page contains 2 image(s)]


---
## Page 72
---


Classifier-Free Guidance (CFG)
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training ∅ 𝑣 𝑦
𝑣
much we “emphasize”
the conditioning y? 𝑥
𝑐𝑓𝑔
𝑡 𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Used everywhere in
Sampling
practice! Very important
for high-quality outputs
𝑝
𝑑𝑎𝑡𝑎
Doubles the cost
of sampling…
Dhariwaland Nichol, “Diffusion Models beat GANs on Image Synthesis”, arXiv2021
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 14 - 72 May 20, 2025

[Page contains 2 table(s)]


### Table 1

| Classifier-Free Guidance (CFG)
𝑝
𝑛𝑜𝑖𝑠𝑒
Can we control how
Training ∅ 𝑣 𝑦
𝑣
much we “emphasize”
the conditioning y? 𝑥
𝑐𝑓𝑔
𝑡 𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
Used everywhere in
Sampling
practice! Very important
for high-quality outputs
𝑝
𝑑𝑎𝑡𝑎
Doubles the cost
of sampling…
Dhariwaland Nichol, “Diffusion Models beat GANs on Image Synthesis”, arXiv2021
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 72 May 20, 2025 |


### Table 2

|  | 𝑝
𝑛𝑜𝑖𝑠𝑒 |  |  |
|  |  |  | 𝑦
𝑣 |
| ∅
𝑣 |  |  |  |
|  |  |  |  |
|  |  | 𝑥
𝑡 |  |


[Page contains 2 image(s)]


---
## Page 73
---


Optimal Prediction
𝑝
𝑛𝑜𝑖𝑠𝑒
Training Q: What is the ∅ 𝑣 𝑦
𝑣
optimal prediction
𝑥
for the network?
𝑐𝑓𝑔
𝑡 𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
𝑝
𝑑𝑎𝑡𝑎
Dhariwaland Nichol, “Diffusion Models beat GANs on Image Synthesis”, arXiv2021
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 14 - 73 May 20, 2025

[Page contains 2 table(s)]


### Table 1

| Optimal Prediction
𝑝
𝑛𝑜𝑖𝑠𝑒
Training Q: What is the ∅ 𝑣 𝑦
𝑣
optimal prediction
𝑥
for the network?
𝑐𝑓𝑔
𝑡 𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
𝑝
𝑑𝑎𝑡𝑎
Dhariwaland Nichol, “Diffusion Models beat GANs on Image Synthesis”, arXiv2021
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 73 May 20, 2025 |


### Table 2

|  | 𝑝
𝑛𝑜𝑖𝑠𝑒 |  |  |
|  |  |  | 𝑦
𝑣 |
| ∅
𝑣 |  |  |  |
|  |  |  |  |
|  |  | 𝑥
𝑡 |  |


[Page contains 1 image(s)]


---
## Page 74
---


Optimal Prediction
𝑝
𝑛𝑜𝑖𝑠𝑒
Q: What is the
Training
optimal prediction
for the network?
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
𝑥
𝑡
There may be many pairs (x, z) that give the
same x ; network must average over them
t
𝑝
𝑑𝑎𝑡𝑎
Dhariwaland Nichol, “Diffusion Models beat GANs on Image Synthesis”, arXiv2021
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 14 - 74 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Optimal Prediction
𝑝
𝑛𝑜𝑖𝑠𝑒
Q: What is the
Training
optimal prediction
for the network?
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
𝑥
𝑡
There may be many pairs (x, z) that give the
same x ; network must average over them
t
𝑝
𝑑𝑎𝑡𝑎
Dhariwaland Nichol, “Diffusion Models beat GANs on Image Synthesis”, arXiv2021
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 74 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 75
---


Optimal Prediction
𝑝
𝑛𝑜𝑖𝑠𝑒
Q: What is the
Training
optimal prediction
for the network?
𝑥
𝑡
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
There may be many pairs (x, z) that give the
same x ; network must average over them
t
𝑜𝑝𝑡
Full noise (t=1) is easy: optimal v is mean of p 𝑣
data
𝑝
𝑑𝑎𝑡𝑎
Dhariwaland Nichol, “Diffusion Models beat GANs on Image Synthesis”, arXiv2021
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 14 - 75 May 20, 2025

[Page contains 2 table(s)]


### Table 1

| Optimal Prediction
𝑝
𝑛𝑜𝑖𝑠𝑒
Q: What is the
Training
optimal prediction
for the network?
𝑥
𝑡
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
There may be many pairs (x, z) that give the
same x ; network must average over them
t
𝑜𝑝𝑡
Full noise (t=1) is easy: optimal v is mean of p 𝑣
data
𝑝
𝑑𝑎𝑡𝑎
Dhariwaland Nichol, “Diffusion Models beat GANs on Image Synthesis”, arXiv2021
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 75 May 20, 2025 |


### Table 2

|  |  |
|  |  |


[Page contains 1 image(s)]


---
## Page 76
---


Optimal Prediction
𝑝
𝑛𝑜𝑖𝑠𝑒
Q: What is the
Training
optimal prediction
for the network?
𝑜𝑝𝑡
𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
There may be many pairs (x, z) that give the
same x ; network must average over them
t 𝑥
𝑡
Full noise (t=1) is easy: optimal v is mean of p
data
No noise (t=0) is easy: optimal v is mean of p 𝑝
noise 𝑑𝑎𝑡𝑎
Dhariwaland Nichol, “Diffusion Models beat GANs on Image Synthesis”, arXiv2021
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 14 - 76 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Optimal Prediction
𝑝
𝑛𝑜𝑖𝑠𝑒
Q: What is the
Training
optimal prediction
for the network?
𝑜𝑝𝑡
𝑣
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
There may be many pairs (x, z) that give the
same x ; network must average over them
t 𝑥
𝑡
Full noise (t=1) is easy: optimal v is mean of p
data
No noise (t=0) is easy: optimal v is mean of p 𝑝
noise 𝑑𝑎𝑡𝑎
Dhariwaland Nichol, “Diffusion Models beat GANs on Image Synthesis”, arXiv2021
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 76 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 77
---


Optimal Prediction
𝑝
𝑛𝑜𝑖𝑠𝑒
Q: What is the
Training
optimal prediction
for the network?
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
𝑥
𝑡
There may be many pairs (x, z) that give the
same x ; network must average over them
t
Full noise (t=1) is easy: optimal v is mean of p
data
No noise (t=0) is easy: optimal v is mean of p 𝑝
noise 𝑑𝑎𝑡𝑎
Middle noise is hardest, most ambiguous
Dhariwaland Nichol, “Diffusion Models beat GANs on Image Synthesis”, arXiv2021
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 14 - 77 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Optimal Prediction
𝑝
𝑛𝑜𝑖𝑠𝑒
Q: What is the
Training
optimal prediction
for the network?
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
𝑥
𝑡
There may be many pairs (x, z) that give the
same x ; network must average over them
t
Full noise (t=1) is easy: optimal v is mean of p
data
No noise (t=0) is easy: optimal v is mean of p 𝑝
noise 𝑑𝑎𝑡𝑎
Middle noise is hardest, most ambiguous
Dhariwaland Nichol, “Diffusion Models beat GANs on Image Synthesis”, arXiv2021
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 77 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 78
---


Optimal Prediction
𝑝
𝑛𝑜𝑖𝑠𝑒
Q: What is the
Training
optimal prediction
for the network?
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
𝑥
𝑡
There may be many pairs (x, z) that give the
same x ; network must average over them
t
Full noise (t=1) is easy: optimal v is mean of p
data
No noise (t=0) is easy: optimal v is mean of p 𝑝
noise 𝑑𝑎𝑡𝑎
Middle noise is hardest, most ambiguous
But we give equal weight to all noise levels!
Dhariwaland Nichol, “Diffusion Models beat GANs on Image Synthesis”, arXiv2021
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 14 - 78 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Optimal Prediction
𝑝
𝑛𝑜𝑖𝑠𝑒
Q: What is the
Training
optimal prediction
for the network?
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
𝑥
𝑡
There may be many pairs (x, z) that give the
same x ; network must average over them
t
Full noise (t=1) is easy: optimal v is mean of p
data
No noise (t=0) is easy: optimal v is mean of p 𝑝
noise 𝑑𝑎𝑡𝑎
Middle noise is hardest, most ambiguous
But we give equal weight to all noise levels!
Dhariwaland Nichol, “Diffusion Models beat GANs on Image Synthesis”, arXiv2021
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 78 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 79
---


Optimal Prediction
𝑝
𝑛𝑜𝑖𝑠𝑒
Q: What is the
Training
optimal prediction
for the network?
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
𝑥
𝑡
There may be many pairs (x, z) that give the
same x ; network must average over them
t
Full noise (t=1) is easy: optimal v is mean of p
data
No noise (t=0) is easy: optimal v is mean of p 𝑝
noise 𝑑𝑎𝑡𝑎
Middle noise is hardest, most ambiguous
But we give equal weight to all noise levels!
Solution: Use a non-uniform noise schedule Dhariwaland Nichol, “Diffusion Models beat GANs on Image Synthesis”, arXiv2021
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 14 - 79 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Optimal Prediction
𝑝
𝑛𝑜𝑖𝑠𝑒
Q: What is the
Training
optimal prediction
for the network?
𝑝 𝑥 ∣ 𝑦 = ∎
𝑑𝑎𝑡𝑎
𝑥
𝑡
There may be many pairs (x, z) that give the
same x ; network must average over them
t
Full noise (t=1) is easy: optimal v is mean of p
data
No noise (t=0) is easy: optimal v is mean of p 𝑝
noise 𝑑𝑎𝑡𝑎
Middle noise is hardest, most ambiguous
But we give equal weight to all noise levels!
Solution: Use a non-uniform noise schedule Dhariwaland Nichol, “Diffusion Models beat GANs on Image Synthesis”, arXiv2021
Ho and Salimans, “Classifier-Free Diffusion Guidance”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 79 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 80
---


Noise Schedules
Training
p(t)
t
There may be many pairs (x, z) that give the Put more emphasis on middle noise
same x ; network must average over them
t
Full noise (t=1) is easy: optimal v is mean of p
data
No noise (t=0) is easy: optimal v is mean of p
noise
Middle noise is hardest, most ambiguous
But we give equal weight to all noise levels!
Solution: Use a non-uniform noise schedule
Esseret al, “Scaling Rectified Flow Transformers for High-Resolution Image Synthesis”, arXiv2024
Stanford CS231n 10th Anniversary Lecture 14 - 80 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Noise Schedules
Training
p(t)
t
There may be many pairs (x, z) that give the Put more emphasis on middle noise
same x ; network must average over them
t
Full noise (t=1) is easy: optimal v is mean of p
data
No noise (t=0) is easy: optimal v is mean of p
noise
Middle noise is hardest, most ambiguous
But we give equal weight to all noise levels!
Solution: Use a non-uniform noise schedule
Esseret al, “Scaling Rectified Flow Transformers for High-Resolution Image Synthesis”, arXiv2024 |
| Stanford CS231n 10th Anniversary Lecture 14 - 80 May 20, 2025 |


[Page contains 2 image(s)]


---
## Page 81
---


Noise Schedules
Training
p(t)
t
There may be many pairs (x, z) that give the Put more emphasis on middle noise
same x ; network must average over them
t Common choice: logit-normal sampling
Full noise (t=1) is easy: optimal v is mean of p
data
No noise (t=0) is easy: optimal v is mean of p
noise
Middle noise is hardest, most ambiguous
But we give equal weight to all noise levels!
Solution: Use a non-uniform noise schedule
Esseret al, “Scaling Rectified Flow Transformers for High-Resolution Image Synthesis”, arXiv2024
Stanford CS231n 10th Anniversary Lecture 14 - 81 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Noise Schedules
Training
p(t)
t
There may be many pairs (x, z) that give the Put more emphasis on middle noise
same x ; network must average over them
t Common choice: logit-normal sampling
Full noise (t=1) is easy: optimal v is mean of p
data
No noise (t=0) is easy: optimal v is mean of p
noise
Middle noise is hardest, most ambiguous
But we give equal weight to all noise levels!
Solution: Use a non-uniform noise schedule
Esseret al, “Scaling Rectified Flow Transformers for High-Resolution Image Synthesis”, arXiv2024 |
| Stanford CS231n 10th Anniversary Lecture 14 - 81 May 20, 2025 |


[Page contains 2 image(s)]


---
## Page 82
---


Noise Schedules
Training
p(t)
t
There may be many pairs (x, z) that give the Put more emphasis on middle noise
same x ; network must average over them
t Common choice: logit-normal sampling
Full noise (t=1) is easy: optimal v is mean of p
data For high-res data, often shift to higher
No noise (t=0) is easy: optimal v is mean of p
noise noise to account for pixel correlations
Middle noise is hardest, most ambiguous
But we give equal weight to all noise levels!
Solution: Use a non-uniform noise schedule
Esseret al, “Scaling Rectified Flow Transformers for High-Resolution Image Synthesis”, arXiv2024
Stanford CS231n 10th Anniversary Lecture 14 - 82 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Noise Schedules
Training
p(t)
t
There may be many pairs (x, z) that give the Put more emphasis on middle noise
same x ; network must average over them
t Common choice: logit-normal sampling
Full noise (t=1) is easy: optimal v is mean of p
data For high-res data, often shift to higher
No noise (t=0) is easy: optimal v is mean of p
noise noise to account for pixel correlations
Middle noise is hardest, most ambiguous
But we give equal weight to all noise levels!
Solution: Use a non-uniform noise schedule
Esseret al, “Scaling Rectified Flow Transformers for High-Resolution Image Synthesis”, arXiv2024 |
| Stanford CS231n 10th Anniversary Lecture 14 - 82 May 20, 2025 |


[Page contains 2 image(s)]


---
## Page 83
---


Diffusion: Rectified Flow
Simple and scalable setup
Training
for many generative
p(t)
modeling problems!
t
Put more emphasis on middle noise
Sampling
Common choice: logit-normal sampling
For high-res data, often shift to higher
noise to account for pixel correlations
Esseret al, “Scaling Rectified Flow Transformers for High-Resolution Image Synthesis”, arXiv2024
Stanford CS231n 10th Anniversary Lecture 14 - 83 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Diffusion: Rectified Flow
Simple and scalable setup
Training
for many generative
p(t)
modeling problems!
t
Put more emphasis on middle noise
Sampling
Common choice: logit-normal sampling
For high-res data, often shift to higher
noise to account for pixel correlations
Esseret al, “Scaling Rectified Flow Transformers for High-Resolution Image Synthesis”, arXiv2024 |
| Stanford CS231n 10th Anniversary Lecture 14 - 83 May 20, 2025 |


[Page contains 3 image(s)]


---
## Page 84
---


Diffusion: Rectified Flow
Simple and scalable setup
Training
for many generative
p(t)
modeling problems!
t
Problem: Does not Put more emphasis on middle noise
Sampling
work naively on high-
Common choice: logit-normal sampling
resolution data
For high-res data, often shift to higher
noise to account for pixel correlations
Esseret al, “Scaling Rectified Flow Transformers for High-Resolution Image Synthesis”, arXiv2024
Stanford CS231n 10th Anniversary Lecture 14 - 84 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Diffusion: Rectified Flow
Simple and scalable setup
Training
for many generative
p(t)
modeling problems!
t
Problem: Does not Put more emphasis on middle noise
Sampling
work naively on high-
Common choice: logit-normal sampling
resolution data
For high-res data, often shift to higher
noise to account for pixel correlations
Esseret al, “Scaling Rectified Flow Transformers for High-Resolution Image Synthesis”, arXiv2024 |
| Stanford CS231n 10th Anniversary Lecture 14 - 84 May 20, 2025 |


[Page contains 3 image(s)]


---
## Page 85
---


Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train encoder + decoder to
convert images to latents
Image
H x W x 3
Decoder
Latent
H/D x W/D x C
Encoder
Image
H x W x 3
Stanford CS231n 10th Anniversary Lecture 14 - 85 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train encoder + decoder to
convert images to latents
Image
H x W x 3
Decoder
Latent
H/D x W/D x C
Encoder
Image
H x W x 3 |
| Stanford CS231n 10th Anniversary Lecture 14 - 85 May 20, 2025 |


[Page contains 2 image(s)]


---
## Page 86
---


Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train encoder + decoder to
convert images to latents
Image
H x W x 3
Common setting: D=8, C=16
Decoder
Image: 256 x 256 x 3
=> Latent: 32 x 32 x 16
Latent
H/D x W/D x C
Encoder / Decoder are CNNs with attention
Encoder
Image
H x W x 3
Stanford CS231n 10th Anniversary Lecture 14 - 86 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train encoder + decoder to
convert images to latents
Image
H x W x 3
Common setting: D=8, C=16
Decoder
Image: 256 x 256 x 3
=> Latent: 32 x 32 x 16
Latent
H/D x W/D x C
Encoder / Decoder are CNNs with attention
Encoder
Image
H x W x 3 |
| Stanford CS231n 10th Anniversary Lecture 14 - 86 May 20, 2025 |


[Page contains 2 image(s)]


---
## Page 87
---


Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train diffusion model to
Train encoder + decoder to
remove noise from latents
convert images to latents
(Encoder is frozen)
Denoised Latent
Image
H/D x W/D x C
H x W x 3
Decoder
Latent
H/D x W/D x C
Encoder
Noisy Latent
H/D x W/D x C
Image
H x W x 3
Stanford CS231n 10th Anniversary Lecture 14 - 87 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train diffusion model to
Train encoder + decoder to
remove noise from latents
convert images to latents
(Encoder is frozen)
Denoised Latent
Image
H/D x W/D x C
H x W x 3
Decoder
Latent
H/D x W/D x C
Encoder
Noisy Latent
H/D x W/D x C
Image
H x W x 3 |
| Stanford CS231n 10th Anniversary Lecture 14 - 87 May 20, 2025 |


[Page contains 4 image(s)]


---
## Page 88
---


Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train diffusion model to
Train encoder + decoder to After training:
remove noise from latents
convert images to latents
(Encoder is frozen)
Denoised Latent
Image
H/D x W/D x C
H x W x 3
Decoder
Latent
H/D x W/D x C
Encoder
Noisy Latent
H/D x W/D x C
Image
H x W x 3
Stanford CS231n 10th Anniversary Lecture 14 - 88 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train diffusion model to
Train encoder + decoder to After training:
remove noise from latents
convert images to latents
(Encoder is frozen)
Denoised Latent
Image
H/D x W/D x C
H x W x 3
Decoder
Latent
H/D x W/D x C
Encoder
Noisy Latent
H/D x W/D x C
Image
H x W x 3 |
| Stanford CS231n 10th Anniversary Lecture 14 - 88 May 20, 2025 |


[Page contains 4 image(s)]


---
## Page 89
---


Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train diffusion model to
Train encoder + decoder to After training:
remove noise from latents
convert images to latents
(Encoder is frozen)
Sample random
latent
Denoised Latent
Image
H/D x W/D x C
H x W x 3
Decoder
Latent
H/D x W/D x C
Encoder
Noisy Latent
H/D x W/D x C
Image
H x W x 3
Stanford CS231n 10th Anniversary Lecture 14 - 89 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train diffusion model to
Train encoder + decoder to After training:
remove noise from latents
convert images to latents
(Encoder is frozen)
Sample random
latent
Denoised Latent
Image
H/D x W/D x C
H x W x 3
Decoder
Latent
H/D x W/D x C
Encoder
Noisy Latent
H/D x W/D x C
Image
H x W x 3 |
| Stanford CS231n 10th Anniversary Lecture 14 - 89 May 20, 2025 |


[Page contains 5 image(s)]


---
## Page 90
---


Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train diffusion model to
Train encoder + decoder to After training:
remove noise from latents
convert images to latents
(Encoder is frozen)
Sample random
latent
Denoised Latent
Image
H/D x W/D x C
H x W x 3
Iteratively apply
…
diffusion model
Decoder
to remove noise
Latent
H/D x W/D x C
Encoder
Noisy Latent
H/D x W/D x C
Image
H x W x 3
Stanford CS231n 10th Anniversary Lecture 14 - 90 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train diffusion model to
Train encoder + decoder to After training:
remove noise from latents
convert images to latents
(Encoder is frozen)
Sample random
latent
Denoised Latent
Image
H/D x W/D x C
H x W x 3
Iteratively apply
…
diffusion model
Decoder
to remove noise
Latent
H/D x W/D x C
Encoder
Noisy Latent
H/D x W/D x C
Image
H x W x 3 |
| Stanford CS231n 10th Anniversary Lecture 14 - 90 May 20, 2025 |


[Page contains 7 image(s)]


---
## Page 91
---


Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train diffusion model to
Train encoder + decoder to After training:
remove noise from latents
convert images to latents
(Encoder is frozen)
Sample random
latent
Denoised Latent
Image
H/D x W/D x C
H x W x 3
Iteratively apply
…
diffusion model
Decoder
to remove noise
Latent
run decoder to
H/D x W/D x C
get image
Encoder
Noisy Latent
H/D x W/D x C
Image
H x W x 3
Stanford CS231n 10th Anniversary Lecture 14 - 91 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train diffusion model to
Train encoder + decoder to After training:
remove noise from latents
convert images to latents
(Encoder is frozen)
Sample random
latent
Denoised Latent
Image
H/D x W/D x C
H x W x 3
Iteratively apply
…
diffusion model
Decoder
to remove noise
Latent
run decoder to
H/D x W/D x C
get image
Encoder
Noisy Latent
H/D x W/D x C
Image
H x W x 3 |
| Stanford CS231n 10th Anniversary Lecture 14 - 91 May 20, 2025 |


[Page contains 8 image(s)]


---
## Page 92
---


Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train diffusion model to
Train encoder + decoder to After training:
remove noise from latents
convert images to latents
(Encoder is frozen)
Sample random
latent
Denoised Latent
Image
H/D x W/D x C
H x W x 3
Iteratively apply
…
diffusion model
Decoder
to remove noise
Latent
run decoder to
H/D x W/D x C
get image
Encoder
Noisy Latent
H/D x W/D x C
Image
Latent diffusion is the most
H x W x 3
common form today
Stanford CS231n 10th Anniversary Lecture 14 - 92 May 20, 2025

[Page contains 2 table(s)]


### Table 1

| Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train diffusion model to
Train encoder + decoder to After training:
remove noise from latents
convert images to latents
(Encoder is frozen)
Sample random
latent
Denoised Latent
Image
H/D x W/D x C
H x W x 3
Iteratively apply
…
diffusion model
Decoder
to remove noise
Latent
run decoder to
H/D x W/D x C
get image
Encoder
Noisy Latent
H/D x W/D x C
Image
Latent diffusion is the most
H x W x 3
common form today |
| Stanford CS231n 10th Anniversary Lecture 14 - 92 May 20, 2025 |


### Table 2

| Train diffusion model to
remove noise from latents
(Encoder is frozen)
Denoised Latent
H/D x W/D x C
Noisy Latent
H/D x W/D x C
Latent diffu
common |  |  | After training:
Sample random
latent
Iteratively apply
…
diffusion model
to remove noise
run decoder to
get image
on is the most
form today |
|  | Latent diffu
common | si | on is the most
form today |


[Page contains 8 image(s)]


---
## Page 93
---


Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train encoder + decoder to How do we train the
convert images to latents encoder+decoder?
Image
H x W x 3
Decoder
Latent
H/D x W/D x C
Encoder
Image
H x W x 3
Stanford CS231n 10th Anniversary Lecture 14 - 93 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train encoder + decoder to How do we train the
convert images to latents encoder+decoder?
Image
H x W x 3
Decoder
Latent
H/D x W/D x C
Encoder
Image
H x W x 3 |
| Stanford CS231n 10th Anniversary Lecture 14 - 93 May 20, 2025 |


[Page contains 2 image(s)]


---
## Page 94
---


Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train encoder + decoder to How do we train the
convert images to latents encoder+decoder? Recall: VAE
Solution: It’s a VAE!
Image
Typically with very
H x W x 3
small KL prior weight
Decoder
Latent
H/D x W/D x C
Encoder
Image
H x W x 3
Stanford CS231n 10th Anniversary Lecture 14 - 94 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train encoder + decoder to How do we train the
convert images to latents encoder+decoder? Recall: VAE
Solution: It’s a VAE!
Image
Typically with very
H x W x 3
small KL prior weight
Decoder
Latent
H/D x W/D x C
Encoder
Image
H x W x 3 |
| Stanford CS231n 10th Anniversary Lecture 14 - 94 May 20, 2025 |


[Page contains 3 image(s)]


---
## Page 95
---


Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train encoder + decoder to How do we train the
convert images to latents encoder+decoder? Recall: VAE
Solution: It’s a VAE!
Image
Typically with very
H x W x 3
small KL prior weight
Decoder
Problem: Decoder
outputs often blurry
Latent
H/D x W/D x C
Encoder
Image
H x W x 3
Stanford CS231n 10th Anniversary Lecture 14 - 95 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train encoder + decoder to How do we train the
convert images to latents encoder+decoder? Recall: VAE
Solution: It’s a VAE!
Image
Typically with very
H x W x 3
small KL prior weight
Decoder
Problem: Decoder
outputs often blurry
Latent
H/D x W/D x C
Encoder
Image
H x W x 3 |
| Stanford CS231n 10th Anniversary Lecture 14 - 95 May 20, 2025 |


[Page contains 3 image(s)]


---
## Page 96
---


Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
How do we train the
Discriminator encoder+decoder? Recall: VAE
Solution: It’s a VAE!
Real Fake
Typically with very
image image
small KL prior weight
Decoder
Problem: Decoder
outputs often blurry
Latent
Recall: GAN
H/D x W/D x C
Solution: Add a
discriminator!
Encoder
Image
H x W x 3
Stanford CS231n 10th Anniversary Lecture 14 - 96 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
How do we train the
Discriminator encoder+decoder? Recall: VAE
Solution: It’s a VAE!
Real Fake
Typically with very
image image
small KL prior weight
Decoder
Problem: Decoder
outputs often blurry
Latent
Recall: GAN
H/D x W/D x C
Solution: Add a
discriminator!
Encoder
Image
H x W x 3 |
| Stanford CS231n 10th Anniversary Lecture 14 - 96 May 20, 2025 |


[Page contains 5 image(s)]


---
## Page 97
---


Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train diffusion model to
After training:
remove noise from latents
Discriminator
(Encoder is frozen)
Sample random
latent
Real Fake
image image
Iteratively apply
…
diffusion model
Decoder
to remove noise
Latent
run decoder to
H/D x W/D x C
get image
Encoder
Modern LDM pipelines use
Image
VAE + GAN + diffusion!
H x W x 3
Stanford CS231n 10th Anniversary Lecture 14 - 97 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Rombachet al, “High-Resolution Image Synthesis
with Latent Diffusion Models”, CVPR 2022
Latent Diffusion Models (LDMs)
Train diffusion model to
After training:
remove noise from latents
Discriminator
(Encoder is frozen)
Sample random
latent
Real Fake
image image
Iteratively apply
…
diffusion model
Decoder
to remove noise
Latent
run decoder to
H/D x W/D x C
get image
Encoder
Modern LDM pipelines use
Image
VAE + GAN + diffusion!
H x W x 3 |
| Stanford CS231n 10th Anniversary Lecture 14 - 97 May 20, 2025 |


[Page contains 9 image(s)]


---
## Page 98
---


Peebles and Xie, ”Scalable Diffusion
Models with Transformer”, ICCV 2023
Diffusion Transformer (DiT)
Diffusion uses standard Transformer blocks!
Main question: How to inject conditioning (timestep t, text, …)
Stanford CS231n 10th Anniversary Lecture 14 - 98 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Peebles and Xie, ”Scalable Diffusion
Models with Transformer”, ICCV 2023
Diffusion Transformer (DiT)
Diffusion uses standard Transformer blocks!
Main question: How to inject conditioning (timestep t, text, …) |
| Stanford CS231n 10th Anniversary Lecture 14 - 98 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 99
---


Peebles and Xie, ”Scalable Diffusion
Models with Transformer”, ICCV 2023
Diffusion Transformer (DiT)
Diffusion uses standard Transformer blocks!
Main question: How to inject conditioning (timestep t, text, …)
Predict scale/shift:
Most common for
diffusion timestep t
Stanford CS231n 10th Anniversary Lecture 14 - 99 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Peebles and Xie, ”Scalable Diffusion
Models with Transformer”, ICCV 2023
Diffusion Transformer (DiT)
Diffusion uses standard Transformer blocks!
Main question: How to inject conditioning (timestep t, text, …)
Predict scale/shift:
Most common for
diffusion timestep t |
| Stanford CS231n 10th Anniversary Lecture 14 - 99 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 100
---


Peebles and Xie, ”Scalable Diffusion
Models with Transformer”, ICCV 2023
Diffusion Transformer (DiT)
Diffusion uses standard Transformer blocks!
Main question: How to inject conditioning (timestep t, text, …)
Predict scale/shift:
Cross-Attention / Joint Attention:
Most common for
Common for text, image, etc conditioning
diffusion timestep t
Stanford CS231n 10th Anniversary Lecture 14 - 100 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Peebles and Xie, ”Scalable Diffusion
Models with Transformer”, ICCV 2023
Diffusion Transformer (DiT)
Diffusion uses standard Transformer blocks!
Main question: How to inject conditioning (timestep t, text, …)
Predict scale/shift:
Cross-Attention / Joint Attention:
Most common for
Common for text, image, etc conditioning
diffusion timestep t |
| Stanford CS231n 10th Anniversary Lecture 14 - 100 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 101
---


Text-to-Image Diffusion
timestep
(scalar)
Noisy latents
h x w x c
Diffusion Clean latents Output image
Decoder
Transformer h x w x c H x W x 3
Text embeddings
D x L
Pretrained
text encoder
(e.g. T5, CLIP)
Text Prompt
A professional documentary photograph of a
monkey shaking hands with a tiger in front of
the Eiffel tower. The monkey is wearing a hat
made out of bananas, and the tiger is
standing on two legs and wearing a suit.
Stanford CS231n 10th Anniversary Lecture 14 - 101 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Text-to-Image Diffusion
timestep
(scalar)
Noisy latents
h x w x c
Diffusion Clean latents Output image
Decoder
Transformer h x w x c H x W x 3
Text embeddings
D x L
Pretrained
text encoder
(e.g. T5, CLIP)
Text Prompt
A professional documentary photograph of a
monkey shaking hands with a tiger in front of
the Eiffel tower. The monkey is wearing a hat
made out of bananas, and the tiger is
standing on two legs and wearing a suit. |
| Stanford CS231n 10th Anniversary Lecture 14 - 101 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 102
---


Text-to-Image Diffusion
timestep
(scalar)
Noisy latents
128 x 128 x 16
Diffusion Clean latents Output image
Decoder
Transformer 128 x 128 x 16 1024 x 1024 x 3
Text embeddings
D x L
Pretrained
text encoder
Example: FLUX.1 [dev]
(e.g. T5, CLIP)
Text Encoder: T5 + CLIP
Encoder/Decoder: 8x8 downsampling
Text Prompt Diffusion model: 12B parameter model
A professional documentary photograph of a 2x2 patchify=> 64x64 = 1024 image tokens
monkey shaking hands with a tiger in front of
the Eiffel tower. The monkey is wearing a hat
made out of bananas, and the tiger is
https://github.com/black-forest-labs/flux
standing on two legs and wearing a suit.
Stanford CS231n 10th Anniversary Lecture 14 - 102 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Text-to-Image Diffusion
timestep
(scalar)
Noisy latents
128 x 128 x 16
Diffusion Clean latents Output image
Decoder
Transformer 128 x 128 x 16 1024 x 1024 x 3
Text embeddings
D x L
Pretrained
text encoder
Example: FLUX.1 [dev]
(e.g. T5, CLIP)
Text Encoder: T5 + CLIP
Encoder/Decoder: 8x8 downsampling
Text Prompt Diffusion model: 12B parameter model
A professional documentary photograph of a 2x2 patchify=> 64x64 = 1024 image tokens
monkey shaking hands with a tiger in front of
the Eiffel tower. The monkey is wearing a hat
made out of bananas, and the tiger is
https://github.com/black-forest-labs/flux
standing on two legs and wearing a suit. |
| Stanford CS231n 10th Anniversary Lecture 14 - 102 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 103
---


Gupta et al, “Photorealistic Video Generation with Diffusion Models”, arXiv2023 (Dec)
OpenAI, “Sora: Creating Video from Text”, 2024 (Feb)
Text-to-Video Diffusion Polyaket al, “Movie Gen: A Cast of Media Foundation Models”, arXiv2024 (Oct)
Kong et al, “HunyuanVideo: A Systematic Framework for Large Video Generative Models”, arXiv2024 (Dec)
timestep NVIDIA, “Cosmos World Foundation Model Platform for Physical AI”, arXiv2025 (Jan)
Team Wan, “Wan: Open and Advanced Large-Scale Video Generative Models”, arXiv2025 (March)
(scalar)
Noisy latents
t x h x w x c
Diffusion Clean latents Output video
Decoder
Transformer t x h x w x c T x H x W x 3
Text embeddings
D x L
Pretrained
text encoder
(e.g. T5, CLIP)
Text Prompt
A red-faced monkey with white fur is bathing in a
natural hot spring. The monkey is playing in the water
with a miniature sail ship in front of it, made of wood
with a white sail and a small rudder. The hot spring is
surrounded by lush greenery, with rocks and trees.
Stanford CS231n 10th Anniversary Lecture 14 - 103 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Gupta et al, “Photorealistic Video Generation with Diffusion Models”, arXiv2023 (Dec)
OpenAI, “Sora: Creating Video from Text”, 2024 (Feb)
Text-to-Video Diffusion Polyaket al, “Movie Gen: A Cast of Media Foundation Models”, arXiv2024 (Oct)
Kong et al, “HunyuanVideo: A Systematic Framework for Large Video Generative Models”, arXiv2024 (Dec)
timestep NVIDIA, “Cosmos World Foundation Model Platform for Physical AI”, arXiv2025 (Jan)
Team Wan, “Wan: Open and Advanced Large-Scale Video Generative Models”, arXiv2025 (March)
(scalar)
Noisy latents
t x h x w x c
Diffusion Clean latents Output video
Decoder
Transformer t x h x w x c T x H x W x 3
Text embeddings
D x L
Pretrained
text encoder
(e.g. T5, CLIP)
Text Prompt
A red-faced monkey with white fur is bathing in a
natural hot spring. The monkey is playing in the water
with a miniature sail ship in front of it, made of wood
with a white sail and a small rudder. The hot spring is
surrounded by lush greenery, with rocks and trees. |
| Stanford CS231n 10th Anniversary Lecture 14 - 103 May 20, 2025 |


---
## Page 104
---


Gupta et al, “Photorealistic Video Generation with Diffusion Models”, arXiv2023 (Dec)
OpenAI, “Sora: Creating Video from Text”, 2024 (Feb)
Text-to-Video Diffusion Polyaket al, “Movie Gen: A Cast of Media Foundation Models”, arXiv2024 (Oct)
Kong et al, “HunyuanVideo: A Systematic Framework for Large Video Generative Models”, arXiv2024 (Dec)
timestep NVIDIA, “Cosmos World Foundation Model Platform for Physical AI”, arXiv2025 (Jan)
Team Wan, “Wan: Open and Advanced Large-Scale Video Generative Models”, arXiv2025 (March)
(scalar)
Noisy latents
t x h x w x c
Diffusion Clean latents Output video
Decoder
Transformer t x h x w x c T x H x W x 3
Text embeddings
D x L
Pretrained
text encoder
(e.g. T5, CLIP)
Text Prompt
A red-faced monkey with white fur is bathing in a
natural hot spring. The monkey is playing in the water
with a miniature sail ship in front of it, made of wood
with a white sail and a small rudder. The hot spring is
Video from Meta Movie Gen
surrounded by lush greenery, with rocks and trees.
(https://ai.meta.com/research/movie-gen/)
Stanford CS231n 10th Anniversary Lecture 14 - 104 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Gupta et al, “Photorealistic Video Generation with Diffusion Models”, arXiv2023 (Dec)
OpenAI, “Sora: Creating Video from Text”, 2024 (Feb)
Text-to-Video Diffusion Polyaket al, “Movie Gen: A Cast of Media Foundation Models”, arXiv2024 (Oct)
Kong et al, “HunyuanVideo: A Systematic Framework for Large Video Generative Models”, arXiv2024 (Dec)
timestep NVIDIA, “Cosmos World Foundation Model Platform for Physical AI”, arXiv2025 (Jan)
Team Wan, “Wan: Open and Advanced Large-Scale Video Generative Models”, arXiv2025 (March)
(scalar)
Noisy latents
t x h x w x c
Diffusion Clean latents Output video
Decoder
Transformer t x h x w x c T x H x W x 3
Text embeddings
D x L
Pretrained
text encoder
(e.g. T5, CLIP)
Text Prompt
A red-faced monkey with white fur is bathing in a
natural hot spring. The monkey is playing in the water
with a miniature sail ship in front of it, made of wood
with a white sail and a small rudder. The hot spring is
Video from Meta Movie Gen
surrounded by lush greenery, with rocks and trees.
(https://ai.meta.com/research/movie-gen/) |
| Stanford CS231n 10th Anniversary Lecture 14 - 104 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 105
---


Gupta et al, “Photorealistic Video Generation with Diffusion Models”, arXiv2023 (Dec)
OpenAI, “Sora: Creating Video from Text”, 2024 (Feb)
Text-to-Video Diffusion Polyaket al, “Movie Gen: A Cast of Media Foundation Models”, arXiv2024 (Oct)
Kong et al, “HunyuanVideo: A Systematic Framework for Large Video Generative Models”, arXiv2024 (Dec)
timestep NVIDIA, “Cosmos World Foundation Model Platform for Physical AI”, arXiv2025 (Jan)
Team Wan, “Wan: Open and Advanced Large-Scale Video Generative Models”, arXiv2025 (March)
(scalar)
Noisy latents
32 x 128 x 72 x 16
Diffusion Clean latents Output video
Decoder
Transformer 33 x 128 x 72 x 16 257 x 1024 x 576 x 3
Text embeddings
D x L
Pretrained
text encoder
(e.g. T5, CLIP) Example: Meta MovieGen
Text Encoder: UL2, ByT5, MetaCLIP
Encoder/Decoder: 8x8x8 downsample
Text Prompt Diffusion model: 30B param DiT
A red-faced monkey with white fur is bathing in a 1x2x2 patchify=> 76K tokens
natural hot spring. The monkey is playing in the water
with a miniature sail ship in front of it, made of wood
with a white sail and a small rudder. The hot spring is
surrounded by lush greenery, with rocks and trees.
Stanford CS231n 10th Anniversary Lecture 14 - 105 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Gupta et al, “Photorealistic Video Generation with Diffusion Models”, arXiv2023 (Dec)
OpenAI, “Sora: Creating Video from Text”, 2024 (Feb)
Text-to-Video Diffusion Polyaket al, “Movie Gen: A Cast of Media Foundation Models”, arXiv2024 (Oct)
Kong et al, “HunyuanVideo: A Systematic Framework for Large Video Generative Models”, arXiv2024 (Dec)
timestep NVIDIA, “Cosmos World Foundation Model Platform for Physical AI”, arXiv2025 (Jan)
Team Wan, “Wan: Open and Advanced Large-Scale Video Generative Models”, arXiv2025 (March)
(scalar)
Noisy latents
32 x 128 x 72 x 16
Diffusion Clean latents Output video
Decoder
Transformer 33 x 128 x 72 x 16 257 x 1024 x 576 x 3
Text embeddings
D x L
Pretrained
text encoder
(e.g. T5, CLIP) Example: Meta MovieGen
Text Encoder: UL2, ByT5, MetaCLIP
Encoder/Decoder: 8x8x8 downsample
Text Prompt Diffusion model: 30B param DiT
A red-faced monkey with white fur is bathing in a 1x2x2 patchify=> 76K tokens
natural hot spring. The monkey is playing in the water
with a miniature sail ship in front of it, made of wood
with a white sail and a small rudder. The hot spring is
surrounded by lush greenery, with rocks and trees. |
| Stanford CS231n 10th Anniversary Lecture 14 - 105 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 106
---


The Era of Video Diffusion Models
Cosmos
(NVIDIA)
Open-Source Model
14B params
Technical Report
No technical info Ray 2 (Luma)
Veo 2
CogVideoX
(Google)
(Zhipu)
Mochi
5B params
(Genmo)
LTX-Video Step-Video
Gen3 (Runway) 10B params Kling 2.0
(Lightricks) (StepFun)
(Kuaishou)
Sora (OpenAI) 2B params 30B params
Dream Machine MovieGen
(Luma) (Meta) Wan
Hunyuan
WALT (Google) (Alibaba)
30B params
(Tencent)
460M params 14B params
13B params
January March May July Sept Nov January March May
2024 2024 2024 2024 2024 2024 2025 2024 2024
Gupta et al, “Photorealistic Video Generation with Diffusion Models”, arXiv2023 (Dec)
Polyaket al, “Movie Gen: AO pCeansAt Io, f“ MSoerdai:a C Froeuantidnag tVioind eMoo fdroemls” ,T aerxXti”v, 22002244 ((FOecbt))
Kong et al, “HunyuanVideo: A Systematic Framework for Large Video Generative Models”, arXiv2024 (Dec)
NVIDIA, “Cosmos World Foundation Model Platform for Physical AI”, arXiv2025 (Jan)
Team Wan, “Wan: Open and Advanced Large-Scale Video Generative Models”, arXiv2025 (March)
Stanford CS231n 10th Anniversary Lecture 14 - 106 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| The Era of Video Diffusion Models
Cosmos
(NVIDIA)
Open-Source Model
14B params
Technical Report
No technical info Ray 2 (Luma)
Veo 2
CogVideoX
(Google)
(Zhipu)
Mochi
5B params
(Genmo)
LTX-Video Step-Video
Gen3 (Runway) 10B params Kling 2.0
(Lightricks) (StepFun)
(Kuaishou)
Sora (OpenAI) 2B params 30B params
Dream Machine MovieGen
(Luma) (Meta) Wan
Hunyuan
WALT (Google) (Alibaba)
30B params
(Tencent)
460M params 14B params
13B params
January March May July Sept Nov January March May
2024 2024 2024 2024 2024 2024 2025 2024 2024
Gupta et al, “Photorealistic Video Generation with Diffusion Models”, arXiv2023 (Dec)
Polyaket al, “Movie Gen: AO pCeansAt Io, f“ MSoerdai:a C Froeuantidnag tVioind eMoo fdroemls” ,T aerxXti”v, 22002244 ((FOecbt))
Kong et al, “HunyuanVideo: A Systematic Framework for Large Video Generative Models”, arXiv2024 (Dec)
NVIDIA, “Cosmos World Foundation Model Platform for Physical AI”, arXiv2025 (Jan)
Team Wan, “Wan: Open and Advanced Large-Scale Video Generative Models”, arXiv2025 (March) |
| Stanford CS231n 10th Anniversary Lecture 14 - 106 May 20, 2025 |


---
## Page 107
---


Diffusion Distillation
After training:
During sampling we need to run the diffusion model
Sample random
many times (~30 – 50 for rectified flow)
latent
This is really slow! Iteratively apply
…
diffusion model
to remove noise
run decoder to
get image
Stanford CS231n 10th Anniversary Lecture 14 - 107 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Diffusion Distillation
After training:
During sampling we need to run the diffusion model
Sample random
many times (~30 – 50 for rectified flow)
latent
This is really slow! Iteratively apply
…
diffusion model
to remove noise
run decoder to
get image |
| Stanford CS231n 10th Anniversary Lecture 14 - 107 May 20, 2025 |


[Page contains 4 image(s)]


---
## Page 108
---


Diffusion Distillation
After training:
During sampling we need to run the diffusion model
Sample random
many times (~30 – 50 for rectified flow)
latent
This is really slow! Iteratively apply
…
diffusion model
to remove noise
Solution: distillation algorithms reduce the number
of steps (sometimes all the way to 1),
run decoder to
can also bake in CFG get image
Salimansand Ho, “Progressive Distillation for Fast Sampling of Diffusion Models”, ICLR 2022
Song et al, “Consistency Models”, ICML 2023
Sauer et al, “Adversarial Diffusion Distillation”, ECCV 2024
Sauer et al, “Fast High-Resolution Image Synthesis with Latent Adversarial Diffusion Distillation”, arXiv2024
Lu and Song, “Simplifying, Stabilizing and Scaling Consistency Models”, ICLR 2025
Salimanset al, “Multistep Distillation of Diffusion Models via Moment Matching”, NeurIPS2025
Stanford CS231n 10th Anniversary Lecture 14 - 108 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Diffusion Distillation
After training:
During sampling we need to run the diffusion model
Sample random
many times (~30 – 50 for rectified flow)
latent
This is really slow! Iteratively apply
…
diffusion model
to remove noise
Solution: distillation algorithms reduce the number
of steps (sometimes all the way to 1),
run decoder to
can also bake in CFG get image
Salimansand Ho, “Progressive Distillation for Fast Sampling of Diffusion Models”, ICLR 2022
Song et al, “Consistency Models”, ICML 2023
Sauer et al, “Adversarial Diffusion Distillation”, ECCV 2024
Sauer et al, “Fast High-Resolution Image Synthesis with Latent Adversarial Diffusion Distillation”, arXiv2024
Lu and Song, “Simplifying, Stabilizing and Scaling Consistency Models”, ICLR 2025
Salimanset al, “Multistep Distillation of Diffusion Models via Moment Matching”, NeurIPS2025 |
| Stanford CS231n 10th Anniversary Lecture 14 - 108 May 20, 2025 |


[Page contains 4 image(s)]


---
## Page 109
---


Generalized Diffusion
Rectified Flow
Sample 𝑥 ∼ 𝑝 , 𝑧 ∼ 𝑝
𝑑𝑎𝑡𝑎 𝑛𝑜𝑖𝑠𝑒
Sample 𝑡 ∼ 𝑝
𝑡
Set 𝑥 = 1 − 𝑡 𝑥 + 𝑡𝑧
𝑡
Set 𝑣 = 𝑧 − 𝑥
𝑔𝑡
Compute 𝑣 = 𝑓 𝑥 , 𝑡
𝑝𝑟𝑒𝑑 𝜃 𝑡
2
Compute loss 𝑣 − 𝑣
𝑔𝑡 𝑝𝑟𝑒𝑑
2
Stanford CS231n 10th Anniversary Lecture 14 - 109 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Generalized Diffusion
Rectified Flow
Sample 𝑥 ∼ 𝑝 , 𝑧 ∼ 𝑝
𝑑𝑎𝑡𝑎 𝑛𝑜𝑖𝑠𝑒
Sample 𝑡 ∼ 𝑝
𝑡
Set 𝑥 = 1 − 𝑡 𝑥 + 𝑡𝑧
𝑡
Set 𝑣 = 𝑧 − 𝑥
𝑔𝑡
Compute 𝑣 = 𝑓 𝑥 , 𝑡
𝑝𝑟𝑒𝑑 𝜃 𝑡
2
Compute loss 𝑣 − 𝑣
𝑔𝑡 𝑝𝑟𝑒𝑑
2 |
| Stanford CS231n 10th Anniversary Lecture 14 - 109 May 20, 2025 |


---
## Page 110
---


Generalized Diffusion
Rectified Flow Generalized Diffusion
Sample 𝑥 ∼ 𝑝 , 𝑧 ∼ 𝑝 Sample 𝑥 ∼ 𝑝 , 𝑧 ∼ 𝑝
𝑑𝑎𝑡𝑎 𝑛𝑜𝑖𝑠𝑒 𝑑𝑎𝑡𝑎 𝑛𝑜𝑖𝑠𝑒
Sample 𝑡 ∼ 𝑝 Sample 𝒕 ∼ 𝑝
𝑡 𝑡
Set 𝑥 = 1 − 𝑡 𝑥 + 𝑡𝑧 Set 𝑥 = 𝒂 𝒕 𝑥 + 𝒃(𝒕)𝑧
𝑡 𝑡
Set 𝑣 = 𝑧 − 𝑥 Set 𝑦 = 𝒄(𝒕)𝑥 + 𝒅(𝒕)𝑧
𝑔𝑡 𝑔𝑡
Compute 𝑣 = 𝑓 𝑥 , 𝑡 Compute 𝑦 = 𝑓 𝑥 , 𝒕
𝑝𝑟𝑒𝑑 𝜃 𝑡 𝑝𝑟𝑒𝑑 𝜃 𝑡
2 2
Compute loss 𝑣 − 𝑣 Compute loss 𝑦 − 𝑦
𝑔𝑡 𝑝𝑟𝑒𝑑 𝑔𝑡 𝑝𝑟𝑒𝑑
2 2
Stanford CS231n 10th Anniversary Lecture 14 - 110 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Generalized Diffusion
Rectified Flow Generalized Diffusion
Sample 𝑥 ∼ 𝑝 , 𝑧 ∼ 𝑝 Sample 𝑥 ∼ 𝑝 , 𝑧 ∼ 𝑝
𝑑𝑎𝑡𝑎 𝑛𝑜𝑖𝑠𝑒 𝑑𝑎𝑡𝑎 𝑛𝑜𝑖𝑠𝑒
Sample 𝑡 ∼ 𝑝 Sample 𝒕 ∼ 𝑝
𝑡 𝑡
Set 𝑥 = 1 − 𝑡 𝑥 + 𝑡𝑧 Set 𝑥 = 𝒂 𝒕 𝑥 + 𝒃(𝒕)𝑧
𝑡 𝑡
Set 𝑣 = 𝑧 − 𝑥 Set 𝑦 = 𝒄(𝒕)𝑥 + 𝒅(𝒕)𝑧
𝑔𝑡 𝑔𝑡
Compute 𝑣 = 𝑓 𝑥 , 𝑡 Compute 𝑦 = 𝑓 𝑥 , 𝒕
𝑝𝑟𝑒𝑑 𝜃 𝑡 𝑝𝑟𝑒𝑑 𝜃 𝑡
2 2
Compute loss 𝑣 − 𝑣 Compute loss 𝑦 − 𝑦
𝑔𝑡 𝑝𝑟𝑒𝑑 𝑔𝑡 𝑝𝑟𝑒𝑑
2 2 |
| Stanford CS231n 10th Anniversary Lecture 14 - 110 May 20, 2025 |


---
## Page 111
---


Generalized Diffusion
Rectified Flow Generalized Diffusion
Sample 𝑥 ∼ 𝑝 , 𝑧 ∼ 𝑝 Sample 𝑥 ∼ 𝑝 , 𝑧 ∼ 𝑝
𝑑𝑎𝑡𝑎 𝑛𝑜𝑖𝑠𝑒 𝑑𝑎𝑡𝑎 𝑛𝑜𝑖𝑠𝑒
Sample 𝑡 ∼ 𝑝 Sample 𝒕 ∼ 𝑝
𝑡 𝑡
Set 𝑥 = 1 − 𝑡 𝑥 + 𝑡𝑧 Set 𝑥 = 𝒂 𝒕 𝑥 + 𝒃(𝒕)𝑧
𝑡 𝑡
Set 𝑣 = 𝑧 − 𝑥 Set 𝑦 = 𝒄(𝒕)𝑥 + 𝒅(𝒕)𝑧
𝑔𝑡 𝑔𝑡
Compute 𝑣 = 𝑓 𝑥 , 𝑡 Compute 𝑦 = 𝑓 𝑥 , 𝒕
𝑝𝑟𝑒𝑑 𝜃 𝑡 𝑝𝑟𝑒𝑑 𝜃 𝑡
2 2
Compute loss 𝑣 − 𝑣 Compute loss 𝑦 − 𝑦
𝑔𝑡 𝑝𝑟𝑒𝑑 𝑔𝑡 𝑝𝑟𝑒𝑑
2 2
𝒂 𝒕 = 1 − 𝑡
𝒃(𝒕) = 𝑡
𝒄(𝒕) = −1
𝒅(𝒕) = 1
Stanford CS231n 10th Anniversary Lecture 14 - 111 May 20, 2025

[Page contains 2 table(s)]


### Table 1

| Generalized Diffusion
Rectified Flow Generalized Diffusion
Sample 𝑥 ∼ 𝑝 , 𝑧 ∼ 𝑝 Sample 𝑥 ∼ 𝑝 , 𝑧 ∼ 𝑝
𝑑𝑎𝑡𝑎 𝑛𝑜𝑖𝑠𝑒 𝑑𝑎𝑡𝑎 𝑛𝑜𝑖𝑠𝑒
Sample 𝑡 ∼ 𝑝 Sample 𝒕 ∼ 𝑝
𝑡 𝑡
Set 𝑥 = 1 − 𝑡 𝑥 + 𝑡𝑧 Set 𝑥 = 𝒂 𝒕 𝑥 + 𝒃(𝒕)𝑧
𝑡 𝑡
Set 𝑣 = 𝑧 − 𝑥 Set 𝑦 = 𝒄(𝒕)𝑥 + 𝒅(𝒕)𝑧
𝑔𝑡 𝑔𝑡
Compute 𝑣 = 𝑓 𝑥 , 𝑡 Compute 𝑦 = 𝑓 𝑥 , 𝒕
𝑝𝑟𝑒𝑑 𝜃 𝑡 𝑝𝑟𝑒𝑑 𝜃 𝑡
2 2
Compute loss 𝑣 − 𝑣 Compute loss 𝑦 − 𝑦
𝑔𝑡 𝑝𝑟𝑒𝑑 𝑔𝑡 𝑝𝑟𝑒𝑑
2 2
𝒂 𝒕 = 1 − 𝑡
𝒃(𝒕) = 𝑡
𝒄(𝒕) = −1
𝒅(𝒕) = 1 |
| Stanford CS231n 10th Anniversary Lecture 14 - 111 May 20, 2025 |


### Table 2

|  |
| 𝒂 𝒕 = 1 − 𝑡
𝒃(𝒕) = 𝑡
𝒄(𝒕) = −1
𝒅(𝒕) = 1 |


---
## Page 112
---


Generalized Diffusion
Variance Preserving (VP) Generalized Diffusion
Sample 𝑥 ∼ 𝑝 , 𝑧 ∼ 𝑝
𝒂 𝒕 = 𝜎 𝑡
𝑑𝑎𝑡𝑎 𝑛𝑜𝑖𝑠𝑒
Sample 𝒕 ∼ 𝑝
𝒃(𝒕) = 1 − 𝜎 𝑡 𝑡
Set 𝑥 = 𝒂 𝒕 𝑥 + 𝒃(𝒕)𝑧
𝑡
Set 𝑦 = 𝒄(𝒕)𝑥 + 𝒅(𝒕)𝑧
If x and z are independent and 𝑔𝑡
Compute 𝑦 = 𝑓 𝑥 , 𝒕
variance=1, then x also has 𝑝𝑟𝑒𝑑 𝜃 𝑡
t
2
variance=1 Compute loss 𝑦 − 𝑦
𝑔𝑡 𝑝𝑟𝑒𝑑
2
Song et al, “Score-Based Generative Modeling through Stochastic Differential Equations”, ICLR 2021
Stanford CS231n 10th Anniversary Lecture 14 - 112 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Generalized Diffusion
Variance Preserving (VP) Generalized Diffusion
Sample 𝑥 ∼ 𝑝 , 𝑧 ∼ 𝑝
𝒂 𝒕 = 𝜎 𝑡
𝑑𝑎𝑡𝑎 𝑛𝑜𝑖𝑠𝑒
Sample 𝒕 ∼ 𝑝
𝒃(𝒕) = 1 − 𝜎 𝑡 𝑡
Set 𝑥 = 𝒂 𝒕 𝑥 + 𝒃(𝒕)𝑧
𝑡
Set 𝑦 = 𝒄(𝒕)𝑥 + 𝒅(𝒕)𝑧
If x and z are independent and 𝑔𝑡
Compute 𝑦 = 𝑓 𝑥 , 𝒕
variance=1, then x also has 𝑝𝑟𝑒𝑑 𝜃 𝑡
t
2
variance=1 Compute loss 𝑦 − 𝑦
𝑔𝑡 𝑝𝑟𝑒𝑑
2
Song et al, “Score-Based Generative Modeling through Stochastic Differential Equations”, ICLR 2021 |
| Stanford CS231n 10th Anniversary Lecture 14 - 112 May 20, 2025 |


---
## Page 113
---


Generalized Diffusion
Variance Exploding (VE) Generalized Diffusion
𝒂 𝒕 = 1 Sample 𝑥 ∼ 𝑝 , 𝑧 ∼ 𝑝
𝑑𝑎𝑡𝑎 𝑛𝑜𝑖𝑠𝑒
𝒃(𝒕) = 𝜎 𝑡 Sample 𝒕 ∼ 𝑝
𝑡
Set 𝑥 = 𝒂 𝒕 𝑥 + 𝒃(𝒕)𝑧
𝑡
𝜎 1 Needs to be big enough Set 𝑦 = 𝒄(𝒕)𝑥 + 𝒅(𝒕)𝑧
𝑔𝑡
to drown out all signal in x Compute 𝑦 = 𝑓 𝑥 , 𝒕
𝑝𝑟𝑒𝑑 𝜃 𝑡
2
Compute loss 𝑦 − 𝑦
𝑔𝑡 𝑝𝑟𝑒𝑑
2
Song et al, “Score-Based Generative Modeling through Stochastic Differential Equations”, ICLR 2021
Karraset al, “Elucidating the Design Space of Diffusion-Based Generative Models”, NeurIPS2022
Stanford CS231n 10th Anniversary Lecture 14 - 113 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Generalized Diffusion
Variance Exploding (VE) Generalized Diffusion
𝒂 𝒕 = 1 Sample 𝑥 ∼ 𝑝 , 𝑧 ∼ 𝑝
𝑑𝑎𝑡𝑎 𝑛𝑜𝑖𝑠𝑒
𝒃(𝒕) = 𝜎 𝑡 Sample 𝒕 ∼ 𝑝
𝑡
Set 𝑥 = 𝒂 𝒕 𝑥 + 𝒃(𝒕)𝑧
𝑡
𝜎 1 Needs to be big enough Set 𝑦 = 𝒄(𝒕)𝑥 + 𝒅(𝒕)𝑧
𝑔𝑡
to drown out all signal in x Compute 𝑦 = 𝑓 𝑥 , 𝒕
𝑝𝑟𝑒𝑑 𝜃 𝑡
2
Compute loss 𝑦 − 𝑦
𝑔𝑡 𝑝𝑟𝑒𝑑
2
Song et al, “Score-Based Generative Modeling through Stochastic Differential Equations”, ICLR 2021
Karraset al, “Elucidating the Design Space of Diffusion-Based Generative Models”, NeurIPS2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 113 May 20, 2025 |


---
## Page 114
---


Generalized Diffusion
x-prediction Generalized Diffusion
𝑦 = 𝑥 [𝒄 𝒕 = 1; 𝒅(𝒕) = 0] Sample 𝑥 ∼ 𝑝 , 𝑧 ∼ 𝑝
𝑔𝑡 𝑑𝑎𝑡𝑎 𝑛𝑜𝑖𝑠𝑒
Sample 𝒕 ∼ 𝑝
𝑡
Set 𝑥 = 𝒂 𝒕 𝑥 + 𝒃(𝒕)𝑧
𝑡
ε-prediction
Set 𝑦 = 𝒄(𝒕)𝑥 + 𝒅(𝒕)𝑧
𝑔𝑡
𝑦 = 𝒛 [𝒄 𝒕 = 0; 𝒅(𝒕) = 1] Compute 𝑦 = 𝑓 𝑥 , 𝒕
𝑔𝑡 𝑝𝑟𝑒𝑑 𝜃 𝑡
2
Compute loss 𝑦 − 𝑦
𝑔𝑡 𝑝𝑟𝑒𝑑
2
v-prediction
𝑦 = 𝒃 𝒕 𝑧 − 𝒂 𝒕 𝑥 [𝒄 𝒕 = 𝒃 𝒕 ; 𝒅(𝒕) = − 𝒂 𝒕 ]
𝑔𝑡
Salimansand Ho, “Progressive Distillation of Diffusion Models”, ICLR 2022
Ho et al, “Imagen Video: High Definition Video Generation with Diffusion Models”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 14 - 114 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Generalized Diffusion
x-prediction Generalized Diffusion
𝑦 = 𝑥 [𝒄 𝒕 = 1; 𝒅(𝒕) = 0] Sample 𝑥 ∼ 𝑝 , 𝑧 ∼ 𝑝
𝑔𝑡 𝑑𝑎𝑡𝑎 𝑛𝑜𝑖𝑠𝑒
Sample 𝒕 ∼ 𝑝
𝑡
Set 𝑥 = 𝒂 𝒕 𝑥 + 𝒃(𝒕)𝑧
𝑡
ε-prediction
Set 𝑦 = 𝒄(𝒕)𝑥 + 𝒅(𝒕)𝑧
𝑔𝑡
𝑦 = 𝒛 [𝒄 𝒕 = 0; 𝒅(𝒕) = 1] Compute 𝑦 = 𝑓 𝑥 , 𝒕
𝑔𝑡 𝑝𝑟𝑒𝑑 𝜃 𝑡
2
Compute loss 𝑦 − 𝑦
𝑔𝑡 𝑝𝑟𝑒𝑑
2
v-prediction
𝑦 = 𝒃 𝒕 𝑧 − 𝒂 𝒕 𝑥 [𝒄 𝒕 = 𝒃 𝒕 ; 𝒅(𝒕) = − 𝒂 𝒕 ]
𝑔𝑡
Salimansand Ho, “Progressive Distillation of Diffusion Models”, ICLR 2022
Ho et al, “Imagen Video: High Definition Video Generation with Diffusion Models”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 114 May 20, 2025 |


---
## Page 115
---


Generalized Diffusion
Generalized Diffusion
Sample 𝑥 ∼ 𝑝 , 𝑧 ∼ 𝑝
𝑑𝑎𝑡𝑎 𝑛𝑜𝑖𝑠𝑒
How do we choose these
Sample 𝒕 ∼ 𝑝
𝑡
functions?
Set 𝑥 = 𝒂 𝒕 𝑥 + 𝒃(𝒕)𝑧
𝑡
Set 𝑦 = 𝒄(𝒕)𝑥 + 𝒅(𝒕)𝑧
𝑔𝑡
Usually through some
Compute 𝑦 = 𝑓 𝑥 , 𝒕
𝑝𝑟𝑒𝑑 𝜃 𝑡
mathematical formalism
2
Compute loss 𝑦 − 𝑦
𝑔𝑡 𝑝𝑟𝑒𝑑
2
Salimansand Ho, “Progressive Distillation of Diffusion Models”, ICLR 2022
Ho et al, “Imagen Video: High Definition Video Generation with Diffusion Models”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 14 - 115 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Generalized Diffusion
Generalized Diffusion
Sample 𝑥 ∼ 𝑝 , 𝑧 ∼ 𝑝
𝑑𝑎𝑡𝑎 𝑛𝑜𝑖𝑠𝑒
How do we choose these
Sample 𝒕 ∼ 𝑝
𝑡
functions?
Set 𝑥 = 𝒂 𝒕 𝑥 + 𝒃(𝒕)𝑧
𝑡
Set 𝑦 = 𝒄(𝒕)𝑥 + 𝒅(𝒕)𝑧
𝑔𝑡
Usually through some
Compute 𝑦 = 𝑓 𝑥 , 𝒕
𝑝𝑟𝑒𝑑 𝜃 𝑡
mathematical formalism
2
Compute loss 𝑦 − 𝑦
𝑔𝑡 𝑝𝑟𝑒𝑑
2
Salimansand Ho, “Progressive Distillation of Diffusion Models”, ICLR 2022
Ho et al, “Imagen Video: High Definition Video Generation with Diffusion Models”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 115 May 20, 2025 |


---
## Page 116
---


Diffusion is a Latent Variable Model
We know the forward process: Add Gaussian noise
Learn a network to approximate the backward process
Optimize variational lower bound (same as VAE)
Sohl-Dickstein et al, “Deep Unsupervised Learning using Nonequilibrium Thermodynamics”, NeurIPS2015
Figure from Ho et al, “Denoising Diffusion Probabilistic Models”, NeurIPS2020
Stanford CS231n 10th Anniversary Lecture 14 - 116 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Diffusion is a Latent Variable Model
We know the forward process: Add Gaussian noise
Learn a network to approximate the backward process
Optimize variational lower bound (same as VAE)
Sohl-Dickstein et al, “Deep Unsupervised Learning using Nonequilibrium Thermodynamics”, NeurIPS2015
Figure from Ho et al, “Denoising Diffusion Probabilistic Models”, NeurIPS2020 |
| Stanford CS231n 10th Anniversary Lecture 14 - 116 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 117
---


Diffusion Learns the Score Function
For any distribution 𝑝 𝑥 over 𝑥 ∈ ℝ𝑁 the score function
𝜕
𝑠: ℝ𝑁 → ℝ𝑁 𝑠 𝑥 = log 𝑝(𝑥)
𝜕𝑥
Is a vector field pointing toward areas of high probability density
Diffusion learns a neural network to approximate the score
function of p
data
Song and Ermon, “Generative Modeling by Estimating Gradients of the Data Distribution”, NeurIPS2019
Ho et al, “Denoising Diffusion Probabilistic Models”, NeurIPS2020
Stanford CS231n 10th Anniversary Lecture 14 - 117 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Diffusion Learns the Score Function
For any distribution 𝑝 𝑥 over 𝑥 ∈ ℝ𝑁 the score function
𝜕
𝑠: ℝ𝑁 → ℝ𝑁 𝑠 𝑥 = log 𝑝(𝑥)
𝜕𝑥
Is a vector field pointing toward areas of high probability density
Diffusion learns a neural network to approximate the score
function of p
data
Song and Ermon, “Generative Modeling by Estimating Gradients of the Data Distribution”, NeurIPS2019
Ho et al, “Denoising Diffusion Probabilistic Models”, NeurIPS2020 |
| Stanford CS231n 10th Anniversary Lecture 14 - 117 May 20, 2025 |


---
## Page 118
---


Diffusion Solves Stochastic Differential Equations
We can describe a continuous noising process
as an SDE
𝑑𝒙 = 𝑓 𝒙, 𝑡 𝑑𝑡 + 𝑔 𝑡 𝑑𝒘
Gives a relationship between infinitesimal
changes in data x, time t, and noise w.
Diffusion learns a neural network to
approximately solve this SDE
Song et al, “Score-Based Generative Modeling through Stochastic Differential Equations”, ICLR 2021
Stanford CS231n 10th Anniversary Lecture 14 - 118 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Diffusion Solves Stochastic Differential Equations
We can describe a continuous noising process
as an SDE
𝑑𝒙 = 𝑓 𝒙, 𝑡 𝑑𝑡 + 𝑔 𝑡 𝑑𝒘
Gives a relationship between infinitesimal
changes in data x, time t, and noise w.
Diffusion learns a neural network to
approximately solve this SDE
Song et al, “Score-Based Generative Modeling through Stochastic Differential Equations”, ICLR 2021 |
| Stanford CS231n 10th Anniversary Lecture 14 - 118 May 20, 2025 |


---
## Page 119
---


Perspectives on Diffusion
Great blog post by Sander Dieleman:
https://sander.ai/2023/07/20/perspectives.html
(All his blog posts are great)
Stanford CS231n 10th Anniversary Lecture 14 - 119 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Perspectives on Diffusion
Great blog post by Sander Dieleman:
https://sander.ai/2023/07/20/perspectives.html
(All his blog posts are great) |
| Stanford CS231n 10th Anniversary Lecture 14 - 119 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 120
---


Autoregressive Models Strike Back
Recall autoregressive models
Too slow on raw pixels
They work great on
(discrete) latents!
Stanford CS231n 10th Anniversary Lecture 14 - 120 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Autoregressive Models Strike Back
Recall autoregressive models
Too slow on raw pixels
They work great on
(discrete) latents! |
| Stanford CS231n 10th Anniversary Lecture 14 - 120 May 20, 2025 |


[Page contains 1 image(s)]


---
## Page 121
---


Autoregressive Models Strike Back
Train encoder + decoder Train autoregressive model
to convert images to to model sequences of
discrete latents discrete latents
Image
H x W x 3
Sample discrete latents from
Decoder the autoregressive model,
pass to decoder to get an
Latent
image
H/D x W/D
integers!
Encoder
Image
van den Oord et al, “Neural Discrete Representation Learning”, NeurIPS2017
H x W x 3 Razaviet al, “Generating Diverse High-Fidelity Images with VQ-VAE-2”, NeurIPS2019
Esseret al, “Taming Transformers for High-Resolution Image Synthesis”, CVPR 2021
Yu et al, “Scaling Autoregressive Models for Content-Rich Text-to-Image Generation”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 14 - 121 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Autoregressive Models Strike Back
Train encoder + decoder Train autoregressive model
to convert images to to model sequences of
discrete latents discrete latents
Image
H x W x 3
Sample discrete latents from
Decoder the autoregressive model,
pass to decoder to get an
Latent
image
H/D x W/D
integers!
Encoder
Image
van den Oord et al, “Neural Discrete Representation Learning”, NeurIPS2017
H x W x 3 Razaviet al, “Generating Diverse High-Fidelity Images with VQ-VAE-2”, NeurIPS2019
Esseret al, “Taming Transformers for High-Resolution Image Synthesis”, CVPR 2021
Yu et al, “Scaling Autoregressive Models for Content-Rich Text-to-Image Generation”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 14 - 121 May 20, 2025 |


[Page contains 3 image(s)]


---
## Page 122
---


Summary
Generative Adversarial Networks
Latent Diffusion Models
Diffusion Models
Stanford CS231n 10th Anniversary Lecture 14 - 122 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Summary
Generative Adversarial Networks
Latent Diffusion Models
Diffusion Models |
| Stanford CS231n 10th Anniversary Lecture 14 - 122 May 20, 2025 |


[Page contains 5 image(s)]


---
## Page 123
---


Next Time:
Vision + Language
Stanford CS231n 10th Anniversary Lecture 14 - 123 May 20, 2025

[Page contains 1 table(s)]


### Table 1

| Next Time:
Vision + Language |
| Stanford CS231n 10th Anniversary Lecture 14 - 123 May 20, 2025 |
