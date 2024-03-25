---
title: Understanding the Stability Criteria of a Numerical Scheme
categories: [cfd]
tags: [cfd, numerical schemes]     # TAG names should always be lowercase
author: aurv
math: true
<!--- image: /assets/img/Vortex-street-1.jpgc--->
---

The basic requirements of a given numerical scheme are to be **consistent**, **stable**, and its ability to **converge** to a physically consistent solution. For linear problems (i.e., which do not involve multiples of the dependent variable or its derivatives), **convergence** is assured by the fulfillment of **consistency** and **stability** (this theorem is called the **Lax Equivalence Theorem**). In this post, checking the stability criteria of a given numerical scheme will be discussed.

## What is the Stability Crtieria?

The term "stability", in the context of numerical methods, refers to the behavior of a numerical solution over time. It is a measure of whether the numerical approximation remains bounded and doesn't exhibit undesirable behaviors such as unbounded growth, oscillations, or erratic behavior. This can be quantified by observing whether a given perturbance in the numerical scheme at a particular iteration or node is amplified through the progression of iterations or the time steps to provide physically inconsistent and unbounded solutions.

## How to Analyse Stability?

The **stability** condition of a numerical scheme is often assessed through a mathematical analysis known as **Von Neumann Stability Analysis**. This method employs the Fourier series representation of the error function associated with the dependent variable. It allows one to examine how this error function, or perturbation, evolves over time and space within the numerical scheme.

For the purpose of demonstration, a 1D unsteady heat-diffusion equation is chosen. The PDE is as shown below

$$
\frac{\partial T}{\partial t} = \alpha \frac{\partial^2 T}{\partial x^2}
$$

Discretizing the above PDE **Forward in time** and **central in space (FTCS)**, we get

$$
T_{i}^{n+1} = r(T_{i+1}^{n}+T_{i-1}^{n}) + (1-2r)T_{i}^{n}
$$

where,

$$
r = \frac{\alpha\Delta t}{(\Delta x)^2}
$$

Assuming that the above equation has a perturbation $$ T^* $$ (i.e., deviation from the actual $$ T $$) at nodes $$ i,\space i+1, $$ and $$ i-1 $$ at times $$ n $$ and $$ n+1 $$, and defining the error $$ \epsilon $$ as $$ T-T^* $$, we can write the following

