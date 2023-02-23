---
layout: post
title: "Thoughts on Electricity Storage"
date: "2023-02-28"
excerpt_separator: <!--more-->
---

Electricity storage systems (batteries, pumped hydro storage) transport electricity through time, from generation earlier to consumption later. 
Generally speaking, storage is valuable when the aggregate amount of electricity generated is adequate to satisfy aggregate demand, but there is a 
mismatch in the timing of supply and demand.  Some basic fact patterns are: 

- **Demand More Variable than Supply**.  As discussed in previous posts, there is both a daily and a seasonal cycle to electricity usage.  If a region's generation is dominated by traditional base-load type power plants with high and constant generation capacity (coal, nuclear) or are quickly dispatchable (e.g., natural gas), there are two basic choices for meeting demand: either have enough generation capacity to cover the peak usage, or marry sub-peak generation with the ability to store energy when demand is low and use it when demand exceeds capacity.  
- **Supply More Variable through time than Demand**.  It is also possible for supply to cycle above and below demand.  Solar power, for example, generates electricity only during a 8-14 hour period during the daytime and none at night.  A grid with significant solar power may need storage
- **Unplanned Intermittancy**.  Power outages due to storms or maintenance issues, or merely unfavorable weather conditions such as low-wind and low-sun [dunkefulflaute](https://en.wikipedia.org/wiki/Dunkelflaute) may mean there is less generation capacity than planned for.   

In all of these situations there will be a question of whether it is more efficient to invest in storage or more (non-intermittent) generation capacity to compensate; this question is beyond the scope of this post.  

This post will attempt to illustrate, using reasonably realistic electricity demand models and overly simplistic supply models (with no unplanned outages) what profile of storage could be useful: how much energy capacity is needed and how frequently it cycles.  

## The Approach

This post uses the following approach: 

1. We have access to electricity storage (e.g., battery storage).  The battery can be "full" (its initial condition) but it can be drawn down in an arbitrarily large amount.  
2. Demand for electricity consumption is taken as a given as a function of time (measured hourly) and supply (whether from the grid or from storage) must be supplied to meet that demand at all times
3. I can specify a maximum grid supply, also as a function of time (hourly).  The supply value at any time could be greater or less than demand at that time. 
4. If the supply exceeds demand at a given time, the excess will be used to "refill" the energy storage system
5. If the grid supply is inadequate to meed demand, the difference will be supplied by a drawdown of the balance in energy storage. 
6. Supply up to the maximum grid supply is "dispatchable", i.e., if neither consumption nor storage refill needs to be powered, generation can be turned down (i.e., to save on fuel costs).
7. Each scenario will then analyzed will be to identify how much battery capacity is actually needed, which can then be used to get a sense of feasibility.

## Individual Scenarios

I'll begin by looking at individual home data for my residence in the Las Vegas, Nevada area.  To keep things simple, I only look at a single month (August 2021), to keep electricity usage relatively consistent.  Things get harder across an entire year when usage between seasons experience much larger swings.

### Demand Variability: Storage to Replace Super-Peak Grid Usage

In the chart below, the blue line in the top chart shows the electricity my family consumed hourly in August 2021.  Imagine I am limited to drawing a maximum level of power at any time from the grid.  For example, this might be the median of each day's peak hourly usage in the evening.  The red line in the top chart shows this limit of 11.5 kW.  This set-up could be driven by a utility plan that encourages me (try to shift some peak usage to off-peak hours) or requires me (e.g., smart grid device) to avoid drawing excessive power at peak times in order to protect the grid. 

If I want to use more power than 11.5 kWh per in any hour during my own peak consumption hours, I must use home battery system that has stored energy from prior periods with lower usage.  So the red line in the bottom chart shows how much aggregate has been drawn down from a full battery (represented by a 0 y-value at the top).   

![KramerMedianPeakAugust](/assets/images/post5_KramerMedianPeak.png)

Since the grid electrical input in this scenario is enough to cover usage for all but a few hours a day on 15 days, we can imagine a battery cycling to supply the gap.  For example, on August 3, air-conditioning driven demand exceeds supply from 2pm to 8pm by between 1 - 3 kWh per hour.  By 8pm slot, the battery would have needed to supply a total of 8.05 kWh.  Once the sun sets, hourly usage falls to under 7 kWh, and the excess up to 11.5 kWh refills the battery by 10pm.

Across the entire month, the largest daily battery usage would have been 8.9 kWh (on August 1).  There are a number of home battery storage products available in the 10-20 kWh capacity area, so this solution seems feasible.  However, at a battery cost for this capacity in the $10,000 - $15,000 area, it may not be economical as an individual solution.[^1]

[^1]: At the rates described in [this post](https://jgkramer.github.io/2022/11/07/Electricity_Usage_Anecdotes.html), this storage scheme would save less than $25 per year by transferring up to 8 kWh from peak times to off-peak times (a savings of $0.31 per kWh) on half the days during the 4 summer peak months.

### Supply Variability: Solar Power

Battery storage is a requirement of any electricity scheme that relied heavily on solar power, because electricity supply is much more variable through time than demand.  Even if solar generates enough electricity in aggregate, a meaningful portion of the day's usage needs to be time shifted from the daytime, when the sun is shining, to nighttime.  One might ask, for example, whether it is possible to use a combination of solar + battery to supply all electricity needs and go "off grid".   

The below analysis assumes the same relative output throughout an **August** day in Nevada as explored in the [last post](https://jgkramer.github.io/2023/01/28/Solar-Generation.html), but scaled down so that the total output over the month is either 110% or 130% of the total electricity consumed in the month.  Note that this generation function is **ideal solar generation**: the system generates electricity assuming good weather and no interruptions.   

![KramerSolarAugust](/assets/images/post5_KramerSolar.png)

Notice the daily cycle: solar generation is strongest in the mid-day, when the need for air conditioning has not yet ramped up, so at this point the battery is filling up.  But generation drops by 50% by the 6-7pm hour, and falls away entirely shortly after.  Meanwhile, the air conditioning peak generally runs until at leaset 8pm, so there is a sharp drawdown from storage in the evening that continues at a slower pace until the next morning. 

One thing that makes this plan tricky is that daily demand fluctuates considerably with both behavior (laundry is a big one) and weather (temperature / AC needs).   Compared to an average of 148 kWh, daily use ranged from 99 kWh (67% of average) to 193 kWh (130% of average), just in one month.  So in order for the battery to fully recharge every day, we needed a solar generation system that was capable of delivering 130% of the average day's consumption every day (orange lines).  With this level of input, the energy storage needs to be at least **69 kWh**.   This is a much larger and more expensive battery but still in the range of quasi-mass production: many electric vehicle batteries fall in the capacity range of 80-120 kWh.   

If we only have enough solar capacity to deliver 110% of the average day's consumption (pink lines), we run into trouble.  The beginning of August 2021 had a number of consecutive days with consumption greater than 110% of average, so day-to-day the battery never had a chance to recharge fully.   The result was a bigger and bigger drawdown of storage capacity until the middle of the month.   The total size of battery needed was at least **156 kWh**. 

All of this occurs without two complications: (1) seasonality (with much larger swings in demand and, for solar, supply) and (2) weather-driven shortfalls.   If we take into account the likelihood that solar generation is not only lower than ideal (in Nevada, [82%](https://jgkramer.github.io/2023/01/28/Solar-Generation.html)), but lower in lumpy ways (i.e., some days with only 50% or less of ideal production), then storage capacity will have to be considerably higher to get through those days.

## State-Level Grid Analysis

I now step back and consider the grid-scale question of how much storage can be useful to economize on generation capacity by looking at the EIA's total demand data for Nevada.  I will also cover a full one-year period (ending November 1, 2022) to capture the challenges arising from seasonality. 

### Demand Variability: Storage to Replace Super-Peak Grid Usage

The grid right now is roughly set up such that generating capacity is approximately capable of handling peak demand.  This is not always used 
in practice as regional balancing authorities import power from other regions to meet peaking demand.  For example, where Nevada's summer electricity demand is 1.8x the spring/fall usage, the state in July/August 2022 imported an average of 1.5 GWh every hour (often 2+ GWh during the afternoon). 

Storage offers an alternative: if generating capacity can supply the grid's consumption at **most** times, storage can supply the difference on days with a few hours of peak demand that are higher.  In this first example, I assume generating based on the following two benchmarks: 

1. The average of the daily consumption peaks during the 4 peak summer months (June to September), which is enough to supply 163% of the average electricity consumption across the year and 81% of the peak hourly usage.

2. The 95th percentile among the 365 "peak hour" consumptions for each day in the year.   This level is 186% of average consumption, and 93% of the maximum peak hour.

![NevadaPeaksFullYear](/assets/images/post5_NV_HighFixed.png)

Because these supply levels are close to the highest hourly peak consumption in the hot summers, with consumption only exceeding these levels for at most a few hours a day, the hypothetical battery storage is always able to fully recharge every day (unlike the 110% solar example above).  Thus the maximum demand on storage is simply how far above the supply level the consumption gets, for how many hours.

<STYLE TYPE="text/css">
<!--
TH{font-family: Arial; font-size: 9pt; text-align: center;}
TD{font-family: Arial; font-size: 9pt; text-align: center;}
TR.coral TD, TR.coral TH {color: #FF7F50;}
TR.plum TD, TR.plum TH {color: #BA55D3;}
TR.blue TD, TR.blue TH {color: blue;}
TR.limegreen TD, TR.limegreen TH {color: limegreen;}
TR.slateblue TD, TR.slateblue TH {color: slateblue;}
-->
</STYLE>
<table>
    <col> <colgroup span="1"></colgroup><colgroup span="6"></colgroup>
    <tr>
        <th colspan="1" scope ="colgroup" style="background-color: #E8E8E8"></th> 
        <th colspan="2" scope ="colgroup" style="background-color: #E8E8E8">Total (GWh)</th> 
        <th colspan="1" scope ="colgroup" style="background-color: #E8E8E8">Average Hourly (GWh/h)</th> 
        <th colspan="1" scope ="colgroup" style="background-color: #E8E8E8">Peak Hourly (GWh/h)</th>   
        <th colspan="1" scope ="colgroup" style="background-color: #E8E8E8">Storage Needed</th>
        <th colspan="1" scope ="colgroup" style="background-color: #E8E8E8"># Days with Non-Zero Storage</th>   
    </tr>
<tr class="blue">
  <th scope="col" style="background-color: #E8E8E8">Demand</th>
    <td>39,384</td> <td>1.00x</td> <td>4.48</td> <td>8.97 </td> <td>--</td> <td>--</td> </tr> 
 <tr class="coral">
  <th scope="col" style="background-color: #E8E8E8">Average Summer Peak</th>
   <td>64,115</td> <td>1.63x</td> <td>7.30</td> <td>7.30</td> <td> <b>11.4 GWh</b></td> <td>18</td> </tr>
<tr class="plum">
  <th scope="col" style="background-color: #E8E8E8">Year's 95th %ile Peak</th>
  <td>73,224</td> <td>1.86x</td> <td>8.34</td> <td>8.34</td> <td> <b>2.6 GWh</b></td> <td>68</td> </tr>
</table>

The results of these plans seem very feasible, especially higher-generation grid architecture.  This could get by with 3 GWh of storage (delivered at a 0.7 GW rate, the difference between 9 GW peak demand and 8.3 GW supply).  There are numerous pumped-hydro storage facilities in the U.S. that can store 10 GWh[^2].  More modern chemical or gravity/weight based storage projects are, as of 2022, in the range of 250 - 500 MWh per project, and a few of these would cover the 3 GWh need.  

[^2]: The [Ludington Pumped Storage Power Plant](https://en.wikipedia.org/wiki/Ludington_Pumped_Storage_Power_Plant) in Michigan, for example, has a storage capacity of 19.5 GWh.  The [Northfield Mountain facility](https://en.wikipedia.org/wiki/Northfield_Mountain_(hydroelectricity_facility)).
   
The result of this experiment is (approximately) that 3 GWh of electricity storage would enable Nevada to eliminate about ~600 MW of electricity generation capacity (8.34 vs. 8.97 peak consumption) or the equivalent in inter-region transfers which may become less reliable over time; 12 GWh of storage would enable Nevada to eliminate ~1.6 GW of electricity generation capacity. 
     
### Limits of Replacing Peak Generation with Storage
    
Compared to the examples above with generation in excess of 160%+ of average consumption, feasibility decays if generation capacity falls to levels where there are numerous consecutive days with daily total consumption in excess of that capacity.  In these scenarios, storage does not refill on a daily basis, and there are accumulating drawdowns as time progresses.  In Nevada, for a generation model that is based on traditional generation sources with constant capacity (Nuclear, Coal, Gas), the risk of this occuring is in the summer.   To illustrate this effect, the chart below (1) eliminates the hourly variability to display daily totals and (2) plots the storage results for fixed generation at levels equal to 1.5x and 1.35x the full-year average (i.e., if always on, enough to supply 1.5x / 1.35x the total annual consumption). 

![NevadaPeaksFullYear](/assets/images/post5_NV_MediumFixed.png)
    
In the case where generation can supply 1.5x of the annual average consumption (6.73 GWh / h), there are many days in the summer where the afternoon and evening consumption this (up to 8.97 GWh at the highest peaks).  Thus many summer days see electricity storage drawdowns on the order of 10 GWh per day, as high afternoon demand uses storage that is refilled at lower-demand nighttime and morning.  There were a **few** days in July where total consumption exceeded 24 hours x 6.73 GWh / h =  161.5 GWh, so the storage usage, while higher than the scenarios above, remained relatively contained at 28 GWh.  If generation is reduced to 1.35x of average, there were more than a month worth of days with consumption in excess of supply in the summer, and with storage not refilling, the storage requirement balloons to 216 GWh.  
    
<table>
    <col> <colgroup span="1"></colgroup><colgroup span="6"></colgroup>
    <tr>
        <th colspan="1" scope ="colgroup" style="background-color: #E8E8E8"></th> 
        <th colspan="2" scope ="colgroup" style="background-color: #E8E8E8">Total (GWh)</th> 
        <th colspan="1" scope ="colgroup" style="background-color: #E8E8E8">Average Hourly (GWh/h)</th> 
        <th colspan="1" scope ="colgroup" style="background-color: #E8E8E8">Peak Hourly (GWh/h)</th>   
        <th colspan="1" scope ="colgroup" style="background-color: #E8E8E8">Days with Demand &gt Supply</th>
        <th colspan="1" scope ="colgroup" style="background-color: #E8E8E8">Storage Needed</th>
    </tr>
    
  <tr class="blue">
  <th scope="col" style="background-color: #E8E8E8">Demand</th>
    <td>39,384</td> <td>1.00x</td> <td>4.48</td> <td>8.97 </td> <td>--</td> <td>--</td> </tr> 
    
  <tr class="slateblue">
  <th scope="col" style="background-color: #E8E8E8">Constant Generation 1.5x</th>
   <td>58,938</td> <td>1.50x</td> <td>6.34</td> <td>6.34</td> <td>7</td> <td> <b>27.5 GWh</b></td> </tr>
    
<tr class="limegreen">
  <th scope="col" style="background-color: #E8E8E8">Year's 95th %ile Peak</th>
   <td>53,045</td> <td>1.35x</td> <td>6.06</td> <td>6.06</td> <td>41</td> <td><b>215.6 GWh</b></td> </tr>
    
</table>
    
### Solar: Some Helpful Supply Variability, Some Costly

Besides its carbon-free generation properties (net of PV panels' energy- and mining-intensive supply chain), solar generates more power in the summer than in the winter.  This feature can be deployed help address one of the features of constant generation that there can be **too little** electricity supply in some parts of the year (high demand summer) and **too much** in other parts (low demand winter), at least in a hot desert state like Nevada without much of a winter heating usage peak.  

The below model assumes generation at ideal solar capacity throughout the year, scaled to produce 150% and 135%, respectively, of the [TODO]
    
![KramerMedianPeakAugust](/assets/images/post5_NV_MediumSolar.png)
 
Compared to the 
    
    

### Solar / Fixed Blend: 
    
### A Word on Power Cycling and Economic Feasibility

Whether that kind of tradeoff is economical may depend on how much the battery gets used: in the 1.86x example above, the benefit of 18 days of batter usage may not justify the capital cost of a 3 GWh storage project (i.e., capital cost savings of 700 MWh less generation may not compensate).  Further economic justification for the capital cost of the storage project can come from using it more frequently in non-peak times **if** it results in fuel savings costs.   
    
Fuel savings costs through the use of storage cannot come from reduction in aggregate fuel usage: electricity that is delivered from storage at peak usage time must have been generated by a power plant at an earlier time.   In fact, if grid electricity is stored, generally only [80% of the energy input](https://www.eia.gov/todayinenergy/detail.php?id=46756) can be retrieved later.  
    
Economizing can only arise if time-shifting allows the grid to replace genreation from high-cost sources at peak times (e.g., petroleum or less efficient natural gas plants on the right of the supply curve) with lower-cost sources at off-peak times (e.g., nuclear, coal or solar on the left side of the supply curve). 

![EIA Supply Curve](/assets/images/EIA_supply_curve.png)
