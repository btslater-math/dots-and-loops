---
layout: post
title: "The IWoAT Blog: Day 2"
date: 2026-08-11
---

Day 2 of the Summer School seems like it will wind up having been the "boring day;" lots of talk about the differences between 
specific models of the stable category (which, admittedly, I thought was going to be the whole conference) and not a whole lot
of "actual math." 

The basic philosophical idea seems to be this: there are various "point-set level" model categories whose homotopy categories are all equivalent
and capture the "stable homotopy theory" we expect. Each of these point-set categories captures some of the properties of the 
homotopy category, but none captures every nice property we want. Often one needs to work at the point-set level in order to 
obtain finer control over constructions in the homotopy category--this seeems to be important when pinning down the associativity
and commutativity axioms in "brave new algebra," for instance--and different model categories provide different levers with
varying degrees of precision. So if you ever need to work seriously with the mechanics of spectra, you need to be comfortable
working in a variety of model categories (whereas if you are more interested in computations you might never need to think about 
any of them). 

Here are the properties we want our model category $M$ to have - Lewis showed you can't have all at once, but you can get a few: 

(I'm paraphrasing a bit from the chapter in the course textbook)

- (A1) There exists a symmetric monoidal smash product
- (A2) There is an adjoint pair $\Sigma^\infty: Top_* \leftrightarrow M : \Omega^\infty$
- (A3) $\Sigma^\infty$ commutes with smash product (at least up to natural transformation)
- (A4) $\Sigma^\infty S^0$ is the unit for the smash product, and "$\eta$ is compatible with the unital isomorphism"
- (A5) There is a natural weak equivalence between $\Omega^\infty \Sigma^\infty X$ and $QX$ (here $QX$ is the fibrant replacement)

Now, let's meet the models!

## Bouslander-Friedland Spectra

This is the "classical" version: a B-F spectrum is a sequence of spaces $X_n$, with structure maps $\Sigma X_n \to X_{n+1}$. This
model has at least two advantages: first, it is (relatively) easy to think about; second, it is clear that it is a "stable" version
of the homotopy category. Clear, that is, once we have defined the morphisms in this category, and this is a major disadvantage of
the model. If you naively take a map $f: X \to Y$ of B-F spectra to be a sequence of maps $f_n: X_n \to Y_n$ commuting with 
the structure maps, then what you wind up with is not stable homotopy theory. For example, the Hopf map, which we certainly
expect to see in the stable homotopy groups of spheres, cannot be written in this way (at least not as a map $\Sigma \Simga^\infty S^0 \to \Sigma^\infty S^0$),
because there is no map $S^2 \to S^1$ suspending to the Hopf fibration $\eta: S^3 \to S^2$. To define morphisms, you need to use
the idea of "cells now, maps later" (as described by Adams) involving cofinal complexes, and this is a mess. (Actualy, I'm not
sure if this is fixed in other models; we didn't really talk about how to describe the morphisms in any of these categories...). That
issue is, I think, fixed if you work with $\Omega$-spectra, but that also means losing a lot of geometric meaning. Another disadvantage,
not fixed by $\Omega$-spectra is that there's no good way to form smash products on the point-set level--or rather, there are too many good 
ways. Adams describes the "handicrafted smash product," which requires a fairly involved choice of which smashand to suspend at
each level. While all of these choices turn out the same in the homotopy category, this is (apparently) not good enough when
dealing with, for instance, $E_\infty$ ring structures, where you are interested not just in whether two maps are homotopic but
also in the homotopy connecting them. 

## Diagram spectra: Orthogonal and Symmetric Spectra

A B-F Spectrum seems like a diagram, in the sense that it is a sequence of spaces, but it is not clear how to make this formal. The answer is
to consider diagrams whose shapes are already in enriched categories. In this case, B-F spectra are diagrams $\Theta \to Top_*$, where
$\Theta$ is the enriched category whose objects are natural numbers and with $\Theta(k,n) = (S^1)^{n-k}$ for $n \geq k$, and a point otherwise.
A diagram of this form is a sequence of spaces $X_1, X_2, \dots$; furthermore, we have a map $S^1 \to Hom(X_n, X_{n+1})$, which by the famous 
adjunction is the same as a choice of map $S^1 \wedge X_n \to X_{n+1}$, i.e. $\Sigma X_n \to X_{n+1}$. 

Using more sophisticated enriched categories as the shape of our diagrams allows for different categories of spectra admitting more 
natural point-set smash products. To be a bit curt: in symmetric spectra, the hom-sets in the diagram used to define symmetric
spectra look like $X^n \otimes \Sigma_n$, for $X$ an invertible object in whatever symmetric monoidal model category we are using
as a base; in orthogonal spectra, we have a category whose objects are inner product spaces and whose hom-spaces are isometric 
inclusions. 

There was a brief mention of how to use Day convolution to induce a smash product on symmetric spectra, but I didn't quite foollow
it (because I'm still not quite used to Kan extensions just yet). (You can do something analogous with orthogonal spectra0.

## $\Gamma$-spaces

I don't understand this one at all. Take $\Gamma^{op}$ to be the category of based finite sets and based functions. A $\Gamma$-space
is a functor $\Gamma^{op} \to Top_*$. Somehow, this gives us a model for connective spectra, apparently for reasons relating to
infinite loop spaces (or maybe delooping). I think we might be learning more about this tomorrow. 

## Stable Model Categories

The upshot here is that the notion of a model category $M$ being stable can be captured using only the data of $M$ - that is, 
a stable model category does not need to be a stabilization of some other category. Specifically, we can define an adjoint pair of
"suspension" and "loops" functors on $Ho(M)$ using pushouts and pullbacks of certain canonical diagrams; $M$ is stable if $\Sigma$
is a self-equivalence $Ho(M) \to Ho(M)$, in which case $\Omega$ is the inverse equivalence. This turns out to be enough to 
determine the main fact about stable categories, which is that fiber sequences and cofiber sequences "agree" (i.e. a sequence is a 
fiber sequence iff it is a cofiber sequence). In fact, if $M$ is stable, then $Ho(M)$ is a triangulated category!

More or less this is all stuff we know to be true from the original case of spectra. But it's surprising that all this is a formal
consequence from the axioms of a model category plus the condition that $\Sigma$ be an equivalence on the homotopy category. 

## Stable $(\infty, 1)$-categories.

Mostly similar stuff to the talk on stable model categories, but I really like the fundamental idea behind this model for 
spectrum. One of the famous motivations for spectra is the Brown Representability Theorem: every cohomology theory is 
represented by a spectrum, and every spectrum represents a cohomology theory. In this talk, we took †his to be the 
*definition* of spectra, first giving a purely categorical analogue of the definition of a cohomology theory in terms
of excisive functors, and then defining a spectrum to be precisely a cohomology theory. (Well, not quite, because 
these guys are valued in spaces rather than groups. So we take a cohomology theory $E$ (represented by a spectrum $E$)
to be the functor $X \mapsto Hom(X, E)$, whose homotopy groups recover what we expect the cohomology theory to be). A nice 
advantage is that you can define spectra over any pointed $\infty$-category $C$ to form the category $Sp(C)$. There's
also a universal property, although I didn't quite catch it. 

Throughout the talk the category of Anima was used in place of based topological spaces. I still don't know what Anima are,
and I haven't had a chance to find out.

## Final Thoughts

Let me end with a problem I was pondering after classes with another student:

**Question**: We know that each topological space $X$ corresponds to an $\infty$-groupoid $\Pi_0(X)$. It is apparently
also true that given an $\infty$-groupoid $G$, one can construct a space $X$ such that $\Pi_0(X) = G$. Is this construction
unique? That is, are there non-homeomorphic spaces $X, Y$ such that $\Pi_0X \cong \Pi_0Y$, where $\cong$ means on-the-nose 
isomorphism? 

I wasn't quite feeling today's lectures, but I'm really looking forward to tomorrow, when we get into more algebra. Stay tuned. 
