# The UK Energy Market

-

![Graph showing alternating current](./images/ac.svg)

Script:
Starting off with the basics, energy in the UK (and most countries) is produced and delivered to homes and businesses in alternating current. This means that the voltage goes up and down multiple times per second. In the UK this is between about -230 volts and +230 volts and back again, 50 times per second.

-

![Messy network of various kinds of power station connected to pylons, which then connect to a standard UK power socket](./images/energy-grid.svg) <!-- .element height="500px" -->

Script:
Now, a large number of generating sources are all connected to the UK energy grid, as are an even large number of energy consumers. Each has to be synchronised and produce power at this rate of 50 hertz.

-

![Frequency meter with a green region at 50 Hz and red regions towards 49 Hz and 51 Hz](./images/frequency-meter.svg)

Script:
If too much power goes into the system, then the frequency starts to rise, and if not enough goes in, then the frequency goes down. This is bad&mdash;not only because your devices you plug in at home expect 50 hertz and won't get the right amount of power, but because massive machines like power stations are designed to spin at a very specific frequency, and if you start spinning them at the wrong speed they will break, which creates a very expensive repair bill. (In reality, you will see blackouts rather than exploding power stations.)

-

![National Grid logo](./images/national-grid.svg)

Script:
National Grid is the company responsible for making sure that this doesn't happen, by ensuring that the power being generated balances the power being used. This has got more difficult in recent years as more renewable energy has connected to the grid, because it is harder to predict when production will increase or decrease.

-

![Flowchart showing players in the market](./images/market-flowchart.svg) <!-- .element height="600px" -->

Script:
Thanks to neoliberalism and an obsession by a certain kind of economist, it has been decided that the best way to solve this problem (like any problem) is to introduce a market. There are a number of different players in this particular market. The UK power market structure is such that suppliers must purchase and pay for all the energy consumed by their customers. Wholesale markets allow suppliers and generators to buy and sell electricity to ensure this requirement can be met. The system operator (National Grid) has final responsibility to ensure supply meets demand. If the system operator must take action to balance the system, these balancing costs are targeted to those who cause the action to be taken. Charges are designed to incentivise parties to trade ahead of delivery / consumption.

-

![Timeline of when elements of the market occur](./images/market-timeline.svg) <!-- .element height="600px" -->

Script:
The market has a number of different mechanisms, happening over various timescales, to trade the energy that will be delivered at a given time $T$. Forwards and futures markets trade energy months or years before it exists. The day-ahead hourly auction agrees trades and sets the price of energy for the following "market day", from 11pm on the current day to 11pm on the next. There is also a within-day continuous market. Frequency response is done to ensure that the energy flows balance and the grid operates at the correct frequency. And any energy that needs to move to enable that hasn't been pre-traded already gets paid for via the imbalance mechanism.

-

![Sketch graph showing energy price against volume, with two curves: the predicted supply and predicted demand. The crossing point of the two curves is at the market clearing price and market clearing volume.](./images/dayahead-curves.svg)

Script:
There are two day-ahead markets, operated by EPEX Spot and NORD Pool. Until Brexit these were coupled together, but now they can have different results. The day-ahead hourly auction divides up the market day into one-hour blocks. Participants submit hourly orders, and an algorithm establishes a demand and supply curves for each hour of the following day based on orders submitted. The Auction Clearing Price is the intersection of the two curves. Max price: 3000 £/MWh. Min price:  -500 £/MWh, and trades are legally binding. Other things to note are that the price is never higher than the purchase price fixed by the buyer, or lower than the sale price offered by the seller (but can be lower and higher respectively). Exchange members use the auction to sell and buy the largest part of the produced/ needed electricity.

-

- Participants submit Buy and Sell Orders around 8:30am each day for each Hour from 23:00 on the current day to 23:00 the following day (the EFA Day)
- Orders consist of the volume of energy the auction participant is seeking to  buy or sell and the max / min price they are willing to transact at;
  - Buy Order: I am willing to Buy [X] MWh in Hour [n] up to a price of £[B]/MWh
  - Sell Order:  I am will to Sell [X] MWh in Hour [n] as long as the price is at least £[S]/MWh
