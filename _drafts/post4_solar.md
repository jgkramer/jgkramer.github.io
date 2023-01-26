---
layout: post
title: "Daily, Seasonal and Weather-Driven Patterns in Utility Solar Generation"
date: "2023-01-22"
hide: true
excerpt_separator: <!--more-->
---

In this post, I use grid-level data to explore a number of real-world considerations that the electricity market must take into account 
when incorporating utility-scale solar power into the mix of generation.  This post will explore: 

- **The Difference Between Generating Capacity and Actual Output**: Unlike some sources (e.g., Nuclear, Coal), which when active can more or less always generate electricity at their maximum capacity, solar does not.  This post will take noisy utility generation data from U.S. regions and use that to both get an estimate of what generation capacity solar generation has at scale, and then see the impact of weather and other factors. 
- **The Daily Cycle**: Solar generates electricity only during the day, contributing from between 7-8 hours in winter to 11-12 hours in summer.  On average this is less than half the day because of minimal generation in the hour just after sunrise or before sunset
- **The Seasonal Cycle**: Both because of shorter daylight hours and lower solar intensity, solar panels in winter generate meaningfully less juice than in summer.  This post goes into details.
- **Differences in Geography**:  While there is some variability across the U.S. in seasonal / the daily cycle, geography also brings climate and weather pattern differences.   I will look at a few solar-heavy U.S. states to see just how big these differences are. 

My ultiamte goal is to create a mathematical model of solar energy as a necessarily variable electricity **supply**.   This can then be matched up against 
the demand for electricity, which itself fluctates.   How the supply and demand fluctuates match up will impact (1) what energy storage may be useful
in an electricity grid and/or (2) what other sources of generation (e.g., natural gas plants) can fill gaps when solar generation does not match demand
well. 

<!--more-->

## Hourly Generation Data from the EIA

Data in this post comes from the U.S. Energy Information Administration.  The EIA's [Hourly Electric Grid Monitor](https://www.eia.gov/electricity/gridmonitor/dashboard/electric_overview/US48/US48),
has hourly granularity by region on a number of variables.  These include total usage and generation in the region 
(balanced by import / export from neighboring regions), as well as a detailed look at generation by type of source (e.g., coal, nuclear, 
natural gas, solar, wind).  

An example of the latter is shown below, which shows the daily generation cycle of solar, days where power output is 
lower due to weather, and how natural gas plants are ramped up and down each day to offset the solar generation cycle.   
The chart also shows how on some days, solar generation is weak, implying that natural gas production doesn't ramp down as much. 

<img src="/assets/images/post4_generation_sample.png"  width="70%" height="70%">

In much of this post I focus my efforts on the Nevada balancing authority, Nevada Power.  I choose this region because it is mostly desert, 
and so weather should not obstruct solar generation on too many days, which enables me to get a better picture of idealized / unobstructed 
solar productivity.

## Ideal Solar Generation: Methodology

My goal is to create a model of solar generation in Nevada to match against electricity demand, which requires a picture of how it fluctuates over 
hours of the day, and times of the year (daylight hours and sun position).  

My first simplifying assumption is that maximum solar generation capacity is uniform throughout each calendar month (i.e.,t he day length and angle
of the sun are consistent within the month).   This is likely to be close to true for winter and summer months (the day length at Boulder City, NV
varies from 9 hours 42 minutes to 9:53 in December and from 14:26 to 15:36 in June), and a less good approximation for spring and fall (March is 11:25
to 12:33).  

My second task is to try to filter out weather-driven variability to get a sense of what solar generation can produce if there were perfect weather 
every day. 

![2022](/assets/images/post4_NVPowerDailyChart.png)

The chart above shows how meaningful weather-driven inconsistency is even in a desert area for solar generation.   The noisy blue line is actual 
output by day in 2022.   The orange line connects the **top 3** days of output in each month, and could be a starting point for estimating 
maximum generation capacity.   But this approach has the shortcoming that even the best days in a month could still have a couple of hours of cloud 
cover and so still systematically understate solar capacity in that month.   In the chart above, July and August (monsoon season in the desert 
southwest with frequent clouds and even rain) may have this problem, as even the orange curve falls short of where I expect given the levels of 
April through June. 

A more robust approach is, for each of the 24 hours in the day, to find the instances where solar generation during **that hour** was among the top 3
of generation in that specific time slot.  If one day has morning clouds and afternoon sun, while a second day has morning sun and afternoon clouds, 
I can compute the solar generation capacity in the period using the first day's afternoon hours and the second day's morning hours. 

Here's what happens in July 2022 using the two alternative approaches: 

![July 2022](/assets/images/post4_NVPowerJulyDays.png)

