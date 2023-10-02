---
layout: post
title: 1.4 Lab 1 Blog Post
subtitle: Experience with first lab assignment by Aydan
cover-img: /assets/img/img-academy-0Kqhnq.jpg
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/path.jpg
tags: [books, test]
---
People have been wondering what Digimon is. So here are some quick FaQs to be answered:
1. What is the average speed (Spd) of all Digimon?

It is 120.4 in obscure units.

2. Write a function that can count the number of Digimon with a specific attribute. For example, count_digimon("Type", "Vaccine") would return 70.

As Digimon are probably very digital beings, coding questions are quite common. Here is a bit of code to help with this:
~~~
def count_stat(type, stat):
    with open("datasets/digimon.csv", "r") as f:
        reader = csv.DictReader(f)

        count = 0

        for row in reader:
            if row[type] == stat:
                count += 1

    f.close()
    return count
~~~

3. The Digimon on your team are restricted by the total amount of Memory that they need. If your team only has 15 Memory, name a team of up to 3 Digimon that has at least 300 attack (Atk) in total.

'Agumon', 'Goblimon', and 'Patamon' would satisfy this condition.

4. Describe your process in finding these answers. Include details such as who you worked with, what methods you tried, what worked or didn’t work, what could have gone better, and what you learned during this lab. Feel free to attach images, screenshots, pseudocode, etc to elaborate on your response!

I worked alone. The final code is more or less the first draft with some cleaning up and revisions. Apart from the choosing a Digimon team function, the coding was without problems. However, I encountered some problems. After finishing the first version, the first errors to be caught were sloppy ones, such as putting a check to break a loop after it should have been broken, or calling for elements from empty dictionaries. For example, this would break:

~~~
second = determine(savePre)
del savePre[second[0]]
if len(savePre) == 0:
    break
~~~

However, this would be fine:

~~~
if len(savePre) == 0:
    break
second = determine(savePre)
del savePre[second[0]]
~~~

However, there was one larger problem that stemmed from my misunderstanding of Python. The problem was that whenever I removed an element from one dictionary, it would remove it from another. I realized much later that it was because you can't create a new dictionary by setting it equal to the old one like this:

~~~
savePre = dictPre
~~~

Rather, you would have to do something like this:

~~~
savePre = {}
for i in dictPre:
    savePre[i] = dictPre[i]
~~~

This little bit stumped me for a while. I had been running through the debugger for almost 30 minutes before googling "how to copy dictionaries" and getting the response, "You have to iterate through them." In the end, I learned during this lab that Python does not make it easy for you to see problems in the code. I also learned that I should have started working on it earlier so that I could have more time to shorten the repetitive code bits some more. It certainly would have been better if I had sectioned off more quality time to work on this. I don't even know what I'm doing anymore.
