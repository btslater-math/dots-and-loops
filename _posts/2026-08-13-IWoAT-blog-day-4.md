---
layout: post
title: "The IWoAT Blog: Day 3"
date: 2026-08-12
---

Short post day, partly because I was out late exploring Beijing, partly because I didn't
really understand today's talks, which were a massive step up in technical complexity from
yesterday's lectures. In fact, I think there are only two things I can sort of point to having
learned today.

## A different view on vector bundles

Traditionally, we think of a vector bundle on $X$ as a map $\xi: E \to X$ which admits a local
trivialization. This definition is "correct" in the sense that it gives the correct result, but
it obscures the condition of the individual fibres a bit. We know that the fiber $E_x$ (for $x \in X$)
is a vector space, and that different fibers are different (but isomorphic) vector spaces. Since
these are just abstract vector spaces, there is *a priori* no way to compare them - and indeed
we don't get to compare them at all except by picking a local trivailization and then insisting
that the fibers of a trivial bundle are actually "the same vector space." Even if we do this,
we are not really comparing these vector spaces, just fixing an automorphism.

The perspective on vector bundles presented in today's first talk on Thom spectra fixes this
issue. Rather than viewing a vector space as a map $E \to X$, we view it (as I understand it)
as a map from $X$ to the $\infty$-groupoid of vector spaces isomorphic to $V$. Now we actually
can compare different fibers, since a path in $X$ corresponds to a path in the aforementioned
$\infty$-groupoid (assuming I've understood this correctly). Neat!

It'll be some time before I understand how the notion of Thom spectra applies to arbitrary 
rings.

## Topological Invariants

The point of "brave new algebra" is that certain topological spaces can be made to act
a bit like the rings, modules, and algebras we know and love from classical abstract algebra. 
I don't totally understand why we should do this, but I guess it's cool that we can. Anyway,
a major theme in today's talks was generalizing classical algebraic invariants to these 
ring/module/algebra spectra. For instance, we replace Hochschild Homology with Topological 
Hochschild Homology. 

Without knowing a bit more of the research landscape, I couldn't figure out the motivation
for these constructions from the talk. Consequently, I retained very little. But I was struck
by what is, in retrospect, an obvious trick: just as the inputs of these invariant-functors
have been upgraded from algebraic objects to topological ones, so too have the *outputs* been
upgraded. 

Slowly but surely I'm starting to piece together the operad/higher algebra picture. The advantage 
of these ring/module/algebra spectra is not just that they are graded (why did I ever think it was?) 
but that they intrinsically store homotopical data. But I'm still waiting to see an application 
where this homotopical data comes in handy.


That's what I could extract from today's talks. I am still sopping after drowning in adjectives
applied to $\infty$-categories and the functors between them, also drenched in sweat from several
hours walking around in August. Hoping tomorrow's lectures - which seem like a return to the more
"computational" picture I'm familiar with - will be more accessible for me. 


