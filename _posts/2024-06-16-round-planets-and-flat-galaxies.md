---
title: Why ar planets spherical, while galaxies are flat? 
categories: [General, Physics]
tags: [physics, general, planets]     # TAG names should always be lowercase
author: aurv
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

Note how certain words are made bold. This is because, if an object is small enough (think human beings), its own mass is too small to be affected by gravity, and the material is able to withstand its own mass. But if the same human got quite large enough, the effect of gravity cannot be ignored. That is why it is quite unrealistic to depict planetary-scale sizes of superheroes in movies and anime, since while the strength scales linearly, and the strength of the bones scales as per the cross-sectional area (say the 2nd order), gravity is a volumetric phenomena, and would grow in the third power.

## Rotating spheres

Now let us bring rotation into the picture. As explained before, an initial angular momentum is imparted on the collection of gases which is conserved on the formed planet. This leads to the planet to rotate about an axis. (More about the conservation of AM <a target="_blank" href="https://aurvadahana.github.io/posts/why-a-bullet-spins/">here</a>).

Due to rotation, the centrifugal force acts on the surface of this planet. The centrifugal force acts *outward*, and tends to throw the mass "out". This centrifugal force tends to decrease the gravitational force experienced by an object on the surface.

This centrifugal force depends on the spin of the planet, and the mass of the objct experiencing it. But the gravitational force depends on the mass of the object as well as the planet itself.

Mathematically,

$$
F_{centrifugal} = m \omega^2 r
$$

$$
F_{gravity} \sim mg
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
