---
layout: math
title: Equivalences
nav_order: 5
mathjax: true
parent: Regular Languages
---

## Equivalences

### DFA/NFA Equivalence

__Theorem:__
For all NFA $N$, there is a DFA $M$ such that $L(M) = L(N)$.
> *Proof.* Given NFA $N$, we can construct the corresponding powerset automaton, which is a DFA recognising $L(N)$.

__Theorem:__
For all DFA $M$, there is a NFA $N$ such that $L(M) = L(N)$.
> *Proof.* Every DFA can be viewed quite directly as a special kind of NFA (with a transition function whose value on each pair of non-$\epsilon$ inputs is a singleton set and is the emptyset on $\epsilon$).

__Corollory:__
A language is regular iff it is recognisable by an NFA.

### NFA/RegEx Equivalence

__Theorem:__
For all regular expressions $R$, there is an NFA $M$ such that $L(R) = L(M)$.

> *Proof.* Clearly the atomic regular expressions $a$ (for $a \in \Sigma$), $\epsilon$ and $\emptyset$ describe regular languages.  Then every regular expression is one of these or is composed from given regular expressions using concatenation, union and Kleene star, which all preserve regularity of their arguments (the regular languages are closed under these regular operations).

__Theorem:__
For all NFA $M$, there is a regular expression $R$ such that $L(R) = L(M)$.      

> *Proof.* In the forward direction, if a language is regular, then it is described by some automaton $M$.  Every such automaton is equivalent (trivially) to a GNFA $G$ and from this GNFA we can construct a 2-state GNFA using the GNFA simplification procedure.  The desired regular expression $R$ can be read directly off the only transition in the 2-state GNFA.

__Corollory:__
A language is regular iff it is described by a regular expression.