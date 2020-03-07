---
layout: math
title: Nondeterministic Finite State Automata
nav_order: 2
mathjax: true
parent: Regular Languages
---

## Nondeterministic Finite State Automata

A __Nondeterministic Finite State Automaton (NFA)__ is a 5-tuple of shape:

$$
    (Q,\,\Sigma,\,\delta,\,q_0,\,F)
$$

whose components are restricted and named as follows:
* $Q$ is any *finite* set, called the __states__
* $\Sigma$ is any alphabet
* $\delta : Q \times \Sigma_{\epsilon} \to \mathcal{P}(Q)$ is called the __transition function__
* $q_0 \in Q$ is called the __start state__ (equivalently: __initial state__)
* $F \subseteq Q$ is called the __accept states__

Here $\Sigma_\epsilon$ is shorthand for $\Sigma \cup \{\epsilon\}$.

### Language Recognised

Let $M = (Q,\,\Sigma,\,\delta,\,q_0,\,F)$ be an NFA and let $w = w_1 \cdots{} w_n$ be a word over the alphabet $\Sigma_\epsilon$.

We say that $M$ __accepts__ $w$ just if there is a sequence of states $r_0,r_1,\ldots,r_n$ in $Q$ satisfying the following properties:
* $r_0 = q_0$
* $r_{i+1} \in \delta(r_i,\,w_{i+1})$
* $r_n \in F$

The __language__ of $M$ is the set $L(M) = \\{w \mid \text{$M$ accepts $w$}\\}$.
We say that $M$ __recognises__ the language $A$ just if $A = L(M)$.  