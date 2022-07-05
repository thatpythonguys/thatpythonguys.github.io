---
author:
  name: Pramana
title: What is a basis? It's complicated...
date: '2022-07-04 14:06'
categories:
  - Fun
tags:
  - topology
  - free groups
  - linalg
permalink: /Jul4th/
math: true
img_path: /assets/img/
pin: true
---

Simply put, a basis in mathematics is the simplest way to represent something, be it a set, object, anything! However, in looking into how several fields of mathematics define a basis, it can turn out very different, and it is entirely dependent on the mathematical idea that the field is studying. So lets start with the basis that most entry-level mathematicians should be familiar with.

# Basis in Linear Algebra

**Linear algebra** is based on the idea of a **vector space**, which has two components: a field of **sclalars** and a set of vectors $\mathbb{V}$. Vector spaces must be closed under **scalar multiplication**, which means that we can multiply any scalar by any vector and define it as scaling up. They are also closed under **vector addition**, so the sum of any two vectors should also be in the vector space. 

The typical introduction to what a basis is in linear algebra is that any linear combination of the set of bases *uniquely* creates every single element of the vector space. Notice how linear combinations make use of the fact that we have scalar multiplication and vector addition. Without that, we would be screwed, because there would be no way for our scalars and vectors to interact!

There's also one more fact about the basis of a vector space; all the vectors have to be **linearly independent**. For vectors to be linearly independent, there should be no way to get one vector from a linear combination of the others.

> **Example 1.** It should feel obvious that $\begin{bmatrix}1 \\ 0\end{bmatrix}$ and $\begin{bmatrix}0 \\ 1\end{bmatrix}$ are linearly independent. Formalizing that "obvious" feeling is part of the job of linear algebra.

The reason we mention this is because when using a basis, we generally want to have as few of them as possible. Why? Because if we weren't seeking the minimum, then we could have arbitrarily large bases. The minimum number of bases of a vector space doesn't change. This type of value that doesn't change, for example, you always need $3$, no less, no more, to define $\mathbb{R}^3$, also known as space. This property is called an **invariant**, and means that we can use it for really useful concepts like **dimension**, which simply is the number of bases needed to define the vector space. It would be weird to say that *a* dimension of $\mathbb{R}^3$ is $3$, does that mean there are others? No, we know that *the* dimension of $\mathbb{R}^3$ is $3$. 

# Basis in Topology

I'll give an overview of what a topology and a topological space are.

> **Definition 1.** Given a set $X$, a **topology** is a set $\mathcal{T}$ that contains subsets of $X$.

As a side note, anytime I use $\mathcal{THIS}$ $\mathcal{FONT}$ when talking about a set, it means a set that contains sets within it, like a meta-set, or, more commonly said, a **collection of sets**. Continuing on...

> $\mathcal{T}$ must satisfy the following properties:
> 1. The empty set and the whole set $X$ must both be in $\mathcal{T}$
> 2. The collection is closed under arbitrarily many unions. 
> 3. The collection is closed under finitely many intersections.

To clear up the second and third requirement, the second says that if we take any number of sets in $\mathcal{T}$ and find the union of them, they should also be in $\mathcal{T}$. The third statement says that the same applies for intersections, but only finitely many (this is to avoid some bad contradictions). 

We call $(X,\mathcal{T})$ a topological space is $\mathcal{T}$ is a topology on $X$. Here's an example to build intuition:

> **Example 2.** Define the **particular point topology** on a set $X$ with an element $p \in X$ as follows:
>
> $$ \mathcal{T}_p := \{ U \subseteq X \mid p \in U \}\cup \{ \emptyset\}.$$
>
> Or put simply, the set of all subsets of $X$ that have $p$ in them. We also have to include the empty set due to the definition of a topology.

> **Exercise.** Show this is a topology.

So what makes a basis on this type of space? Well if we have a basis, we should be able to form every element in the topology just by using the basis and the properties that a topological space has. 

> **Definition 2.** A basis of a topology $\mathcal{B}$ is a collection of subsets of $X$ such that
> 1. $\mathcal{B}$ covers $X$
> 2. Given $B_1, B_2 \in \mathcal{B}$, for all $x \in B_1 \cap B_2$, there is $B_x \in \mathcal{B}$ such that $x \in B_x \subseteq B_1 \cap B_2$.

The reason we need the first requirement should be obvious. The topology contains $X$, the full set, so if $\mathcal{B}$ did not cover all of $X$, then we could not make a union and get the full set $X$.

The second requirement says given two subsets in $\mathcal{B}$, for all elements $x$ in the intersection of those subsets, there is another basis element that is contained in the intersection and has $x$. The reason that we need this is not entirely clear, but I encourage looking up proofs for why this is required to have a topology (hint: it mainly has to do with the intersection property of topologies).

