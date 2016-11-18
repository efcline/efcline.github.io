---
layout: page
title: Assignment 5 Reflection
categories: [general, class, assignments]
tags: [general, class, scripts, data, databases]
shortview: true
---

# Assignment 5 Reflection

Writing and running a script was easy, but the next step (adding it all into MySQL as its own database) turned out to be difficult. 
While I understood the concepts behind it all, actually getting MySQL to behave turned into quite the endeavor. 

If you'd like to follow along with the aid of our GitHub repo, please [find it here](https://github.com/sarecht/octocat2).

My group started with the initial script, `octocat.sh` and tried to add the data in the file our script appended to (`data.csv`) to a 
newly created database, also named after our friendly GitHub mascot.
Even creating a table in MySQL was hard! I did most of the typing, and made several typos in many 
subsequent attempts. Eventually, we ended up with an octocat database, with columns for Name, Age, Class Standing, Favorite Animal,
Favorite Color, Timestamp, and Unique ID. 

MySQL is a system that you can easily switch into with a simple `mysql-ctl cli` in any Cloud 9 workspace,
but how to get it to switch between bash and mysql within a bash script? At first we tried to write all this 
into our script, telling it to go to MySQL, use a certain database, add to a certain database, show all
work, but that quickly crashed and burned. A quick perusal of Stack Exchange gave us the following:

> `mysql -u -p -e "instructions" `

But while that worked fine in our workspace we couldn't make it play nice with our script! Eventually
we settled on asking the script runner their username and making it into a `$user` variable, then 
adding:

> `mysql -u $user -p -e "instructions" `

At this point our next step was to ensure that each group member could see and edit the table 
via a `mysqldump`. I feel like a whiner, but compared to the super-friendly GitHub/Cloud 9 duo, MySQL is
not very good for collaboration. In order to dump it all to a .sql file via dump and export, you then have
to import into another user's profile. This is a little like `git push` / `git pull` which is pretty easy
but each importer had to already have an empty table in their workspace waiting in order for the `mysql -u -p octocat < octocat.sql` 
to work. This caused a lot of initial heartache, then a lot of excited yelling when we finally figured it out.

As soon as each user was able to have the imcomplete assignment in their own workspace, we set out to try
and get the script to add all data into the octocat database. Looking back, it's hilarious how many
obstacles we ran into and how messed up our database got before we fixed it, but it did cause some initial
panic. Let's see...first we tried to just import all data in the .csv file to octocat with a little

> `mysql -u -p -e "load data infile '/home/ubuntu/workspace/octocat2/octocat/data.csv' into table octocat;`

But we quickly realized that this created duplicate lines of data within octocat - not very useful or very
professional. Then removing those duplicate lines became a chore. I settled on deleting things line by (duplicate) line, but
Sarah found a great `TRUNCATE` command that cleared the whole thing. I'm always a little fearful when erasing
things - what if it messes up and we can't fix it? - but this one was perfect. 

At the same time, we were still wrestling with our script and getting it all to add properly to octocat. 
I wanted to use the `INSERT` command, but that proved too difficult, so we switched to attempting the `IGNORE`
line. I think our problem here was that we weren't entirely sure what it meant to `ESCAPE` a line or character
and that limited our understanding of using the various escape keys we found on Stack Exchange and at W3
Schools. We tried what seemed like a great couple of lines we found online, one with a `/n` key, but 
that really made things crazy - adding data hereafter added in the first (another duplicate) line of data
but stopped halfway through the second line and boxes were left empty/NULL and the whole table was totally
skewed! Luckily at that point we had the "clear *all* the stuff" command pretty well under control. I think
we had to delete everything at least 4 times? I didn't keep a tally, but it seemed like it.

After lots of searching and asking our professor, we arrived at:

> `mysql -D octocat -u $user -e "LOAD DATA INFILE '/home/ubuntu/workspace/octocat2/octocat/data.csv' IGNORE INTO TABLE octocat FIELDS TERMINATED BY ','(Name, Age, Class, Animal, Color, Date, ID);"`

And hey! It works!

# Running our script

If you like, you may run our script on your own machine! However, you will need to do the following:

* create an empty database named octocat in your workspace
* import our existing data with `mysql -u yourUsername -p octocat < octocat.sql

And you should be able to see everything!

