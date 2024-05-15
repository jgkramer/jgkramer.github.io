---
layout: post
title: "Data Centers Driving Electricity Growth: A Look at Virginia Data"
date: "2023-06-05"
hide: true
author: "Jared Kramer"
excerpt_separator: <!--more-->
---

<head>
  {% include latex.html %}
</head>

Electricity demand in the U.S. has had near-zero growth for the last several decades.  According to a [Goldman Sachs report](https://www.goldmansachs.com/intelligence/pages/gs-research/generational-growth-ai-data-centers-and-the-coming-us-power-surge/report.pdf), "US annual power generation over the past 20 years averag[ed] less than 0.5% growth."  In recent months, a number of [utility reports](https://insidelines.pjm.com/pjm-publishes-2024-long-term-load-forecast/) and [media sources](https://www.wsj.com/business/energy-oil/how-big-data-centers-are-slowing-the-shift-to-clean-energy-44ef4145) have proclaimed a shift towards resumed electricity growth, feuled by a growth in data center installations (especially driven by data-intensive AI applications), along with other electrification initatives including electric vehicles and electric heating.   The Goldman Sachs report, for instance, forecasts 2.4% annual growth through 2030.

This post collects utility scale data that this acceleration is not only in the future, but has already started to occur.  Virginia, home to half the data center market in the U.S., has already seen electricity demand average year-over-year growth rates close to 4% since 2019, compared to approximately 0.5% for neighboring regions.  This demand growth in Virginia approximately tracks the increase in data centers there.

<!--more-->

### Virginia's Electricity Demand

Using [Energy Information Administration](https://www.eia.gov/opendata/browser/electricity/rto/region-data) data, we are able to plot the average electricity demanded for each month since 2019 in the Dominion Energy Virginia sub-region, which accounts for the [majority of Virginia's territory](https://www.pjm.com/library/~/media/about-pjm/pjm-zones.ashx) including Northern Virginia suburbs in Loudon County with the bulk of data center installations.  

![Virginia 5-year demand](/assets/images/post10_DOM_GW_demand.png)

A few things stand out: 
- The typical seasonal pattern of peaks in summer (for cooling) and winter (for heating)
- A COVID-driven dip in demand from 2019 to 2020, followed by a rebound the following year
- Most relevantly, a consistent growth trend from year to year, anecdotally supporting the data center story.

How much growth?  The following chart shows the cumulative percentage growth for each month since the corresponding month in 2019, which we consider our baseline year.   We use the corresponding month to try to eliminate the effect of seasonality (e.g., December 2022 appears to have been particularly cold).   

![Virginia 5-year % growth](/assets/images/post10_DOM_percent_growth.png)
