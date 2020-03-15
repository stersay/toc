---
layout: math
title: Pushdown Automata
nav_order: 2
mathjax: true
parent: Context-Free Languages
---

## Pushdown Automata

A __pushdown automaton (PDA)__ is a 6-tuple $$(Q,\Sigma,\Gamma,\delta,q_0,F)$$ where:
* $$Q$$ is a finite set of states
* $$\Sigma$$ is a finite alphabet
* $$\Gamma$$ is a finite alphabet called the __stack alphabet__
* $$\delta : Q \times \Sigma_\epsilon \times \Gamma_\epsilon \to \mathcal{P}(Q \times \Gamma_\epsilon)$$ is the transition function
* $$q_0 \in Q$$ is the start state
* $$F \subseteq Q$$ is the set of accept states.

### Computation and Language

Suppose $$P = (Q,\Sigma,\Gamma,\delta,q_0,F)$$ is a PDA.  We say that word $w \in \Sigma^*$ is __accepted__ just if it can be written as $w_1 w_2 \cdots{} w_m$, with each $w_i \in \Sigma_\epsilon$, and there is a sequence of states $$r_0,r_1,\ldots,r_m \in Q$$ and strings $$s_0,s_1,\ldots,s_m \in \Gamma^*$$ (representing intermediate stacks) such that:
* $$r_0 = q_0$$ and $$s_0 = \epsilon$$.
* For each $i \in \{0..m-1\}$ we have $$(r_{i+1},b) \in \delta(r_i,w_{i+1},a)$$ (for some $$a,b \in \Gamma_\epsilon$$) and $$s_i$$ is of the form $$at$$ (for some stack $$t \in \Gamma^*$$) and then $$s_{i+1} = bt$$.
* $$r_m \in F$$.

The __language recognised__ by $P$ is $$L(P) = \{w \mid \text{$w$ is accepted by $P$}\}$$.