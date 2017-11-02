---
layout: post
title: Improving the Command Line - Better Visual Feedback
category: T31LoSB
tags: [command-line, ui]
release: bedsui-Alpha-20171021.zip
banner: /img/t31losb/the-thirty-one-lieutenants-of-sorcerer-bedsui.png
---

The command line auto complete has an issue. For reference on the right is what a user typed, and on the left is what the game thinks the user means.

![Old Command Line]({{ "/img/t31losb/20171021/old-style-command-line.png" | absolute_url }}){:class="img-fluid rounded"}

Unless one is paying close attention, one might not notice the game interpreting small typos wrong (or against what one would expect anyway). This week I tried to improve the visual feedback and make it clearer what command the user is actually about to run, adding new color distinction to the auto complete.

![New Command Line]({{ "/img/t31losb/20171021/command-line-feedback.gif" | absolute_url }}){:class="img-fluid rounded"}

What the user actually typed is highlighted in bright blue, and what the auto complete infers is tacked on in dark teal. If no command can exactly match what the user typed, the auto complete will show its best guess in yellow. Likewise, perfect matches are shown in green.
