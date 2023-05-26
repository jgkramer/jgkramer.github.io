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
 
In this post I return to the structure of electricity pricing in the U.S., this time focusing on a pricing concept that is mandatory for business customers that 
exceed a certain size (measured in monthly electricity consumption): **Demand Pricing.**  Under a demand pricing scheme, an electricity customer is charged in two separate ways: 

(1) First, energy consumption.  This is the concept described in [earlier](https://jgkramer.github.io/2022/10/15/Residential-Electricity-Rates.html) [posts](https://jgkramer.github.io/2022/11/07/Electricity_Usage_Anecdotes.html) -- the total energy consumption, measured in kilowatt-hours (kWh), during a month is measured, and a per-kWh rate is applied.   The per-kWh charge may depend on the season and time of day (as in a Time of Use Plan), or it may be fixed.  

(2) Second, electricity "demand."  Here, utilities bill not for the energy consumed (in kWh), but rather for the maximum **rate** of energy consumption in a short period of time (such as a 15 minute period), at any time during the billing period (typically monthly).  This is a measurement of maximum **power** 
rather than aggregate energy consumption and so is often priced on a per-kW (rather than per-kWh).   The demand charge can also depend on the season and time of day. 

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

August 22 was similalry a hot day, but my house had only one active A/C unit because the second one had broken.  The single unit struggled to cool the house during the hottest part of the day, and made up for that by operating a higher percentage of the time (like the automated manufacturer in the above example).  The highest 15-minute period of consumption was 2.4 kWh around noon (probably the A/C plus the oven working on lunch), a demand of ~9.6 kW. 

The total consumption on these two days was similar, with the single A/C day using slightly more total energy (155.9 kWh vs. 150.2).   So under a residential billing program based on energy consumption, the two A/C set-up would be cheaper.   But because it has a higher demand, the demand charge inverts the cost, making the two A/C unit more expensive assuming a 30-day month of identical days.  Details below:

| |Day's Usage (kWh)|Monthly Usage (kWh)|Peak Demand (kW)|Usage Cost|Demand Cost|**Total Cost**|
|:-------------|:--------------:|:--------------:|:--------------:|:--------------:|:--------------:|:--------------:|
|1&nbsp;A/C&nbsp;Unit|155.9|4,676|9.7|$533.03|$74.89|**$607.90**|
|2&nbsp;A/C&nbsp;Units|150.2|4,504|14.1|$513.41|$108.18|**$621.59**|

This example is contrived: my house was much more unpleasant with a single A/C unit than with two: the zone with the working unit was too cold and the side with the broken unit was too hot.   But it illustrates the point that demand (power) vs. usage (energy) may point in different directions. 

#### Real Example 2: Staggering vs. Parallel Use of Equipment

The second example is more realistic, and reflects the electricity usage over 6 days of San Diego-based friends with an electric vehicle.  Visible in the chart is the overnight EV charging at 8 kW of power (scheduled to end at 6:00 am, and start however long is needed before that to fully charge the car), as well as the running of their pool filter at about 1.5 kW from 5:00 to 11:00 am. 

![Overlapping equipment](/assets/images/post7_overlap.png)

The 1 hour overlap of EV charging and pool filter runnning causes the electricity consumption in each of the four 15-minute periods between 5 and 6am to be about 0.4 kWh higher.  Starting (and stopping) the pool filter an hour later would leave total energy consumption exactly the same (about 40 kWh per day).   But eliminating the overlap would reduce **peak demand** during this period by 1.3 kW from 9.64 kW to 8.34 kW.  In the Nevada fixed-rate plan described above, this would save about $10 per month.   Under a demand-based rate plan in San Diego, where demand is priced at $30 / kW, this would save $40 per month.[^2]

[^2].  Again, this is an motivating example.  In the real world, utilities often offer separate plans for EV owners, with EV charging separately metered. 

For actual commercial and industrial users, with electricity usage hundreds or thousands the magnitudes described here, intelligently sequencing the operation of power-hungry equipment to avoid overlaps if possible can have a meaningful impact on cost and grid stability (as can selecting the time of day they are used under TOU plans). 

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
        <th colspan="2" scope ="colgroup"></th> 
         <th colspan="2" scope ="colgroup">Southern Nevada (NV Energy)</th> 
         <th colspan="2" scope ="colgroup">Florida (FPL)</th>
    <tr class="blue">
     <th colspan="2">Plan Name</th>
     <th>LGS-1</th> <th>OLGS-1</th> <th>General Service Demand</th><th>General Service Demand-TOU</th>
    </tr>
    <tr class="blue">
     <th colspan="2">Applicable customers:</th>
     <th colspan="2">Medium (monthly usage > 3500 kWh, demand < 200 kW), choice between two</th>
     <th colspan="2">Businesses larger than small businesses, choice betwen two</th>
    </tr>
    <tr class="gray">
     <th  colspan="2">Fixed vs. TOU</th>
     <td>Fixed</td><td>TOU</td><td>Fixed</td><td>TOU</td>
    </tr>
    <tr>
     <th rowspan="2" class="purple">Summer - Peak</th>
     <th class="purple">Consumption / kWh</th>
     <td>$0.114</td><td>$0.209</td>
     <td>$0.068</td><td>$0.100</td>
    </tr>
    <tr>
     <th class="purple">Demand / kW</th>
     <td>$7.69</td><td>$11.28</td>
     <td>$11.29</td><td>$11.29</td>
    <tr>
     <th rowspan="2" class="purple">Summer - Off-Peak</th>
     <th class="purple">Consumption / kWh</th>
     <td rowspan="6">Same</td><td>$0.106</td>
     <td rowspan="6">Same</td><td>$0.055</td>
    </tr>
    <tr>
     <th class="purple">Demand / kW</th>
      <td>-</td>
      <td>-</td>
    <tr>
     <th rowspan="2" class="purple">Winter - Peak</th>
     <th class="purple">Consumption / kWh</th>
      <td>n/a</td>
      <td>$0.100</td>
    </tr>
    <tr>
     <th class="purple">Demand / kW</th>
      <td>n/a</td>
      <td>$11.29</td>
    <tr>
     <th rowspan="2" class="purple">Winter - Off-Peak</th>
     <th class="purple">Consumption / kWh</th>
      <td>$0.105</td>
      <td>$0.055</td>
    </tr>
    <tr>
     <th class="purple">Demand / kW</th>
      <td>$3.97</td>
      <td>-</td>
</table>
                       
A couple of points to notice: 

**Demand vs. Consumption Trade-off**.   Note that demand charges are priced in **dollars** whereas energy consumption charges are priced in **cents**.  This means that an incremental 1 kWh of consumption has different costs depending on whether that kWh is at the moment of peak demand or not.   For example, in the TOU plan in Nevada, if a customer adds an extra kWh of consumption during its peak hour of the month (i.e., more air conditioning on a hot summer afternoon), then that kWh costs $11.28 because it increases demand.   In contrast, if that kWh was consumed at any other time, it would cost 21 cents.  The cost of the incremental **demand** is thus 54x that of the cost of incremental **consumption**.  This shows the relative cost to the system of concentrating electricity usage at times of peak demand.   

Different states have different ratios: in Florida's TOU plan, for example, the ratio of the cost of incremntal demand to incremental consumption is 113x.  In Massachusetts it is 201x.  In these latter states it is especially critical for business electricity consumers to try to smooth out their electricity use throughout the day. 

#### More Complex: Multiple Types of Demand


### Another Way of Looking at Consumption Cost