- Multiple orders can be submitted for each hour at different price levels (allowing for strategies based on splitting volume to different price levels)

-

- By 12pm each day, EPEX / N2EX will match the buy and sell orders;
  - Sell Orders priced less than or equal to the Auction Clear Price will be filled  (sellers looking to receive more than the auction clear price will not have made a sale)
  - Buy Orders priced more than or equal to the Auction Clear Price will be filled  (buyers looking to pay less than the auction clear price will not have  made a purchase)
- All participants pay or are paid at the Auction Clearing Price for the hour. Prices are in £/MWh

-

![Example of a graph showing demand across a 24-hour period, with price being lowest overnight and highest in the afternoon. Demand is stratified so at low demand only renewables and nuclear contribute, but at high demand combined cycles, coal, and combustion turbines contribute.](./images/hourly-price-example.gif) <!-- .element height="400px" -->

Script:
So what determines the price? The cost of generating power is based on the cost of fuel and generator efficiency. For example,  a gas generator must buy fuel, covert it to power  via some efficiency factor (modern generators typically being more efficient) and pay for resulting carbon obligations. Some generation has negligible marginal fuel costs, such as  renewables or nuclear. At higher levels of demand, more expensive generation must be used – resulting in higher prices. The Market Price will be set by the marginal generating unit&mdash;the minimum profitability for the most expensive generation method needed to match the anticipated demand.

-

![Screenshot of a news article discussing negative electricity prices](./images/negative-price.png) <!-- .element height="500px" -->

Script:
If there is an excess of production and low demand, the market would usually prevent negative prices, since no market participant would want to pay to produce energy. However, some renewables receive subsidies, so can profitably operate while paying to produce. In extreme cases, as was seen at the start of COVID, this can drive the wholesale price negative, so that consumers are paid to use energy (as the power has nowhere else to go).

-

![Diagram showing the phases of balancing if supply is insufficient](./images/balancing.png) <!-- .element height="500px" -->

Script:
As a result of the total position of all Parties there will be a net overall imbalance on the system (i.e.  Generation ≠ Demand). Around 1 Hour Ahead of delivery, National Grid starts to take action to balance generation and demand through the Balancing Mechanism. The System Operator (National Grid) matches generation and demand by buying and selling energy in the Balancing Mechanism via Bid / Offer Acceptances (BOAs). These are _paid as bid_, unlike in the day-ahead auction. January 2021 saw highest BM prices for 20 years. Tight margins (the gap between generation and demand) and low temperatures pushed National Grid ESO to issue two Electricity Margin Notices (EMN). On Wednesday 6 January, EDF’s West Burton B was called on £4,000 / MWh. Price volatility is likely to become increasingly common, as Great Britain relies increasingly on intermittent generation.

-

![Photograph of the National Grid control room](./images/national-grid-control-room.jpg) <!-- .element height="500px" -->

Script:
This is where this balancing is managed from. If you've ever seen the black and white moving pattern in the corner of a television screen, this is to alert National Grid that a commercial break is about to start, because this can create a spike in demand as everyone gets up to put the kettle on.

-

## The AIMLAC Energy Market

- Day-ahead market
  - Hourly auction
  - Bids close 9am **UTC** for market day beginning at 11pm **UTC**
  - Bids are capped at the capacity of the grid connection at the AIMLAC site
- Imbalance market
  - Imbalance price from EPEX Spot is always used, no trading here

Script:
To make your and our lives easier, we have created a simplified version of this market for the challenge. Rather than the large variety of different systems in reality, we cut things down to two markets: the day-ahead auction, in blocks of one hour, with bids closing at 9am for a market day starting at 11pm. Unlike the real markets, we do not account for daylight saving time here; all times are in UTC. Because this simplification allows for some unchecked arbitrage that in the real world would distort the market to the point it became unprofitable, the fictional grid has imposed the constraint that you can only buy or sell as much as your grid connection would allow&mdash;i.e. you act as a bona fide producer and consumer rather than a speculative trader. Any excess or shortfall is automatically bought or sold at the imbalance price; no bids are made in this market.
