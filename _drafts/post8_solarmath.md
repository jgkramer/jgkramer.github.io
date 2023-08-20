---
layout: post
title: "Why Winter Solar Generation Is a Two-Humped Camel: Solar Trigonometry"
date: "2023-07-10"
hide: true
author: "Jared Kramer"
excerpt_separator: <!--more-->
---

<head>
  {% include latex.html %}
</head>
 
Nerd alert.  This post uses math (trigonometry and linear algebra) of solar angles and the physical attributes of utility-scale solar panels to explain the shape of the graph below.  The graph shows Nevada's utility-scale solar generation by hour of the day, for each month. 

![solar](/assets/images/post8_NV_solar_by_month.png)

Three features of the data are notable:

1.  Long hours of consistently high output in summer.  Of the roughly 14 hours per day of production in June, 10 of those are at least 90% of the peak: the intensity drops off only during the two hours after sunrise and two hours before sunset.  

2.  The "dip" in mid-day in winter months.  The best solar generation does not occur when the sun is highest in the sky at mid-day, but in peaks before and after.

The data is consistent with **single-axis** solar tracking panels adjusts the position of a solar panel along one axis of rotation (i.e., east to west) to make the sun's rays strike the panel as close to perpendicular as possible.  By pointing east in the morning, rotating to be horizontal at mid-day, and then pointing towards the west in the afternoon, a tracking panel can lengthen the period of time that the sun's rays strike at a near-perpendicular angle to the panel.  

In the winter, the two-peak shape occurs because the sun is overall quite low in the sky.  In the mid-day the sun is in the south.  The best the panel can do is to be horizontal, but the sun is low enough that the angle of incidence is not very perpendicular.  The best angles occur in morning and afternoon when the sun is further east and west, and the panel can be adjusted to point east and west.  The dip does not occur in the summer because the elevation of the sun is high enough that a horizontal panel has a good angle of incidence.  

The strong hours in the summer are particularly long because the sun rises in the north-east, and gets to due east around 9:00 a.m. (8 a.m. standard time).   At this point an east-west orientation can point a panel directly at the sun.   Ih the afternoon, the sun gets to due west around 5:00 p.m. (4 p.m. standard time).  So the hours where the panel can get a nearly-perpendicular angle to the sun span more than this 8-hour period.

### A Simplified Model of Solar Panels

I don't have enough information to mathematically model the absolute power output of solar panels in Nevada.  However, with an analysis of the angle of the sun and the position of panels (plus some data about the intensity of the sun's rays) we can approximate at the output of panels relative to their maximum capacity, and so can validate the shape of the generation curves above. 

