# lecture_11

Extracted using pdfplumber



---
## Page 1
---


Lecture 11:
Large-Scale Distributed Training
Stanford CS231n 10th Anniversary Lecture 11 - 1 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Lecture 11:
Large-Scale Distributed Training |
| Stanford CS231n 10th Anniversary Lecture 11 - 1 May 6, 2025 |


---
## Page 2
---


Administrative
Reminders:
● Friday 5/9: Midterm Review Session
● Tuesday 5/13: In-Class Midterm
Stanford CS231n 10th Anniversary Lecture 11 - 2 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Administrative
Reminders:
● Friday 5/9: Midterm Review Session
● Tuesday 5/13: In-Class Midterm |
| Stanford CS231n 10th Anniversary Lecture 11 - 2 May 6, 2025 |


---
## Page 3
---


Today:
Large-Scale Distributed Training
Stanford CS231n 10th Anniversary Lecture 11 - 3 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Today:
Large-Scale Distributed Training |
| Stanford CS231n 10th Anniversary Lecture 11 - 3 May 6, 2025 |


---
## Page 4
---


Running Example: Llama3-405B
● GPT4 kicked off a trend of not sharing any model details:
“Given both the competitive landscape and the safety implications of large-scale
models like GPT-4, this report contains no further details about the architecture
(including model size), hardware, training compute, dataset construction, training
method, or similar.”
● Llama3: Open-source LLM released by Meta in April 2024;
paper shares many model and training details
● Llama4: Released initial models April 2025, but no paper yet
Llama Team, “The Llama 3 Herd of Models”, https://arxiv.org/abs/2407.21783
OpenAI, ”GPT4 Technical Report”, arXiv2023
Stanford CS231n 10th Anniversary Lecture 11 - 4 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Running Example: Llama3-405B
● GPT4 kicked off a trend of not sharing any model details:
“Given both the competitive landscape and the safety implications of large-scale
models like GPT-4, this report contains no further details about the architecture
(including model size), hardware, training compute, dataset construction, training
method, or similar.”
● Llama3: Open-source LLM released by Meta in April 2024;
paper shares many model and training details
● Llama4: Released initial models April 2025, but no paper yet
Llama Team, “The Llama 3 Herd of Models”, https://arxiv.org/abs/2407.21783
OpenAI, ”GPT4 Technical Report”, arXiv2023 |
| Stanford CS231n 10th Anniversary Lecture 11 - 4 May 6, 2025 |


---
## Page 5
---


GPUs and How to Train On Them
A bit about GPU hardware How to train on lots of GPUs
Stanford CS231n 10th Anniversary Lecture 11 - 5 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| GPUs and How to Train On Them
A bit about GPU hardware How to train on lots of GPUs |
| Stanford CS231n 10th Anniversary Lecture 11 - 5 May 6, 2025 |


[Page contains 2 image(s)]


---
## Page 6
---


GPUs and How to Train On Them
A bit about GPU hardware How to train on lots of GPUs
Stanford CS231n 10th Anniversary Lecture 11 - 6 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| GPUs and How to Train On Them
A bit about GPU hardware How to train on lots of GPUs |
| Stanford CS231n 10th Anniversary Lecture 11 - 6 May 6, 2025 |


[Page contains 2 image(s)]


---
## Page 7
---


Inside a GPU: NVIDIA H100
GPU = Graphics Processing Unit
Originally for graphics
Now a general parallel processor
Stanford CS231n 10th Anniversary Lecture 11 - 7 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Inside a GPU: NVIDIA H100
GPU = Graphics Processing Unit
Originally for graphics
Now a general parallel processor |
| Stanford CS231n 10th Anniversary Lecture 11 - 7 May 6, 2025 |


[Page contains 1 image(s)]


---
## Page 8
---


Inside a GPU: NVIDIA H100
GPU = Graphics Processing Unit
Originally for graphics
Now a general parallel processor
Compute Cores
Stanford CS231n 10th Anniversary Lecture 11 - 8 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Inside a GPU: NVIDIA H100
GPU = Graphics Processing Unit
Originally for graphics
Now a general parallel processor
Compute Cores |
| Stanford CS231n 10th Anniversary Lecture 11 - 8 May 6, 2025 |


[Page contains 1 image(s)]


---
## Page 9
---


Inside a GPU: NVIDIA H100
GPU = Graphics Processing Unit
Originally for graphics
Now a general parallel processor
Compute Cores
80 GB of HBM Memory
3352 GB/sec bandwidth to cores
Stanford CS231n 10th Anniversary Lecture 11 - 9 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Inside a GPU: NVIDIA H100
GPU = Graphics Processing Unit
Originally for graphics
Now a general parallel processor
Compute Cores
80 GB of HBM Memory
3352 GB/sec bandwidth to cores |
| Stanford CS231n 10th Anniversary Lecture 11 - 9 May 6, 2025 |


### Table 2

|  |
|  |
|  |


[Page contains 1 image(s)]


---
## Page 10
---


Inside a GPU: NVIDIA H100
H100 Compute Cores
Stanford CS231n 10th Anniversary Lecture 11 - 10 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Inside a GPU: NVIDIA H100
H100 Compute Cores |
| Stanford CS231n 10th Anniversary Lecture 11 - 10 May 6, 2025 |


[Page contains 2 image(s)]


---
## Page 11
---


Inside a GPU: NVIDIA H100
H100 Compute Cores
50MB of L2 Cache
Stanford CS231n 10th Anniversary Lecture 11 - 11 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Inside a GPU: NVIDIA H100
H100 Compute Cores
50MB of L2 Cache |
| Stanford CS231n 10th Anniversary Lecture 11 - 11 May 6, 2025 |


[Page contains 2 image(s)]


---
## Page 12
---


Inside a GPU: NVIDIA H100
H100 Compute Cores
50MB of L2 Cache
132 Streaming Multiprocessors (SMs)
These are independent parallel cores
(Actually 144 here; only 132 are enabled due to yield)
Stanford CS231n 10th Anniversary Lecture 11 - 12 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Inside a GPU: NVIDIA H100
H100 Compute Cores
50MB of L2 Cache
132 Streaming Multiprocessors (SMs)
These are independent parallel cores
(Actually 144 here; only 132 are enabled due to yield) |
| Stanford CS231n 10th Anniversary Lecture 11 - 12 May 6, 2025 |


[Page contains 2 image(s)]


---
## Page 13
---


H100 Streaming Multiprocessor
Inside a GPU: NVIDIA H100
Sort of like
a CPU core
with vector
instructions
Stanford CS231n 10th Anniversary Lecture 11 - 13 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| H100 Streaming Multiprocessor
Inside a GPU: NVIDIA H100
Sort of like
a CPU core
with vector
instructions |
| Stanford CS231n 10th Anniversary Lecture 11 - 13 May 6, 2025 |


### Table 2

|  |  |


[Page contains 3 image(s)]


---
## Page 14
---


H100 Streaming Multiprocessor
Inside a GPU: NVIDIA H100
256 KB L1 cache, 256 KB registers
Sort of like
a CPU core
with vector
instructions
Stanford CS231n 10th Anniversary Lecture 11 - 14 May 6, 2025

[Page contains 3 table(s)]


### Table 1

| H100 Streaming Multiprocessor
Inside a GPU: NVIDIA H100
256 KB L1 cache, 256 KB registers
Sort of like
a CPU core
with vector
instructions |
| Stanford CS231n 10th Anniversary Lecture 11 - 14 May 6, 2025 |


### Table 2

|  |
|  |
|  |


### Table 3

|  |  |


[Page contains 3 image(s)]


---
## Page 15
---


H100 Streaming Multiprocessor
Inside a GPU: NVIDIA H100
256 KB L1 cache, 256 KB registers
128 FP32 Cores
Computes a*x + b per clock cycle
2 FLOPs = Floating Point Operations
256 FLOP/cycle per SM
Sort of like
a CPU core
with vector
instructions
Stanford CS231n 10th Anniversary Lecture 11 - 15 May 6, 2025

[Page contains 3 table(s)]


### Table 1

| H100 Streaming Multiprocessor
Inside a GPU: NVIDIA H100
256 KB L1 cache, 256 KB registers
128 FP32 Cores
Computes a*x + b per clock cycle
2 FLOPs = Floating Point Operations
256 FLOP/cycle per SM
Sort of like
a CPU core
with vector
instructions |
| Stanford CS231n 10th Anniversary Lecture 11 - 15 May 6, 2025 |


### Table 2

|  |
|  |
|  |


### Table 3

|  |  |


[Page contains 3 image(s)]


---
## Page 16
---


H100 Streaming Multiprocessor
Inside a GPU: NVIDIA H100
256 KB L1 cache, 256 KB registers
128 FP32 Cores
Computes a*x + b per clock cycle
2 FLOPs = Floating Point Operations
256 FLOP/cycle per SM
4 Tensor Cores
Computes AX + B per clock cycle
Sort of like
Matrix operation: [16x4][4x8] + [16x8]
a CPU core
16*4*8*2 = 1024 FLOPs
with vector
4096 FLOP/cycle per SM
instructions
Mixed precision: 16-bit / 32-bit
Stanford CS231n 10th Anniversary Lecture 11 - 16 May 6, 2025

[Page contains 7 table(s)]


### Table 1

| H100 Streaming Multiprocessor
Inside a GPU: NVIDIA H100
256 KB L1 cache, 256 KB registers
128 FP32 Cores
Computes a*x + b per clock cycle
2 FLOPs = Floating Point Operations
256 FLOP/cycle per SM
4 Tensor Cores
Computes AX + B per clock cycle
Sort of like
Matrix operation: [16x4][4x8] + [16x8]
a CPU core
16*4*8*2 = 1024 FLOPs
with vector
4096 FLOP/cycle per SM
instructions
Mixed precision: 16-bit / 32-bit |
| Stanford CS231n 10th Anniversary Lecture 11 - 16 May 6, 2025 |


### Table 2

|  |
|  |
|  |


### Table 3

|  |  |
|  |  |


### Table 4

|  |  |
|  |  |


### Table 5

|  |  |  |
|  |  |  |


### Table 6

|  |  |
|  |  |


### Table 7

|  |  |
|  |  |


[Page contains 3 image(s)]


---
## Page 17
---


GPUs Have Gotten Much Faster!
FP32 Tensor Core
6000 B200
5000 TC
83.3 FP32
5000
4000
c
e
s
/P3000
O
L H100
F
T
989 TC
2000 67 FP32
A100
V100 312 TC
1000
125 TC 19.5 FP32
K40 P100
15.7 FP32
5 FP32 10.6 FP32
0
Apr-12 Aug-13 Dec-14 May-16 Sep-17 Feb-19 Jun-20 Oct-21 Mar-23 Jul-24 Dec-25
Stanford CS231n 10th Anniversary Lecture 11 - 17 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| GPUs Have Gotten Much Faster! |
| FP32 Tensor Core
6000 B200
5000 TC
83.3 FP32
5000
4000
c
e
s
/P3000
O
L H100
F
T
989 TC
2000 67 FP32
A100
V100 312 TC
1000
125 TC 19.5 FP32
K40 P100
15.7 FP32
5 FP32 10.6 FP32
0
Apr-12 Aug-13 Dec-14 May-16 Sep-17 Feb-19 Jun-20 Oct-21 Mar-23 Jul-24 Dec-25 |
| Stanford CS231n 10th Anniversary Lecture 11 - 17 May 6, 2025 |


### Table 2

|  |  |  |  |  |  |  |  |  | 5
83 | B200
000 TC
.3 FP32 |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  | H1
989 | 00
TC |  |  |
|  |  |  | V100 |  | A10
312 | 6
0
TC | 7 F | P32 |  |  |
| 5 | K40
FP32 | P1
10.6 F | 125 TC
00
15.7 FP
P32 | 32 | 19.5 F | P32 |  |  |  |  |


---
## Page 18
---


GPUs Have Gotten Much Faster!
FP32 Tensor Core
6000 B200
1000x speedup
5000 TC
since 2013! 83.3 FP32
5000
4000
c
e
s
/P3000
O
L H100
F
T
989 TC
2000 67 FP32
A100
V100 312 TC
1000
125 TC 19.5 FP32
K40 P100
15.7 FP32
5 FP32 10.6 FP32
0
Apr-12 Aug-13 Dec-14 May-16 Sep-17 Feb-19 Jun-20 Oct-21 Mar-23 Jul-24 Dec-25
Stanford CS231n 10th Anniversary Lecture 11 - 18 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| GPUs Have Gotten Much Faster! |
| FP32 Tensor Core
6000 B200
1000x speedup
5000 TC
since 2013! 83.3 FP32
5000
4000
c
e
s
/P3000
O
L H100
F
T
989 TC
2000 67 FP32
A100
V100 312 TC
1000
125 TC 19.5 FP32
K40 P100
15.7 FP32
5 FP32 10.6 FP32
0
Apr-12 Aug-13 Dec-14 May-16 Sep-17 Feb-19 Jun-20 Oct-21 Mar-23 Jul-24 Dec-25 |
| Stanford CS231n 10th Anniversary Lecture 11 - 18 May 6, 2025 |


### Table 2

|  |  |  |  |  | 1000x s
since | peedup
2013! |  |  |  | 5
83 | B200
000 TC
.3 FP32 |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  | H1
989 | 00
TC |  |  |
|  |  |  |  | V100 |  | A1
312 | 6
00
TC | 7 F | P32 |  |  |
| 5 | K40
FP32 |  | P1
10.6 F | 125 TC
00
15.7 FP
P32 | 32 | 19.5 F | P32 |  |  |  |  |


---
## Page 19
---


GPUs Have Gotten Much Faster!
FP32 Tensor Core
6000 B200
1000x speedup
5000 TC
since 2013! 83.3 FP32
5000
4000
We can also train
c
e
s with > 1 GPU!
/P3000
O
L H100
F
T
989 TC
2000 67 FP32
A100
V100 312 TC
1000
125 TC 19.5 FP32
K40 P100
15.7 FP32
5 FP32 10.6 FP32
0
Apr-12 Aug-13 Dec-14 May-16 Sep-17 Feb-19 Jun-20 Oct-21 Mar-23 Jul-24 Dec-25
Stanford CS231n 10th Anniversary Lecture 11 - 19 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| GPUs Have Gotten Much Faster! |
| FP32 Tensor Core
6000 B200
1000x speedup
5000 TC
since 2013! 83.3 FP32
5000
4000
We can also train
c
e
s with > 1 GPU!
/P3000
O
L H100
F
T
989 TC
2000 67 FP32
A100
V100 312 TC
1000
125 TC 19.5 FP32
K40 P100
15.7 FP32
5 FP32 10.6 FP32
0
Apr-12 Aug-13 Dec-14 May-16 Sep-17 Feb-19 Jun-20 Oct-21 Mar-23 Jul-24 Dec-25 |
| Stanford CS231n 10th Anniversary Lecture 11 - 19 May 6, 2025 |


### Table 2

|  |  |  |  |  | 1000x s
since | peedup
2013! |  |  |  | 5
83 | B200
000 TC
.3 FP32 |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  | We can
with > | also train
1 GPU! |  |  |  |  |  |
|  |  |  |  |  |  |  |  | H1
989 | 00
TC |  |  |
|  |  |  |  | V100 |  | A1
312 | 6
00
TC | 7 F | P32 |  |  |
| 5 | K40
FP32 |  | P1
10.6 F | 125 TC
00
15.7 FP
P32 | 32 | 19.5 F | P32 |  |  |  |  |


---
## Page 20
---


NVIDIA H100 GPU
H100 GPU
3352 GB/sec inside the GPU
Stanford CS231n 10th Anniversary Lecture 11 - 20 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| NVIDIA H100 GPU
H100 GPU
3352 GB/sec inside the GPU |
| Stanford CS231n 10th Anniversary Lecture 11 - 20 May 6, 2025 |


[Page contains 1 image(s)]


---
## Page 21
---


NVIDIA H100 GPU
GPU Server
H100 GPU
3352 GB/sec inside the GPU
Server = 8x GPU
900 GB/sec between GPUs
Stanford CS231n 10th Anniversary Lecture 11 - 21 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| NVIDIA H100 GPU
GPU Server
H100 GPU
3352 GB/sec inside the GPU
Server = 8x GPU
900 GB/sec between GPUs |
| Stanford CS231n 10th Anniversary Lecture 11 - 21 May 6, 2025 |


[Page contains 9 image(s)]


---
## Page 22
---


Case Study: Meta’s Llama3 Cluster
H100 GPU
Server Rack
3352 GB/sec inside the GPU
Server = 8x GPU
900 GB/sec between GPUs
Rack = 2 Servers = 16x GPU
Llama Team, “The Llama 3 Herd of Models”, https://arxiv.org/abs/2407.21783
Stanford CS231n 10th Anniversary Lecture 11 - 22 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Case Study: Meta’s Llama3 Cluster
H100 GPU
Server Rack
3352 GB/sec inside the GPU
Server = 8x GPU
900 GB/sec between GPUs
Rack = 2 Servers = 16x GPU
Llama Team, “The Llama 3 Herd of Models”, https://arxiv.org/abs/2407.21783 |
| Stanford CS231n 10th Anniversary Lecture 11 - 22 May 6, 2025 |


[Page contains 3 image(s)]


---
## Page 23
---


Case Study: Meta’s Llama3 Cluster
H100 GPU
3352 GB/sec inside the GPU
Server = 8x GPU
900 GB/sec between GPUs
Rack = 2 Servers = 16x GPU
Pod = 192 Racks = 3072 GPUs
50 GB/sec between GPUs
Llama Team, “The Llama 3 Herd of Models”, https://arxiv.org/abs/2407.21783
Stanford CS231n 10th Anniversary Lecture 11 - 23 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Case Study: Meta’s Llama3 Cluster
H100 GPU
3352 GB/sec inside the GPU
Server = 8x GPU
900 GB/sec between GPUs
Rack = 2 Servers = 16x GPU
Pod = 192 Racks = 3072 GPUs
50 GB/sec between GPUs
Llama Team, “The Llama 3 Herd of Models”, https://arxiv.org/abs/2407.21783 |
| Stanford CS231n 10th Anniversary Lecture 11 - 23 May 6, 2025 |


[Page contains 2 image(s)]


---
## Page 24
---


Case Study: Meta’s Llama3 Cluster
H100 GPU
3352 GB/sec inside the GPU GPU Cluster
Server = 8x GPU
900 GB/sec between GPUs
Rack = 2 Servers = 16x GPU
Pod = 192 Racks = 3072 GPUs
50 GB/sec between GPUs
Cluster = 8 Pods = 24,576 GPUs
< 50GB/sec between GPUs
Llama Team, “The Llama 3 Herd of Models”, https://arxiv.org/abs/2407.21783
Stanford CS231n 10th Anniversary Lecture 11 - 24 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Case Study: Meta’s Llama3 Cluster
H100 GPU
3352 GB/sec inside the GPU GPU Cluster
Server = 8x GPU
900 GB/sec between GPUs
Rack = 2 Servers = 16x GPU
Pod = 192 Racks = 3072 GPUs
50 GB/sec between GPUs
Cluster = 8 Pods = 24,576 GPUs
< 50GB/sec between GPUs
Llama Team, “The Llama 3 Herd of Models”, https://arxiv.org/abs/2407.21783 |
| Stanford CS231n 10th Anniversary Lecture 11 - 24 May 6, 2025 |


[Page contains 8 image(s)]


---
## Page 25
---


GPU Cluster = One Big Computer
Total Cluster Stats
24,576 GPUs GPU Cluster
1.875 PB of GPU memory
415M FP32 cores
13M Tensor Cores
24.3 EFLOP/sec = 24.3 x 1018
Goal: Train one giant neural
network on this cluster
Stanford CS231n 10th Anniversary Lecture 11 - 25 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| GPU Cluster = One Big Computer
Total Cluster Stats
24,576 GPUs GPU Cluster
1.875 PB of GPU memory
415M FP32 cores
13M Tensor Cores
24.3 EFLOP/sec = 24.3 x 1018
Goal: Train one giant neural
network on this cluster |
| Stanford CS231n 10th Anniversary Lecture 11 - 25 May 6, 2025 |


[Page contains 8 image(s)]


---
## Page 26
---


Google: Tensor Processing Units (TPUs)
Custom chips designed by Google
TPU v5p:
459 TFLOP/sec BF16 per chip
95GB of memory per chip
Arranged in pods of 8960 chips
Stanford CS231n 10th Anniversary Lecture 11 - 26 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Google: Tensor Processing Units (TPUs)
Custom chips designed by Google
TPU v5p:
459 TFLOP/sec BF16 per chip
95GB of memory per chip
Arranged in pods of 8960 chips |
| Stanford CS231n 10th Anniversary Lecture 11 - 26 May 6, 2025 |


[Page contains 1 image(s)]


---
## Page 27
---


