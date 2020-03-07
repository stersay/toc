---
layout: math
title: Closure Properties
nav_order: 4
mathjax: true
parent: Regular Languages
---

## Closure Properties

The regular languages are closed under various operations on languages.  In particular, the following three operations are called the __regular operations__:
* __Union__:  $A \cup B = \\{x \mid x \in A \vee x \in B\\}$
* __Concatenation__: $A \circ B = \\{xy \mid x \in A \wedge y \in B\\}$
* __Kleene Star__: $A^* = \\{x_1x_2\cdots{}x_k \mid k \geq 0 \wedge \forall i.\ x_i \in A\\}$

__Theorem:__
The regular languages are closed under intersection, that is: if $A$ and $B$ are regular, then so is $A \cap B$.

> *Proof:* Since $A$ and $B$ are regular, they are recognised by two DFA $M_1$ and $M_2$ respectively.  For any two DFA, we can construct their product $M_3$ in such a way that we are guaranteed $L(M_3) = A \cap B$.

__Theorem:__
The regular languages are closed under complement, that is: if $A$ is regular, then so is $\bar{A} = \Sigma^* - A$.

> *Proof.* Since $A$ is regular, there is some DFA $M = (Q,\Sigma,\delta,q_0,F)$ that recognises it.  Construct a new DFA $N = (Q,\Sigma,\delta,q_0,F')$ where $F' = Q - F$ (i.e. the accepting and non-accepting states of $M$ are interchanged).  This way $L(N) = \bar{L(M)} = \bar{A}$.

__Theorem:__
The regular languages are closed under union: if $A$ and $B$ are both regular languages over the same alphabet, then $A \cup B$ is regular.

> *Proof.* Suppose $(Q_1,\Sigma,\delta_1,q_1,F_1)$ is an NFA recognising $A$ and $(Q_2,\Sigma,\delta_2,q_2,F_2)$ is a NFA recognising $B$.
Then choose some $q_0 \notin Q_1 \cup Q_2$ and construct NFA $(Q,\,\Sigma,\,\delta,\,q_0,F)$ to recognise $A \cup B$:
* $Q = \\{q_0\\} \cup Q_1 \cup Q_2$ 
* $F = F_1 \cup F_2$
* $$\delta(q,\,a) = 
        \begin{cases}
            \delta_1(q,\,a) & \text{if $q \in Q_1$} \\
            \delta_2(q,\,a) & \text{if $q \in Q_2$} \\
            \{q_1,\,q_2\} & \text{if $q = q_0$ and $a = \epsilon$} \\
            \emptyset & \text{otherwise}
        \end{cases}$$

__Theorem:__
The regular languages are closed under concatenation: if $A$ and $B$ are regular languages over the same alphabet, then so is $A \circ B$.

> *Proof.* Suppose $(Q_1,\Sigma,\delta_1,q_1,F_1)$ is an NFA recognising $A$ and $(Q_2,\Sigma,\delta_2,q_2,F_2)$ is a NFA recognising $B$.  Then construct $(Q,\Sigma,\delta,q_0,F)$ to recognise $A \circ B$:
* $Q = Q_1 \cup Q_2$
* $q_0 = q_1$
* $F = F_2$
* $$\delta(q,a) = 
\begin{cases}
    \delta_1(q,a) & \text{if $q \in Q_1 \setminus F_1$ or ($q \in F_1$ and $a \neq \epsilon$)} \\
    \delta_1(q,a) \cup \{q_2\} & \text{$q \in F_1$ and $a = \epsilon$} \\
    \delta_2(q,a) & \text{if $q \in Q_2$} \\
\end{cases}$$

__Theorem:__
The regular languages are closed under the Kleene star operation: if $A$ is regular, then so is $A^*$.

> *Proof.* Suppose $(Q,\Sigma,\delta,q_0,F)$ is an NFA recognising $A$.  Choose some $q_0' \notin Q$ and construct $(Q',\Sigma,\delta',q_0',F')$ so it recognises $A^*$:
* $Q' = Q \cup \{q_0'\}$
* $F' = F \cup \{q_0'\}$
* $$\delta'(q,a) = 
\begin{cases}
    \delta(q,a) & \text{if $q \in Q \setminus F$ or $q \in F$ and $a \neq \epsilon$} \\
    \delta(q,a) \cup \{q_0'\} & \text{if $q \in F$ and $a = \epsilon$} \\
    \{q_0\} & \text{if $q = q_0'$ and $a = \epsilon$} \\
    \emptyset & \text{if $q = q_0$ and $a \neq \epsilon$}
\end{cases}$$