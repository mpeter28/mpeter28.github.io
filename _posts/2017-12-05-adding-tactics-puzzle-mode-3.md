---
layout: post
title: Adding a Tactics Puzzle Mode - Part Three
category: T31LoSB
tags: [refactor, ui]
release: bedsui-Stable-20171205.zip
banner: /img/t31losb/the-thirty-one-lieutenants-of-sorcerer-bedsui.png
---

This week I sunk some time into further finishing and polishing the tactics puzzle mode. It's more performant, has a big new feature, and has more varied puzzles.

Performance wise, puzzles still take roughly fifteen seconds to generate, but I've implemented a multi threaded Consumer/Producer pattern to get around this. While the player is solving one puzzle, a background thread generates new puzzles and enqueues the new puzzles into a thread safe queue. When the player needs a new puzzle, the main game thread pops one of the pre-made puzzles off the queue. From the player's perspective, new puzzles are generated instantly.

![Solution]({{ "/img/t31losb/20171205/solution.png" | absolute_url }}){:class="img-fluid rounded"}

The new feature is a puzzle solution screen. Previously, when the player failed a puzzle the game would just move onto the next puzzle with no explanation of why the player's moves were wrong or what the correct solution was. I still haven't done anything about the first issue, but now the game will explain the optimal solution. The player can step through the moves of the solution, seeing the board for every move.

![Complex Problem]({{ "/img/t31losb/20171205/complexproblem.png" | absolute_url }}){:class="img-fluid rounded"}

I've added procedurally generated walls to the two-on-one puzzles. More kinds of tactics emerge now.