Other Training Chips
AMD MI325X AWS Trainium2
1300 TFLOP/sec BF16 667 TFLOP/sec BF16
256GB memory 96GB memory
Packed in UltraServers with 64 chips
Stanford CS231n 10th Anniversary Lecture 11 - 27 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Other Training Chips
AMD MI325X AWS Trainium2
1300 TFLOP/sec BF16 667 TFLOP/sec BF16
256GB memory 96GB memory
Packed in UltraServers with 64 chips |
| Stanford CS231n 10th Anniversary Lecture 11 - 27 May 6, 2025 |


[Page contains 2 image(s)]


---
## Page 28
---


Today: GPUs and How to Train On Them
A bit about GPU hardware How to train on lots of GPUs
Stanford CS231n 10th Anniversary Lecture 11 - 28 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Today: GPUs and How to Train On Them
A bit about GPU hardware How to train on lots of GPUs |
| Stanford CS231n 10th Anniversary Lecture 11 - 28 May 6, 2025 |


[Page contains 2 image(s)]


---
## Page 29
---


Today: GPUs and How to Train On Them
A bit about GPU hardware How to train on lots of GPUs
Stanford CS231n 10th Anniversary Lecture 11 - 29 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Today: GPUs and How to Train On Them
A bit about GPU hardware How to train on lots of GPUs |
| Stanford CS231n 10th Anniversary Lecture 11 - 29 May 6, 2025 |


[Page contains 2 image(s)]


---
## Page 30
---


How to train on lots of GPUs
A model with L layers operates on tensors of shape (Batch, Sequence, Dim)
Data Parallelism (DP) Context Parallelism (CP)
Split on Batch dimension Split on Sequence dimension
Pipeline Parallelism (PP) Tensor Parallelism (TP)
Split on L dimension Split on Dim dimension
Stanford CS231n 10th Anniversary Lecture 11 - 30 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| How to train on lots of GPUs
A model with L layers operates on tensors of shape (Batch, Sequence, Dim)
Data Parallelism (DP) Context Parallelism (CP)
Split on Batch dimension Split on Sequence dimension
Pipeline Parallelism (PP) Tensor Parallelism (TP)
Split on L dimension Split on Dim dimension |
| Stanford CS231n 10th Anniversary Lecture 11 - 30 May 6, 2025 |


---
## Page 31
---


How to train on lots of GPUs
A model with L layers operates on tensors of shape (Batch, Sequence, Dim)
Data Parallelism (DP) Context Parallelism (CP)
Split on Batch dimension Split on Sequence dimension
Pipeline Parallelism (PP) Tensor Parallelism (TP)
Split on L dimension Split on Dim dimension
Stanford CS231n 10th Anniversary Lecture 11 - 31 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| How to train on lots of GPUs
A model with L layers operates on tensors of shape (Batch, Sequence, Dim)
Data Parallelism (DP) Context Parallelism (CP)
Split on Batch dimension Split on Sequence dimension
Pipeline Parallelism (PP) Tensor Parallelism (TP)
Split on L dimension Split on Dim dimension |
| Stanford CS231n 10th Anniversary Lecture 11 - 31 May 6, 2025 |


---
## Page 32
---


Data Parallelism
Recall: Loss is usually averaged
over a minibatch of N samples
Stanford CS231n 10th Anniversary Lecture 11 - 32 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Data Parallelism
Recall: Loss is usually averaged
over a minibatch of N samples |
| Stanford CS231n 10th Anniversary Lecture 11 - 32 May 6, 2025 |


---
## Page 33
---


Data Parallelism
Recall: Loss is usually averaged
over a minibatch of N samples
Idea: Use minibatch of MN samples,
split over M GPUs
Stanford CS231n 10th Anniversary Lecture 11 - 33 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Data Parallelism
Recall: Loss is usually averaged
over a minibatch of N samples
Idea: Use minibatch of MN samples,
split over M GPUs |
| Stanford CS231n 10th Anniversary Lecture 11 - 33 May 6, 2025 |


---
## Page 34
---


Data Parallelism
Recall: Loss is usually averaged
over a minibatch of N samples
Idea: Use minibatch of MN samples,
split over M GPUs
Gradients are linear, so each GPU
computes its own gradient:
𝑀 𝑁
1
𝐿 = ෍෍ℓ 𝑥 ,𝑊
𝑖,𝑗
𝑀𝑁
𝑖=1𝑗=1
𝑀 𝑁
𝜕𝐿 1 1 𝜕
= ෍ ෍ ℓ 𝑥 ,𝑊
𝑖,𝑗
𝜕𝑊 𝑀 𝑁 𝜕𝑊
𝑖=1 𝑗=1
Stanford CS231n 10th Anniversary Lecture 11 - 34 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Data Parallelism
Recall: Loss is usually averaged
over a minibatch of N samples
Idea: Use minibatch of MN samples,
split over M GPUs
Gradients are linear, so each GPU
computes its own gradient:
𝑀 𝑁
1
𝐿 = ෍෍ℓ 𝑥 ,𝑊
𝑖,𝑗
𝑀𝑁
𝑖=1𝑗=1
𝑀 𝑁
𝜕𝐿 1 1 𝜕
= ෍ ෍ ℓ 𝑥 ,𝑊
𝑖,𝑗
𝜕𝑊 𝑀 𝑁 𝜕𝑊
𝑖=1 𝑗=1 |  |  |
|  | Recall: Loss is usually averaged
over a minibatch of N samples
Idea: Use minibatch of MN samples,
split over M GPUs
Gradients are linear, so each GPU
computes its own gradient:
𝑀 𝑁
1
𝐿 = ෍෍ℓ 𝑥 ,𝑊
𝑖,𝑗
𝑀𝑁
𝑖=1𝑗=1
𝑀 𝑁
𝜕𝐿 1 1 𝜕
= ෍ ෍ ℓ 𝑥 ,𝑊
𝑖,𝑗
𝜕𝑊 𝑀 𝑁 𝜕𝑊
𝑖=1 𝑗=1 |  |
| S | tanford CS231n 10th Anniversary | Lecture 11 - 34 May 6, 2025 |
|  |  |  |


---
## Page 35
---


Data Parallelism
Recall: Loss is usually averaged
over a minibatch of N samples
Idea: Use minibatch of MN samples,
split over M GPUs
Gradients are linear, so each GPU
computes its own gradient:
𝑀 𝑁 Each GPU
1
computes gradient
𝐿 = ෍෍ℓ 𝑥 ,𝑊
𝑖,𝑗
𝑀𝑁
on N examples
𝑖=1𝑗=1
𝑀 𝑁
𝜕𝐿 1 1 𝜕
= ෍ ෍ ℓ 𝑥 ,𝑊
𝑖,𝑗
𝜕𝑊 𝑀 𝑁 𝜕𝑊
𝑖=1 𝑗=1
Stanford CS231n 10th Anniversary Lecture 11 - 35 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Data Parallelism
Recall: Loss is usually averaged
over a minibatch of N samples
Idea: Use minibatch of MN samples,
split over M GPUs
Gradients are linear, so each GPU
computes its own gradient:
𝑀 𝑁 Each GPU
1
computes gradient
𝐿 = ෍෍ℓ 𝑥 ,𝑊
𝑖,𝑗
𝑀𝑁
on N examples
𝑖=1𝑗=1
𝑀 𝑁
𝜕𝐿 1 1 𝜕
= ෍ ෍ ℓ 𝑥 ,𝑊
𝑖,𝑗
𝜕𝑊 𝑀 𝑁 𝜕𝑊
𝑖=1 𝑗=1 |  |  |
|  | Recall: Loss is usually averaged
over a minibatch of N samples
Idea: Use minibatch of MN samples,
split over M GPUs
Gradients are linear, so each GPU
computes its own gradient:
𝑀 𝑁 Each GP
1
compute
𝐿 = ෍෍ℓ 𝑥 ,𝑊
𝑖,𝑗
𝑀𝑁
on N exa
𝑖=1𝑗=1
𝑀 𝑁
𝜕𝐿 1 1 𝜕
= ෍ ෍ ℓ 𝑥 ,𝑊
𝑖,𝑗
𝜕𝑊 𝑀 𝑁 𝜕𝑊
𝑖=1 𝑗=1 |  |
| S | tanford CS231n 10th Anniversary | Lecture 11 - 35 May 6, 2025 |
|  |  |  |


---
## Page 36
---


Data Parallelism
Recall: Loss is usually averaged
over a minibatch of N samples
Idea: Use minibatch of MN samples,
split over M GPUs
Gradients are linear, so each GPU
computes its own gradient:
𝑀 𝑁 Each GPU
1
computes gradient
𝐿 = ෍෍ℓ 𝑥 ,𝑊
𝑖,𝑗
𝑀𝑁
on N examples
𝑖=1𝑗=1
𝑀 𝑁
𝜕𝐿 1 1 𝜕
= ෍ ෍ ℓ 𝑥 ,𝑊 Average gradients
𝑖,𝑗
𝜕𝑊 𝑀 𝑁 𝜕𝑊
across M GPUs
𝑖=1 𝑗=1
Stanford CS231n 10th Anniversary Lecture 11 - 36 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Data Parallelism
Recall: Loss is usually averaged
over a minibatch of N samples
Idea: Use minibatch of MN samples,
split over M GPUs
Gradients are linear, so each GPU
computes its own gradient:
𝑀 𝑁 Each GPU
1
computes gradient
𝐿 = ෍෍ℓ 𝑥 ,𝑊
𝑖,𝑗
𝑀𝑁
on N examples
𝑖=1𝑗=1
𝑀 𝑁
𝜕𝐿 1 1 𝜕
= ෍ ෍ ℓ 𝑥 ,𝑊 Average gradients
𝑖,𝑗
𝜕𝑊 𝑀 𝑁 𝜕𝑊
across M GPUs
𝑖=1 𝑗=1 |  |  |
|  | Recall: Loss is usually averaged
over a minibatch of N samples
Idea: Use minibatch of MN samples,
split over M GPUs
Gradients are linear, so each GPU
computes its own gradient:
𝑀 𝑁 Each GP
1
compute
𝐿 = ෍෍ℓ 𝑥 ,𝑊
𝑖,𝑗
𝑀𝑁
on N exa
𝑖=1𝑗=1
𝑀 𝑁
𝜕𝐿 1 1 𝜕
= ෍ ෍ ℓ 𝑥 ,𝑊 Average
𝑖,𝑗
𝜕𝑊 𝑀 𝑁 𝜕𝑊
across M
𝑖=1 𝑗=1 |  |
| S | tanford CS231n 10th Anniversary | Lecture 11 - 36 May 6, 2025 |
|  |  |  |


---
## Page 37
---


Data Parallelism
Recall: Loss is usually averaged
GPU 1
over a minibatch of N samples
Idea: Use minibatch of MN samples,
split over M GPUs
Gradients are linear, so each GPU
computes its own gradient:
GPU 2
1. Each GPU has it’s own copy of model + optimizer
GPU 3
Stanford CS231n 10th Anniversary Lecture 11 - 37 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Data Parallelism
Recall: Loss is usually averaged
GPU 1
over a minibatch of N samples
Idea: Use minibatch of MN samples,
split over M GPUs
Gradients are linear, so each GPU
computes its own gradient:
GPU 2
1. Each GPU has it’s own copy of model + optimizer
GPU 3 |
| Stanford CS231n 10th Anniversary Lecture 11 - 37 May 6, 2025 |


---
## Page 38
---


Data Parallelism
x
1,1
x
1,2
x
Recall: Loss is usually averaged
1,3
GPU 1
over a minibatch of N samples
Idea: Use minibatch of MN samples,
split over M GPUs
x
2,1
x
2,2
Gradients are linear, so each GPU
x
2,3
computes its own gradient:
GPU 2
1. Each GPU has it’s own copy of model + optimizer
2. Each GPU loads its own batch of data
x
3,1
x
3,2
x
3,3
GPU 3
Stanford CS231n 10th Anniversary Lecture 11 - 38 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Data Parallelism
x
1,1
x
1,2
x
Recall: Loss is usually averaged
1,3
GPU 1
over a minibatch of N samples
Idea: Use minibatch of MN samples,
split over M GPUs
x
2,1
x
2,2
Gradients are linear, so each GPU
x
2,3
computes its own gradient:
GPU 2
1. Each GPU has it’s own copy of model + optimizer
2. Each GPU loads its own batch of data
x
3,1
x
3,2
x
3,3
GPU 3 |
| Stanford CS231n 10th Anniversary Lecture 11 - 38 May 6, 2025 |


---
## Page 39
---


Data Parallelism
x
1,1
x L
1,2 1
x
Recall: Loss is usually averaged
1,3
GPU 1
over a minibatch of N samples
Idea: Use minibatch of MN samples,
split over M GPUs
x
2,1
x L
2,2 2
Gradients are linear, so each GPU
x
2,3
computes its own gradient:
GPU 2
1. Each GPU has it’s own copy of model + optimizer
2. Each GPU loads its own batch of data
3. Each GPU runs forward to compute loss x
3,1
x L
3,2 3
x
3,3
GPU 3
Stanford CS231n 10th Anniversary Lecture 11 - 39 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Data Parallelism
x
1,1
x L
1,2 1
x
Recall: Loss is usually averaged
1,3
GPU 1
over a minibatch of N samples
Idea: Use minibatch of MN samples,
split over M GPUs
x
2,1
x L
2,2 2
Gradients are linear, so each GPU
x
2,3
computes its own gradient:
GPU 2
1. Each GPU has it’s own copy of model + optimizer
2. Each GPU loads its own batch of data
3. Each GPU runs forward to compute loss x
3,1
x L
3,2 3
x
3,3
GPU 3 |
| Stanford CS231n 10th Anniversary Lecture 11 - 39 May 6, 2025 |


---
## Page 40
---


Data Parallelism
x
1,1
x L
1,2 1
x
Recall: Loss is usually averaged
1,3
GPU 1 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
over a minibatch of N samples 1 1 1 1
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
Idea: Use minibatch of MN samples,
split over M GPUs
x
2,1
x L
2,2 2
Gradients are linear, so each GPU
x
2,3
computes its own gradient: 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
2 2 2 2
GPU 2
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
1. Each GPU has it’s own copy of model + optimizer
2. Each GPU loads its own batch of data
3. Each GPU runs forward to compute loss x
3,1
4. Each GPU runs backward to compute gradients x L
3,2 3
x
3,3
GPU 3 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
3 3 3 3
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
Stanford CS231n 10th Anniversary Lecture 11 - 40 May 6, 2025

[Page contains 4 table(s)]


### Table 1

| Data Parallelism
x
1,1
x L
1,2 1
x
Recall: Loss is usually averaged
1,3
GPU 1 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
over a minibatch of N samples 1 1 1 1
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
Idea: Use minibatch of MN samples,
split over M GPUs
x
2,1
x L
2,2 2
Gradients are linear, so each GPU
x
2,3
computes its own gradient: 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
2 2 2 2
GPU 2
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
1. Each GPU has it’s own copy of model + optimizer
2. Each GPU loads its own batch of data
3. Each GPU runs forward to compute loss x
3,1
4. Each GPU runs backward to compute gradients x L
3,2 3
x
3,3
GPU 3 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
3 3 3 3
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4 |
| Stanford CS231n 10th Anniversary Lecture 11 - 40 May 6, 2025 |


### Table 2

| 𝜕𝐿
1
𝜕𝑊
1 | 𝜕𝐿
1
𝜕𝑊
2 | 𝜕𝐿
1
𝜕𝑊
3 | 𝜕𝐿
1
𝜕𝑊
4 |


### Table 3

| 𝜕𝐿
2
𝜕𝑊
1 | 𝜕𝐿
2
𝜕𝑊
2 | 𝜕𝐿
2
𝜕𝑊
3 | 𝜕𝐿
2
𝜕𝑊
4 |


### Table 4

| 𝜕𝐿
3
𝜕𝑊
1 | 𝜕𝐿
3
𝜕𝑊
2 | 𝜕𝐿
3
𝜕𝑊
3 | 𝜕𝐿
3
𝜕𝑊
4 |


---
## Page 41
---


𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
Data Parallelism 1 2 3 4
x
1,1
x L
1,2 1
x
Recall: Loss is usually averaged
1,3
GPU 1 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
over a minibatch of N samples 1 1 1 1
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
Idea: Use minibatch of MN samples, 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
split over M GPUs 𝜕𝑊 1 𝜕𝑊 2 𝜕𝑊 3 𝜕𝑊 4
x
2,1
x L
2,2 2
Gradients are linear, so each GPU
x
2,3
computes its own gradient: 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
2 2 2 2
GPU 2
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
1. Each GPU has it’s own copy of model + optimizer
𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
2. Each GPU loads its own batch of data
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
3. Each GPU runs forward to compute loss x
3,1
4. Each GPU runs backward to compute gradients x L
3,2 3
5. Average gradients across all GPUs x
3,3
GPU 3 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
3 3 3 3
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
Stanford CS231n 10th Anniversary Lecture 11 - 41 May 6, 2025

[Page contains 9 table(s)]


### Table 1

| 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
Data Parallelism 1 2 3 4
x
1,1
x L
1,2 1
x
Recall: Loss is usually averaged
1,3
GPU 1 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
over a minibatch of N samples 1 1 1 1
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
Idea: Use minibatch of MN samples, 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
split over M GPUs 𝜕𝑊 1 𝜕𝑊 2 𝜕𝑊 3 𝜕𝑊 4
x
2,1
x L
2,2 2
Gradients are linear, so each GPU
x
2,3
computes its own gradient: 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
2 2 2 2
GPU 2
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
1. Each GPU has it’s own copy of model + optimizer
𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
2. Each GPU loads its own batch of data
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
3. Each GPU runs forward to compute loss x
3,1
4. Each GPU runs backward to compute gradients x L
3,2 3
5. Average gradients across all GPUs x
3,3
GPU 3 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
3 3 3 3
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4 |
| Stanford CS231n 10th Anniversary Lecture 11 - 41 May 6, 2025 |


### Table 2

| 𝜕𝐿
𝜕𝑊
1 | 𝜕𝐿
𝜕𝑊
2 | 𝜕𝐿
𝜕𝑊
3 | 𝜕𝐿
𝜕𝑊
4 |


### Table 3

|  |  |  |  |  |  |  |


### Table 4

| 𝜕𝐿
1
𝜕𝑊
1 | 𝜕𝐿
1
𝜕𝑊
2 | 𝜕𝐿
1
𝜕𝑊
3 | 𝜕𝐿
1
𝜕𝑊
4 |  |
|  |  |  |  |  |


### Table 5

| 𝜕𝐿
𝜕𝑊
1 | 𝜕𝐿
𝜕𝑊
2 | 𝜕𝐿
𝜕𝑊
3 | 𝜕𝐿
𝜕𝑊
4 |


### Table 6

|  |  |  |  |  |  |  |


### Table 7

| 𝜕𝐿
2
𝜕𝑊
1 | 𝜕𝐿
2
𝜕𝑊
2 | 𝜕𝐿
2
𝜕𝑊
3 | 𝜕𝐿
2
𝜕𝑊
4 |  |
|  |  |  |  |  |
| 𝜕𝐿
𝜕𝑊
1 | 𝜕𝐿
𝜕𝑊
2 | 𝜕𝐿
𝜕𝑊
3 | 𝜕𝐿
𝜕𝑊
4 |  |


### Table 8

|  |  |  |  |  |  |  |


### Table 9

| 𝜕𝐿
3
𝜕𝑊
1 | 𝜕𝐿
3
𝜕𝑊
2 | 𝜕𝐿
3
𝜕𝑊
3 | 𝜕𝐿
3
𝜕𝑊
4 |


---
## Page 42
---


𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
Data Parallelism 1 2 3 4
x
1,1
x L
1,2 1
x
Recall: Loss is usually averaged
1,3
GPU 1 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
over a minibatch of N samples 1 1 1 1
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
Idea: Use minibatch of MN samples, 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
split over M GPUs 𝜕𝑊 1 𝜕𝑊 2 𝜕𝑊 3 𝜕𝑊 4
x
2,1
x L
2,2 2
Gradients are linear, so each GPU
x
2,3
computes its own gradient: 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
2 2 2 2
GPU 2
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
1. Each GPU has it’s own copy of model + optimizer
𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
2. Each GPU loads its own batch of data
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
3. Each GPU runs forward to compute loss x
3,1
4. Each GPU runs backward to compute gradients x L
3,2 3
5. Average gradients across all GPUs x
3,3
6. Each GPU updates its own weights GPU 3 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
3 3 3 3
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
Stanford CS231n 10th Anniversary Lecture 11 - 42 May 6, 2025

[Page contains 9 table(s)]


### Table 1

| 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
Data Parallelism 1 2 3 4
x
1,1
x L
1,2 1
x
Recall: Loss is usually averaged
1,3
GPU 1 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
over a minibatch of N samples 1 1 1 1
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
Idea: Use minibatch of MN samples, 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
split over M GPUs 𝜕𝑊 1 𝜕𝑊 2 𝜕𝑊 3 𝜕𝑊 4
x
2,1
x L
2,2 2
Gradients are linear, so each GPU
x
2,3
computes its own gradient: 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
2 2 2 2
GPU 2
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
1. Each GPU has it’s own copy of model + optimizer
𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
2. Each GPU loads its own batch of data
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
3. Each GPU runs forward to compute loss x
3,1
4. Each GPU runs backward to compute gradients x L
3,2 3
5. Average gradients across all GPUs x
3,3
6. Each GPU updates its own weights GPU 3 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
3 3 3 3
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4 |
| Stanford CS231n 10th Anniversary Lecture 11 - 42 May 6, 2025 |


