---
layout: post
title: Animal Crossing Socks and APIs
subtitle: The Journey of 🧦
cover-img: /assets/img/image.avif
thumbnail-img: /assets/img/GUEST_50df8e55-aeac-4e60-85e7-5fe5208e9a5c.jpg
share-img: /assets/img/path.jpg
tags: [books, test]
---
In this lab, we used APIs to obtain data about the socks in Animal Crossing.


## APIs? How that?

We requested responses from an API hosted on a server that stored the data we needed to complete this lab. Using the requests module in Python, we could get the data we needed from the API by requesting the data from a specific HTTP URL, "https://afeingoldhm.pythonanywhere.com/socks". The data was locked, so we needed to use a key in the request parameters for the API, as well as an index number to get a specific response from the API. Using the requests module, we could access the data stored at a specific URL using the access key so that the API could recognize the client, me, and use the index number to get information about a specific sock.


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


### Process


To start the lab, before writing anything, I decided to start writing the program to find the information we needed. I worked with Ellen towards both the beginning and end of the coding portion of the lab. At the start, we worked together to figure out how to get responses from the API, including how to format the payload to get the responses from the API we wanted. In the end, using the introduction to APIs assignment, it looked as it did below.


~~~
payload = {'key': API_KEY, 'idx': num}
response = requests.get(BASE_URL + ENDPOINT, params = payload)
~~~


I encountered some brief problems while trying to run the code, first because VsCode had some strange problems where the requests module did not exist (solved by running the file through terminal and Spyder), and second because the file with the code had the same name as another file (socks.py) which did a circular import of socks and requests (solved by renaming the file). The remainder of the time spent coding the first assignment of the lab went quickly and smoothly. The only trouble occurred with small spelling and formatting mistakes. I would sometimes ask Ellen for help to figure out what was wrong, and she would help me spot the errors. 


Then, I started working on the second assignment in the lab. Initially, I tried to get the data with two separate functions, but since I chose not to create a CSV to store the data from the API, I decided to make a single function so I would only have to request the data from the API once. After adding some new variables and a couple if statements, the program ran smoothly. However, after reviewing the data with Ellen, I realized the data for the second assignment was wrong. I had not read that there was double counting among sock colors and thus had failed to account for that. Initially, it looked like this.


~~~
if data["Color 1"] not in colors:
    colors[data["Color 1"]] = 1
else:
    colors[data["Color 1"]] += 1
if data["Color 2"] not in colors:
    colors[data["Color 2"]] = 1
else:
    colors[data["Color 2"]] += 1
~~~


The problem was that the else in the second if statement would add "Color 2," even if it was double counting "Color 1." The fix was simple but required many minutes of verbal reasoning with Ellen to fix it since we kept backtracking. Ironically, the first fix I made was right but I convinced myself it was wrong. In the end, it turned out to be right and the conditionals for the second assignment are as follows.


~~~
if data["Color 1"] not in colors:
    colors[data["Color 1"]] = 1
else:
    colors[data["Color 1"]] += 1
if data["Color 2"] not in colors:
    colors[data["Color 2"]] = 1
elif data["Color 1"] != data["Color 2"]:
    colors[data["Color 2"]] += 1
~~~


In the end, the entire coding bit went smoothly more or less, with great efficiency as well thanks to Ellen. I learned how to use APIs, which was really cool and something I'm pretty sure I'll use again in the future. I feel as though this lab also could not have gone better, apart from technical issues with software during testing. However, these issues have left me more prepared for the future as I also now know how to deal with these issues for the future.
