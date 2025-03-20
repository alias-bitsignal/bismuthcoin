---
title: Tesla Battery Monitoring
date: 2020-05-25
authors:
  - name: Bismuth Foundation
    link: https://github.com/bismuthfoundation
    image: https://raw.githubusercontent.com/bismuthfoundation/MEDIA-KIT/refs/heads/master/Logo_v2/bis300px.png
tags:
  - plugin
  - crystal
  - dapp
---
![](/images/2020-05-25-battery-monitoring.webp)
Tesla is a market leader in electric vehicles (EVs). They have currently sold and delivered more than 1 million EVs worldwide while production is ramping up fast with new factories in Europe and China.
<!--more-->

## Tesla Battery Monitoring on Blockchain

Although EVs in general require little maintenance, one expensive component in the car needs to be treated with care: the battery. This video explains what can happen if it is not. With Tesla EVs, there is an 8-year warranty on the battery. After this period of time, there is no longer a warranty, but a car is normally expected to last much longer than this. Although battery costs are declining over time, a replacement battery would typically cost $10,000 or more nowadays.

So, what can an owner do to maximize the lifetime of his or her EV battery? The CEO of Tesla – Elon Musk – has previously recommended to keep the battery level between 80% and 30%, see this tweet and the reply.

![](/images/2020-05-25-tweet.png)

The table below illustrates that the lifetime of Li-Ion batteries is limited to a number of charging cycles. As seen from the table, smaller charging cycles consume proportionally less lifetime compared with full charges. The typical lifetime of a Li-Ion battery with 0-100% charge cycles is typically 450 cycles. With 10% charge cycles, on the other hand, the lifetime would typically be 10,000 cycles or more. So, a battery with 10% charging cycles will typically achieve a double lifetime compared to one which has done 0-100% cycles, for the same kWh energy consumption. It is clear from this observation that the charging behavior of the owner will significantly influence the condition of the battery, and hence the potential resale value of the vehicle.

![](/images/2020-05-25-Li-cycle-life.png)
Table from the paper: Yu Miao et.al., “Current Li-Ion Battery Technologies in Electric Vehicles and Opportunities for Advancements”, https://doi.org/10.3390/en12061074

When selling an EV on the second hand market, the remaining lifetime of the battery should be one of the most important questions. However, this question could be quite difficult to answer. If the battery condition is unknown, this could affect the resale value by giving the owner a lower price regardless of the actual condition. If, on the other hand the owner can prove, somehow, that the battery was treated with care and the expected amount of remaining lifetime is significant, the resale value of the vehicle should naturally be higher.

On the Tesla screen inside the vehicle and also on Tesla’s phone app, it is possible to view and inspect some battery parameters. However, these parameters are lost over time. There is a plot in the car which shows the efficiency (Wh/mi or Wh/km), but this plot is limited to the last few miles or kilometers. After a certain distance those values are lost for the owner.

Tesla has an (unofficial) API which allows 3rd party services to log data from owner’s cars. However, by using these services you have to either expose your Tesla login credentials or give an API token to these services. Many owners do not feel comfortable doing this, because it means the 3rd party service could potentially take control over your car, not just read data. Also, there is no guarantee that a 3rd party web service will continue to exist over the lifetime of your car. The average lifetime of an app or a web service is usually considerably shorter than a vehicle. If the operator of the service decides to discontinue – for whatever reason – your vehicle data may be lost. Even if you have a backup of the data, this may not be very useful if the user interface to display and analyze the data is no longer available. Another factor is the cost: most of the 3rd party services require you to pay a monthly fee to use their service to display and analyze your own historic data.

This is where blockchain technology enters the picture. The article [“Decentralized Condition Monitoring”](/blog/2020-04-30-condition-monitoring/) explains how a public blockchain can be a good solution when the following conditions are met:

* More than one participant needs to be able to submit and update data.
* The participants do not need to know and trust each other.
* The data does not need to be private.
* The database needs to be resistant to attacks or censorship.

