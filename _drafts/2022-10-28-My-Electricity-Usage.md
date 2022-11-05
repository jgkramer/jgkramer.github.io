---
layout: post
title: "Anecdotes on Electricity Usage"
date: "2022-11-7"
hide: true
excerpt_separator: <!--more-->
---

The last post's foray into electricity rates, especially Time-Of-Use (TOU) plans, inspired me to inquire about my own electricity usage patterns 
in the Las Vegas area.  First, I will build some intuition about patterns of use by time of day by visualizing my smart-meter outputs (provided by 
NVEnergy's website) on a handful of days across different seasons.   I will then step back and look at total consumption across an entire year. 

## A Sampling of Usage Data

#### Winter
Winter electricity usage is modest -- temperatures are chilly but our heating is natural-gas powered (this uses a little bit of electricity, generating
the day-long squiggles, but not too much).  Thus the **64 kWh** consumption from 3-Feb is about our baseline usage from lights and appliances.
The **25 kWh** incresae on Tuesday 1-Feb is the impact of our once-a-week laundry day: our electric dryer is rated 26A x 240V = ~6 kW maximum, 
so running it for 5-6 hours with some breaks and some low power times (e.g., cool down) seems to approximately account for the 25 kWh.

![February Usage](/assets/images/post2_usage_Feb.png)

#### Summer
August in Nevada is hot, both in high temperatures (many days over 100&deg;F) and low temperatures (many over 80&deg;F), meaning air conditioning 
tends to run most of the day and night.  This brings the total electricity usage to **2.0 to 2.5x** the winter baseline usage. 

![August Usage](/assets/images/post2_usage_Aug.png)

Electricity consumption is sensitive to temperatures: 164 kWh on the 109&deg; day vs. 131 on the 96&deg; day, with the majority of the increase 
coming from peak hours.  Our family keeps the house 4&deg; cooler at night, so the general pattern is moderate usage at night when it is not as hot, 
to maintain the cooler temperatures; **lower** usage in the late morning as we let the house warm up a bit during the day; and **much higher** usage 
in the late afternoon / evening as the house warms up and weather is hottest.

#### Spring

![May Usage](/assets/images/post2_usage_May.png)

## Aggregate Usage and Cost of Plans

<table>
    <col> <colgroup span="3"></colgroup> <colgroup span ="1"></colgroup>
    <tr>
        <td rowspan="2"></td>
        <th colspan="3" scope ="colgroup">Time of Use</th>
        <th colspan="1" scope ="colgroup">Fixed Rate</th>
    </tr>
    <tr>
        <th scope="col">Peak</th> <th scope="col">Off-Peak</th> <th scope="col">Total</th> <th scope="col">Total</th>
    </tr>
    <tr>
        <th scope="row">Usage (kWh)</th> <td>3,781</td> <td>25,224</td> <td>29,006</td> <td>29,006</td>
    </tr>
    <tr>
        <th scope="row">Est. Cost</th> <td>$1,512.22</td> <td>$23,87.94</td> <td>$3,900.16</td> <td>$4,144.93</td>
    </tr>
</table>
