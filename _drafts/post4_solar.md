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
natural gas, solar, wind).  An example of the latter is shown below, which shows the daily generation cycle of solar, days where power output is 
lower due to weather, and how natural gas plants are ramped up and down to offset the solar generation cycle. 

<img src="/assets/images/post4_generation_sample.png"  width="70%" height="70%">

## Ideal Solar Generation: Methodology

My goal is to create a model of solar generation in Nevada to match against electricity demand, which requires a picture of how it fluctuates over 
hours of the day, and times of the year (daylight hours and sun position).  Because the real-world output in any data set is muddled by weather, my 
first step is to strip out this variability.  Weather intermittency can be re-added later as a driver of storage needs.

My simplifying assumptions are that: 
- Maximum solar generation capacity is uniform throughout each calendar month (i.e., the day length and angle of the sun are consistent)
    - This is likely close to true for winter and summer months (the day length at Copper Mountain, NV varies between 9h 23m and 9h 35m in December) and a less good approximation for spring and fall (March is 11h 19m to 12h 37m) 
- In each month there are at least 5 days of unobstructed generation, from which I can derive a picture of ideal output 
    - While there are periods of clouds and rain in Nevada (in January 2023 there are both from a west coast atmospheric river), the fact that the state is mostly desert makes this a good approximation, even accounting for the fact that there are multiple generation sites with slightly different conditions

![December Days](/assets/images/post4_december.png)

So for each month I averaged the hourly solar generation of the top-5 days in that month (for December, the chosen days are the ones on the orange
line above, and the other blue-line days are ignored). 

## Ideal Solar Generation: Full Year Results
