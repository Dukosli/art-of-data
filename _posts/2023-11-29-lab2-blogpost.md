---
layout: post
title: Animal Crossing Socks and APIs
subtitle: The Journey of 🧦
cover-img: /assets/img/image.avif
thumbnail-img: /assets/img/GUEST_50df8e55-aeac-4e60-85e7-5fe5208e9a5c.jpg
share-img: /assets/img/path.jpg
tags: [books, test]
---

1. Discuss how you used the API to obtain the dataset.

### Analysis Results

Now for the analysis of the socks in Animal Crossing. Using the program using the Animal Crossing API, I found that the following socks had the most variations of color. The highest count of variations was eight socks, and the following socks had that many variations:


argyle crew socks<br>
color-blocked socks<br>
frilly knee-high socks<br>
holey tights<br>
kiddie socks<br>
mixed-tweed socks<br>
no-show socks<br>
semi-opaque socks<br>
semi-opaque tights<br>
sequin leggings<br>
simple-accent socks<br>
striped socks<br>
striped tights<br>
tube socks<br>
ultra no-show socks<br>
vivid leggings<br>
vivid socks<br>
vivid tights<be>


For a similar analysis of the variations, my program also counted how many colors and how many of them existed in all the socks. Since every sock had two colors, the socks with the same first and second colors only had that color counted once. Here are the numbers of each color:


Pink: 44<br>
Red: 43<br>
Aqua: 33<br>
Orange: 28<br>
Purple: 39<br>
Green: 51<br>
Blue: 48<br>
Yellow: 34<br>
White: 89<br>
Black: 65<br>
Beige: 16<br>
Gray: 33<br>
Brown: 11<br>
Colorful: 14<be>


### Code Discussion


The program got this data by first creating a few dictionaries and lists to store the analysis data. Then, it ran a while loop that would check every index from the responses from the API until the API could not give another response. For each iteration in the loop, the response from the API would get saved into a variable called data, and the information would be taken from data and put into its respective dictionary or list. For the number of variations, this meant that it would count how many variations of each sock there were, while also counting whether or not that number of variations was greater than the greatest number of variations from the iteration before. For sock colors, it counted the number of socks of a color in a dictionary, and if the color were not already in the dictionary, it would be added. After the loop finished this process, the number of variations dictionary was iterated through to find how many socks had variations equal to the greatest counted number of variations. Finally, the data was printed, copied, and pasted here.



1. Discuss your process of how you worked on this lab. Include details such as who you worked with, what methods you tried, what worked or didn’t work, what could have gone better, and what you learned during this lab. Focus more on the programming side of the lab! Feel free to attach images, screenshots, pseudocode, etc to elaborate on your response.


