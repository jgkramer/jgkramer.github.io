---
layout: post
title: "Demand Pricing"
date: "2023-05-31"
hide: true
author: "Jared Kramer"
excerpt_separator: <!--more-->
---
 
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

> This is not the case among commercial and industrial energy users, whose electricity use--both consumption and demand--vary greatly. Some need large amounts of electricity once in a while--others, almost constantly. Complicating this is the fact that electricity cannot be stored. It must be generated and supplied to each customer as it is called for--instantly, day or night, in extremely variable quantities. Meeting these customers' needs requires keeping a vast array of expensive equipment--transformers, wires, substations and even generating stations--on constant standby. The amount and size of this equipment must be large enough to meet peak consumption periods, i.e., when the need for electricity is highest.

### Some Examples

The table below presents a few examples of demand-based business rates in different U.S. statess.   Often, a customer ends up in a rate category based on their usage patterns 
(for example, in Nevada, business customers who consume less than 3,500 kWh per month are in a non-demand based plan). 

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
     <th colspan="1" scope ="colgroup">Massachusetts (National Grid)</th>
    <tr class="blue">
     <th colspan="2">Plan Name</th>
     <th>LGS-1</th> <th>OLGS-1</th> <th>General Service Demand</th><th>General Service Demand-TOU</th><th>General Service-Demand</th>
    </tr>
    <tr class="blue">
     <th colspan="2">Applicable customers:</th>
     <th colspan="2">Medium (monthly usage > 3500 kWh, demand < 200 kW), choice between two</th>
     <th colspan="2">Businesses larger than small businesses, choice betwen two</th>
     <th>Average use > 10,000 kWh / month, demand < 200 kW</th>
    </tr>
    <tr class="gray">
     <th  colspan="2">Fixed vs. TOU</th>
     <td>Fixed</td><td>TOU</td><td>Fixed</td><td>TOU</td><td>Fixed</td>
    </tr>
    <tr>
     <th rowspan="2" class="purple">Summer - Peak</th>
     <th class="purple">Consumption / kWh</th>
     <td>$0.114</td><td>$0.209</td>
     <td>$0.068</td><td>$0.100</td>
     <td>$0.062</td>
    </tr>
    <tr>
     <th class="purple">Demand / kW</th>
     <td>$7.69</td><td>$11.28</td>
     <td>$11.29</td><td>$11.29</td>
     <td>$12.47</td>
    <tr>
     <th rowspan="2" class="purple">Summer - Off-Peak</th>
     <th class="purple">Consumption / kWh</th>
     <td>$0.114</td><td>$0.106</td>
     <td>$0.068</td><td>$0.055</td>
     <td>$0.062</td>
    </tr>
    <tr>
     <th class="purple">Demand / kW</th>
     <td>$7.69</td><td>$0.00</td>
     <td>$11.29</td><td>$0.00</td>
     <td>$12.47</td>
    <tr>
     <th rowspan="2" class="purple">Winter - Peak</th>
     <th class="purple">Consumption / kWh</th>
     <td>n/a</td><td>n/a</td>
     <td>$0.068</td><td>$0.100</td>
     <td>$0.062</td>
    </tr>
    <tr>
     <th class="purple">Demand / kW</th>
     <td>n/a</td><td>n/a</td>
     <td>$11.29</td><td>$11.29</td>
     <td>$12.47</td>
    <tr>
     <th rowspan="2" class="purple">Winter - Off-Peak</th>
     <th class="purple">Consumption / kWh</th>
     <td>$0.114</td><td>$0.105</td>
     <td>$0.068</td><td>$0.055</td>
     <td>$0.062</td>
    </tr>
    <tr>
     <th class="purple">Demand / kW</th>
     <td>$7.69</td><td>$3.97</td>
     <td>$11.29</td><td>$0.00</td>
     <td>$12.47</td>
</table>
                       

