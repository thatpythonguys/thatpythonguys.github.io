---
author:
  name: Riju
title:  "DeMorgan's Law"
date:   2022-06-28 10:00:00 -0500
categories:
  - Set Theory
tags:
  - set theory
  - proofs
permalink: /Jun28th/
math: true
img_path: /assets/img/
pin: false
---

DeMorgan's Laws are one of the most important laws in basic set theory and come up time and time again. The proof of DeMorgan's law provides a nice introduction to proofs and reasoning to why it works.
> **Theorem**. $(A \cup B)^c = A^c \cap B^c$

*Proof.*

$$
\begin{align*}
&\text{First prove that } (A \cup B)^c \subseteq A^c \cap B^c \\
&\text{Let } x \in (A \cup B)^c. \\
&x \notin A \text{ and } x \notin B. \\
&x \in A^c \text{ and } x \in B^c. \\
&x \in A^c \cap B^c \\
\end{align*}
$$

Now we have to prove the statement in the opposite direction to establish equality.

$$
\begin{align*}
&\text{Now prove that } A^c \cap B^c \subseteq (A \cup B)^c  \\
&\text{Let } x \in A^c \cap B^c. \\
&x \in A^c \text{ and } x \in B^c. \\
&x \notin A \text{ and } x \notin B. \\
&x \in (A \cup B)^c \\
&\therefore (A \cup B)^c = A^c \cap B^c \\
\end{align*}
$$

As you can see, most of the work is simply just breaking apart the set theory language, interpreting it and putting it back together in a new way. Given this proof, the next exercise should be fairly simple.

> **Exercise**. Prove $(A \cap B)^c = A^c \cup B^c$
