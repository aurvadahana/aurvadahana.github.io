---
title: Understanding the Stability Criteria of a Numerical Scheme
categories: [Fluid-Thermo-Dynamics, CFD]
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

<a id="errorfn">Assuming that the above equation has a perturbation $$ T^* $$ (i.e., deviation from the actual $$ T $$) at nodes $$ i,\space i+1, $$ and $$ i-1 $$ at times $$ n $$ and $$ n+1 $$, and defining the error $$ \epsilon $$ as $$ T-T^* $$, we can write the following</a>

$$
T_{i}^{*(n+1)} = r(T_{i+1}^{*(n)}+T_{i-1}^{*(n)}) + (1-2r)T_{i}^{*(n)}
$$

$$
\begin{equation}
\epsilon_{i}^{n+1} = r(\epsilon_{i+1}^{n}+\epsilon_{i-1}^{n}) + (1-2r)\epsilon_{i}^{n}
\label{eq:1}
\end{equation}
$$

An exponential form is now assumed for the error function above, of the form $$ \epsilon = e^{at}e^{jkx} $$, where $$ j $$ is the complex number $$ \sqrt{-1} $$. This particular structure is a simplified form of a **Fourier Series** assumption which will not be explored in this post. The separation of the temporal and spatial variables into different exponents here allows the study of variation of the error of the dependent variable on both these dimensions. Also, since the interest of **Stability** is to analyze the variation of the error function over time, and not in space, the magnitude of the spatial exponent is constrained to 1 by the complex number added in the exponent. Hence, the entire responsibility of error propagation now rests on the temporal term.

Substituting this form of the error function in \eqref{eq:1}

$$
e^{a(t+\Delta t)}e^{jkx} = (1-2r)e^{at}e^{jkx}+r(e^{at}e^{jk(x+\Delta x)} + e^{at}e^{jk(x-\Delta x)}
$$

Defining an **Amplification factor**, $$ A = {e^{a(t+\Delta t)}}/{e^{(at)}} $$, which represents the amplified factor of the error in the same location, we get

$$
A = (1-2r)+r(e^{jk\Delta x}+e^{-jk\Delta x}) 
$$

$$
A=(1-2r)+2r\cos\theta
$$

$$
A=1-2r(1-\cos\theta)
$$

$$
A=1-4r\sin^2\frac{\theta}{2} 
$$

As part of the **Stability condition**, this Amplification factor should be less than (or equal to) one, since the error **not being amplified** is the criteria, which means even the same error being carried through time is permissible.

$$
|A| \le 1  \implies -1 \le 1-4r\sin^2\frac{\theta}{2} \le 1\\
r \ge 0 \space , \space r \le \frac{1}{2\sin^2\frac{\theta}{2}}
$$

Since all the parameters in $$ r $$ are anyway $$\ge 0$$, the first criterion is a default condition. Considering the second criterion, the maximum value of $$\sin^2(\theta/2)$$ ensures a minimum value of RHS. Satisfying the minimum of RHS is a sufficient condition for all other values of $$\theta$$. Hence, the stability criteria boils down to:

$$
\frac{\alpha\Delta t}{(\Delta x)^2} \le \frac{1}{2}
$$

This criterion shows that the 1D Unsteady heat equation discretized using FTCS (Forward in time, Central in Space) is a **conditionally stable** numerical scheme. 

## Examples of Stability Criteria applied to different Governing Differential Equations and Numerical Schemes

Various other examples of different numerical schemes applied to different Governing Differential Equations are shown below.

### 1. CTCS (Richardson's method) on 1D-transient heat equation

As the name suggests, the discretization of the 1D transient heat equation shall be performed centrally in time and centrally in space. Though it may appear that Central Difference generally performs better than Forward or backward schemes, it will be shown here that the Central difference is not always desirable.

The Governing Differential Equation is given by:

$$
\frac{\partial T}{\partial t} = \alpha \frac{\partial^2 T}{\partial x^2}
$$

Discretizing it central in time and space, we get:

$$
\begin{equation}
T_{i}^{n+1} - T_{i}^{n-1} = 2r(T_{i+1}^{n}-2T_{i}^{n} + T_{i-1}^{n})
\label{eq:2}
\end{equation}
$$

where,

$$
r = \frac{\alpha\Delta t}{(\Delta x)^2}
$$

Introducing the error function for the dependent variable as shown [here](#errorfn) eqref{eq:2}, we get:

$$
\epsilon_{i}^{n+1} - \epsilon_{i}^{n-1}= 2r(\epsilon_{i+1}^{n}-2\epsilon_{i}^{n}+\epsilon_{i-1}^{n})
$$

$$
(e^{a(t+\Delta t)}-e^{a(t-\Delta t)})e^{jkx} = 2re^{at}(e^{jk(x+\Delta x)}-2e^{jkx} + e^{jk(x-\Delta x)})
$$

Defining the Amplification factor, $$ A = {e^{a(t+\Delta t)}}/{e^{(at)}} $$

$$
A - \frac{1}{A} = 2r(e^{jk\Delta x}+e^{-jk\Delta x} -2)
$$

$$
A - \frac{1}{A} = 4r(\cos\theta - 1)
$$

$$
A - \frac{1}{A} = -8r\sin^2\frac{\theta}{2}
$$

$$
A^2+8Ar\sin^2\frac{\theta}{2}-1=0
$$

In this quadratic equation of $$A$$, it can be observed that the product of its roots is 1, implying if one of the roots is greater than one, another is less than one. Solving for $$A$$:

$$
A = \frac{-8r\sin^2\frac{\theta}{2}\pm\sqrt{64r^2\sin^4\frac{\theta}{2}+4}}{2} = -4r\sin^2\frac{\theta}{2}\pm\sqrt{16r^2\sin^4\frac{\theta}{2}+1}
$$

$$
|max(A)| = |-\beta-\sqrt{\beta^2+1}|\ge1
$$

because every term in $$\beta$$﻿﻿ is always positive.

This scheme is **Unconditionally Unstable**. Despite the usage of a Central difference scheme in time, the scheme is unstable compared to the Forward difference counterpart.


