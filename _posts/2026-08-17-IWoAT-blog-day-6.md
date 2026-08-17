---
layout: post
title: "The IWoAT Blog: Day 6"
date: 2026-08-12
---

After a draining Friday of talks and a restorative weekend of tourism, I returned to IWoAT today 
well-rested and with my excitement for math rekindled. Today was the first day of the conference,
with four excellent talks, although I don't have much to say about any of them - the two symplectic
topology talks, while engaging, were a bit too far out of my wheelhouse for me to really have any
meaningful thoughts on, and I've seen Sihao present this project before (and read an early version
of the paper in question) so not much new there either. Mark Behrens' talk, which I had been looking
forward to after reading [Belmont and Ray's paper on the Kervaire Invariant problem at prime 3](https://arxiv.org/pdf/2507.10157),
was the most exciting of the bunch, and while the initial progress on building $BP_{\mu_3}$ is good,
it seems there's still a ways to go before it can be used to solve that remaining case of the Kervaire
invariant problem (for instance, as I understand it, we still don't know the multiplicative structure on 
the... cohomology? I don't remember), and I'd need to sit with the construction a bit longer to 
figure out if there are any accessible projects to work on.

On the half-an-hour walk back from the Peking University math building to the hotel I'm staying at,
I started thinking about a discussion I had with [Alex Waugh](https://sites.google.com/view/alex-waugh) 
over lunch last week (on Tuesday, I believe) about equivariant analogues of characteristic classes. 
He told me about his recent work constructing "equivariant Stiefel-Whitney classes," I asked about 
what might be said about Chern classes, and the question of an equivariant analogue of the Splitting 
Principle came up. This seems pretty interesting, and I wanted to put some initial thoughts on paper
before searching the literature for anything. 

## The classical case

Let's first recall the almost too-obvious definition of a vector bundle: a vector bundle over a space
$B$ is a map $\xi: E \to B$ such that: (1) there is a vector space $V$ such that for each $b \in B$, 
$\xi^{-1}(b) \cong V$ and, moreover (2) there is an open cover $\{U_\alpha\}$ of $B$ such that 
$\xi^{-1}(U_{\alpha})) \cong U_\alpha \times V$. In both cases, I suppose, $\cong$ means homeomorphic, 
but there's a bit more: in (1), we really mean to view each fiber as a vector space; in (2), the 
specified homeomorphism needs to play nice with the projection map, so that a point $(x, v) \in 
U_\alpha \times V$ is mapped (by the isomorphism followed by $\xi$) to the point $x \in B$. (In the 
smooth case you probably also want to upgrade these to diffeomorphisms, to avoid any mischief with
exotic spheres). As for the Splitting Principle:

**Theorem**: Let $\xi: E \to X$ be a complex vector bundle with $X$ paracompact. There exists a 
space $Y$ and a map $f: Y \to X$ such that: (1) $f^*: H^*(X) \to H^*(Y)$ is injective, and (2)
the pullback bundle $f^*\xi$ decomposes as a direct sum of line bundles on $Y$. 

Actually, Wikipedia lists a modification for complexifications of real bundles, which might be 
relevant here:

**Theorem**: Let $\xi: E \to X$ be a real vector bundle of rank $2n$, again with $X$ paracompact. 
There exists a space $Y$ and a map $f: Y \to X$ such that: (1) $f^*: H^*(X) \to H^*(Y)$ is injective,
and (2) $f^*(E \otimes \mathbb{C}) = L_1 \oplus \overline{L_1} \oplus \cdots \oplus L_n \oplus \overline{L_n}$. 

I mention this second one because the process of complexifying $\xi$ also adds in a $C_2$ action by conjugation,
which plays a role in the formulation of the splitting principle in this case.

## Going equivariant

There are basically three difficulties in the way of generalizing this to the equivariant case. The first
one I assume has already been resolved, but here it is anyway: what, exactly, is an equivariant vector bundle? 

The naïve definition would be to say that it is a $G$-equivariant map $\xi: E \to X$ which is a vector bundle
after forgetting the $G$-action. This seemed a bit problematic to me while I was walking in the hot sun but 
now I'm not so sure it's an issue on its own. 

Potentially more problematic is that line bundles aren't really the natural building block in the equivariant
setting. Reason is, if $b \in B$ is an $H$-fixed point, then $H$ acts on the fibre $\xi^{-1}(b)$, giving us an
$H$-representation; unless this is a 1-dimensional representation, splitting it into line bundles tosses out 
this group-action data, which will presumably ruin whatever equivariant calculations we might hope to do. The 
expected analogue would be "irrep bundles," but, er, what does that actually mean? The fibres of a $G$-equivariant
bundle are $H$-representations on $H$-fixed points, but as the point $b \in B$ varies, the stabilizer group $H_b$ 
varies as well; we also need to consider how the group relates different fibres in the same orbit. 

The third problem, of course, is figuring out how to construct $Y$; Alex seemed to think there'd be a problem
getting the induced map on cohomology to be injective, for which I'll take his word for now. But let's get back 
to those representation bundles.

## A conjectural definition

In order to get a clearer picture of how the group $G$ acts on the fibers of a vector bundle, I was thinking 
about the following definition:

**Definition:** Let $X$ be a $G$-space, for $G$ finite. A $G$-vector bundle on $X$ with fiber $V$ is a $G$-equivariant 
map $\xi: E \to X$ such that for each $x \in X$, the preimage of the orbit $Gx$ has the structure of $|G|$ copies
of $V$, indexed by the elements of $G$ (as $V_g$), so that $V_e$ is the fiber over $x$ and $V_g$ is the fiber 
over $gx$, and for all $g, h \in G$, we have a linear map $g: V_h \to V_{gh}$. We should also be able to pick
an open cover $\{U_\alpha\}$ such that the preimage of the orbit $GU_{\alpha}$ is isomorphic to "$U_\alpha \times V_G$", 
where $V_G$ is the set of copies of $V$. (Specifically, this means that the preimage of $g.(U_\alpha)$ is homeomorphic
to $g.(U_\alpha) \times V_g$ in an appropriate way). 

This definition is sort of a mouthful, but it has a couple of nice properties. First of all, we are from the start
*identifying* the fibres over various points in an orbit (not just observing that they are abstractly isomorphic),
which allows us to consider the action $G$ induces across fibres. Actually, we almost certainly want to modify the definition
slightly to say that if the map $\phi: V_G \to \xi^{-1}(Gx)$ sends $V_g$ and $V_h$ to the same fibre, then it actually
"lines them up," meaning that, if we consider vectors $v_g \in V_g, v_h \in V_h$ which are both "copies" of the same 
$v \in V$, $\phi(v_g) = \phi(v_h) \in \xi^{-1}(Gx)$. This doesn't seem strictly necessary (and I have another concern
I'll get to momentarily) but it ensures that the action of $G$ on fibres is encoded entirely within the structure of 
$V_G$, and does not depend on choice of isomorphism $\phi$. (Alternatively, we could take all the action maps $V_g \to V_h$ 
to be identification, and let the map $\phi$ do the work, but it seems better to encode this structure in the algebra
of $V_G$ than in the topology of $\phi$). 

Another related advantage is that it encodes the representation structure without explicit appeal to fixed points. 
That is, from our definition, we get for free that if $x$ is an $H$-fixed point, then $\xi^{-1}(x)$ is an $H$-representation.
Here again it seems best to align the various $V_g$'s in $\xi^{-1}(x)$, so that we can easily extract information
about this representation from $V_G$ - or, looked at another way, we can easily *prescribe* this structure 
without worrying about an impish choice of $\phi$. (The more I think about this the more I think this extra condition
is absolutely necessary for what I'd like to do). 

## Qualms

My new definition seems pretty nice, but there are a couple wrinkles that still need to be ironed out. 

First of all, is this definition even "right"? Meaning, does everything we expect to be a $G$-equivariant vector bundle
actually satisfy this definition? I'm a little worried the structure of $V_G$ might not be uniform (even if we assume $X$
is connected), so either a proof or a counterexample is in order. Specifically, we might run into issues as we move
between fixed-point-sets. 

Second, and relatedly, I'm a bit worried about the part of the definition that specifies behaviour on neighborhoods. 
I mean, it should be fine, since there's no smooth structure, but I'm still a little worried.

Third, how should we define an "irrep bundle?" Well, I guess we want the action of $G$ on $V_G$ to be an 
irrep of $G$ after we identify the various copies of $V$. So that was easier than I thought. But when we
try to prove a splitting principle, this might get a bit funky (since is the restriction of an irrep to a
subgroup still an irrep?).

Finally, we probably want to understand the classifying space of these bundles, which might vary as we change the
structure of $V_G$. 

With that, it's dinnertime for me; I'll think more about these tomorrow.