The collection of solar radiation by a flat PV panel is based on the [flux](https://en.wikipedia.org/wiki/Flux) of the sun's rays into the surface: sunlight landing perpendicular to the surface generate the most energy; sunlight parallel to the surface generates no energy.  Hence we want to measure the angle between that vector and the normal (perpendicular) vector $\vec{N}$ to the panel's surface.   If those vectors have zero angle between them, the sun is shining perpendicular to surface, and energy is maximized.   Higher angle means the sun is shining less directly on the panel.   Mathematically then, the solar energy that the panel can capture is proportional to the [cosine](https://www.e-education.psu.edu/eme812/node/896) of the angle between the sun's position vector and the normal vector of the solar panel. 

### Sun Position

Imagine our solar panel is at the origin in a 3-dimensional plot.   The vector of sun's position is described with two angles.  

1.  The **elevation** angle of the sun above the horizon, which I denote as $\phi$ (this can go from 0&deg; at the horizon to 90&deg; directly overhead)
2.  The **azimuth** angle, which is the direction on the horizon that the sun is over, ranging over 0&deg; for North, to 90&deg; East, 180&deg; South, 270&deg; West and up to 360&deg; to go back to North.

<div style="padding: 0; margin: 0;">
  <img src="/assets/images/post8_angles_2.png" alt="Image" width="655" height="409">
</div>

We'll eventually want to find the angle between the sun's position vector and the vector normal to a solar panel on the ground, so we'll derive the (x, y, z) coordinates of the sun's position on a unit sphere from the angles.   From triangle trigonometry, the z-coordinate is simply 1 times the sine of the elevation angle, $sin \phi$.  Similarly, the length of the distance from the origin to the projection of the sun onto the xy plane is $cos \phi$.  The x and y coordinates are then the projections of that point onto the x and y axis using the azimuth angle: the x-coordinate is $cos \phi\~sin \theta$ and the y-coordinate is $-cos \phi\~cos \theta$ (the negative sign comes from my chosen orientation of the positive y-axis as being south).   Thus the position vector of the sun ends up as the unit vector $[cos \phi\~sin \theta,\~-cos \phi\~cos \theta,\~sin \phi\]$.

Finding these two angles for the sun's position at any location on Earth at any time is a [straightforward computation](https://gml.noaa.gov/grad/solcalc/azel.html) based on longitude, latitude, time of day and day of year (and timezone).  

Here's a few examples: 



### Single-Axis Tracking Panels

For a single panel, solar yield is maximized by **dual-axis** tracking: which can be rotated on two axes (e.g., horizontal and vertical) to point at any point in the sky.  But most utility scale solar arrays (including those in Nevada) are **single-axis** trackers, and look like the below near Las Vegas:

![solar array](/assets/images/post8_nellis-solar-array.jpeg)

The panels sit in long parallel rows and can be most efficiently managed and spaced by rotating them together on a single axis of rotation (i.e. rotating a single bar rotates the entire row of panels).  Here, a horizontal axis that allows the panels to point east in the morning, tilt towards horizontal to point overhead at mid-day, then point towards the west in the evening, will be optimal.

### Finding the Angle of Incidence and then Optimizing It

Imagine that we tilt our solar panel an angle $\alpha$ away from vertical, with positive $\alpha$'s toward the east and negative $\alpha$'s toward the west.  Again assuming a unit sphere model of the sky, the east-west orientation means that the direction the panel points lies on the xz plane, at the unit vector $[sin \alpha, 0, cos \alpha]$.

<div style="padding: 0; margin: 0;">
  <img src="/assets/images/post8_angles_3.png" alt="Image" width="655" height="409">
</div>

So we are looking for the angle, $\beta$, between the dashed blue vector where the panel is pointing and the yellow vector representing the sun's position.  But our ultimate target is actually $cos\~\beta$ to determine the solar flux onto the panel.  Because the panel vector and the solar position vector are both unit vectors, $cos\~\beta$ is simply the **dot product** of these two vectors.  Hence: 

$cos\~\beta = sin\~\alpha\~cos\~\phi\~sin\~\theta + cos\~\alpha\~sin\~\phi\~\~\~\~(1)$

The solar operator only contols the tilt angle of the panels $\alpha$.  So to maximize solar power generation, I assume that the utilitty sets $\alpha$ to maximize $cos\~\beta$, i.e., we set $\frac{\partial}{\partial{\alpha}}cos\~\beta = 0$.   Taking the partial derivative of the above, we are looking to find $\alpha$ such that.

$0 = cos\~\alpha\~cos\~\phi\~sin\~\theta - sin\~\alpha\~sin\~\phi$.   

Rearranging and dividing by $cos\~\alpha\~sin\~\phi$ gets us that at the optimal tilt angle $\alpha$,

$tan\~\alpha\ = \frac{sin\~\theta}{tan\~\phi}$ 

For this article's analysis, I don't need the optimal $\alpha$ itself.  To estimate the solar output at different times of day, with different sun posiitons, I just need to solve for the value of $\cos\~\beta$ at the optimal $\alpha$. The expression for $cos\~\beta$ uses both $\cos\~\alpha$ and $sin\~\alpha$, both of which can be derived from $tan\~\alpha\$: 

$cos\~\alpha\ = \dfrac{1}{\sqrt{1 + tan^2\~\alpha}} = \dfrac{tan\~\phi}{\sqrt{tan^2\~\phi + sin^2\~\theta}}$, and

$sin\~\alpha\ = \dfrac{tan\~\alpha}{\sqrt{1 + tan^2\~\alpha}} = \dfrac{sin\~\theta}{\sqrt{tan^2\~\phi + sin^2\~\theta}}$.

These two expressions can now be substituted into the expression of $cos\~\beta$ from equation (1): 

$cos\~\beta = \dfrac{sin^2\~\theta\~cos\~\phi}{\sqrt{tan^2\~\phi + cos^2\~\theta}} + \dfrac{tan\~\phi\~sin\~\phi}{\sqrt{tan^2\~\phi + cos^2\~\theta}}$, which ultimately simplifies to: 

$cos\~\beta = \sqrt{1 - cos^2\~\theta\~cos^2\~\phi}$

A quick gut check validates this formula: when the sun is due East or West, $\phi$ is 90&deg; or 270&deg;, $cos\~\phi$ is 1 or -1, so the entire expression simplifies to $cos\~\beta = 1$.  This makes sense because an East-West tilting panel can point straight at the sun and receive maximum solar flux.   This is similarly true when the sun is directly overhead, with $\theta =$ 90&deg;, $cos\~\phi = 1$ and $cos\~\beta = 1$.

### Adjusting for Lower Solar Intensity at Lower Angles

The last piece of this analysis is to reflect the fact that sunlight is less intense when the sun is lower in the sky -- even with a panel pointed directly at the sun.  This is because sunlight has to pass through more atmosphere (dimming it) at lower angles rather than higher angles.  The intensity of the sunlight reaching a panel pointed directly at the sun (the panel surface is perpendicular or `normal` to the sunlight rays) is called [Direct Normal Irradiance](https://en.wikipedia.org/wiki/Solar_irradiance) ("DNI") and can be measured empirically at given locations.

The [National Solar Radiation Database](https://nsrdb.nrel.gov/data-viewer) provides data sets of solar radiation metrics at various locations on the earth's surface for every day in 10-minute increments.  The chart below shows "Clearsky" DNI in Las Vegas from 2021, with all days in a given month averaged into a single time series (both to smooth out irregularitize and to match the solar generation data we started with). 

![DNI](/assets/images/post8_NV_dni_by_month.png)

### All Together

Finally, we can estimate total solar generation over the course of any day in Nevada by: 

- Computing the solar angle positions $\phi$ and $\theta$ for the day and time at that location
- From those solar angles, determining the best angle to position a single-axis solar panel at to point most directly at the sun, and then what proportion of solar energy -- i.e., $cos\~\beta$ -- can be captured at that angle
- Multiplying this proportion by the total direct solar radiation (DNI) reaching the ground at that time

The results of this exercise are shown below. 

![Modeled Results](/assets/images/post8_NV_modeled_by_month.png)

These **modeled** curves match many of the features of the **actual** solar generation curves shown at the beginning, suggesting that my model of how utility solar panels work in Nevada is accurate. 

(1) the extra long hours of near-peak generation throughout many hours of the day in summer that comes from being able to track the sun while it is high in the sky appears in the June curve above. 

(2) The double-peak in winter months, with a trough in generation at mid-day when an east-west tilting panel cannot get as good an angle on the sun low in the sky in the south, as it can in the late morning / early afternoon when the sun, still low, is more east or west in the sky. 

The modeled outputs also capture a third feature of 




 








