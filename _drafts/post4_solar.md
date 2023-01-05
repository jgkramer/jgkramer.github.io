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

## Data Source: EIA

Data in this post comes from the Energy Information Administration website; in particular, its [Hourly Electric Grid Monitor](https://www.eia.gov/electricity/gridmonitor/dashboard/electric_overview/US48/US48),
which provides hour-granularity by region (defined by the electric grid balancing authority serving that region) on a number of variables.
These include total usage and generation in the region (balanced by import / export from neighboring regions), as well as a detailed look
at generation by type of source (e.g., coal, nuclear, natural gas, solar, wind).  An example of this latter chart is shown below, which shows
the daily generation cycle of solar, days where power output is lowered due to weather, and how natural gas plants are ramped up and down
to offset the solar generation cycle. 

<img src="/assets/images/post4_generation_sample.png"  width="70%" height="70%">


