---
layout: post
title: The Proof of Concept
category: "Schroedinger-Chess"
banner: /img/schroedingerchess/project-image.png
---

This is the third in a [series](schroedinger-chess/2017/11/28/introduction-to-haft-schroedinger-chess.html) of [posts](schroedinger-chess/2017/11/29/as-a-csp-problem.html) detailing *Haft Schroedinger Chess*. In this post I briefly review the [Proof of Concept Github](https://github.com/mpeter28/HaftSchroedingerChess) project which demonstrates key concepts discussed in the other two articles.

![Proof of Concept]({{ "/img/schroedingerchess/20171130/prototype.png" | absolute_url }}){:class="img-fluid rounded"}

The Proof of Concept:

1. Is written in Java
2. Builds using Maven
3. Does not have any AI, rather it showcases a constraint satisfaction problem solver that can determine move legality
4. Does not have check
5. Is missing many 'edge' case rules from chess like enpassant and piece promotion
6. Does not have an optimized CSP solver; the revelation about domain retricting came after it was written, and I never got around to updating it

Go have a look!

