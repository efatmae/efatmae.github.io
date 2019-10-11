---
title: "Elevate - A Language for Specifying Optimization Strategies"
collection: talks
type: "Poster"
permalink: /talks/2019-07-ACACES
venue: "ACACES 2019"
date: 2019-07-14
location: "Fiuggi, Italy"
---

<a href="/files/talks/2019/ACACES-2019.pdf" style="margin-right:1em; text-decoration: none;"><span class="fa-stack fa-1x"><i class="fa fa-file fa-2x"></i></span> Poster</a>

 The increasing trend towards specialised hardware accelerators makes writing portable software that achieves high performance and efficiency across multiple devices a challenging – if not impossible – task for most programmers. Higher level programming languages combined with sophisticated code generators have emerged as a promising direction to address this performance portability challenge. Among these approaches is the Lift project (www.lift-projet.org). The high-level Lift language allows developers to express applications in a composable and portable way. Lift programs are then translated with a rewrite system into a low-level form from which high-performance code is generated. These two layers clearly separate the functional “what to compute” from the imperative “how to compute it”. In this talk I will present an early version of Elevate a new language to define optimisation strategies of Lift programs as compositions of rewrite rules. While other systems, such as Halide, provide means to apply schedules or strategies externally, Elevate is designed to be extensible and allows developers to define their own optimisation strategies such as tiling or particular strategies to map computations to the hardware. I will show that Lift and Elevate successfully address the performance portability challenge on a series of applications ranging from linear algebra over HPC stencil computations to machine learning.

This is joined work with Michel Steuwer (University of Glasgow) 