Deriving July capacity for each hour of the day by taking the best 3 hours in that time slot throughout the month (mixing and matching days) does indeed
produce a more complete estimate of solar utility capacity.   Visible from the light blue lines the first part of the month had weak morning generation, 
but strong afternoon generation.   Later parts of the month had some days with strong morning generation but inconsistent afternoon generation.   
Taking the best 3 complete days results in a capacity estimate of 20,200 MWh, with a better morning than afternoon profile (this methodology seems to 
avoid the early-July days).   Taking the best 3 hours for each hourly slot increases this to 21,500 MWh -- 6% higher and much more likely a more 
complete picture of what generation could be in July.

## Seasonality of Ideal Solar Generation 

I apply this same methodology to every month of the year, and the result is the following "ideal" solar generation in Nevada for each month of the year,
ignoring weather obstructions or other outages. 

![All months](/assets/images/post4_NVPower_all_hourly.png)

There are two key patterns to note: compared to the winter months, solar in the summer can generate much more electricity than in the winter, **both**
because: 

1. There are more hours in the day where the sun is shining.   In June, generation covers 13 hours: starting from the 5-6am slot and ending in the 6-7pm slot.[^1].  Contrast December, where generation runs about 8 hours: from the 7-8am hour until the 3-4pm hour.  

2. The maximum generation per hour is **higher in the summer**: presumably due to the higher angle of the sun in the sky. 

<STYLE TYPE="text/css">
<!--
TH{font-family: Arial; font-size: 8pt; text-align: center;}
TD{font-family: Arial; font-size: 8pt; text-align: center;}
--->
</STYLE>
<table>
    <col> <colgroup span="1"></colgroup><colgroup span="3"></colgroup>
    <tr>
        <th colspan="1" scope ="colgroup" style="background-color: #D6EEEE"></th>
        <th colspan="3" scope ="colgroup" style="background-color: #D6EEEE">Full Capacity</th>
    </tr>
    <tr>
        <th scope="col" style="background-color: #D6EEEE">Month</th> 
        <th scope="col" style="background-color: #D6EEEE">Daily Generation Capacity (MWh)</th> 
        <th scope="col" style="background-color: #D6EEEE">Max Hourly Rate (MWh)</th> 
        <th scope="col" style="background-color: #D6EEEE">Hours of Full Generation</th>
    </tr>
<tr>
  <th scope="col" style="background-color: #D6EEEE">June</th>
 <td>22,515</td><td>1,952</td><td>11.5</td></tr>
<tr>
  <th scope="col" style="background-color: #D6EEEE">December</th>
 <td>11,689</td><td>1,505</td><td>7.8</td></tr>
</table>

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


Some macroscopic patterns are intuitive and symmetrical.   December and January appear to be the lowest production months, followed by November and 
February.  The late spring and summer are a bit strange -- although June is a strong month, May look even better, and July looks weak compared to April 
(perhaps because monsoon season brings frequent morning clouds?).

<STYLE TYPE="text/css">
<!--
TH{font-family: Arial; font-size: 8pt; text-align: center;}
TD{font-family: Arial; font-size: 8pt; text-align: center;}
--->
</STYLE>
<table>
    <col> <colgroup span="1"></colgroup><colgroup span="3"></colgroup><colgroup span ="5"></colgroup>
    <tr>
        <th colspan="1" scope ="colgroup" style="background-color: #D6EEEE"></th>
        <th colspan="3" scope ="colgroup" style="background-color: #D6EEEE">Full Capacity</th>
    </tr>
    <tr>
        <th scope="col" style="background-color: #D6EEEE">Month</th> 
        <th scope="col" style="background-color: #D6EEEE">Daily Generation Capacity (MWh)</th> 
        <th scope="col" style="background-color: #D6EEEE">Max Hourly Rate (MWh)</th> 
        <th scope="col" style="background-color: #D6EEEE">Hours of Full Generation</th>
    </tr>
<tr>
  <th scope="col" style="background-color: #D6EEEE">December</th>
 <td>22,515</td><td>1,952</td><td>11.5</td>
    </tr>
<tr>
  <th scope="col" style="background-color: #D6EEEE">December</th>
 <td>11,689</td><td>1,505</td><td>7.8</td>
</tr></table>

### Different Geographies


First chart -- multi-series stacked bar chart.  For each state, monthly bars for "unobstructured capacity" and "2022 actual production".    This will
show seasonal cycle in cpacity, and also whether weather affects some geographies more than others. 

Next chart - bars of 90+, 60-90, 30-60, 0-30.   Meant to show whether weather is "some days really bad" or not.   in different geographies. 

could do hours per day by differentn states, but that's kinda boring. 



[^1] All times have converted to Standard Time for comparability, which is why the sunset time in June may seem early for those used to Daylight Savings time. 



