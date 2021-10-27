# Definitions
## Base Case
The verification of the truth of $P(1)$ in an induction proof.
Also known as:
- base step
- basis step
- anchor
## Induction Hypothesis
The statement $P(k)$ in an induction proof.
## $(k+1)^{st}$ statement
The statement $P(k+1)$ in an induction proof.

# The Principle of Mathematical Induction
For each positive integer $n$, let $P(n)$ be a statement. If
1. $P(1)$ is true and
2. the implication $P(k) \implies P(k+1)$ is true for every positive integer $k$,

then $P(n)$ is true for every positive integer $n$.
# The General Principle of Mathematical Induction
Basically just above but for an arbitrary starting point!

For a fixed integer $m$, let $S = \{i \in \mathbb{Z}: i \geq m\}$. 
For each $n \in S$, let $P(n) be a statement. If
1. $P(m)$ is true and
2. $\forall k \in S, P(k) \implies P(k + 1)$ is true,

then $\forall n \in S, P(n)$ is true.