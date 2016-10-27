--- 
layout: page
title: Assignment 3
categories: [general, class, assignments]
tags: [general, class, scripts, pandoc]
shortview: true 
---

# Pandoc, Scripts, and More!

In this post we will discuss assignment 3, trials and tribulations, and the like! 

> Scripts are fun!

...is the basic takeaway I have from this assignment. I wish I were more code-savvy and could have gotten my `if`/`then` to work, but I figure sometimes it's better to err on the side of caution. Here are the files I created with my script:

 * [gallica.md (source)](https://github.com/efcline/assignment-3-efcline/blob/5debcf7c302491b28bb0ba23982f5d45658a32cb/gallica.md)
 * [gallica.md.html](https://github.com/efcline/assignment-3-efcline/commit/ad7f9dbdb116696c02ebc5f47dffc1e7f84e72ca)
 * [gallica.md.docx](https://github.com/efcline/assignment-3-efcline/blob/6d1a2e00763c3a4fcf2589aa653e8d1779682057/gallica.md.odt)
 * [gallica.md.odt](https://github.com/efcline/assignment-3-efcline/blob/5debcf7c302491b28bb0ba23982f5d45658a32cb/gallica.md.docx)
 * [gallica.md.pdf](https://github.com/efcline/assignment-3-efcline/blob/b2a2d5c22c106a70d86fcd89395c8e4c67b98062/gallica.md.pdf)

And here is the script I used to do so (plus a link to my workspace):
 * [efcline-convert-docs.sh](https://github.com/efcline/assignment-3-efcline/blob/bf1406d3546526eb6e4bdcb83f5994ce4ec2defb/efcline-convert-docs.sh)
 * [Cloud9 Editor for efcline](https://ide.c9.io/efcline/assignment3)

But wait! How did we get here? What are these files? What does it all mean?

Pandoc is the ultimate document converter. Instead of the dropdown bar when you go to save a text document you've been working on, 
pandoc can take one file and do many things with it. Special features are added on using flags like `-S` or `--smart` (for fancy, curly quotes instead of boring straight ones).
Others are more simplistic, like the `-o` which designates output, or the `-f` and `-t` which work like arrows for "from" and "to."

I selected a document I put together for another INLS class, one in which we are building LibGuides for subjects or courses we either took in the past or had some interest in. 
In this case, I picked a course I enjoyed in undergrad (one of UNC's French Lit classes). Gallica.md is a quick write-up we did, assessing one of the resources we had chosen that
we found useful for research or general knowledge required for our classes. I looked at Gallica, which is a French database.

Essentially, I grabbed the word document I had submitted for class and threw everything in NotePad, where I worked to format it using the Markdown skills we learned earlier.
Once I had my markdown file (gallica.md), I was ready to write my script!

Scripts are fun because you get to write a little bit of code for the computer but you can also ask for interactions with users. My script `efcline-convert-docs.sh`
ended up being pretty basic, but at least it works! I used (probably overused) the commands `echo` `read` and `read -p` which echoes out a line of text but also waits for prompting from the user.
With a little work, I soon had four similar but important commands. Here is the html conversion:

* `pandoc -o $FILE.html $FILE` Here `FILE` is a variable, whatever markdown file the user decides (at the beginning of the script) they would like to convert.

After that it was quick work! There are a few breaks wherein the person running the script is prompted for input, mosting in the form of "What's your name?" or "Should we continue?"

The only troubles I encountered were either me tripping over my own feet or figuring out how to ensure the logo image displayed properly in each file format.
Tripping over my own feet in scripts included: 

* typos
* not working in the correct directory
* trying advanced things and neglecting to fully erase all of the malfunctioning bits from the script before trying to run it again

In essence, mistakes that really aren't that hard to avoid, and one would honestly think I knew better. 

Making sure images displayed corectly instead of making my Cloud9 workspace spit out unhappy messages about files not found turned out to have an easy fix: put the image in the working tree with all the other scripts and files we're working with!
And how did I come by this valuable piece of information? By talking to my peers, who turned out to be having similar issues. Teamwork ftw!