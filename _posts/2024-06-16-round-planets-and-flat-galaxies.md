---
title: Why are planets spherical, but galaxies flat? 
categories: [General, Physics]
tags: [physics, general, planets]     # TAG names should always be lowercase
author: aurv
math: true
image: /assets/img/posts/2024-06-16-round-planets-and-flat-galaxies/saturb_rings.avif
---

The other day I just stumbled on that image of shanideva with his rings, and it made me wonder something I should have naturally thought of much before: why are the planets round while the bigger celestial objects like the galaxies, or even the solar system, so amaazigly two dimensional? Why flat of all the other shapes they could take?

The answer to this is quite simple in its fundamental principles, and I thought I'd just jot it down here.

## Equilibrium

One of the fundamental "principles" in physics is that of equilibrium; every object tries to maintain itself in an equilibrium unless an external force of some sort acts on it. During the initial stages of the fomration of a planet (for example), it was just gases collecting together due to its own mass, and because of the initial momentum imparted from The Big Bang, or whatever explosion of energy from it, a net angular momentum.

If you really think about it, every ("collection" of) object(s) has a net angular momentum simply because of this initial Bang. No object is truly "stationary", since through conservation of linear and angular momentum, every object has a tendency to remain in its state of motion, linear or rotational.

So, when a mass of gas come together, and assuming there is no external interaction as of yet, this collection too has an angular momentum, which becomes more defined as they come together and reach a state of equilibrium.

This collection slowly forms into rocky structures and eventually into a planet (apologies to shanideva for the implied atheism), which is drawn to itself due to the self-weight. But, why does it necessarily have to form a spherical shape?

## The Sphere

Let us ignore the angular momentum, the "spinning", for a moment, and imagine the planet as a collection of rocky "blocks". Now, the gravitational forces have a spherical symmetry, i.e., the force acts towards the center of the object, equal in all directions. In other words, at a distance x away from the center, the gravitational force is equal in all directions at the same distance.

The only way the planet can reach a state of equilibrium with such a - **large enough** - symmetric force acting through it, is for the planet itself to achieve a spherical shape **by overcoming its own mass**. This is called the "**Hydrostatic Equilibrium**"

Think of it in blocks; one block being placed on top of the other along a radial direction through the center, with the block closer to the center experiencing the pressure from all the blocks above it. If the planet were flat, i.e., two-dimensional, then the "blocks" closer to the center would not have been in equilibrium, and would have deformed more "out" of this two-dimensional plane, since there is no other block on the sides for it to exert pressure on. Hence, even if you start off as a 2D shape, wih a large enough gravitational force, it would naturally form a spherical shape such that the blocks closer to the center is able to achieve equilibrium only because it exerts (and also experiences) pressure from the blocks on its sides along the azimuthal axis.

This is the same reason why water droplets - in the absence of gravity - are perfectly spherical due to their own cohesive forces.

Going back to the earlier statement:

> The only way the planet can reach a state of equilibrium with such a - **large enough** - symmetric force acting through it, is for the planet itself to achieve a spherical shape **by overcoming its own mass**.

Note how certain words are made bold. This is because, if an object is small enough (think human beings), its own mass is too small to be affected by gravity, and the material is able to withstand its own mass. But if the same human got quite large enough, the effect of gravity cannot be ignored. (That is why it is quite unrealistic to depict planetary-scale sizes of superheroes in movies and anime, since while the strength scales linearly, and the strength of the bones scales as per the cross-sectional area (say the 2nd order), gravity is a volumetric phenomena, and would grow in the third power.)

Anyway, this is the reason why water droplets become spherical rather easily, because as a fluid it has lesser strength against its cohesive forces.