### Table 2

| 𝜕𝐿
𝜕𝑊
1 | 𝜕𝐿
𝜕𝑊
2 | 𝜕𝐿
𝜕𝑊
3 | 𝜕𝐿
𝜕𝑊
4 |


### Table 3

|  |  |  |  |  |  |  |


### Table 4

| 𝜕𝐿
1
𝜕𝑊
1 | 𝜕𝐿
1
𝜕𝑊
2 | 𝜕𝐿
1
𝜕𝑊
3 | 𝜕𝐿
1
𝜕𝑊
4 |  |
|  |  |  |  |  |


### Table 5

| 𝜕𝐿
𝜕𝑊
1 | 𝜕𝐿
𝜕𝑊
2 | 𝜕𝐿
𝜕𝑊
3 | 𝜕𝐿
𝜕𝑊
4 |


### Table 6

|  |  |  |  |  |  |  |


### Table 7

| 𝜕𝐿
2
𝜕𝑊
1 | 𝜕𝐿
2
𝜕𝑊
2 | 𝜕𝐿
2
𝜕𝑊
3 | 𝜕𝐿
2
𝜕𝑊
4 |  |
|  |  |  |  |  |
| 𝜕𝐿
𝜕𝑊
1 | 𝜕𝐿
𝜕𝑊
2 | 𝜕𝐿
𝜕𝑊
3 | 𝜕𝐿
𝜕𝑊
4 |  |


### Table 8

|  |  |  |  |  |  |  |


### Table 9

| 𝜕𝐿
3
𝜕𝑊
1 | 𝜕𝐿
3
𝜕𝑊
2 | 𝜕𝐿
3
𝜕𝑊
3 | 𝜕𝐿
3
𝜕𝑊
4 |


---
## Page 43
---


𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
Data Parallelism 1 2 3 4
x
1,1
x L
1,2 1
x
Recall: Loss is usually averaged
1,3
GPU 1 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
over a minibatch of N samples 1 1 1 1
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
Idea: Use minibatch of MN samples, 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
split over M GPUs 𝜕𝑊 1 𝜕𝑊 2 𝜕𝑊 3 𝜕𝑊 4
x
2,1
x L
2,2 2
Gradients are linear, so each GPU
x
2,3
computes its own gradient: 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
2 2 2 2
GPU 2
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
1. Each GPU has it’s own copy of model + optimizer
𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
2. Each GPU loads its own batch of data
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
3. Each GPU runs forward to compute loss x
3,1
4. Each GPU runs backward to compute gradients x L
3,2 3
5. Average gradients across all GPUs x
3,3
6. Each GPU updates its own weights GPU 3 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
3 3 3 3
(4) and (5) can run in parallel! 𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
Stanford CS231n 10th Anniversary Lecture 11 - 43 May 6, 2025

[Page contains 9 table(s)]


### Table 1

| 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
Data Parallelism 1 2 3 4
x
1,1
x L
1,2 1
x
Recall: Loss is usually averaged
1,3
GPU 1 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
over a minibatch of N samples 1 1 1 1
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
Idea: Use minibatch of MN samples, 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
split over M GPUs 𝜕𝑊 1 𝜕𝑊 2 𝜕𝑊 3 𝜕𝑊 4
x
2,1
x L
2,2 2
Gradients are linear, so each GPU
x
2,3
computes its own gradient: 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
2 2 2 2
GPU 2
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
1. Each GPU has it’s own copy of model + optimizer
𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
2. Each GPU loads its own batch of data
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
3. Each GPU runs forward to compute loss x
3,1
4. Each GPU runs backward to compute gradients x L
3,2 3
5. Average gradients across all GPUs x
3,3
6. Each GPU updates its own weights GPU 3 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
3 3 3 3
(4) and (5) can run in parallel! 𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4 |
| Stanford CS231n 10th Anniversary Lecture 11 - 43 May 6, 2025 |


### Table 2

| 𝜕𝐿
𝜕𝑊
1 | 𝜕𝐿
𝜕𝑊
2 | 𝜕𝐿
𝜕𝑊
3 | 𝜕𝐿
𝜕𝑊
4 |


### Table 3

|  |  |  |  |  |  |  |


### Table 4

| 𝜕𝐿
1
𝜕𝑊
1 | 𝜕𝐿
1
𝜕𝑊
2 | 𝜕𝐿
1
𝜕𝑊
3 | 𝜕𝐿
1
𝜕𝑊
4 |  |
|  |  |  |  |  |


### Table 5

| 𝜕𝐿
𝜕𝑊
1 | 𝜕𝐿
𝜕𝑊
2 | 𝜕𝐿
𝜕𝑊
3 | 𝜕𝐿
𝜕𝑊
4 |


### Table 6

|  |  |  |  |  |  |  |


### Table 7

| 𝜕𝐿
2
𝜕𝑊
1 | 𝜕𝐿
2
𝜕𝑊
2 | 𝜕𝐿
2
𝜕𝑊
3 | 𝜕𝐿
2
𝜕𝑊
4 |  |
|  |  |  |  |  |
| 𝜕𝐿
𝜕𝑊
1 | 𝜕𝐿
𝜕𝑊
2 | 𝜕𝐿
𝜕𝑊
3 | 𝜕𝐿
𝜕𝑊
4 |  |


### Table 8

|  |  |  |  |  |  |  |


### Table 9

| 𝜕𝐿
3
𝜕𝑊
1 | 𝜕𝐿
3
𝜕𝑊
2 | 𝜕𝐿
3
𝜕𝑊
3 | 𝜕𝐿
3
𝜕𝑊
4 |


---
## Page 44
---


𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
Data Parallelism 1 2 3 4
x
1,1
x L
1,2 1
x
Recall: Loss is usually averaged
1,3
GPU 1 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
over a minibatch of N samples 1 1 1 1
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
Idea: Use minibatch of MN samples, 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
split over M GPUs 𝜕𝑊 1 𝜕𝑊 2 𝜕𝑊 3 𝜕𝑊 4
x
2,1
x L
2,2 2
Gradients are linear, so each GPU
x
2,3
computes its own gradient: 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
2 2 2 2
GPU 2
Problem: Model size constrained by GPU memory. 𝜕𝑊 1 𝜕𝑊 2 𝜕𝑊 3 𝜕𝑊 4
𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
Each weight needs 4 numbers (weight, grad, Adam β
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1, 1 2 3 4
β ). Each number needs 2 bytes. x
2 3,1
x L
3,2 3
1B params takes 8GB; 10B params fills up 80GB GPU. x
3,3
GPU 3 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
3 3 3 3
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
Stanford CS231n 10th Anniversary Lecture 11 - 44 May 6, 2025

[Page contains 9 table(s)]


### Table 1

| 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
Data Parallelism 1 2 3 4
x
1,1
x L
1,2 1
x
Recall: Loss is usually averaged
1,3
GPU 1 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
over a minibatch of N samples 1 1 1 1
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
Idea: Use minibatch of MN samples, 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
split over M GPUs 𝜕𝑊 1 𝜕𝑊 2 𝜕𝑊 3 𝜕𝑊 4
x
2,1
x L
2,2 2
Gradients are linear, so each GPU
x
2,3
computes its own gradient: 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
2 2 2 2
GPU 2
Problem: Model size constrained by GPU memory. 𝜕𝑊 1 𝜕𝑊 2 𝜕𝑊 3 𝜕𝑊 4
𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
Each weight needs 4 numbers (weight, grad, Adam β
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1, 1 2 3 4
β ). Each number needs 2 bytes. x
2 3,1
x L
3,2 3
1B params takes 8GB; 10B params fills up 80GB GPU. x
3,3
GPU 3 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
3 3 3 3
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4 |
| Stanford CS231n 10th Anniversary Lecture 11 - 44 May 6, 2025 |


### Table 2

| 𝜕𝐿
𝜕𝑊
1 | 𝜕𝐿
𝜕𝑊
2 | 𝜕𝐿
𝜕𝑊
3 | 𝜕𝐿
𝜕𝑊
4 |


### Table 3

|  |  |  |  |  |  |  |


### Table 4

| 𝜕𝐿
1
𝜕𝑊
1 | 𝜕𝐿
1
𝜕𝑊
2 | 𝜕𝐿
1
𝜕𝑊
3 | 𝜕𝐿
1
𝜕𝑊
4 |  |
|  |  |  |  |  |


### Table 5

| 𝜕𝐿
𝜕𝑊
1 | 𝜕𝐿
𝜕𝑊
2 | 𝜕𝐿
𝜕𝑊
3 | 𝜕𝐿
𝜕𝑊
4 |


### Table 6

|  |  |  |  |  |  |  |


### Table 7

| 𝜕𝐿
2
𝜕𝑊
1 | 𝜕𝐿
2
𝜕𝑊
2 | 𝜕𝐿
2
𝜕𝑊
3 | 𝜕𝐿
2
𝜕𝑊
4 |  |
|  |  |  |  |  |
| 𝜕𝐿
𝜕𝑊
1 | 𝜕𝐿
𝜕𝑊
2 | 𝜕𝐿
𝜕𝑊
3 | 𝜕𝐿
𝜕𝑊
4 |  |


### Table 8

|  |  |  |  |  |  |  |


### Table 9

| 𝜕𝐿
3
𝜕𝑊
1 | 𝜕𝐿
3
𝜕𝑊
2 | 𝜕𝐿
3
𝜕𝑊
3 | 𝜕𝐿
3
𝜕𝑊
4 |


---
## Page 45
---


𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
Data Parallelism 1 2 3 4
x
1,1
x L
1,2 1
x
Recall: Loss is usually averaged
1,3
GPU 1 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
over a minibatch of N samples 1 1 1 1
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
Idea: Use minibatch of MN samples, 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
split over M GPUs 𝜕𝑊 1 𝜕𝑊 2 𝜕𝑊 3 𝜕𝑊 4
x
2,1
x L
2,2 2
Gradients are linear, so each GPU
x
2,3
computes its own gradient: 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
2 2 2 2
GPU 2
Problem: Model size constrained by GPU memory. 𝜕𝑊 1 𝜕𝑊 2 𝜕𝑊 3 𝜕𝑊 4
𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
Each weight needs 4 numbers (weight, grad, Adam β
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1, 1 2 3 4
β ). Each number needs 2 bytes. x
2 3,1
x L
3,2 3
1B params takes 8GB; 10B params fills up 80GB GPU. x
3,3
GPU 3 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
3 3 3 3
Solution: Split model weights across GPUs 𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
Stanford CS231n 10th Anniversary Lecture 11 - 45 May 6, 2025

[Page contains 9 table(s)]


### Table 1

| 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
Data Parallelism 1 2 3 4
x
1,1
x L
1,2 1
x
Recall: Loss is usually averaged
1,3
GPU 1 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
over a minibatch of N samples 1 1 1 1
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
Idea: Use minibatch of MN samples, 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
split over M GPUs 𝜕𝑊 1 𝜕𝑊 2 𝜕𝑊 3 𝜕𝑊 4
x
2,1
x L
2,2 2
Gradients are linear, so each GPU
x
2,3
computes its own gradient: 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
2 2 2 2
GPU 2
Problem: Model size constrained by GPU memory. 𝜕𝑊 1 𝜕𝑊 2 𝜕𝑊 3 𝜕𝑊 4
𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
Each weight needs 4 numbers (weight, grad, Adam β
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1, 1 2 3 4
β ). Each number needs 2 bytes. x
2 3,1
x L
3,2 3
1B params takes 8GB; 10B params fills up 80GB GPU. x
3,3
GPU 3 𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
3 3 3 3
Solution: Split model weights across GPUs 𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4 |
| Stanford CS231n 10th Anniversary Lecture 11 - 45 May 6, 2025 |


### Table 2

| 𝜕𝐿
𝜕𝑊
1 | 𝜕𝐿
𝜕𝑊
2 | 𝜕𝐿
𝜕𝑊
3 | 𝜕𝐿
𝜕𝑊
4 |


### Table 3

|  |  |  |  |  |  |  |


### Table 4

| 𝜕𝐿
1
𝜕𝑊
1 | 𝜕𝐿
1
𝜕𝑊
2 | 𝜕𝐿
1
𝜕𝑊
3 | 𝜕𝐿
1
𝜕𝑊
4 |  |
|  |  |  |  |  |


### Table 5

| 𝜕𝐿
𝜕𝑊
1 | 𝜕𝐿
𝜕𝑊
2 | 𝜕𝐿
𝜕𝑊
3 | 𝜕𝐿
𝜕𝑊
4 |


### Table 6

|  |  |  |  |  |  |  |


### Table 7

| 𝜕𝐿
2
𝜕𝑊
1 | 𝜕𝐿
2
𝜕𝑊
2 | 𝜕𝐿
2
𝜕𝑊
3 | 𝜕𝐿
2
𝜕𝑊
4 |  |
|  |  |  |  |  |
| 𝜕𝐿
𝜕𝑊
1 | 𝜕𝐿
𝜕𝑊
2 | 𝜕𝐿
𝜕𝑊
3 | 𝜕𝐿
𝜕𝑊
4 |  |


### Table 8

|  |  |  |  |  |  |  |


### Table 9

| 𝜕𝐿
3
𝜕𝑊
1 | 𝜕𝐿
3
𝜕𝑊
2 | 𝜕𝐿
3
𝜕𝑊
3 | 𝜕𝐿
3
𝜕𝑊
4 |


---
## Page 46
---


Fully Sharded Data Parallelism (FSPD)
Split model weights across GPUs
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
x
2,1
x L
2,2 2
x
2,3
W W W W
1 2 3 4
GPU 2
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019
Stanford CS231n 10th Anniversary Lecture 11 - 46 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Fully Sharded Data Parallelism (FSPD)
Split model weights across GPUs
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
x
2,1
x L
2,2 2
x
2,3
W W W W
1 2 3 4
GPU 2
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019 |
| Stanford CS231n 10th Anniversary Lecture 11 - 46 May 6, 2025 |


---
## Page 47
---


Fully Sharded Data Parallelism (FSPD)
Split model weights across GPUs
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs
i
x
2,1
x L
2,2 2
x
2,3
W W W W
1 2 3 4
GPU 2
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019
Stanford CS231n 10th Anniversary Lecture 11 - 47 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Fully Sharded Data Parallelism (FSPD)
Split model weights across GPUs
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs
i
x
2,1
x L
2,2 2
x
2,3
W W W W
1 2 3 4
GPU 2
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019 |
| Stanford CS231n 10th Anniversary Lecture 11 - 47 May 6, 2025 |


---
## Page 48
---


Fully Sharded Data Parallelism (FSPD)
Split model weights across GPUs
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs
i
2. All GPUs run forward for layer i, then
delete their local copy of W
i
x
2,1
x L
2,2 2
x
2,3
W W W W
1 2 3 4
GPU 2
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019
Stanford CS231n 10th Anniversary Lecture 11 - 48 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Fully Sharded Data Parallelism (FSPD)
Split model weights across GPUs
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs
i
2. All GPUs run forward for layer i, then
delete their local copy of W
i
x
2,1
x L
2,2 2
x
2,3
W W W W
1 2 3 4
GPU 2
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019 |
| Stanford CS231n 10th Anniversary Lecture 11 - 48 May 6, 2025 |


---
## Page 49
---


Fully Sharded Data Parallelism (FSPD)
Split model weights across GPUs
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
computing forward
2. All GPUs run forward for layer i, then
with W
delete their local copy of W i
i
x
2,1
x L
2,2 2
x
2,3
W W W W
1 2 3 4
GPU 2
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019
Stanford CS231n 10th Anniversary Lecture 11 - 49 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Fully Sharded Data Parallelism (FSPD)
Split model weights across GPUs
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
computing forward
2. All GPUs run forward for layer i, then
with W
delete their local copy of W i
i
x
2,1
x L
2,2 2
x
2,3
W W W W
1 2 3 4
GPU 2
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019 |
| Stanford CS231n 10th Anniversary Lecture 11 - 49 May 6, 2025 |


---
## Page 50
---


Fully Sharded Data Parallelism (FSPD)
Split model weights across GPUs
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
computing forward
2. All GPUs run forward for layer i, then
with W
delete their local copy of W i
i
x
2,1
x L
2,2 2
x
2,3
W W W W
1 2 3 4
GPU 2
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019
Stanford CS231n 10th Anniversary Lecture 11 - 50 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Fully Sharded Data Parallelism (FSPD)
Split model weights across GPUs
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
computing forward
2. All GPUs run forward for layer i, then
with W
delete their local copy of W i
i
x
2,1
x L
2,2 2
x
2,3
W W W W
1 2 3 4
GPU 2
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019 |
| Stanford CS231n 10th Anniversary Lecture 11 - 50 May 6, 2025 |


---
## Page 51
---


Fully Sharded Data Parallelism (FSPD)
Split model weights across GPUs
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
computing forward
2. All GPUs run forward for layer i, then
with W
delete their local copy of W i
i
x
2,1
x L
2,2 2
x
2,3
W W W W
1 2 3 4
GPU 2
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019
Stanford CS231n 10th Anniversary Lecture 11 - 51 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Fully Sharded Data Parallelism (FSPD)
Split model weights across GPUs
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
computing forward
2. All GPUs run forward for layer i, then
with W
delete their local copy of W i
i
x
2,1
x L
2,2 2
x
2,3
W W W W
1 2 3 4
GPU 2
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019 |
| Stanford CS231n 10th Anniversary Lecture 11 - 51 May 6, 2025 |


---
## Page 52
---


Fully Sharded Data Parallelism (FSPD)
Split model weights across GPUs
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
computing forward
2. All GPUs run forward for layer i, then
with W
delete their local copy of W i
i
x
2,1
x L
2,2 2
x
2,3
W W W W
1 2 3 4
GPU 2
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019
Stanford CS231n 10th Anniversary Lecture 11 - 52 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Fully Sharded Data Parallelism (FSPD)
Split model weights across GPUs
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
computing forward
2. All GPUs run forward for layer i, then
with W
delete their local copy of W i
i
x
2,1
x L
2,2 2
x
2,3
W W W W
1 2 3 4
GPU 2
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019 |
| Stanford CS231n 10th Anniversary Lecture 11 - 52 May 6, 2025 |


---
## Page 53
---


Fully Sharded Data Parallelism (FSPD)
Split model weights across GPUs
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
computing forward
2. All GPUs run forward for layer i, then
with W
delete their local copy of W i
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
2,3
W W W W
1 2 3 4
GPU 2
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019
Stanford CS231n 10th Anniversary Lecture 11 - 53 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Fully Sharded Data Parallelism (FSPD)
Split model weights across GPUs
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
computing forward
2. All GPUs run forward for layer i, then
with W
delete their local copy of W i
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
2,3
W W W W
1 2 3 4
GPU 2
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019 |
| Stanford CS231n 10th Anniversary Lecture 11 - 53 May 6, 2025 |


---
## Page 54
---


Optimization: don’t delete last
weight at end of forward to
Fully Sharded Data Parallelism (FSPD) avoid immediately resending it
Split model weights across GPUs
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
computing forward
2. All GPUs run forward for layer i, then
with W
delete their local copy of W i
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
2,3
W W W W
1 2 3 4
GPU 2
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019
Stanford CS231n 10th Anniversary Lecture 11 - 54 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Optimization: don’t delete last
weight at end of forward to
Fully Sharded Data Parallelism (FSPD) avoid immediately resending it
Split model weights across GPUs
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
computing forward
2. All GPUs run forward for layer i, then
with W
delete their local copy of W i
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
2,3
W W W W
1 2 3 4
GPU 2
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019 |
| Stanford CS231n 10th Anniversary Lecture 11 - 54 May 6, 2025 |


---
## Page 55
---


Optimization: don’t delete last
weight at end of forward to
Fully Sharded Data Parallelism (FSPD) avoid immediately resending it
𝜕𝐿
Split model weights across GPUs 1
𝜕𝑊
4
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
2. All GPUs run forward for layer i, then computing forward 𝜕𝐿 2
with W
delete their local copy of W i 𝜕𝑊 4
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
4. All GPUs run backward for layer i to 2,3
W W W W
compute local dL/dW and delete W 1 2 3 4
i i GPU 2
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019
Stanford CS231n 10th Anniversary Lecture 11 - 55 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Optimization: don’t delete last
weight at end of forward to
Fully Sharded Data Parallelism (FSPD) avoid immediately resending it
𝜕𝐿
Split model weights across GPUs 1
𝜕𝑊
4
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
2. All GPUs run forward for layer i, then computing forward 𝜕𝐿 2
with W
delete their local copy of W i 𝜕𝑊 4
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
4. All GPUs run backward for layer i to 2,3
W W W W
compute local dL/dW and delete W 1 2 3 4
i i GPU 2
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019 |
| Stanford CS231n 10th Anniversary Lecture 11 - 55 May 6, 2025 |