For the above-mentioned reasons a solution for battery condition monitoring of Tesla EVs has been implemented by using the open source Bismuth public blockchain. Specifically, a Tesla plug-in (also called “crystal” in Bismuth terminology) has been developed for use together with the open source [TornadoWallet](https://github.com/bismuthfoundation/TornadoWallet). Some of the features of the implemented solution are:

* The vehicle owner will not expose his or her login credentials to anyone, since the app runs on the local computer.
* All the code involved is open source and publicly available on GitHub on the official account of the Bismuth Foundation. Hence, anyone can verify that the software is safe to use and that there is no malicious intent.
* When the owner submits data from the vehicle to the public blockchain, he or she can decide to publish the vehicle’s identification number (VIN) openly, or to encrypt it with a password to remain anonymous. This should ideally be a strong password, and not identical to an existing one used for other apps or services.
* If the owner wants to sell the vehicle in the future, the password can be revealed to the new owner. The new owner can then verify that the submitted data actually belongs to the vehicle’s VIN.
* The first owner can transfer the virtual asset on the blockchain to the new owner, to allow the new owner to continue to submit data from the vehicle using his or her own account, while keeping the entire track record.
* To discourage spam and fake data, there are some costs (fees in BIS currency) involved when registering a new VIN on the chain and to submit data.
* If someone submits fake data to the chain, this would most likely be detected by other users, or by new data analysis services based on the publicly available data. For example, the odometer of a car can never decrease, or the amount of energy (kWh) added should, to some extent, match the battery level and distance driven parameters.
* To view and analyze the data is free for everyone. A public website has been set up for this purpose, to allow anyone to view and analyze the data without owning a Tesla vehicle or the need to run the TornadoWallet on their local computer. 

The public website has been developed to also work well with the Tesla in-car browser (Chromium). The screenshots below are taken from an actual vehicle, for both Night and Day mode.

![](/images/2020-05-25-Tesla-Bismuth-Crystal-01.png)
viewed in a Tesla vehicle (Night Mode).
![](/images/2020-05-25-Tesla-Bismuth-Crystal-02.png)
viewed in a Tesla vehicle (Day Mode).

If you have an Android phone it is also possible to run the Tesla plug-in locally by using Termux, [see link](https://steinbuch.wordpress.com/2015/01/24/tesla-model-s-battery-degradation-data). In this way, it is possible to submit vehicle data while on the road, for example just before and after charging your vehicle at a public supercharger station.

The screenshot below shows the data viewing and analysis section of the app. In this example, the vehicle IDs available for viewing have been encrypted with a password. Hence the actual VIN numbers of these cars are not available. The address on the right shows which Bismuth account has submitted the data.

![](/images/2020-05-25-Tesla-Bismuth-Crystal-03.png)

In the menu above, a vehicle asset ID is selected as well as the start and end dates. After that, a number of parameters are available for viewing and analysis. One example plot is the “Estimated Max Range vs. Odometer” and the associated curve fit, see plot below.

![](/images/2020-05-25-Tesla-Bismuth-Crystal-04.png)
Estimated Range vs. Odometer and Curve Fit.

The green dots in this plot represent individual data points submitted by the owner to the blockchain. The parameter “Estimated Max Range” is based on data from the Tesla API, by dividing the estimated remaining range with the battery level. The curve fit is based on the data points matching the “Range Filter”. In this example only the 1% largest values are used to estimate the red curve. As can be seen from this plot, the estimated max range is falling, from about 485km to 480km. However, this plot does not necessarily represent the true battery condition, since a number of parameters may influence the estimate, such as ambient temperature, driving style, road conditions, etc. The way to get a more accurate measure of maximum range is to do a full charge (0-100%) and then check the EPA rated range (in North America) or Typical range (in Europe and Asia/Pacific), see link. However, you don’t want to do this exercise too often, as a 0-100% deep charging cycle is exactly what reduces the remaining lifetime of the battery the most.

If the owner submits data to the blockchain regularly, just before and after every charging event, it is instead possible to estimate the battery life without having to do deep charges. If all the charging events are recorded, Bismuth’s Tesla app allows for counting the cycles, using a method called rainflow counting, as illustrated in the screenshots below. The rainflow method is normally used in counting fatigue cycles in mechanical engineering, but it can also be used for counting battery cycles.

![](/images/2020-05-25-Tesla-Bismuth-Crystal-05.png)
![](/images/2020-05-25-Tesla-Bismuth-Crystal-06.png)
Counted battery cycles and “Full Cycle Equivalent” during a selected time period.

The plot above shows that the owner has made several charging cycles at various levels from 10% up to 100%. By using the Li-Ion cycle life table from Miao et.al, these charging events are converted and summed up to a “Full Cycle Equivalent” of 6.03 during the time period selected (May 2020). Since the battery is expected to have a life time of about 450 full cycles, it can be estimated that 1.3% of the battery life was used up during this particular month. If this owner charges the equivalent of 6 full cycles every month, this battery can be expected to last about 77 months, or 6.5 years – significantly less than the normal expected lifetime of a car. Hence, by using the developed app, an owner can monitor the battery lifetime consumption of the vehicle on a daily, weekly or monthly basis, without performing harmful 0-100% deep charges.

Currently, there is talk about new batteries which will be capable of “a million miles” and a much higher number of charging cycles. In the paper by Harlow et.al, “[A Wide Range of Testing Results on an Excellent Lithium-Ion Cell Chemistry to be used as Benchmarks for New Battery Technologies](https://iopscience.iop.org/article/10.1149/2.0981913jes)” (2019) batteries with NMC532 cathodes have been found capable of higher cycle life, of 5000 or more deep charges. However, it is currently being speculated that such batteries will be used in vehicles connected to the grid (V2G), which means that deep charges could potentially happen much more frequently, perhaps even on a daily basis (charge at night when power prices are low, and sell during the day when prices are high). In such scenarios it could be of even larger importance to record the charging cycles to document remaining lifetime and ensure as high a resale value of the vehicle as possible. If and when V2G becomes a reality, the Bismuth team will make available automated data to blockchain submission scripts to capture high-frequency charging events.

![](/images/2020-05-25-Tesla-Bismuth-Crystal-07.png)

With Bismuth’s Tesla app, PDF files can also be generated for selected dates to document, for example, total distance driven during a given period or the sum of charge energy (kWh) added. In the example above, the sum of charge energy added is found to be 131.13kWh, since there are only three actual charging events (58.49, 51.18 and 21.46 kWh) in the submitted data. Such reports could for example follow the car when sold, as an alternative to giving away the password for the asset id on the blockchain.

The remaining two screenshots below are only available in the local app, and not on the public website. The first screenshot shows the asset registration screen. Here, the Tesla credentials are entered (username and password) as well as a (strong) anonymizer password if the user does not want to expose the actual VIN number. When the asset id has been registered, it will be linked to the Bismuth wallet address by paying a small fee. Only data for this asset id submitted from this account will be visible on the public website and in the plotting and analytics section of the app. If the owner later wants to transfer the vehicle to another owner, it must first be unregistered on the chain which allows the new owner to register it. By using the same password as the previous owner the original data set for the vehicle can be continued by the new owner. If a different password is used, then the asset id will be different and a new data set will be started from scratch. The Tesla credentials (username and password) will always stay on the local computer, and are never exposed to any external websites or services.

By entering the Tesla credentials and the anonymizer password (if any), battery data is collected from the vehicle. Once the data has been collected, it can be submitted to the Bismuth blockchain by paying a small fee.

![](/images/2020-05-25-Tesla-Bismuth-Crystal-09.png)
Screen for fetching battery data using the Tesla API.

Bismuth crypto currency is required to pay for fees and can be purchased on one of the BIS [exchanges](/exchanges).

Help and support is given in our [Discord](https://discord.gg/4tB3pYJ) There is a dedicated channel named #batterylife.  
For those who are not able to run from the source code, updated binaries for Windows, Mac and Linux are available at our [Github Repository](https://github.com/bismuthfoundation/TornadoWallet).


## References

- [Current Li-Ion Battery Technologies in Electric Vehicles and Opportunities for Advancements](https://doi.org/10.3390/en12061074)
- [Benchmarks for New Battery Technologies](https://iopscience.iop.org/article/10.1149/2.0981913jes)
- [BIS Exchanges](/echanges)
- [Bismuth Discord](https://discord.gg/4tB3pYJ)

