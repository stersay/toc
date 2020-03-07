---
layout: math
title: GNFA Construction
nav_order: 8
mathjax: true
parent: Regular Languages
---   

## GNFA Construction

### Generalised Nondeterministic Finite Automata

Let $\mathcal{R}$ be the collection of all regular expressions on the alphabet $\Sigma$.

A __generalized NFA (GNFA)__ is a 5-tuple $(Q,\Sigma,\delta,q_\text{start},q_\text{accept})$ with:
* $Q$ is a finite set of states
* $\Sigma$ is the input alphabet
* $\delta : (Q - \\{q_\text{accept}\\}) \times (Q - \\{q_\text{start}\\}) \to \mathcal{R}$ is the transition function
* $q_\text{start}$ is the initial state
* $q_\text{accept}$ is the (single) accepting state

### Language Recognised

A GNFA __accepts__ a string $w$ just if $w = w_1 w_2 \cdots{} w_k$ (with each $w_i \in \Sigma^*$) and there is a corresponding sequence of states $q_0,q_1,\ldots,q_k$ with:
* $q_0 = q_\text{start}$
* $q_k = q_\text{accept}$
* for each $i \in \\{1..k\\}$, $w_i \in L(\delta(q_{i-1},q_i))$

### Simplifying GNFA

Given any GNFA $G = (Q,\Sigma,\delta,q_\text{start},q_\text{accept})$ with $\|Q\| > 2$ we can construct a smaller one $G' = (Q',\Sigma,\delta',q_\text{start},q_\text{accept})$ with $\|Q'\| = \|Q\| - 1$, recognising exactly the same language.

Choose any state $q_\text{rip} \in Q - \\{q_\text{start},\,q_\text{accept}\\}$ and set:
* $Q' = Q - \\{q_\text{rip}\\}$
* for each $(p,q) \in (Q' - \\{q_\text{accept}\\}) \times (Q' -\\{q_\text{start}\\})$ set:

$$
\delta'(p,q) = R_1R_2^*R_3 \cup R_4
$$

where $R_1 = \delta(p,q_\text{rip})$, $R_2 = \delta(q_\text{rip},q_\text{rip})$, $R_3 = \delta(q_\text{rip},q)$ and $R_4 = \delta(p,q)$.

By simplifiying repeatedly we can obtain a 2-state GNFA (essentially a regular expression).