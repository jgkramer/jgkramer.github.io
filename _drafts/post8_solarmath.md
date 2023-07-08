---
layout: post
title: "Solar Geometry"
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

Two features of the data are unintuitive:

1.  Long hours of consistently high output in summer.  Of the roughly 14 hours per day of production in June, 10 of those are at least 90% of the peak: the intensity drops off only during the two hours after sunrise and two hours before sunset.  

2.  The "dip" in mid-day in winter months.  The best solar generation does not occur when the sun is highest in the sky at mid-day, but in peaks before and after.

The data is consistent with **single-axis** solar tracking panels adjusts the position of a solar panel along one axis of rotation (i.e., east to west) to make the sun's rays strike the panel as close to perpendicular as possible.  By pointing east in the morning, rotating to be horizontal at mid-day, and then pointing towards the west in the afternoon, a tracking panel can lengthen the period of time that the sun's rays strike at a near-perpendicular angle to the panel.  

In the winter, the two-peak shape occurs because the sun is overall quite low in the sky.  In the mid-day the sun is in the south.  The best the panel can do is to be horizontal, but the sun is low enough that the angle of incidence is not very perpendicular.  The best angles occur in morning and afternoon when the sun is further east and west, and the panel can be adjusted to point east and west.  The dip does not occur in the summer because the elevation of the sun is high enough that a horizontal panel has a good angle of incidence.

### Solar Angles

To analyze the input of light onto a solar panel, we first need to describe the position of the sun in the sky.  This is done with two angles: 

1.  The **elevation** angle of the sun above the horizon, which I denote as $$\phi$$ (this can go from 0 degrees at the horizon to 90 degrees directly overhead)
2.  The **azimuth** angle, which is position on the 

<img src="/assets/images/post8_angles_1.png" alt="Image" width="900" height="496">




### Single-Axis Tracking Panels

For a single panel, solar yield is maximized by **dual-axis** tracking: which can be rotated on two axes (e.g., horizontal and vertical) to point at any point in the sky.  But most utility scale solar arrays (including those in Nevada) are **single-axis** trackers, and look like the below near Las Vegas:

![solar array](/assets/images/post8_nellis-solar-array.jpeg)

The panels sit in long parallel rows and can be most effiienntly managed and spaced by rotating them together on a single axis of rotation.   Here, a horizontal axis that allows the panels to point east in the morning, tilt towards horizontal to point overhead at mid-day, then 

###
 




The strong hours in the summer are particularly long because the sun rises in the north-east, and gets to due east around 9:00 a.m. (8 a.m. standard time).   At this point an east-west orientation can point a panel directly at the sun.   Ih the afternoon, the sun gets to due west around 5:00 p.m. (4 p.m. standard time).  





