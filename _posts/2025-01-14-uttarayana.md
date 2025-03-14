---
title: The Uttarayana Confusion
categories: [General, Physics]
tags: [physics, general, solar]     # TAG names should always be lowercase
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

The sidereal year (pronounced sigh-dee-real, "of the stars") is the time taken by the earth to come back to exactly the *same point* with respect to the Sun (i.e., to complete one revolution). In other words, it is the "true" year, measured with respect to the "stars" (or the infinitely distant viewer).

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

The angle precessed by the Earth's axis in this same time is:

$$
\theta_p = \pi - \omega_p T_{trop}
$$

where $ \pi $ is included since initial angle (at point a) is $ \pi $, and $ \omega_p$ is rat of precession of Earth's axis.

![Desktop View](/assets/img/posts/2025-01-13-Uttarayana/Tropical_Sidereal_math.jpg){: width="520" }
_Tropical Year and Precession_

From the figure above, it can be observed that $ \theta_e $ and $ \theta_p$ are related to each other, given by:

$$
\theta_e = \theta_p + \pi
$$

$$
\omega_r T_{trop} = \pi - \omega_p T_{trop} + \pi = 2\pi - \omega_p T_{trop}
$$

Simplifying,

$$
\begin{equation}
T_{trop} = \frac{2\pi}{\left( \omega_r + \omega_p \right)}
\label{eq:1} \end{equation}
$$

Naturally, the sidereal year is defined as:

$$
T_{side} = \frac{2\pi}{\omega_r}
$$

since it is defined as the time taken to complete one revolution. And, for precession

$$
T_{p} = \frac{2\pi}{\omega_p}
$$

Substituting this in \eqref{eq:1},

$$
T_{trop} = \frac{2\pi}{\left( \frac{2\pi}{T_{side}} + \frac{2\pi}{T_p} \right) }
$$

$$
\begin{equation}
\frac{1}{T_{trop}} = \frac{1}{T_{side}} + \frac{1}{T_{p}}
\label{eq:2} \end{equation}
$$

For example, if the Earth precessed every one year, then (geometrically/astronimically), tropical year should be half that of the sidereal year. This holds true as per \eqref{eq:2} as well,

$$
\frac{1}{T_{trop}} = 1 + 1 = 2 \implies T_{trop} = \frac12
$$

As per the actual numbers, $T_p$ = 25772 years! Substituting this in \eqref{eq:2},

$$
\frac{1}{T_{trop}} = 1 + \frac{1}{25772} = \implies T_{trop} = \frac{25772}{25773} \mathrm{years} = 0.9999611997051 \mathrm{years}
$$

In terms of days, the Sidereal year is 365.256363004 days. Hence, the tropical year is 365.242190949 days. The difference is = 0.01417205459 days or 20'24.465516576", or 20.4077586096 mins.

i.e., it takes $T_{trop}$ time for sun to come back to same position at same time and day when viewed from the earth, but it takes the stars 20.4077586096 mins longer to reach the same position. Since we are a part of Earth (with the precession etc.), we feel the effect of the "tropical year" in terms of seasons and movement of the sun, but not of the stars.

## Uttaryana and Makara Sankranti

The Makara Sankranti is a "Sidereal event", since it involves the entry of Sun into Capricorn/Makara constellation. While the Uttarayana (as explained above) is a "tropical event". This means that in a tropical calendar, the Uttarayana would be constant, while Makara Sankranti would constantly change. But in the sidereal year, it would be exact opposite.

Ofcourse, it is impractical to follow the Sidereal year for day-to-day activities, since our days are governed by the Sun's motion, with the seasons, days and nights, etc. Hence, as per the tropical calendar, the Uttarayana or Winter Solstice is a constant at around Dec ~22, while the Makara Sankranti shifts "forward" every (tropical) year, since it takes the stars and constellation *longer* (by 20.4077586096 mins/year) to reach the same place every year.

As of now, the exact time for Winter Solstice / Uttarayana (as in 2024) is ~ Dec 21 2:51pm, and Sun enters Capricorn by Jan 14, 08:54am. The exact difference being 23 days, 18h, 3mins. Why then is the Uttarayana considered the same as Makara Sankranti in the Hindu custom?

Probably because, *at one point in time* they were indeed coinciding, but the Makara Sankranti shifted forward along the tropical year, while the general Hindu belief still considered them the same. We can generally calculate at what point in history the 2 may have conincided.

Current difference between Uttarayana and Makara Sankranti = 23D 18H 3M = 34203 mins

The time delay between Sidereal and Tropical years = 20.4077586096 mins/year.

Dividing, 34203 / 20.4077586096 = ~1675.98 years or ~1676 years. i.e., at approximately 1676 years in the past (or ~348AD), the two events may have been coinciding. If one checks the general Panchangs available online at around Dec 21 or 22 ~348AD, this is indeed true.

This is also the period where India advanced significantly in the Gupta Era. Possibly had several astronomical developments as well, as the civilisation and literatures stabilized. For e.g., the famous Surya Siddhanta, or the Chandravakyas of Varunchi, or the famous astronomer Aryabhata, are all dated around this period. It could be possible that the belief of Uttarayana and Makara Sankranti carried forward among the public at large and continued to as it is today. Although, the Sidereal and Tropical Years are indeed mentioned int he astronomical treatises of Indian history, hence the knowledge of this indeed is preserved in literature. Would be digging those out in the near future, maybe


