---
title: "Maschke's Theorem"
date: 2026-5-14
author_profile: false
permalink: /posts/2026/5/maschke/
tags:
  - representation theory
---

We explain a proof of Maschke's theorem by almost "pure thought."

> **Theorem 1** (Maschke)**.**
Let \\(G\\) be a finite group. Then any finite-dimensional complex representation of \\(G\\) is isomorphic to a direct sum of irreducible representations of \\(G\\).

> **Remark 2.**
In fact, the hypothesis that the representations are finite-dimensional is unnecessary, and we will remove it in Corollary 11 with the help of transfinite induction.

> **Remark 3.**
In fact, our proof will work for representations of \\(G\\) over any algebraically closed field \\(k\\) of characteristic not dividing \\(\left|G\right|\\). Slight modifications will also work for continuous representations of compact groups.

I am aware of approximately two (related) approaches to Theorem 1.
1. There are purely algebraic proofs which feature the so-called Reynolds operator \\(\sum_{g\in G}g\\).
2. One can use Weyl's unitarian trick in order to find an invariant non-degenerate bilinear form on a finite-dimensional representation. Then one can take complements.

We will more or less follow the first proof, but we will attempt to do as little calculation as possible. The rough sketch is that the Reynolds operator can be used to show that the functor \\((-)^G\\) is exact. (See Proposition 9 and Corollary 10.) However, it will take some time to explain why this is relevant.

Let's begin by recalling some properties of projective modules. In our application, we will take \\(R\\) to be the ring \\(\mathbb C[G]\\) so that a representation of \\(G\\) is just  \\(\mathbb C[G]\\)-module.

> **Lemma 4.**
> Let \\(R\\) be a ring,
and choose some \\(R\\)-module \\(P\\).
The following are equivalent.
> 1. The functor \\(\operatorname{Hom}_R(P,-)\\) is exact.
> 2. Any short exact sequence \\[0\to A\to B\to P\to0\\] splits.
> 3. The module \\(P\\) is a direct summand of a free module.
> 
> A module satisfying any of these conditions is called projective.

*Proof.*
We show the two implications separately.
- To show that 1 implies 2, label the map \\(B\to P\\) as \\(p\\), and we are interested in finding a section \\(s\colon P\to B\\) for which \\(p\circ s=\operatorname{id}\_P\\). (From here, one can show formally that the summed map \\(A\oplus P\to B\\) is an isomorphism.) To this end, we note that \\(p\\) being surjective implies that
\\[(p\circ-)\colon\operatorname{Hom}\_R(P,B)\to\operatorname{Hom}\_R(P,P)\\]
is surjective by exactness. Thus, there is \\(s\colon P\to B\\) for which \\(p\circ i=\operatorname{id}\_P\\).
- To show that 2 implies 3, we note that there is certainly some free module \\(F\\) which surjects onto \\(P\\). (For example, \\(F=R^{\oplus P}\\) will do the trick.) Let \\(K\\) be the kernel of the projection \\(F\twoheadrightarrow P\\), and we conclude by noticing that the short exact sequence
\\[0\to K\to F\to P\to0\\]
splits!
- To show that 3 implies 1, we recall that \\(\operatorname{Hom}_R(P,-)\\) is a right adjoint to \\(-\otimes_R P\\), so it is always left exact. It only remains to show that a surjection \\(p\colon M\to M''\\) induces a surjection \\(\operatorname{Hom}\_R(P,M)\to\operatorname{Hom}\_R(P,M'')\\). To this end, choose some map \\(b\colon P\to M''\\), which we would like to lift to a map \\(P\to M\\).

    We now use 3 to write \\(P\oplus Q=F\\) for some other module \\(Q\\) and free module \\(F\\). Because \\(F\\) is free, one can lift the composite \\(F\to P\to M''\\) to a map \\(F\to M\\): indeed, simply choose lifts in \\(M\\) for the image of each generator of \\(F\\). Then the desired lift \\(P\to M\\) is the composite \\(P\to F\to M\\). \\(\blacksquare\\)

Roughly speaking, to show Theorem 1, we see that it will be enough to show that any short exact sequence splits, so we should show that every module is projective. Accordingly, we should show that the functor \\(\operatorname{Hom}_{\mathbb C[G]}(V,-)\\) is always exact. We will do this in two steps.

> **Lemma 5.**
Let \\(V\\) and \\(W\\) be complex representations of a finite group \\(G\\). Then
\\[\operatorname{Hom}\_G(V,W)=\operatorname{Hom}\_{\mathbb C}(V,W)^G.\\]
Here, \\((-)^G\colon\operatorname{Rep}\_{\mathbb C}(G)\to\mathrm{Vec}\_{\mathbb C}\\) is the invariants functor given by \\(V^G=\\{v\in V:gv=v\text{ for all }g\in G\\}\\).

