---
title: "Discrete Adjoints for Accurate Numerical Optimization with Application to Quantum Control"
collection: publications
permalink: /publication/2020-10-22-QC
excerpt: 'We consider optimizing control functions for realizing logical gates in a closed quantum systems, where the evolution of the state vector is governed by the time dependent Schrödinger equation.'
date: 2020-01-04
venue: 'arXiv'
paperurl: 'http://fortinog.github.io/files/QC.pdf'
---
We consider optimizing control functions for realizing logical gates in a closed quantum systems, where the evolution of the state vector is governed by the time dependent Schrödinger equation. This is an optimal control problem where the objective function consists of two parts: the infidelity of the quantum gate and an integral in time over highly energetic states. We write Schrödingers equation as a Hamiltonian system in terms of the real and imaginary parts of the state vector and discretize the system with the Strömer-Verlet scheme, which is a partitioned Runge-Kutta method. We develop a compatible scheme for the adjoint differential equation, which allows the gradient of the discretized objective function to be calculated exactly. This allows all components of the gradient to be calculated at the cost of solving two Schrödinger systems, independently of the number of parameters in the control functions. The control function are expanded in a series of B-spline basis functions with built-in carrier waves. The interior point L-BFGS algorithm from the IPOPT package is used to minimize the objective function, subject to amplitude constraints on the parameter vector. The method is applied to Hamiltonians that model the dynamics of a super-conducting qudit. By calculating the spectrum of the Hessian at the optima we find that many eigenvalues are small and that a handful are negative, indicating that the optimization problem is non-convex.

[Download paper here](https://arxiv.org/pdf/2001.01013.pdf)

<!-- Recommended citation: Your Name, You. (2009). "Paper Title Number 1." <i>Journal 1</i>. 1(1). -->