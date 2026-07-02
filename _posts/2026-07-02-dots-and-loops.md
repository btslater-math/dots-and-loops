---
layout: post
title: "Some Thoughts on the Explicit Kervaire Invariant 1 Problem"
date: 2026-07-02
---

# Introduction

The [Kervaire Invariant One Problem](https://arxiv.org/pdf/2412.10879) is, depending on one's personal taste, a homotopy-theoretic
problem with applications to smooth manifolds, or a manifold-theoretic problem that can be attacked using tools from homotopy theory.
The homotopy-theoretic version is best suited to actually solving the problem (since it is easier, though not by much,
to work with algebraic objects than geometric ones), whereas the differential-topological version is better, though not by much,
for motivating the problem. Here are, roughly, the two ways of phrasing the classical problem:

**Kervaire Invariant One Problem (Homotopy Theory Version)**: For which values of $j$ do the elements $h_j^2$ on the $E_2$-page of the 
Adams Spectral Sequence survive to the $E_\infty$ page?

**Kervaire Invariant One Problem (Manifold Theoretic Veresion)**: For which dimensions $n$ do there exist framed $n$-manifolds $M$ which
cannot be transformed into spheres via surgery? 

**Answer**: In the following dimensions: $2, 6, 14, 30, 62, 126$. 

Basically, such an $n$-manifold exists if and only if there is an element $h_j^2$ in $\pi_n(\mathbb{S})$, the stable homotopy groups of spheres.
This immediately rules out all dimensions not of the form $2^{j+1}-2$. The dimensions *not* of this form have been handled using homotopy theory. For 
example, Hill-Hopkins-Ravenel [proved](https://arxiv.org/pdf/0908.3724) that the elements $h_j^2$ vanish after $h_6^2 \in \pi_{126}(\mathbb{S})$, 
using techniques in equivariant homotopy theory; Lin-Wang-Xu [resolved the last case](https://arxiv.org/pdf/2412.10879) by means of explicit ASS 
calculations, which I think is how the 30- and 62-dimensional cases were solved as well. 

These homotopy-theoretic proofs guarantee that Kervaire-Invariant-One framed manifolds exist, but do not produce explicit examples. Such examples
should be abundant - the Kervaire Invariant is a group homomorphism from "manifolds up to cobordism" to $$\mathbb{Z}/2$$, meaning "half of all 
framed manifolds have Kervaire Invariant One" in these dimensions. But since nobody really knows all that many framed $126$-manifolds, for instance, 
this hypothetical cornucopia is of little use. We therefore have the following (hard!) problem:

**Explicit Kervaire Invariant One Problem**: For each $2 \leq j \leq 7$, give an explicit example of a $(2^j - 2)$-dimensional framed manifold
with Kervaire Invariant One.

In light of the fact that mathematics is a social endeavor, not just a rational one, what we are really asking is:

**"True" Explicit Kervaire Invariant One Problem**: For each $2 \leq j \leq 7$, give an easy-to-understand description of a $(2^j - 2)$-dimensional framed manifold
with Kervaire Invariant One.

(It is not impressive to give a construction of such a manifold unless mathematicians can convince themselves they can somehow "see" this construction,
since there is certainly a wealth of examples we cannot "see" anyway).

The 2-, 6-, and 14-dimensional cases are easy to solve on the manifold-theory side: take, for instance the manifolds $S^1 \times S^1, S^3 \times S^3, S^7 \times S^7$
with certain framings. You can probably see that these have the desired properties through differential topology. Or, you can use the [Pontryagin-Thom Construction](https://math.uchicago.edu/~may/REU2018/REUPapers/Slaoui.pdf)
to convert the elements in $\pi_*(\mathbb{S})$ to stably framed cobordism classes of manifolds. Then it's clear that $h_1^2, h_2^2, h_3^2$ are 
detected by the squares of the Hopf maps; since the P-T construction takes a map of spheres to one of its smooth fibers, and since the fibers
of the Hopf maps are $S^1, S^3, S^7$, we get the explicit examples almost immediately. 

Unfortunately, the classes detected by $h_4^2, h_5^2, h_6^2$ are not necessarily squares of anything, since $h_4, h_5, h_6$ do not survive the 
tribulations of the ASS. So we need to be more inventive. The only one of these cases which has been solved is the $n=30$ case, due to Jones. [Here](https://www.sas.rochester.edu/mth/sites/doug-ravenel/otherpapers/jones2.pdf)
is a presentation he made, which goes over the problem in great detail). 

**Jones' Manifold**: Let $Y$ be the surface of genus $5$. Let $D_8$ be the dihedral group of order $8$, which acts on $Y$ like a "fidget spinner." We also have
a $D_8$ action on $Y \times S^7 \times S^7 \times S^7 \times S^7$, where $D_8$ acts on $Y$ as just described, and permutes the four copies of $S^7$ 
in the usual way. Let $M = (Y \times S^7 \times S^7 \times S^7 \times S^7)/D_8$. Then $M$ has a framing of Kervaire Invariant One. 

Jones' paper is found [here](https://webhomes.maths.ed.ac.uk/~v1ranick/papers/jones1.pdf). 

Now, various great topologists have tried their hand at solving the Explicit Kervaire Invariant One problem, and with a bit of googling you can find the thoughts of
Atiyah, for instance. Here are *my* thoughts, inspired by Jones' example. 


# Technique 1: Toda Brackets

[Zhouli Xu](https://sites.google.com/view/xuzhouli) suggested this one to me. In addition to familiar operations of addition and multiplication, the stable
homotopy groups of spheres $\pi_n(\mathbb{S})$ have a family of more exotic operations known as [Toda Brackets](https://ncatlab.org/nlab/show/Toda+bracket). 
For example, given classes $\alpha, \beta, \gamma$ such that $\alpha \beta = 0$ and $\beta \gamma = 0$, one can compute the bracket $\langle \alpha, \beta, \gamma \rangle$. 
This is (roughly) given by $\alpha B + A\gamma$, where $B$ is an explicit null-homotopy of $\beta \gamma$ and $A$ is an explicit null-homotopy of $\alpha \beta$. 
(Cf. Massey Products. A nice exposition of the three-fold Toda bracket is found in Mosher and Tangora's excellent book, although I'm still looking for a good
source on higher Toda brackets)! Since $\pi_n(\mathbb{S})$ is isomorphic (as a ring) to the framed cobordism ring $\Omega_{fr}$, we can construct
similar Toda Bracket operations on $\Omega_{fr}$, and then hope that these correspond to some meaningful geometric operation. It is not hard to 
see this hope realized:

## The Manifold Threefold Toda Bracket
Let $M_1, M_2, M_3$ be smooth framed manifolds, such that $M_1M_2$ and $M_2M_3$ are both framed-nullbordant. Let $W_{12}$ and $W_{23}$ be framed manifolds 
such that $\partial W_{12} = M_1\times M_2$ and $\partial W_{23} = M_2 \times M_3$ (both with the correct framings). Then the Toda Bracket $\langle M_{1}, M_2, M_3 \rangle$
is obtained by gluing together $M_1 \times W_{23}$ and $W_{12} \times M_3$ along their mutual boundary $M_1 \times M_2 \times M_3$. 

Easier said than done. Finding explicit nullbordisms seems pretty much impossible when the manifolds have any complexity, and working out the gluing seems
a bit tricky as well. On the other hand, Jones found his manifold by considering a four-fold Toda bracket of $\sigma$'s and $2$'s, so there might be something 
to this.

The two ways to do it are either: take a high-arity bracket of simple terms or take a low-arity bracket of elements in higher stems. A recent [preprint by Minami](https://arxiv.org/pdf/2511.16121)
gives many explicit representatives of cobordism classes corresponding to various homotopy classes of maps, which might be a good starting point, but finding the nullbordism 
in this case seems tricky (and like more of a differential topology problem than an algebraic topology problem). On the other hand, even identifying
an appropriate high-arity bracket seems annoying (and I don't know what techniques exist for this sort of thing). 

# Technique 2: ASS on the Cobordism Side

At the UCLA Algebraic Topology arXiv seminar last quarter, Yuxuan Li (from Tsinghua, but he might not have a personal website) gave a talk constructing an 
Adams Spectral Sequence on the cobordism side using resolutions of Thom spectra. This approach has a geometric interpretation in terms of manifolds with corners. 
I can imagine a "geometric Adams Spectral Sequence" whose terms and differentials can be described in manifold-theoretic (or manifold-with-corners-theoretic) language,
and which is isomorphic to the usual Adams Spectral Sequence (or, if not isomorphic, at least has the same bigrading). If we could then identify these terms
geometrically - with a geometric version of the May spectral sequence, for instance - then we might be able to describe a term on the $E_1$ page as a product of 
accessible objects, and then "trim it down." I talked to Yuxuan about this, though, and he didn't seem to think it would work. 

# Technique 3: An Equivariant Approach

The $D_8$ action in Jones' construction seems very conspicuous to me, especially in light of the current surge in interest in equivariant homotopy theory. 
My dream scenario is that $Y \times (S^7)^4/D_8$ can be seen to correspond to the $D_8$-manifold $Y \times (S^7)^4$ in some $D_8$-equivariant homotopy 
groups, ideally with a map to (although at least we'd have a map from) $\pi_n(\mathbb{S}$. (Best of all possible worlds: these homotopy groups are just $\pi_n^{D_8}(\mathbb{S})$.
In this case, we might be able to see this $D_8$-manifold as a product of simpler $D_8$-equivariant classes - which would suggest that $G$-equivariant homotopy
groups might allow us to see the "higher" algebraic structure of $\pi_n(\mathbb{S})$ on the level of ordinary algebra. A [recent preprint](https://arxiv.org/pdf/2503.20818)
of Williams proves the equivariant version of the Pontryagin-Thom theorem, but I haven't thought about it enough to see if it does the trick.

# Conclusion... for now.

There are other approaches out there, but these are the three I can call my own. If I think of more, I'll update the article. 


