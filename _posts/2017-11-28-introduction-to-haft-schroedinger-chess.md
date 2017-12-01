---
layout: post
title: Introduction to Haft Schroedinger Chess
category: "Schroedinger-Chess"
banner: /img/schroedingerchess/project-image.png
---

*Haft Schroedinger Chess* is a chess variant with rules inspired by quantum mechanics. Like traditional chess, it is a combinatorial game, meaning it is both deterministic (no random chance at all) and has no hidden information. This post explains the rules and some of the resulting consequences to game play.

First, let me explain the game roughly as David explained the idea to me. Imagine a game of chess, but at the very start none of the back rank pieces have a fixed piece type. As players move the non-pawn back rank pieces, those pieces slowly acquire their piece type. This information isn't a hidden state being revealed by the moves; moving a piece in a long straight line *makes* that piece into a Queen or Rook. Moving that same piece again on a diagonal locks it into being a Queen.

Until all pieces have their piece type locked in, there is entanglement between the pieces based on piece identity. For example, each side in chess only has two rooks. In *Haft Schroedinger Chess*, a player can move three of their pieces like a Rook. Two of those pieces will eventually lock in as Rooks, but the third has to lock in as the Queen, the only other piece that can move in a long straight line like the Rook. Until the identities of all three pieces are firmly established, each is potentially the Queen and potentially a Rook and can behave like either. Establishing the identity of one piece, say by moving it on a diagonal, establishes the identities of the other two pieces due to the entanglement.

Lets imagine another entanglement scenario. A player has moved two of their pieces like a Rook, and two others like a Bishop. Any of those four pieces could potentially be the Queen. If one of the potential-Bishops moves like a Rook, then it is the Queen and the potential-Rooks are actual rooks. If one of the potential-Rooks moves like a Bishop, then it is likewise the Queen and the two potential-Bishops are actual Bishops. If a fifth unrelated piece made its first move like a Rook, then the two potential-Bishops would have to be actual Bishops, because the Queen would have to be one the three pieces that moved like a Rook.

So far these entanglements have been between pieces on the same side. Check adds entanglements between pieces of both sides, since the King can not be moved into or exposed to check. The entanglement takes the form of a conditional; if my piece on 'a6' is my King, then your piece on 'a5' can not be a Rook.

Any move which produces impossible entanglements is an illegal move. Four pieces on the same side can not all move like a Bishop, as only three pieces can do that. There always has to be a way to concretely fix each piece's piece type such that the correct number of pieces of each type is maintained.

These examples make for a good intuitive understanding of the game. Now let's define proper rules! To do this, I'm fist going to define a simpler game which the rules of *Haft Schroedinger Chess* will need to reference. This simpler game is *Scramble Chess*.

*Scramble Chess* has almost the same rules of traditional chess, except each player may place their major pieces on their back rank however they like before the game starts. These pieces aren't hidden; both sides know what all the pieces are, and after piece placement the game proceeds like traditional chess. The only other change is that there is no castling (for obvious reasons). We'll call any possible starting position the two players in *Scramble Chess* a valid Scramble Chess starting position. Any valid Scramble Chess starting position will have the same pieces as the starting position in traditional chess. Just the piece placement will differ. Here's one of the many valid Scramble Chess starting positions:

    RNBNBKQR
    pppppppp
    ........
    ........
    ........
    ........
    pppppppp
    KQRRBBNN

Now that we've defined the concept of a valid Scramble Chess starting position, we can give semi-formal rules for *Haft Schroedinger Chess*:

1. As in traditional chess, there are two players who play on alternating turns.
2. Also like traditional chess, the game is played on an eight by eight board.
3. Each player has a set of sixteen pieces they can move: eight pawns and eight major pieces.
4. At the outset, each player's sixteen pieces are arranged as in the following diagram. 
5. On their turn, a player may move any one of their pieces to wherever, so long as there exists at least one valid Scramble Chess starting position such that if the moves of the *Haft Schroedinger Chess* match were replayed as *Scramble Chess* moves on that valid Scramble Chess starting position they would all be legal *Scramble Chess* moves.
6. The game is over when every game of *Scramble Chess* with identical moves produces an ended *Scramble Chess* game.

Starting Position Diagram:

    MMMMMMMM
    pppppppp
    ........
    ........
    ........
    ........
    pppppppp
    MMMMMMMM

The fifth rule is heavy and implies a lot through its math-definition-esque wording. It's important though, as earlier I said any move which produces impossible entanglements is an illegal move. Rule five gives us a real, objective definition of what that means. An impossible entanglement is any position that no *Scramble Chess* game could ever reach. For example, let's imagine the player with White pieces spent their first three turns moving Major pieces 1, 2, and 3 like so:

    ........
    .123....
    pppppppp
    ...MMMMM

Each of the three major pieces has made a Knight jump, but every valid Scramble Chess starting position has two and only two Knights per side. The third major piece move for the White player would be illegal; they'd have to make a different, legal move.

As a further example, let's revisit our first entanglement scenario where a player moves three of their major pieces like a Rook. This is legal, because valid Scramble Chess starting positions have two Rooks and a Queen per side. Assuming no other illegal moves or entanglement conflicts with the Bishops, there will be many valid Scramble Chess starting positions allowing those three pieces to be moved like Rooks. Once one of the three potential-Rooks moves like a Bishop, that piece is the Queen from then on, as in every valid Scramble Chess starting position, there is only one Queen and it is the only piece that can move as both Rook and Bishop. In each of the few valid Scramble Chess starting positions that still match this *Haft Schroedinger Chess* match, the other two-potential Rooks will be Rooks, so any future moves need to treat those two pieces as Rooks in oder to be legal moves. This is where the concept of piece lockin emerges from.

Any way, these rules cause fun complications. I'll leave a few of the more interesting ones for you to ponder:

1. When a pawn promotes, it too becomes a major piece with undefined piece type.
2. Capturing a piece makes it not the King.
3. You can't capture the Queen unless you capture a piece that is currently locked in as the Queen.
4. Knights are way less interesting than Rooks and Bishops.

It's left as an exercise to the reader **why** these things are true.

