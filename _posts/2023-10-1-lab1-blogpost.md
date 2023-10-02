---
layout: post
title: 1.4 Lab 1 Blog Post
subtitle: Experience with first lab assignment by Aydan
cover-img: /assets/img/img-academy-0Kqhnq.jpg
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/path.jpg
tags: [books, test]
---
People have been wondering what Digimon are. So here are some quick FaQ's to be answered:
1. What is the average speed (Spd) of all Digimon?
It is 120.4 in obscure units.
2. Write a function that can count the number of Digimon with a specific attribute. For example, count_digimon("Type", "Vaccine") would return 70.

```python
def count_stat(type, stat):
    with open("datasets/digimon.csv", "r") as f:
        reader = csv.DictReader(f)

        count = 0

        for row in reader:
            if row[type] == stat:
                count += 1

    f.close()
    return count
```

4. The Digimon on your team are restricted by the total amount of Memory that they need. If your team only has 15 Memory, name a team of up to 3 Digimon that has at least 300 attack (Atk) in total.
5. Describe your process in finding these answers. Include details such as who you worked with, what methods you tried, what worked or didn’t work, what could have gone better, and what you learned during this lab. Feel free to attach images, screenshots, pseudocode, etc to elaborate on your response!
