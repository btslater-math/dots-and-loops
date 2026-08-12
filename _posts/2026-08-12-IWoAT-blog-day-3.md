---
layout: post
title: "The IWoAT Blog: Day 3"
date: 2026-08-12
---

Lots of stuff today in the direction of "brave new algebra" - ring, module and algebra spectra; Morita theory for ring spectra; 
the relationship between Eilenberg-MacLane spectra of rings and the rings themselves - but the main one I want to get straight in 
my head today was the talk on Operads. 

## Operads

Since first hearing Peter May speak about operads at the UChicago REU long before I knew
enough topology to appreciate them, I have not understood operads. But today's talk was excellent, and I think I may (heh) be 
approaching some understanding of what these gadgets do.

First, what is a (binary) operation on a set (or space) $X$? Well, it's just a map $\mu: X^2 \to X$. But we can see that by 
recursively applying $\mu$ we can obtain a variety of higher-arity operations. For instance, there is a ternary operation $\mu_3: X^3 \to X$
given by $\mu_3(x,y,z) = \mu(\mu(x, y), z)$ and another, $\mu_3': X^3 \to X$, given by $\mu_3'(x,y,z) = \mu(x, \mu(y,z))$. Likewise, using
similar nesting, we can obtain operations of arbitrary arity--although *a priori* there will be many roads to the same arity. Of course, we rarely consider arbitrary operations on a set - in the world of sets, we typically care only about associative ones, in which case the operations 
$\mu_3$ and $\mu_3'$ agree, and more generally all the variously composed $n$-ary operations agree. Associativity can be categorically 
encoded easily, using a single small commutative diagram, as in the categorical definition of a monoid.

In the world of spaces, however, it's a different story - we routinely have operations which are only associative *up to homotopy*. 
For example, the composition of loops on a space $X$, which is a natural binary operation on $\Omega X$, is not associative on the nose. Likewise,
the composition of sphere-maps, which is the natural binary operation on $\Omega^2 X$, is both associative and commutative *up to homotopy*, but 
not on the nose. If we look at, say, $\Omega^3 X$, we might expect the binary operation to have slighly different higher-arity behavior, etc. 
The idea of an operad is to provide a single framework for "operations with properties up to homotopy" which can then be applied in a variety
of settings. 

## How operads work

Without going into the full details, an operad $O$ in a symmetric monoidal category $C$ is a sequence of objects $O(1), O(2), \dots$ in $C$ 
equipped with

1. A right action of the symmetric group $\Sigma_m$ on $O(m)$, for each $m$
2. A unit map $1 \to O(1)$
3. Composition maps $\Gamma: O(m) \times O(j_1) \times \cdots times O(j_m) \to O(\sum_i j_i)$, which has to be $\Sigma_{\sum j_i}$-equivariant

satisfying certain additional properties I won't list. 

There are operads we build and operads we are freely given. The ones we build encode specific types of operation. The ones we are given are 
the "endomorphism operads." Each object $X \in C$ has an operad $End_X$ which encodes the abstract idea of a family of operations on $X$. 
In particular, $End_X(n) = Hom(X^n, X)$. The symmetric group acts by permuting the factors of $X$; the unit map picks out the identity $X \to X$;
the composition maps are the "obvious" compositions: the first term is a map $X^m \to X$, and for each $i$ we take a map $X^{j_i} \to X$ that lands in 
the $i$th factor of $X^m$. Composing all these maps gives a map $X^{j_1 + \cdots + j_m} \to X$.

The idea (h/t to Alex Waugh, today's speaker, for introducing this analogy) is: just like how an action of a group $G$ on $X$ is a homomorphism
$G \to End(X)$, an action of an *operad* $O$ on $X$ is a map of operads $O \to End_X$ (that is, for each $n$ a map $O(n) \to End_X(n)$ commuting
with all the maps in the definition). That is, an operad action picks out a particular operation on $X$ whose composition satisfies whatever 
conditions we choose. 

## Examples of Operads

The simplest example is the "commutative operation" operad, $Com$. For each $n$, $Com(n) = \{*\}$; all the structure maps are the trivial ones.
A $Com$-action on $X$ picks out a single map of each arity; moreover, since operad morphisms have to be appropriately equivariant, the triviality
of the $\Sigma_n$ action on $Com(n)$ implies that a $Com$-action on $X$ must pick out maps which are invariant under the action of the symmetric group, 
which are precisely commutative operations. Good.

Next is the "associative operation" operad, $Ass$. For each $n$, $Ass(n) = \Sigma_n$, with the obvious symmetric group action; composition
is given by inclusion of block permutations. An $Ass$-action on $X$ picks out, for each $n$, a $\Sigma_n$-orbit of maps $X^n \to X$. These
maps depend only on the order of the inputs - which implies that the composition has to be associative, because changing the order of the 
*composition* does not change the order of the *inputs themselves*. 

This is clearer if we look at an operad for a non-associative operation. The Little-1-Cubes operad $C_1$ has as $C_1(m)$ the space
of embeddings of $m$ copies of $[0,1]$ into $[0,1]$, with $\Sigma_n$ acting by permuting the copies of $[0,1]$, and composition arising
by embedding more copies of $[0,1]$ into one of the alread-embedded $[0,1]$'s. Observe that this operation is definitely not associative
(but that it is associative up to homotopy). A $C_1$-action on $X$ picks out quite a large family of operations on $X$, which are related 
by reordering the arguments and applying homotopies. (How can we see the homotopies? Well, this operad lives in the category of spaces,
and so the map $C_1(n) \to Hom(X^n, X)$ is a map of topological spaces. The homotopies between embeddings are paths in $C_1(n)$, which 
must get taken to paths in $Hom(X^n, X)$). Observe that this type associative-up-to-homotopy operation is exactly like composition in a 
loop space. One early application of operads was to give an abstract encoding of the algebraic structure of an infinite loop space,
which led to the famous detection theorem. 

As I understand it, operads nowadays are also used to encode new types of operations. For example, I believe the Tambara functors of
equivariant homotopy theory have their multplication structure defined in terms of a certain type of operad. 

To sum up (because I'm getting sleepy) - the point of operads is to encode operations on spaces, particularly when the composition of 
these operations is only "nice" up to certain types of homotopy. In this case, the operad allows us to specify exactly which types of
homotopy we want to consider. 








