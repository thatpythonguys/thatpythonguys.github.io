---
author:
  name: Pramana
title: Number Theory - Perfect Numbers
date: '2022-06-19 10:00:00 -0500'
categories:
  - Fun
  - Number Theory
tags:
  - number theory
  - perfect numbers
permalink: /Jun19th/
math: true
img_path: /assets/img/
pin: false
---

**Perfects numbers** are a highly studied subset of the positive integers
that relate to our understanding of number theory. 

I will show a proof of the structure of all **even** perfect numbers,
and a bonus section on the conspiracy of odd perfect numbers.

$\sigma(n)$ will denote the sum of divisors of 
$n$, a positive integer.

> **Definition 1**. If $n$ factors into prime factors 
> $n = p_1^{e_1}p_2^{e_2}\cdots p_t^{e_t}$, then
> 
> $$ \sigma(n)=\prod_{i=1}^{t}(1+p_i+p_i^2+\cdots+p_i^{a_i}) = \prod_{i=1}^{t}\frac{p_i^{a_i+1}-1}{p_i-1}$$
> 
> (the last simplification is a result of [this](https://math.stackexchange.com/questions/900869/prove-xn-1-x-1xn-1xn-2-x1)).

> **Definition 2**. A number $n$ is **perfect** if 
> $\sigma(n)=2n$.

Notice that $\sigma(n)$ is **multiplicative**, meaning that for positive
integers $m$ and $n$, if their greatest common divisor is $1$, then 
$\sigma(mn)=\sigma(m)\sigma(n)$.

## Creating Perfect Numbers

> **Theorem 3**. An even number is perfect if and only if it is 
> of the form 
> $2^{p-1}(2^p-1)$, where 
> $p$ is a prime and 
> $2^p-1$ is a prime.

*Proof.*  
To prove this, we can just use the formula for 
$\sigma(n)$. Note that $n$ is already in its factored form, as we assumed
$2^p-1$ is a prime. Therefore, 

$$
\begin{align*} 

\sigma(n) &= \frac{2^{p-1+1}-1}{2-1}\cdot\frac{(2^p-1)^{2}-1}{(2^p-1)-1} \\
&= (1+2^{p}-1)\cdot 2^p-1\\
&= 2^p(2^p-1) \\
&= 2(2^{p-1}(2^p-1)) \\
&= 2n.
\end{align*}
$$

As desired. More interestingly, the converse of the claim is also true. 
That is, all even perfect numbers must be of the form $2^{p-1}(2^p-1)$.

To show this, we will use a proof by contrapositive. Assume that $p$
is prime, but $2^p-1$ is not. As a consequence of $\sigma$ being 
multiplicative, we can write 

$$ 
\begin{align*}
\sigma(2^{p-1}(2^p-1)) &= \sigma(2^{p-1})\sigma(2^p-1) \\
&= 2^p\cdot\sigma(2^p-1)
\end{align*}
$$

We aren't actually going to calculate $\sigma(2^p-1)$, we just need 
to have a bound that shows that it cannot be a perfect number anymore. 

Notice that $\sigma(2^p-1)$ not being prime means that it has more than
two factors. It has factors $1,2^p-1$ (all numbers do), and has some
mysterious other factor $q > 1$. However, the sum of these is 
$\sigma(2^p-1) \geq 1+2^p-1+q = 2^p+q$. Plugging this back into the equation,

$$ 
\begin{align*}
2n=\sigma(2^{p-1}(2^p-1)) &= 2^p\cdot\sigma(2^p-1) \\ 
&= 2^p\cdot(2^p+q) \\ 
2n = 2^{p}(2^p-1) &< 2^p\cdot(2^p+q)
\end{align*}
$$

So the sum of divisors will always be more than $2n$. This means that the
number cannot be perfect, finishing the proof.
$\blacksquare$

### So we can create as many as we want right?

Probably not, or possibly yes. There are two conditions for generating
these perfect numbers. 

1. $p$ must be prime. There exist infinitely many primes (credit to Euclid), so we don't have to worry about limitations with finding prime numbers.
2. However, $2^p-1$ also being prime is an issue. These numbers are called the **Mersenne primes**. The thing is, it's an unsolved problem as to whether or not there are an unlimited amount of them. 

The Mersenne prime condition limits whether or not we can prove 
there are infinitely many perfect numbers.

## Bonus: Odd Perfect Numbers?

An open problem in math is whether odd perfect numbers exist or not. 
While we have not proof they don't exist, numbers have been checked 
to [very high values](https://www.lirmm.fr/~ochem/opn/opn.pdf)
with no perfect odd numbers.
In fact, there are [a lot](https://en.wikipedia.org/wiki/Perfect_number#Odd_perfect_numbers) of properties (that I
would recommend checking out, they get very specific) that an odd perfect
number must satisfy, but we still have yet to find an example or a 
proof showing that it does not exist. 
