---
layout: post
title: North vs. South
date: "2022-12-10"
hide: true
excerpt_separator: <!--more-->
---

This post explores the seasonality of electricity usage at both the individual level (e.g., my own) and how it scales to the macro level
(e.g., state-wide in Nevada).  I then explore how seasonality varies from one place to another across the country, making use of both anecdotal 
individual homeowner data I have collected, as well as state-wide data.  

<!--more-->

### Nevada

The following chart shows Nevada's monthly consumption throughout the year in TeraWatt-hours (1 billion kWh), averaged over the 3 year period 
Sep. 2019 to Aug. 2022.  This and similar statewide data is derived from data sets on the U.S. Energy Information Agency website breaking down energy 
consumption by [state, month and sector](https://www.eia.gov/electricity/data.php#sales).

![NV Statewide Usage](/assets/images/post3_NV_statewide.png)

Several observations: 

* Residential total use of 14.1 TWh (14.1 billion kWh) per year for 3.1 million Nevada residents    
  - Average of 4,500 kWh per year per Nevada resident.  
  - My family-of-four total of 30,000 kWh for a year was 6.6x the per capita usage, not surprising for a larger-than-average single-family suburban home
* Heavy seasonality of residential usage, most prominently a big summer air-conditioning peak
  - Of the 14.1 TWh annual usage, 49.8% occurs during the four months June through September
  - Peak usage month (July) is 2.63x the minimum usage month (November)
* There is a small winter peak, perhaps driven by a combination of heating and more lighting / appliance usage with shorter daylight hours
  - Peak winter usage month (December) is 1.24x the minimum usage month

Note that the TOTAL state electricity usage has less seasonality than the residential sector: the summer peak is 1.8x the minimum usage month, and the 
winter peak is 1.1x.  Highly variable climate control electric usage is presumably lower for the commercial and industrial sectors than for residences.

I then compare statewide usage to my own, showing the percentage of annual consumption in each month of the year.  The individual usage throughout the 
year very closely matches the profile of aggregate month-to-month residential use (commercial and industrial use is visibly less seasonal).[^1] 

[^1]: In the dark blue series, the artificially-low consumption in June-July due to travel has been replaced by (1) July being assumed to be the same as 
August and (2) June being halfway between May and August. 

![Kramer-NV Comparison](/assets/images/post3_Kramer_vs_NV.png)

### Northern Lands

Next up, a colder climate: Connecticut in the U.S. Northeast.  Average July high temperatures in New Haven, Connecticut: 86&deg;F (Las Vegas: 107&deg;F); 
average January high temperatures: 37&deg;F (Las Vegas: 59&deg;F).  Below is the statewide monthly consumption chart for the state.

![CT Statewide Usage](/assets/images/post3_CT_statewide.png)

Observations: 

* For a slightly larger population than Nevada (3.6 million), the total annual electricity usage is 13.0 TWh / year, for an annual usage per capita of 3600 kWh
* There is an air-conditioning summer peak, but it is much smaller than in Nevada
  - 37% of annual residentual consumption is in the 4 summer months June through September
  - Peak usage month (August) is only **1.49x** the minimum usage month (April)
* There is a second peak in the winter, corresponding to the heating season
  - The peak is smaller than the summer peak but larger than Nevada's winter peak: Connecticut January usage is **1.31x** April's minimum.  
  - Both the smaller size of the winter peak, as well as the overall lower per capita electricity consumption compared to Nevada, are likely driven by the fact that the winter portion of New England heating and cooling is mostly fueled by fossil fuels (80% between heating oil, natural gas and propane) rather than electricity. 
  - That there remains **some** winter peak derives from the ~16% of home heating that is electric powered.[^2]

![image](/assets/images/post3_new_england_households_heating_by_fuel_2021_0.png)

[^2]: The graphic above, and New England stats for 2021, are courtesy the Massachusetts state [website](https://www.mass.gov/service-details/how-massachusetts-households-heat-their-homes) (downloaded 26-Nov-22).

The last point is illustrated by comparing the seasonal profile of two houses in Connecticut: (1) one with an all-electric HVAC system 
(heat pump for both heating and cooling), and (2) another with heat provided by utility natural-gas furnaces.  **[NOTE UPDATE AFTER NOVEMBER 14WP BILL 
COMES OUT].**

![image](/assets/images/post3_CT_line.png)

Notice that for the house with gas-fueled winter heat, the winter electricity peak is small (1.25x the minimum month) while the summer peak is 
quite prominent (close to 2.0x).  Meanwhile, the winter peak for the all-electric HVAC house is larger (2.3x minimum) than the summer A/C peak 
(1.9x the minimum): it takes more energy to heat a home 30-50 degrees above the outside temperature than it does to cool a home 10-20 degrees cooler
than the outside temperature.   The state-wide portfolio, which is a blend of these two categories (but weighted towards the fossil-fuel fired home), 
thus has a blended seasonality profile as seen above. 

### You Wanted to See Alaska and Florida

As we'll see, most U.S. states have electricity consumption seasonality akin to Nevada and Connecticut (but with different relative sizes of summer
and winter peaks).   This is not true for Alaska and Florida: 

![image](/assets/images/post3_FLandAK_line.png)




## Every State (plotly)


