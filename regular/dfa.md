---
layout: math
title: Deterministic Finite State Automata
nav_order: 1
mathjax: true
parent: Regular Languages
---

## Deterministic Finite State Automata

A __Deterministic Finite State Automaton (DFA)__ (in Sipser: just __Finite Automaton__) is a 5-tuple of shape:
$$
    (Q,\,\Sigma,\,\delta,\,q_0,\,F)
$$
whose components are restricted and named as follows:
* $Q$ is any _finite_ set, called the __states__
* $\Sigma$ is any alphabet
* $\delta : Q \times \Sigma \to Q$ is called the __transition function__
* $q_0 \in Q$ is called the __start state__ (equivalently: __initial state__)
* $F \subseteq Q$ is called the __accepting states__ 

We write DFA generically using $M,N,P$ and so on.

Let $M = (Q,\,\Sigma,\,\delta,\,q_0,\,F)$ be a DFA and let $w = w_1 \cdots{} w_n$ be a word over the alphabet $\Sigma$.

We say that $M$ __accepts__ $w$ just if there is a sequence of states $r_0,r_1,\ldots,r_n$ in $Q$ satisfying the following properties:

(i) $r_0 = q_0$

(ii) $\delta(r_i,\,w_{i+1}) = r_{i+1}$

(iii) $r_n \in F$

The __language__ of $M$ is the set $L(M) = \\{w \mid \text{$M$ accepts $w$}\\}$.
We say that $M$ __recognises__ the language $A$ just if $A = L(M)$.  