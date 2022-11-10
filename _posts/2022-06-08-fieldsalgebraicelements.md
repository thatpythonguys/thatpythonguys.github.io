---
author:
  name: Pramana
title:  "Fields - Algebraic Elements"
date:   2022-06-08 7:01:26 -0500
categories: [Abstract Algebra]
tags: [fields, transcendentals]
permalink: /Jun8th/
math: true
img_path: /assets/img/
pin: false
---

# Algebraic Elements

Which number is "further" from the integers, $\sqrt{2}+\sqrt{3}$ or
$\sqrt{2}$? It intuitively feels like it would be harder to
get to $\sqrt2+\sqrt3$ using the integers and the operations we know,
like squarerooting, adding, and subtracting. But is there any quantifiable
way to explain those intuitions?

This post is to help show what makes a number **algebraic**.
To do this, I need to explain what fields are, and then we can
expand the idea to show that some numbers, like $\sqrt{2}+\sqrt{3}$ are
"harder" to get than $\sqrt{2}$ from the integers, $\mathbb{Z}$.

## What are Fields?

[Fields](https://en.wikipedia.org/wiki/Field_(mathematics)) are a unique type
of algebraic structure. They are a lot like a
[group](https://en.wikipedia.org/wiki/Group_(mathematics)), but instead of just
having one operation, they have two. "Addition", and "Multiplication".
I only put those in quotes because technically they don't have to
behave like the good old addition and multiplication we know,
but for the most part, we can assume that they are.

Along with this, fields have **distributivity**. It
says that, $$ a(b+c) = ab + ac,$$ which means that addition and
multiplication have a means of interacting with each other.

We define addition and division the way we expect them to be,
 and we have them act on our regular numbers,
whether they be $\mathbb{Z}$ or $\mathbb{R}$.

## Algebraic Numbers and Degrees

Now when we say a number is **algebraic** in a certain field, we mean
that some polynomials with coefficients in that field has a root
that is the number we are looking for.

> **Example**
>
> $\sqrt{2}$ is algebraic in $\mathbb{Z}$. Why?
> Because if $x=\sqrt2$, then $x^2=2$, so a polynomial that we can form
> with $\sqrt2$ as a root is $f(x)=x^2-2$.

In fact, in the last example, it's easy to see that $x^2-2$ doesn't
split into any smaller polynomials. This means that $f(x)$ is
an [irreducible polynomial](https://en.wikipedia.org/wiki/Irreducible_polynomial). In reality, all algebraic numbers of a field
have a unique irreducible polynomial that has it as a root.

This fact allows us to get a scale for how algebraic a number can be.
We see that the irreducible polynomial that has a root of $\sqrt2$ has
a degree (largest power of $x$) of $2$. This motivates us to define
the degree of $\sqrt2$ over $\mathbb{Z}$ as $2$.

Now think about the beginning question, what polynomial has a root of
$\sqrt2+\sqrt3$? Well a good starting point, like the last one,
was to let $x=\sqrt2+\sqrt3$, and try to create a polynomial with
integer roots out of it. The process is as follows:

$$
\begin{align*}
x &= \sqrt2+\sqrt3 \\
x- \sqrt2 &= \sqrt3 \\
x^2-2\sqrt2x + 2 &= 3 \\
x^2 -1 &= 2\sqrt2x \\
x^4-10x^2+1&=0
\end{align*}
$$

Our desired polynomial is $x^4-10x^2+1$. Checking that this
is irreducible is important, but I won't cover it here,
(see [Einsenstein's Irreducibility Criterion](https://en.wikipedia.org/wiki/Eisenstein%27s_criterion)). Once we know it is irreducible,
then we can conclude that $\sqrt2+\sqrt3$ has degree $4$ in $\mathbb{Z}$.

Well then, since we need a higher degree to find a polynomial with a root of
$\sqrt2+\sqrt3$, there is a mathematical justification for why it is
"harder" to get $\sqrt2+\sqrt3$ over $\sqrt2$.

## Bonus: Transcendentals

**Transcendental numbers** are often discussed when talking about $\pi$ or $e$.
The definition of transcendental number is simple: a number is transcendental
in a field $F$ if it isn't algebraic. What that's saying is that there is
no polynomial that exists that has $\pi$ or $e$ as a root. Proofs for these
are quite difficult, but a google search may be worth the time to look at them.
