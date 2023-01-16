---
layout: post
title: "Daily, Seasonal and Weather-Driven Patterns in Utility Solar Generation"
date: "2023-01-22"
hide: true
excerpt_separator: <!--more-->
---

In this post, I use grid-level data to explore a number of real-world considerations that the electricity market must take into account 
when incorporating utility-scale solar power into the mix of generation.  These include: 

- The daily alternation between daytime solar generation and nighttime non-generation
- The annual cycle of higher generation in the summer (longer days / higher sunlight angle) than in the winter (shorter days / lower angle)
- Reductions in output on days when the weather is cloudy (this can vary by geography)
- Incorporating this variable profile into the grid where demand for electricity itself fluctuates, but not always in step with solar generation.  

The net result of these factors will be manifested in either (1) energy storage requirements and/or (2) having additional generation capacity 
(e.g., natural gas plants) that can fill in the gaps when solar generaiton is lower.  

<!--more-->

## Hourly Generation Data from the EIA

Data in this post comes from the U.S. Energy Information Administration.  The EIA's [Hourly Electric Grid Monitor](https://www.eia.gov/electricity/gridmonitor/dashboard/electric_overview/US48/US48),
has hourly granularity by region on a number of variables.  These include total usage and generation in the region 
(balanced by import / export from neighboring regions), as well as a detailed look at generation by type of source (e.g., coal, nuclear, 
natural gas, solar, wind).  

An example of the latter is shown below, which shows the daily generation cycle of solar, days where power output is 
lower due to weather, and how natural gas plants are ramped up and down to offset the solar generation cycle. 

<img src="/assets/images/post4_generation_sample.png"  width="70%" height="70%">

In much of this post I focus my efforts of the region of Nevada where the balancing authority is NV Power.  This is geographically the majority 
of the state but excludes the area around Las Vegas itself.  I choose this region because it is mostly desert, and so weather should not obstruct
solar generation on too many days, which enables me to get a better picture of idealized / unobstructed solar productivity.

## Ideal Solar Generation: Methodology

My goal is to create a model of solar generation in Nevada to match against electricity demand, which requires a picture of how it fluctuates over 
hours of the day, and times of the year (daylight hours and sun position).  Because the real-world output in any data set is muddled by weather, my 
first step is to strip out this variability.  Weather intermittency can be re-added later as a driver of storage needs.

My simplifying assumptions are that: 
- Maximum solar generation capacity is uniform throughout each calendar month (i.e., the day length and angle of the sun are consistent)
    - This is likely close to true for winter and summer months (the day length at Copper Mountain, NV varies from 9h 23m to 9h 35m in December and from 15h 01m to 15h 14m) and a less good approximation for spring and fall (March is 11h 19m to 12h 37m) 
- In each month there are at least 5 days of unobstructed generation, from which I can derive a picture of ideal output 
    - While there are periods of clouds and rain in Nevada (in January 2023 there are both from a west coast atmospheric river), the fact that the state is mostly desert makes this a good approximation, even accounting for the fact that there are multiple generation sites with slightly different conditions

![December Days](/assets/images/post4_NVPowerdailychart.png)

So for each month I averaged the hourly solar generation of the top-5 days in that month (for December, the chosen days are the ones on the orange
line above, and the other blue-line days are ignored).   The results for December are below: 

![December by Hour](/assets/images/post4_month12_hourly.png)

A full December day's worth of generation in this region is ~10,400 MWh, roughly 7.5 hours worth of the maximum output of 1,383 MWh.   In terms of 
actual production hours -- there are 9 hour slots in the day with at least 10% of max production, and 7 hours of full or mostly-full capacity (60% or 
better).  Of 9.5 hours of daylight in December, about 2 of them are "lost" to the sun being too low in the sky to generate meaningful power. 

By comparison, the total productivity across all days in December 2022 was ~8,300 MWh per day, meaning that weather (or other outages) reduced output by
20%.  It matters to achieving reliability and the cost of energy storage needed to offset intermittency whether this impact was driven by a 
larger number of medium-output days,or a smaller number of days with very low generation, and we'll look at this data in the next section.

One small feature that I didn't expect is that the peak generation hours are 10 to 11 a.m. and 1 to 2 p.m., with the hours in between slightly 
lower.  Solar noon at this time of year is around 11:40 a.m.  I don't know what is going on here, but perhaps panel positioning is at a 
somewhat lower angle than the highest in the sky that the sun gets, to better capture low-angle hours in the morning and afternoon.  

This chart shows the same exercise for June, the month of the summer solstice. 

![June by Hour](/assets/images/post4_month6_hourly.png)

A full June day's worth of generation in this region is ~21,300 MWh, roughly 11.4 hours worth of the maximum output of 1,860 MWh.  June maximum 
generation is **double** that of December, with roughly equal contributions from more hours of daylight and stronger sunlight (higher sun angle) 
when the sun does shine.  

Another way of expressing this is as a capacity factor: in peak summer, one can say that utility-scale solar is working **half** the time on good 
days (11.5 hours of full power).   In the darkest winter, the output is halved again, and is working at only a **quarter** of its physical capacity.  
All of this before weather impact. 

Finally, In 2022, there was less loss to weather in June than in December: across all days, average total daily generation was ~19,700, only a 7.5% 
loss from the best days.

## Ideal Solar Generation: Full Year Results
