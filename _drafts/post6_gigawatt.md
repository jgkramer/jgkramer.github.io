---
layout: post
title: "What the Hell Is a Gigawatt?"
date: "2023-03-26"
hide: true
author: "Great Scott"
excerpt_separator: <!--more-->
---
 
I sometimes find it frustrating as an observer of energy markets and policy to understand the quantities those markets deal in.  News and commentators quote prices in units that consumers may be unfamiliar with, making it difficult to intuit the importance of those prices.  This post will serve as a gentle reference for what energy quantities mean and how to convert between different standard market conventions. 

Here are some examples: 

- **War in Ukraine**.  European wholesale natural gas prices (Dutch Title Transfer Facility or Dutch TTF) ran from &euro;88 per megawatt hour (MWh) in February 2022 before Russia's invasion of Ukraine, to a peak of &euro;340 per MWh in August 2022 when concerns about a winter shortage crested.   After conservation efforts, European countries securing liquefied natural gas imports, and a warmer-than-feared winter, prices fell back to [&euro;76](https://www.nytimes.com/2023/01/03/business/europe-natural-gas-prices.html) by January 2023 and to [&euro;40](https://www.nasdaq.com/articles/europe-gas-dutch-benchmark-hits-19-month-low-on-strong-winds-and-milder-weather) by March.  In 2020, these prices were under &euro;20 per MWh.

