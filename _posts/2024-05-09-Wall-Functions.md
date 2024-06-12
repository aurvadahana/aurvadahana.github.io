---
title: Wall Function Treatment
categories: [Fluid-Thermo-Dynamics, CFD]
tags: [cfd, turbulence, log-law, boundary layer, wall functions]
author: aurv
math: true
---

Continuing from the <a target="_blank" href="https://aurvadahana.github.io/posts/turbulent-boundary-layers/">post</a> about derivation of the logarithmic region of the turbulent boundary layer, this post aims to elaborate on how CFD codes compute the wall shear stress for various scenarios of mesh refinement.

Note that this is just a basic introduction into wall functions. Modern CFD codes use advanced wall functions such as the **Spalding Function** (named <a target="_blank" href="https://www.afs.enea.it/project/neptunius/docs/fluent/html/th/node99.htm">**Standard Wall Functions**</a> in ANSYS Fluent). Also the concept of $$y^+$$ and wall-functions apply to only turbulent boundary layers, and not its laminar counterparts.

## Motivation for use

When a domain is discretised, generally speaking, the solution between the cells are interpolated in a linear fashion. Hence, regions where the solution variable changes rapidly (i.e., has a high gradient), a finer mesh setting is required to capture the solution in a piece-wise linear fashion.

One region where the solution variable has high gradient is the velocity near the wall, which also directly influences the wall shear-stress computation. Hence, ideally we need quite a fine mesh to capture the region near the wall, otherwise the solution is not resolved appropriately, as in images below.

![Desktop View](/assets/img/posts/2024-05-09-Wall-Functions/Piece-wise linear refined.png){: width="300" }
_Refined mesh near the wall to capture the solution_

![Desktop View](/assets/img/posts/2024-05-09-Wall-Functions/Piece-wise linear coarse.png){: width="500" }
_A coarse mesh fails to capture the solution properly_

This is a huge problem in CFD, since all of the impact on the entire fluid domain is because of the presence of the walls and the boundary layers, hence it is crucial that the solution is captured properly.

But sometimes, say for high Re flows, the boundary layer is much smaller, making the requirement of the mesh refinement also very fine, the orders of $$y^+$$ of 1 requires very fine mesh which makes the computation time also very high, which may not be affordable or feasible in many cases. So, there needs to be a way to have a coarse mesh but still have an accurate solution, and this naturally involves a non-linear interpolation between the first cell and the wall as in the below image. This involves the utilisation of the **wall-functions**

![Desktop View](/assets/img/posts/2024-05-09-Wall-Functions/Non-linear.png){: width="350" }
_Non-linear interpolation using wall functions_

## Logarithmic Dependence of $$y^+$$ with velocity

Recall that the variation of velocity profile in a turbulent boundary layer is linear at first, and then changes to logarithmic as the solution progresses from the viscous sublayer to the logarithmic region. This relation could be utilised for the wall-functions.

![Desktop View](/assets/img/posts/2024-05-04-turbulent-boundary-layers/cover_turbulent_bl.png){: width="500" }
_Velocity profile variation with y+_

The above function is plot below:

![Desktop View](/assets/img/posts/2024-05-04-turbulent-boundary-layers/Intersection point.png){: width="600" }
_Intersection point of the two functions_

Mathematically, this can be expressed as

$$
U^+ = \begin{cases} 
y^+ & y^+ < 10.67 \\
\frac{1}{\kappa}\ln y^+ + B & y^+ > 10.67
\end{cases}
$$