*Proof.*
This follows more or less from the definition of the \\(G\\)-action on \\(\operatorname{Hom}\_{\mathbb C}(V,W)\\), which we recall is given by
\\[(g\varphi)(v)=g\cdot\varphi\left(g^{-1}\cdot v\right),\\]
for \\(g\in G\\) and \\(\varphi\in\operatorname{Hom}\_{\mathbb C}(V,W)\\) and \\(v\in V\\). Thus, we see that a linear map \\(\varphi\colon V\to W\\) preserves the \\(G\\)-action if and only if \\(g\cdot\varphi(v)=\varphi(g\cdot v)\\) for all \\(v\in V\\) and \\(g\in G\\), which is equivalent to \\(g\cdot\varphi=\varphi\\) for all \\(g\in G\\). \\(\blacksquare\\)

Thus, to show that \\(\operatorname{Hom}\_G(V,-)\\) is exact, we may as well show that the functors \\(\operatorname{Hom}\_{\mathbb C}(V,-)\\) and \\((-)^G\\) are exact. The former is not so hard because all vector spaces are free modules. For the latter, we will require a trick.

> **Remark 6.**
To slightly motivate what follows (in Remark 8), note that Lemma 5 implies that the functor \\((-)^G\\) is naturally isomorphic to the functor \\(\operatorname{Hom}_G(\mathbb C,-)\\), where \\(\mathbb C\\) refers to the trivial representation.

> **Definition 7.**
Fix a finite group \\(G\\). Then we define the *coinvariants* functor \\((-)\_G\colon\operatorname{Rep}\_{\mathbb C}(G)\to\mathrm{Vec}_{\mathbb C}\\) by
\\[V\_G:=V/I_GV,\\]
where \\(I_G\subseteq\mathbb C[G]\\) is the ideal generated by the elements \\(\\{g-1\\}\_{g\in G}\\). Equivalently, \\(I_GV\subseteq V\\) is the subspace \\(\\{gv-v\\}\_{g\in G,v\in V}\\).

> **Remark 8.**
We claim that \\((-)\_G\\) is naturally isomorphic to the functor \\(\mathbb C\otimes\_{\mathbb C[G]}-\\), where \\(\mathbb C\\) refers to the trivial representation. Let's construct the two inverse natural isomorphisms.
- For any representation \\(V\\), there is a natural quotient map \\(V\to\mathbb C\otimes\_{\mathbb C[G]}V\\) given by \\(v\mapsto1\otimes v\\). This map contains \\((g-1)v\\) in its kernel for any \\(g\in G\\) and \\(v\in V\\), so \\(I_GV\\) is in the kernel.
- For any representation \\(V\\), there is a natural \\(\mathbb C\\)-bilinear map \\(\mathbb C\times V\to V\\) given by scalar multiplication. Taking a further quotient to \\(V_G\\) produces a \\(\mathbb C[G]\\)-bilinear map because \\(g\overline v=\overline v\\) for any \\(g\in G\\) and \\(\overline v\in V_G\\), so we receive a natural map \\(\mathbb C\otimes_{\mathbb C[G]}V\to V_G\\).

Remark 8 in particular implies that the functor \\((-)_G\\) is right exact because it is a left adjoint. The relevance of this functor is the following.

> **Proposition 9.**
Fix a finite group \\(G\\). The functors \\((-)^G\\) and \\((-)_G\\) are naturally isomorphic.

*Proof.*
The natural transformation \\((-)^G\Rightarrow(-)_G\\) can be defined directly: for a representation \\(V\\), and then we define the natural map \\(V^G\to V\_G\\) as the composite
\\[V^G\subseteq V\twoheadrightarrow V\_G.\\]
The difficulty lies in constructing an inverse, for which we use the Reynolds operator: for any representation \\(V\\), note that there is a map \\(R\_V\colon V\to V\\) given by
\\[R\_V(v)=\frac1{\left|G\right|}\sum\_{g\in G}gv.\\]
Here are some checks.
- The map \\(R\_V\\) is natural in \\(V\\) because morphisms of representations commute with the \\(G\\)-action.
- Note \\(R\_V\\) outputs to \\(V^G\\) because any \\(G\\)-action merely rearranges the sum.
- Note \\(R\_V\\) factors through \\(V\_G\\): indeed, for any \\(g\in G\\) and \\(v\in V\\), we see that \\(R\_V(gv)\\) and \\(R\_V(v)\\) are simply rearrangements of the same sum, so \\(R\_((g-1)v)=0\\) follows.

