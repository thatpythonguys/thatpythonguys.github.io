---
author:
  name: Pramana
title: Fields - Finite Fields
date: '2022-06-15 10:00:00 -0500'
categories:
  - Abstract Algebra
tags:
  - fields
  - algebra
  - splitting fields
permalink: /Jun15th/
math: true
img_path: /assets/img/
pin: false
---

With groups, it's easy for us to find finite ones that have the same order,
but are not the same (up to isomorphism). The simplest example I can give is
$\mathbb{Z}_4$ and $\mathbb{Z}_2\times\mathbb{Z}_2$, which both have 
order $2$, but they are not isomorphic. The former is a cyclic group, 
but the latter is not!

However, with fields, I hope to show in this post that fields are 
the exactly the same as each other (up to isomorphism)
if they have the same **finite** order. This means when I tell you I have a 
field of order $4$, I really mean **the** field of order $4$–there is only one.

## Splitting Fields

I do not want to spend too much time focusing on splitting fields, but 
I will mention some important takeaways that are useful for this proof. 

> **Definition 1**. A **splitting field** is a field such that for a polynomial
> $f(x)$ over a field $K$, 
> all roots are contained in the field. 

For example, the splitting field for $r(x)=x^2-2$ over $\mathbb{Q}$ is 
$\mathbb{Q}(\sqrt{2})$, since the roots of this function are $\pm\sqrt2$,
meaning we must attach $\sqrt2$ to $\mathbb{Q}$.

> **Theorem 2**.
> Let $f(x)$ be a polynomial over $K$. If the extensions fields $F$ and $E$
> are both splitting fields over $K$, then they are isomorphic.

*Proof.* An entire chapter of the book. See [these notes](http://www.math.toronto.edu/gscott/nov4_2015.pdf) for a full proof. $\blacksquare$

## Size of Finite Fields

> **Definition 3**. The **characteristic** of a field $F$ is the smallest
> positive number $n$ such that $1\cdot n =0$. If one does not exist,
> the characteric is $0$. Denoted $\mathrm{char}(F)$.

All [integral domains](https://en.wikipedia.org/wiki/Integral_domain) have characteristic $0$ or $p$, where $p$ is a 
prime. Since all fields are integral domains, we know that fields can 
only have characteristic $0$ or $p$. 

> **Theorem 4**.
> All finite fields with characteristic $p$ have order $p^n$, 
> where $p$ is a prime number, and $n$ is a positive integer. 

*Proof.*  First note that if a field $F$ has characteristic $p$,
then the homomorphism $\phi: \mathbb{Z}\rightarrow F$ such that
$\phi(n)=n\cdot1$ has a kernel $p\mathbb{Z}$. From the [ring isomorphism theorem](https://en.wikipedia.org/wiki/Isomorphism_theorems#Theorem_A_(rings)),
we can say that the image of $\phi(\mathbb{Z})$, which we will call
$K$, is isomorphic to 
$\mathbb{Z}/\ker(\phi) = \mathbb{Z}/p\mathbb{Z} \cong \mathbb{Z}_p$.

Now, since $F$ is a vector space over $K$, and both $F$ and $K$
are finite, we let $[F:K]=n$. Every element $f \in F$ has the unique form

$$f=a_1v_1+a_2v_2+\cdots+a_nv_n$$

for a basis $v_i$ and coefficients $a_i$, with $a_i \in K$. To count the number 
of possible elements we can form, simply use combinatorics. There are $p$ choices 
for each $a_i$, because there are $p$ elements in $K$. So the number of possible 
elements is $p^n$, for the $n$ coefficients. $\blacksquare$

We call $K$ the **prime subfield** of $F$. Note that $1 \in K$.
This theorem gives us an idea about how some fields are structured. 

## Useful Theorems/Lemmas

> **Theorem 5**. Let $F$ be a finite field with $p^n$ elements. Then 
> $F$ is a splitting field for $x^{p^n}-x$ over its prime subfield $K$.

> **Corollary 6**. Two finite fields are isomorphic if and only if 
> they have the same number of elements. 

*Proof.* Let $F$ and $E$ both have $p^n$ elements, and have 
prime subfields $K$ and $L$. $K\cong L\cong \mathbb{Z}_p$. Since
the polynomial $x^{p^n}-x$ splits over $F$ and $E$ in $K$ and $L$,
$F$ and $E$ are both splitting fields, and by Theorem 2, they are
isomorphic. $\blacksquare$

> **Lemma 7**. Let $F$ be a field with characteristic $p$, and let $n$
> be a positive integer. 
> 
> $$ \{ a \in F \mid a^{p^n}-a=0\}$$
>
> is a subfield of $F$.

> **Lemma 8**. Let $F$ be a field of characteristic $p$. If $n$ is a
> positive integer not divisible by $p$, then $x^n-1$ has no repeated
> roots in any extension field of $F$.

## The Main Theorem

> **Theorem 9**. For prime $p$ and positive integer $n$, there is a 
> field with $p^n$ elements. 

*Proof*. We want to create a field $F$ with $p^n$ elements. So let
$F$ be the splitting field for $f(x)=x^{p^n}-x$ over $\mathbb{Z}_p$.
Since 

$$f(x)=x^{p^n}-x = x(x^{p^n-1}-1),$$

and $p$ does not divide $p^n-1$, we know from Lemma 8 that there are
no repeated roots in the polynomial. Lemma 7 tells us that all
these roots form their own field. Therefore $F$ is a field that 
contains all roots of $f(x)$, of which there are $p^n$ unique ones.
$\blacksquare$

Since any finite field of the same order is isomorphic, and we can 
create fields of any possible order $p^n$, we can call 
these finite fields
**the** field of order $9,27,100,729$ etc. 
In fact, the field with $p^n$ elements is called the **Galois field**
of order $p^n$, denoted $\mathrm{GF}(p^n)$.

The main point in all of this is that we have a fairly good 
understanding of how fields can behave when they are finite–something
that we can't say for even finite groups 
(see [Monster group](https://en.wikipedia.org/wiki/Monster_group)).
This makes finite fields a good candidate for studying cryptography,
where encryption needs to be hard to crack, but easy to implement.