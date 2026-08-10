---
layout: post
title: "The IWoAT Blog: Day 1"
date: 2026-08-10
---

[Well alright](https://www.youtube.com/watch?v=F3NImB7FMz4)! It's the end of the first day of the 
2026 IWoAT summer school, and as a way to consolidate the material from the lectures in my head 
(and to give me what to do at night) I'm going to try to post blog posts on each day's material. 
These won't really be detailed lecture notes - more a summary of what I find important/interesting.
I think what I'll do is split it up talk-by-talk. 

## Program Overview 

Not much to say about this - a pretty good look at why homotopy theory, and in turn stable homotopy
theory, is a worthwhile topic to study (although it doesn't match my conception of the subject 
as well as my as-yet-unwritten blogpost about the reasons to stabilize, which I wanted to have up 
before the summer school started). Let me first say that I'm a big fan of the phrase "working to 
the left of the integers." 

One point that did jump out to me was Prof. Blumberg's discussion of the centrality of spheres to 
homotopy theory. He pointed out that the decision to build algebraic topology around spheres is 
a choice about aspects of topology we want to emphasize/care about, and this is quite true. He also 
mentioned (in response to an audience question) that while stabilizing by "inverting the spheres" 
produces a rich, meaningful theory, there is essentially no other kind of stabilization - trying to 
invert other families of spaces either kills the entire category, does nothing at all, or does the
same thing as spheres would have. He treated this as being a bit mysterious, but it really isn't surprising
to me that the spheres wind up being, in some sense, the only natural building blocks for homotopy theory.
That's because we chose to prioritize spheres (and, too, Euclidean spaces) the moment we defined the
notion of homotopy! Given maps $f, g: X \to Y$, a homotopy from $f$ to $g$ is a map $h: X \times [0,1] \to Y$.
Thus, a map from $f$ to itself is a map $X \times S^1 \to Y$. Likewise, if we study homotopies between homotopies,
we will have to consider maps $X \times [0,1]^2 \to Y$, and if all of these homotopies are "self-homotpies" we will
really have a map $X \times S^2 \to Y$. And so it goes. So there was never going to be a version of 
homotopy theory that doesn't center the spheres.

A question I was too shy to ask during the Q&A: Blumberg mentioned that one desirable property of 
the stable category is that it is "algebraic," by which he seemed to mean that it was triangulated. 
That's actually a pretty satisfying reason on its own - but just before coming to Beijing, I was reading
about monads, and now everything looks like a nail. One thing it might mean to call a category $D$ "algebraic" 
is that $D$ is *monadic*. That is, there might be some adjoint pair $F: C \rightleftarrows D : U$ such that $D$
is equivalent to the category $C^T$ of algebras over the monad $UF: C \to C$ - intuitively, this should mean
that objects of $D$ look like objects of $C$ enriched with some additional algebraic structure. Well, 
as I understand it, $\mathrm{Sp}$ is the domain of a right adjoint functor; the adjunction is $\Sigma^\infty: \mathrm{Top}_* \rightleftarrows \mathrm{Sp} : \Omega^\infty$.
Is $\mathrm{Sp}$ monadic over $\mathrm{Top}_*$? (Phrased like this there's nothing embarassing about this question. 
But it wasn't until I wrote it out just now that I knew what I wanted to ask). 

## Model Categories

This was the talk I found most interesting - model categories I had been wanting to learn about for a long time
and just never really found a good reason to learn. Here is my understanding of the motivation:

When you take a first course in algebraic topology - particularly if you learn it from Hatcher, although I think
May gets a pretty similar effect - you eventually realize that, despite the fundamental objects of study being
topological spaces and continuous maps, you hardly ever consider the actual definitions of topological spaces or 
continuous maps! Indeed, point-set topology seems to have almost nothing to do with algebraic topology, and even
the notion of "sameness" is different (homotopy-equivalence, as opposed to the point-set notion of homeomorphism). When you 
go a little deeper and learn about Puppe sequences - you really get a feel for this from Mosher&Tangora - you 
meet fibrations and cofibrations, the notions that power the various long exact sequences you learn in Hatcher. 
Indeed, out of all the many continuous maps in the category of spaces, the only ones which you really need to 
do homotopy theory are the equivalences, fibrations, and cofibrations - the rest are just flavor text.

Model Categories are therefore categories which have all the basic tools we need to do homotopy theory. Notably, 
this does not seem to include an "interval" object! A model category is a (complete, cocomplete, locally small) 
category $\mathcal{M}$, with three special classes of morphism: the "weak equivalences" $\mathcal{W}$; the 
"fibrations" $\mathcal{F}$; and the "cofibrations" $\mathcal{C}$. Naturally, these can't be completely arbitrary;
there are certain axioms they need to satisfy to make the resulting "homotopy theory" match our intuitions 
(and to ensure that it is tractable). For example, we need $\mathcal{W}$ to satisfy:

1. $\mathcal{W}$ contains all identity maps.
2. $\mathcal{W}$ is closed under retracts.
3. Let $f$ and $g$ be composable maps, $gf$ the composition. If two of $f, g, fg$ are in $\mathcal{W}$, then so's the third.

We also need the property (familiar from classical homotopy theory) that every map can be replaced (up to weak equivalence) 
by both a fibration and a cofibration. This is captured in the notion of a "weak factorization system," which also stipulates
that the fibrations and cofibrations satisfy a certain lifting property. I find this lifting property a bit mysterious - I know
it's true of ordinary fibrations and cofibrations (since this is the first result in "More Concise Algebraic Topology") but it 
seems completely ad hoc, hardly the central property of these maps. But who knows? 

Model categories turn out to admit something analogous to projective and injective resolutions; these are the fibrant 
and cofibrant replacements. I still haven't quite internalized this idea yet, but the idea is that these fibrant and cofibrant
replacements can be used to compute total derived functors (just like how projective and injective resolutions are used to 
compute derived functors homologically). A priori there may be many acceptable (co)fibrant replacements, but Quillen identified 
functorial replacements. (Here, again, I wonder if there's something monadic going on--just like how we can use the free-forgetful 
monad to get projective resolutions of modules). Crucially, we can also replace every object with a weakly-equivalent object
that is both fibrant *and* cofibrant. 

The last point, and the one that I really need to work through, is lifting model structures to diagram categories in order to compute
homotopy limits and colimits.  But it's getting late, so I'll save this for tomorrow.

## Simplicial Model Categories

The basic idea here is to consider model categories enriched in Simplicial Sets. The notion of an enriched category leads me to 
a sort of vague question:

Question: An enriched category is one whose hom-functors land in an arbitrary monoidal category $(V, \otimes 1)$. If there is
a forgetful functor $F: V \to Set$, it is natural to hope that hitting those hom-functors with $F$ should recover the hom-sets
in the "unenriched" category, whatever this means; on the other hand, not every category has an obvious forgetful functor to $\mathrm{Set}$. 
Is there an example of a $V$-enriched category $C$, where $V$ is some exotic category, such that there is no meaningful forgetful 
functor $V \to Set$ allowing us to interpret $C$ as an ordinary category? 

Anyway, the main point of this talk was to explain how to enrich a model category in Simplicial Sets. The reason to do this
is that a simplicial set structure on $Hom(X,Y)$ describes a notion of "path of morphism," "path of paths," etc. (Another
way to say this is that it gives us a way to specify higher-categorical structure). There's then an extra axiom ("SM7") that 
must be satisfied in order for te resulting enriched category to have a suitable model structure. Like the lifting properties, t
his seems quite mysterious to me, and I don't really understand what it "does." 

One obviously important idea in this talk, which I didn't quite internalize the first time around, was the construction of 
"hammock localization," which allows us to formally invert morphisms in a way that respects the entire simplicial structure.
We ended on a result which says, roughly, that the hammock-localized Hom-SSet $N(X, Y)$ is isomoprhic to the unlocalized hom-SSet 
$M(QX, RY)$ - so here is something captured by our resolutions. (I seem to recall there being an analogous result with 
localization of an Abelian category in homological algebra). 


## $(\infty, 1)$-Categories

Here's that good old Lurianic wisdom. Kabbalistic indeed! While I understand why $(\infty, 1)$-categories should be important to 
homotopy theory - since, after all, they aim to capture the different ways two maps can be "equivalent," which is exactly 
what homotopy theory does - I have to admit that in practice I still don't quite get what's going on here. I guess you really
just have to sit down with "Higher Topos Theory" and a pen and paper for a while to get a feel for it - or, more likely, you 
need to hit some problem that can only be solved using this technology. I still haven't internalized this machinery, and it 
still seems like for a lot of applications it's just more trouble than its worth. (This was the imporession I got from Blumberg
during the Q&A, anyway). 


## And that's all for the first day!

More tomorrow. 

