---
layout: post
title: "Data Centers Driving Electricity Growth: A Look at Virginia Data"
date: "2024-05-19"
hide: true
author: "Jared Kramer"
excerpt_separator: <!--more-->
---

<head>
  {% include latex.html %}
</head>

Electricity demand in the U.S. has had near-zero growth for the last several decades.  According to a [Goldman Sachs report](https://www.goldmansachs.com/intelligence/pages/gs-research/generational-growth-ai-data-centers-and-the-coming-us-power-surge/report.pdf), "US annual power generation over the past 20 years averag[ed] less than 0.5% growth."  In recent months, a number of [utility reports](https://insidelines.pjm.com/pjm-publishes-2024-long-term-load-forecast/) and [media sources](https://www.wsj.com/business/energy-oil/how-big-data-centers-are-slowing-the-shift-to-clean-energy-44ef4145) have proclaimed a shift towards resumed electricity growth.  This is attributed primarily to growth in data center installations, which has been accelerated by data-intensive AI applications, along with other electrification initatives including electric vehicles and electric heating.  The Goldman Sachs report, for instance, forecasts 2.4% annual growth through 2030.

This post collects utility scale data that this acceleration is not only in the future, but has already started to occur.  Virginia, home to half the data center market in the U.S., has already seen electricity demand average year-over-year growth rates close to 4% since 2019, compared to near zero for neighboring regions.  This demand growth in Virginia approximately tracks the increase in data centers there.

<!--more-->

### Virginia's Electricity Demand

#### Growth Data

Using [Energy Information Administration](https://www.eia.gov/opendata/browser/electricity/rto/region-data) data, we plot the average electricity demanded for each month since 2019 in the Dominion Energy Virginia sub-region, which accounts for the [majority of Virginia's territory](https://www.pjm.com/library/~/media/about-pjm/pjm-zones.ashx) including Northern Virginia suburbs in Loudon County with the bulk of data center installations.  

![Virginia 5-year demand](/assets/images/post10_DOM_GW_demand.png)

A few things stand out: 
- The typical seasonal pattern of peaks in summer (for cooling) and winter (for heating)
- A COVID-driven dip in demand from 2019 to 2020, followed by a rebound in 2021
- Most relevantly, a consistent growth trend from year to year, anecdotally supporting the data center story.

How much growth?  The following chart shows the cumulative percentage growth for each month since the corresponding month in 2019, which we consider our baseline year.  We use the corresponding month to try to eliminate the effect of seasonality (e.g., December 2022 appears to have been particularly cold).  On average, in this limited data set of 53 months, the average year-over-year increase was 3.9% (+/- a large 6.5% standard deviation due to significant swings like hot or cold weather one year to another, COVID and recovery from COVID, etc).  

![Virginia 5-year % growth](/assets/images/post10_DOM_growth.png)

### Other Regions' Growth

The 3.9% average year-over-year growth in Virginia can be contrasted to the same data for four adjacent regions in the southeastern and mid-Atlantic United States: (1) Tennessee, (2) the Carolinas region, (3) the Baltimore region, and (4) the "American Electric Power" subregion of PJM, covering parts of western Virginia (not where the data centers are), West Virginia and southern Ohio.  

![Tennessee 5-year demand](/assets/images/post10_multi_GW_demand_1.png)

![Carolinas 5-year demand](/assets/images/post10_multi_GW_demand_2.png)

None of these charts show the same upward trend seen in the Virginia data above.   They all tell the same near-zero growth trajectory story attributed to the U.S. more broadly. 

<STYLE TYPE="text/css">
<!--
TH{font-family: Arial; font-size: 9pt; text-align: center;}
TD{font-family: Arial; font-size: 9pt; text-align: center;}
TH{font-family: Arial; font-size: 9pt}
TD{font-family: Arial; font-size: 9pt}
--->
</STYLE>
<table>
    <tr>
        <td rowspan="1"></td>
        <th colspan="1" scope ="colgroup" style="background-color: #D6EEEE">Dominion Virginia</th>
        <th colspan="1" scope ="colgroup" style="background-color: #D6EEEE">Carolinas</th>
        <th colspan="1" scope ="colgroup" style="background-color: #D6EEEE">Tennessee</th>
        <th colspan="1" scope ="colgroup" style="background-color: #D6EEEE">Am. Electric Power</th>
        <th colspan="1" scope ="colgroup" style="background-color: #D6EEEE">Baltimore Area</th>
    </tr>
    <tr>
        <th scope="col" style="background-color: #D6EEEE">Average YoY Growth %</th>
        <td>3.9%</td>
        <td>0.4%</td>
        <td>0.5%</td>
        <td>-0.2%</td>
        <td>-1.0%</td>
    </tr>
    <tr>
        <th scope="col" style="background-color: #D6EEEE">Std dev</th>
        <td>6.5%</td>
        <td>7.0%</td>
        <td>7.8%</td>
        <td>5.3%</td>
        <td>6.8%</td>
    </tr>
</table>

#### Comparison to Data Center Growth

So the part of Virginia including Data Center Alley has shown ~3.5 - 4.0% excess growth per annum compared to nearby regions.  Can we tell whether that is in fact data center-driven? 

The below chartplot data from PJM (source: [GS report]((https://www.goldmansachs.com/intelligence/pages/gs-research/generational-growth-ai-data-centers-and-the-coming-us-power-surge/report.pdf)) showing the increase since 2019 in data-center electricity consumption in GW in the Dominion Virginia region, against the overall increase in average electricity consumption in the region since 2019.   While not perfectly aligned, they move strongly together. 

![Aggregate Demand vs. Data Center Growth](/assets/images/post10_data_center_comparison.png)

#### Conclusion

Electricity demand data fits the story: Virginia, the center of gravity for data center growth, does indeed show a strong increase in electricity consumption over the last 5 years relative to neighboring regions.  The level of increase, moreover, reasonably tracks the reported growth in data center electricity usage.  As this sector continues to grow, we should expect continued demand growth in Virginia and other geographies that begin to attract these installations.