- **U.S. Natural Gas Prices**.  Quoted in MMBTU (million british thermal units).  Often are in the $2 to $4 range, but driven by Ukraine-driven supply shocks, [briefly exceeded $9 in 2022](https://www.wsj.com/articles/natural-gas-prices-plunge-and-drillers-dial-back-236a2a9).  In California, a pipeline closure limited supply and prices averaged [$19.40 per MMBTU in early January, and briefly exceeded $40](https://www.wsj.com/articles/natural-gas-prices-have-fallen-back-to-earthexcept-in-california-11673411627) while the Henry Hub benchmark was under $4.00.   

- **U.S. electricity generation**.  In February 2023, New England faced a cold snap that saw next-day wholesale electricity prices jump ["by 140% to about $237 per megawatt hour."](https://www.reuters.com/business/energy/wholesale-power-prices-spike-us-northeast-arctic-blast-arrives-2023-02-03/).  In 2019 the Millstone nuclear plant in Connecticut was kept in operation in part for a deal where the plant operator was guaranteed to sell half of its generation for [$49.99 per MWh](https://www.cga.ct.gov/2020/rpt/pdf/2020-R-0203.pdf).

- **Global Energy Consumption**.  BP's [Statistical Review of World Energy 2022](https://www.bp.com/content/dam/bp/business-sites/en/global/corporate/pdfs/energy-economics/statistical-review/bp-stats-review-2022-full-report.pdf) reported that global primary energy consumption was 595 exajoules (EJ) in 2021, 31 EJ above 2020 and 8 EJ higher than the pre-COVID 2019 levels.

- **Utility Bills**.  Electricity customers are generally billed in cents per kilowatt-hour (kWh).  Utility natural gas is frequently billed in "Therms" (100,000 BTU) or "CCF" (hundred cubic feed, which is 1.037 Therms).  In Europe, natural gas is typically billed per kWh.   In Australia, billing for gas is in megajoules (MJ). 

- **Oil**.  And of course, crude oil is always quoted by market participants in dollars per barrel.  And heating oil is sold in gallons when it is delivered by truck into New England homes.

Here we go!

<!--more-->

### Energy and Power

A **joule (J)** is the standard (SI) unit of **energy**, equivalent to the work done by applying 1 Newton of force over 1 meter of distance.  A 500 mL single-serve bottle of water has a mass of 0.5 kg.  Gravity at the Earth's surface causes acceleration of ~10 $m/s^2$,[^1] so the weight of gravity applies about $0.5 kg \times 10 m / s^2 = 5 N$ of force on the bottle.  

[^1]: Actually $9.8 m/s^2$, but the math is easier at 10. 

If I apply $5\ N$ of upward force to offset gravity and lift the bottle 1 meter from the floor (stomach height for me), I have increased the bottle's gravitational potential energy by $5\ N \times 1\ m = 5\ J$ of gravitational potential energy.  If I drop it, by the time it hits the ground it is moving with about $5\ J$ of kinetic energy.  If I do the same exercise at a height of 20 cm (~8 inches), the quantity of energy involved is 1 joule. 

**Power** is a rate of energy flow or energy transfer, and is measured in quantity of energy per unit time.  A **watt** is the SI unit, defined as joules per second.   Lifting and dropping a liter bottle from a height of 1 meter ($5\ J$ each) once per second generates power at a rate of 5 watts.  If this could be harnessed with a cable, pulley and alternator system (this is the basic principle behind gravity based storage), for example, it theoretically would be enough power to light up the lightbulb on my night table.[^2]

[^2]:  *What the hell is a gigawatt??*  It's 1 billion watts, about the power output from a large convential powerplant such as a nuclear, coal or natural gas plant.  Comparing this to dropping bottles of water?  A double decker Airbus A380 airplane has a mass of about half a million kilograms when full.  200 of these super-jumbo jets together represents 100 million kg, and raising them all one meter off the ground gives them $(100 \times 10^6~kg) \times 10\ m/s^2 \times 1\ m = 10^9\ J$ or 1 gigajoule of gravitational potential energy.  Dropping them to the ground over the course of 1 second converts that energy into kinetic energy at a rate of 1 GJ per second, a power rate of 1 gigawatt (GW).  Do that over and over again and you've got yourself a 1 gigawatt power plant.  Doing this with 242 planes gives you 1.21 gigawatts!

Taking this relationship backwards, a joule is the amount of energy delivered from one watt of power for one second: one joule equals 
one "watt second."  Since one hour is 3,600 seconds, a **watt hour** is 3,600 joules and the unit of consumption for residential electricity, a **kilowatt  hour (kWh)** is one thousand of those: 3,600,000 joules or 3.6 megajoules (MJ).

To compare some energy numbers at the macroscopic scale:  

- My house uses about 30,000 kWh (a.k.a. 30 MWh) of electricity in a year. 
- The U.S. generates and consumes [about 4,000 TWh](https://www.eia.gov/energyexplained/electricity/electricity-in-the-us-generation-capacity-and-sales.php) of electricity per year.   A terawatt hour is one billion kWh, so this is $(4,000 \times 10^9 kWh) \times (3.6 \times 10^6 J / kWh) = 1.44 \times 10^{19} J$.  $10^{18}$ gets a prefix "exa", so this is 14.4 exajoules (14.4 EJ). 
- So U.S. **electricity consumption** alone (not including other uses of energy like heat and transportation) represents 2.3% of the 595 EJ of total global primary energy consumption in 2021.
- By contrast, the United State's broader total primary energy consumption in 2021 was 93 EJ, about 16% of global energy consumption.
- Note that electricity consumption in the U.S. reflects only ~15% of total energy use. 

And power:

- Simply dividing my 30,000 kWh of annual electricity use in a year by $365 \times 24 = 8,760$ gives an **average power consumption** for my house of 3.4 kW.  But my [actual power usage](https://jgkramer.github.io/2022/11/07/Electricity_Usage_Anecdotes.html) ranges from ~1 kW to a peak power of ~14 kW with the air conditioners running full-blast in the summer.  The difference between average power and peak power is why one needs to be careful in reading stats stating how many homes [power plants can serve](https://www.cnet.com/home/energy-and-utilities/gigawatt-the-solar-energy-term-you-should-know-about/), especially when it comes to renewable sources where generation is non-constant.
- For the entire U.S., dividing $4,000\ TWh$ by 8,760 hours per year gives us an **average U.S. power** consumption of 0.456 terawatts or 456 GW.  According to the EIA, at the end of 2021 the U.S. had [1,144 GW total](https://www.eia.gov/energyexplained/electricity/electricity-in-the-us-generation-capacity-and-sales.php) of utility-scale electricity generation capacity, or about 2.5x the average power consumption.  This "overcapacity" makes sense given the significant deviations across hours of the day and seasons of electricity usage.

#### Another Unit: BTU's

One more important unit of (thermal) energy, at least in the U.S., is the BTU (British Thermal Unit).  Originally conceived the heat energy required to raise the temperature of one pound of water by 1&deg;F, it is now defined as [~1,055 joules](https://www.britannica.com/science/British-thermal-unit).  A BTU is a small unit of energy practically speakin: a Therm (my residential billing unit for utility natural gas) is 100,000, and trading prices for natural gas in the U.S. are quoted in MMBTU, or millions of BTU.[^3]

[^3]:  Traded prices also generally specify a location: for example, Henry Hub gas prices refer to natural gas delivered at a particular distribution hub in Erath, Lousiana. 

BTU's are also a typical unit of sizing for air conditioning units in the U.S. (e.g., a window air conditioner might be an 8,000 BTU unit).   This measures the amount of heat energy transferred out of the space being cooled per hour (e.g., 8,000 BTU of heat energy per hour removed to the outside to cool a room).  Larger air conditioning units like central A/C are often measured in "tons", equivalent to 12,000 BTU, why not.[^4]

[^4]:  It's called a "ton" because melting a ton of ice requires [286,000 BTU](https://davisac.com/blog/the-reason-air-conditioner-capacity-is-measured-in-tons#:~:text=Rounding%20up%2011%2C917%20Btu%2Fhr,ton%20of%20air%20conditioner%20capacity) of thermal energy: spread over 24 hours, this is about 12,000 BTU per hour of heat transfer.   Sounds pretty heavy!

#### Conversion Reference Table

Here is a conversion table between watt hours, joules and BTU.

<STYLE TYPE="text/css">
<!--
TH{font-family: Arial; font-size: 9pt; text-align: center;}
TD{font-family: Arial; font-size: 9pt; text-align: center;}
--->
</STYLE>
<table>
    <tr>
        <th colspan="4" scope ="colgroup" style="background-color: #D6EEEE">Using Watt-hours</th>
    </tr>
    <tr>
        <th scope="col" style="background-color: #D6EEEE">Watt-hours</th> 
        <th scope="col" style="background-color: #D6EEEE">Joules</th> 
        <th scope="col" style="background-color: #D6EEEE">BTU</th>
        <th scope="col" style="background-color: #D6EEEE">Explanation</th>
    </tr>
    <tr>
        <td>1 W s</td><td>1 J </td><td>0.00095 BTU</td><td>Definition (watt = joule / s)</td>
    </tr>
    <tr>
        <td>1 W h</td><td>3.6 kJ</td><td>3.412 BTU</td><td>Hour = 3,600 seconds</td>
    </tr>
    <tr>
        <td>1 kWh</td><td>3.6 MJ</td><td>3,412 BTU</td><td>x1000</td>
    </tr>
    <tr>
        <td>1 MWh</td><td>3.6 GJ</td><td>3.412 MMBTU</td><td>x1000</td>
    </tr>
     <tr>
         <td>1 GWh</td><td>3.6 TJ</td><td>3,412 MMBTU</td><td>Tera = $10^{12}$</td>
    </tr>
     <tr>
         <td>1 TWh</td><td>3.6 PJ</td><td>3.4 million MMBTU</td><td>Peta = $10^{15}$</td>
    </tr>    
    <tr>
         <td>1,000 TWh</td><td>3.6 EJ</td><td>3.4 billion MMBTU</td><td>Exa = $10^{18}$</td>
    </tr>  
</table>

#### Oil: Barrels and Gallons.

A barrel of oil is 42 gallons.   One barrel of crude oil contains about [5.7 million BTU](https://www.eia.gov/energyexplained/units-and-calculators/).  And a gallon of home heating oil (how I used to heat my old home in Connecticut) has 138,500 BTU of thermal energy.

How important is oil to the global energy mix? 

- Global oil production as of 2021 is about [90 million barrels per day](https://www.statista.com/statistics/265203/global-oil-production-since-in-barrels-per-day), or about 32.8 billion barrels per year.
- In energy terms this equates to $32.8 \times 10^9\ bbl \times 5.7\ MMBTU / bbl \times 3.6~EJ / 3.4 \times 10^9\ MMBTU = 198\ EJ$ of total energy.   
- Oil therefore speaks for one-third of global primary energy consumption of 595 EJ.[^5]

[^5]:  BP's statistical review reports that coal and natural gas each represent another ~25% of total energy consumption, with nuclear, hydro and renewables representing the rest. 

### Thermal Energy vs. Electrical Energy

#### Heat Engines and Heat Rate

Another important concept is the difference in forms of energy.  Most relevant to energy markets are two kinds: thermal (heat) energy and electrical 
energy.  Fuels such as oil and gas can be thought of as containing thermal energy (stored in chemical bonds and released through combustion).   These can be: 

1. Combusted and the resulting heat consumed directly, as with utility natural gas burned in my home's furnace to heat my house; or 
2. Combusted and the resulting heat used in a heat engine or turbine to convert the energy to electrical energy, as with natural gas burned in a power plant to heat another fluid that drives a turbine which in turn generates electricity. 

In usage (1) above more than 95% of the thermal energy stored in natural gas, for example, can be captured to heat a home.  Converting heat energy to electrical energy via (2) results in lost energy due to the thermodynamic constraints of heat engines.[^6]

[^6]:  Carnot's Theorem states that a heat engine operating between a hot temperature $T_H$ (measured against absolute zero) and a cold temperature $T_C$ cannot have efficiency exceeding ${T_H - T_C} \over T_H$.

The efficiency of a power plant's conversion of thermal energy in fuel into electrical energy is referred to as the plant's **heat rate**.  Heat rate is [generally defined](https://www.eia.gov/tools/faqs/faq.php?id=107&t=3) as the amount of fuel energy required to generate a given amount of eletricity.  In the U.S., this is quoted as the number of BTU's of (thermal) energy input required to generate 1 kWh of electricity.   1 kWh is 3,412 BTU's, so all heat rates are higher than 3,412.  A heat rate of 6,800 has a 50% energy conversion efficiency: fuel with 6,800 BTU of thermal energy is needed to produce 3,400 kWh of electricity.  Efficient natural gas plants have heat rates in the [7,000 to 8,000 area](https://www.eia.gov/electricity/annual/html/epa_08_01.html), with coal plants around 10,000.

In European countries where thermal energy is quoted in kWh or MWh, this concept is more directly expressed in [percentage efficiency](https://www.statista.com/statistics/548943/thermal-efficiency-gas-turbine-stations-uk/), i.e., a 50% effcient natural gas plant requires gas with 2 kWh of thermal energy to generate 1 kWh of electricity.
 
### Applications

#### Heating Prices 

Now we are equipped to wrangle some of the disparate price quotations we have seen.  We'll begin with a simple one: the prices of natural gas, as used directly by consumers for thermal energy.  

A couple of points of reference: in the Las Vegas area, with mild winters, my family consumed 1,420 therms of gas in 2022, with about 72% of this coming in January, February, November and December.  A therm is 100,000 BTU, so my annual gas utility gas gost reflects 142 million BTU.  Converting this into kilowatt hours, that is $142 \times 10^6\ BTU \times 1\ kWh / 3,412\ BTU = 41,620\ kWh$ of thermal energy.  Friends of ours in Connecticut consume about 2,300 therms of gas in a year, about $67,400\ kWh$.  

<STYLE TYPE="text/css">
<!--
TH{font-family: Arial; font-size: 9pt; text-align: center;}
TD{font-family: Arial; font-size: 9pt; text-align: center;}
--->
</STYLE>
<table>
    <tr>
        <th scope="col" style="background-color: #D6EEEE"> </th> 
        <th scope="col" style="background-color: #D6EEEE">Quoted Price</th>
        <th scope="col" style="background-color: #D6EEEE">Conversion to kWh</th>
        <th scope="col" style="background-color: #D6EEEE">Price per kWh</th>
        <th scope="col" style="background-color: #D6EEEE">1 Year of My Nevada Heating (41,620 kWh)</th>
        <th scope="col" style="background-color: #D6EEEE">1 Year of Connecticut heating (67,400 kWh)</th>
    </tr>
    <tr>
        <th style="background-color: #D6EEEE">Avg. U.S. Natural Gas Prices since 2010</th> 
        <td>$3.50 / MMBTU </td><td> $\times 3.41\ MMBTU / 1000\ kWh$ </td><td> $= \$0.011$ </td><td> $497 </td><td> $805 </td>
    </tr>
    <tr>
        <th style="background-color: #D6EEEE">Ukraine-Elevated U.S. Prices</th> 
        <td>$9.00 / MMBTU </td><td> $\times 3.41\ MMBTU / 1000\ kWh$ </td><td> $= \$0.031$ </td><td> $1,278 </td><td> $2,070 </td>
    </tr>
    <tr>
        <th style="background-color: #D6EEEE">California Supply-Disrupted Gas Prices</th>
        <td>$40.00 / MMBTU </td><td> $\times 3.41\ MMBTU / 1000\ kWh$ </td><td> $= \$0.137$ </td><td> $5,680 </td><td> $9,200 </td>
    </tr>
    <tr>
        <th style="background-color: #D6EEEE">2020 European Gas Prices</th> 
        <td>&euro;15 / MWh </td> <td> $\times 1.05 USD / EUR \times 1 MWh / 1000\ kWh$ </td><td> $= \$0.016$</td><td> $656 </td> <td> $1,061 </td>
    </tr>
    <tr>
        <th style="background-color: #D6EEEE">Ukraine-Spike August 2022 European Gas</th> 
        <td>&euro;340 / MWh </td> <td> $\times 1.05 USD / EUR \times 1 MWh / 1000\ kWh$ </td><td> $= \$0.357$</td><td> $14,858 </td> <td> $24,062 </td>
    </tr>
</table>

The above prices are based on traded prices in commodities markets, and are more akin to wholesale prices, with retail prices being even higher after taking into account the costs of delivery and customer service.  However, they give some context to energy prices quoted in the news.  In the U.S., natural gas heating costs are low compared to other parts of the world, and while the Russian invasion of Ukraine caused prices to spike and heating bills to rise at a rate of hundreds of dollars per year.   

But in Europe this impact was thousands of dollars per year.  This is why, for example, the U.K. spent around [&pound;70 billion](https://www.reuters.com/business/energy/uk-energy-support-schemes-cost-halved-mild-winter-tames-prices-nao-2023-02-07/) in energy subsidies during the 2022-2023 winter.  The same kind of subsidy-policy impact was achieved in the U.S., only at the $40 / MMBTU gas level in California in early 2023, [where the state responded with energy bill credits to consumers.](https://www.gov.ca.gov/2023/02/06/governor-newsom-calls-for-federal-investigation-of-high-natural-gas-prices-as-california-provides-relief/).

#### Electricity 

In dealing with electricity, we need to be cognizant of the conversion from thermal energy inputs to electricity outputs.  

For example, since the low cost of natural gas (and electricity generation by natural gas plants) has been identified as an economic culprit for the closure of nuclear power plants in the U.S., we'll benchmark the fuel-component cost of gas-generated electricity against Connecticut's contract to purchase electricity from Millstone power plant at $49.99 per MWh, or $0.05 per kWh.

<STYLE TYPE="text/css">
<!--
TH{font-family: Arial; font-size: 9pt; text-align: center;}
TD{font-family: Arial; font-size: 9pt; text-align: center;}
--->
</STYLE>
<table>
    <tr>
        <th scope="col" style="background-color: #D6EEEE"> </th> 
        <th scope="col" style="background-color: #D6EEEE">Base Price</th> 
        <th scope="col" style="background-color: #D6EEEE">Conversion to BTU</th>
        <th scope="col" style="background-color: #D6EEEE">Heat Rate</th>
        <th scope="col" style="background-color: #D6EEEE">Cost per kWh / MWh of Electricity</th>
    </tr>
    <tr>
        <th style="background-color: #D6EEEE">Avg. U.S. Natural Gas Prices since 2010</th> 
        <td>$3.50</td><td> $\times 1 / 1,000,000$ </td><td> $\times 7500$ </td><td> $= \$0.0263 / \$26.25$ </td>
    </tr>
    <tr>
        <th style="background-color: #D6EEEE">90th Percentile Natural Gas Prices Since 2010</th> 
        <td>$5.00</td><td> $\times 1 / 1,000,000$ </td><td> $\times 7500$ </td><td> $= \$0.0375 / \$37.50 $ </td>
    </tr>
    <tr>
        <th style="background-color: #D6EEEE">Ukraine-Driven Spike in U.S. Natural Gas Prices</th>
        <td>$9.00</td><td> $\times 1 / 1,000,000$ </td><td> $\times 7500$ </td><td> $= \$0.0675 / \$67.50$ </td>
    </tr>
</table>

The simple economic criticism of nuclear has some appeal: most of the time, natural gas prices are low enough that the $50 / MWh Connecticut agrement is a higher price for wholesale electricity than would otherwise be available (the brekaeven is around $6.67).  But this simple analysis does not take into account the zero-carbon nature of nuclear generation compared to gas.  Nor does it account for the volatility in the gas market and the possibility that as liquefied natural gas exports become more common in the U.S., that the low prices of U.S. gas may converge towards the higher global prices. 

#### Oil

Oil is not frequently used for electricity generation, but it is used for home heating in New England.  Home heating oil is often regarded as a more expensive fuel for home heating than natural gas.   I'll test that hypothesis using: (1) the current cost of home heating oil in New England [($3.00 wholesale)](https://www.eia.gov/dnav/pet/pet_pri_wfr_a_EPD2F_PWR_dpgal_w.htm), (2) the trading price of WTI crude oil ($70 / barrel), (3) the trading price of Henry Hub natural gas in the U.S. in February 2023 ($2.38 / MMBTU for Henry Hub) and (4) the trading price of Dutch TTF natural gas in Europe as of March 2023 (&euro;40 per MWh).  

<STYLE TYPE="text/css">
<!--
TH{font-family: Arial; font-size: 9pt; text-align: center;}
TD{font-family: Arial; font-size: 9pt; text-align: center;}
--->
</STYLE>
<table>
    <tr>
        <th scope="col" style="background-color: #D6EEEE"> </th> 
        <th scope="col" style="background-color: #D6EEEE">Base Price</th> 
        <th scope="col" style="background-color: #D6EEEE">Conversion 1</th>
        <th scope="col" style="background-color: #D6EEEE">Conversion 2</th>
        <th scope="col" style="background-color: #D6EEEE">Cost per kWh heating energy</th>
    </tr>
    <tr>
        <th style="background-color: #D6EEEE">Home Heating Oil</th>
        <td>$3.00 / gallon </td><td> $\times 1\ gal / 138,500\ BTU$ </td><td> $\times 3412\ BTU / 1\ kWh$ </td><td> $= \$0.074 $</td>
    </tr>
    <tr>
        <th style="background-color: #D6EEEE">WTI Crude Oil</th>
        <td>$70 / barrel </td><td> $\times 1\ barrel / 5.7\ million\ BTU$ </td><td> $\times\ 3412 BTU / 1 kWh$ </td><td> $= \$0.042 $</td>
    </tr>
    <tr>
        <th style="background-color: #D6EEEE">U.S. Natural Gas</th>
        <td>$2.38 / MMBTU </td><td> $\times 3.412 MMBTU / 1 MWh$ </td><td> $\times 1\ MWh / 1,000\ kWh$ </td><td> $= \$0.008$ </td>
    </tr>
    <tr>
        <th style="background-color: #D6EEEE">Euro Natural Gas</th>
        <td>&euro;40 / MWh </td><td> $\times 1\ EUR / 1.09\ USD$ </td><td> $\times 1\ MWh / 1,000\ kWh$ </td><td> $= \$0.037$ </td>
    </tr>
</table>

The relationship between the first two prices is intuitive: heating oil is a more finished product and its price reflects both the cost of the raw input commodity, crude oil, as well as the costs of processing.  Homes aren't heated with crude oil directly.  

The price per kWh of natural gas heating seems shockingly low compared to heating oil, cheaper by a factor of ~9x.  By contrast, the EIA estimates that oil-heating homes costs about [2.5x the cost](https://www.eia.gov/outlooks/steo/report/winterfuels.php) of gas-heating homes.   What is likely happening there is that the heating oil price, being a finished product that is relatively cheap and easy to transport, likely represents a price that is close to that paid by retail customers.  Natural gas commodity trading levels, by contrast, is the price of a product that is far away from end customers.  Natural gas is difficult and costly to store and transport, and as such the residential price is often [multiples of the traded price](https://www.eia.gov/todayinenergy/detail.php?id=20272).

### Wrap

Plutonium isn't yet available in every corner drug store, but multiplication and dimensional analysis is readily available to help make sense of a lot of energy numbers floating around.  Safe travels!