---
## Page 56
---


Optimization: don’t delete last
weight at end of forward to
Fully Sharded Data Parallelism (FSPD) avoid immediately resending it
𝜕𝐿
Split model weights across GPUs 1
𝜕𝑊
4
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
2. All GPUs run forward for layer i, then computing forward 𝜕𝐿
with W
delete their local copy of W i 𝜕𝑊 4
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
4. All GPUs run backward for layer i to 2,3
W W W W
compute local dL/dW and delete W 1 2 3 4
i i GPU 2
5. After backward for layer i, all GPUs
send local dL/dW to owning GPU and
i
delete local dL/dW
i
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019
Stanford CS231n 10th Anniversary Lecture 11 - 56 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Optimization: don’t delete last
weight at end of forward to
Fully Sharded Data Parallelism (FSPD) avoid immediately resending it
𝜕𝐿
Split model weights across GPUs 1
𝜕𝑊
4
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
2. All GPUs run forward for layer i, then computing forward 𝜕𝐿
with W
delete their local copy of W i 𝜕𝑊 4
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
4. All GPUs run backward for layer i to 2,3
W W W W
compute local dL/dW and delete W 1 2 3 4
i i GPU 2
5. After backward for layer i, all GPUs
send local dL/dW to owning GPU and
i
delete local dL/dW
i
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019 |
| Stanford CS231n 10th Anniversary Lecture 11 - 56 May 6, 2025 |


---
## Page 57
---


Optimization: don’t delete last
weight at end of forward to
Fully Sharded Data Parallelism (FSPD) avoid immediately resending it
𝜕𝐿
Split model weights across GPUs 1
𝜕𝑊
4
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
2. All GPUs run forward for layer i, then computing forward 𝜕𝐿
with W
delete their local copy of W i 𝜕𝑊 4
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
4. All GPUs run backward for layer i to 2,3
W W W W
compute local dL/dW and delete W 1 2 3 4
i i GPU 2
5. After backward for layer i, all GPUs
send local dL/dW to owning GPU and
i
delete local dL/dW
i
6. Owner of W makes gradient update
i
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019
Stanford CS231n 10th Anniversary Lecture 11 - 57 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Optimization: don’t delete last
weight at end of forward to
Fully Sharded Data Parallelism (FSPD) avoid immediately resending it
𝜕𝐿
Split model weights across GPUs 1
𝜕𝑊
4
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
2. All GPUs run forward for layer i, then computing forward 𝜕𝐿
with W
delete their local copy of W i 𝜕𝑊 4
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
4. All GPUs run backward for layer i to 2,3
W W W W
compute local dL/dW and delete W 1 2 3 4
i i GPU 2
5. After backward for layer i, all GPUs
send local dL/dW to owning GPU and
i
delete local dL/dW
i
6. Owner of W makes gradient update
i
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019 |
| Stanford CS231n 10th Anniversary Lecture 11 - 57 May 6, 2025 |


---
## Page 58
---


Optimization: don’t delete last
weight at end of forward to
Fully Sharded Data Parallelism (FSPD) avoid immediately resending it
𝜕𝐿
Split model weights across GPUs 1
𝜕𝑊
4
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
2. All GPUs run forward for layer i, then computing forward 𝜕𝐿
with W
delete their local copy of W i 𝜕𝑊 4
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
4. All GPUs run backward for layer i to Fetch W while 2,3
i W W W W
compute local dL/dW and delete W computing with 1 2 3 4
i i GPU 2
5. After backward for layer i, all GPUs W ; send dL/dW
i+1 i
send local dL/dW to owning GPU and and update W i
i
while computing
delete local dL/dW
i with W
6. Owner of W makes gradient update i-1
i
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019
Stanford CS231n 10th Anniversary Lecture 11 - 58 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Optimization: don’t delete last
weight at end of forward to
Fully Sharded Data Parallelism (FSPD) avoid immediately resending it
𝜕𝐿
Split model weights across GPUs 1
𝜕𝑊
4
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
2. All GPUs run forward for layer i, then computing forward 𝜕𝐿
with W
delete their local copy of W i 𝜕𝑊 4
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
4. All GPUs run backward for layer i to Fetch W while 2,3
i W W W W
compute local dL/dW and delete W computing with 1 2 3 4
i i GPU 2
5. After backward for layer i, all GPUs W ; send dL/dW
i+1 i
send local dL/dW to owning GPU and and update W i
i
while computing
delete local dL/dW
i with W
6. Owner of W makes gradient update i-1
i
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019 |
| Stanford CS231n 10th Anniversary Lecture 11 - 58 May 6, 2025 |


---
## Page 59
---


Optimization: don’t delete last
weight at end of forward to
Fully Sharded Data Parallelism (FSPD) avoid immediately resending it
𝜕𝐿
Split model weights across GPUs 1
𝜕𝑊
4
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
2. All GPUs run forward for layer i, then computing forward 𝜕𝐿
with W
delete their local copy of W i 𝜕𝑊 4
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
4. All GPUs run backward for layer i to Fetch W while 2,3
i W W W W
compute local dL/dW and delete W computing with 1 2 3 4
i i GPU 2
5. After backward for layer i, all GPUs W ; send dL/dW
i+1 i
send local dL/dW to owning GPU and and update W i
i
while computing
delete local dL/dW
i with W
6. Owner of W makes gradient update i-1
i
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019
Stanford CS231n 10th Anniversary Lecture 11 - 59 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Optimization: don’t delete last
weight at end of forward to
Fully Sharded Data Parallelism (FSPD) avoid immediately resending it
𝜕𝐿
Split model weights across GPUs 1
𝜕𝑊
4
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
2. All GPUs run forward for layer i, then computing forward 𝜕𝐿
with W
delete their local copy of W i 𝜕𝑊 4
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
4. All GPUs run backward for layer i to Fetch W while 2,3
i W W W W
compute local dL/dW and delete W computing with 1 2 3 4
i i GPU 2
5. After backward for layer i, all GPUs W ; send dL/dW
i+1 i
send local dL/dW to owning GPU and and update W i
i
while computing
delete local dL/dW
i with W
6. Owner of W makes gradient update i-1
i
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019 |
| Stanford CS231n 10th Anniversary Lecture 11 - 59 May 6, 2025 |


---
## Page 60
---


Optimization: don’t delete last
weight at end of forward to
Fully Sharded Data Parallelism (FSPD) avoid immediately resending it
𝜕𝐿 𝜕𝐿
Split model weights across GPUs 1 1
𝜕𝑊 𝜕𝑊
3 4
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
2. All GPUs run forward for layer i, then computing forward 𝜕𝐿 2 𝜕𝐿
with W
delete their local copy of W i 𝜕𝑊 3 𝜕𝑊 4
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
4. All GPUs run backward for layer i to Fetch W while 2,3
i W W W W
compute local dL/dW and delete W computing with 1 2 3 4
i i GPU 2
5. After backward for layer i, all GPUs W ; send dL/dW
i+1 i
send local dL/dW to owning GPU and and update W i
i
while computing
delete local dL/dW
i with W
6. Owner of W makes gradient update i-1
i
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019
Stanford CS231n 10th Anniversary Lecture 11 - 60 May 6, 2025

[Page contains 3 table(s)]


### Table 1

| Optimization: don’t delete last
weight at end of forward to
Fully Sharded Data Parallelism (FSPD) avoid immediately resending it
𝜕𝐿 𝜕𝐿
Split model weights across GPUs 1 1
𝜕𝑊 𝜕𝑊
3 4
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
2. All GPUs run forward for layer i, then computing forward 𝜕𝐿 2 𝜕𝐿
with W
delete their local copy of W i 𝜕𝑊 3 𝜕𝑊 4
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
4. All GPUs run backward for layer i to Fetch W while 2,3
i W W W W
compute local dL/dW and delete W computing with 1 2 3 4
i i GPU 2
5. After backward for layer i, all GPUs W ; send dL/dW
i+1 i
send local dL/dW to owning GPU and and update W i
i
while computing
delete local dL/dW
i with W
6. Owner of W makes gradient update i-1
i
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019 |
| Stanford CS231n 10th Anniversary Lecture 11 - 60 May 6, 2025 |


### Table 2

| 𝜕𝐿
1
𝜕𝑊
3 | 𝜕𝐿
1
𝜕𝑊
4 |


### Table 3

| 𝜕𝐿
2
𝜕𝑊
3 | 𝜕𝐿
𝜕𝑊
4 |


---
## Page 61
---


Optimization: don’t delete last
weight at end of forward to
Fully Sharded Data Parallelism (FSPD) avoid immediately resending it
𝜕𝐿 𝜕𝐿 𝜕𝐿
Split model weights across GPUs 1 1 1
𝜕𝑊 𝜕𝑊 𝜕𝑊
2 3 4
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
2. All GPUs run forward for layer i, then computing forward 𝜕𝐿 2 𝜕𝐿 𝜕𝐿
with W
delete their local copy of W i 𝜕𝑊 2 𝜕𝑊 3 𝜕𝑊 4
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
4. All GPUs run backward for layer i to Fetch W while 2,3
i W W W W
compute local dL/dW and delete W computing with 1 2 3 4
i i GPU 2
5. After backward for layer i, all GPUs W ; send dL/dW All at the same time:
i+1 i
send local dL/dW to owning GPU and and update W i - Send grads and update W 3
i
while computing - Run backward with W
delete local dL/dW 2
i with W - Fetch W
6. Owner of W makes gradient update i-1 1
i
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019
Stanford CS231n 10th Anniversary Lecture 11 - 61 May 6, 2025

[Page contains 3 table(s)]


### Table 1

| Optimization: don’t delete last
weight at end of forward to
Fully Sharded Data Parallelism (FSPD) avoid immediately resending it
𝜕𝐿 𝜕𝐿 𝜕𝐿
Split model weights across GPUs 1 1 1
𝜕𝑊 𝜕𝑊 𝜕𝑊
2 3 4
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
2. All GPUs run forward for layer i, then computing forward 𝜕𝐿 2 𝜕𝐿 𝜕𝐿
with W
delete their local copy of W i 𝜕𝑊 2 𝜕𝑊 3 𝜕𝑊 4
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
4. All GPUs run backward for layer i to Fetch W while 2,3
i W W W W
compute local dL/dW and delete W computing with 1 2 3 4
i i GPU 2
5. After backward for layer i, all GPUs W ; send dL/dW All at the same time:
i+1 i
send local dL/dW to owning GPU and and update W i - Send grads and update W 3
i
while computing - Run backward with W
delete local dL/dW 2
i with W - Fetch W
6. Owner of W makes gradient update i-1 1
i
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019 |
| Stanford CS231n 10th Anniversary Lecture 11 - 61 May 6, 2025 |


### Table 2

|  |  |  |  |
| 𝜕𝐿
1
𝜕𝑊
2 | 𝜕𝐿
1
𝜕𝑊
3 |  | 𝜕𝐿
1
𝜕𝑊
4 |


### Table 3

| 𝜕𝐿
2
𝜕𝑊
2 | 𝜕𝐿
𝜕𝑊
3 | 𝜕𝐿
𝜕𝑊
4 |


---
## Page 62
---


Optimization: don’t delete last
weight at end of forward to
Fully Sharded Data Parallelism (FSPD) avoid immediately resending it
𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
Split model weights across GPUs 1 1 1
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
2. All GPUs run forward for layer i, then computing forward 𝜕𝐿 2 𝜕𝐿 2 𝜕𝐿 𝜕𝐿
with W
delete their local copy of W i 𝜕𝑊 1 𝜕𝑊 2 𝜕𝑊 3 𝜕𝑊 4
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
4. All GPUs run backward for layer i to Fetch W while 2,3
i W W W W
compute local dL/dW and delete W computing with 1 2 3 4
i i GPU 2
5. After backward for layer i, all GPUs W ; send dL/dW
i+1 i
send local dL/dW to owning GPU and and update W i
i
while computing
delete local dL/dW
i with W
6. Owner of W makes gradient update i-1
i
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019
Stanford CS231n 10th Anniversary Lecture 11 - 62 May 6, 2025

[Page contains 3 table(s)]


### Table 1

| Optimization: don’t delete last
weight at end of forward to
Fully Sharded Data Parallelism (FSPD) avoid immediately resending it
𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
Split model weights across GPUs 1 1 1
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
2. All GPUs run forward for layer i, then computing forward 𝜕𝐿 2 𝜕𝐿 2 𝜕𝐿 𝜕𝐿
with W
delete their local copy of W i 𝜕𝑊 1 𝜕𝑊 2 𝜕𝑊 3 𝜕𝑊 4
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
4. All GPUs run backward for layer i to Fetch W while 2,3
i W W W W
compute local dL/dW and delete W computing with 1 2 3 4
i i GPU 2
5. After backward for layer i, all GPUs W ; send dL/dW
i+1 i
send local dL/dW to owning GPU and and update W i
i
while computing
delete local dL/dW
i with W
6. Owner of W makes gradient update i-1
i
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019 |
| Stanford CS231n 10th Anniversary Lecture 11 - 62 May 6, 2025 |


### Table 2

| 𝜕𝐿
1
𝜕𝑊
1 | 𝜕𝐿
𝜕𝑊
2 | 𝜕𝐿
1
𝜕𝑊
3 | 𝜕𝐿
1
𝜕𝑊
4 |


### Table 3

| 𝜕𝐿
2
𝜕𝑊
1 | 𝜕𝐿
2
𝜕𝑊
2 | 𝜕𝐿
𝜕𝑊
3 | 𝜕𝐿
𝜕𝑊
4 |


---
## Page 63
---


Optimization: don’t delete last
weight at end of forward to
Fully Sharded Data Parallelism (FSPD) avoid immediately resending it
𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
Split model weights across GPUs 1 1
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
2. All GPUs run forward for layer i, then computing forward 𝜕𝐿 2 𝜕𝐿 2 𝜕𝐿 𝜕𝐿
with W
delete their local copy of W i 𝜕𝑊 1 𝜕𝑊 2 𝜕𝑊 3 𝜕𝑊 4
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
4. All GPUs run backward for layer i to Fetch W while 2,3
i W W W W
compute local dL/dW and delete W computing with 1 2 3 4
i i GPU 2
5. After backward for layer i, all GPUs W ; send dL/dW
i+1 i
send local dL/dW to owning GPU and and update W i
i
while computing
delete local dL/dW
i with W
6. Owner of W makes gradient update i-1
i
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019
Stanford CS231n 10th Anniversary Lecture 11 - 63 May 6, 2025

[Page contains 3 table(s)]


### Table 1

| Optimization: don’t delete last
weight at end of forward to
Fully Sharded Data Parallelism (FSPD) avoid immediately resending it
𝜕𝐿 𝜕𝐿 𝜕𝐿 𝜕𝐿
Split model weights across GPUs 1 1
𝜕𝑊 𝜕𝑊 𝜕𝑊 𝜕𝑊
1 2 3 4
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
2. All GPUs run forward for layer i, then computing forward 𝜕𝐿 2 𝜕𝐿 2 𝜕𝐿 𝜕𝐿
with W
delete their local copy of W i 𝜕𝑊 1 𝜕𝑊 2 𝜕𝑊 3 𝜕𝑊 4
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
4. All GPUs run backward for layer i to Fetch W while 2,3
i W W W W
compute local dL/dW and delete W computing with 1 2 3 4
i i GPU 2
5. After backward for layer i, all GPUs W ; send dL/dW
i+1 i
send local dL/dW to owning GPU and and update W i
i
while computing
delete local dL/dW
i with W
6. Owner of W makes gradient update i-1
i
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019 |
| Stanford CS231n 10th Anniversary Lecture 11 - 63 May 6, 2025 |


### Table 2

| 𝜕𝐿
𝜕𝑊
1 | 𝜕𝐿
𝜕𝑊
2 | 𝜕𝐿
1
𝜕𝑊
3 | 𝜕𝐿
1
𝜕𝑊
4 |


### Table 3

| 𝜕𝐿
2
𝜕𝑊
1 | 𝜕𝐿
2
𝜕𝑊
2 | 𝜕𝐿
𝜕𝑊
3 | 𝜕𝐿
𝜕𝑊
4 |


---
## Page 64
---


Optimization: don’t delete last
weight at end of forward to
Fully Sharded Data Parallelism (FSPD) avoid immediately resending it
Split model weights across GPUs
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
computing forward
2. All GPUs run forward for layer i, then
with W
delete their local copy of W i
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
4. All GPUs run backward for layer i to Fetch W while 2,3
i W W W W
compute local dL/dW and delete W computing with 1 2 3 4
i i GPU 2
5. After backward for layer i, all GPUs W ; send dL/dW
i+1 i
send local dL/dW to owning GPU and and update W i Repeat with next batch of data
i while computing Data was being pre-fetched
delete local dL/dW
i with W during forward+backward
6. Owner of W makes gradient update i-1
i
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019
Stanford CS231n 10th Anniversary Lecture 11 - 64 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Optimization: don’t delete last
weight at end of forward to
Fully Sharded Data Parallelism (FSPD) avoid immediately resending it
Split model weights across GPUs
x
Each weight W is owned by one GPU, 1,1
i x L
which also holds its grads and optim states 1,2 1
x
1,3
GPU 1 W W W W
1 2 3 4
1. Before forward for layer i, the GPU that
owns W broadcasts it to all GPUs Fetch W while
i+1
i
computing forward
2. All GPUs run forward for layer i, then
with W
delete their local copy of W i
i
x
3. Before backward for layer i, owner 2,1
x L
broadcasts W to all GPUs 2,2 2
i
x
4. All GPUs run backward for layer i to Fetch W while 2,3
i W W W W
compute local dL/dW and delete W computing with 1 2 3 4
i i GPU 2
5. After backward for layer i, all GPUs W ; send dL/dW
i+1 i
send local dL/dW to owning GPU and and update W i Repeat with next batch of data
i while computing Data was being pre-fetched
delete local dL/dW
i with W during forward+backward
6. Owner of W makes gradient update i-1
i
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019 |
| Stanford CS231n 10th Anniversary Lecture 11 - 64 May 6, 2025 |


---
## Page 65
---


Hybrid Sharded Data Parallel (HSDP)
Split N = M*K GPUs into M groups of K Example: HSDP with M=2 groups of K=4 GPUs
Each group of K GPUs does FSDP, splits
model weights across all K GPUs. K can GPU (1, 1) GPU (2, 1)
W W W W W W W W
be O(100) GPUs. 1 2 3 4 1 2 3 4
Do DP across the M groups.
GPU (1, 2) GPU (2, 2)
W W W W W W W W
1 2 3 4 1 2 3 4
GPU (1, 3) GPU (2, 3)
W W W W W W W W
1 2 3 4 1 2 3 4
GPU (1, 4) GPU (2, 4)
W W W W W W W W
1 2 3 4 1 2 3 4
Stanford CS231n 10th Anniversary Lecture 11 - 65 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Hybrid Sharded Data Parallel (HSDP)
Split N = M*K GPUs into M groups of K Example: HSDP with M=2 groups of K=4 GPUs
Each group of K GPUs does FSDP, splits
model weights across all K GPUs. K can GPU (1, 1) GPU (2, 1)
W W W W W W W W
be O(100) GPUs. 1 2 3 4 1 2 3 4
Do DP across the M groups.
GPU (1, 2) GPU (2, 2)
W W W W W W W W
1 2 3 4 1 2 3 4
GPU (1, 3) GPU (2, 3)
W W W W W W W W
1 2 3 4 1 2 3 4
GPU (1, 4) GPU (2, 4)
W W W W W W W W
1 2 3 4 1 2 3 4 |
| Stanford CS231n 10th Anniversary Lecture 11 - 65 May 6, 2025 |


---
## Page 66
---


Hybrid Sharded Data Parallel (HSDP)
Split N = M*K GPUs into M groups of K Example: HSDP with M=2 groups of K=4 GPUs
Each group of K GPUs does FSDP, splits
model weights across all K GPUs. K can GPU (1, 1) GPU (2, 1)
W W W W W W W W
be O(100) GPUs. 1 2 3 4 1 2 3 4
Do DP across the M groups.
GPU (1, 2) GPU (2, 2)
Multidimensional parallelism: Use W W W W W W W W
1 2 3 4 1 2 3 4
different parallelism strategies at the
same time! Organize GPUs in a 2D grid
GPU (1, 3) GPU (2, 3)
W W W W W W W W
1 2 3 4 1 2 3 4
GPU (1, 4) GPU (2, 4)
W W W W W W W W
1 2 3 4 1 2 3 4
Stanford CS231n 10th Anniversary Lecture 11 - 66 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Hybrid Sharded Data Parallel (HSDP)
Split N = M*K GPUs into M groups of K Example: HSDP with M=2 groups of K=4 GPUs
Each group of K GPUs does FSDP, splits
model weights across all K GPUs. K can GPU (1, 1) GPU (2, 1)
W W W W W W W W
be O(100) GPUs. 1 2 3 4 1 2 3 4
Do DP across the M groups.
GPU (1, 2) GPU (2, 2)
Multidimensional parallelism: Use W W W W W W W W
1 2 3 4 1 2 3 4
different parallelism strategies at the
same time! Organize GPUs in a 2D grid
GPU (1, 3) GPU (2, 3)
W W W W W W W W
1 2 3 4 1 2 3 4
GPU (1, 4) GPU (2, 4)
W W W W W W W W
1 2 3 4 1 2 3 4 |
| Stanford CS231n 10th Anniversary Lecture 11 - 66 May 6, 2025 |


