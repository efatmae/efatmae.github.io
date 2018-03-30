---
title: "High Performance Stencil Code Generation with Lift"
collection: talks
type: "Poster"
permalink: /talks/2017-12-Google-Summit
venue: "Compiler and Programming Language Summit 2017"
date: 2017-12-04
location: "Munich, Germany"
---

<a href="/files/talks/2017/Google-Summit-2017.pdf" style="margin-right:1em; text-decoration: none;"><span class="fa-stack fa-1x"><i class="fa fa-file fa-2x"></i></span> Poster</a>

Stencil computations are widely used from physical simulations to machine-learning and are commonly executed on modern parallel systems such as multi-core CPUs, Graphic Processing Units or accelerators such as Intel’s Xeon Phi. Although stencil computations have been extensively studied, optimizing them for the increasingly diverse hardware landscape remains challenging even for performance experts.

Domain Specific Languages (DSLs) have been proposed for raising the programming abstractions while offering good performance. However, DSLs shift the burden of optimizing and compiling stencil codes for ever-changing hardware architectures on the DSL implementers who have to re-implement full-fledged parallelizing optimizing compilers for every architecture. The Lift project has recently emerged as a promising compilation framework to achieve performance portability. Lift defines a small set of reusable parallel primitives that DSL writers can easily build upon. Lift’s key novelty is its ability to automatically explore the optimization space by using as a system of extensible rewrite rules which encode specific optimizations.

In this talk, I show how Lift is extended to generate efficient code for stencil applications.  With the addition of only two new Lift primitives and a single rewrite rules we are able to express stencil computations of arbitrary dimensionality and compile them to efficient code on three different GPU architectures. The ability to express complex multidimensional stencil computations as compositions of simple 1D primitives is a powerful new insight of our design which enables us to build an elegant optimizing compiler. By automatically exploring optimizations through an extensible set of rewrite rules, Lift can automatically optimize for novel architectures and, therefore, provides a future proof optimization methodology.
