---
layout: post
title: Re-Balancing Bolt Attacks
category: T31LoSB
tags: [refactor, ui]
banner: /img/t31losb/the-thirty-one-lieutenants-of-sorcerer-bedsui.png
release: bedsui-Stable-20180223.zip
---

This week I spent most of my development time just playing and enjoying my game, but I did get around to re-balancing Long Bows and Spells, the two bolt based attacks in the game. Having spent most of this year so far working out user interface issues, this is the first update this year to make changes to the actual game mechanics.

*Long Bows*

Long Bows count as physical weapons and impede piece movement. The attack range for a unit with a Long Bow is similar to the Bishop in chess, long diagonals radiating out from the unit. When I first coded up Long Bows, the attack range was exactly that of the Bishop, but shortly after I made Long Bows incapable of firing at close range. Otherwise they were too powerful in comparison to the other weapons:

![Current Bows]({{ "/img/t31losb/20180223/currentBows.png" | absolute_url }}){:class="img-fluid rounded"}

Now Long Bows have the reverse problem. After I shrunk the size of the battle field, the long reach of the Long Bow became significantly less useful and the weapon became weak. For this release I'm trying a new compromise threat range:

![Buffed Bows]({{ "/img/t31losb/20180223/buffedBows.png" | absolute_url }}){:class="img-fluid rounded"}

*Spells*

Spell attacks are overpowered. In he hands of the player this isn't an issue. A fair fight would cause too many casualties to the player's team, and they would never advance through successive battles. When used by the computer units though, the attack radius of the spell produces a no-go zone around a unit that makes the unit too difficult to safely approach and attack: 

![Current Spells]({{ "/img/t31losb/20180223/currentSpells.png" | absolute_url }}){:class="img-fluid rounded"}

Around mid game the enemy Lieutenants have reliable access to spells, and the game has a problematic difficulty spike. So with the latest release I've nerfed spells. Now they function like Long Bows do, with a gap around the caster that is too close to hit with the spell. Attacking units now have a shot to to approach and maneuver around casters that will hopefully make fighting the computer controlled casters easier and more interesting.

![Nerfed Spells]({{ "/img/t31losb/20180223/nerfedspells.png" | absolute_url }}){:class="img-fluid rounded"}
