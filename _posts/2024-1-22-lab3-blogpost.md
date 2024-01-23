---
layout: post
title: What Your Battery Usage Tells You About You
subtitle: Using CO2 Emission Equivalents
cover-img: /assets/img/upgrading-laptop-battery-calibrating-charging-pcexpertservice.jpg
thumbnail-img: /assets/img/hero-image.fill.size_994x559.v1678673307.jpg
share-img: /assets/img/hero-image.fill.size_994x559.v1678673307.jpg
tags: [books, test]
---

In this lab, I used the System Resource Usage Monitor Utility command on my Windows computer to generate a "battery report," which lists rudimentary data on energy usage per source of usage for each running program over time. On windows, it is easy to acquire this data. Simply use the following command to generate the csv on the file path PATH:
~~~
powerpowercfg /srumutil /output PATH\srumutil.csv
~~~
This data interested me because I can use it to find out how much power I use while active, as well has how much energy I waste while idling or closing my computer (without shutting it off). Since I never shut my computer down (foolishly), I can see what impacts this has had on the world by using the mtCO2e conversion from [Measuring Your Application Power and Carbon Impact Part 1](https://devblogs.microsoft.com/sustainable-software/measuring-your-application-power-and-carbon-impact-part-1/) and my data given in mJ. Of course, this needs a point to it. 

I want to determine whether or not I should shut my computer down when I do not use it for long periods, determined purely from an environmental standpoint. Sure, it is a drag, but this data can tell me whether or not it is worth it using the mtCO2e conversion. 

In the lab, I primarily focused on the variables TimeStamp, the time at which the data was recorded, ScreenOn, whether the screen was on when data was collected, and TotalEnergyConsumption, the total energy consumed over a period given in mJ.



2. Distributions of variables (center and variability)
3. Relationships between variables

Unsurprisingly, there was a positive correlation between ScreenOn and TotalEnergyConsumption, considering the boolean as an integer binary. Surprisingly, the power average power usage of my computer while it was off was not much lower than the average when it was on, which is interesting. 

4. Visualizations of the dataset

![Data Visualization](https://github.com/Dukosli/art-of-data/blob/master/assets/img/8980ea8e-6da2-4548-b226-d9e32fab928a.png)

5. Limitations of your analysis and the dataset

Of course, the dataset is not perfect. According to devblog above, "the data provided are estimates and don’t necessarily reflect the energy at the wall (key things missing will be loss from the AC adapter, fans, discreet GPU utilization and a few other items)." This means that the data collected was an underestimation of the true total energy consumed. 

6. What conclusions can you draw about this dataset? What is your supporting evidence?
