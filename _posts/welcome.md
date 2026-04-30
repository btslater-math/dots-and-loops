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
still clearly different. For example, what's the difference between a circle and, say, a figure 8? 

$$\bigcirc 8$$

An ant living on a circle doesn't have many routes for an afternoon stroll. It can walk clockwise or counterclockwise, 
maybe making a few complete laps in each direction, before eventually returning home to where it started. This still 
leaves plenty of routes, but just as we reduced the infinity of points on the circle to a single "path component before,"
we can define a relation which makes many of the paths on a circle the same.

Imagine our ant has a poor sense of direction, and decides to keep track of the route home by unspooling a thread
as it walks. Suppose it walks halfway around the circle, and then turns back. When it gets home and reels the thread in,
it has no trouble collecting the entire thing. But now suppose it makes a complete lap clockwise. When it tries to reel the thread
in this time, the string will get caught around the planet. If it goes a half lap further and then turns back, then it will
be able to reel in the thread up to where it was after just a single complete lap, but no tighter. But if it now goes 
all the way around the planet *counterclockwise*, the thread can once again be spooled back up. 

In other words, as far as the thread can tell, the ant's route can be described quite easily: either it walked around the circle
a certain number of times clockwise in total, or it walked around a certain number of times counterclockwise in total. (That "certain 
number" can, of course, be zero). Thus, each path can be represented with a positive or negative integer.

This collection of "loops" which can be drawn on a shape $X$ is called its "first homotopy group" or "fundamental group," denoted
$\pi_1(X)$. So, $\pi_1(\bigcirc) = \mathbb{Z}$. ($\mathbb{Z}$ is just fancy notation for the set of integers). 

If the ant lives on the node of a figure eight, things are quite different. Now, it has two loops it can walk around: either the top 
loop or the bottom. If it walks (with its thread) clockwise around the top loop and then counterclockwise around the bottom loop, it 
won't be able reel the string back in. In fact (you'll have to take my word for this), even if it then goes back around the top 
loop counterclockwise, it *still* won't be able to reel the thread in!. To untangle the thread from this state (clockwise around the 
top, then counterclockwise around the bottom, then counterclockwise around the top), it would need to go over the two loops in reverse
order, undoing its progress each time (so, clockwise around the top, then clockwise around the bottom, then counterclockwise around the 
top). On the other hand, if it just goes clockwise around the top loop, it can fix the string by simply going counterclockwise around 
the top loop, just like before. The ant on the figure 8 therefore has many more routes for its stroll: it can go any number of times 
around the top loop, then any number of times around the bottom, then any number of times around the top, then any number of times 
around the bottom... and it can do this as many times as it wants (although it has to stop eventually). 

Thus, $\pi_1(8)$ is much larger than $\pi_1(\bigcirc)$. (For those with some group theory knowledge, $\pi_1(8)$ is the "free product"
$\mathbb{Z} * \mathbb{Z}$). 

On a more technical level, a loop on $X$ can be described as a continuous map from the circle to $X$. Two such loops, 
$f, g: \bigcirc \to X$, correspond to the same loop in $\pi_1$ (i.e. look the same after "reeling in the string" as much as possible) if
there exists a map $h$ from the cylinder $\bigcirc \times [0,1]$ to $X$, such that $h$ looks like $f$ on the bottom of the cylinder 
and like $g$ on the top (i.e., $h(\theta, 0) = f(\theta)$ and $h(\theta, 1) = g(\theta)$).

## So, there you have it

$\pi_0$ and $\pi_1$, Dots and Loops... of course, there are many more weapons in the topologist's arsenal, which I'll probably
give an introductory account of at some point. But I think this is enough for tonight.
