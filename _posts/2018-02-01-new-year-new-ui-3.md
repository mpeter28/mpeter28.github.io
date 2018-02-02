---
layout: post
title: New Year, New User Interface - Part Three
category: T31LoSB
tags: [refactor, ui]
banner: /img/t31losb/the-thirty-one-lieutenants-of-sorcerer-bedsui.png
release: bedsui-Stable-20180201.zip
---

It took a solid month of coding, but the new mouse based interface is in a playable state (check out the latest release!!), and I've ripped out the last of the old command line code. I know the [last](/t31losb/2018/01/19/new-year-new-ui.html) [two](/t31losb/2018/01/25/new-year-new-ui-2.html) updates were minimal, so for this update I'm going to take more time to show off the new features and explan the thing behind the changes I made.

**New Framework**

Each time I've overhauled the game's interface (this is the third time), I first made a new interface framework before doing any of the actual interface work itself. The framework provides constraints which help with interface consitency, and the framework also provides a good architectural foundation to help the code quality.

Normally with these frameworks, the interface doesn't directly affect anything in the underlying game state. There is a list of commands, and the interface allows user to request one of those commands, but the command class itself (an not any interface code) makes the requested change to the game state. With the command line inteface, the arrangement was very basic; each available command had a name, and the user was just typing out the name of which ever command they wanted.

To make the new mouse interface easier, I've designed a tree based model for describing commands.

![Example Command Tree]({{ "/img/t31losb/20180201/commandTree.png" | absolute_url }}){:class="text-centered img-fluid rounded"}

The start state for the user interface is the root node of the tree. Each node represents a piece of info for a command, and each complete path from root to leaf node is a complete command. The commands in the example tree are:

        kalor move a5
        kalor move a6
        kalor attack b3
        freja cast acid north
        freja cast acid west
        freja cast acid east
        freja move c8
        freja move d7

As the user interacts with the interface's current view, the user advances the interface through different nodes in the tree, and when a leaf node is reached that path formed from the root is the chosen command. At each node, the interface updates the view to show information relevant for choosing the next node.

The command tree is made pretty explicit at the bottom of the interface:

![Command Tree Navigation]({{ "/img/t31losb/20180201/commandTreeNavigation.png" | absolute_url }}){:class="text-centered img-fluid rounded"}

This widget can be used to directly move about the nodes of the command tree.

**The Combat Interface**

The new combat interface front-loads a lot more information.

![Annotated Combat Screen]({{ "/img/t31losb/20180201/annotatedCombatScreen.png" | absolute_url }}){:class="text-centered img-fluid rounded"}

Circled in red are important things the player needs to know but otherwise might overlook without a reminder. In this case one of the player's units, Good Boy, is within the range of enemy attack.

Circled in light blue is the log, which now records more than one event at a time and records less important events such as enemy piece movement (which the command line interface did not alert the player to). Nothing exciting about the log, it's the norm for roguelikes.

Circled in green is the new unit directory. My hope is that this will serve as a heads up display, letting the player know the defense stats (circled in purple) and melee attacks of every unit at a glance.

![Mouse Responsive]({{ "/img/t31losb/20180119/mouseOver.gif" | absolute_url }}){:class="img-fluid rounded"}

And as seen in a previous update, the battle map is mouse responsive and is the primary way I intend the user to select combat commands.

**The Battle Preperation Interface**

![Annotated Battle Preperation Screen]({{ "/img/t31losb/20180201/annotatedBattlePrepScreen.png" | absolute_url }}){:class="text-centered img-fluid rounded"}

The screen shot didn't capture the mouse, but the items in the inventory list are mouse selectable. Circled in green is an item being hovered over. Clicking the item would equip it to Cedarwood. Circled in purple is a preview of the stat changes equipping a shield to Cedarwood would cause.

Like the combat interface, the battle preperation interface also has alerts (circled in red). These alerts tell the player whenever a party member has a free equipment slot which an inventory item could fill. If there are no alerts, the player knows they've equipped everything they could have equipped.

**The Tactics Solution Review Interface**

![Review Solution Screen]({{ "/img/t31losb/20180201/reviewSolution.png" | absolute_url }}){:class="text-centered img-fluid rounded"}
