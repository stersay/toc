---
layout: math
title: Pumping Lemma
nav_order: 9
mathjax: true
parent: Regular Languages
---   

## Pumping Lemma

__Lemma:__
Suppose $A$ is regular.  Then there is some $p \in \mathbb{N}$ such that for any word $w$ with $|w| \geq p$, we may split $w$ as $w = xyz$ such that:
* For each $i \geq 0$, $xy^iz \in A$.
* $\|y\| > 0$
* $\|xy\| \leq p$

## Consequences

__Theorem:__
* The language $\{0^n1^n \mid n \in \mathbb{N}\}$ is not regular.
* The language $\{ww \mid w \in \{0,1\}^*\}$ is not regular.