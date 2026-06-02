---
layout: post
title: "The Name of the Rows"
date: 2026-05-15
---

I'm currently teaching (well, teacher's-assisting) UCLA's Math 115A, a first course in abstract
linear algebra. This has been a lot of fun, but it's also made me aware of a conceptual distinction
which, despite being central to my understanding of math, I find very difficult to explain. This
is the distinction between a mathematical object (in this case, a vector) and its representation 
(a column vector).

Let's briefly recall the definitions, or at least the ideas of them. A **vector space** $V$ is a 
set $V$ (whose elements we usually call vectors), with two operations (addition and scalar[^1] multiplication),
along with a "zero vector" $0$, which has the property that for any other vector $v \in V$, $0 + v = 0$.

The common first examples are the Euclidean plane and 3-dimensional Euclidean space. In a high school
physics class, you are taught to think of the vectors in these spaces as "arrows:" you add them "tip-to-tail,"
and perform scalar multiplication by adjusting the length of a vector (while keeping it pointed 
in the same direction).

Once we shift to the abstract point of view, we are trained to regard this picture with arrows as 
childish.[^2] (It is even a bit embarassing to say phrases like "tip-to-tail" out loud). And to a certain
extent, I am in favor of this shift in attitude. After all, even many finite-dimensional vector spaces
have no obvious description in terms of "arrows" - the space of solutions to a second-degree 
homogeneous ODE with constant coefficients, for example - to say nothing of infinite dimensional 
spaces. That said, these pictures have an advantage, which is that they give us a way to specify
a vector without naming it. 







[^1]: Technically, to make complete sense of this, you need to specify the field in which these scalars live. 

[^2]: There is actually a mature way to think of vectors as arrows: if $V$ is a vector space over the field $F$,
then a vector $v \in V$ is just a linear map $v: F \to V$, i.e. an "arrow" in the category of $$F$$-vector spaces.
