---
title: "Research"
permalink: /research/
author_profile: true
---

As one of the core-developers of [Lift](http://www.lift-project.org/stencils.html), I am focussing on performance portable code generation for parallel accelerators.
I have been particularly focussing on code generation for stencil computations.
A paper about this work has been published at [CGO'18](/publications/2018/CGO/) and won the prestigious **Best Paper Award**.

## What I am interested in
In my research, I aim to achieve performance-portability by providing a tool chain which combines high-level programming abstractions and modern compiler technology with application and architecture domain knowledge. 
Ever since I started my undergraduate, Ive been actively collaborating with researchers from the Universities of Edinburgh and Glasgow, and participated in multiple research visits every year.
I just started the third year of my PhD which is typically five years in Germany and my work so far has lead to six peer-reviewed publications including winning the best paper award at the prestigious ACM SIGPLAN International Symposium on Code Generation and Optimization (CGO). 
This paper showed that it is possible to both have an expressive, generic high-level language in which problems are specified while at the same generating high performance code which matches or outperforms hand optimized reference implementations. 
In the future, I plan to use these ideas to build a programming model, language, and compiler/synthesizer for DNNs and GPUs.

### Motivation
GPUs unlocked the breakthroughs achieved with the help of Artificial Intelligence, especially Deep Learning, thanks to their capabilities of processing huge amounts of data in reasonable time frames. 
Deep learning applications are usually written using high-level frameworks like TensorFlow or PyTorch which provide convenient interfaces for data scientists while promising high performance at the same time.
The heavy lifting of achieving high performance is done by libraries such as cuBLAS or cuDNN. These libraries are called by high-level frameworks and provide carefully hand-optimized implementations for a fixed set of common deep learning building blocks (such as GEMM or Convolution).
The task of the library programmer is incredibly challenging: For each of the building blocks of the library, say GEMM, a high-performance implementation has to be provided for all commonly used architectures, input sizes, varying precision, and different storage formats. 
For example in the domain of linear algebra, cuBLAS is tuned from Kepler to Turing which are used in embedded Jetson devices up to server class Tesla GPUs. 
For GEMM, in case of extreme input sizes, different implementations have to be chosen (e.g., in extreme cases where m and n are small like in implicit GEMM wgrad kernels (m = n = 64, k = 401408), different algorithm variations need to be implemented since the only way to fill the whole GPU with work in this case is splitting the k-dimension across thread blocks). 
Various precision implementations are provided for half, single or double precision and storage formats (row-major, column-major) have a big impact on performance.
To make matters worse, these high-performance implementations need to be provided as optimized SASS assembly code because important performance critical architectural features are only exposed as this API level.
I call the gap between the abstract mathematical program and its optimized implementation the abstraction gap.
Currently, programmers building high-performance libraries lack sufficient high-level abstractions which allow them to rapidly prototype and conveniently experiment with different optimizations. 
In my research, I aim to bridge the abstraction gap by providing a tool chain for library programmers which A) assists programmers in experimenting with optimizations by providing a high-level AI domain-specific IR and compiler which is designed to reuse and express optimizations as combinations of simple and composable strategies which can be both written manually by performance experts but also automatically explored using program synthesis; B) automates tedious and error prone tasks such as computing array indices which specify how a multidimensional compute hierarchy accesses multidimensional data structures; and C) allows to express deep learning computations as compositions of high-level building blocks in the spirit of my work on stencil computations in Lift.
These expressions can then be transformed using semantics preserving rewrite-rules which allow to optimize computations across the typically narrow interface of libraries.

