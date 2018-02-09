---
layout: post
title: Dynamically Resizable Game Window
category: T31LoSB
tags: [refactor, ui]
banner: /img/t31losb/the-thirty-one-lieutenants-of-sorcerer-bedsui.png
---

This week I started an overhaul of the game's windowing code to allow dynamic resizing. Hopefully I'll fufill one of the [requests](https://www.reddit.com/r/roguelikedev/comments/7jxz0q/feedback_friday_30_the_thirty_one_lieutenants_of/drbeur5/) made in my reddit Feedback Friday. 

![Dynamically Resizable]({{ "/img/t31losb/20180208/dynamicSizing.gif" | absolute_url }}){:class="img-fluid rounded"}

So far, I finished the column and row resizing. I still need logic to add and remove rows and columns as well as update the font size, so that the dnamic resizing looks cleaner. 

This change was fun, as it involved digging through several year old code (the UI framework is a carry forward from a previous project). I'm really glad I took the time back then to write unit tests on all the visual and input processing code. Having a proper regression suite to validate the new changes made working with the old code a hundred times easier.


