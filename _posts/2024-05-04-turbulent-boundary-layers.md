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

The first one in the Turbulent stress terms is the normal stress component, while the remaining two are the shear stresses. These terms are called Turbulent "stresses" because they come in the **stress** term of the Navier Stokes equations.

<div id="fn1" style="position: absolute; left: -9999px;">Placeholder</div>
## Notes

[[1]](#ffn1)
Remember that,

$$
\overline{u^{'}} = \frac{1}{T}\int_{0}^{T} \left( u - u^{'} \right) \ \mathrm{dt} = \overline{u} - \overline{\overline{u}} = \overline{u} - \overline{u} = 0
$$

But,

$$
\overline{u'}^{2}} = \frac{1}{T}\int_{0}^{T} \left( u - \overline{u} \right)^{2} \ \mathrm{dt} = \frac{1}{T} \int_{0}^{T} \left( u^{2} + \overline{u}^{2} - 2u\overline{u} \right) \ \mathrm{dt} \ne 0
$$

