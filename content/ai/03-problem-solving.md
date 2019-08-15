---
title: "Problem Solving"
draft: false
---

### Search and Planning Problems

_First stage of the problem solving process_ → defining the choices and their consequences. One also need to define what the goal is or, in other words, when one can consider the problem solved.

-   **The state space** → the set of _possible_ situations.
-   **Transitions** → possible moves between one state and another. One only counts direct transitions that can be accomplished with a single action. A sequence of multiple transitions ( e.g. from A to C, from C to D, and from D to B) is called **path.**
-   **Costs** → refer to the fact that, oftentimes the different transitions aren’t all alike. They can differ in ways that make some transitions more preferable or cheaper and others more costly.

* * *

### Games

Two-player, perfect-information games

-   The different states of the game are represented by nodes in the **game tree.**
-   _The nodes are arranged in levels_ → each level correspond to a player’s turn in the game → the _root node_ of the tree is the initial condition (usually depicted at the top of the diagram).

-   The tree end when the winning condition is met.

<img src="/img/content/ai/tik-tak-toe.png" class="img-fluid figure-img img-custom">

-   Starting from the last level **assign a numerical value** to every node of the tree [1, cap 2.3]
    -   One player wants to maximise the root value, the other wants to minimise it
    -   Assign numbers to previous levels based on which player is playing and **assumptions** → both players choose what is best for them and that what is best for one is the worst for the other (so called “zero-sum game”).


-   The value of the root node, which is said to be the value of the game, tells us who wins

#### The Minimax Algorithm

_It guarantees optimal game play in, theoretically speaking, any deterministic, two-person, perfect-information zero-sum game._

-   Given a state of the game, the algorithm simply computes the values of the children of the given state and chooses the one that has the maximum value if it is Max’s turn, and the one that has the minimum value if it is Min’s turn. More information in [2].

#### The Problem of Massive Game Trees

In many games, the game tree is simply way too big to traverse in full. In chess the average branching factor is about 35, which means one needs to explore about 2.7 quadrillion node for just 10 moves.

#### Tricks

**Heuristic Evaluation Function** → input = board position + which player’s turn is next → output = an estimate of the likely outcome of the game (continuing from the given board position).
_Used to stop the minimal recursion before reaching an end-node_

**Depth-limited version** of the minmax algorithm →  the _depth_ refers to the number of steps that the game tree is expanded before applying a heuristic evaluation function

#### Real-world scenarios

-   The number of states in even a moderately complex real-world scenario grows out of hand → solutions by exhaustive search (“brute force”) are out of question

-   In general transitions between states are not deterministic → one needs to adapt the algorithm to accept the concept of probability and tackle real AI problems.

* * *

## References

1.  [Elements of AI](https://course.elementsofai.com/) — Chapter 2.1, [2.3](https://course.elementsofai.com/2/3)
2.  [Minimax](https://en.wikipedia.org/wiki/Minimax) — Wikipedia
