---
layout: post
title: North vs. South: Seasonality in Electricity Consumption
date: "2022-12-10"
hide: true
excerpt_separator: <!--more-->
---

This post explores the seasonality of electricity usage at both the individual level (my own) and how it scales to the  macro level (e.g., state-wide 
in Nevada).  I then explore how seasonality varies from one place to another across the country, making use of both anecdotal individual homeowner data I 
have collected, as well as state-wide data.  

<!--more-->

## Nevada

The following chart shows Nevada's monthly consumption throughout the year in TeraWatt-hours (1 billion kWh), averaged over the 3 year period 
Sep. 2019 to Aug. 2022.  My source is the U.S. Energy Information Agency, which provides excellent data sets breaking down energy consumption by 
[state, month and sector](https://www.eia.gov/electricity/data.php#sales).

![NV Statewide Usage](/assets/images/post3_NV_statewide.png)

Several observations: 

* Residential total use of 14.1 TWh (14.1 billion kWh) per year for 3.1 million Nevada residents    
  - Average of 4,500 kWh per year per Nevada resident.  
  - My family-of-four total of 30,000 kWh for a year was 6.6x the per capita usage, not surprising for a larger-than-average single-family suburban home
* Heavy seasonality of residential usage
  - Minimum consumption is in the late fall / early spring, when outdoor temperatures are closest to indoor comfort levels, minimizing HVAC energy use
* There is a very prominent summer peak: 
  - Of the 14.1 TWh annual usage, **49.8%** occurs during the four months June through September
  - Peak usage month (July) is 2.63x the minimum month (November)
* There is a small winter peak, perhaps driven by a combination of heating and more lighting / appliance usage with shorter daylight hours
  - Peak winter usage month (December) is 1.24x the minimum usage month

Note that the TOTAL state electricity consumption has less seasonality than the residential sector: the summer peak is 1.8x the minimum usage month, 
and the winter peak is 1.1x.  Highly variable climate control electricity consumption is presumably lower for the commercial and industrial sectors 
than for residences.

I then compare statewide usage to my own, showing the fraction of annual consumption in each calendar.  The individual usage throughout the 
year very closely matches the profile of aggregate month-to-month residential use (commercial and industrial use is visibly less seasonal).[^1] 

[^1]: In the dark blue series, the artificially-low consumption in June-July due to travel has been replaced by (1) July being assumed to be the same as 
August and (2) June being halfway between May and August. 

![Kramer-NV Comparison](/assets/images/post3_Kramer_vs_NV.png)

## Northern Lands

Next up, a colder climate: Connecticut in the U.S. Northeast.  Average July high temperatures in New Haven, CT: 86&deg;F (Las Vegas: 107&deg;F); 
average January high temperatures: 37&deg;F (Las Vegas: 59&deg;F).  Below is the statewide monthly consumption chart for the state.

![CT Statewide Usage](/assets/images/post3_CT_statewide.png)

Observations: 

* For a slightly larger population than Nevada (3.6 million), the total annual electricity usage is 13.0 TWh / year
  - Annual consumption per capita: 3,600 kWh
* Minimum consumption once again is in spring / fall
* There is an air-conditioning summer peak, but it is much smaller than in Nevada
  - 37% of annual residentual consumption is in the 4 summer months June through September
  - Peak usage month (August) is only **1.49x** the minimum (April)
* There is a second peak in the winter, corresponding to heating season
  - The peak is smaller than the summer peak but larger than Nevada's winter peak: Connecticut January usage is **1.31x** April's minimum.  
  - Both the smaller size of the winter peak, as well as the overall lower per capita electricity consumption compared to Nevada, are likely driven by the fact that the winter part of New England heating and cooling is mostly powered by fossil fuels (80% between heating oil, natural gas and propane) rather than electricity. 
  - That there remains **some** winter peak derives from the fraction of home heating (16% in New England) that is electric powered.[^2]

![image](/assets/images/post3_new_england_households_heating_by_fuel_2021_0.png)

[^2]: The graphic above, and New England stats for 2021, are courtesy the Massachusetts state [website](https://www.mass.gov/service-details/how-massachusetts-households-heat-their-homes) (downloaded 26-Nov-22).

The impact of "what energy source fuels heating" is illustrated by comparing the seasonal profile of two houses in Connecticut: 
(1) one with an all-electric HVAC system (heat pump for both heating and cooling), and (2) another with heat provided by utility natural-gas furnaces.  
**[NOTE UPDATE AFTER NOVEMBER 14WP BILL COMES OUT].**

![image](/assets/images/post3_CT_line.png)

Notice that for the house with gas-fueled winter heat, the winter electricity peak is small (1.25x the minimum month) while the summer peak is 
quite prominent (close to 2.0x).  Meanwhile, the winter peak for the all-electric HVAC house is larger (2.3x minimum) than the summer A/C peak 
(1.9x the minimum): it takes more energy to heat a home 30-50 degrees above the outside temperature than it does to cool a home 10-20 degrees cooler
than the outside temperature.  The state-wide portfolio, which is a blend of these two categories (but weighted towards the fossil-fuel fired home), 
thus has a blended seasonality profile as seen above. 

## You Wanted to See Alaska and Florida

Most U.S. states consume electricity with seasonality akin to Nevada and Connecticut: winter (partial) heating peak, summer air conditioning peak, and 
spring/fall troughs where there is little HVAC needed one way or the other.  This is not true for Alaska and Florida: 

![image](/assets/images/post3_FLandAK_line.png)

Much of Alaska is always colder than indoor comfortable temperatures: summer high temperatures in Anchorage are just above 60&deg;F.  
So the annual cycle ranges from "heavy electricity consumption for heating in winter" to "less heavy electricity consumption for heating in summer", 
with no summer peak at all.  The winter peak is 1.6x the summer nadir. 

Florida is the opposite: it is always hot and humid, and many residents use air conditioning all year round (with occasional winter heating), 
with more of it being used in the summer.  So the annual cycle is various degrees of electricity for cooling, peaking in summer.  Summer consumption
is 1.6x the winter minimum.

## Every State

Beyond the individual examples above, the maps below show the height of the summer and winter electricity usage peak month, as a 
multiple of the consumption in the lowest electricity month, typically a fall or spring month.  Higher numbers (e.g., 2 - 2.5x) evidence greater 
seasonal variation in electricity usage than lower numbers (e.g., 1.25 - 1.5x).  The full data set that drives the maps is [here](/assets/csv/post3_map.csv).

While there are other measures of seasonality (e.g., % of total consumption in the summer months), I find the peak-height metric relevant because it
conveys the full range of power output that the grid must supply.  Electriicty generation plants must provide not merely the total energy consumed in 
a locale throughout the year, but must instantaneously provide the power demanded at all times -- up to a peak consumption much higher than the average. 
Coping with this variability is the challenge and miracle of the [grid](https://bam.kalzumeus.com/archive/markets-in-power/), and different generation 
sources contribute differentially into this variability of demand.  Nuclear, hydroelectric and coal, for example, are useful as "always on" base load
generation, while natural gas is often used in "peaker" plants that can by cycled up and down to deal with fluctuations. 

![image](/assets/images/post3_summer_map.png)

Starting with the summer analysis, we see the general pattern that southern states with hotter summers and presumably more air-conditioning usage
have a higher relative electricity consumption than northern states with cooler summers.  The states with the highest summer peak values (Nevada at 2.63x 
and Arizona at 2.47x) have the two cities -- Las Vegas and Phoenix -- with the [highest number of days](https://www.currentresults.com/Weather-Extremes/US/hottest-cities.php) that reach 100&deg;F (Austin, TX is a distant third).   

Some of the states that buck this intuition are souther locations where the weather is warm but consistently so 
(i.e., summer isn't too much warmer).  Florida (discussed above) is an example of this, as is Hawaii.  Curiously, New Jersey has the third-highest relative summer peak, at 2.25x.

The winter map below is more complicated than the simple inverse of summer.  Generally, there are higher winter peaks in northern states with 
colder climates as more energy is used for winter heating.  However, climate is not only the explanatory variable. 

![image](/assets/images/post3_winter_map.png)

Variation, as discussed above, is also driven by winter heating fuel source.  North Dakota, for example, has a similar climate 
to surrounding states Montana, Minnesota and South Dakota.   However, [41%](https://www.eia.gov/state/print.php?sid=ND) of its homes use electric 
heat in the winter, compared to [27%](https://www.eia.gov/state/print.php?sid=MT), [19%](https://www.eia.gov/state/print.php?sid=MN) and 
[33%](https://www.eia.gov/state/print.php?sid=SD) for the other three.  The same is true of West Virginia and Virginia, which also have a higher-than 
avearge fraction of homes with electric heating ([45%](https://www.eia.gov/state/print.php?sid=WV) and [57%](https://www.eia.gov/state/print.php?sid=VA)), 
while Michigan and New York, despite cold winters, have low shares of electric heating [12%](https://www.eia.gov/state/print.php?sid=MI) and [15%](https://www.eia.gov/state/print.php?sid=NY)
Thus it is the combination of both climate and residential infrastructure that drive how much electricity consumption peaks in the winter. 

This is not the full story: even beyond primary sources of heating, [Doomberg](https://doomberg.substack.com/p/new-england-is-an-energy-crisis-waiting) 
and [Meredith Angwin](https://meredithangwin.com/books/) detail how much of an impact even **supplemental heating** via space heaters has in extremely 
cold conditions, which can destabilize the New England grid despite a relatively low proportion of electric heated homes and a modest **average** peak 
in winter electricity usage. 

## This is Complicated

What started as a simple observation about my home electricity bills during different months revealed an extremely complicated equation.  
Seasonal variation in electricity demand is determined not only by climate, but also by the myriad local infrastructure  decisions about how humans 
heat and cool their homes (which in turn depends on variables like whether residential areas are dense enough to merit utility natural gas, 
or whether heating oil is efficiently deliverable by truck).  Regulations and grid architecture surely play a role as well, and this is before 
even getting into the different characteristics of different flavors of electricity generation. 

And if anyone can explain New Jersey, please reach out to me. 

## Code and Coda

The [coding](www.github.com/jgkramer/hummingbird) for this post was fun, and I focused particularly on modularizing the reading of 
utility-provided CSV files with home usage of various cadence (all the way from 15-minute granularity to monthly usage data).  I welcome a discussion 
with any readers who care to share data and draw lessons from it, especially commercial / industrial customers with energy as a significant input to 
operations, and who face a more complicated set of decisions (including demand-spike based pricing). 