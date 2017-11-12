---
layout: post
title: Adding a Tactics Puzzle Mode - Part Two
category: T31LoSB
tags: [refactor, ui]
release: bedsui-Stable-20171111.zip
banner: /img/t31losb/the-thirty-one-lieutenants-of-sorcerer-bedsui.png
---

Continuing from last week's [post](/t31losb/2017/11/02/adding-tactics-puzzle-mode.html), the new tactics puzzle mode, while not finished, is playable!

![Tactics Mode]({{ "/img/t31losb/20171111/tactics-mode.png" | absolute_url }}){:class="img-fluid rounded"}

The puzzles aren't what I expected, but not in a bad way. Unlike traditional chess puzzles, where deviating from the correct line is strictly wrong and an automatic failure, my procedural puzzle generator produces more flexible puzzles with multiple solutions. One of the solution paths is usually shorter, and therefore 'better', but the player can recover from a minor mistake. The only comparable chess tactics puzzles I know of are the endgame puzzles on Chess Tempo, which punish you for being inefficient but won't outright fail you. Importantly though, the harder puzzles are genuinely challenging without being inaccessibly difficult.

![Hard Puzzle]({{ "/img/t31losb/20171111/hard-puzzle.png" | absolute_url }}){:class="img-fluid rounded"}

There's still work to do. I'd like a greater variety of puzzles for one. Currently all the puzzles use the same, empty 5 by 5 arena, so the puzzles only have so much room to be different. Hopefully, Procedurally generating the arenas as well as the piece layouts will solve that.

Generating the puzzles is also slow. Not prohibitively, but it does take fifteen seconds to create puzzles with three pieces. I don't think I can speed that up, but I can multi thred to generation to make the next puzzle while the player is solving the current one.

![The King Escapes]({{ "/img/t31losb/20171111/king-escape.png" | absolute_url }}){:class="img-fluid rounded"}

