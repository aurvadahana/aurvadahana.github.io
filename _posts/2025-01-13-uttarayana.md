---
title: The Uttarayana Confusion
categories: [General, Physics]
tags: [physics, general, history, solar]     # TAG names should always be lowercase
author: aurv
math: true
<!--- image: /assets/img/Vortex-street-1.jpgc--->
---

The 14th of January every year is usually celebrated in India as "Uttarayana", or the (start) of the northward movement of the sun, astronomically speaking. As the days of the year pass by, the orbit of the sun along our skies also shift. For example, when viewed from India, the Sun's orbit looks something like this through the year:

One can notice that the sunrise and west is not exactly along the true east or west, but is offset towards the north or south according to the time of the year. These "solar events" define the solstices and equinoxes. For the northern hemisphere:

![Desktop View](/assets/img/posts/2025-01-13-Uttarayana/Sun_orbit.gif){: width="380" }
_Sun's Orbit_

During the equinoxes, the sun rises and sets in the true east and west respectively. These occur during March ~20 (Vernal Equinox) and Sep ~22 (Autumnal Equinox). The other extremes are the Summer Solstice (Jun ~21) - when the days are the longest and sunrise occurs farthest towards northern side - and the Winter Solstice (Dec ~22) - when the days are the shortest, and sunrise occurs towards the southern offset of east.

The day of the Winter Solstice is ideally to be called the "Uttarayana", when the sun's orbit begins its "northward" movement. But why then is the day Sun enters Capricorn (Makara) called the day of Uttarayana?

## Sidereal vs Tropical Years

For this, a brief explanation into the definitions of "year" is required. There are two types of years - the sidereal and tropical.

The sidereal year (pronounced sigh-dee-real, "of the stars") is the time taken by the earth to come back to exactly the *same point* with respect to the Sun. In other words, it is the "true" year, measured with respect to the "stars" (or the infinitely distant viewer).

The "tropical" year - which the Gregorian calendar follows - is defined as the time taken by the earth from a particular orientation - to reach the exact same orientation with respect to the sun. Now, ideally both of them should be the same. But aren't because of a particular type of motion of the Earth.

The Earth has three types of motions - rotation about its own axis, revolution around the Sun, and precession - which is the wobbling of the Earth's axis itself.

![Desktop View](/assets/img/posts/2025-01-13-Uttarayana/Precession.png){: width="450" }
_Earth's Precession_

It is not rotation of the Earth, but a "rotation" of the axis itself. Note that the orientation (/angle) of the axis itself does not change. Also, it is a very slow process, and it takes the earth about 26000 years to complete one precession, i.e., the axis completes one circle.

It is this Precession which causes the difference between the Sidereal and Tropical years.

To visualise these motions collectively, let us ignore the Earth's rotation and view the orbit from the top-view.

![Desktop View](/assets/img/posts/2025-01-13-Uttarayana/Tropical_Sidereal_year.jpg){: width="520" }
_Tropical vs Sidereal Year_

As can be observed, the Sidereal year is the time taken for the earth to complete one revolution. And the tropical year is when the earth is back to the same orientation w.r.t the Sun. In clearer words, say the earth starts its revolution with the axis facing the Sun (point a), then the "same orientation" means the earth has to revolve and reach the spot where the axis faces towards the Sun the same way (point b). If not for Precession, this would be the same as the Sidereal year.

But why is this orientation relevant? Because the orientation of the axis to the Sun is what defines the seasons. E.g., the axis facing the sun means summer for the Northern Hemisphere, and it facing away brings forth Winter. So, summer would infact return at point b (according to tropical year, hence the name) and NOT point b (according to the Sidereal year). Ofcourse, the rate of precession shown in the image is exaggerated, and is much smaller compared to Earth's revolution, such that a -> b is almost unnoticeable over one year.

To mathematically compute this difference: say tthe angle covered by earth in a tropical year is $ \theta_e $, then

$$
\theta_e = \omega_r T_{trop}
$$

where $ \omega_r $ and $ T_{trop} $ are rate of revolution and Tropical year time, respectively.

The angle precessed by the Earth in this same time is:

$$
\theta_a = \pi - \omega_p T_{trop}
$$

where $ \pi $ is included since initial angle (at point a) is $ \pi $.

![Desktop View](/assets/img/posts/2025-01-13-Uttarayana/Tropical_Sidereal_math.jpg){: width="520" }
_Tropical Year and Precession_

From the figure above, it can be observed that $ \theta_e $ and $ \theta_p$ are related to each other, given by:

$$
\theta_e = \theta_p + \pi
$$

$$
\omega_r T_{trop} = \pi - \omega_p T_{trop} + \pi
$$