---
## Page 67
---


Hybrid Sharded Data Parallel (HSDP)
Split N = M*K GPUs into M groups of K Example: HSDP with M=2 groups of K=4 GPUs
Each group of K GPUs does FSDP, splits
model weights across all K GPUs. K can GPU (1, 1) GPU (2, 1)
W W W W W W W W
be O(100) GPUs. 1 2 3 4 1 2 3 4
Do DP across the M groups.
GPU (1, 2) GPU (2, 2)
Multidimensional parallelism: Use W W W W W W W W
1 2 3 4 1 2 3 4
different parallelism strategies at the
same time! Organize GPUs in a 2D grid
GPU (1, 3) GPU (2, 3)
W W W W W W W W
3x communication inside each group of K: 1 2 3 4 1 2 3 4
W in forward, W + dL/dW in backward.
Keep them in the same node / pod.
GPU (1, 4) GPU (2, 4)
1x communication across the M groups: dL/dW W W W W W W W W
1 2 3 4 1 2 3 4
in backward. Can use slower communication.
Stanford CS231n 10th Anniversary Lecture 11 - 67 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Hybrid Sharded Data Parallel (HSDP)
Split N = M*K GPUs into M groups of K Example: HSDP with M=2 groups of K=4 GPUs
Each group of K GPUs does FSDP, splits
model weights across all K GPUs. K can GPU (1, 1) GPU (2, 1)
W W W W W W W W
be O(100) GPUs. 1 2 3 4 1 2 3 4
Do DP across the M groups.
GPU (1, 2) GPU (2, 2)
Multidimensional parallelism: Use W W W W W W W W
1 2 3 4 1 2 3 4
different parallelism strategies at the
same time! Organize GPUs in a 2D grid
GPU (1, 3) GPU (2, 3)
W W W W W W W W
3x communication inside each group of K: 1 2 3 4 1 2 3 4
W in forward, W + dL/dW in backward.
Keep them in the same node / pod.
GPU (1, 4) GPU (2, 4)
1x communication across the M groups: dL/dW W W W W W W W W
1 2 3 4 1 2 3 4
in backward. Can use slower communication. |
| Stanford CS231n 10th Anniversary Lecture 11 - 67 May 6, 2025 |


---
## Page 68
---


Data Parallelism (DP, FSPD, HSDP)
Split data and model weights across GPUs
x
Can now scale up to big models that don’t fit in 1,1
x L
a single GPU! 1,2 1
x
1,3
GPU 1 W W W W
A model with 100B params needs 4 numbers 1 2 3 4
per param (param, grad, Adam β , β );
1 1
2 bytes per number takes 800GB;
splitting over 80 GPUs is just 10GB per GPU!
x
2,1
x L
2,2 2
x
2,3
W W W W
1 2 3 4
GPU 2
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019
Stanford CS231n 10th Anniversary Lecture 11 - 68 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Data Parallelism (DP, FSPD, HSDP)
Split data and model weights across GPUs
x
Can now scale up to big models that don’t fit in 1,1
x L
a single GPU! 1,2 1
x
1,3
GPU 1 W W W W
A model with 100B params needs 4 numbers 1 2 3 4
per param (param, grad, Adam β , β );
1 1
2 bytes per number takes 800GB;
splitting over 80 GPUs is just 10GB per GPU!
x
2,1
x L
2,2 2
x
2,3
W W W W
1 2 3 4
GPU 2
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019 |
| Stanford CS231n 10th Anniversary Lecture 11 - 68 May 6, 2025 |


---
## Page 69
---


Data Parallelism (DP, FSPD, HSDP)
Split data and model weights across GPUs
x
Can now scale up to big models that don’t fit in 1,1
x L
a single GPU! 1,2 1
x
1,3
GPU 1 W W W W
A model with 100B params needs 4 numbers 1 2 3 4
per param (param, grad, Adam β , β );
1 1
2 bytes per number takes 800GB;
splitting over 80 GPUs is just 10GB per GPU!
x
2,1
Problem: Model activations can fill up memory. x L
2,2 2
Llama3-405B Transformer has 126 layers,
x
2,3
D=16,384, seq length 4096. Just FFN hidden W W W W
1 2 3 4
activations need 2*126*(4*16384)*4096 bytes GPU 2
= 63GB; plus need other activations.
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019
Stanford CS231n 10th Anniversary Lecture 11 - 69 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Data Parallelism (DP, FSPD, HSDP)
Split data and model weights across GPUs
x
Can now scale up to big models that don’t fit in 1,1
x L
a single GPU! 1,2 1
x
1,3
GPU 1 W W W W
A model with 100B params needs 4 numbers 1 2 3 4
per param (param, grad, Adam β , β );
1 1
2 bytes per number takes 800GB;
splitting over 80 GPUs is just 10GB per GPU!
x
2,1
Problem: Model activations can fill up memory. x L
2,2 2
Llama3-405B Transformer has 126 layers,
x
2,3
D=16,384, seq length 4096. Just FFN hidden W W W W
1 2 3 4
activations need 2*126*(4*16384)*4096 bytes GPU 2
= 63GB; plus need other activations.
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019 |
| Stanford CS231n 10th Anniversary Lecture 11 - 69 May 6, 2025 |


---
## Page 70
---


Data Parallelism (DP, FSPD, HSDP)
Split data and model weights across GPUs
x
Can now scale up to big models that don’t fit in 1,1
x L
a single GPU! 1,2 1
x
1,3
GPU 1 W W W W
A model with 100B params needs 4 numbers 1 2 3 4
per param (param, grad, Adam β , β );
1 1
2 bytes per number takes 800GB;
splitting over 80 GPUs is just 10GB per GPU!
x
2,1
Problem: Model activations can fill up memory. x L
2,2 2
Llama3-405B Transformer has 126 layers,
x
2,3
D=16,384, seq length 4096. Just FFN hidden W W W W
1 2 3 4
activations need 2*126*(4*16384)*4096 bytes GPU 2
= 63GB; plus need other activations.
Solution: Don’t keep all activations in
memory; recompute them on the fly!
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019
Stanford CS231n 10th Anniversary Lecture 11 - 70 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Data Parallelism (DP, FSPD, HSDP)
Split data and model weights across GPUs
x
Can now scale up to big models that don’t fit in 1,1
x L
a single GPU! 1,2 1
x
1,3
GPU 1 W W W W
A model with 100B params needs 4 numbers 1 2 3 4
per param (param, grad, Adam β , β );
1 1
2 bytes per number takes 800GB;
splitting over 80 GPUs is just 10GB per GPU!
x
2,1
Problem: Model activations can fill up memory. x L
2,2 2
Llama3-405B Transformer has 126 layers,
x
2,3
D=16,384, seq length 4096. Just FFN hidden W W W W
1 2 3 4
activations need 2*126*(4*16384)*4096 bytes GPU 2
= 63GB; plus need other activations.
Solution: Don’t keep all activations in
memory; recompute them on the fly!
Rajbhandrariet al, “ZeRO: Memory Optimizations Toward Training Trillion Parameter Models”, arXiv2019 |
| Stanford CS231n 10th Anniversary Lecture 11 - 70 May 6, 2025 |


---
## Page 71
---


Activation Checkpointing
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
𝐴 𝐺
1 1
Stanford CS231n 10th Anniversary Lecture 11 - 71 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Activation Checkpointing
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
𝐴 𝐺
1 1 |
| Stanford CS231n 10th Anniversary Lecture 11 - 71 May 6, 2025 |


---
## Page 72
---


Activation Checkpointing
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Q: How much compute and memory does
𝐴 𝐺
1 1
→ ←
this take? Assume each 𝐹 and 𝐹 is O(1)
𝑖 𝑖
compute and memory.
Stanford CS231n 10th Anniversary Lecture 11 - 72 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Activation Checkpointing
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Q: How much compute and memory does
𝐴 𝐺
1 1
→ ←
this take? Assume each 𝐹 and 𝐹 is O(1)
𝑖 𝑖
compute and memory. |
| Stanford CS231n 10th Anniversary Lecture 11 - 72 May 6, 2025 |


---
## Page 73
---


Compute: 1
Activation Checkpointing
Current Memory: 1
Peak Memory: 1
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Q: How much compute and memory does
𝐴 𝐺
1 1
→ ←
this take? Assume each 𝐹 and 𝐹 is O(1)
𝑖 𝑖
compute and memory.
Stanford CS231n 10th Anniversary Lecture 11 - 73 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Compute: 1
Activation Checkpointing
Current Memory: 1
Peak Memory: 1
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Q: How much compute and memory does
𝐴 𝐺
1 1
→ ←
this take? Assume each 𝐹 and 𝐹 is O(1)
𝑖 𝑖
compute and memory. |
| Stanford CS231n 10th Anniversary Lecture 11 - 73 May 6, 2025 |


### Table 2

| 𝐴
4
𝐴
3
𝐴
2 | 𝐴
4 |
|  | 𝐴
1 |


---
## Page 74
---


Compute: 2
Activation Checkpointing
Current Memory: 2
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Q: How much compute and memory does
𝐴 𝐺
1 1
→ ←
this take? Assume each 𝐹 and 𝐹 is O(1)
𝑖 𝑖
compute and memory.
Stanford CS231n 10th Anniversary Lecture 11 - 74 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Compute: 2
Activation Checkpointing
Current Memory: 2
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Q: How much compute and memory does
𝐴 𝐺
1 1
→ ←
this take? Assume each 𝐹 and 𝐹 is O(1)
𝑖 𝑖
compute and memory. |
| Stanford CS231n 10th Anniversary Lecture 11 - 74 May 6, 2025 |


### Table 2

| 𝐴
4
𝐴
3 | 𝐴
4 |  |
|  |  |  |
|  | 𝐴
2 |  |


---
## Page 75
---


Compute: 3
Activation Checkpointing
Current Memory: 3
Peak Memory: 3
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Q: How much compute and memory does
𝐴 𝐺
1 1
→ ←
this take? Assume each 𝐹 and 𝐹 is O(1)
𝑖 𝑖
compute and memory.
Stanford CS231n 10th Anniversary Lecture 11 - 75 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Compute: 3
Activation Checkpointing
Current Memory: 3
Peak Memory: 3
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Q: How much compute and memory does
𝐴 𝐺
1 1
→ ←
this take? Assume each 𝐹 and 𝐹 is O(1)
𝑖 𝑖
compute and memory. |
| Stanford CS231n 10th Anniversary Lecture 11 - 75 May 6, 2025 |


### Table 2

| 𝐴
4 | 𝐴
4 |
|  | 𝐴
3 |


---
## Page 76
---


Compute: 4
Activation Checkpointing
Current Memory: 4
Peak Memory: 4
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Q: How much compute and memory does
𝐴 𝐺
1 1
→ ←
this take? Assume each 𝐹 and 𝐹 is O(1)
𝑖 𝑖
compute and memory.
Stanford CS231n 10th Anniversary Lecture 11 - 76 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Compute: 4
Activation Checkpointing
Current Memory: 4
Peak Memory: 4
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Q: How much compute and memory does
𝐴 𝐺
1 1
→ ←
this take? Assume each 𝐹 and 𝐹 is O(1)
𝑖 𝑖
compute and memory. |
| Stanford CS231n 10th Anniversary Lecture 11 - 76 May 6, 2025 |


---
## Page 77
---


Compute: 5
Activation Checkpointing
Current Memory: 4
Peak Memory: 4
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Q: How much compute and memory does
𝐴 𝐺
1 1
→ ←
this take? Assume each 𝐹 and 𝐹 is O(1)
𝑖 𝑖
compute and memory.
Stanford CS231n 10th Anniversary Lecture 11 - 77 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Compute: 5
Activation Checkpointing
Current Memory: 4
Peak Memory: 4
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Q: How much compute and memory does
𝐴 𝐺
1 1
→ ←
this take? Assume each 𝐹 and 𝐹 is O(1)
𝑖 𝑖
compute and memory. |
| Stanford CS231n 10th Anniversary Lecture 11 - 77 May 6, 2025 |


### Table 2

| 𝐴
4 |  |  |  |
|  | 𝐴
4 |  | 𝐺
4 |
|  |  |  |  |
|  | 𝐴
3 |  | 𝐺
3 |


---
## Page 78
---


Compute: 6
Activation Checkpointing
Current Memory: 3
Peak Memory: 4
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Q: How much compute and memory does
𝐴 𝐺
1 1
→ ←
this take? Assume each 𝐹 and 𝐹 is O(1)
𝑖 𝑖
compute and memory.
Stanford CS231n 10th Anniversary Lecture 11 - 78 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Compute: 6
Activation Checkpointing
Current Memory: 3
Peak Memory: 4
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Q: How much compute and memory does
𝐴 𝐺
1 1
→ ←
this take? Assume each 𝐹 and 𝐹 is O(1)
𝑖 𝑖
compute and memory. |
| Stanford CS231n 10th Anniversary Lecture 11 - 78 May 6, 2025 |


### Table 2

| 𝐴
4
𝐴
3 |  |  |  | 𝐺
4 |
|  | 𝐴
3 |  |  | 𝐺
3 |
|  |  |  |  |  |
|  | 𝐴
2 |  |  | 𝐺
2 |


---
## Page 79
---


Compute: 7
Activation Checkpointing
Current Memory: 2
Peak Memory: 4
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Q: How much compute and memory does
𝐴 𝐺
1 1
→ ←
this take? Assume each 𝐹 and 𝐹 is O(1)
𝑖 𝑖
compute and memory.
Stanford CS231n 10th Anniversary Lecture 11 - 79 May 6, 2025

[Page contains 3 table(s)]


### Table 1

| Compute: 7
Activation Checkpointing
Current Memory: 2
Peak Memory: 4
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Q: How much compute and memory does
𝐴 𝐺
1 1
→ ←
this take? Assume each 𝐹 and 𝐹 is O(1)
𝑖 𝑖
compute and memory. |
| Stanford CS231n 10th Anniversary Lecture 11 - 79 May 6, 2025 |


### Table 2

| 𝐴
4
𝐴
3
𝐴
2 |  |  |  | 𝐺
4
𝐺
3 |
|  | 𝐴
2 |  |  | 𝐺
2 |
|  |  |  |  |  |
|  | 𝐴
1 |  |  | 𝐺
1 |


### Table 3

| 𝐺
4 |
|  |
| 𝐺
3 |


---
## Page 80
---


Compute: 8
Activation Checkpointing
Current Memory: 1
Peak Memory: 4
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Q: How much compute and memory does
𝐴 𝐺
1 1
→ ←
this take? Assume each 𝐹 and 𝐹 is O(1)
𝑖 𝑖
compute and memory.
Stanford CS231n 10th Anniversary Lecture 11 - 80 May 6, 2025

[Page contains 3 table(s)]


### Table 1

| Compute: 8
Activation Checkpointing
Current Memory: 1
Peak Memory: 4
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Q: How much compute and memory does
𝐴 𝐺
1 1
→ ←
this take? Assume each 𝐹 and 𝐹 is O(1)
𝑖 𝑖
compute and memory. |
| Stanford CS231n 10th Anniversary Lecture 11 - 80 May 6, 2025 |


### Table 2

| 𝐴
4
𝐴
3
𝐴
2
𝐴
1 |  | 𝐺
4
𝐺
3
𝐺
2 |
|  |  | 𝐺
1 |


### Table 3

| 𝐺
4 |
|  |
| 𝐺
3 |


---
## Page 81
---


Compute: 8
Activation Checkpointing
Current Memory: 1
Peak Memory: 4
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Stanford CS231n 10th Anniversary Lecture 11 - 81 May 6, 2025

[Page contains 3 table(s)]


### Table 1

| Compute: 8
Activation Checkpointing
Current Memory: 1
Peak Memory: 4
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1 |
| Stanford CS231n 10th Anniversary Lecture 11 - 81 May 6, 2025 |


### Table 2

| 𝐴
4
𝐴
3
𝐴
2
𝐴
1 |  | 𝐺
4
𝐺
3
𝐺
2 |
|  |  | 𝐺
1 |


### Table 3

| 𝐺
4 |
|  |
| 𝐺
3 |


---
## Page 82
---


Compute: 8
Activation Checkpointing
Current Memory: 1
Peak Memory: 4
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass
Stanford CS231n 10th Anniversary Lecture 11 - 82 May 6, 2025

[Page contains 3 table(s)]


### Table 1

| Compute: 8
Activation Checkpointing
Current Memory: 1
Peak Memory: 4
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass |
| Stanford CS231n 10th Anniversary Lecture 11 - 82 May 6, 2025 |


### Table 2

| 𝐴
4
𝐴
3
𝐴
2
𝐴
1 |  | 𝐺
4
𝐺
3
𝐺
2 |
|  |  | 𝐺
1 |


### Table 3

| 𝐺
4 |
|  |
| 𝐺
3 |


---
## Page 83
---


Compute: 1
Activation Checkpointing
Current Memory: 1
Peak Memory: 1
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass
Stanford CS231n 10th Anniversary Lecture 11 - 83 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Compute: 1
Activation Checkpointing
Current Memory: 1
Peak Memory: 1
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass |
| Stanford CS231n 10th Anniversary Lecture 11 - 83 May 6, 2025 |


### Table 2

| 𝐴
4
𝐴
3
𝐴
2 |  | 𝐺
4
𝐺
3
𝐺
2
𝐺
1 |
|  | 𝐴
1 |  |


---
## Page 84
---


Compute: 2
Activation Checkpointing
Current Memory: 1
Peak Memory: 1
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass
Stanford CS231n 10th Anniversary Lecture 11 - 84 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Compute: 2
Activation Checkpointing
Current Memory: 1
Peak Memory: 1
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass |
| Stanford CS231n 10th Anniversary Lecture 11 - 84 May 6, 2025 |


### Table 2

| 𝐴
4
𝐴
3 |  |  | 𝐺
4
𝐺
3
𝐺
2
𝐺
1 |
|  |  | 𝐴
2 |  |
|  | 𝐴
1 |  |  |


---
## Page 85
---


Compute: 3
Activation Checkpointing
Current Memory: 1
Peak Memory: 1
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass
Stanford CS231n 10th Anniversary Lecture 11 - 85 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Compute: 3
Activation Checkpointing
Current Memory: 1
Peak Memory: 1
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass |
| Stanford CS231n 10th Anniversary Lecture 11 - 85 May 6, 2025 |


### Table 2

| 𝐴
4 |  |  | 𝐺
4
𝐺
3
𝐺
2
𝐺
1 |
|  |  | 𝐴
3 |  |
|  | 𝐴
2
𝐴
1 |  |  |


---
## Page 86
---


Compute: 4
Activation Checkpointing
Current Memory: 1
Peak Memory: 1
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass
Stanford CS231n 10th Anniversary Lecture 11 - 86 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Compute: 4
Activation Checkpointing
Current Memory: 1
Peak Memory: 1
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass |
| Stanford CS231n 10th Anniversary Lecture 11 - 86 May 6, 2025 |


### Table 2

|  |  | 𝐺
4
𝐺
3
𝐺
2
𝐺
1 |
|  | 𝐴
4 |  |
| 𝐴
3
𝐴
2
𝐴
1 |  |  |


---
## Page 87
---


Compute: 5
Activation Checkpointing
Current Memory: 1
Peak Memory: 1
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass
Stanford CS231n 10th Anniversary Lecture 11 - 87 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Compute: 5
Activation Checkpointing
Current Memory: 1
Peak Memory: 1
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass |
| Stanford CS231n 10th Anniversary Lecture 11 - 87 May 6, 2025 |


### Table 2

| 𝐴
4
𝐴
3
𝐴
2
𝐴
1 |  |  |  |
|  | 𝐴
4 |  | 𝐺
4 |
|  |  | 𝐺
3
𝐺
2
𝐺
1 |  |


---
## Page 88
---


Compute: 6
Activation Checkpointing
Current Memory: 2
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass
Stanford CS231n 10th Anniversary Lecture 11 - 88 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Compute: 6
Activation Checkpointing
Current Memory: 2
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass |
| Stanford CS231n 10th Anniversary Lecture 11 - 88 May 6, 2025 |


### Table 2

| 𝐴
4
𝐴
3
𝐴
2 |  |  |  |
|  | 𝐴
4 |  | 𝐺
4 |
|  |  | 𝐺
3
𝐺
2
𝐺
1 |  |
|  | 𝐴
1 |  |  |


---
## Page 89
---


