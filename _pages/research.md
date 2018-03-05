---
title: "Research"
permalink: /research/
author_profile: true
---

As one of the core-developers of [Lift](http://www.lift-project.org/stencils.html), I am focussing on performance portable code generation for parallel accelerators.
I have been particularly focussing on code generation for stencil computations.
A paper about this work has been published at [CGO'18](/publications/2018/CGO/) and won the prestigious **Best Paper Award**.

I am especially interested in expressing optimizations as formal rewrite rules and the systematic exploration of the space of possible implementation choices.

# Available Dissertation Topics
This is an overview of the currently available topics for bachelor and master dissertations.
If you have any questions or are interested in one or more topics feel free to drop me an email.

## Designing a DSL for Expressing Rewrite Rules in Lift
(Suitable for bachelor and master students)
In Lift, programs are optimized by applying rewrite rules.
Currently, these rewrite rules are tightly integrated in the Scala implementation of Lift.
In this thesis, a Domain Specific Language (DSL) needs to be designed and implemented which allows to express rewrite rules more conveniently.

## Automatic Optimization of Image Processing Pipelines in Lift
(Suitable for master students)
Image Processing Pipelines are applications consisting of multiple simple computations which together form a computation graph.
An example for such an application is the Harris Corner Detection algorithm which consists of multiple Matrix Multiply and Convolution nodes.
Scheduling and fusing these computations to achieve highest performance is a non-trivial task.
This thesis should extend Lift with the functionality to express, optimize and execute computation graphs.

## Algorithmic Convolution Transformations in Lift
(Suitable for master students)
Convolutions are simple stencil computations which frequently occur in deep learning and are executed iteratively millions of times.
High-performance implementations of convolutions are provided in vendor-tuned libraries such as cuDNN for Nvidia GPUs.
In order to get the highest performance possible across different architectures, one needs to adjust the implementation for the given device, input size and weight-matrix size.
Generally, there exist four different variants to compute convolutions: [_Direct_](http://www.lift-project.org/publications/2016/hagedorn16masterthesis.pdf), [_GEMM-based_](https://arxiv.org/pdf/1410.0759.pdf), [_FFT-based_](https://arxiv.org/pdf/1312.5851.pdf) and [_Winograd_](https://arxiv.org/pdf/1509.09308.pdf).
All of these approaches compute the same result using a different strategy suitable for a particular situation.
The goal of this thesis is to implement all strategies as Lift-expressions and formulate rewrite rules which allow to transform expressions to implement different strategies.
An interesting [paper](https://arxiv.org/pdf/1710.01079.pdf) related to this topic has been published at CGO'18.

## Performance Modelling of Lift Low-Level Expressions
(Suitable for bachelor and master students)
[Performance Models](http://www.ac.uma.es/~siham/CPE.pdf) are used to predict the performance of programs without actually executing them.
In this thesis, a performance model for stencil computations shall be integrated into Lift in order to predict the performance of low-level Lift expressions.

## Optimizing Stencil Computations for Intel Xeon Phi using Vectorization
(Suitable for bachelor students)
Optmizing programs for Intels Xeon Phi accelerator is an interesting challenge as it requires to efficiently use the wide vector registers availabe in AVX-512.
In this thesis, stencil computations such as simple convolutions applications, shall be analyzed and systematically optimized on Intels newest Xeon Phi platforms.

## Evaluation of the PPCG Polyhedral Compilation Framework
(Suitable for bachelor students)
PPCG, is a state-of-the-art polyhedral complier which automatically generates OpenCL and CUDA programs.
In this thesis, the performance achieved by PPCG and Lift shall be evaluated using multiple benchmarks.

## Evaluation of the Futhark Optimizing Compiler
(Suitable for bachelor students)
[Futhark](https://futhark-lang.org/) is a new functional language designed to be compiled to high-performance OpenCL code targeted for GPUs.
Similar to Lift, Futhark relies on automatic rewriting of functional programs during the optimization phase of their compiler.
In this thesis, the performance achieved by Futhark and Lift shall be evaluated using multiple benchmarks implemented in both languages.

## Implementing an Evaluation Module for the Auto-Tuning Framework (ATF)
(Suitable for bachelor students)
The ATF is an auto-tuning framework developed at the University of Münster.
An auto-tuner automatically optimizes a program which contains so-called _tuning parameters_ by generating and systematically exploring the space of possible values for each of these parameters. 
In this thesis, the ATF will be extended with a new module which, at the end of the automated tuning, systematicaly analyzes the results.
This consists of generating multiple plots for the achieved results.
Often enough, observing the same results using different metrics reveals new insights and information.
With the help of the new module, the analysis of the produced data shall be significantly simplified and easily configurable to the developers needs.

## More topics include:
### Visualizing Transformations and Rewriting of Functional Programs
(Suitable for bachelor and master students)

### Implementing an LLVM Frontend for Lift
(Suitable for bachelor and master students)


