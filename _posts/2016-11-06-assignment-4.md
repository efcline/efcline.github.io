---
layout: page
title: Assignment 4
categories: [general, class, assignments]
tags: [general, class, scripts, data]
shortview: true
---

# Data Creation

In this assignment my group (Sarah, Sanjana, and myself) worked together to
make a script with specific questions, then take the answers and add them to an ever-growing .csv file.

We named our script `octocat` in honor of Github's icon and mascot. Writing out our questions and having the script store the responses was the easy
part, then with a little manoevering and help from our professor the datestamp and unique identifiers were added as well. 

Sanjana made a really good point when we were writing our questions - I thought all variable names had to be all caps, but as long as you name 
them and use the `$` or just backticks (``) around the defined name, you may write a variable however you like.

With a little help from the ever-useful Stack Exchange, I figured out how to make a unique identifier. 
Defining the `ID` variable in the beginning of the script and then calling it out to append to the .csv file at the end worked very well. 
The same was true of the datestamp, and then when all the questions are answered the script does one last thing...

> `echo "$answers" >> data.csv`

And you can see all the answers in our file! Here is a link to our [github repository](https://github.com/sarecht/octocat). 

# Resolving Issues

I think the biggest issue here was just communication. Figuring out how/when to push to github or pull became very tricky very quickly.
Luckily, we did the majority of our work together in class, and were able to determine who was doing what when. So, when one person
was working on the script the other two would offer advice and troubleshoot, and then pull the completed files one at a time. This meant
that we didn't have any problems with branches or merge conflicts, because we collaborated together on our master branch. 