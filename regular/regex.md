---
layout: math
title: Regular Expressions
nav_order: 3
mathjax: true
parent: Regular Languages
---

# Regular Expressions

We say that an expression (i.e. piece of syntax) $R$ is a __regular expression__ over an alphabet $\Sigma$ just if it has one of the following 5 shapes:

$a$ | for some $a \in \Sigma$ 
$\epsilon$ | 
$\emptyset$ | 
$(R_1 \cup R_2)$ | where $R_1$ and $R_2$ are regular expressions 
$(R_1 \circ R_2)$ | where $R_1$ and $R_2$ are regular expressions 
$(R_1^*)$ | where $R_1$ is a regular expression 

We use $\mathcal{R}$ to denote the set of all regular expressions and $R$ as a generic element of that set.

## Language

The __language__ $L(R)$ defined by a regular expression $R$ is computed as follows:

$$
\begin{align*}
    L(a) &= \{a\} \\
    L(\epsilon) &= \{\epsilon\} \\
    L(\emptyset) &= \emptyset \\
    L(R_1 \cup R_2) &= L(R_1) \cup L(R_2) \\
    L(R_1 \circ R_2) &= L(R_1) \circ L(R_2) \\
    L(R_1^*) &= L(R_1)^*
\end{align*}
$$

## Conventions

* Parentheses can be omitted from nested applications of the same binary operator (union or concat).
* Parentheses can be omitted from nested applications of different operators under the agreement that: star binds tightest, then concatenation and then union.
* The concatenation symbol is typically omitted.
* We write $\Sigma$ as if it were part of the syntax of regular expressions, meant as a shorthand for the (proper) regular expression $(a_1 \cup a_2 \cup \cdots{} \cup a_k)$ where $\Sigma = \{a_1,\,a_2,\,\ldots,a_k\}$.
* We will lazily write $R$ both for the expression and for its language (properly written: $L(R)$).  From now on we will not write $L(R)$ unless we are being extra precise.