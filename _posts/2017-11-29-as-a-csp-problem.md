---
layout: post
title: Constraint Satisfaction in Haft Schroedinger Chess
category: "Schroedinger-Chess"
banner: /img/schroedingerchess/project-image.png
---

In the [previous post](schroedinger-chess/2017/11/28/introduction-to-haft-schroedinger-chess.html), we established rules for *Haft Schroedinger Chess*, crucially rule five which defines what makes a move legal. However, we didn't establish a practical way to verify if a move is legal based on that definition; it isn't a constructive rule.

To do that, I'm going to introduce the concept of [Constraint Satisfaction Problems](https://en.wikipedia.org/wiki/Constraint_satisfaction_problem). Imagine a Sudoku puzzle: 

    ...|.2.|...
    4..|...|...
    ...|..1|3..
    ---+---+---
    ...|...|...
    .4.|6..|.5.
    ...|.8.|...
    ---+---+---
    ...|.5.|...
    ..9|...|...
    ...|...|..7

Can this Sudoku puzzle be solved? That question is a Constraint Satisfaction Problem. Constraint Satisfaction Problems have three components:

1. A list of variables
2. For each variable a set of possible values that variable can be
3. Rules (or constraints) limiting what values two or more variables can be in relation to each other

For Sudoku those three components are:

1. A variable for each blank box
2. Every variable must be a whole number between 1 and 9 inclusive
3. No column, row, or box may have a repeated number in its boxes

Our question, 'Can this Sudoku puzzle be solved?' is equivalent to asking 'Is there a way to assign each variable a value such that the constraints are satisfied?'. Similarly, deciding if a move in *Haft Schroedinger Chess* is legal is also a Constraint Satisfaction Problem with these three components:

1. A variable for every major piece on both sides
2. Each variable is one of King, Queen, Rook, Bishop, or Knight
3. For each side only one variable can be a King, one a Queen, two be Rooks, two be Bishops, and two be Knights. Additionally, the moves played so far (as well as the one about to be played) must be consistent with the piece values assigned to the variables representing each piece.

Asking 'Is this *Haft Schroedinger Chess* move legal?' is the same as asking 'Is there a way to assign a piece value to every major piece such that the above constraints are satisfied?'. If there is at least one way to do that, then the move is legal. Note, that there can (an probably will be) be many variable assignments that satisfy the constraints.

The valid Scramble Chess starting position required in the definition of move legality is whichever one has matching piece assignments to the constraint solution. There's a one to one correspondence between solutions to this CSP and valid Scramble Chess starting position, as a valid Scramble Chess starting position is nothing more than assigning a piece value to each of sixteen variables, one for each major piece. 

As an example, let's evaluate the legality of moves in a sample game. In the following diagram, the white pieces are the capital 'P's and the eight numbers at the bottom. The black pieces are the opposing 'p's and eight numbers at the top.

    1234567.
    ppp.pppp
    ......8.
    ...p....
    ....P...
    ...6....
    PPPP.PPP
    12345.78

So far the game has played:

1. e4, d5
2. White piece 6 to d3, Black piece 8 to g6

Can white play piece 6 capture d5? The constraints for this instance of the necessary Constraint Satisfaction Problem is:

1. The standard roster rules (only one Queen, etc)
2. White piece 6 is a Bishop or a Queen (based on white move two)
3. Black piece 8 is a Knight (based on black move two)
4. White piece 6 is a Rook or a Queen (needs to be true for the desired third white move)

And indeed there are many, many solutions to this CSP. Each of these solutions will have White piece 6 as the Queen though, locking it in as the Queen. Likewise Black piece 8 is locked in a s a Knight.

Unfortunately, Constraint Satisfaction Problems (outside of special cases) are not computationally easy to find solutions for. Many types of Constraint Satisfaction Problems, such as [Boolean Satisfiability](https://en.wikipedia.org/wiki/Boolean_satisfiability_problem#Unrestricted_satisfiability_.28SAT.29) are NP-complete.

At it's worst, solving a Constraint Satisfaction Problem means brute forcing every combination of variable values, which takes exponential time. For *Haft Schroedinger Chess* this would mean having to potentially search 5^16 combinations to find one and prove a move is legal. The problem of finding a solution starts easy but gets hard as the game progresses. At the beginning of the game after only a few moves have been played there are few constraints, and most variable assignments are valid solutions. As more moves are played and the number of constraints increases, the ratio of solution to invalid variable assignments increases. Finding a valid solution to show a move is legal will require searching through more and more of possible variable assignments. 

There is a special case that side steps the issue. If *Haft Schroedinger Chess* is played without check, determining move legality is trivial. This is fast to solve because there are no interdependencies between piece values beyond the initial roster rules of chess. Every additional move reduces the number of values one specific variable can be without adding any new constraints. The space we need to search through gets smaller, as opposed to less saturated with solutions.

If *Haft Schroedinger Chess* is played with check though, each move will make determining move legality harder and harder. Imagine this scenario, depicted with the same conventions as the last sample game:

    12.45678
    ppp.pppp
    ....3...
    ........
    ........
    ......8.
    PPPP.PPP
    1234567.

Black piece 3 moved from c8 to e6 using a diagonal, making it either a Bishop of Queen. Now White wished to move White piece 2 to c3 like a Knight. That's a legal move, but it adds two new constraints:

1. If Black piece 3 is a Queen or Rook, then White piece 5 is not a King
2. If White piece 5 is a King, then Black piece 3 is not a Queen or Rook

Leaving a piece in check is illegal in both traditional and scramble chess, so the Black piece 3 White piece 5 has to be required to produce no checks. Otherwise there can't be a valid Scramble Chess starting position needed to make the move legal. These two new constraints can't be simplified as variable domain restrictions.