### Bridging the Abstraction Gap
#### A. Optimizations as Replacable and Composable Strategies
Due to the abstraction gap, optimizations must be implemented directly in low-level assembly code. 
However, common optimizations such as tiling or even more advanced optimizations like crosswise/contiguous shared memory prefetching are explainable conceptually without ever looking at the low-level assembly code. 
In fact, we often describe them using fairly simple drawings on a whiteboard. 
I want to build an IR in which these optimizations are specified on an abstract level and which enables performance experts to conveniently and more safely experiment with different optimizations for different target hardware.
Halide has pioneered a way of allowing domain experts (in the domain of image processing) to rapidly prototype and choose optimizations by using a high-level API without dealing with low-level details like transforming index expressions. 
Inspired by their approach and during my summer internship at the deep learning compiler team at NVIDIA, I started developing a high-level AI domain-specific IR in the spirit of Halide which allows rapid prototyping of high performance GEMM implementations. 
In this IR, optimizations are described as combinations of simple and composable building blocks. 
The developed building blocks allow to conveniently decompose a given problem into smaller sub-problems which can be optimized in isolation and which are mapped to the different levels of the compute and memory hierarchy. 
This way, specific combinations of recurring optimizations can be defined as reusable optimization strategies which can be plugged into a decomposition of another problem.
The first promising performance measurements show that the generated code for GEMM using this novel approach matches the manual optimized code written by NVIDIA engineers while significantly raising the level of abstraction.
In my research, I envision to innovate the way we think about optimizing GPU deep learning applications by combining my work on this language and compiler with my experience on code generation and stencil computations especially convolutions which I have extensively studied in my PhD. 
Furthermore, I plan to allow unspecified optimization strategies in a program (e.g., how to load data from global to shared memory) and use program synthesis techniques to explore optimal solutions satisfying interacting constraints such as maximizing bandwidth while avoiding shared memory bank conflicts.

#### B. Increasing Safety and Correctness by Automation
All optimizations mentioned above eventually map logical chunks of data to both threads and specific locations in the memory hierarchy. In code, these mappings translate into complicated index transformations which are crucial for correctness as they might lead to invalid memory accesses. 
Furthermore, these index transformations are easy to get wrong but at the same time can be automatically generated from a decompositional high-level IR as proposed in A).
As one of the main developers of the Lift language and compiler, I worked on code generation and especially arithmetic expression simplification. 
Boundary conditions in stencil computations require indices to be transformed into long and complicated expressions. 
I helped to developed an OpenSource library ArithExpr which simplifies the automatically generated indices.
Another performance critical but tedious task which however is a good candidate for automation using appropriate tools is the generation of swizzle expressions. 
These expression change the mapping of threads to data in order to satisfy a number of constraints which enforce correctness of the expression, while ensuring that memory bandwidth is best utilized. 
By developing a novel code generator which is inspired by the automated capabilities of ArithExpr, library programmers will be able to rely on correct index transformations being generated automatically. o
This enables programmers to quickly and freely explore different optimization possibilities.

#### C. High-Level DSL for Tensor Computations
So far, the proposed technologies will enable library programmers to explore high-performance implementations for common deep learning building blocks more conveniently, quickly and safely. 
However, the one fundamental problem with applications relying on libraries for providing high-performance is the composition of library functions:
Libraries provide implementations for a small set of fixed primitives which might not be sufficient for the next generation neural network architectures. 
There might be a new type of neural network layer, a new way to compute an existing layer (e.g., for convolution layers we have multiple implementation choices: direct, GEMM-based, FFT-based or Winograd) or a specific fusion of layers which is not covered by the library API. 
In all these cases the library programmers need to optimize for these new use cases from scratch.
Instead of mapping operations in neural networks to fixed library APIs, I want to allow expressing these operations in Lift and perform high-level transformations across operations (e.g., layer fusion) using rewrite rules. 
This way, we can compile from high-level frameworks such as TensorFlow or their IRs (e.g., XLA) to Lift and optimize these expressions using the tools proposed in A) and B). 
My work on supporting stencil computations showed that Lift’s language is easily extensible and it’s rewrite rules and exploration are powerful enough to encode high-level transformations.
Rather than defining a fixed set of operations up-front, we can then easily adjust our computations to the requirements of today’s and tomorrow’s neural network architectures.

### Conclusion
In my research, I work towards developing a flexible DSL for tensor computations which will be compiled into a novel AI domain specific IR allowing to experiment with optimizations and use modern code generation techniques to generate high performance GPU code. 
I am always looking for new collaborations because I think ambitious goals are best solved in a team.
If you are interested in working together or know any research that might be of interest to me please feel free to contact me!
