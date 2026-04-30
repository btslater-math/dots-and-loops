---
layout: post
title: "Dots & Loops"
date: 2026-04-29
---

Welcome to **Dots & Loops**, a blog about topology, algebra, miscellaneous mathematical topics, and 
maybe miscellaneous non-mathematical topics. For those who managed to find this page without knowing 
me already, I'm [Ben Slater]({{btslater-math.github.io}}), a PhD student at UCLA working in algebraic 
topology. 

I'll be making two types of posts here. The first are aimed at a general audience, with less mathematical 
background than me. I often get asked (by family, friends, strangers at parties...) what I'm working on,
but even the least-technical explanations I can think of require a fair bit of background. You could 
say that the point of these posts is to **loop** laypeople in on what topology - and higher math in 
general - is all about. The second are aimed at people with exactly the same mathematical background 
as me: homotopy theory is a broad field, and I find that putting my thoughts into writing is the best 
way for me to connect the **dots**.

But that's not why the blog is called [Dots & Loops]({{https://www.youtube.com/watch?v=vbeJ4-OMorU}}).
So for the inaugural post, I thought I'd give a quick introduction (for a general audience) of the first 
two tools one learns in algebraic topology: $\pi_0$ and $\pi_1$, which (roughly speaking) measure dots 
and loops.


## What is algebraic topology?

Well, I'll save a full explanation for a future post, but here's the basic idea. Since ancient times, 
mathematicians have been interested in studying shapes. But mathematics is also about precise reasoning, 
and to reason about a shape you need a precise description of it.

The best way to describe a shape is to draw it on a piece of paper, but this only works for low-dimensional
shapes. Lines, circles, triangles, squares, and so on are easy; cubes and tetrahedra aren't too bad once
you know how to draw them; spheres, tori, and other curvier "surfaces" take some real artistic talent; and
you can forget about drawing 4-dimensional shapes (let alone the [62-dimensional beasts]({{https://en.wikipedia.org/wiki/Kervaire_invariant}})
I was trying to tame last fall). 

The second best way to describe a shape is to graph it with a set of equations; this is the purview of a 
field called [algebraic geometry]({{https://en.wikipedia.org/wiki/Algebraic_geometry}}). The advantage of this 
approach is that it works equally well in all dimensions. For example, a circle is given by the equation
$x^2 +y^2 = 1$, a sphere in 3 dimensions is given by $x^2 + y^2 + z^2 = 1$, a sphere in 4 dimensions is 
given by $x^2 + y^2 + z^2 + w^2 = 1$, and so on until we run out of variable names. The *disadvantage* is 
that most shapes can't be described in equations this way. Take out a pen and a piece of paper and draw a 
shape right now; there is literally zero chance that your shape can be described in equations. In fact 
(for reasons relating to [cardinality]({{https://en.wikipedia.org/wiki/Cardinality}}) (that I won't 
get into here, but which you can think about if you have enough background), there is *no chance that your
shape can be precisely described at all*. So we can give up on ever proving mathematical results about 
most specific shapes.

But that doesn't mean we can't study these shapes at all. The basic idea behind the field of topology is 
to give descriptions of shapes which, though not "precise" enough to allow us to exactly recreate a shape
from its description, are at least precise enough for us to reason about. So, rather than thinking about 
a perfect sphere, we speak of a "topological sphere," which captures some of the properties of a sphere, but 
(importantly) not its absolute roundness and symmetry. Every day objects which a topologist would call 
"spherical" include (but are not limited to): metal balls, basketballs, oranges, apples, grapes, lemons, six-sided
dice, and pencils. (To be a bit more precise, I mean the *surfaces* of these objects, not their interiors).

The problem is that because our categories of shapes are so broad, it can be difficult to determine which 
category a shape should actually be placed into, or when two shapes are "topologically the same." For example,
is the chair I'm sitting in "spherical?" What about my stove? And that's just shapes we can see - it gets
much worse when we only have an abstract description of the shape (such as "the unique double-cover of the 
space of all orientation-preserving isometries of $n$-dimensional space"). 

The goal of algebraic topology is to develop tools for determining when two shapes are different.

## Dots

So, how can we identify when two shapes are different? Here's a warmup: Why are two circles (O O) a different
shape from just one circle (O)? Well, the first has two pieces, and the second has just one; that's good enough
for natural language, but not for proving theorems. So how can we make it more precise?

Suppose you were an ant living on a circle - and I mean just the rim of it. A map of your world would look like 

$$\bigcirc$$

This makes navigation easy enough! Suppose you wanted to visit your aunt. You could mark your house with a red 
dot (a "base point"), and your aunt's with a black dot. You can always find a path between the two points by going around the 
circle clockwise (or [auntie-clockwise]({{https://en.wiktionary.org/wiki/anticlockwise}})), which you can 
represent by just highlighting part of the circle. This is true no matter where on the circle you put the black dot. 

Now, suppose your circle-world had a circle moon. Now the map might look like

$$\bigcirc \,\,\,\,\,\, \circ$$

Suppose your house is still on the big circle, but now your aunt lives on the little circle. The path between 
them now passes through empty space. Without a rocket, you have no way to visit your aunt.

Observe that there are now two types of points: those on the big circle, which you can reach on foot, and 
those on the little circle, which you cannot. Of course, if you were already on the little circle, you 
could reach any other point on the little circle, but none of the points on the big circle. 

We can do the same thing with any shape $X$: we divide it into "path components," based on which points can be reached
"on foot" from which other points. That is, to determine if two points $P$ and $Q$ should be on in the same 
component, we place one dot at $P$ and one dot at $Q$, and see if there is a path between them that doesn't
leave the surface of $X$. To be technical about it: we say that $P$ and $Q$ are on the same 
path component if there is a continuous function $f: [0,1] \to X$ such that $f(0) = P$ and $f(1) = Q$. The set
of path components of $X$ is called the "zeroth homotopy group of $X$," denoted $\pi_0(X)$, but for the 
purposes of understanding the name of the blog, you can think of it as measuring the types of "dots" in $X$. 

## Loops

We now have a way of determining how many pieces a shape has. But many shapes come in just a single piece, and are
still clearly different. For example, what's the difference between a circle and, say, a sphere? 

