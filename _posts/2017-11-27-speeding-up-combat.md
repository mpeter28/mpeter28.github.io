---
layout: post
title: Speeding Up Combat
category: T31LoSB
tags: [refactor, ui]
release: bedsui-Stable-20171127.zip
banner: /img/t31losb/the-thirty-one-lieutenants-of-sorcerer-bedsui.png
---

This week's update builds off [lasts week's efforts](/t31losb/2017/11/24/map-generation-character-balance.html) to improve the core game play. Last week was about balance, this week is about pacing.

With the holiday (American Thanksgiving was Thursday), I finally got a chance to see my brother and have him play test T31LoSB. He's seen previous prototypes of the Tafl/Chess combat system, but never played this incarnation, and he focused on the sluggishness of the actual battles.

First was how long commands take to type out. Take the following two commands:

    move range <row column>
    threat range <row column>

The crucial piece of info the predictive text matcher needs to guess the command is all the way at the end. The player has to type out "move range" and "threat range" every time. Compare the alternative:

    <row column> move range
    <row column> threat range

With the commands structured to have <row column> first, the predictive text matcher can uniquely identify the command as soon as the 'm' in "move range" or 't' in "threat range" is typed. Much less annoying. At some point in the future I'm planning to go over every command and make sure the crucial info is front loaded to optimize typing speed. For now I just fixed the more obviously annoying commands, such as the example two.

The next issue was how many turns are needed to win a battle. There's too much time spent on initial piece deployment; openings last longer than in chess, despite each side having half as many pieces. Chess is played on a tiny board, 8 by 8, compared to battlefields in T31LoSB, 15 by 30. The bigger playing field slows down everything with the extra moves wasted just covering the distance, so I tried cutting down the board to 9 by 18. 

![Smaller Board]({{ "/img/t31losb/20171127/smaller-board.png" | absolute_url }}){:class="img-fluid rounded"}

It's quite a size reduction, having less than one half the squares the old, larger board had, and it feels faster (at least to me).

The smaller board has had other useful effects too. The computer AI has an annoying tendency to leave its lieutenant unguarded, making for easy, boring wins. On a smaller board the computer's pieces are naturally clustered close, so it's more likely a piece will be near by to protect the lieutenant. The AI hasn't changed, but it plays stronger.

The density of pieces, both the player's and the computer's, also increases how often tactical combinations arise; closer pieces mean more possibilities and more interesting positions.
