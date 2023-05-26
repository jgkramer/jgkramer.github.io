---
layout: post
title: "Demand Pricing"
date: "2023-05-31"
hide: true
author: "Jared Kramer"
excerpt_separator: <!--more-->
---

<head>
  {% include latex.html %}
</head>
 
In this post I return to the electricity pricing in the U.S., this time focusing on a concept that absent for most residential customers but mandatory for business customers that exceed a certain size: **demand pricing**.   Under a demand pricing scheme, an electricity customer is charged in two separate ways: 

(1) **Energy consumption.**  Described in [earlier](https://jgkramer.github.io/2022/10/15/Residential-Electricity-Rates.html) [posts](https://jgkramer.github.io/2022/11/07/Electricity_Usage_Anecdotes.html), like residential plans most demand plans charge for total energy consumption, measured in kilowatt-hours (kWh), and a per-kWh rate is applied.   The per-kWh charge may depend on the season and time of day (as in a Time of Use Plan), or it may be fixed.

(2) **Demand (maximum power).**  Here, utilities bill not for the energy consumed (in kWh), but rather for the maximum **rate** of energy consumption in a short period of time (such as a 15 minute period), at any time during the billing period (typically monthly).  This is a measurement of maximum **power** 
rather than aggregate energy consumption and so is often priced on a per-kW (rather than per-kWh).   The demand charge can also depend on the season and time of day. 

**(a little outline here)**

<!--more-->

### Why is there a Demand Charge for Commercial and Industrial Customers? 

The idea of pricing for peak demand (especially during heavy use periods such as summer afternoons) is derived from the physical need of an electricity grid to 
continuously balance electricity supply and consumption.  Large electricity consumers such as commercial and industrial users pose a greater risk to grid 
reliability through sharp spikes in the quantity of electricity demanded -- they may require bringing online additional "peaking" generation capacity and in the 
limit may result in more electriicty being demanded than supplied.   As such, usage spikes are priced at a premium, both to cover the infrastructure costs of the 
utility providing this flexibility as well as to incentivize a smoother usage profile.

National Grid, a utility operator in the northeast U.S., [explains](https://www9.nationalgridus.com/niagaramohawk/non_html/eff_elec-demand.pdf) that while residential consumers have simple rate structures based on consumptinonly because "there is relatively little variation in electricity use from home to home..."

> This is not the case among commercial and industrial energy users, whose electricity use--both consumption and demand--vary greatly. Some need large amounts of electricity once in a while--others, almost constantly. Complicating this is the fact that electricity cannot be stored. It must be generated and supplied to each customer as it is called for--instantly, day or night, in extremely variable quantities. Meeting these customers' needs requires keeping a vast array of expensive equipment--transformers, wires, substations and even generating stations--on constant standby. The amount and size of this equipment must be large enough to meet peak consumption periods, i.e., when the need for electricity is highest.[^1]

[^1]:  FPL [helpfully uses](https://www.fpl.com/rates/understand-demand.html#:~:text=What%20is%20Demand%3F,demand%20for%20each%20billing%20period.) a water utility analogy.  While most customers can be served with a standard one-inch-pipe,  one who uses significant water in bursts will require special equipment from the water company (larger main lines or service pipes), with "demand" charges covering the costs of equipment needed to handle more flow than standard.  

### A Gentle Introduction to Demand

#### A Simple Pricing Plan (Nevada)

We'll begin with a simple example: the Southern Nevada LGS-1 plan, which is for medium sized businesses (monthly consumption averaging above 3,500 kWh and demand < 200 kWh), and is constant throughout times of day and seasons.  There is also a time-of-use plan available (described below). 

This plan has an $0.114 / kWh usage charge, and $7.69 demand charge.   Note that the demand charge is quoted in **dollars** per kWh rather than the usage charge in **cents** per kWh, indicating that a business's energy bill is much more sensitive to how much its electricity usage peaks at its maximum consumption point in a month, than to its overall usage. 

A medical facility that uses 8,000 kWh per month but is open only 20 days a month for 10 hours and high air conditioning use during those hours, might have an **average** usage of 40 kW but a peak demand of 100 kW, and thus be charged $$8,000 kWh \times \$0.114 / kWh + 100 kW \times \$7.69 / kW = \$1,681.$$

Meanwhile a small highly automated manufacturing facility with limited human staffing and HVAC use may have its machines running 25 days a month for 16 hours, of an **average** usage of 20 kW but with a peak demand of only 40 kW.  Its charge will be $$8,000 kWh \times \$0.114 + 40 kW \times \$7.69 / kW = $1,220.$$  The automated facility has a 25% lower energy bill with the same usage, solely because its usage is more spread out over time than the HVAC-intensive medical facility. 

#### Real Example 1: One A/C vs. Two

Ignoring the fact that I am a residential customer rather than a commercial one, I examined two days of my home's electricity consumption in August 2022 to intuitively explore the impact of demand vs. consumption pricing.  August 16, 2022 was a normal hot summer day in Southern Nevada, and it is easy to see the operation in the afternoon and early evening of my two central air-conditionng units, each of which can consume ~1 kWh in 15-minute increments (~4 kW power consumption).  Note that the highest consumption was around 5pm, with both A/C units running and using a total of 3.5 kWh in 15 minutes, which is an average demand power of ~14 kW during this period. 

![1 vs. 2 A/C Comparison](/assets/images/post7_august_comparison.png)

August 22 was similarly a hot day, but I had only one A/C unit because the second one had broken.  The single unit struggled to cool the house during the hottest part of the day, and made up for that by operating many more hours (like the automated manufacturer in the above example).  The highest 15-minute period of consumption was 2.4 kWh around noon (probably the A/C plus the oven working on lunch), a demand of ~9.6 kW. 

The total consumption on these days was similar, with the one-A/C day using slightly more total energy (155.9 kWh vs. 150.2).  So under a residential billing program based on energy consumption, the two-A/C set-up would be cheaper.  But because it had a higher demand, the demand charge inverts the cost, making the two A/C unit more expensive assuming a 30-day month of identical days.  Details below:

| |Day's Usage (kWh)|Monthly Usage (kWh)|Peak Demand (kW)|Usage Cost|Demand Cost|**Total Cost**|
|:-------------|:--------------:|:--------------:|:--------------:|:--------------:|:--------------:|:--------------:|
|1&nbsp;A/C&nbsp;Unit|155.9|4,676|9.7|$533.03|$74.89|**$607.90**|
|2&nbsp;A/C&nbsp;Units|150.2|4,504|14.1|$513.41|$108.18|**$621.59**|

This example is contrived: my house was much more unpleasant with a single A/C unit than with two: the zone with the working unit was too cold and the side with the broken unit was too hot.   But it illustrates the point that demand (power) vs. usage (energy) may point in different directions. 

#### Real Example 2: Staggering vs. Parallel Use of Equipment

The second example is more realistic, and reflects the electricity usage over 6 days of San Diego-based friends with an electric vehicle.  Visible in the chart is the overnight EV charging at 8 kW of power (scheduled to end at 6:00 am, and start however long is needed before that to fully charge the car), as well as the running of their pool filter at about 1.5 kW from 5:00 to 11:00 am. 

![Overlapping equipment](/assets/images/post7_overlap.png)

The 1 hour overlap of EV charging and pool filter runnning causes the electricity consumption in each of the four 15-minute periods between 5 and 6am to be about 0.4 kWh higher.  Starting (and stopping) the pool filter an hour later would leave total energy consumption exactly the same (about 40 kWh per day).   But eliminating the overlap would reduce **peak demand** during this period by 1.3 kW from 9.64 kW to 8.34 kW.  In the Nevada fixed-rate plan described above, this would save about $10 per month.   Under San Diego commercial plans, in which demand is priced at $60 / kW, this would save $80 per month.[^2]

[^2].  Again, this is an motivating example.  In the real world, utilities often offer separate plans for EV owners, with EV charging separately metered. 

For actual commercial and industrial users, with electricity usage hundreds or thousands the magnitudes described here, managing the operation of power-hungry equipment to be sequential rather than parallel can generate large cost reductions (and improvements in grid stability). 

### Rate Structures in Different States

#### Simple Structures

The table below presents a few examples of demand-based business rates in different U.S. statess.   Often, a customer ends up in a rate category based on their usage patterns 

<STYLE TYPE="text/css">
<!--
TH{font-family: Arial; font-size: 9pt; text-align: center;}
TD{font-family: Arial; font-size: 9pt; text-align: center;}
TR.gray TD, TR.gray TH {background-color: lightgray;}
TR.blue TD, TR.blue TH {background-color: #E8E8E8;}
TD.purple TH.purple {background-color: #E6E6FA;}
-->
</STYLE>
<table>
    <tr class="blue">
      <th colspan="2" scope = "colgroup"></th> 
      <th colspan="2" scope = "colgroup">Southern Nevada (NV Energy)</th> 
      <th colspan="2" scope = "colgroup">Florida (FPL)</th>
      <th colspan="2" scope = "colgroup">Virginia (Dominion)</th>
    <tr class="blue">
     <th colspan="2">Plan Name</th>
     <th>LGS-1</th> <th>OLGS-1</th> <th>General Service Demand</th><th>General Service Demand-TOU</th><th>Small General (5P)</th><th>Large General (6P)</th>
    </tr>
    <tr class="blue">
     <th colspan="2">Applicable customers:</th>
     <th colspan="2">Medium (monthly usage > 3500 kWh, demand < 200 kW), can choose:</th>
     <th colspan="2">Businesses larger than small businesses can choose:</th>
      <th>Demand < 500 kW</th><th>Demand > 500 kW</th>
    </tr>
    <tr class="gray">
     <th  colspan="2">Time-of-Use?</th>
      <td>No</td><td>Yes</td><td>No</td><td>Yes</td><td>Yes</td><td>Yes</td>
    </tr>
    <tr>
     <th rowspan="2" class="purple">Summer&nbsp;Peak</th>
     <th class="purple">Energy&nbsp;/&nbsp;kWh</th>
     <td>$0.114</td><td>$0.209</td>
     <td>$0.068</td><td>$0.100</td>
     <td>$0.056</td><td>$0.041</td>
    </tr>
    <tr>
     <th class="purple">Demand&nbsp;/&nbsp;kW</th>
     <td>$7.69</td><td>$11.28</td>
     <td>$11.29</td><td>$11.29</td>
     <td>$11.77</td><td>$15.33</td> 
    <tr>
     <th rowspan="2" class="purple">Summer&nbsp;Off-Peak</th>
     <th class="purple">Energy&nbsp;/&nbsp;kWh</th>
     <td rowspan="6">Same</td><td>$0.106</td>
     <td rowspan="6">Same</td><td>$0.055</td>
     <td>$0.040</td><td>$0.035</td>
    </tr>
    <tr>
     <th class="purple">Demand&nbsp;/&nbsp;kW</th>
      <td>$0.00</td>
      <td>$0.00</td>
      <td>$0.00</td><td>$0.00</td>
    <tr>
     <th rowspan="2" class="purple">Winter&nbsp;Peak</th>
     <th class="purple">Energy&nbsp;/&nbsp;kWh</th>
      <td>$0.105</td>
      <td>$0.100</td>
      <td>$0.056</td><td rowspan="4">Same as summer</td>
    </tr>
    <tr>
     <th class="purple">Demand&nbsp;/&nbsp;kW</th>
      <td>$3.97</td>
      <td>$11.29</td>
       <td>$9.21</td>
    <tr>
     <th rowspan="2" class="purple">Winter&nbsp;Off-Peak</th>
     <th class="purple">Energy&nbsp;/&nbsp;kWh</th>
      <td rowspan="2">No time-of-day changes in winter</td>
      <td>$0.055</td>
      <td>$0.040</td>
    </tr>
    <tr>
     <th class="purple">Demand&nbsp;/&nbsp;kW</th>
      <td>$0.00</td>
      <td>$0.00</td>
</table>
                       
A couple of points to notice: 

**Peak vs. Off-Peak**.  Pricing plans that charge more for energy usage during peak times (e.g., summer afternoons) apply the same idea to demand charges as well.  In fact, the differential in demand pricing is more stark: both Nevada and Florida plans listed above have non-zero demand charges **only** for peak periods (Nevada has no peak/off-peak distinction in winter): the maximum power consumption during off-peak hours is totally ignored. 

This set-up suggests that it is system-wide constraints, such as finite generation capacity, that demand pricing is primarily targeting, since that constraint is tested only during peak system-wide usage periods.  The costs of stressing more local constraints such as local transmission and transformer equipment would be more applcable at all times. 

**Demand vs. Consumption Exchange Ratio**.   Power demand is priced in **dollars** (per kW) whereas energy consumption is priced in **cents** (per kWh).  This means that an extra kWh consumed at the moment of peak demand costs multiples of a kWh consumed at any other time.  

For example, in Nevada's TOU plan, an extra kWh of consumption during the peak hour of the month costs $11.28 during the summer.  At any other peak time it costs 21 cents.  The cost of incremental demand is thus 54x that of the cost of incremental consumption.  In Florida's TOU plan, the cost of incremental demand is 113x that of non-peak incremental consumption.  As we'll see below, a San Diego commercial plan has a $60 / kW demand charge and a $0.023 / kWh consumption charge, a 2600x ratio. 

The differences in these exchange ratios could rationally reflect differential marginal costs of the grid supplying incremental peak electricity vs. non-peak electricity.  For example, California is [awash with solar-generated kWh](https://www.etcc-ca.com/news/california%E2%80%99s-duck-problem-and-how-fix-it-cheaply) during the middle of the day, but still experiences a large ramp-up in power demanded in the early evening.  

A moderate ratio between demand and consumption charges may (like the differential between peak and off-peak consumption) may simply reflect the higher cost of generation: solar may make the incremental kWh nearly free during mid-day but the need to use coal or gas during peak evening hours means more fuel costs.   A high ratio like San Diegos may indicate that the marginal cost of evening power may not simply reflect fuel but begin to reflect the high capital costs of building "peaking" generation capacity.   

Marginal costs may not be the driver of these differences, however.  The setting of electric rates -- typically requiring state public utility commission approval -- is a political process and therefore may reflect the policy preferences of non-economic stakeholders as well. 

#### More Complex: Multiple Types of Demand

We have Nevada and we have San Diego.   So good. 

### Another Way of Looking at Consumption Cost