Bases in topology don't really have this size factor that linear algebra has, mainly because the bases of topologies tend to be infinite. However, they can be used in other ways to show, for example, that one topology is contained in the other (can you guess how?).

# "Basis" in Abstract Algebra

This summer I've been doing research work on geometric group theory, which required me to learn about combinatorial group theory. I'm going to explain the basic motivations that led mathematicians to choose to continue research in those fields. As a reminder, a group is defined as follows:

> **Definition 3.** A set $S$ of elements is a **group** if there is:
> 1. A **binary operation** $\cdot$ that takes two elements of the set and sends the to another element: $s_1\cdot s_2 = s_3 \in S$.
> 2. **Associativity**, meaning that $(a\cdot b)\cdot c = a\cdot (b\cdot c)$. Basically, we can ignore parenthesis; the order that we do things doesn't matter!
> 3. The **identity** is an element called $1_G$ such that any element combined with $1_G$ gives back that element.
> 4. Every element has **inverses**, such that $a\cdot a^{-1} = a^{-1}\cdot a = 1_G$.

To help build the idea of a "basis" in a group, I'll start with a simpler concept, cyclic groups.

## Cyclic Groups

The idea with a cyclic group is to choose one element of the group, say $a$, and let it interact with only itself (and its inverse). We call this the **cyclic group**, denoted $\langle a \rangle$, or the **group generated by $a$**. What does it look like?, kind of like this:

$$ \langle a \rangle = \{ \cdots, a^{-2}, a^{-1}, 1_G, a, a^2, \cdots\}.$$

Imagine putting $a$ in a box and shaking it until we had all possible products of $a$ (and $a^{-1}$, which we know exists by the definition of a group).

Now I'll ask a weird question: how could we make it finite? Say we wanted to make the group only have $7$ elements just for the kick of it. Well how about this: once we get to $a^7$, we tell the group to stop and turn around back to $1_G$, the identity. What about the negative values? Well notice that 

$$ a^{-2} = a^{-2}(1_G) = a^{-2}(a^7) = a^5,$$

so really we can just call $a^{-2}$, $a^5$. We can call this "rule" $a^7=1_G$. What we've just created is called a **relator on $G$**,
and $a$ is called a **generator of $G$**. We can combine these to get the **presentation of $G$**. For example, we would denote the group we created above as

$$ G = \langle a \mid a^7 = 1_G \rangle = \{ 1_G, a, a^2, \cdots, a^6\}.$$

## Presentation of Groups

In fact, all groups have a presentation. We give them some generators and then add some "rules" (or relators) that they must follow (aside from the regular rules of all groups), and then it can be used to represent any group!

This is the best form of creating a "basis" for a group. 

> **Example 3.** Here's a presentation for $\mathbb{Z}^2$, or all 2D points that have integer coordinates:
>
> $$ \mathbb{Z}^2= \langle a = \begin{bmatrix}  1 \\ 0\end{bmatrix}b= \begin{bmatrix}  0 \\ 1 \end{bmatrix} \mid ab=ba\rangle.$$
>
> I should note that $ab = ba$ is actually a necessary relator we need to mention. See, nowhere in the group definition does it say that groups elements have to commute. This rule says they do. Groups that also commute have a special name: **Abelian Groups**.

## Alien Math

![Glep](glep.jpg){: width="300" height="200" }
_Figure 1: Glep_

The alien mathematician Glep comes up to you, and explains how he also knows group theory (which the aliens call Glepglop theory in honor of him) and created his definition of $\mathbb{Z}^2$ (which he calls $\overline{\overline{\mathfrak{REAL}}}$), 

$$ \overline{\overline{\mathfrak{REAL}}}= \langle a = \begin{bmatrix}  1 \\ 0\end{bmatrix}b= \begin{bmatrix}  1 \\ 1 \end{bmatrix} \mid ab=ba\rangle.$$

Well there's nothing wrong! This works just as fine as the other definition. So now suppose that we weren't told that both of these groups create $\mathbb{Z}^2$. How would we know that Glep came from a different cultural background and was creating the same group in a different way? How do we know 

$$ \langle a = \begin{bmatrix}  1 \\ 0\end{bmatrix}b= \begin{bmatrix}  99 \\ 1 \end{bmatrix} \mid ab=ba\rangle, $$

also works? (check it, it does). While it may seem easy to tell for an easy group like $\mathbb{Z}^2$, groups can get very complex ([citation](https://en.wikipedia.org/wiki/Monster_group)), and we've found there is no general rule to telling us that two representations are the same. However, we can get pretty close. Our means of telling the Glep that we really are talking about the same group drove study of both combinatorial and geometric group theory.