---
author:
  name: Riju
title:  "Linear Algebra - Playing with Markdown and LaTeX"
date:   2022-02-15 7:01:26 -0500
categories: [Fun, Linear Algebra]
tags: []
permalink: /Feb15th/
math: true
img_path: /assets/img/
pin: false
---
![The llamas](IMG-3749.jpg){: width="300" height="200" }
_LLamas_


Hello! This is my first real post, so this is going to mostly just be a test of my Markdown abilities.


Anyways I thought it was interesting how repetitive the introduction of linear algebra can be. That's not to say that the repetition is bad, it's just that we've found a lot of ways to essentially say the same thing.

Consider a system of $m$ equations with $n$ variables:

$$
\begin{gather*}
a_{11}x_1 + a_{12}x_2 + a_{13}x_3 + \cdots + a_{1m}x_n = b_1 \\
a_{21}x_1 + a_{22}x_2 + a_{23}x_3 + \cdots + a_{2m}x_n = b_2 \\
a_{31}x_1 + a_{32}x_2 + a_{33}x_3 + \cdots + a_{3m}x_n = b_3 \\
\vdots \\
a_{m1}x_1 + a_{m2}x_2 + a_{m3}x_3 + \cdots + a_{mn}x_n = b_m

\end{gather*}
$$

Even if we had no idea how to do Linear Algebra, we could probably solve for $x_1, x_2, x_3 \cdots$. (provided that a solution exists, of course). We would just use a combination of elimination and substitution.

## Augmented Matrices
But mathematicians got lazy and were looking for easier way to solve them. So they took all the coefficients ($a_1, a_2, a_3 \cdots$) of the variables ($x_1, x_2, x_3, \cdots$) in the equations and made a matrix, like so:

$$
\begin{equation*}
A_{m,n} =
\begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots  & \vdots  & \ddots & \vdots  \\
a_{m1} & a_{m2} & \cdots & a_{mn}
\end{bmatrix}
\end{equation*}
$$

And then they just appended the numbers $b_1, b_2, b_3$ to the end. We've obtained what is known as the augmented matrix!

$$
\begin{equation*}
A_{m,n} =
\begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} & b_{1}\\
a_{21} & a_{22} & \cdots & a_{2n} & b_{2}\\
\vdots  & \vdots  & \ddots & \vdots & \vdots \\
a_{m1} & a_{m2} & \cdots & a_{mn} & b_{m}
\end{bmatrix}
\end{equation*}
$$

Now you can do a bunch of row operations and solve the equations.

## Vector Equations

In fact, the augmented matrix and vector equations are exactly equivalent forms! You can prove it yourself, with some very straightforward expansion.

$$
\begin{align*}
x_1
\begin{bmatrix}
 a_{11} \\
 \vdots \\
 a_{m1}
\end{bmatrix} +
x_2
\begin{bmatrix}
 a_{12} \\
 \vdots \\
 a_{m2}
\end{bmatrix} +
x_3
\begin{bmatrix}
 a_{1m} \\
 \vdots \\
 a_{mn}
\end{bmatrix} =

\begin{bmatrix}
 b_{1} \\
 \vdots \\
 b_{m}
\end{bmatrix}
\end{align*}
$$

## Matrix-Vector Multiplication
And all this, in fact, is equal to matrix-vector multiplication. I won't get into the long proof here because it's annoying to write out and boring. If you know matrix-vector multiplication you should be able to prove it for yourself.

$$
\begin{align*}
A\vec{x} = \vec{b}
\end{align*}
$$

A is the coefficient matrix, $\vec{x}$ is a column vector of all your variables and $\vec{b}$ stores the solutions to each equation. Linear systems of equations, augmented matrices, and vector equations and matrix-vector multiplication are all basically the same thing. Alright, that's all for now. No new thoughts, just figuring out how to write.

Cheers.
