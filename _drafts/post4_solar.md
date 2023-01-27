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

I have two goals.  The first is to provide real data that concretely fleshes out some of the features of solar generation that are often qualitatively
addressed in much energy commentary (e.g., intermittency).   The second is to start generating a mathematical model of solar energy as a variable 
electricity **supply**.  This can then be matched up against fluctuating **demand** for electricity.   How the supply and demand flucutations interact can 
generate other interesting outputs such as (1) how much energy storage is useful in the grid and/or (2) what other sources of generation (e.g., natural gas) may be needed to fill gaps. 

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
    <col> <colgroup span="1"></colgroup><colgroup span="5"></colgroup>
    <tr>
        <th colspan="1" scope ="colgroup" style="background-color: #D6EEEE"></th>
        <th colspan="5" scope ="colgroup" style="background-color: #D6EEEE">Full Capacity</th>
    </tr>
    <tr>
        <th scope="col" style="background-color: #D6EEEE">Month</th> 
        <th scope="col" style="background-color: #D6EEEE">Daily Generation Capacity (MWh)</th> 
        <th scope="col" style="background-color: #D6EEEE">Monthly Peak Hour (MWh)</th>
        <th scope="col" style="background-color: #D6EEEE">Hours Active per Day</th>
        <th scope="col" style="background-color: #D6EEEE">Equiv. Hours @ Monthly Peak</th>
        <th scope="col" ="background-color: #D6EEEE">Equiv. Hours @ Maximum Physical Output</th>
    </tr>
<tr>
  <th scope="col" style="background-color: #D6EEEE">June</th>
 <td>22,515</td><td>1,952</td><td>14</td><td>11.5</td><td>11.5</td></tr>
<tr>
  <th scope="col" style="background-color: #D6EEEE">December</th>
 <td>11,689</td><td>1,505</td><td>9</td><td>7.8</td><td>5.9</td></tr>
<tr>
<th scope="col" style="background-color: #D6EEEE">24h of Max. Summer Sun</th>/n<td>47,176</td> <td>1,966</td><td>-</td><td>-</td><td>24</td></tr>
</table>

Finally, I include the final line above as an estimate maximum physical capacity of the solar panels constituting Nevada's solar utility installations. 
Treating the highest generation of any hour in the year as the physical output (in megawatts) assuming full ideal sun at the best angle, the panels 
could physically generate 47,000 MWh in a 24-hour period.  By this standard, in June, Nevada's best-case solar generation (before weather) is 48% of the physical capacity of the panels (i.e., 11.5 hours of maximum physical output per day).   
In December, it is 25% (5.9 hours of maximum physical output).

While it is impossible to expect any solar utility to reach even half of this level (the sun doesn't shine at night), it is still a useful benchmark
because we can measure all other outputs against this quantity.  Even before taking into account weather, it may be that some geographies are better at 
taking a fixed capital input (a solar panel) and converting it into electricity due to day lengths, angles of the sun and permanent obstructions like 
mountains or nearby forests.

## Putting it All Together

We are finally equipped to paint a full year picture of the ebbs and flows of solar generation in Nevada: starting with a top line (unrealizable) 
benchmark of the full capacity of the plants, we will see how much of that benchmark is produced and when, taking into account (1) daily cycles, (2) 
seasonal cycles and (3) weather, to reach actual production. 

![Monthly Capacity Curve](/assets/images/post4_NVPower_monthly.png)

Compared to the full-blast summer output of the Nevada solar installations of 1,966 MWh per hour, we see that full capacity throughout the year runs
between 5.9 hour outputs in the winter and 11.5 in the summer, with an average throughout the year of 9.38 hour-equivalents of full-blast production
per day.  Actual production every month in 2022 was between 10% and 30% lower than full capacity, depending on the month.   It ranged between the 
equivalent of 4.2 hours in January to 10.4 hours in May, and averaged the equivalent of 7.66 hours per day throughout the year (18% lower than 
capacity). 

The months where the weather slippage was the greatest are not intuitively surprising to me given my experience of Nevada weather -- there can be 
cloud cover and sometimes precipitation in the coldest part of the winter, and there is the summer monsoon season in July/August with frequent 
rain as well.  

## Exploring Different Geographies

### Capacity Curves

Finally, I performed the same analysis above on three other locations in states with relatively high solar energy generation -- Texas and parts of 
Florida and North Carolina.  Starting with the pattern of "full capacity" (without weather interruption) throughout the year in each locale: 

![Monthly Capacity Curve by State](/assets/images/post4_multi_state.png)

These results are not intuitive to me.   While different geographies have different climates, this chart measures weather-free "full capacity" in 
different months of the year, benchmarked against maximum one-hour summer utility output.  As such, I was not expecting significant variability 
across locations.   But they are: the average capacity throughout the year is 9.4 hours, 7.6 hours, 9.1 hours and 8.0 hours in Nevada, North Carolina,
Texas and Florida, respectively.[^2]

[^2] One (speculative!) possible explanation is that different utilities in different locations have different physical panels that contribute to differential capturing of the sun.  For example, when looking at the June hourly capacity chart for different locations (below), notice that in North Carolina, generation is only briefly at its peak; whereas in Nevada, the shape of the curve is a flat-topped plateau (5 hours above 90% of peak for NC, vs. 9 hours for NV).   If the Nevada utility had motorized solar panels that could track the sun across the sky, while the North Carolina utility did not, this type of chart could result.  

![Monthly Capacity Curve by State](/assets/images/post4_multi_state_june_hours.png) 

### The Weather

Finally, we see the impact of the weather.  As presaged at the beginning, desert climate Nevada loses relatively little solar generation little to 
non-sunny skies relative, and in 2022 its average solar production was 7.7 "full blast" hours per day throughout the year.  The other locales all have
more variable weather with greater cloud cover and precipitation, and as such suffer another ~30% generation loss instead of ~18% in the desert.  Texas 
comes in second at 6.6 "full blast" hours, Florida at 5.7 hours, and North Carolina at 5.2 hours.

![Overall Actual vs Capacity](/assets/images/post4_multi_state_bar.png) 

### ChatGPT

A quick note that while the writing, analytics and the coding were all authored by me, I got a small amount of help late in this project by querying 
ChatGPT to find convenient python library functions to use, rather than searching for them on the internet or reading about them in package documentation. 
It was definitely labor-saving, and I expect to be doing more of it in the future. 

