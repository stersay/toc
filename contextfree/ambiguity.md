---
layout: math
title: Ambiguity
nav_order: 2
mathjax: true
parent: Context-Free Languages
---

## Ambiguity

<!-- ### Parse Trees

A parse tree is a $(V \cup \Sigma)$-labelled ordered tree satisfying the following properties:
* The root is the start variable $S$.
* The leaves are all terminals.
* If a node $n$ has, in order, children $n_1, n_2, \ldots, n_k$ then $n \to n_1n_2\cdots{}n_k$ is a rule of the grammar.

### Ambiguous Grammars -->

A derivation of a string $w$ in a grammar $G$ is a __leftmost derivation__ if, at every step, the leftmost remaining variable is the one replaced.

A string $w$ is generated __ambiguously__ in a context-free grammar $G$ if it has two or more different leftmost derivations.  Grammar $G$ is __ambiguous__ if it generates some string ambiguously.