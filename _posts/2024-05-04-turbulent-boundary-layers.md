---
title: Turbulent Boundary Layers - The Log-Law
categories: [Fluid-Thermo-Dynamics, CFD]
tags: [cfd, turbulence, log-law, boundary layer]
author: aurv
math: true
image: /assets/img/posts/2024-05-04-turbulent-boundary-layers/cover_turbulent_bl.png
---

This post will try to consolidate my learnings about the turbulent boundary layers, in particular, the theory leading up to the log-law.

Here, two important assumptions are that of the external flat plate scenario, and that the wall is smooth.

## Turbulent Shear Stress

The shear stress is the rate of transportation of momentum per unit area, in the direction normal to that of the flow. From the Navier-Stokes' x-momentum equation:

$$
\rho \frac{\mathrm{d}u}{\mathrm{d}x} = -\frac{\mathrm{\partial}p}{\mathrm{\partial}x} + \frac{\mathrm{\partial}\sigma_{xx}}{\mathrm{\partial}x} + \frac{\mathrm{\partial}\tau_{yx}}{\mathrm{\partial}y} + \frac{\mathrm{\partial}\tau_{zx}}{\mathrm{\partial}z}
$$

<div id="ffn1" style="position: absolute; left: -9999px;">Placeholder</div>
In this particular case, the changes in the quantities of interest in the z-direction is negligible, hence the dominant direction for the shear stress is the y-direction. Also similarly in the RANS[[1]](#fn1):

$$
\rho \frac{\mathrm{d}U}{\mathrm{d}x} = -\frac{\mathrm{\partial}\overline{p}}{\mathrm{\partial}x} + \mu\nabla^2 U - \rho \left[ \frac{\mathrm{\partial}\overline{u^{'}u^{'}}}{\mathrm{\partial}x} + \frac{\mathrm{\partial}\overline{u^{'}v^{'}}}{\mathrm{\partial}y} + \frac{\mathrm{\partial}\overline{u^{'}w^{'}}}{\mathrm{\partial}z} \right] + \rho g_x
$$

Rearranging,

$$
\rho \frac{\mathrm{d}U}{\mathrm{d}x} = -\frac{\mathrm{\partial}\overline{p}}{\mathrm{\partial}x} + \rho g_x + \frac{\mathrm{\partial}}{\mathrm{\partial}x} \left( \mu\frac{\mathrm{\partial}U}{\mathrm{\partial}x} - \rho \overline{u^{'}} \overline{u^{'}} \right) + \frac{\mathrm{\partial}}{\mathrm{\partial}y} \left( \mu\frac{\mathrm{\partial}U}{\mathrm{\partial}y} - \rho \overline{u^{'}} \overline{v^{'}} \right) + \frac{\mathrm{\partial}}{\mathrm{\partial}z} \left( \mu\frac{\mathrm{\partial}U}{\mathrm{\partial}z} - \rho \overline{u^{'}} \overline{w^{'}} \right)
$$

The equation is of the form $$ \mathrm{Inertia} = \mathrm{Pressure Gradient} + \mathrm{Body Force} + \mathrm{Turbulent Stresses} $$

The first one in the Turbulent stress terms is the normal stress component, while the remaining two are the shear stresses. The **Turbulent Kinetic Energy** is associated with the Reynolds **Normal** Stresses.

These terms are called Turbulent "stresses" because they come in the **stress** term of the Navier Stokes equations.

The total shear is, hence,

$$
\tau = \mu \frac{\mathrm{\partial}U}{\mathrm{\partial}y} - \rho u' v' = \tau_{lam} + \tau_{turb}
$$

## Regions in the Turbulent Boundary Layer

At about $$ y < 0.1 \delta $$, Laminar/Viscous shear dominates. This **inner layer** velocity is given by:

$$
u_{\mathrm{inner}} = f\left( y, \tau, \rho, \underline{\mu} \right)
$$

- Notice that the inner layer is dependent on viscosity and is independent of the free-stream velocity or the boundary layer thickness. Hence it is called the **viscous layer**
- The outer layer is independent of viscosity, since it is at a sufficient distance away from the wall.

At $$ y < 0.1\delta $$, $$\tau = \tau_{wall}$$

By dimensional analysis, the shear stress has dimensions of $$[\mathrm{density}] * [\mathrm{velocity}]^2$$

Hence, a velocity $$u_{\tau}$$ is defined such that

$$
\tau = \rho u_{\tau}^2
$$

where, $$u_{\tau}$$ is the **Friction Velocity**

$$
u_{\tau} = \sqrt{\frac{\tau}{\rho}}
$$

This velocity is used for non-dimensionalising as well.

$$
u^+ = \frac{U}{u_{\tau}} \ \ y^+ = \frac{yu_{tau}}{\nu}
$$

<div id="ffn2" style="position: absolute; left: -9999px;">Placeholder</div>
where $$y^+$$ is like a **local Reynolds number**. A measure of viscous and turbulent transport at different distances from the wall[[2]](#fn2).

$$
u_{\mathrm{outer}} = f\left( y, \tau, \rho, \underline{U_{\mathrm{inf}}}, \underline{\delta} \right)
$$

## Notes

<div id="fn1" style="position: absolute; left: -9999px;">Placeholder</div>
[[1]](#ffn1)
Remember that,

$$
\overline{u^{'}} = \frac{1}{T}\int_{0}^{T} \left( u - u^{'} \right) \ \mathrm{dt} = \overline{u} - \overline{\overline{u}} = \overline{u} - \overline{u} = 0
$$

But,

$$
\overline{u'}^{2} = \frac{1}{T}\int_{0}^{T} \left( u - \overline{u} \right)^{2} \ \mathrm{dt} = \frac{1}{T} \int_{0}^{T} \left( u^{2} + \overline{u}^{2} - 2u\overline{u} \right) \ \mathrm{dt} \ne 0
$$

<div id="fn2" style="position: absolute; left: -9999px;">Placeholder</div>
[[2]](#ffn2)
Recollect that low $$y^+$$ models are also called **low Re** models

