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

![June and December](/assets/images/post4_NVPowerdailychart.png)

So for each month I averaged the hourly solar generation of the top-5 days in that month.  The charts for June and December 2022 intuitively show that
the top-5-dates methodology (represented by the orange lines) indeed seems to capture the "full output" of the solar installations at work.  The days 
where the blue line dips materially are filtered out.   

The intraday generation results for June are below: 

![June by Hour](/assets/images/post4_month6_hourly.png)

A full June day's worth of generation in this region is ~21,300 MWh, roughly 11.4 hours worth of the maximum output of 1,860 MWh.  In terms of 
actual production hours -- there are 14 hour slots in the day with at least 10% of max production, and 11 hours of full or mostly-full capacity (60% 
or better).  Of the 15 hours of daylight in June, about 3 of them are "lost" to the sun being too low in the sky to generate meaningful power.

By comparison, the average productivity across all days in June 2022 was ~19,700 MWh, meaning that weather (or other outages) reduced output
by 7.5%.  It matters to achieving reliability and the cost of energy storage needed to offset intermittency whether this was caused by a large number of 
medium-output days, or a smaller number of days with very low generation, and we'll look at this data in the next section. 

This chart shows the same exercise for December, the winter solstice month.

![December by Hour](/assets/images/post4_month12_hourly.png)

A full December day's worth of generation in this region is ~10,400 MWh, roughly 7.5 hours worth of the maximum output of 1,383 MWh.   In terms of 
actual production hours -- 9 had at least 10% power and 7 had at least 60% or better.   So of the 9.5 hours of December daylight, 2 were lost.
The weather impact appears to have been much harsher in December.  Average productivity across all days was ~8,300 MWh, a decrease of 20% from 
full capacity. 

Since these two months are the bookends of the year from a sun perspective, note that December's solar productivity was roughly **half** that of June. 
THis was driven both by the reduced hours of power generation (December at 66% of June) and reduced "maximum" generation when the sun was at its 
highest (December at 74% of June).

Another way of expressing this is as a capacity factor: in peak summer, one can say that utility-scale solar is working **half** the time on good 
days (11.5 hours of full power).   In the darkest winter, the output is halved again, and is working at only a **quarter** of its physical capacity.  
All of this before weather impact. 

## Ideal Solar Generation: Full Year Results

Next up is the "full capacity" chart (based on the top 5 days of each month) for every month in the year.  

![All months](/assets/images/post4_all_months_hourly.png)
