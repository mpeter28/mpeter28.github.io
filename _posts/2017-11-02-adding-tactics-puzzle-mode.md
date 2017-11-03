---
layout: post
title: Adding a Tactics Puzzle Mode
category: T31LoSB
tags: [tutorial]
banner: /img/t31losb/the-thirty-one-lieutenants-of-sorcerer-bedsui.png
---

Good games need good tutorials, and a good tutorial should feel like a natural extension of the game, teaching the player without them realising they're even playing the tutorial. Given the steep learning curve of the average roguelike (especially the Ascii variety), 'The Thirty One Lieutenants of Sorcerer Bedsui' especially needs a good tutorial.

If you've ever studied chess seriously, you're probably familiar with the concept of a tactics puzzle. In a tactics puzzle, the student is presented with a board position and has to choose the best move to play, usually with the objective of winning a large piece advantage or checkmating the opposing King in 'X' number of moves.

Take for example the below puzzle, white to play:

![Classic Chess Puzzle taken from 'Saavedra v Fernando 1895']({{ "/img/t31losb/20171102/promote-to-rook.png" | absolute_url }}){:class="img-fluid rounded"}

Do you see the answer? White will win by advancing the 'c' file pawn, but the trick is to promote to a rook instead of a queen when the oportunity arises.

I enjoy chess tactics puzzles. They're fun in their own right, and they're one of the best ways to improve quickly. More importantly, T31LoSB draws heavy inspiration from chess. If tactics puzzles can teach people chess, tactics puzzles can teach people to play T31LoSB as well.

Can I make tactics puzzles for my game? Yes. Imagine the following toy situation:

![Ladder Start]({{ "/img/t31losb/20171102/ladder-start.png" | absolute_url }}){:class="img-fluid rounded mx-auto"}

The spider (blue 'S') attacks in eight directions with its many legs as if it were a knight. The human (green '@') has a more limited attack range. The human can flee to the south or to the east, but attempting to go north or west results in swift death in the spider's attack range. Eventualy the human will end up in the corner, and as there is no passing your turn, is forced to step into danger, dying to the spider.

![Ladder End]({{ "/img/t31losb/20171102/ladder-end.png" | absolute_url }}){:class="img-fluid rounded mx-auto"}

Alternatively, if the human starts out adjacent to the spider, the spider is unable to escape. Fleeing to the west will run it into a wall and death.

![Human Wins]({{ "/img/t31losb/20171102/human-wins.png" | absolute_url }}){:class="img-fluid rounded mx-auto"}

Why one side is destined to lose each time isnt't immediately obvious. Working through how these positions play out is a learning experience, an experience that's easy to make a puzzle (and thus a tutorial mini game!) out of.

Generating the puzzles makes use of the same [algorithms](https://en.wikipedia.org/wiki/Retrograde_analysis) which produce [chess end game tables](https://en.wikipedia.org/wiki/Endgame_tablebase). Once generated, the player will attempt one problem after another, with the game grading them on their move choices. As they get problems right, they get harder puzzles, and likewise easier puzzles as they get problems wrong.

So far, I've completed the position 'solver' needed to generate the puzzles and grade player solutions. Still in the works is a user interface to play it all through.




