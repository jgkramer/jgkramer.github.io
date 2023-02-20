---
layout: post
title: "Thoughts on Electricity Storage"
date: "2023-02-28"
excerpt_separator: <!--more-->
---

Electricity storage systems (batteries, pumped hydro storage) transport electricity through time, from generation earlier to consumption later. 
Generally speaking, storage is valuable when the aggregate amount of electricity generated is adequate to satisfy aggregate demand, but there is a 
mismatch in the timing of supply and demand.  Some basic fact patterns are: 

- **Supply More Variable Demand**.  As discussed in previous posts, there is both a daily and a seasonal cycle to electricity usage.  If a region's generation is dominated by traditional base-load type power plants with high and constant generation capacity (coal, nuclear) or are quickly dispatchable (e.g., natural gas), there are two basic choices for meeting demand: either have enough generation capacity to cover the peak usage, or marry sub-peak generation with the ability to store energy when demand is low and use it when demand exceeds capacity.  
- **Demand More Variable through time than Supply**.  It is also possible for supply to cycle above and below demand.  Solar power, for example, generates electricity only during a 8-14 hour period during the daytime and none at night.  A grid with significant solar power may need storage
- **Unplanned Intermittancy**.  Power outages due to storms or maintenance issues, or merely unfavorable weather conditions such as low-wind and low-sun [dunkefulflaute](https://en.wikipedia.org/wiki/Dunkelflaute) may mean there is less generation capacity than planned for.   

In all of these situations there will be a question of whether it is more efficient to invest in storage or more (non-intermittent) generation capacity to compensate; this question is beyond the scope of this post.  

This post will attempt to illustrate, using reasonably realistic electricity demand models and overly simplistic supply models (with no unplanned outages) what profile of storage could be useful: how much energy capacity is needed and how frequently it cycles.  

## The Approach

This post uses the following approach: 

1. We have access to electricity storage (e.g., battery storage).  The battery can be "full" (its initial condition) but it can be drawn down in an arbitrarily large amount.  
2. Demand for electricity consumption is taken as a given as a function of time (measured hourly) and supply (whether from the grid or from storage) must be supplied to meet that demand at all times
3. I can specify a maximum grid supply, also as a function of time (hourly).  The supply value at any time could be greater or less than demand at that time. 
4. If the supply exceeds demand at a given time, the excess will be used, first, to "refill" the energy storage system; and second, if the energy storage is full, the supply is "lost" (this would in reality result in a reduction in generation).
5. If the grid supply is inadequate to meed demand, the difference will be supplied by a drawdown of the balance in energy storage. 
6. The exercise in each scenario analyzed will be to identify how much battery capacity is actually needed, and how frequently the battery is cycled.  

## Individual Scenarios

### Replace Peak Grid

Here is a scenario using my home's data.  The blue line in the top chart shows the electricity my family consumed hourly in August 2021.  Imagine I am limited to drawing a maximum level of power at any time from the grid.  For example, this might be the median of each day's peak hourly usage in the evening.  The red line in the top chart shows this limit of 11.5 kW.  This set-up could be driven by a utility plan that encourages me (try to shift some peak usage to off-peak hours) or requires me (e.g., smart grid device) to avoid drawing excessive power at peak times in order to protect the grid. 

If I want to use more power than 11.5 kWh per in any hour during my own peak consumption hours, I must use home battery system that has stored energy from prior periods with lower usage.  So the red line in the bottom chart shows how much aggregate has been drawn down from a full battery (represented by a 0 y-value at the top).   

![KramerMedianPeakAugust](/assets/images/post5_KramerMedianPeak.png)

Since the grid electrical input in this scenario is enough to cover usage for all but a few hours a day on 15 days, we can imagine a battery cycling to supply the gap.  For example, on August 3, air-conditioning driven demand exceeds supply from 2pm to 8pm by between 1 - 3 kWh per hour.  By 8pm slot, the battery would have needed to supply a total of 8.05 kWh.  Once the sun sets, hourly usage falls to under 7 kWh, and the excess up to 11.5 kWh refills the battery by 10pm.

Across the entire month, the largest daily battery usage would have been 8.9 kWh (on August 1).  There are a number of home battery storage products available in the 10-20 kWh capacity area, so this solution seems feasible.  However, at a battery cost for this capacity in the $10,000 - $20,000 area, it may not be economical as an individual solution.[^1]

[^1]: At the rates described in [this post](https://jgkramer.github.io/2022/11/07/Electricity_Usage_Anecdotes.html), this storage scheme would save less than $25 per year by transferring up to 8 kWh from peak times to off-peak times (a savings of $0.31 per kWh) on half the days during the 4 summer peak months.

### Solar Power

Battery storage is a requirement of any electricity scheme that relied heavily on solar power.  Even if solar generates enough electricity in aggregate, 
a meaningful portion of the day's usage needs to be time shifted from the daytime, when the sun is shining, to nighttime.  

![KramerSolarAugust](/assets/images/post5_KramerSolar.png)
