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

There are two key patterns to note: compared to the summer months, solar generation in the winter can only generate about **half as much** electricity
per day as in the summer, for two reasons.  

1. The maximum generation per hour is **higher in the summer** due to the higher angle of the sun in the sky.  Full sun in December generates only ~77% as much power as full sun in June.  

2. There are more hours in the day where the sun is shining.   In June, generation runs from the 5-6am slot until the 6-7pm slot.[^1].  Contrast December, where generation runs from the 7-8am hour until the 3-4pm hour.  Both of these stats are in-line with the length of daylight hours in the summer and winter outlined above (15+ and 9+). 

[^1] All times have converted to Standard Time for comparability, which is why the sunset time in June may seem early for those used to Daylight Savings time. 


<STYLE TYPE="text/css">
<!--
TH{font-family: Arial; font-size: 9pt; text-align: center;}
TD{font-family: Arial; font-size: 9pt; text-align: center;}
--->
</STYLE>
<table>
    <col> <colgroup span="1"></colgroup><colgroup span="4"></colgroup>
    <tr>
        <th colspan="1" scope ="colgroup" style="background-color: #D6EEEE"></th>
        <th colspan="4" scope ="colgroup" style="background-color: #D6EEEE">Full Capacity</th>
    </tr>
    <tr>
        <th scope="col" style="background-color: #D6EEEE">Month</th> 
        <th scope="col" style="background-color: #D6EEEE">Daily Generation Capacity (MWh)</th> 
        <th scope="col" style="background-color: #D6EEEE">Max Hourly Rate (MWh)</th>
        <th scope="col" style="background-color: #D6EEEE">Hours Active per Day</th>
        <th scope="col" style="background-color: #D6EEEE">Equiv. Hours of Max Power</th>
    </tr>
<tr>
  <th scope="col" style="background-color: #D6EEEE">June</th>
 <td>22,515</td><td>1,952</td><td>14</td><td>11.5</td></tr>
<tr>
  <th scope="col" style="background-color: #D6EEEE">December</th>
 <td>11,689</td><td>1,505</td><td>9</td><td>7.8</td></tr>
<tr>
<th scope="col" style="background-color: #D6EEEE">24h Full Output</th>/n<td>47,176</td> <td>1,966</td><td>-</td><td>-</td></tr>    
</table>

Finally, I include the final line above as an estimate maximum physical capacity of the solar panels constituting Nevada's solar utility installations. 
Treating the highest generation of any hour in the year as the physical output (in megawatts) assuming full ideal sun at the best angle, the panels 
could physically generate 47,000 MWh in a 24-hour period.  While it is impossible to expect any solar utility to reach even half of this level (the sun 
doesn't shine at night), it is still a useful benchmark because we can measure all other outputs against this quantity.  Even before taking into account 
weather, it may be that some geographies are better at taking a fixed capital input (a solar panel) and converting it into electricity due to day lengths, 
angles of the sun and permanent obstructions like mountains or nearby forests.  

This is akin to asking (for example) whether a 1 kW rooftop solar installation can expect to generate 500, 1,000 or 2,000 kWh in a year at your location
(given 8,760 hours in a year). 

## Putting it All Together




### Different Geographies


First chart -- multi-series stacked bar chart.  For each state, monthly bars for "unobstructured capacity" and "2022 actual production".    This will
show seasonal cycle in cpacity, and also whether weather affects some geographies more than others. 

Next chart - bars of 90+, 60-90, 30-60, 0-30.   Meant to show whether weather is "some days really bad" or not.   in different geographies. 

could do hours per day by differentn states, but that's kinda boring. 






