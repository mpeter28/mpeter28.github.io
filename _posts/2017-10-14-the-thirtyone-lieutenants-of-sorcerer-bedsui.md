---
layout: post
title: Project Launch - The Thirty One Lieutenants of Sorcerer Bedsui
category: T31LoSB
tags: [overview, vision]
release: bedsui-Alpha-20171014.zip
banner: /img/t31losb/the-thirty-one-lieutenants-of-sorcerer-bedsui.png
---

*Chaos blankets the world. From his tower in the southern marches, the illusionist Bedsui manipulates the minds of many great Kings and Emperors, sowing war and discord. But soon the madness ends! Steeling their resolve, a band of adventurers prepares to storm the tower and defeat the sorcerer. However, between them and their goal await Bedsui's many servants...*

After a year of working on my game in private, the perfectionist in me has finally decided I have enough completed to share. *The Thirty One Lieutenants of Sorcerer Bedsui* is a Java roguelike, created as a prototype to show off novel, squad-based combat mechanics. Currently in a fully playable state. I am hoping to incorporate feedback into a more ambitious game in the future.

![Title Screen]({{ "/img/t31losb/20171014/titlescreen.png" | absolute_url }}){:class="img-fluid rounded"}

![Roster View]({{ "/img/t31losb/20171014/roster.png" | absolute_url }}){:class="img-fluid rounded"}

![Challenge Screen]({{ "/img/t31losb/20171014/challengescreen.png" | absolute_url }}){:class="img-fluid rounded"}

'The Thirty One Lieutenants of Sorcerer Bedsui' is a turn based, squad combat roguelike with many of the boilerplate roguelike elements (fantasy setting, ASCII graphics, kill monsters and collect loot...). What distinguishes T31LoSB is the combat system, which dispenses with the usual 'one space per turn movement' and 'melee attacks are all to adjacent squares'. I am hoping to incorporate feedback on the combat mechanics into a more ambitious game in the future.

All combatants, monsters and player characters, move about the board like tafl pieces (or the rook from chess), only stopping when blocked by a wall, unit, or wandering into an enemy's melee range. In most roguelikes, the melee range for units are the eight immediately adjacent squares. In T31LoSB different weapons provide different melee ranges specific to the weapon type.

Units, player and monster, are fragile. Any attack which rolls higher than a unit's relevant defense stat is fatal. My intent is the create combat that focuses on maneuvering and coordinating a squad of various weapon types, and where trapping enemy units is the primary challenge of killing them instead of relying on more hit points and stronger attacks.

Instead of key bindings, T31LoSB uses an in built command line for all player input; it's typo tolerant and has predictive text features!

![Combat View]({{ "/img/t31losb/20171014/combat.png" | absolute_url }}){:class="img-fluid rounded"}

![Equip Sword]({{ "/img/t31losb/20171014/equipsword.png" | absolute_url }}){:class="img-fluid rounded"}

![Lightning Spell]({{ "/img/t31losb/20171014/balllightning.png" | absolute_url }}){:class="img-fluid rounded"}
