---
layout: math
title: Product Construction
nav_order: 6
mathjax: true
parent: Regular Languages
---

## The Product Construction

Suppose we have two DFA over the same alphabet:

$$
    \begin{array}{l}
      M_1 = (Q_1,\,\Sigma,\,\delta_1,\,q_1,\,F_1) \\
      M_2 = (Q_2,\,\Sigma,\,\delta_2,\,q_2,\,F_2) 
    \end{array}
$$

The __product automaton__ $M_3$ is the DFA defined as $(Q,\,\Sigma,\,\delta,\,q_0,\,F)$
where:
* $Q = Q_1 \times Q_2$
* $\delta((p_1,\,p_2),a) = (\delta_1(p_1,\,a),\,\delta_2(p_2,\,a))$
* $q_0 = (q_1,\,q_2)$
* $F = F_1 \times F_2$

This definition ensures that $L(M_3) = L(M_1) \cap L(M_2)$.