One can find lumpy non-spherical objects in the solar system - like the asteroid 52 Europa (not to be confused with the much larger and denser moon of Jupiter) with a mean diameter of ~320km, while the ~930km 1 Ceres (which alone accounts for 25% of the asteroid belt's total mass, and hence labeled a Dwarf Planet) is spherical.

![Desktop View](/assets/img/posts/2024-06-16-round-planets-and-flat-galaxies/a_few_asteroids.png){: width="400" }
_Images of a few Asteroids. Notice the shapes_

Naturally, the material of the object also matters. Mimas is only about ~396km in (mean) diameter but is still significantly spherical. This is because it is composed majorly of water ice, with a mean density of ~1150kg/m<sup>3</sup>, only about half density of 1 Ceres and a third of 52 Europa.

![Desktop View](/assets/img/posts/2024-06-16-round-planets-and-flat-galaxies/Mimas_Cassini.jpg){: width="500" }
_Mimas imaged by the Cassini orbiter, 2010, with the large Herschel Crater on the right_

## Rotating Spheres

Now let us bring rotation into the picture. As explained before, an initial angular momentum is imparted on the collection of gases which is conserved on the formed planet. This leads to the planet to rotate about an axis. (More about the conservation of AM <a target="_blank" href="https://aurvadahana.github.io/posts/why-a-bullet-spins/">here</a>).

Due to rotation, the centrifugal force acts on the surface of this planet. The centrifugal force acts *outward*, and tends to throw the mass "out". This centrifugal force tends to decrease the gravitational force experienced by an object on the surface.

This centrifugal force depends on the spin of the planet, and the mass of the objct experiencing it. But the gravitational force depends on the mass of the object as well as the planet itself.

Mathematically,

$$
F_{centrifugal} = m \omega^2 r
$$

<div id="ffn1" style="position: absolute; left: -9999px;">Placeholder</div>
and the gravitational force, [[1]](#fn1)

$$
F_{gravity} = mg
$$

where $$m$$ is the mass of the object.

The net gravitational force experienced by an object along the equator:

$$
F_{net} = m \left( g - \omega^2 r \right)
$$

$$
g_{eff} = g - \omega^2 r
$$

Means, closer to the poles ($$r = 0$$), the gravity is maximum, while the equator has minimum gravity

For this reason, fast-spinning planets such as Jupiter and Saturn, which complete a rotation about their axis in 10 and 10.5 hours respectively, the equatorial diameter is considerably longer than the polar diameter, giving the planet a bulged out shape near the equator. For instance, the equatorial diameter of Saturn is 120,536km compared to a polar diameter of 108,728km (about 11% higher!). Naturally means, an object experiences 11% lesser gravity at the equator in Saturn compared to the poles, this is only about 0.3% for earth.

Another example is the star <a target="_blank" href="https://www.skyatnightmagazine.com/advice/altair">Altair</a> in the Aquila constellation, which spins about its axis every 8.9hours and its equatorial diameter is 25% larger than at the poles.

## Orbiting Bodies

Let us go one step further, to the orbiting rocks and ice which make up the rings of Saturn. In this case, the gravitational force (or more accurately, the resulting centrepetal force) is completely balanced out by the centrifugal force due to the rotation

Mathematically,

$$
m \omega^2 r = G \frac{mM}{r^2}
$$

The angular velocity in such a state of equilibrium is given by:

$$
\omega = \sqrt{G\frac{M}{r^3}}
$$

This equation is valid for an object when the centrifugal force is matched by the gravity-induced-centrepetal force.

## Flat Galaxies

Now, we have looked into:

- Why planets are spherical
- Why objects stay on a planet's surface due to gravity
- Why some objects orbit around a planet

But why are these orbits always two-dimensional? Rings of various planets, the solar system, the galaxies; why are all of them flat?

Remember that the collection of gases has a net angular momentum initially. But in this case, due to them being spread quite further apart, the effect of gravity is not strong enough to pull them together to form planets. Rather, they start colliding and cancel each other out. And when an equilibrium is reached, assuming no external disturbance (which is not that hard to come by in this vast expanse of space), they cancel each other out until everything is rotating uniformly within an axis; the **same axis of rotation as its initial net angular momentum**, thus conserving the angular momentum of this isolated system.

But in the case of planets, the gravitational pull is much more dominant, and due to spherical symmetry, they form spherical shapes.

## What about Saturn Rings?

The objects within the Saturn's rings too are wide apart and have negligible gravity to form an own sphere. Neither do they collapse into Saturn (as said before) because of the balance of gravitational centrepetal and centrifugal forces, quite similar to the case of all planets revolving around the Sun; even though they are rotated by gravity, the gravity itself isn't strong enough to collapse them because they're balanced by the centrifugal forces 




## Notes

<div id="fn1" style="position: absolute; left: -9999px;">Placeholder</div>
[[1]](#ffn1)

The gravitational force is given by:

$$
F = G \frac{mM}{R^2}
$$

where $$G = 6.674 \ \mathrm{x} \ 10^{-11} \mathrm{m^3 kg^{-1} s^{-2}}$$

When the object is on the surface of the planet, the distance $$R$$ is equal to sum of the radiuses of both the objects. But since the smaller object has a much smaller size, $$R$$ is the radius of the planet itself.

In this context, the acceleration due to gravity $$g$$ is defined such that

$$
F = mg = G \frac{mM}{R^2}
$$

$$
g = G \frac{M}{R^2}
$$

Hence, the acceleration due to gravity depends on the mass of the planet, and is inversely dependent on its radius.