Compute: 7
Activation Checkpointing
Current Memory: 2
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass
Stanford CS231n 10th Anniversary Lecture 11 - 89 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Compute: 7
Activation Checkpointing
Current Memory: 2
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass |
| Stanford CS231n 10th Anniversary Lecture 11 - 89 May 6, 2025 |


### Table 2

| 𝐴
4
𝐴
3 |  |  |  |
|  | 𝐴
4 |  | 𝐺
4 |
|  |  | 𝐺
3
𝐺
2
𝐺
1 |  |
|  | 𝐴
2 |  |  |
| 𝐴
1 |  |  |  |


---
## Page 90
---


Compute: 8
Activation Checkpointing
Current Memory: 2
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass
Stanford CS231n 10th Anniversary Lecture 11 - 90 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Compute: 8
Activation Checkpointing
Current Memory: 2
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass |
| Stanford CS231n 10th Anniversary Lecture 11 - 90 May 6, 2025 |


### Table 2

| 𝐴
4 |  |  |  |
|  | 𝐴
4 |  | 𝐺
4 |
|  |  | 𝐺
3
𝐺
2
𝐺
1 |  |
|  | 𝐴
3 |  |  |
| 𝐴
2
𝐴
1 |  |  |  |


---
## Page 91
---


Compute: 9
Activation Checkpointing
Current Memory: 1
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass
Stanford CS231n 10th Anniversary Lecture 11 - 91 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Compute: 9
Activation Checkpointing
Current Memory: 1
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass |
| Stanford CS231n 10th Anniversary Lecture 11 - 91 May 6, 2025 |


### Table 2

| 𝐴
4 |  |  | 𝐺
4 |
| 𝐴
3
𝐴
2
𝐴
1 | 𝐴
3 |  | 𝐺
3 |
|  |  | 𝐺
2
𝐺
1 |  |


---
## Page 92
---


Compute: 10
Activation Checkpointing
Current Memory: 2
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass
Stanford CS231n 10th Anniversary Lecture 11 - 92 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Compute: 10
Activation Checkpointing
Current Memory: 2
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass |
| Stanford CS231n 10th Anniversary Lecture 11 - 92 May 6, 2025 |


### Table 2

| 𝐴
4 |  |  | 𝐺
4 |
| 𝐴
3
𝐴
2 | 𝐴
3 |  | 𝐺
3 |
|  |  | 𝐺
2
𝐺
1 |  |
|  | 𝐴
1 |  |  |


---
## Page 93
---


Compute: 11
Activation Checkpointing
Current Memory: 2
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass
Stanford CS231n 10th Anniversary Lecture 11 - 93 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Compute: 11
Activation Checkpointing
Current Memory: 2
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass |
| Stanford CS231n 10th Anniversary Lecture 11 - 93 May 6, 2025 |


### Table 2

|  |  | 𝐺
4 |
| 𝐴
4 |  |  |
|  |  |  |
| 𝐴
3 |  | 𝐺
3 |
|  | 𝐺
2
𝐺
1 |  |
| 𝐴
2 |  |  |
|  |  |  |
| 𝐴
1 |  |  |


---
## Page 94
---


Compute: 12
Activation Checkpointing
Current Memory: 1
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass
Stanford CS231n 10th Anniversary Lecture 11 - 94 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Compute: 12
Activation Checkpointing
Current Memory: 1
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass |
| Stanford CS231n 10th Anniversary Lecture 11 - 94 May 6, 2025 |


### Table 2

|  |  | 𝐺
4
𝐺
3 |
| 𝐴
4 |  |  |
|  |  |  |
| 𝐴
3 |  |  |
|  |  |  |
| 𝐴
2 |  | 𝐺
2 |
|  |  |  |
|  | 𝐺
1 |  |
| 𝐴
1 |  |  |


---
## Page 95
---


Compute: 13
Activation Checkpointing
Current Memory: 2
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass
Stanford CS231n 10th Anniversary Lecture 11 - 95 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Compute: 13
Activation Checkpointing
Current Memory: 2
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass |
| Stanford CS231n 10th Anniversary Lecture 11 - 95 May 6, 2025 |


### Table 2

|  |  | 𝐺
4
𝐺
3 |
| 𝐴
4 |  |  |
|  |  |  |
| 𝐴
3 |  |  |
|  |  |  |
| 𝐴
2 |  | 𝐺
2 |
|  |  |  |
|  | 𝐺
1 |  |
| 𝐴
1 |  |  |


---
## Page 96
---


Compute: 14
Activation Checkpointing
Current Memory: 1
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass
Stanford CS231n 10th Anniversary Lecture 11 - 96 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Compute: 14
Activation Checkpointing
Current Memory: 1
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Idea: Recompute activations
during the backward pass |
| Stanford CS231n 10th Anniversary Lecture 11 - 96 May 6, 2025 |


### Table 2

|  |  | 𝐺
4
𝐺
3
𝐺
2 |
| 𝐴
4 |  |  |
|  |  |  |
| 𝐴
3 |  |  |
|  |  |  |
| 𝐴
2 |  |  |
|  |  |  |
|  |  |  |
| 𝐴
1 |  | 𝐺
1 |


---
## Page 97
---


Compute: 14
Activation Checkpointing
Current Memory: 1
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Full Recomputation: O(N2) compute, O(1) memory
Idea: Recompute activations
during the backward pass
Stanford CS231n 10th Anniversary Lecture 11 - 97 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Compute: 14
Activation Checkpointing
Current Memory: 1
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Full Recomputation: O(N2) compute, O(1) memory
Idea: Recompute activations
during the backward pass |
| Stanford CS231n 10th Anniversary Lecture 11 - 97 May 6, 2025 |


### Table 2

|  |  | 𝐺
4
𝐺
3
𝐺
2 |
| 𝐴
4 |  |  |
|  |  |  |
| 𝐴
3 |  |  |
|  |  |  |
| 𝐴
2 |  |  |
|  |  |  |
|  |  |  |
| 𝐴
1 |  | 𝐺
1 |


---
## Page 98
---


Compute: 14
Activation Checkpointing
Current Memory: 2
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Full Recomputation: O(N2) compute, O(1) memory
Idea: Recompute activations
Problem: N2 compute is bad!
during the backward pass
Stanford CS231n 10th Anniversary Lecture 11 - 98 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Compute: 14
Activation Checkpointing
Current Memory: 2
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Full Recomputation: O(N2) compute, O(1) memory
Idea: Recompute activations
Problem: N2 compute is bad!
during the backward pass |
| Stanford CS231n 10th Anniversary Lecture 11 - 98 May 6, 2025 |


### Table 2

|  |  | 𝐺
4
𝐺
3
𝐺
2 |
| 𝐴
4 |  |  |
|  |  |  |
| 𝐴
3 |  |  |
|  |  |  |
| 𝐴
2 |  |  |
|  |  |  |
|  |  |  |
| 𝐴
1 |  | 𝐺
1 |


---
## Page 99
---


Compute: 14
Activation Checkpointing
Current Memory: 2
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Full Recomputation: O(N2) compute, O(1) memory
Idea: Don’t recompute everything;
Problem: N2 compute is bad!
save a checkpoint every C layers
Stanford CS231n 10th Anniversary Lecture 11 - 99 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Compute: 14
Activation Checkpointing
Current Memory: 2
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Full Recomputation: O(N2) compute, O(1) memory
Idea: Don’t recompute everything;
Problem: N2 compute is bad!
save a checkpoint every C layers |
| Stanford CS231n 10th Anniversary Lecture 11 - 99 May 6, 2025 |


### Table 2

|  |  | 𝐺
4
𝐺
3
𝐺
2 |
| 𝐴
4 |  |  |
|  |  |  |
| 𝐴
3 |  |  |
|  |  |  |
| 𝐴
2 |  |  |
|  |  |  |
|  |  |  |
| 𝐴
1 |  | 𝐺
1 |


---
## Page 100
---


Compute: 14
Activation Checkpointing
Current Memory: 2
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Full Recomputation: O(N2) compute, O(1) memory
C checkpoints: O(N2/C) compute, O(C) memory
Idea: Don’t recompute everything;
save a checkpoint every C layers
Stanford CS231n 10th Anniversary Lecture 11 - 100 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Compute: 14
Activation Checkpointing
Current Memory: 2
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Full Recomputation: O(N2) compute, O(1) memory
C checkpoints: O(N2/C) compute, O(C) memory
Idea: Don’t recompute everything;
save a checkpoint every C layers |
| Stanford CS231n 10th Anniversary Lecture 11 - 100 May 6, 2025 |


---
## Page 101
---


Compute: 14
Activation Checkpointing
Current Memory: 2
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Full Recomputation: O(N2) compute, O(1) memory
C checkpoints: O(N2/C) compute, O(C) memory
Idea: Don’t recompute everything;
√𝑁 checkpoints: O(N √𝑁) compute, O(√𝑁) memory save a checkpoint every C layers
Stanford CS231n 10th Anniversary Lecture 11 - 101 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Compute: 14
Activation Checkpointing
Current Memory: 2
Peak Memory: 2
Each layer in the network is two functions:
𝐴 𝐺
4 4
Forward: Compute next-layer activations
→
𝐴 = 𝐹 𝐴
𝑖+1 𝑖 𝑖 𝐴 𝐺
3 3
Backward: Compute prev-layer gradients
← 𝐴 𝐺
𝐺 = 𝐹 (𝐴 , 𝐺 )
𝑖 𝑖 𝑖 𝑖+1 2 2
Forward+backward: O(N) compute, O(N) memory
𝐴 𝐺
1 1
Full Recomputation: O(N2) compute, O(1) memory
C checkpoints: O(N2/C) compute, O(C) memory
Idea: Don’t recompute everything;
√𝑁 checkpoints: O(N √𝑁) compute, O(√𝑁) memory save a checkpoint every C layers |
| Stanford CS231n 10th Anniversary Lecture 11 - 101 May 6, 2025 |


---
## Page 102
---


How to train on lots of GPUs
HSDP + Activation checkpointing can take you a long way!
Scaling recipe:
1. Use data parallelism up to ~128 GPUs, models with ~1B params
2. Always set per-GPU batch size to max out GPU memory
3. If your model is >1B params, consider FSDP
4. Add activation checkpointing to fit larger batches per GPU
5. If you have >256 GPUs, consider HSDP
6. If you have >1K GPUs, models >50B params, or sequence lengths
> 16K then use more advanced strategies (CP, PP, TP)
Problem: Lots of knobs to tune! How should we set them?
Solution: Maximize Model Flops Utilization (MFU)
Stanford CS231n 10th Anniversary Lecture 11 - 102 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| How to train on lots of GPUs
HSDP + Activation checkpointing can take you a long way!
Scaling recipe:
1. Use data parallelism up to ~128 GPUs, models with ~1B params
2. Always set per-GPU batch size to max out GPU memory
3. If your model is >1B params, consider FSDP
4. Add activation checkpointing to fit larger batches per GPU
5. If you have >256 GPUs, consider HSDP
6. If you have >1K GPUs, models >50B params, or sequence lengths
> 16K then use more advanced strategies (CP, PP, TP)
Problem: Lots of knobs to tune! How should we set them?
Solution: Maximize Model Flops Utilization (MFU) |
| Stanford CS231n 10th Anniversary Lecture 11 - 102 May 6, 2025 |


---
## Page 103
---


Hardware FLOPs Utilization (HFU)
Recall: H100 can theoretically do
989.4 TFLOP/sec of 16-bit matrix
multiplies on Tensor Cores
Question: How much throughput
can we see in practice?
Chowdheryet al, “PaLM: Scaling Language Modeling with Pathways”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 11 - 103 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Hardware FLOPs Utilization (HFU)
Recall: H100 can theoretically do
989.4 TFLOP/sec of 16-bit matrix
multiplies on Tensor Cores
Question: How much throughput
can we see in practice?
Chowdheryet al, “PaLM: Scaling Language Modeling with Pathways”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 11 - 103 May 6, 2025 |


---
## Page 104
---


Hardware FLOPs Utilization (HFU)
Recall: H100 can theoretically do
989.4 TFLOP/sec of 16-bit matrix
multiplies on Tensor Cores
Question: How much throughput
can we see in practice?
Hardware FLOPs Utilization (HFU):
The fraction of theoretical matmul
performance we actually achieve
Chowdheryet al, “PaLM: Scaling Language Modeling with Pathways”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 11 - 104 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Hardware FLOPs Utilization (HFU)
Recall: H100 can theoretically do
989.4 TFLOP/sec of 16-bit matrix
multiplies on Tensor Cores
Question: How much throughput
can we see in practice?
Hardware FLOPs Utilization (HFU):
The fraction of theoretical matmul
performance we actually achieve
Chowdheryet al, “PaLM: Scaling Language Modeling with Pathways”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 11 - 104 May 6, 2025 |


---
## Page 105
---


Hardware FLOPs Utilization (HFU)
Recall: H100 can theoretically do
Benchmark for
989.4 TFLOP/sec of 16-bit matrix
multiplies on Tensor Cores the best-case
scenario: only
Question: How much throughput matrix multiply
can we see in practice?
Hardware FLOPs Utilization (HFU): Run this with CUDA_LAUNCH_BLOCKING=1,
otherwise GPU kernels launch async and
The fraction of theoretical matmul
measurements are wrong
performance we actually achieve
Chowdheryet al, “PaLM: Scaling Language Modeling with Pathways”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 11 - 105 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Hardware FLOPs Utilization (HFU)
Recall: H100 can theoretically do
Benchmark for
989.4 TFLOP/sec of 16-bit matrix
multiplies on Tensor Cores the best-case
scenario: only
Question: How much throughput matrix multiply
can we see in practice?
Hardware FLOPs Utilization (HFU): Run this with CUDA_LAUNCH_BLOCKING=1,
otherwise GPU kernels launch async and
The fraction of theoretical matmul
measurements are wrong
performance we actually achieve
Chowdheryet al, “PaLM: Scaling Language Modeling with Pathways”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 11 - 105 May 6, 2025 |


[Page contains 1 image(s)]


---
## Page 106
---


