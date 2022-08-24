---
layout: single
title: "Research"
permalink: /research/
author_profile: true
---

A complete list of publications is available on my [Google Scholar page](https://scholar.google.com/citations?user=4-LEq38AAAAJ&hl=en), or on my [CV](../files/Fortino_Garcia_CV.pdf). All preprints are also available on [arXiv](https://arxiv.org/a/garcia_f_1.html).

My research interests are broadly in numerical methods for linear PDEs, scientific computing, and optimization. More specifically, my research focuses on numerical methods for problems related to wave propagation primarily in two main areas: 
- [Time-domain approaches for Helmholtz problems](#time-domain-approaches-for-helmholtz-problems)
- [Optimal control for quantum systems](#optimal-control-for-quantum-systems)

I gratefully acknowledge the support of the NSF (DMS-1913076 and DMS-2103382) as well as STINT initiation grant IB2019–8154 in making this work possible. 


## Time-domain approaches for Helmholtz problems

For many applications in seismology, optics, and  acoustics it is important to find solutions of the time-dependent wave equation that are periodic in the limit as time goes to infinity (which are commonly called *time-harmonic solutions*). Rather than solve the wave equation forward in time to obtain this solution it is common to instead solve the *Helmholtz equation* which is a second order time-independent PDE. The Helmholtz equation is notoriously difficult to solve by direct or iterative methods due to the resolution requirements and the indefinite nature of the differential operator, especially at high frequencies. This has lead to a very rich and active research area in designing preconditioners and direct solvers (which you can read more about [here](https://www.unige.ch/~gander/Preprints/HelmholtzReview.pdf)).

Rather than working with the Helmholtz equation directly, we instead propose going back to the time-domain to seek time-harmonic solutions of the wave equation in an iterative fashion. This method, which we have named the WaveHoltz iteration, instead seeks to find a fixed point of an operator that takes a time-average of a wave equation solution over a single period. What is remarkable about our method is that it *results in a positive definite system* whereas the Helmholtz problem may be indefinite, is *scalable and memory-lean* since it exploits wave equation solves as its main workhorse, and is *simple to apply to other models* such as damped wave equations or even [Maxwell's equations](https://ieeexplore.ieee.org/abstract/document/9743767). For instance, below we plot the log of the real part of the Helmholtz solution for a point source inside of a wedge with discontinuous wavespeeds and impedance (outflow) boundary conditions.
<img src="../files/wedge_undamped_f20.png" width="400" />

WaveHoltz can be extended in a straightforward way to solve the *Navier* or *Navier-Cauchy* equation (not to be confused with the ubiquitous Navier-Stokes equation!) which is the elastic analogue of the Helmholtz equation. Below is a log plot of the magnitude of the solution of the Navier equation for an elastic inclusion (perhaps more recognizable as the cover image of a [certain book](https://www.cambridge.org/core/books/finite-volume-methods-for-hyperbolic-problems/97D5D1ACB1926DA1D4D52EAD6909E2B9)) obtained using the WaveHoltz iteration.
<img src="../files/inclusion_om100_r2_p6.png" width="700" />

### Selected relevant papers:

- [WaveHoltz: Iterative Solution of the Helmholtz Equation via the Wave Equation](https://epubs.siam.org/doi/abs/10.1137/19M1299062)
- [El-WaveHoltz: A Time-Domain Iterative Solver for Time-Harmonic Elastic Waves](https://arxiv.org/abs/2205.12344)
- [Extensions and Analysis of an Iterative Solution of the Helmholtz Equation via the Wave Equation](https://arxiv.org/abs/2205.12349)

[Back to top](#top)

## Optimal Control for quantum systems

