---
layout: post
title: "Impact of a New Nuclear Plant on Carbon Emissions"
date: "2023-12-3"
hide: true
author: "Jared Kramer"
excerpt_separator: <!--more-->
---

<head>
  {% include latex.html %}

<STYLE TYPE="text/css">
<!--
TH{font-family: Arial; font-size: 9pt; text-align: center;}
TD{font-family: Arial; font-size: 9pt; text-align: center;}
TR.gray TD, TR.gray TH {background-color: lightgray;}
TR.blue TD, TR.blue TH {background-color: #D6EEEE;}
TD.purple TH.purple {background-color: #E6E6FA;}
-->
</STYLE>
</head>

It has been common in recent years to see commentary nuclear power plant closure results in increased electricity generation by fossil-fuel buring power plants.  Examples include the 2021 shut-down of [Indian Point](https://www.nytimes.com/2021/04/12/nyregion/indian-point-power-plant-closing.html) in New York State, and the 2023 closure of Germany's [three last operating nuclear plants](https://www.theguardian.com/environment/2023/apr/15/germany-last-three-nuclear-power-stations-to-shut-this-weekend) which left the country's generation footprint as being among the most [carbon-intensive](https://www.washingtonpost.com/opinions/2023/05/10/germany-end-nuclear-cost-climate-health/) in Europe.

This article explores the impact on fossil-fuel burning electricity generation around a similar natural experiment in the other direction: the activation of the Vogtle 3 nuclear power plant in the U.S. state of Georgia on July 31, 2023.  

<!--more-->

I draw on data from the U.S. region where the grid is operated by The Southern Company (most of Alabama and Georgia and smaller parts of Misssissippi and Florida).  Beginning with the noisy picture of how much power is generated daily by each nuclear plant in the region, I build to the smoother picture of how much electricity is generated by the region's plants (both before and after Vogtle 3 came online).  

I then examine the overall electricity generation profile of the region in comparable months over several years (attempting to control for different demand profiles in different seasons), and estimate the carbon impact of the new Vogtle plant.

### A Picture of One Region's Nuclear Supply

There are seven nuclear plants in The Southern Company's territory: two at Farley Nuclear Generating Plant in Alabama (recently upgraded to [~950 MW each](https://www.nrc.gov/docs/ML2035/ML20351A176.pdf)), two at the Hatch plant in Georgia ([924 MW each](https://www.georgiapower.com/company/energy-industry/generating-plants/plant-hatch.html)) and now three at Vogtle in Georgia ([~1,150 MW each](https://www.georgiapower.com/company/energy-industry/generating-plants/plant-vogtle.html)) 

The Nuclear Regulatory Commission provides [daily reports](https://www.nrc.gov/reading-rm/doc-collections/event-status/reactor-status/index.html) of the power output of each nuclear plant in the U.S. (as a percentage of that plant's maximum capacity).  Taking the percent power generation for each plant and applying it to the capacity, we can see a picture of the region's day-by-day nuclear capacity in the plot below.

![Daily 2022-2023](/assets/images/post9_2022_2023_single_plants.png)

Notable features: 

- Most visible is the ramp-up at Vogtle Unit 3 as it was tested and brought up to full power for service July 31, 2023
- Every 1.5 to 2 years, plants undergo a several-week to several-month long refueling outage preceded by a "rampdown" in output (e.g., Vogtle 1 in Sep. 2021 and March 2023; Vogtle 2 in March 2022 and Sep. 2023; Farley 2 in April 2022 and Oct. 2023)
- Unscheduled outages due to equipment failures or minor upgrades lasting a few days also occur

Summing the generation together for all plants produces a smoother picture. 

![Aggregate 2022-2023](/assets/images/post9_2022_2023_aggregate.png)

While there are discrete ups and downs, we see an overall generation trend at ~90% of capacity.   The fleet has not had many days at full capacity since Vogtle 3 came online -- in part because it has been autumn and spring and autumn are when plants typically plan [refueling outages](https://www.eia.gov/todayinenergy/detail.php?id=60682).  But the contribution of the additional 1.1 GW of generation creates a material step-up in nuclear generation: 900 MW based on these months alone, and assuming the capacity factor pre-and-post Vogtle stabilizes at equivalent levels of ~92%, the run-rate contribution of the plant will be just above 1 GW. 

<table>
    <tr>
        <td rowspan="2"></td>
        <th colspan="1" scope ="colgroup" style="background-color: #D6EEEE">2 Years Pre-Vogtle</th>
        <th colspan="1" scope ="colgroup" style="background-color: #D6EEEE">Since Vogtle</th>
    </tr>
    <tr>
        <th scope="col" style="background-color: #D6EEEE">Aug 2021 to Jul 2023</th> 
        <th scope="col" style="background-color: #D6EEEE">Aug 2023 to Nov 2023</th>
    </tr>
    <tr>
        <th scope="row" style="background-color: #D6EEEE">Capacity (MW)</th> 
        <td>6,047</td><td>7,164</td>
    </tr>
    <tr>
        <th scope="row" style="background-color: #D6EEEE">Average Generation (MW)</th> 
        <td>5,583</td><td>6,487</td>
    </tr>
    <tr>
        <th scope="row" style="background-color: #D6EEEE">%</th> 
        <td>92.3%</td><td>90.6%</td>
    </tr>
</table>

### Impact to Carbon Emitting Generation Over Time

#### Simple Statistics are Confounded

With the incremental carbon-fee generation, we'd expect the Southeast region to see a step-function down in generation from carbon-generating sources (coal and natural gas) for comparable periods in 2021-2022 vs. 2023.  The below chart shows the generation from the main sources in the system for each of August, September, October and November (the 4 months since Vogtle 3 came online) for the last 3 years. 

![Bars by Month 2021-2023](/assets/images/post9_monthbars.png)

The simple analysis is surprisingly inconclusive.  There is no obvious decrease in gas + coal generation in 2023 (the monthly averages across the 3 years are in fact 15.2 TWh, 14.3 TWh, and 14.5 TWh), although there is enough evidence of confounding factors that a closer look is needed: 

- August 2023 saw 18.7 TWh of gas + coal generation, the same as 2021 and higher than the 2022 level.   But August 2023 was the hottest month in a very hot summer, and total demand and generation was higher than in previous years, so 18.7 TWh may have been less than what we would have seen without Vogtle 3.
- October and November 2023 saw 0.2 TWh **decrease** from 2022's gas + coal levels despite a higher overall demand and generation total.
- October and November 2023 saw meaningful **decreases** from 2021's levels, but the impact of Vogtle's presence vs. the overall lower generation total is not immediately apparent
  
#### More Detailed Analysis 

The idea of a possible depedence on total generation makes sense: natural gas espcially serves a "peaking" role in our grid, bridging the gap between total demand and sources of elecricity that are supply constrained such as: (1) nuclear, which has very high fixed costs and low marginal costs and is not easy to vary in response to demand and (2) weather-based sources where generation capacity is determined by extrinsic inputs such as weather (solar, wind, hydro).   

Since supply-constrained generation should be largely independent of demand level, we'd expect fossil-fuel generation to have a high correlation to total electricity demand.  The monthly chart above hints at this relationship, but to establish it more firmly we need more data points.

The below chart reports the relationship between **daily** total generation and **daily** fossil-fuel generation during August - November in each of the years 2021, 2022 and 2023 (all daily totals in GWh were divided by 24 hours to show the average generation rate in GW for the day).

![Linear Regression 2021-2023](/assets/images/post9_linreg.png)

Once we use regression analysis to control for the daily fluctiation in total electricity demanded and generated, we can see that 2023 has a lower fossil-generation level for each given level of total demand than 2021 or 2022.  For a typical level of total demand (29 GW, the middle of the chart), in 2023 there was about 600 MW less natural gas and coal generation than 2021 and 1 GW less than 2022. 

### Impact to Carbon Footprint

The Energy Information Agency provides data on the carbon-dioxide intensity of electricity generation from different fuel sources.  In 2022, Coal and Natural Gas had the following profiles: 

<table>
    <tr>
        <th colspan="1" scope ="colgroup" style="background-color: #D6EEEE">Fuel type</th>
        <th colspan="1" scope ="colgroup" style="background-color: #D6EEEE">2022 U.S. Generation (TWh)</th>
        <th colspan="1" scope ="colgroup" style="background-color: #D6EEEE">2022 CO<sub>2</sub> Emissions (million metric tons)</th>
        <th colspan="1" scope ="colgroup" style="background-color: #D6EEEE">Million Metric tons per TWh</th>
    </tr>
    <tr>
        <th scope="col" style="background-color: #D6EEEE">Coal</th>
        <td>831.5</td>
        <td>868</td>
        <td>1.04</td>
    </tr>
    <tr>
        <th scope="col" style="background-color: #D6EEEE">Natural Gas</th>
        <td>1,687.1</td>
        <td>743</td>
        <td>0.44</td>
    </tr>
    <tr>
        <th scope="col" style="background-color: #D6EEEE">All energy sources</th>
        <td>4,230.7</td>
        <td>1,650</td>
        <td>0.39</td>
    </tr>
</table>
Source: https://www.eia.gov/tools/faqs/faq.php?id=74&t=11
<p></p>
During the years 2021 - 2023, the southeast region generated 360 TWh of electricity from natural gas and 130 TWh from coal, so from simple proportions we can say that each TWh of fossil-fuel generation is 0.73 TWh reduction in natural gas generation and 0.27 TWh reduciton in coal generation.  Converting into CO<sub>2</sub> emissions:

$$0.73 \times 0.44 \frac{MM~tons~CO_2}{TWh} (natural gas) + 0.27 \times 1.04 \frac{MM tons CO_2}{TWh} (coal)$$
$$ = 0.60 \frac{MM tons CO_2}{TWh} (blended)$$

If the presence of the new nuclear plant gives us 600 - 1,000 MW less natural gas / coal generation, we get the following reduciton in CO<sub>2</sub> emissions over the course of a year (8,760 hours):

<table>
    <tr>
        <th colspan="1" scope ="colgroup" style="background-color: #D6EEEE">Fossil generation reduction</th>
        <th colspan="1" scope ="colgroup">600 MW</th>
        <th colspan="1" scope ="colgroup">1,000 MW</th>
    </tr>
    <tr>
        <th scope="col" style="background-color: #D6EEEE">Annual reduction (TWh)</th>
        <td>5.26</td>
        <td>8.76</td>
    </tr>
    <tr>
        <th scope="col" style="background-color: #D6EEEE">CO<sub>2</sub> equivalent (MM tons)</th>
        <td>3.15</td>
        <td>5.26</td>
    </tr>
</table>

So we get an annualized reduction of **3.15 to 5.26 million metric tons of CO<sub>2</sub>** emmission.   By comparison, an average car emits 4.6 metric tons of CO<sub>2</sub> per year, making the impact of Vogtle 3 the equivalent of removing the emissions of about **685,000 to 1.14 million** automobiles from the road. 

### Conclusion

It may seem obvious that a nuclear plant coming on line should displace fossil-fuel burning sources of electricity on the grid, and result in a reduction in CO<sub>2</sub> emissions.  Because electricity generation is highly variable over time, actually observing this relationship is not as easy at taking simple averages, but the relationship is indeed borne out by basic regression analysis.  Vogtle Unit 4 is scheduled to begin operations in the [first quarter of 2024](https://www.world-nuclear-news.org/Articles/Vogtle-4-start-up-moved-to-2024), another look at the data then should hopefully make this impact even more clear. 


