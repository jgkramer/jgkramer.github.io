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

![All months](/assets/images/post4_NVPower_all_hourly.png)

Some macroscopic patterns are intuitive and symmetrical.   December and January appear to be the lowest production months, followed by November and 
February.  The late spring and summer are a bit strange -- although June is a strong month, May look even better, and July looks weak compared to April 
(perhaps because monsoon season brings frequent morning clouds?).

<STYLE TYPE="text/css">
<!--
TH{font-family: Arial; font-size: 8pt; text-align: center}
TD{font-family: Arial; font-size: 8pt; text-align: center}
--->
</STYLE>
<table>
    <col> <colgroup span="1"></colgroup><colgroup span="3"></colgroup><colgroup span ="5"></colgroup>
    <tr>
        <th colspan="1" scope ="colgroup" style="background-color: #D6EEEE"></th>
        <th colspan="3" scope ="colgroup" style="background-color: #D6EEEE">Full Capacity</th>
        <th colspan="5" scope ="colgroup" style="background-color: #D6EEEE">Actual Production</th>
    </tr>
    <tr>
        <th scope="col" style="background-color: #D6EEEE">Month</th> 
        <th scope="col" style="background-color: #D6EEEE">Daily Generation Capacity (MWh)</th> 
        <th scope="col" style="background-color: #D6EEEE">Max Hourly Rate (MWh)</th> 
        <th scope="col" style="background-color: #D6EEEE">Hours of Full Generation</th>
        <th scope="col" style="background-color: #D6EEEE">% of Full Capacity</th>
        <th scope="col" style="background-color: #D6EEEE">Days 90%+</th>
        <th scope="col" style="background-color: #D6EEEE">Days 60-90%</th>
        <th scope="col" style="background-color: #D6EEEE">Days 30-60%</th>
        <th scope="col" style="background-color: #D6EEEE">Days 30%-</th>
    </tr>
<tr>
  <th scope="col" style="background-color: #D6EEEE">January</th>
 <td>10,366</td><td>1,321</td><td>7.8</td><td>86.1%<td>11</td><td>16</td><td>4</td><td>0</td>
</tr>
<tr>
  <th scope="col" style="background-color: #D6EEEE">February</th>
 <td>14,302</td><td>1,636</td><td>8.7</td><td>88.8%<td>16</td><td>11</td><td>1</td><td>0</td>
</tr>
<tr>
  <th scope="col" style="background-color: #D6EEEE">March</th>
 <td>16,982</td><td>1,816</td><td>9.4</td><td>88.4%<td>17</td><td>12</td><td>2</td><td>0</td>
</tr>
<tr>
  <th scope="col" style="background-color: #D6EEEE">April</th>
 <td>19,828</td><td>1,909</td><td>10.4</td><td>92.8%<td>21</td><td>8</td><td>1</td><td>0</td>
</tr>
<tr>
  <th scope="col" style="background-color: #D6EEEE">May</th>
 <td>21,486</td><td>1,923</td><td>11.2</td><td>94.9%<td>25</td><td>6</td><td>0</td><td>0</td>
</tr>
<tr>
  <th scope="col" style="background-color: #D6EEEE">June</th>
 <td>21,260</td><td>1,857</td><td>11.4</td><td>92.5%<td>21</td><td>8</td><td>1</td><td>0</td>
</tr>
<tr>
  <th scope="col" style="background-color: #D6EEEE">July</th>
 <td>19,154</td><td>1,825</td><td>10.5</td><td>90.1%<td>21</td><td>8</td><td>2</td><td>0</td>
</tr>
<tr>
  <th scope="col" style="background-color: #D6EEEE">August</th>
 <td>18,806</td><td>1,825</td><td>10.3</td><td>88.7%<td>18</td><td>11</td><td>2</td><td>0</td>
</tr>
<tr>
  <th scope="col" style="background-color: #D6EEEE">September</th>
 <td>18,086</td><td>1,807</td><td>10.0</td><td>92.0%<td>23</td><td>5</td><td>2</td><td>0</td>
</tr>
<tr>
  <th scope="col" style="background-color: #D6EEEE">October</th>
 <td>16,148</td><td>1,760</td><td>9.2</td><td>92.2%<td>21</td><td>10</td><td>0</td><td>0</td>
</tr>
<tr>
  <th scope="col" style="background-color: #D6EEEE">November</th>
 <td>13,698</td><td>1,666</td><td>8.2</td><td>86.0%<td>16</td><td>11</td><td>2</td><td>1</td>
</tr>
<tr>
  <th scope="col" style="background-color: #D6EEEE">December</th>
 <td>10,364</td><td>1,383</td><td>7.5</td><td>80.1%<td>15</td><td>11</td><td>2</td><td>3</td>
</tr></table>


