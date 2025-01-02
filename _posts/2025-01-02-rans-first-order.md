---
title: RANS First-Order Models
categories: [Fluid-Thermo-Dynamics, CFD]
tags: [cfd, turbulence, RANS, turbulent-diffusion, Boussinesq, turbulent-viscosity]
author: aurv
math: true
---

## RANS

To model turbulence, one method is by Reynolds Averaging the Navier-Stokes equations which leads to the Turbulence Closure Problem in the RANS equations (as discussed [here](https://aurvadahana.github.io/posts/turbulence-and-its-modeling/)). RANS equations are given by:

$$
\frac{\partial \overline{u_i}}{\partial t} + \overline{u_j} \frac{\partial \overline{u_i}}{\partial x_j} = -\frac{1}{\rho} \frac{\partial \overline{p} }{\partial x_i} + \nu \frac{\partial^2 \overline{u_i}}{\partial x_j^2} - \frac{\partial \overline{u_i^{\prime}} \overline{u_j^{\prime}} }{\partial x_j}
$$

RANS can be solved by various methods, one of which is modeling the Reynolds Stress Tensor directly and is hence called _First-Order Models_. 

First-Order Models are modeled based on the assumption of similarity of the structure of the stress tensor between laminar and turbulent flows, i.e., based on an analogy between them. The stress tensor for laminar flows for Newtonian fluids is familiar to us:

$$
\tau_{ij} = \nu \left( \frac{\partial u_i}{\partial x_j} + \frac{\partial u_j}{\partial x_i} \right) - \frac{2}{3}\nu\frac{\partial u_k}{\partial x_k}\delta_{ij} = 2\nu S_{ij} - \frac{2}{3}\nu\frac{\partial u_k}{\partial x_k}\delta_{ij}
$$

where $\delta_{ij}$ is the kronecker delta and $S_{ij}$ is the Strain-Rate Tensor. For incompressible flows, the final term becomes zero due to continuity equation.

$$
\tau_{ij} = 2\nu S_{ij}, \qquad S_{ij} = \frac{1}{2} \left( \frac{\partial u_i}{\partial x_j} + \frac{\partial u_j}{\partial x_i} \right)
$$

## Boussinesq Hypothesis

In First-Order Models, it is hypothesised that, the Reynolds Stress Tensor has the same structure as the above case. For RST, the symbol of $\tau$ is used, since it is a _tensor_ and hence symbolising shear.

$$
\tau_{ij}^{turb} = -\overline{u_i^{'}u_j^{'}} = 2\frac{\mu_t}{\rho} S_{ij} - \frac{2}{3} \delta_{ij}k \ , \quad S_{ij} = \frac{1}{2} \left( \frac{\partial \overline{u_i}}{\partial x_j} + \frac{\partial \overline{u_j}}{\partial x_i} \right)
$$

It can be noticed here that the RST containing instantaneous velocities (and 6 unknown terms) is written in terms of the mean flow variables and a scalar quantity known as _turbulent viscosity_ or _eddy viscosity_. The purpose of these turbulence models is to compute this turbulent viscosity to get around the closure problem.

This particular hypothesis of relating the RST as a factor of the Strain Rate Tensor is called the _Boussinesq Hypothesis_. For Non-Newtonian fluids, the Boussinesq hypothesis has non-linear relation of the turbulent shear stress with the Strain tensor

## Turbulent Diffusion

- Why is a "viscosity" chosen as the proportionality constant? Because, turbulent by its nature is _dissipative_, but this dissipation is NOT _molecular diffusion_.
  - Turbulence is characterized by high Re and hence high inertial force over viscous force, thus the molecular diffusion is indeed very minute in comparison to advection or inertial force.
  - But turbulence IS dissipative. This diffusion is called _turbulent diffusion_, and is (hence) characterized by the turbulent viscosity. Infact, this mathematical assumption when substitued in the RANS term, the diffusion term becomes:

$$
\nu \frac{\partial^2 \overline{u_i}}{\partial x_j^2} - \frac{\partial \overline{u_i^{\prime}} \overline{u_j^{\prime}} }{\partial x_j} = \nu \frac{\partial^2 \overline{u_i}}{\partial x_j^2} + \frac{\partial}{\partial x_j} \left( \nu_t \left( \frac{\partial \overline{u_i}}{\partial x_j} + \frac{\partial \overline{u_j}}{\partial x_i} \right) - \frac{2}{3} \delta_{ij}k \right)
$$

$$
\left( \nu + \nu_t \right) \frac{\partial^2 \overline{u_i}}{\partial x_j^2} + 2\nu_t \frac{\partial}{\partial x_i} \frac{\partial \overline{u_j}}{\partial x_j} - \frac{2}{3} \frac{\partial}{\partial x_j} \left( \delta_{ij} k \right) = \left( \nu + \nu_t \right) \frac{\partial^2 \overline{u_i}}{\partial x_j^2} - \frac{2}{3} \frac{\partial}{\partial x_j} \left( \delta_{ij} k \right)
$$

  - Notice how the diffusion term is increased via the addition of the turbulent viscosity term. 
- Since this parameter is a mathematical concept to be used for CFD to manifest directly the dissipative propoerty of turbulence, it is NOT a propoerty of the fluid, but is a property of the FLOW.

## More on the Boussinesq Hypothesis

The Boussinesq Hypothesis is a "brutal and flawed" approximation of the actual physics, but it has been demonstrated that it is accurate if good standard practices are followed. It can be noticed above that the hypothesis contains a term proportional to the (specific) Turbulent Kinetic Energy for the principal components of the tensor (as represented by the kronecker delta). The significance of it is for consistency.

The RST is given by:

$$
\begin{equation}
\tau_{ij}^{turb} = -\overline{u_i^{\prime}} \overline{u_j^{\prime}} = - \left(\begin{array}{lll} \overline{u^{\prime} u^{\prime}} & \overline{u^{\prime} v^{\prime}} & \overline{u^{\prime} w^{\prime}} \\ \overline{v^{\prime} u^{\prime}} & \overline{v^{\prime} v^{\prime}} & \overline{v^{\prime} w^{\prime}} \\ \overline{w^{\prime} u^{\prime}} & \overline{w^{\prime} v^{\prime}} & \overline{w^{\prime} w^{\prime}}\end{array}\right)
\label{eq:1} \end{equation}
$$

As per the Boussinesq Hypothesis:

$$
\begin{equation}
\tau_{ij}^{turb} = -\overline{u_i^{'}u_j^{'}} = \frac{1}{\rho} \left(\begin{array}{lll} 2\mu_t S_{11} - \frac{2}{3}k &  2\mu_t S_{12} &  2\mu_t S_{13} \\ 2\mu_t S_{21} &  2\mu_t S_{22} - \frac{2}{3}k & 2\mu_t S_{23} \\ 2\mu_t S_{31} & 2\mu_t S_{32} & 2\mu_t S_{33} - \frac{2}{3}k\end{array}\right)
\label{eq:2} \end{equation}
$$

where,

$$
S_{11} = \frac{\partial u_1}{\partial x_1}, \quad S_{12} = \frac{1}{2}\left( \frac{\partial u_1}{\partial x_2} + \frac{\partial u_2}{\partial x_1} \right) \quad \mathrm{etc.}
$$

Taking the trace of tensor in \eqref{eq:1}:

$$
\tau_{ii}^{turb} = -\left( \overline{u_1^{\prime2}} + \overline{u_2^{\prime2}} + \overline{u_3^{\prime2}} \right)
$$

Taking the trace of tensor in \eqref{eq:2}:

$$
\tau_{ii}^{turb} = 2\nu_t\left(\frac{\partial u_i}{\partial x_i}\right) - 2k = -2k
$$

Equating the above two:

$$
k [m^2/s^2] = \frac{1}{2}\left( \overline{u_1^{\prime2}} + \overline{u_2^{\prime2}} + \overline{u_3^{\prime2}} \right)
$$

Which is consistent with the definition of (specific) TKE; hence the significance of the last term in the Boussinesq Hypothesis.

This Hypothesis is the most commonly used method to model turbulence. In order to compute the turbulent viscosity from it, various models are used:

## First-Order RANS Turbulence Models

![Desktop View](/assets/img/posts/2025-01-02-turbulence-and-its-modeling/Turbulence_Closure_Models.png){: width="500" }
_Reynolds Averaging Turbulence Models_

### 1. Zero-Equation Models

These are based on the Mixing Length Theory and simple Dimensional Analysis. Here, the turbulent viscosity is assumed as being proportional to the turbulent length scale times the turbulent velocity scale.

$$
\nu_t \left[ m^2/s \right] = l_s \left[ m \right]*u_s \left[ m/s \right]
$$

$$
\nu_t = l_o * l_o \frac{dU}{dy}
$$

where $l_o$ is the mixing length used as the length scale.

The Mixing Length is determined from experiments or the Boundary Layer Theory. Although, it should be noted that $l_o$ is NOT universal and depends on the nature of the problem.

#### Pros

- Easy to implement
- Fast
- Accurate for simpler flows where $l_o$ is determined experimentally

#### Cons

- When $l_o$ is unknwon (which is most engineering problems), results are very inaccurate. Especially for flows with separation or re-circulation.

### 2. One-Equation Models

The guess for the velocity scale in the mixing length model of the Zero-Equation model can be improved further. It can be characterized using the (specific) Turbulent Kinetic Energy.

$$
u_s = \sqrt k
$$

where,

$$
k = \frac{1}{2} \overline{u_i^{\prime}} \overline{u_i^{\prime}}
$$

But again, we do not know $u_i^{\prime}$. Hence an equation for TKE is directly developed.
