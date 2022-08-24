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

Rather than working with the Helmholtz equation directly, we instead propose going back to the time-domain to seek time-harmonic solutions of the wave equation in an iterative fashion. This method, which we have named the WaveHoltz iteration, instead seeks to find a fixed point of an operator that takes a time-average of a wave equation solution over a single period. What is remarkable about our method is that it *results in a positive definite system* whereas the Helmholtz problem may be indefinite, is *scalable and memory-lean* since it exploits wave equation solves as its main workhorse, and is *simple to apply to other models* such as damped wave equations or elastic media. 


{% comment %}
#Below is a plot of density at times .3 and .7 for a horizontally periodic version of a compressible inviscid weak shock-vortex interaction from [Shu (1998)](https://ntrs.nasa.gov/archive/nasa/casi.ntrs.nasa.gov/19980007543.pdf). The solution is computed using an entropy stable method on a quadrilateral mesh of 100-by-50 elements of polynomial degree 4. No regularization is applied apart from a consistent [interface dissipation](https://www.sciencedirect.com/science/article/pii/S0021999116306477), yet the solution remains stable in the presence of the shock. 
#<img src="../files/shockvortex.png" width="900" />
{% endcomment %}
<p float="left">
<img src="../files/wedge_undamped_f20.png" width="850" />
</p>


### Selected relevant papers:

- [WaveHoltz: Iterative Solution of the Helmholtz Equation via the Wave Equation](https://epubs.siam.org/doi/abs/10.1137/19M1299062)
- [El-WaveHoltz: A Time-Domain Iterative Solver for Time-Harmonic Elastic Waves](https://arxiv.org/abs/2205.12344)
- [Extensions and Analysis of an Iterative Solution of the Helmholtz Equation via the Wave Equation](https://arxiv.org/abs/2205.12349)

[Back to top](#top)
<!-- 
## Optimal Control for quantum systems

This work, done in collaboration with Dr. Anders Petersson at Lawrence Livermore National Laboratory (LLNL), focuses on numerical methods for optimal control of quantum systems. The methods of QCLLNL were motivated by the need of Dr. Jonathan Dubois's Quantum Coherent Device Physics Group at LLNL for efficient software capable of generating high-fidelity quantum logic gates. Specifically, our approach was co-designed by the quantum group at LLNL to be faster and more robust than competing quantum control software, such as QuTiP, at finding control signals that perform logic gates on superconducting qubits. The evolution of these superconducting qubits is governed by the ODE Schrödinger equation
which can be derived by diagonalizing the original Schrödinger PDE in space.

$f(t)$ is a real-valued function of time representing a microwave pulse driving the system. A distinguishing feature of our approach is that the number of control parameters defining the control is independent of the number of timesteps needed, which is in contrast to the customary GRAPE algorithm~\cite{Khaneja-2005}. This decoupling is achieved by expanding $f$ in a B-spline basis with carrier waves, thus allowing precise triggering of transition frequencies of the system using a small number of control parameters. This expansion yields a physically motivated continuous approximation of $f$ and, in tandem with a discretize-then-optimize approach, we leverage the symplectic and time-reversible St\"ormer-Verlet scheme to compute exact discrete gradients. The gradient is computed using the adjoint-state method, and the unitary evolution of Schr\"odinger coupled with the time-reversibility of the Störmer-Verlet scheme gives a memory-lean method.

The resulting optimal control software, for which I am a primary developer, is a package written in the Julia programming language and is named JuQBox. Preliminary numerical results indicate JuQBox can be orders of magnitudes (in some cases up to 300x) faster than competing software using GRAPE. Moreover, few parameters are needed to achieve gate fidelities of 99.9\% or greater which affords JuQBox scalability to much larger problems. The successful co-design of JuQBox has allowed the quantum group at LLNL to acquire control signals realizing an experimental fidelity of up to 99.4\%, \cite{XianLLNL}.

<img src="../files/wadg_example.png" width="900" />

This approach has been extended to "matrix-valued" weights, with applications in elastic and poroelastic wave propagation.  We have also utilized weight-adjusted mass matrices to construct efficient and provably stable high order DG schemes on curved simplicial meshes, as well as on quadrilateral and hexahedral meshes for multi-patch DG isogeometric analysis. On tensor product elements, weight-adjusted mass matrices provide the additional benefit of re-exposing a Kronecker product structure which is lost for a standard weighted finite element mass matrix.

### Selected relevant paper(s):
- [Optimal Control of Closed Quantum Systems via B-Splines with Carrier Waves](https://arxiv.org/abs/2106.14310)



 -->