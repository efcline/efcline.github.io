---
layout: page
title: Presentation Time!
categories: [general, class, assignments]
tags: [general, class, scripts, data, databases]
shortview: true
---

# Presentations and Final Thoughts

Hey, this was a cool presentation! We selected data visualization (which is a difficult word to say several
times in a row, FYI) so that we could talk about our love of beautiful maps and graphs and generally 
gush over how awesome everything looks when you put things together and tell a great story. In essence, we wanted to show:

* what data viz is
* how it has evolved over time
* highlight a few tools
* show a few good/bad examples
* talk about cool ideas for the future

Getting going was a bit rough. Neither Kelsey nor I had any experience with reveal.js, but it's a fairly
intuitive process. We're both pretty good with CSS and HTML/Markdown, so writing the actual presentation 
once we had done a bit of research wasn't very difficult. 

Honestly the only snafu we ran into was remembering to run `./build-presentation.sh` with our freshly edited
presentation file. Many a time we went to preview our changes, worried for a while because we couldn't see
anything different, then remembered it needed to be converted via Pandoc. Practice makes perfect, though,
and that quickly became one of our first troubleshooting tactics.

Recording the audio took some time, but we had fun with it and took turns writing and recording separate 
slides. 

All in all, we both contributed to research. Ellen did a little more of the coding, Kelsey did a little more
of the scripting (for our audio files). We both looked for cool images to include, and we did most of the work 
in collaborative mode (i.e. sitting together at a desk, figuring out what works best).

# Prettiness

Once the general structure of the presentation was done, we thought about adding in a few *fancy* ideas, such
as fragments. These are little animations that halt the progress of the presentation to load separate lines
at the click of a mouse. Fragments may be written like this:

> `<p class="fragment">`

...and are a lot of fun to play with! This animation, while great, didn't do so great things to the overall
flow and structure of the presentation - in fact, for a while it would run each fragment, finish, then bounce
the entire presentation back to the beginning slide! 

We were stumped until our professor pointed out that each slide was still showing an id that was uniform throughout
the whole presentation. Aha! A quick fix was adding numbers to make the section IDs unique. Our problem slide now looks like this:

> `<section id="my-slide4" class="slide level1" data-audio-src="audio-files/tools.ogg"></section>`

And hooray! It all works! You can watch our [presentation here](https://kelhammer.github.io/dynamicduo/#/).

# Conclusions

We thought about changing the overall look/layout of the presentation, but we both really liked the black and white color scheme
and decided to stick with that. Since our pictures are so colorful, we didn't want to detract or distract with new colors and
strange backgrounds.

This presentation was the culmination of all our skills. Scripts, HTML, pandoc, github and Cloud9...the only skill we learned
that we didn't use in this instance was databases (MySQL). It was fun to practice all the things we learned.

Also when we were finishing up the final product, a few of our fellow SILS students took a 
look at what we had and were very impressed with our collective tech know-how! 

I feel very accomplished! 

<iframe src="//giphy.com/embed/nXxOjZrbnbRxS" width="480" height="648" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="http://giphy.com/gifs/win-nXxOjZrbnbRxS">via GIPHY</a></p>






