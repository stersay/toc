---
layout: math
title: Powerset Construction
nav_order: 7
mathjax: true
parent: Regular Languages
---

## Powerset Construction

### Epsilon Closure

Suppose $(Q,\,\Sigma,\,\delta,\,q_0,\,F)$ is an NFA and $R \subseteq Q$.  The __epsilon closure__ of $R$ is the following set of states:

$$
  E(R) = \left\{\;q \quad\middle|\quad \begin{array}{c}\text{$q$ can be reached from a state in $R$}\\\text{without reading another letter}\end{array} \;\right\}
$$

### Powerset Automaton

Suppose $N = (Q_N,\,\Sigma,\,\delta_N,\,q_N,\,F_N)$ is an NFA.  Then we construct a DFA $M$, the __powerset automaton__ as follows:

$$
    (Q_M,\,\Sigma,\,\delta_M,\,q_M,\,F_M)
$$

where:
* $Q_M = \mathcal{P}(Q_N)$
* $\delta_M(R,a) = \\{q \mid \exists r \in R \wedge q \in E(\delta_N(r,a)) \\}$
* $q_M = E(\\{q_N\\})$
* $F_M = \\{R \in Q_M \mid R \cap F_N \neq \emptyset\\}$

This guarantees that $L(M) = L(N)$.