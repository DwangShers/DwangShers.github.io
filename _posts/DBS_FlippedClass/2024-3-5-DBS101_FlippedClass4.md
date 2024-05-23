---
Title: DBS101 Flipped Class 4
categories: [DBS101, Flipped_Class4]
tags: [DBS101]
---

### Topic : Advanced Aggregation Functions
----

In our flipped class session four, we got to dive into Advanced Aggregation Functions. We formed groups, and I ended up in Group1 (G1), where we learned about Ranking. Other groups were Windowing (G2), Pivoting (G3), and Rollup/Cube (G4). Then, we got extra instructions for our group work. We had 10 minutes for instructions, 30 minutes for group chats, and 20 minutes to present to the class. I was in Group1, and we showed how Ranking works using a database. It was awesome to put our new knowledge into action and share it with everyone.

---
Our main goal was to learn how to use advanced aggregation functions and why they're important.Our tutor gave us lots of useful stuff to learn more about advanced aggregation functions.

We had websites like 
https://docs.data.world/documentation/sql/concepts/advanced/aggregate_functions.html

https://runestone.academy/ns/books/published/practical_db/PART1_SQL/11-advanced-topics/advanced-topics.html  

Plus, we were told to refer textbook called "Database Systems Fundamentals," especially Chapter 5, pages 219-231. All these helped us understand advanced aggregation functions better and how to use them properly.

---
From my group, we covered some important topics about ranking and understanding. 

First off all, we learned about "RANK." This function helps us figure out the rank of something in a group of items. It's like giving each item a place in line, starting from 1. But, if there are items with the same rank, there might be gaps in the numbering. There was even a example using baseball stats to see who hit the most home runs in a season. 

![alt text](</image/Screenshot from 2024-03-20 23-32-26.png>)

In this image, we can see that there is gap in numbering.

Then, we talked about "DENSE_RANK." This one is similar to "RANK," . It still gives items a rank, but it doesn't leave any gaps. So, if two items have the same rank, the next one will still be ranked correctly without any skipped numbers. We looked at another example using baseball stats to see who hit the most home runs without any gaps in the ranking.

![alt text](</image/Screenshot from 2024-03-20 23-35-44.png>)

Next up was "ROW_NUMBER."  It gives each row in a group a unique number, starting from 1. We saw an example where it helped us organize employees' names alphabetically by their regional office.

![alt text](</image/Screenshot from 2024-03-20 23-38-06.png>)

Lastly, we covered "PERCENT_RANK." This one calculates the percentage ranking of something in a group of items. It's like saying, "You're in the top 25%," or "You're at the bottom 10%." We checked an example with orders from different accounts to see how they stacked up against each other in terms of order value.

![alt text](</image/Pasted image.png>)

---
#### Windowing 
Second group presented on window functions, which are super useful for data analysis. They let us look at data in groups and also see each row's details. For example, I learned to list all books by an author, showing how many books they've written and their order by publication year. This was done using COUNT and ROW_NUMBER functions, which are part of window functions.

Window functions aren't just for adding up numbers. They also rank rows and compare them. This lets us do lots of different analyses, like calculating running totals or comparing individual rows to the whole group.

In short, window functions is like adding a super tool to my data analysis toolkit. They let me do advanced analyses and make informed decisions.

![alt text](</image/Screenshot from 2024-03-20 23-56-00.png>)

![alt text](</image/Screenshot from 2024-03-20 23-56-18.png>)

---
#### PIVOT
Third group presented on PIVOT. It is a tool for transforming data, like turning rows and columns in a data. 

Lets say, there is a table showing products and their sales in different offices. Each row lists a product's sales in a specific office. But what if you want to flip that around? Instead of rows for each product's sales in various offices, you want columns for each office showing the sales for each product. That's where PIVOT comes in.

![alt text](</image/Screenshot from 2024-03-21 00-11-52.png>)

![alt text](</image/Screenshot from 2024-03-21 00-12-03.png>)

---
#### ROLLUP and CUBE
Last topic was presentation by Group 4. ROLLUP and CUBE are like special tools that help us make sense of data in different ways. In simple,,

ROLLUP is like a super handy way to summarize data. Imagine having a bunch of deals in different regions, and to see the total sales for each region and each sales agent. ROLLUP does just that. It groups data by different levels, like region and sales agent, and gives the total sales for each group.

CUBE. It's like ROLLUP. While ROLLUP works in a hierarchy, CUBE is more about exploring all the possible combinations of your data. So, to see sales numbers for products and sales agents, CUBE will show all the different combinations. It's like looking at data from all angles to find interesting patterns.

But when using ROLLUP or CUBE, things can get a bit tricky if there are empty spaces in the data. That's where the GROUPING aggregation comes in handy. It helps us sort out those tricky spots and make sense of our data.