Thus, we have constructed a natural transformation \\(R\colon(-)_G\to(-)^G\\). Here are the inverse checks; fix a representation \\(V\\).
- The composite \\(V^G\to V\_G\to V^G\\) sends \\(v\in V^G\\) to the coset \\(\overline v\in V\_G\\). But \\(R\_V(v)=v\\) by construction, so the composite \\(V^G\to V\_G\to V^G\\) is the identity.
- The map \\(V\_G\to V^G\\) send some coset \\(\overline v\\) to \\(R\_V(v)=\frac1{\left\|G\right\|}\sum\_{g\in G}gv\\), where \\(v\in V\\) is a lift of \\(\overline v\\). But the images of \\(gv\\) and \\(v\\) agree in \\(V\_G\\), so the image of \\(R\_V(v)\\) in \\(V\_G\\) is just \\(v\\). Thus, the composite \\(V\_G\to V^G\to V\_G\\) is the identity. \\(\blacksquare\\)

> **Corollary 10.**
Fix a finite group \\(G\\). Then the functor \\((-)^G\\) is exact.

*Proof.*
Note that \\((-)^G\\) is a right adjoint by Remark 6, so it is left exact. Similarly, \\((-)_G\\) is a left adjoint by Remark 8, so it is right exact. We conclude by Proposition 9. \\(\blacksquare\\)

Let's collect everything we've said.

*Proof of Theorem 1.*
Thus far, we have managed to show that all representations are projective modules: indeed, for any representation \\(V\\),  we should show that the functor \\(\operatorname{Hom}\_G(V,-)\\) is exact. By Lemma 5, it is enough to show that the two functors \\(\operatorname{Hom}\_{\mathbb C}(V,-)\\) and \\((-)^G\\) are exact. The former holds by Lemma 4 because \\(V\\) is free over \\(\mathbb C\\), and the latter holds by Corollary 10.

We now turn to the proof of Theorem 1. Say that a representation \\(V\\) is reducible if and only if it is isomorphic to a direct sum of irreducible representations. We would like to show that all representations are irreducible.

<!-- Let's start with the finite-dimensional case, which is the main part of the argument. -->
We will show that all finite-dimensional representations are reducible by induction on dimension. The zero-dimensional case has no content because such a representation is the empty sum of irreducible representations. For the induction, note that a representation \\(V\\) is either irreducible, in which case we are done, or \\(V\\) admits a proper nonzero subrepresentation \\(W\\). For the latter case, note that the short exact sequence
\\[0\to W\to V\to V/W\to0\\]
splits by Lemma 4, so the reducibility of \\(V\\) follows because the inductive hypothesis grants the reducibility of \\(W\\) and \\(V/W\\). \\(\blacksquare\\)

While we're here, we fulfill the promise of Remark 2.

> **Corollary 11.**
Let \\(G\\) be a finite group. Then any representation of \\(G\\) is isomorphic to a direct sum of irreducible representations of \\(G\\).

*Proof.*
Wwe use transfinite induction. Indeed, choose some representation \\(V\\), which we would like to show is a direct sum of irreducible representations. By choosing a basis of \\(V\\) and considering the generated subrepresentations, we see that there is an ascending filtration \\(\\{V\_\alpha\\}\_{\alpha\le\Lambda}\\) of subrepresentations of \\(V\\), where \\(\Lambda\\) is some ordinal, such that \\(V\_0=0\\), \\(V\_\Lambda=V\\), and each partial quotient \\(V\_{\alpha+1}/V\_\alpha\\) is finite-dimensional.

We will show (by transfinite induction) that each \\(V\_\alpha\\) is a direct sum of irreducible representations, and the inclusion \\(V\_\beta\subseteq V\_\alpha\\) (for \\(\beta<\alpha\\)) is a surjection onto some of the irreducible components of \\(V\_\alpha\\). The start of our indution is \\(\alpha=0\\), where \\(V\_\alpha=0\\), so the claim has no content. We now have two inductive cases.
- Given the claim for \\(\alpha\\), we must show it for \\(\alpha+1\\). Well, the claim follows because the short exact sequence
\\[0\to V\_\alpha\to V\_{\alpha+1}\to V\_\alpha/V\_{\alpha+1}\to0\\]
splits. Namely, we may produce the decomposition of \\(V\_{\alpha+1}\\) by gluing together the decompositions for \\(V\_\alpha\\) and the finite-dimensional representation \\(V\_\alpha/V\_{\alpha+1}\\).
- For a limit ordinal \\(\beta\\), if the claim is true for each \\(\alpha<\beta\\), then we must show the claim for \\(\beta\\). Well,
\\[V\_\beta=\bigcup\_{\alpha<\beta}V\_\alpha,\\]
so we may simply glue together the decompositions for each \\(V\_\alpha\\) into a decomposition for \\(V\_\beta\\). The hypothesis on the decompositions in the claim implies that the decompositions glue together. \\(\blacksquare\\)

> **Remark 12.**
Morally, the proof of Corollary 11 just shows that any representation is a direct sum of finite-dimensional ones. Accordingly, we have also shown that all irreducible representations are finite-dimensional.