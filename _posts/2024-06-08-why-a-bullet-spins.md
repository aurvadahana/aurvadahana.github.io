![image](https://github.com/aurvadahana/aurvadahana.github.io/assets/164757444/7730ad5e-2bdf-47b6-92ad-180fa60a4874)---
title: Why a Bullet is spun
categories: [General, Physics]
tags: [physics, general]
author: aurv
math: true
hidden: true
---

## Stability and Centre of Gravity

First of all, the center of gravity of an object is a point where the net weight of the object **appears** to act, and is not actually acting in the "real" world. This makes it easier for calculation and qualititative understanding of general physics related to the same.

Stability refers to how "stable" a system is, in this context, with respect to gravity. An object is in **Stable equilibrium** if any kind of external moment (or, displacement) which acts on the body causes the body to tend to return to its original position before being disturbed.

For example, a cone is placed on a flat surface with its circular shape as the base. Any small displacements tend to restore the cone back to its original position due to the counteracting moment on it. This moment is the couple created due to the loss of collinearity between the reaction force (which acts on the area of contact between object and flat surface), and the weight (which acts downwards from the center of gravity).

![Desktop View](/assets/img/posts/2024-06-08-why-a-bullet-spins/stable_equi.png){: width="300" }
_Stable Equilibrium_

When the same cone is placed on its tip as the base, it is in a state of **Unstable Equilibrium**. Even slight negligible deflection, can tend to topple the cone over to a more stable state. This is because, the couple which is create due to the loss of collinearity is not counteracting but is acting against any tendency for the object to reach its original state.

![Desktop View](/assets/img/posts/2024-06-08-why-a-bullet-spins/unstable_equi.png){: width="300" }
_Unstable Equilibrium_

As a general rule of thumb for visual understanding, if the line drawn vertically from the COG lies outside of the object's "base", then the object topples over due to lack of any counter-acting moment.

## The Spinning Top

A non-spinning top placed on its tip is much like the unstable equilibrium case above. In reality, this slight disturbance could be due to various reasons: placing the cone on its tip requires perfect accuracy so as to not topple it over without any external disturbance. Even so, it requires perfect symmetry of the cone as well, which is not possible due to manufacturing defects.

### Principle of Angular Momentum

When a top is spinning, it has angular momentum; a quality which depends on the top's rotational speed and its moment of inertia. The universal rule of Angular Momentum is its conservation; it tends to remain constant unless acted on by an external torque. One thing to note here is that Angular Momentum is a **vector**, i.e., it has both direction and magnitude. And its conservation implies resistance to change in both these aspects of Angular Momentum.

Mathematically, the Angular Momentum is given by:

$$
\vec{L} = I\vec{\omega}
$$

where:

- I is the momentum of inertia of the object. It is the measure of how the mass is distributed relative to the axis it is measured from (typically, axis of rotation). A higher value means it has its mass distributed further away from axis of rotation (remember the **I** shape of railway tracks, to prevent their bending). Also, as the name itself suggests, this quantity means resistance of the object to **rotational** motion; a higher value implies requirement of higher force for causing rotation about the axis it is measured from

- $$ \vec{\omega} $$ is the angular velocity **vector**. which indicates the speed and **direction** of rotation. Its direction is measured by the right hand thumb rule, and the Angular Momentum gets its direction from this quantity.

The principle of conservation of Angular Momentum states that in the absence of any external **torque** (notice how the Newton's laws are just restated for rotational motion), the total angular momentum of a system remains constant. Mathematically:

$$
\frac{\mathrm{d}\vec{L}}{\mathrm{d}t} = \vec{\tau}_{ext}
$$

On the absence of external torque:

$$
\frac{\mathrm{d}\vec{L}}{\mathrm{d}t} = 0 \implies \vec{L} = \mathrm{constant}
$$

### Effect of Gyroscopy

When an object spins, it has angular momentum. WIthout effect of gravity, friction and air drag, not only does it tend to keep spinning, but it also keeps its axis intact. This is why <a target="_blank" href="https://www.youtube.com/watch?v=xGdH0lwFOiM">this</a> happens, for example.

A spinning top is similarly governed. Consider blowing on a top as in the below image, along direction in red which is rotating in the green rotation.

![Desktop View](/assets/img/posts/2024-06-08-why-a-bullet-spins/blowing_spinning_top.png){: width="300" }

Counter-intuitively, the top moves in the direction shown in red, instead of along the direction of blowing. The direction of the gyroscopic effect is defined by the cross product of the spin axis ($$ \vec{a} $$) and torque axis or direction of external force (($$ \vec{b} $$), and is hence given by the right-hand rule.

![Desktop View](/assets/img/posts/2024-06-08-why-a-bullet-spins/RHT.png){: width="300" }
_Right-Hand rule for cross products_

Similarly, gravity acts uniformly along a spinning top. As it loses its angular momentum due to air drag and friction, the top tilts slightly, causing a loss of collinearity between the reaction force on the base and the weight acting along the center of gravity, as in the figure (a) below (note that it represents only one particular instance of a rotating top). This "gyroscopic moment" is equivalent to a couple acting like in the figure (b) below, with equal and opposite forces on opposite faces of the top.

Now, this "gravitational couple" is very small at first, and gains magnitude only as the top slows down due to loss of momentum from air drag and friction. If the angular momentum is high (or, the spinning rate is high), the effect of gyroscopy is also high, and hence the top tends to stay spinning and precessing longer.
