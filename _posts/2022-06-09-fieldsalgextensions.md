---
author:
  name: Pramana
title: Fields - Extensions and Degrees
date: '2022-06-09 10:00:00 -0500'
categories:
  - Fun
  - Abstract Algebra
tags:
  - fields
  - algebra
  - linalg
permalink: /Jun9th/
math: true
img_path: /assets/img/
pin: false
---

# Field Extensions and Linear Algebra

I hope to show the relationship between field extensions and linear
algebra, and how a proof using the latter can extend to a
useful property of the former.

## Extension Fields are Just Vector Spaces

An **extension field** of a field $F$ is any field that contains $F$
as a subfield. There are many ways to extend a field. If you take
an element $u \notin F$, and then let $u$ be in $F$,
then it extends $F$. We denote this $F(u)$, and this is a field
extension. Since we only added a single element,
this is called a **simple extension**.

Turns out there is a fundamental connection between field extensions,
and linear algebra, and can be used to prove some interesting theorems.
Most importantly,
If $F$ is a field extension of $K$ then $F$ is simply
a [vector space](https://en.wikipedia.org/wiki/Vector_space) over $K$.
Elements of $K$ are scalars, and elements of $F$ are vectors.

## D(imensions)egrees

We can also recontextualize **dimension** in terms of our fields, since
sticking with linear algebra terms can get confusing when dealing with
groups because of the different contexts (sorry Riju).
The **degree** of $F$ as a vector space over $K$
is denoted $[F:K]$. This has the exact same meaning as dimension,
but can be used to come to different conclusions from the eyes of groups.

> ##### Theorem 1: Multiplicativity Formula for Degrees
>
> Let $E$ be an field extension of $K$ and $F$
> be a field extension of $E$. Then, $$[F:K] = [F:E][E:K]$$

The real interesting part of this for me (and why I'm writing this
in the first place) is the fact that the proof uses basic concepts
from linear algebra to prove this.

_Proof_.
Since we are dealing with field extensions, $F$ is just a vector space
over $E$, and $E$ is just a vector space over $K$.
Therefore we can come up with a basis $\{u_1, u_2, \dots, u_n\}$ for
$F$ over $E$ (assuming $[F:E]=n$), and the basis
$\{v_1,v_2,\dots,v_m\}$ for $E$ over $K$ (assuming $[E:K]=m$).

I claim that the set of pairwise products, $u_iv_j$, which
I will call the set $\mathcal{B}$ is the basis for
the vector space of $F$ over $K$. We can do this by showing that
$\mathcal{B}$ both spans $F$ over $K$ and each basis is linearly
independent. The number of ways to
combine $u$'s and $v$'s is $nm$, which would complete the proof.

To show that $\mathcal{B}$ [spans](https://en.wikipedia.org/wiki/Linear_span) $F$ over $K$, note that for any element $u$
in $F$, we can have

$$ u= \sum_{i=1}^{n}a_iu_i,$$

where each $u_i$ is the basis for $F$ over $E$, and each $a_i$ is
in $E$, since $F$ is a vector space over $E$. Similarly,
for each element $a_i$ in $E$, we can write it as

$$ a_i = \sum_{j=1}^mc_{ij}v_j,$$

where each $v_j$ is the basis for $E$ over $K$, and each $c_{ij}$ is
in $K$. Well then we can combine these sums to get

$$ u = \sum_{i=1}^n\sum_{j=1}^mc_{ij}v_ju_i,$$

showing us that any $u$ in $F$ can be found as the sum of its basis vectors
times $c_{ij}$ in $K$.

The next step is to show that $\mathcal{B}$ is [linearly independent](https://en.wikipedia.org/wiki/Linear_independence).
Recall that a set is linearly independent if any linear combination of
the set that equals $0$ implies that all coefficients are $0$ as well.
Suppose $ \sum_{i,j}c_{ij}v_ju_i=0$ for a linear combination of
the set $\mathcal{B}$. This is the same as

$$ 0 =\sum_{i=1}^n\left(\sum_{j=1}^mc_{ij}v_j\right)u_i. $$

Notice that the inner "$j$" sum is a coefficient for the $u_i$ basis.
Now since each $u_i$ form a basis for $F$ over $E$, each of its
coefficients $\sum_{j=1}^mc_{ij}v_j$ must be $0$. Similarly, each $v_j$
form a basis for $E$ over $K$, so each coefficient $c_{ij}$
must also be $0$. This completes the proof, because we have shown that
a linear combination of $\mathcal{B}$ that equals $0$ must have all
coefficients $c_{ij}$ equal $0$.
$\blacksquare$

Now what use does this linear algebra proof have beyond linear algebra
itself? Here's a useful example for how we can use it to determine the
degree of one field extension over the original field.

> ##### Example 2: $[\mathbb{Q}(\sqrt3,\sqrt2):\mathbb{Q}]$
>
> From Theorem 1, we know that
>
> $$ [\mathbb{Q}(\sqrt3,\sqrt2):\mathbb{Q}] = [\mathbb{Q}(\sqrt3,\sqrt2):\mathbb{Q}(\sqrt2)][\mathbb{Q}(\sqrt2):\mathbb{Q}].$$
>
> We know that $[\mathbb{Q}(\sqrt2):\mathbb{Q}]=2$, because the minimal
> polynomial for $\sqrt2$ in $\mathbb{Q}$ is $p(x)=x^2-2$. Moreover, we
> can show that the minimal polynomial for $\sqrt3$ in $\mathbb{Q}(\sqrt2)$
> is $x^2-3$. Therefore $[\mathbb{Q}(\sqrt3,\sqrt2):\mathbb{Q}(\sqrt2)]=2$.
> So
>
> $$ [\mathbb{Q}(\sqrt3,\sqrt2):\mathbb{Q}] = 2\cdot 2= \boxed{4}. $$
>
> What's more, we can use this to find the basis for
> $\mathbb{Q}(\sqrt3,\sqrt2)$ over $\mathbb{Q}$, it is a field extension and therefore a vector space.
>
> The basis $\mathbb{Q}(\sqrt2)$ over $\mathbb{Q}$ is $\{1,\sqrt2\}$,
> and the basis for $\mathbb{Q}(\sqrt3,\sqrt2)$ over $\mathbb{Q}(\sqrt2)$
> is $\{1,\sqrt{3}\}$, so taking all possible products, the basis is
>
> $$\{ 1, \sqrt2, \sqrt3, \sqrt6\},$$
>
> perfectly matching up with our degree, $4$.

The idea of a basis, as shown by the last example, is very different
from the basis used in a typical introduction class for Linear Algebra.
We don't use vectors as a basis, instead we just use numbers. It
becomes much more abstract it that way.

It should be clear that this theorem is very useful for understanding
how field extensions interact, and allow us to learn more about
the degrees of certain field extensions. I hope to show
the further use of this theorem in future posts.