Hardware FLOPs Utilization (HFU)
Recall: H100 can theoretically do
Benchmark for
989.4 TFLOP/sec of 16-bit matrix
multiplies on Tensor Cores the best-case
scenario: only
Question: How much throughput matrix multiply
can we see in practice?
Hardware FLOPs Utilization (HFU):
Matmul HFU on H100
The fraction of theoretical matmul
100
Large matrix
performance we actually achieve
80
multiply gets
)%
60
(
U
~80% HFU F 40
H
20
on H100 0
0 10000 20000 30000 40000
Matrix Size
Chowdheryet al, “PaLM: Scaling Language Modeling with Pathways”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 11 - 106 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Hardware FLOPs Utilization (HFU)
Recall: H100 can theoretically do
Benchmark for
989.4 TFLOP/sec of 16-bit matrix
multiplies on Tensor Cores the best-case
scenario: only
Question: How much throughput matrix multiply
can we see in practice?
Hardware FLOPs Utilization (HFU):
Matmul HFU on H100
The fraction of theoretical matmul
100
Large matrix
performance we actually achieve
80
)%
multiply gets 60
(
U
~80% HFU F 40
H
20
on H100 0
0 10000 20000 30000 40000
Matrix Size
Chowdheryet al, “PaLM: Scaling Language Modeling with Pathways”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 11 - 106 May 6, 2025 |


### Table 2

|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |


[Page contains 1 image(s)]


---
## Page 107
---


Hardware FLOPs Utilization (HFU)
Recall: H100 can theoretically do
Benchmark for
989.4 TFLOP/sec of 16-bit matrix
multiplies on Tensor Cores the best-case
scenario: only
Question: How much throughput matrix multiply
can we see in practice?
Hardware FLOPs Utilization (HFU):
Matmul HFU on H100
The fraction of theoretical matmul
100
Large matrix
performance we actually achieve
80
multiply gets
)%
60
(
U
Problem: HFU does not account for ~80% HFU F 40
H
20
activation checkpointing or “helper” on H100 0
0 10000 20000 30000 40000
computation like data augmentation,
Matrix Size
optimizer, preprocessing
Chowdheryet al, “PaLM: Scaling Language Modeling with Pathways”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 11 - 107 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Hardware FLOPs Utilization (HFU)
Recall: H100 can theoretically do
Benchmark for
989.4 TFLOP/sec of 16-bit matrix
multiplies on Tensor Cores the best-case
scenario: only
Question: How much throughput matrix multiply
can we see in practice?
Hardware FLOPs Utilization (HFU):
Matmul HFU on H100
The fraction of theoretical matmul
100
Large matrix
performance we actually achieve
80
)%
multiply gets 60
(
U
Problem: HFU does not account for ~80% HFU F 40
H
20
activation checkpointing or “helper” on H100 0
0 10000 20000 30000 40000
computation like data augmentation,
Matrix Size
optimizer, preprocessing
Chowdheryet al, “PaLM: Scaling Language Modeling with Pathways”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 11 - 107 May 6, 2025 |


### Table 2

|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |


[Page contains 1 image(s)]


---
## Page 108
---


Model FLOPs Utilization (MFU)
Idea: What fraction of the GPU’s theoretical peak
FLOPs is being used for “useful” model computation?
1. Compute FLOP = total number of matrix
theoretical
multiply FLOPs in the forward + backward pass
(can approximate backward = 2x forward)
(Ignore nonlinearities, normalization, elementwise
ops like residuals. They will run on FP32 cores)
2. Look up FLOP/sec = theoretical max
theoretical
throughput of your device (H100: 989 TFLOP/sec)
3. Compute t = FLOP / FLOP/sec
theoretical theoretical theoretical
4. Measure t = Actual time for a full iteration of
actual
data loading, forward, backward, optimizer step
5. MFU = t / t
theoretical actual
Chowdheryet al, “PaLM: Scaling Language Modeling with Pathways”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 11 - 108 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Model FLOPs Utilization (MFU)
Idea: What fraction of the GPU’s theoretical peak
FLOPs is being used for “useful” model computation?
1. Compute FLOP = total number of matrix
theoretical
multiply FLOPs in the forward + backward pass
(can approximate backward = 2x forward)
(Ignore nonlinearities, normalization, elementwise
ops like residuals. They will run on FP32 cores)
2. Look up FLOP/sec = theoretical max
theoretical
throughput of your device (H100: 989 TFLOP/sec)
3. Compute t = FLOP / FLOP/sec
theoretical theoretical theoretical
4. Measure t = Actual time for a full iteration of
actual
data loading, forward, backward, optimizer step
5. MFU = t / t
theoretical actual
Chowdheryet al, “PaLM: Scaling Language Modeling with Pathways”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 11 - 108 May 6, 2025 |


---
## Page 109
---


Model FLOPs Utilization (MFU)
Idea: What fraction of the GPU’s theoretical peak
FLOPs is being used for “useful” model computation?
1. Compute FLOP = total number of matrix
theoretical
multiply FLOPs in the forward + backward pass
Example: Wide
(can approximate backward = 2x forward)
MLP with big
(Ignore nonlinearities, normalization, elementwise
batch size gets
ops like residuals. They will run on FP32 cores)
~49% MFU on
2. Look up FLOP/sec = theoretical max
theoretical H100
throughput of your device (H100: 989 TFLOP/sec)
3. Compute t = FLOP / FLOP/sec
theoretical theoretical theoretical
4. Measure t = Actual time for a full iteration of
actual
data loading, forward, backward, optimizer step
5. MFU = t / t
theoretical actual
Chowdheryet al, “PaLM: Scaling Language Modeling with Pathways”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 11 - 109 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Model FLOPs Utilization (MFU)
Idea: What fraction of the GPU’s theoretical peak
FLOPs is being used for “useful” model computation?
1. Compute FLOP = total number of matrix
theoretical
multiply FLOPs in the forward + backward pass
Example: Wide
(can approximate backward = 2x forward)
MLP with big
(Ignore nonlinearities, normalization, elementwise
batch size gets
ops like residuals. They will run on FP32 cores)
~49% MFU on
2. Look up FLOP/sec = theoretical max
theoretical H100
throughput of your device (H100: 989 TFLOP/sec)
3. Compute t = FLOP / FLOP/sec
theoretical theoretical theoretical
4. Measure t = Actual time for a full iteration of
actual
data loading, forward, backward, optimizer step
5. MFU = t / t
theoretical actual
Chowdheryet al, “PaLM: Scaling Language Modeling with Pathways”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 11 - 109 May 6, 2025 |


[Page contains 1 image(s)]


---
## Page 110
---


Model FLOPs Utilization (MFU)
Idea: What fraction of the GPU’s theoretical peak
FLOPs is being used for “useful” model computation?
1. Compute FLOP = total number of matrix
theoretical
multiply FLOPs in the forward + backward pass
Example: Wide
(can approximate backward = 2x forward)
MLP with big
(Ignore nonlinearities, normalization, elementwise
batch size gets
ops like residuals. They will run on FP32 cores)
~49% MFU on
2. Look up FLOP/sec = theoretical max
theoretical H100
throughput of your device (H100: 989 TFLOP/sec)
3. Compute t = FLOP / FLOP/sec
theoretical theoretical theoretical
4. Measure t = Actual time for a full iteration of
actual
data loading, forward, backward, optimizer step
5. MFU = t / t
theoretical actual
Optimize distributed training setup to maximize MFU!
Chowdheryet al, “PaLM: Scaling Language Modeling with Pathways”, arXiv2022
Stanford CS231n 10th Anniversary Lecture 11 - 110 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Model FLOPs Utilization (MFU)
Idea: What fraction of the GPU’s theoretical peak
FLOPs is being used for “useful” model computation?
1. Compute FLOP = total number of matrix
theoretical
multiply FLOPs in the forward + backward pass
Example: Wide
(can approximate backward = 2x forward)
MLP with big
(Ignore nonlinearities, normalization, elementwise
batch size gets
ops like residuals. They will run on FP32 cores)
~49% MFU on
2. Look up FLOP/sec = theoretical max
theoretical H100
throughput of your device (H100: 989 TFLOP/sec)
3. Compute t = FLOP / FLOP/sec
theoretical theoretical theoretical
4. Measure t = Actual time for a full iteration of
actual
data loading, forward, backward, optimizer step
5. MFU = t / t
theoretical actual
Optimize distributed training setup to maximize MFU!
Chowdheryet al, “PaLM: Scaling Language Modeling with Pathways”, arXiv2022 |
| Stanford CS231n 10th Anniversary Lecture 11 - 110 May 6, 2025 |


[Page contains 1 image(s)]


---
## Page 111
---


Model FLOPs Utilization (MFU)
Idea: What fraction of the GPU’s theoretical peak
FLOPs is being used for “useful” model computation?
MFU >30% is good, >40% is excellent
Stanford CS231n 10th Anniversary Lecture 11 - 111 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Model FLOPs Utilization (MFU)
Idea: What fraction of the GPU’s theoretical peak
FLOPs is being used for “useful” model computation?
MFU >30% is good, >40% is excellent |
| Stanford CS231n 10th Anniversary Lecture 11 - 111 May 6, 2025 |


---
## Page 112
---


Model FLOPs Utilization (MFU)
Idea: What fraction of the GPU’s theoretical peak
FLOPs is being used for “useful” model computation?
MFU >30% is good, >40% is excellent
Chowdheryet al, “PaLM: Scaling Language Modeling with Pathways”, arXiv2022
Example: Llama3-405B
training on H100 GPUs
Llama Team, “The Llama3 Herd of Models”, arXiv2024
Stanford CS231n 10th Anniversary Lecture 11 - 112 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Model FLOPs Utilization (MFU)
Idea: What fraction of the GPU’s theoretical peak
FLOPs is being used for “useful” model computation?
MFU >30% is good, >40% is excellent
Chowdheryet al, “PaLM: Scaling Language Modeling with Pathways”, arXiv2022
Example: Llama3-405B
training on H100 GPUs
Llama Team, “The Llama3 Herd of Models”, arXiv2024 |
| Stanford CS231n 10th Anniversary Lecture 11 - 112 May 6, 2025 |


[Page contains 3 image(s)]


---
## Page 113
---


Model FLOPs Utilization (MFU)
Idea: What fraction of the GPU’s theoretical peak
FLOPs is being used for “useful” model computation?
MFU >30% is good, >40% is excellent
More recent devices
sometimes get worse MFU
since their peak FLOPs
increases much faster than
Chowdheryet al, “PaLM: Scaling Language Modeling with Pathways”, arXiv2022
their memory bandwidth
A100 => H100:
Example: Llama3-405B
3.1x FLOPs
training on H100 GPUs
2.1x memory bandwidth
Llama Team, “The Llama3 Herd of Models”, arXiv2024
Stanford CS231n 10th Anniversary Lecture 11 - 113 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Model FLOPs Utilization (MFU)
Idea: What fraction of the GPU’s theoretical peak
FLOPs is being used for “useful” model computation?
MFU >30% is good, >40% is excellent
More recent devices
sometimes get worse MFU
since their peak FLOPs
increases much faster than
Chowdheryet al, “PaLM: Scaling Language Modeling with Pathways”, arXiv2022
their memory bandwidth
A100 => H100:
Example: Llama3-405B
3.1x FLOPs
training on H100 GPUs
2.1x memory bandwidth
Llama Team, “The Llama3 Herd of Models”, arXiv2024 |
| Stanford CS231n 10th Anniversary Lecture 11 - 113 May 6, 2025 |


[Page contains 3 image(s)]


---
## Page 114
---


How to train on lots of GPUs
A model with L layers operates on tensors of shape (Batch, Sequence, Dim)
Data Parallelism (DP) Context Parallelism (CP)
Split on Batch dimension Split on Sequence dimension
Pipeline Parallelism (PP) Tensor Parallelism (TP)
Split on L dimension Split on Dim dimension
Stanford CS231n 10th Anniversary Lecture 11 - 114 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| How to train on lots of GPUs
A model with L layers operates on tensors of shape (Batch, Sequence, Dim)
Data Parallelism (DP) Context Parallelism (CP)
Split on Batch dimension Split on Sequence dimension
Pipeline Parallelism (PP) Tensor Parallelism (TP)
Split on L dimension Split on Dim dimension |
| Stanford CS231n 10th Anniversary Lecture 11 - 114 May 6, 2025 |


---
## Page 115
---


How to train on lots of GPUs
A model with L layers operates on tensors of shape (Batch, Sequence, Dim)
Data Parallelism (DP) Context Parallelism (CP)
Split on Batch dimension Split on Sequence dimension
Pipeline Parallelism (PP) Tensor Parallelism (TP)
Split on L dimension Split on Dim dimension
Stanford CS231n 10th Anniversary Lecture 11 - 115 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| How to train on lots of GPUs
A model with L layers operates on tensors of shape (Batch, Sequence, Dim)
Data Parallelism (DP) Context Parallelism (CP)
Split on Batch dimension Split on Sequence dimension
Pipeline Parallelism (PP) Tensor Parallelism (TP)
Split on L dimension Split on Dim dimension |
| Stanford CS231n 10th Anniversary Lecture 11 - 115 May 6, 2025 |


---
## Page 116
---


Context Parallelism (CP)
GPU 1 GPU 2
(Usually for Transformers)
Idea: Transformers operate on L-length sequences.
Use multiple GPUs to process a single long sequence
GPU 1 GPU 2
Stanford CS231n 10th Anniversary Lecture 11 - 116 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Context Parallelism (CP)
GPU 1 GPU 2
(Usually for Transformers)
Idea: Transformers operate on L-length sequences.
Use multiple GPUs to process a single long sequence
GPU 1 GPU 2 |
| Stanford CS231n 10th Anniversary Lecture 11 - 116 May 6, 2025 |


[Page contains 1 image(s)]


---
## Page 117
---


Context Parallelism (CP)
GPU 1 GPU 2
(Usually for Transformers)
Idea: Transformers operate on L-length sequences.
Use multiple GPUs to process a single long sequence
Normalization, residual connections: Easy, they
have no weights and trivially parallelizable
GPU 1 GPU 2
Stanford CS231n 10th Anniversary Lecture 11 - 117 May 6, 2025

[Page contains 4 table(s)]


### Table 1

| Context Parallelism (CP)
GPU 1 GPU 2
(Usually for Transformers)
Idea: Transformers operate on L-length sequences.
Use multiple GPUs to process a single long sequence
Normalization, residual connections: Easy, they
have no weights and trivially parallelizable
GPU 1 GPU 2 |
| Stanford CS231n 10th Anniversary Lecture 11 - 117 May 6, 2025 |


### Table 2

|  |  |


### Table 3

|  |  |


### Table 4

|  |  |


[Page contains 1 image(s)]


---
## Page 118
---


Context Parallelism (CP)
GPU 1 GPU 2
(Usually for Transformers)
Idea: Transformers operate on L-length sequences.
Use multiple GPUs to process a single long sequence
Normalization, residual connections: Easy, they
have no weights and trivially parallelizable
MLP: Trivially parallelizable, but has weights. Each
GPU keeps a copy of the weights and communicates
gradients like in DP
GPU 1 GPU 2
Stanford CS231n 10th Anniversary Lecture 11 - 118 May 6, 2025

[Page contains 5 table(s)]


### Table 1

| Context Parallelism (CP)
GPU 1 GPU 2
(Usually for Transformers)
Idea: Transformers operate on L-length sequences.
Use multiple GPUs to process a single long sequence
Normalization, residual connections: Easy, they
have no weights and trivially parallelizable
MLP: Trivially parallelizable, but has weights. Each
GPU keeps a copy of the weights and communicates
gradients like in DP
GPU 1 GPU 2 |
| Stanford CS231n 10th Anniversary Lecture 11 - 118 May 6, 2025 |


### Table 2

|  |  |


### Table 3

|  |  |


### Table 4

|  |  |


### Table 5

|  |  |


[Page contains 1 image(s)]


---
## Page 119
---


Context Parallelism (CP)
GPU 1 GPU 2
(Usually for Transformers)
Idea: Transformers operate on L-length sequences.
Use multiple GPUs to process a single long sequence
Normalization, residual connections: Easy, they
have no weights and trivially parallelizable
MLP: Trivially parallelizable, but has weights. Each
GPU keeps a copy of the weights and communicates
gradients like in DP
Attention: More complex, need to dig in
GPU 1 GPU 2
Stanford CS231n 10th Anniversary Lecture 11 - 119 May 6, 2025

[Page contains 4 table(s)]


### Table 1

| Context Parallelism (CP)
GPU 1 GPU 2
(Usually for Transformers)
Idea: Transformers operate on L-length sequences.
Use multiple GPUs to process a single long sequence
Normalization, residual connections: Easy, they
have no weights and trivially parallelizable
MLP: Trivially parallelizable, but has weights. Each
GPU keeps a copy of the weights and communicates
gradients like in DP
Attention: More complex, need to dig in
GPU 1 GPU 2 |
| Stanford CS231n 10th Anniversary Lecture 11 - 119 May 6, 2025 |


### Table 2

|  |  |


### Table 3

|  |  |


### Table 4

|  |  |
|  |  |
|  |  |


[Page contains 1 image(s)]


---
## Page 120
---


Context Parallelism (CP)
(Usually for Transformers)
Idea: Transformers operate on L-length sequences.
Use multiple GPUs to process a single long sequence
Stanford CS231n 10th Anniversary Lecture 11 - 120 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Context Parallelism (CP)
(Usually for Transformers)
Idea: Transformers operate on L-length sequences.
Use multiple GPUs to process a single long sequence |
| Stanford CS231n 10th Anniversary Lecture 11 - 120 May 6, 2025 |


[Page contains 1 image(s)]


---
## Page 121
---


Context Parallelism (CP)
(Usually for Transformers)
Idea: Transformers operate on L-length sequences.
Use multiple GPUs to process a single long sequence
QKV Projection: Same as MLP, parallelize over the
sequence and sync gradients as in DP
Stanford CS231n 10th Anniversary Lecture 11 - 121 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Context Parallelism (CP)
(Usually for Transformers)
Idea: Transformers operate on L-length sequences.
Use multiple GPUs to process a single long sequence
QKV Projection: Same as MLP, parallelize over the
sequence and sync gradients as in DP |
| Stanford CS231n 10th Anniversary Lecture 11 - 121 May 6, 2025 |


[Page contains 1 image(s)]


---
## Page 122
---


Context Parallelism (CP)
(Usually for Transformers)
Idea: Transformers operate on S-length sequences.
Use multiple GPUs to process a single long sequence
QKV Projection: Same as MLP, parallelize over the
sequence and sync gradients as in DP
Attention operator: Hardest to parallelize
Stanford CS231n 10th Anniversary Lecture 11 - 122 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Context Parallelism (CP)
(Usually for Transformers)
Idea: Transformers operate on S-length sequences.
Use multiple GPUs to process a single long sequence
QKV Projection: Same as MLP, parallelize over the
sequence and sync gradients as in DP
Attention operator: Hardest to parallelize |
| Stanford CS231n 10th Anniversary Lecture 11 - 122 May 6, 2025 |


[Page contains 1 image(s)]


---
## Page 123
---


Context Parallelism (CP)
(Usually for Transformers)
Idea: Transformers operate on S-length sequences.
Use multiple GPUs to process a single long sequence
QKV Projection: Same as MLP, parallelize over the
sequence and sync gradients as in DP
Attention operator: Hardest to parallelize
(Option 1) Ring Attention: Divide into blocks and
distribute over GPUs. Inner loop over keys/values,
outer loop over queries. Complex to implement but
can scale to very long sequences.
Liu et al, ”Ring Attention with Blockwise
Transformers for Near-Infinite Context”, arXiv2023
Stanford CS231n 10th Anniversary Lecture 11 - 123 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Context Parallelism (CP)
(Usually for Transformers)
Idea: Transformers operate on S-length sequences.
Use multiple GPUs to process a single long sequence
QKV Projection: Same as MLP, parallelize over the
sequence and sync gradients as in DP
Attention operator: Hardest to parallelize
(Option 1) Ring Attention: Divide into blocks and
distribute over GPUs. Inner loop over keys/values,
outer loop over queries. Complex to implement but
can scale to very long sequences.
Liu et al, ”Ring Attention with Blockwise
Transformers for Near-Infinite Context”, arXiv2023 |
| Stanford CS231n 10th Anniversary Lecture 11 - 123 May 6, 2025 |


### Table 2

|  |  |  |


[Page contains 1 image(s)]


---
## Page 124
---


Context Parallelism (CP)
(Usually for Transformers)
Idea: Transformers operate on S-length sequences.
Use multiple GPUs to process a single long sequence
QKV Projection: Same as MLP, parallelize over the
sequence and sync gradients as in DP
GPU 1 GPU 2 GPU 3
Attention operator: Hardest to parallelize
(Option 2) Ulysses: Don’t try to distribute attention matrix,
instead parallelize over heads in multihead attention.
Simpler, but max parallelism = number of heads
Jacobs et al, “DeepSpeedUlysses: System Optimizations for Enabling
Training of Extreme Long Sequence Transformer Models”, arXiv2023
Stanford CS231n 10th Anniversary Lecture 11 - 124 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Context Parallelism (CP)
(Usually for Transformers)
Idea: Transformers operate on S-length sequences.
Use multiple GPUs to process a single long sequence
QKV Projection: Same as MLP, parallelize over the
sequence and sync gradients as in DP
GPU 1 GPU 2 GPU 3
Attention operator: Hardest to parallelize
(Option 2) Ulysses: Don’t try to distribute attention matrix,
instead parallelize over heads in multihead attention.
Simpler, but max parallelism = number of heads
Jacobs et al, “DeepSpeedUlysses: System Optimizations for Enabling
Training of Extreme Long Sequence Transformer Models”, arXiv2023 |
| Stanford CS231n 10th Anniversary Lecture 11 - 124 May 6, 2025 |


[Page contains 1 image(s)]


---
## Page 125
---


Context Parallelism (CP)
(Usually for Transformers)
Idea: Transformers operate on S-length sequences.
Use multiple GPUs to process a single long sequence
Often used for long-sequence finetuning.
Example: Llama3-405B training:
- Stage 1: S=8192, no context-parallelism
- Stage 2: S=131,072, 16-way context-parallelism
(8192 per GPU)
Llama Team, “The Llama3 Herd of Models”, arXiv2024
Stanford CS231n 10th Anniversary Lecture 11 - 125 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Context Parallelism (CP)
(Usually for Transformers)
Idea: Transformers operate on S-length sequences.
Use multiple GPUs to process a single long sequence
Often used for long-sequence finetuning.
Example: Llama3-405B training:
- Stage 1: S=8192, no context-parallelism
- Stage 2: S=131,072, 16-way context-parallelism
(8192 per GPU)
Llama Team, “The Llama3 Herd of Models”, arXiv2024 |
| Stanford CS231n 10th Anniversary Lecture 11 - 125 May 6, 2025 |


---
## Page 126
---


How to train on lots of GPUs
A model with L layers operates on tensors of shape (Batch, Sequence, Dim)
Data Parallelism (DP) Context Parallelism (CP)
Split on Batch dimension Split on Sequence dimension
Pipeline Parallelism (PP) Tensor Parallelism (TP)
Split on L dimension Split on Dim dimension
Stanford CS231n 10th Anniversary Lecture 11 - 126 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| How to train on lots of GPUs
A model with L layers operates on tensors of shape (Batch, Sequence, Dim)
Data Parallelism (DP) Context Parallelism (CP)
Split on Batch dimension Split on Sequence dimension
Pipeline Parallelism (PP) Tensor Parallelism (TP)
Split on L dimension Split on Dim dimension |
| Stanford CS231n 10th Anniversary Lecture 11 - 126 May 6, 2025 |


---
## Page 127
---


How to train on lots of GPUs
A model with L layers operates on tensors of shape (Batch, Sequence, Dim)
Data Parallelism (DP) Context Parallelism (CP)
Split on Batch dimension Split on Sequence dimension
Pipeline Parallelism (PP) Tensor Parallelism (TP)
Split on L dimension Split on Dim dimension
Stanford CS231n 10th Anniversary Lecture 11 - 127 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| How to train on lots of GPUs
A model with L layers operates on tensors of shape (Batch, Sequence, Dim)
Data Parallelism (DP) Context Parallelism (CP)
Split on Batch dimension Split on Sequence dimension
Pipeline Parallelism (PP) Tensor Parallelism (TP)
Split on L dimension Split on Dim dimension |
| Stanford CS231n 10th Anniversary Lecture 11 - 127 May 6, 2025 |


---
## Page 128
---


Pipeline Parallelism (PP)
Idea: Split the layers of the model
across GPUs. Copy activations
between layers at GPU boundaries.
GPU 1 GPU 2 GPU 3 GPU 4
Huang et al, “Gpipe: Efficient Training of Giant Neural Networks using Pipeline Parallelism”, arXiv2018
Stanford CS231n 10th Anniversary Lecture 11 - 128 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Pipeline Parallelism (PP)
Idea: Split the layers of the model
across GPUs. Copy activations
between layers at GPU boundaries.
GPU 1 GPU 2 GPU 3 GPU 4
Huang et al, “Gpipe: Efficient Training of Giant Neural Networks using Pipeline Parallelism”, arXiv2018 |
| Stanford CS231n 10th Anniversary Lecture 11 - 128 May 6, 2025 |


---
## Page 129
---


Pipeline Parallelism (PP)
Idea: Split the layers of the model
across GPUs. Copy activations
between layers at GPU boundaries.
GPU 1 GPU 2 GPU 3 GPU 4
Problem: Sequential dependencies;
GPUs are mostly sitting idle.
Huang et al, “Gpipe: Efficient Training of Giant Neural Networks using Pipeline Parallelism”, arXiv2018
Stanford CS231n 10th Anniversary Lecture 11 - 129 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Pipeline Parallelism (PP)
Idea: Split the layers of the model
across GPUs. Copy activations
between layers at GPU boundaries.
GPU 1 GPU 2 GPU 3 GPU 4
Problem: Sequential dependencies;
GPUs are mostly sitting idle.
Huang et al, “Gpipe: Efficient Training of Giant Neural Networks using Pipeline Parallelism”, arXiv2018 |
| Stanford CS231n 10th Anniversary Lecture 11 - 129 May 6, 2025 |


---
## Page 130
---


Pipeline Parallelism (PP)
Idea: Split the layers of the model
across GPUs. Copy activations
between layers at GPU boundaries.
GPU 1 GPU 2 GPU 3 GPU 4
Problem: Sequential dependencies;
GPUs are mostly sitting idle. Time
Max MFU with N-way PP is 1/N
GPU 1 → ←
GPU 2 → ←
GPU 3 → ←
GPU 4 → ←
Huang et al, “Gpipe: Efficient Training of Giant Neural Networks using Pipeline Parallelism”, arXiv2018
Stanford CS231n 10th Anniversary Lecture 11 - 130 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Pipeline Parallelism (PP)
Idea: Split the layers of the model
across GPUs. Copy activations
between layers at GPU boundaries.
GPU 1 GPU 2 GPU 3 GPU 4
Problem: Sequential dependencies;
GPUs are mostly sitting idle. Time
Max MFU with N-way PP is 1/N
GPU 1 → ←
GPU 2 → ←
GPU 3 → ←
GPU 4 → ←
Huang et al, “Gpipe: Efficient Training of Giant Neural Networks using Pipeline Parallelism”, arXiv2018 |
| Stanford CS231n 10th Anniversary Lecture 11 - 130 May 6, 2025 |


### Table 2

| GPU 1 | → |  |  |  |  |  |  | ← |
| GPU 2 |  | → |  |  |  |  | ← |  |
| GPU 3 |  |  | → |  |  | ← |  |  |
| GPU 4 |  |  |  | → | ← |  |  |  |


---
## Page 131
---


Pipeline Parallelism (PP)
Idea: Split the layers of the model
across GPUs. Copy activations
between layers at GPU boundaries.
GPU 1 GPU 2 GPU 3 GPU 4
Problem: Sequential dependencies;
GPUs are mostly sitting idle. Time
Max MFU with N-way PP is 1/N
GPU 1 → Bubble ←
GPU 2 → ←
GPU 3 → ←
GPU 4 → ←
Huang et al, “Gpipe: Efficient Training of Giant Neural Networks using Pipeline Parallelism”, arXiv2018
Stanford CS231n 10th Anniversary Lecture 11 - 131 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Pipeline Parallelism (PP)
Idea: Split the layers of the model
across GPUs. Copy activations
between layers at GPU boundaries.
GPU 1 GPU 2 GPU 3 GPU 4
Problem: Sequential dependencies;
GPUs are mostly sitting idle. Time
Max MFU with N-way PP is 1/N
GPU 1 → Bubble ←
GPU 2 → ←
GPU 3 → ←
GPU 4 → ←
Huang et al, “Gpipe: Efficient Training of Giant Neural Networks using Pipeline Parallelism”, arXiv2018 |
| Stanford CS231n 10th Anniversary Lecture 11 - 131 May 6, 2025 |


### Table 2

| GPU 1 | → |  |  | Bub | bl | e |  | ← |
| GPU 2 |  | → |  |  |  |  | ← |  |
| GPU 3 |  |  | → |  |  | ← |  |  |
| GPU 4 |  |  |  | → | ← |  |  |  |


---
## Page 132
---


Pipeline Parallelism (PP)
Idea: Split the layers of the model
across GPUs. Copy activations
between layers at GPU boundaries.
GPU 1 GPU 2 GPU 3 GPU 4
Problem: Sequential dependencies;
GPUs are mostly sitting idle. Time
Max MFU with N-way PP is 1/N
GPU 1 → Bubble ←
GPU 2 → ←
Solution: Run multiple microbatches
at the same time, pipeline them GPU 3 → ←
through the GPUs
GPU 4 → ←
Huang et al, “Gpipe: Efficient Training of Giant Neural Networks using Pipeline Parallelism”, arXiv2018
Stanford CS231n 10th Anniversary Lecture 11 - 132 May 6, 2025

[Page contains 2 table(s)]


### Table 1

| Pipeline Parallelism (PP)
Idea: Split the layers of the model
across GPUs. Copy activations
between layers at GPU boundaries.
GPU 1 GPU 2 GPU 3 GPU 4
Problem: Sequential dependencies;
GPUs are mostly sitting idle. Time
Max MFU with N-way PP is 1/N
GPU 1 → Bubble ←
GPU 2 → ←
Solution: Run multiple microbatches
at the same time, pipeline them GPU 3 → ←
through the GPUs
GPU 4 → ←
Huang et al, “Gpipe: Efficient Training of Giant Neural Networks using Pipeline Parallelism”, arXiv2018 |
| Stanford CS231n 10th Anniversary Lecture 11 - 132 May 6, 2025 |


### Table 2

| GPU 1 | → |  |  | Bub | bl | e |  | ← |
| GPU 2 |  | → |  |  |  |  | ← |  |
| GPU 3 |  |  | → |  |  | ← |  |  |
| GPU 4 |  |  |  | → | ← |  |  |  |


---
## Page 133
---


Pipeline Parallelism (PP) - Microbatches
Idea: Split the layers of the model
across GPUs. Copy activations
between layers at GPU boundaries.
GPU 1 GPU 2 GPU 3 GPU 4
Time
Example:
4-way PP with 4
microbatches.
Max MFU increases
from 1/4 = 25%
to 16/28 ≈ 57.1%
Huang et al, “Gpipe: Efficient Training of Giant Neural Networks using Pipeline Parallelism”, arXiv2018
Stanford CS231n 10th Anniversary Lecture 11 - 133 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Pipeline Parallelism (PP) - Microbatches
Idea: Split the layers of the model
across GPUs. Copy activations
between layers at GPU boundaries.
GPU 1 GPU 2 GPU 3 GPU 4
Time
Example:
4-way PP with 4
microbatches.
Max MFU increases
from 1/4 = 25%
to 16/28 ≈ 57.1%
Huang et al, “Gpipe: Efficient Training of Giant Neural Networks using Pipeline Parallelism”, arXiv2018 |
| Stanford CS231n 10th Anniversary Lecture 11 - 133 May 6, 2025 |


[Page contains 1 image(s)]


---
## Page 134
---


How to train on lots of GPUs
A model with L layers operates on tensors of shape (Batch, Sequence, Dim)
Data Parallelism (DP) Context Parallelism (CP)
Split on Batch dimension Split on Sequence dimension
Pipeline Parallelism (PP) Tensor Parallelism (TP)
Split on L dimension Split on Dim dimension
Stanford CS231n 10th Anniversary Lecture 11 - 134 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| How to train on lots of GPUs
A model with L layers operates on tensors of shape (Batch, Sequence, Dim)
Data Parallelism (DP) Context Parallelism (CP)
Split on Batch dimension Split on Sequence dimension
Pipeline Parallelism (PP) Tensor Parallelism (TP)
Split on L dimension Split on Dim dimension |
| Stanford CS231n 10th Anniversary Lecture 11 - 134 May 6, 2025 |


---
## Page 135
---


Tensor Parallelism (TP)
XW = Y (1 GPU)
Idea: Split the weights of each
linear layer across GPUs, use
block matrix multiply
=
X: [NxD] W: [DxD] Y: [NxD]
Stanford CS231n 10th Anniversary Lecture 11 - 135 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Tensor Parallelism (TP)
XW = Y (1 GPU)
Idea: Split the weights of each
linear layer across GPUs, use
block matrix multiply
=
X: [NxD] W: [DxD] Y: [NxD] |
| Stanford CS231n 10th Anniversary Lecture 11 - 135 May 6, 2025 |


---
## Page 136
---


Tensor Parallelism (TP)
XW = Y (4-way TP)
Idea: Split the weights of each
linear layer across GPUs, use
block matrix multiply
W W W W = Y Y Y Y
1 2 3 4 1 2 3 4
X: [NxD] W: [DxD] Y: [NxD]
Block shapes: [1x1] [1x4] [1x4]
GPU i computes
XW = Y
i i
Stanford CS231n 10th Anniversary Lecture 11 - 136 May 6, 2025

[Page contains 3 table(s)]


### Table 1

| Tensor Parallelism (TP)
XW = Y (4-way TP)
Idea: Split the weights of each
linear layer across GPUs, use
block matrix multiply
W W W W = Y Y Y Y
1 2 3 4 1 2 3 4
X: [NxD] W: [DxD] Y: [NxD]
Block shapes: [1x1] [1x4] [1x4]
GPU i computes
XW = Y
i i |
| Stanford CS231n 10th Anniversary Lecture 11 - 136 May 6, 2025 |


### Table 2

| Y
1 | Y
2 | Y
3 | Y
4 |


### Table 3

| W
1 | W
2 | W
3 | W
4 |


---
## Page 137
---


Tensor Parallelism (TP)
XW = Y (4-way TP)
Idea: Split the weights of each
linear layer across GPUs, use
block matrix multiply
W W W W = Y Y Y Y
1 2 3 4 1 2 3 4
Problem: Need to gather
parts of Y after forward, can’t
overlap with communication
X: [NxD] W: [DxD] Y: [NxD]
Block shapes: [1x1] [1x4] [1x4]
GPU i computes
XW = Y
i i
Stanford CS231n 10th Anniversary Lecture 11 - 137 May 6, 2025

[Page contains 3 table(s)]


### Table 1

| Tensor Parallelism (TP)
XW = Y (4-way TP)
Idea: Split the weights of each
linear layer across GPUs, use
block matrix multiply
W W W W = Y Y Y Y
1 2 3 4 1 2 3 4
Problem: Need to gather
parts of Y after forward, can’t
overlap with communication
X: [NxD] W: [DxD] Y: [NxD]
Block shapes: [1x1] [1x4] [1x4]
GPU i computes
XW = Y
i i |
| Stanford CS231n 10th Anniversary Lecture 11 - 137 May 6, 2025 |


### Table 2

| Y
1 | Y
2 | Y
3 | Y
4 |


### Table 3

| W
1 | W
2 | W
3 | W
4 |


---
## Page 138
---


Tensor Parallelism (TP)
XW = Y (4-way TP)
Idea: Split the weights of each
linear layer across GPUs, use
block matrix multiply
W W W W = Y Y Y Y
1 2 3 4 1 2 3 4
Problem: Need to gather
parts of Y after forward, can’t
overlap with communication
X: [NxD] W: [DxD] Y: [NxD]
Block shapes: [1x1] [1x4] [1x4]
Trick: With 2 consecutive TP
layers, shard first over row
GPU i computes
and second over column to
XW = Y
avoid communication i i
Stanford CS231n 10th Anniversary Lecture 11 - 138 May 6, 2025

[Page contains 3 table(s)]


### Table 1

| Tensor Parallelism (TP)
XW = Y (4-way TP)
Idea: Split the weights of each
linear layer across GPUs, use
block matrix multiply
W W W W = Y Y Y Y
1 2 3 4 1 2 3 4
Problem: Need to gather
parts of Y after forward, can’t
overlap with communication
X: [NxD] W: [DxD] Y: [NxD]
Block shapes: [1x1] [1x4] [1x4]
Trick: With 2 consecutive TP
layers, shard first over row
GPU i computes
and second over column to
XW = Y
avoid communication i i |
| Stanford CS231n 10th Anniversary Lecture 11 - 138 May 6, 2025 |


### Table 2

| Y
1 | Y
2 | Y
3 | Y
4 |


### Table 3

| W
1 | W
2 | W
3 | W
4 |


---
## Page 139
---


(4-way TP)
XW = Y (layer 1)
Tensor Parallelism (TP) – Two Layers
YU = Z (layer 2)
U
1
U
2
= Y Y Y Y =
1 2 3 4 U
3
U
4
X: [NxD] W: [DxD] Y: [NxD] U: [DxD] Z: [DxD]
Stanford CS231n 10th Anniversary Lecture 11 - 139 May 6, 2025

[Page contains 4 table(s)]


### Table 1

| (4-way TP)
XW = Y (layer 1)
Tensor Parallelism (TP) – Two Layers
YU = Z (layer 2)
U
1
U
2
= Y Y Y Y =
1 2 3 4 U
3
U
4
X: [NxD] W: [DxD] Y: [NxD] U: [DxD] Z: [DxD] |
| Stanford CS231n 10th Anniversary Lecture 11 - 139 May 6, 2025 |


### Table 2

| Y
1 | Y
2 | Y
3 | Y
4 |


### Table 3

|  |  |  |  |


### Table 4

| U
1 |
| U
2 |
| U
3 |
| U
4 |


---
## Page 140
---


(4-way TP)
XW = Y (layer 1)
Tensor Parallelism (TP) – Two Layers
YU = Z (layer 2)
U
1
U
2
W W W W = Y Y Y Y =
1 2 3 4 1 2 3 4 U
3
U
4
X: [NxD] W: [DxD] Y: [NxD] U: [DxD] Z: [DxD]
Block
shapes: [1x1] [1x4] [1x4] [4x1] [1x1]
Stanford CS231n 10th Anniversary Lecture 11 - 140 May 6, 2025

[Page contains 4 table(s)]


### Table 1

| (4-way TP)
XW = Y (layer 1)
Tensor Parallelism (TP) – Two Layers
YU = Z (layer 2)
U
1
U
2
W W W W = Y Y Y Y =
1 2 3 4 1 2 3 4 U
3
U
4
X: [NxD] W: [DxD] Y: [NxD] U: [DxD] Z: [DxD]
Block
shapes: [1x1] [1x4] [1x4] [4x1] [1x1] |
| Stanford CS231n 10th Anniversary Lecture 11 - 140 May 6, 2025 |


### Table 2

| Y
1 | Y
2 | Y
3 | Y
4 |


### Table 3

| W
1 | W
2 | W
3 | W
4 |


### Table 4

| U
1 |
| U
2 |
| U
3 |
| U
4 |


---
## Page 141
---


(4-way TP)
XW = Y (layer 1)
Tensor Parallelism (TP) – Two Layers
YU = Z (layer 2)
U
1
U
2
W W W W = Y Y Y Y =
1 2 3 4 1 2 3 4 U
3
U
4
X: [NxD] W: [DxD] Y: [NxD] U: [DxD] Z: [DxD]
Block
shapes: [1x1] [1x4] [1x4] [4x1] [1x1]
Z = Y U + Y U
1 1 2 2
+ Y U + Y U
3 3 4 4
Stanford CS231n 10th Anniversary Lecture 11 - 141 May 6, 2025

[Page contains 4 table(s)]


### Table 1

| (4-way TP)
XW = Y (layer 1)
Tensor Parallelism (TP) – Two Layers
YU = Z (layer 2)
U
1
U
2
W W W W = Y Y Y Y =
1 2 3 4 1 2 3 4 U
3
U
4
X: [NxD] W: [DxD] Y: [NxD] U: [DxD] Z: [DxD]
Block
shapes: [1x1] [1x4] [1x4] [4x1] [1x1]
Z = Y U + Y U
1 1 2 2
+ Y U + Y U
3 3 4 4 |
| Stanford CS231n 10th Anniversary Lecture 11 - 141 May 6, 2025 |


### Table 2

| Y
1 | Y
2 | Y
3 | Y
4 |


### Table 3

| W
1 | W
2 | W
3 | W
4 |


### Table 4

| U
1 |
| U
2 |
| U
3 |
| U
4 |


---
## Page 142
---


(4-way TP)
XW = Y (layer 1)
Tensor Parallelism (TP) – Two Layers
YU = Z (layer 2)
U
1
U
2
W W W W = Y Y Y Y =
1 2 3 4 1 2 3 4 U
3
U
4
X: [NxD] W: [DxD] Y: [NxD] U: [DxD] Z: [DxD]
Block
shapes: [1x1] [1x4] [1x4] [4x1] [1x1]
GPU i computes GPU i computes Z = Y U + Y U
1 1 2 2
XW = Y YU = Z + Y U + Y U
i i i i i 3 3 4 4
Stanford CS231n 10th Anniversary Lecture 11 - 142 May 6, 2025

[Page contains 4 table(s)]


### Table 1

| (4-way TP)
XW = Y (layer 1)
Tensor Parallelism (TP) – Two Layers
YU = Z (layer 2)
U
1
U
2
W W W W = Y Y Y Y =
1 2 3 4 1 2 3 4 U
3
U
4
X: [NxD] W: [DxD] Y: [NxD] U: [DxD] Z: [DxD]
Block
shapes: [1x1] [1x4] [1x4] [4x1] [1x1]
GPU i computes GPU i computes Z = Y U + Y U
1 1 2 2
XW = Y YU = Z + Y U + Y U
i i i i i 3 3 4 4 |
| Stanford CS231n 10th Anniversary Lecture 11 - 142 May 6, 2025 |


### Table 2

| Y
1 | Y
2 | Y
3 | Y
4 |


### Table 3

| W
1 | W
2 | W
3 | W
4 |


### Table 4

| U
1 |
| U
2 |
| U
3 |
| U
4 |


---
## Page 143
---


(4-way TP)
XW = Y (layer 1)
Tensor Parallelism (TP) – Two Layers
YU = Z (layer 2)
U
1
U
2
W W W W = Y Y Y Y =
1 2 3 4 1 2 3 4 U
3
U
4
X: [NxD] W: [DxD] Y: [NxD] U: [DxD] Z: [DxD]
Block
shapes: [1x1] [1x4] [1x4] [4x1] [1x1]
No need for communication after XW=Y! Each GPU Z = Y U + Y U
1 1 2 2
computes one term of Z, then broadcasts to all other GPUs + Y U + Y U
3 3 4 4
Stanford CS231n 10th Anniversary Lecture 11 - 143 May 6, 2025

[Page contains 4 table(s)]


### Table 1

| (4-way TP)
XW = Y (layer 1)
Tensor Parallelism (TP) – Two Layers
YU = Z (layer 2)
U
1
U
2
W W W W = Y Y Y Y =
1 2 3 4 1 2 3 4 U
3
U
4
X: [NxD] W: [DxD] Y: [NxD] U: [DxD] Z: [DxD]
Block
shapes: [1x1] [1x4] [1x4] [4x1] [1x1]
No need for communication after XW=Y! Each GPU Z = Y U + Y U
1 1 2 2
computes one term of Z, then broadcasts to all other GPUs + Y U + Y U
3 3 4 4 |
| Stanford CS231n 10th Anniversary Lecture 11 - 143 May 6, 2025 |


### Table 2

| Y
1 | Y
2 | Y
3 | Y
4 |


### Table 3

| W
1 | W
2 | W
3 | W
4 |


### Table 4

| U
1 |
| U
2 |
| U
3 |
| U
4 |


---
## Page 144
---


How to train on lots of GPUs
A model with L layers operates on tensors of shape (Batch, Sequence, Dim)
Data Parallelism (DP) Context Parallelism (CP)
Split on Batch dimension Split on Sequence dimension
Pipeline Parallelism (PP) Tensor Parallelism (TP)
Split on L dimension Split on Dim dimension
Stanford CS231n 10th Anniversary Lecture 11 - 144 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| How to train on lots of GPUs
A model with L layers operates on tensors of shape (Batch, Sequence, Dim)
Data Parallelism (DP) Context Parallelism (CP)
Split on Batch dimension Split on Sequence dimension
Pipeline Parallelism (PP) Tensor Parallelism (TP)
Split on L dimension Split on Dim dimension |
| Stanford CS231n 10th Anniversary Lecture 11 - 144 May 6, 2025 |


---
## Page 145
---


How to train on lots of GPUs
A model with L layers operates on tensors of shape (Batch, Sequence, Dim)
Data Parallelism (DP) Context Parallelism (CP)
Split on Batch dimension Split on Sequence dimension
Q: Which to use for largest models?
A: All of them!
Pipeline Parallelism (PP) Tensor Parallelism (TP)
Split on L dimension Split on Dim dimension
Stanford CS231n 10th Anniversary Lecture 11 - 145 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| How to train on lots of GPUs
A model with L layers operates on tensors of shape (Batch, Sequence, Dim)
Data Parallelism (DP) Context Parallelism (CP)
Split on Batch dimension Split on Sequence dimension
Q: Which to use for largest models?
A: All of them!
Pipeline Parallelism (PP) Tensor Parallelism (TP)
Split on L dimension Split on Dim dimension |
| Stanford CS231n 10th Anniversary Lecture 11 - 145 May 6, 2025 |


---
## Page 146
---


ND Parallelism
Use TP, CP, PP, and DP
all at the same time!
Arrange GPUs in a 4D grid
GPUs index in the grid
gives its rank along each
parallelism dimension
Example: LLama3-405B
Optimize setup to
maximize MFU
Llama Team, “The Llama3 Herd of Models”, arXiv2024
Stanford CS231n 10th Anniversary Lecture 11 - 146 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| ND Parallelism
Use TP, CP, PP, and DP
all at the same time!
Arrange GPUs in a 4D grid
GPUs index in the grid
gives its rank along each
parallelism dimension
Example: LLama3-405B
Optimize setup to
maximize MFU
Llama Team, “The Llama3 Herd of Models”, arXiv2024 |
| Stanford CS231n 10th Anniversary Lecture 11 - 146 May 6, 2025 |


[Page contains 2 image(s)]


---
## Page 147
---


Summary: Large-Scale Distributed Training
A GPU is a parallel processor Split up the computation along different axes
with hundreds of cores Consider a model with many Layers, operating
on tensors of shape (Batch, Seq, Dim)
- Data Parallel (DP): Split on Batch
- Context Parallel (CP): Split on Seq
- Pipeline Parallel (PP): Split on Layers
- Tensor Parallel (TP): Split on Dim
A GPU cluster has O(10K) GPUs
Activation Checkpointing saves
memory by recomputing during backward
Tune parallelism recipe to maximize
Model Flops Utilization (MFU)
Stanford CS231n 10th Anniversary Lecture 11 - 147 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Summary: Large-Scale Distributed Training
A GPU is a parallel processor Split up the computation along different axes
with hundreds of cores Consider a model with many Layers, operating
on tensors of shape (Batch, Seq, Dim)
- Data Parallel (DP): Split on Batch
- Context Parallel (CP): Split on Seq
- Pipeline Parallel (PP): Split on Layers
- Tensor Parallel (TP): Split on Dim
A GPU cluster has O(10K) GPUs
Activation Checkpointing saves
memory by recomputing during backward
Tune parallelism recipe to maximize
Model Flops Utilization (MFU) |
| Stanford CS231n 10th Anniversary Lecture 11 - 147 May 6, 2025 |


[Page contains 2 image(s)]


---
## Page 148
---


Next Time:
Self-Supervised Learning
Stanford CS231n 10th Anniversary Lecture 11 - 148 May 6, 2025

[Page contains 1 table(s)]


### Table 1

| Next Time:
Self-Supervised Learning |
| Stanford CS231n 10th Anniversary Lecture 11 - 148 May 6, 2025 |
