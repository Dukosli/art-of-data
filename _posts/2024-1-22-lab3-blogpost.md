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
This data interested me because I can use it to find out how much power I use while active, as well has how much energy I waste while idling or closing my computer (without shutting it off). Since I never shut my computer down (foolishly), I can see what impacts this has had on the world by using the mtCO2e conversion from https://devblogs.microsoft.com/sustainable-software/measuring-your-application-power-and-carbon-impact-part-1/ and my data given in mJ.


Discuss your analysis of the dataset. Include details such as:
1. The variables you looked at

TimeStamp, ScreenOn, TotalEnergyConsumption

2. Distributions of variables (center and variability)
3. Relationships between variables
4. Visualizations of the dataset
5. Limitations of your analysis and the dataset
6. What conclusions can you draw about this dataset? What is your supporting evidence?
