---
title: "Morphisms to \\\\(\\mathbb P^n_{\\mathbb Z}\\\\)"
date: 2026-6-12
author_profile: false
permalink: /posts/2026/6/projective-space/
tags:
  - algebraic geometry
---

We explain how to construct a morphism to \\(\mathbb P^n_{\mathbb Z}\\).

For this entire blog post, we fix a nonnegative integer \\(n\\). We are interested in the following theorem.

> **Theorem 1.**
There is a natural isomorphism between the set of morphisms from a scheme \\(X\\) to \\(\mathbb P^n_{\mathbb Z}\\) and the set of isomorphism classes of line bundles \\(\mathcal L\\) equipped with \\(n+1\\) global sections \\(\\{s\_0,\ldots,s\_{n+1}\\}\\) which have no common zero.

This theorem confused me for a long time because I did not understand where these sections and line bundles should come from. In my opinion, many classical texts on the subject do not provide satisfactory explanations as to why a line bundle \\(\mathcal L\\) is necessary (instead of merely working with global sections of \\(\mathcal O\_X\\)). (It is not hard to explain the presence of the \\(n+1\\) sections: this is just a fancy way of asking for a surjective map \\(\mathcal O\_X^{n+1}\to\mathcal L\\).)

For my own personal use, we will try to explain "what's going on" behind Theorem 1, meaning that we would like to explain why
\\[X\mapsto\left\\{\mathcal O^{n+1}\twoheadrightarrow\mathcal L:\mathcal L\in\operatorname{Pix}X\right\\}\\]
is a natural thing to do. We will also take a "functor of points" perspective, pretending that we have never seen the construction of the scheme \\(\mathbb P^n\_{\mathbb Z}\\) and instead try to characterize it as representing the above functor; at the end, we will construct it. Thus, we will eventually provide a proof of Theorem 1, but it is far from the most efficient one.

A First Approximation
--

Intuitively, we expect \\(\mathbb P^n\\) to classify lines in \\((n+1)\\)-affine space. For technical reasons (see Remark 3), we will instead view this data as classifying one-dimensional quotients of \\((n+1)\\)-affine space.

> **Example 2.**
Fix a field \\(k\\). Then a morphism \\(\operatorname{Spec}k\to\mathbb P^n_{\mathbb Z}\\) is basically a closed point in \\(\mathbb P^n(k)\\), which amounts to the data of \\(n+1\\) scalars \\(\\{a\_0,\ldots,a\_{n+1}\\}\\) which do not all vanish, up to multiplication by \\(k^\times\\). This is equivalent to the data of a row matrix \\(k^{n+1}\to k\\) of full rank, up to scalar, which is equivalent to the data of a quotient \\(k^{n+1}\to k\\) up to isomorphism of \\(k\\).

Thus, as a first approximation, we may expect that a morphism \\(\operatorname{Spec}A\to\mathbb P^n_{\mathbb Z}\\) has equivalent data to a quotient map \\(A^{n+1}\to A\\), up to isomorphism.

> **Remark 3.**
Let's explain (in rough terms) why it is more convenient to consider quotients instead of sub-objects. The reason is that a "line" should be viewed as a subspace which admits a complement. For example, over a local ring \\(A\\), we should be classifying split short exact sequences
\\[0\to A\to A^{n+1}\to A^n\to0.\\]
This is a lot of data! However, note that the kernel of the map \\(A^{n+1}\to A^n\\) is projective and hence free (because \\(A\\) is local), and it then has rank one, so the isomorphism class of this short exact sequence can be remembered merely by remembering the surjection \\(A^{n+1}\to A^n\\). Similarly, by passing to the dual, we see that this short exact sequence has equivalent data to a surjection \\(A^{n+1}\to A\\).

This first approximation is wrong. In fact, there is no scheme \\(P\\) equipped with a natural isomorphism between the set of morphisms \\(\operatorname{Spec}A\to P\\) and the set of isomorphism classes of quotients \\(A^{n+1}\to A\\). To prove this, let's recall some notions related to representability of functors.

> **Notation 4.**
Given a category \\(\mathcal C\\), we let \\(\mathrm{PSh}(\mathcal C)\\) denote the *presheaf category* of functors \\(\mathcal C^{\mathrm{op}}\to\mathrm{Set}\\), where morphisms are given by natural transformations. Given an object \\(X\in\mathcal C\\), we let \\(h_X\\) denote the presheaf
\\[h_X(Y):=\operatorname{Mor}_{\mathcal C}(Y,X).\\]

> **Theorem 5** (Yoneda)**.**
Fix a category \\(\mathcal C\\). For any object \\(X\\) and presheaf \\(\mathcal F\\), there is a natural isomorphism
\\[\operatorname{Mor}_{\mathrm{PSh}(\mathcal C)}(h\_X,\mathcal F)\cong\mathcal F(X).\\]

*Sketch.*
Given a natural transformation \\(\eta\colon h\_X\to\mathcal F\\), we can produce the element \\(\eta\_X(\mathrm{id}\_X)\in\mathcal F(X)\\). Conversely, given an element \\(x\in\mathcal F(X)\\), one can construct a natural transformation \\(\eta\colon h\_X\to\mathcal F\\) as follows: for any \\(Y\in\mathcal C\\) and \\(f\in h\_X(Y)\\), we define
\\[\eta\_Y(f):=\mathcal Ff(x).\\]
From here, one has to check that \\(\eta\\) assembles into a natural transformation and that these two constructions are inverse. One should then check that the constructions are natural in \\(X\\) and \\(\mathcal F\\). We will write out none of these checks. \\(\blacksquare\\)

> **Corollary 6.**
Fix a category \\(\mathcal C\\). Then the map \\(X\mapsto h\_X\\) defines a fully faithful embedding \\(\mathcal C\to\mathrm{PSh}(\mathcal C)\\).

*Proof.*
By Theorem 5, one has
\\[\operatorname{Mor}\_{\mathrm{PSh}(\mathcal C)}(h\_X,h\_Y)\cong h\_Y(X)=\operatorname{Mor}\_{\mathcal C}(X,Y).\\]
We will be done if we can check that this map sends a morphism \\(f\colon X\to Y\\) to the natural transformation \\((f\circ -)\colon h\_X\to h\_Y\\). We may as well run the inverse check. To this end, by construction, \\((f\circ-)\\) goes to the element \\(f\circ{\mathrm{id}\_X}\\) of \\(h\_Y(X)\\), which is the morphism \\(f\colon X\to Y\\). \\(\blacksquare\\)

It is in general an interesting question which presheaves \\(\mathcal F\\) are in the image of the embedding \\(\mathcal C\to\mathrm{PSh}(\mathcal C)\\), in which case we may say that \\(\mathcal F\\) is represented by the corresponding object of \\(\mathcal C\\). Of course, this question is intractable in such generality, so we now return to the setting of schemes. Here is one test for representability.

> **Definition 7.**
A *(Zariski) sheaf*  is a presheaf \\(\mathcal F\in\mathrm{PSh}(\mathrm{Sch})\\) satisfying the following sheaf condition: for any open cover \\(\mathcal U\\) of a scheme \\(Y\\), we have
\\[\mathcal F(Y)=\mathrm{eq}\left(\prod\_{U\in\mathcal U}\mathcal F(U)\rightrightarrows\prod\_{U,V\in\mathcal U}\mathcal F(U\times_YV)\right),\\]
where the two maps are given by the two restrictions. (Recall that \\(U\times_YV\\) can be identified with the intersection of the images of \\(U\\) and \\(V\\) in \\(Y\\).) If merely the natural map from \\(\mathcal F(Y)\\) is always injecive, then \\(\mathcal F\\) is called *separated*.

> **Remark 8.**
More explicitly, there is a natural map \\(\mathcal F(Y)\to\prod\_U\mathcal F(U)\\) given by taking the product of the restrictions. By functoriality, this map factors through the equalizer to produce a map
\\[\mathcal F(Y)\to\mathrm{eq}\left(\prod\_{U\in\mathcal U}\mathcal F(U)\rightrightarrows\prod\_{U,V\in\mathcal U}\mathcal F(U\times_YV)\right),\\]
which we want to be an isomorphism.

> **Proposition 9.**
Fix a scheme \\(X\\). Then the presheaf \\(h\_X\in\mathrm{PSh}(\mathrm{Sch})\\) is a Zariski sheaf.

*Proof.*
Fix an open cover \\(\mathcal U\\) of a scheme \\(Y\\), and we are interested in showing that the natural map
\\[h\_X(Y)\to\mathrm{eq}\left(\prod\_{U\in\mathcal U}h\_X(U)\rightrightarrows\prod\_{U,V\in\mathcal U}h\_X(U\cap V)\right)\\]
is an isomorphism.
- Injective: we must show that two maps \\(f,g\colon Y\to X\\) can be checked to be equal by checking if \\(f\|\_U=g\|\_U\\) for all \\(U\in\mathcal U\\). This is certainly true on the level of topological spaces, and it is true for the sheaves because morphisms of sheaves can be checked to be equal on stalks.
- Surjective: given morphisms \\(f\_U\colon U\to X\\) which agree on intersections, we must show that these morphisms glue to a morphism \\(Y\to X\\). Well, this is certainly possible on the topological spaces, and it is then possible for the sheaves because morphisms of sheaves glue. (For example, one can start by defining a morphism of sheaves on the base consisting of open subsets contained in an open subset of \\(\mathcal U\\).) \\(\blacksquare\\)

We are now ready to explain why we should not ask for \\(\mathbb P^n_{\mathbb Z}\\) to represent the functor sending the affine scheme \\(\operatorname{Spec}A\\) to isomorphism classes of quotients \\(A^{n+1}\to A\\). By Proposition 9, it is enough to show that this is not a sheaf.

> **Definition 10.**
Let \\(\mathcal Q\\) denote the presheaf on \\(\mathrm{Sch}\\) defined by sending the scheme \\(X\\) to the set of isomorphism classes of quotients \\(\mathcal O\_X^{n+1}\to\mathcal O\_X\\). Here, two quotients are isomorphic if they differ by an element of \\(\mathcal O\_X^\times(X)\\).

> **Remark 11.**
The presheaf \\(\mathcal Q\\) is at least separateted. Indeed, for an open cover \\(\mathcal U\\) of \\(X\\), we must show that the natural map
\\[\mathcal Q(X)\to\mathrm{eq}\left(\prod\_{U\in\mathcal U}\mathcal Q(U)\rightrightarrows\prod\_{U,V\in\mathcal U}\mathcal Q(U\cap V)\right)\\]
is injective. Choose two quotients \\(\pi,\tau\colon\mathcal O\_X^{n+1}\to\mathcal O\_X\\) which agree in the equalizer. Then each \\(U\in\mathcal U\\) admits some scalar \\(c\_U\in\mathcal O\_X^\times\\) for which \\(\pi\|\_U=c\_U\tau\|\_U\\). For example, it follows that the locus where \\(\pi-c\tau\\) vanishes is open for each \\(c\in\mathcal O\_X(X)^\times\\), so the locus where \\(\pi-\tau\\) vanishes is both open and closed. By rescaling \\(\tau\\), we may assume that \\(\pi\_x=\tau\_x\\) for some \\(x\\) in each connected component of \\(X\\), so it follows that \\(\pi=\tau\\).

> **Proposition 12.**
Suppose \\(n\ge1\\). Then \\(\mathcal Q\\) is not a sheaf, even if restricted to open covers of affine schemes by affine schemes.

*Proof.*
In light of Remark 11, the issue will be surjectivity of the natural map. The rough idea is that one cannot in general "glue" free modules to free modules. This is an issue because we need to glue surjections \\(A^{n+1}\to A\\) together from an open cover, but the free module \\(A\\) may fail to glue! Accordingly, our counterexample will come from a projective module which fails to be free.

Let \\(A\\) be a Dedekind domain which is not a unique factorization domain. For example, \\(A=\mathbb Z[\sqrt{-5}]\\) will suffice. Then \\(A\\) is not a principal ideal domain, so \\(A\\) admits an ideal \\(I\\) which is not principal. Because \\(I\subseteq A\\), we do know that \\(I\\) is projective of rank at most one, and it is rank one because \\(I\\) is nonzero. Let \\(\mathcal U\\) be a trivializing open cover for \\(I\\); we may as well assume that each \\(U\in\mathcal U\\) is a distinguished affine open subset \\(D(f\_U)\\).

Now, because \\(A\\) is a Dedekind domain, \\(I\\) can be generated by two elements, meaning that there is a surjection \\(A^2\to I\\). By appending by zeroes, we receive a surjection \\(\pi\colon A^{n+1}\to I\\). (Here is the only place where we use \\(n\ge1\\).) Localization is exact, so \\(\pi\\) induces a surjection
\\[A^{n+1}\_f\to I\_f\\]
for each \\(f\in A\\). In particular, for each \\(U\in\mathcal U\\), we have a surjection \\(A^{n+1}\_{f\_U}\to I\_{f\_U}\cong A\_{f\_U}\\), which we call \\(\pi\_U\\).

To complete the proof, we will show that the tuple \\((\pi\_U)\\) is in the codomain but not the image of the map
\\[\mathcal Q(A)\to\mathrm{eq}\left(\prod\_{U\in\mathcal U}\mathcal Q(U)\rightrightarrows\prod\_{U,V\in\mathcal U}\mathcal Q(U\cap V)\right).\\]
Here are our checks.
- In codomain: for \\(U,V\in\mathcal U\\), we must show that \\(\pi\_U\|\_{U\cap V}=\pi\_V\|\_{U\cap V}\\). Well, up to choosing a trivialization of \\(I\|\_{U\cap V}\\) (which is unique up to an element of \\(A^\times\\)), both of these maps are given by localizing the surjection \\(\pi\colon A^{n+1}\to I\\).
- Not in image: suppose that \\((\pi\_U)\\) is the image of the surjection \\(\tau\colon A^{n+1}\to A\\). Then we will show that \\(I\\) is principal, which is a contradiction. By adjusting each \\(\pi\_U\\) by a scalar, we may assume that \\(\tau\|\_U=\pi\_U\\) for each \\(U\in\mathcal U\\). This means that the induced isomorphisms \\(I\_{f\_U}\cong A\_{f\_U}\\) agree on intersections, so these isomorphisms on an open cover glue to a global trivialization of the line bundle \\(I\\), which means that \\(I\cong A\\), so \\(I\\) is principal. \\(\blacksquare\\)

The Sheafification
---
This section is rather technical, so I have written the rest of the post so that it is not logically necessary. On the other hand, I think it provides some explicit motivation for the presence of line bundles in Theorem 1.

In sheaf theory, the natural way to fix the problem that a presheaf is not a sheaf is to pass to the sheafification. Thus, we should sheafify \\(\mathcal Q\\). Of course, we should probably start by explaining what the sheafification is in our context.

> **Definition 13.**
Let \\(\mathcal F\colon\mathrm{Sch}^{\mathrm{op}}\to\mathrm{Set}\\) be a presheaf. A morphism \\(i\colon\mathcal F\to\mathcal F^{\mathrm{sh}}\\) is a *sheafification* if and only if \\(\mathcal F^{\mathrm{sh}}\\) is a Zariski sheaf, and any map from \\(\mathcal F\\) to a Zariski sheaf\\(\mathcal G\\) factors uniquely through \\(i\\).

There is a general process of sheafification (on a "site"), and it will be useful to us to know something about it. For motivation, if we have a separated presheaf \\(\mathcal F\\), the obstruction of \\(\mathcal F\\) being a sheaf is that there are sections which "should be there" (coming from open covers) but are not. To fix this problem, we formally add in the required sections.

> **Definition 14.**
Let \\(\mathcal F\colon\mathrm{Sch}^{\mathrm{op}}\to\mathrm{Set}\\) be a presheaf. For any open cover \\(\mathcal U\\) of a scheme \\(X\\), we define
\\[\check{\mathrm H}^0(\mathcal U;\mathcal F):=\operatorname{eq}\left(\prod\_{U\in\mathcal U}\mathcal F(U)\rightrightarrows\prod\_{U,U'\in\mathcal U}\mathcal F(U\times\_XU')\right).\\]

This notation comes from Čech cohomology. Of course, Definition 14 is only adding in the sections from the single open cover \\(\mathcal U\\), but we will need to add in all sections from all open covers. To this end, we want to take a colimit over open covers.

> **Definition 15.**
Fix a scheme \\(X\\). Then a *refinement* of an open cover \\(\mathcal U\\) is an open cover \\(\mathcal V\\) of \\(X\\) and a function \\(\alpha\colon\mathcal V\to\mathcal U\\) such that \\(V\subseteq\alpha(V)\\) for each \\(V\in\mathcal V\\).

> **Remark 16.**
A refinement \\(\alpha\colon\mathcal V\to\mathcal U\\) induces a morphism \\(\alpha^*\colon\check{\mathrm H}^0(\mathcal U;\mathcal F)\to\check{\mathrm H}^0(\mathcal V;\mathcal F)\\): for example, \\(\alpha\\) chooses maps \\(\mathcal F(\alpha(V))\to\mathcal F(U')\\) for each \\(V\in\mathcal V\\), which combines to a morphism
\\[\prod\_{U\in\mathcal U}\mathcal F(U)\to\prod\_{V\in\mathcal V}\mathcal F(V),\\]
given by the maps \\(\prod\_{U\in\mathcal U}\mathcal F(U)\to\mathcal F(\alpha(V))\to\mathcal F(V)\\). This commutes with restriction, so we get a morphism on \\(\check{\mathrm H}^0\\).

> **Remark 17.**
While we're here, we note that any two choices of refinements \\(\alpha,\beta\colon\mathcal V\to\mathcal U\\) actually induce the same map \\(\check{\mathrm H}^0(\mathcal U;\mathcal F)\to\check{\mathrm H}^0(\mathcal V;\mathcal F)\\). Indeed, for \\((s\_U)\_U\in\check{\mathrm H}^0(\mathcal U;\mathcal F)\\), we want to show that \\(\alpha^\*(s)=\beta^\*(s)\\). Well, for \\(V\in\mathcal V\\), we must show \\((\alpha^\*s)_V=(\beta^\*s)\_V\\), which is equivalent to showing
\\[s\_{\alpha(V)}\|\_V\stackrel?=s\_{\beta(V)}\|_V.\\]
But this holds because \\(s\_{\alpha(V)}\|\_{\alpha(V)\cap\beta(V)}=s\_{\alpha(V)}\|\_{\alpha(V)\cap\beta(V)}\\) (by definition of \\(\mathrm{\check H}^0\\)!), and \\(V\subseteq\alpha(V)\cap\beta(V)\\).

> **Definition 18.**
Let \\(\mathcal F\colon\mathrm{Sch}^{\mathrm{op}}\to\mathrm{Set}\\) be a presheaf. For a scheme \\(X\\), we define
\\[\check{\mathrm H}^0(X;\mathcal F):=\operatorname{colim}\_{\mathcal U}\check{\mathrm H}^0(\mathcal U;\mathcal F),\\]
where the colimit is taken over open covers, with morphisms given by refinement (and Remark 16).

> **Remark 19.**
Because any two open covers admit a common refinement (and the morphisms given by refinement are canonical by Remark 17), the colimit in Definition 18 is filtered.

We now upgrade the construction \\(\mathrm{\check H}^0(X;\mathcal F)\\) to a presheaf.

> **Remark 20.**
Given a morphism \\(f\colon Y\to X\\), any open cover \\(\mathcal U\\) of \\(X\\) induces an open cover \\(f^{-1}\mathcal U\\) of \\(Y\\) by taking the pre-image. The same argument as in Remark 16 provides us with a map \\(f^\*\colon\check{\mathrm H}^0\left(\mathcal U;\mathcal F\right)\to\check{\mathrm H}^0\left(f^{-1}\mathcal U;\mathcal F\right)\\) by using the various restrictions of \\(\mathcal Ff\\). Because everything is basically induced by \\(\mathcal Ff\\), naturality of \\(\mathcal F\\) makes these morphisms compatible with refinement, so we may pass to the colimit to receive a map
\\[f^\*\colon\mathrm{\check H}^0(X;\mathcal F)\to\mathrm{\check H}^0(Y;\mathcal F).\\]

Quickly, we note that the maps of Remark 20 are functorial. For example, \\({\mathrm{id}\_X}\\) goes to the identity map on \\(\mathrm{\check H}^0(X;\mathcal F)\\). Also, \\((f\circ g)^\*=g^\*\circ f^\*\\) for morphisms \\(f\colon Y\to X\\) and \\(g\colon Z\to Y\\). We will not write out these checks by hand, but they follow by expanding out the definition and tying everything back to the functoriality of \\(\mathcal F\\). We thus may make the following definition.

> **Definition 21.**
Let \\(\mathcal F\colon\mathrm{Sch}^{\mathrm{op}}\to\mathrm{Set}\\) be a presheaf. Then we define the presheaf \\(\mathcal F^+\\) by \\(\mathcal F^+(X):=\mathrm{\check H}^0(X;\mathcal F)\\), with morphisms as in Remark 20.

> **Remark 22.**
The construction of Remark 8 provides a map \\(\mathcal F(X)\to\mathcal F^+(X)\\) for any scheme \\(X\\). The restrictions maps of \\(\mathcal F^+\\) are induced by the restriction maps for \\(\mathcal F\\) (first on open covers \\(\mathcal U\\) and then by passing to the colimit), so this upgrades to a morphism \\(\mathcal F\to\mathcal F^+\\) of presheaves.

> **Remark 23.**
Given a morphism \\(\mathcal F\to\mathcal G\\) of presheaves, we get a natural map \\(\mathrm{\check H}^0(\mathcal U;\mathcal F)\to\mathrm{\check H}^0(\mathcal U;\mathcal G)\\) for any open cover \\(\mathcal U\\) by functoriality of limits. Functoriality of colimits then produces a map \\(\mathcal F^+(X)\to\mathcal G^+(X)\\) for any scheme \\(X\\). As in Remark 22, this upgrades to a morphism of presheaves by functoriality of limits and colimits.

At least in the case where \\(\mathcal F\\) is a separated presheaf, we expect \\(\mathcal F^+\\) to be the sheafification. This will turn out to be true, but it is a little tricky to check.

> **Lemma 24.**
Let \\(\mathcal F\colon\mathrm{Sch}^{\mathrm{op}}\to\mathrm{Set}\\) be a presheaf. For any scheme \\(X\\), any \\(s\in\mathcal F^+(X)\\) admits an open cover \\(\mathcal U\\) of \\(X\\) satisfying the following: for any \\(U\in\mathcal U\\), the restriction \\(s\|\_U\\) is in the image of the map \\(\mathcal F(U)\to\mathcal F^+(U)\\).

*Proof.*
By definition of \\(\mathcal F^+(X)\\), there is an open cover \\(\mathcal U\\) of \\(X\\) so that \\(s\\) comes from an element \\((s\_U)\_U\in\check{\mathrm H}^0(\mathcal U;\mathcal F)\\). Now, for \\(U\in\mathcal U\\), we see \\(s\_U\in\mathcal F(U)\\), which we claim agrees with the element \\(s\|\_U\\) in \\(\mathcal F^+(U)\\).

Well, \\(s\|\_U\\) is given by restricting the coordinates of \\(s\\) component-wise to the open cover \\(U\cap\mathcal U\\) of \\(U\\). The key input is that the open cover \\(U\cap\mathcal U\\) is refined by the open cover \\(\\{U\\}\\). Thus, \\(s\|\_U\\) agrees with the element \\(s\_U\in\check{\mathrm H}^0(\\{U\\};\mathcal F)\\) once embedded into the directed limit \\(\mathcal F^+(U)\\). \\(\blacksquare\\)

> **Proposition 25.**
Let \\(\mathcal F\colon\mathrm{Sch}^{\mathrm{op}}\to\mathrm{Set}\\) be a presheaf. Then \\(\mathcal F^+\\) is separated.

*Proof.*
Fix a scheme \\(X\\) and two sections \\(s,s'\in\mathcal F^+(X)\\) which agree when restricted to an open cover \\(\mathcal U\\) of \\(X\\). By refining \\(\mathcal U\\) and Lemma 24, we may assume that \\(s\|\_U\\) and \\(s'\|\_U\\) are both in the image of the natural map \\(\mathcal F(U)\to\mathcal F^+(U)\\) for each \\(U\in\mathcal U\\). We will write \\(s\_U\\) and \\(s'\_U\\) for these pre-images in \\(\mathcal F(U)\\), respectively.

Now, for each \\(U\in\mathcal U\\), we know that \\(s\_U\\) and \\(s'\_U\\) are equal in \\(\mathcal F^+(U)\\). This means that \\(U\\) admits an open cover \\(\mathcal V\_U\\) for which \\(s\_U\|\_V=s'\_U\|\_V\\) for each \\(V\in\mathcal V\_U\\). Then the open cover \\(\mathcal V=\bigcup\_{U\in\mathcal U}\mathcal V\_U\\) of \\(X\\) admits the element
\\[(s\_U\|\_V)\_{V\in\mathcal V\_U}=(s'\_U\|\_V)\_{V\in\mathcal V\_U}\\]
in \\(\mathrm{\check H}^0(\mathcal V;\mathcal F)\\) which witnesses \\(s=s'\\) in \\(\mathcal F^+(X)\\). \\(\blacksquare\\)

> **Proposition 26.**
Let \\(\mathcal F\colon\mathrm{Sch}^{\mathrm{op}}\to\mathrm{Set}\\) be a separated presheaf. Then \\(\mathcal F^+\\) is a sheaf.

*Proof.*
By Proposition 25, \\(\mathcal F^+\\) is already separated, so we only have to check gluing. Namely, suppose that we are given an open cover \\(\mathcal U\\) of a scheme \\(X\\) along with sections \\(s\_U\in\mathcal F^+(U)\\) such that \\(s\_U\|\_{U\cap V}=s\_V\|\_{U\cap V}\\) for each \\(U,V\in\mathcal U\\). Then we would like to find \\(s\in\mathcal F(X)\\) restricting to each \\(s\_U\\).

Quickly, we note that we may refine \\(\mathcal U\\) to some open cover \\(\mathcal U'\\) with no trouble. Indeed, the compatibility of the sections remains true after restriction. Then if we can find \\(s\\) gluing the restricted sections \\(s\_{U'}\\) for \\(U'\in\mathcal U'\\), then \\(s\|\_U\|\_{U\cap U'}=s\_U\|\_{U\cap U'}\\) for each \\(U\in\mathcal U\\) and \\(U'\in\mathcal U'\\), so \\(s\|\_U=s\_U\\) holds for each \\(U\in\mathcal U\\) because \\(\mathcal F^+\\) is already known to be separated.

Accordingly, we use Lemma 4 to refine \\(\mathcal U\\) so that \\(s\_U\\) is the image of the natural map \\(\mathcal F(U)\to\mathcal F^+(U)\\) for each \\(U\in\mathcal U\\). Because \\(\mathcal F\\) is separated, the natural map \\(\mathcal F\to\mathcal F^+\\) is injective, so this element \\(s\_U\\) is unique. Furthermore, the equality \\(s\_U\|\_{U\cap V}=s\_V\|\_{U\cap V}\\) for each \\(U,V\in\mathcal U\\) takes place in \\(\mathrm F^+(U\cap V)\\) but upgrades to an equality in \\(\mathcal F(U\cap V)\\). Thus, \\((s\_U)\\) is an element in \\(\check{\mathrm H}^0(\mathcal U;\mathcal F)\\), so it maps to an element \\(s\\) in \\(\mathcal F^+(X)\\). As in Lemma 24, we see that \\(s\|\_U=s\_U\\), so we are done! \\(\blacksquare\\)

> **Theorem 27.**
Let \\(\mathcal F\colon\mathrm{Sch}^{\mathrm{op}}\to\mathrm{Set}\\) be a presheaf. Then the map \\(\mathcal F\to\mathcal F^{++}\\) is the sheafification of \\(\mathcal F\\).

*Proof.*
By Propositions 25 and 26, \\(\mathcal F^{++}\\) is a sheaf. It remains to check the universal property. Well, choose a sheaf \\(\mathcal G\\) and a map \\(\eta\colon\mathcal F\to\mathcal G\\). We want to show that there is a unique induced map \\(\mathcal F^{++}\to\mathcal G\\).
- Uniqueness: for \\(s\in\mathcal F^{++}(X)\\), Lemma 24 (applied iteratively) tells us that \\(s\\) comes from an open cover \\(\mathcal U\\) of \\(X\\), meaning that \\(s\|\_U\in\mathcal F^{++}(U)\\) is the image of some \\(s\_U\in\mathcal F(U)\\) for each \\(U\in\mathcal U\\). Now, the image of \\(s\\) in \\(\mathcal G(X)\\) must be compatible with the images of \\(s\_U\in\mathcal G(U)\\), which uniquely determines \\(s\\) because \\(\mathcal G\\) is separated.
- Existence: the maps in Remarks 22 and 23 provide a commutative diagram
\\[\begin{array}{cccccccccc}
\mathcal F &\to& \mathcal F^+ &\to& \mathcal F^{++} \\\\\\\\
\downarrow && \downarrow && \downarrow \\\\\\\\
\mathcal G &\to& \mathcal G^+ &\to& \mathcal G^{++}
\end{array}\\]
where the vertical morphisms are induced by \\(\eta\\). Because \\(\mathcal G\\) is a sheaf, the bottom arrows are all isomorphisms, so we receive an induced map \\(\mathcal F^{++}\to\mathcal G\\). \\(\blacksquare\\)

> **Remark 28.**
The same argument shows that \\(\mathcal F^+\\) is the sheafification when \\(\mathcal F\\) is separated.

We now have a template to fix the problem presented in the previous subsection: it is impossible to represent \\(\mathcal Q\\) by a scheme because it is not a Zariski sheaf, but maybe the sheafification \\(\mathcal Q^+\\) (see Remark 28) can be represented. Line bundles arise naturally when trying to describe \\(\mathcal Q^+\\) explicitly, which we now explain.

> **Definition 29.**
Let \\(\mathcal P\\) denote the presheaf defined by sending the scheme \\(X\\) to the set of isomorphism classes of surjections \\(\mathcal O\_X^{n+1}\to\mathcal L\\), where \\(\mathcal L\\) is a line bundle on \\(X\\). Two surjections \\(\pi\colon\mathcal O\_X^{n+1}\to\mathcal L\\) and \\(\tau\colon\mathcal O\_X^{n+1}\to\mathcal M\\) are isomorphic if and only if there is an isomorphism \\(\mathcal L\cong\mathcal M\\) compatible with the surjections.

> **Proposition 30.**
We have \\(\mathcal Q^+\cong\mathcal P\\). In particular, \\(\mathcal P\\) is a sheaf.

*Proof.*
The core idea is that an element of \\(\mathcal Q^+(X)\\) is the data of gluing together local surjections \\(\mathcal O\_U^{n+1}\to\mathcal O\_U\\). The local \\(\mathcal O\_U\\)s glue together to a line bundle (which is not necesssarily trivial!), and then one can glue the local surjections to a global surjection, which is the data of an element of \\(\mathcal P(X)\\). Making this precise is a little tricky.

Let's start by describing a map \\(\mathcal P\to\mathcal Q^+\\).
0. Fix a scheme \\(X\\), and we will describe a map \\(\eta\colon\mathcal P(X)\to\mathcal Q^+(X)\\). Choose a surjection \\(\pi\colon\mathcal O\_X^{n+1}\to\mathcal L\\). Then \\(\mathcal L\\) admits a trivializing open cover \\(\mathcal U\\); choose isomorphisms \\(\varphi\_U\colon\mathcal L\|\_U\to\mathcal O\_U\\) for each \\(U\in\mathcal U\\).

    We claim that the tuple \\((\varphi\_U\circ\pi\|\_U)\_U\\) is an element of \\(\check{\mathrm H}^0(\mathcal U;\mathcal Q)\\), which is then an element in \\(\mathcal Q^+(X)\\). Certainly each composite \\(\varphi\_U\circ\pi\|\_U\\) is a surjection \\(\mathcal O\_U^{n+1}\to\mathcal O\_U\\), so we only have to show compatbility. Well, for \\(U,V\in\mathcal U\\), one has the composite isomorphism
    \\[\mathcal O\_U\|\_{U\cap V}\stackrel{\varphi\_U}\cong\mathcal L\|\_{U\cap V}\stackrel{\varphi\_V}\cong\mathcal O\_V\|\_{U\cap V},\\]
    which is compatible with the surjections \\(\varphi\_U\circ\pi\|\_U\\) and \\(\varphi\_V\circ\pi\|\_V\\) by construction, so these surjections agree when restricted to \\(U\cap V\\).

0. Continue with \\(X\\) fixed. We claim that the map \\(\mathcal P(X)\to\mathcal Q^+(X)\\) is well-defined. Changing the isomorphism class of \\(\mathcal L\\) does not do much to our construction, but we do have to check that changing the open cover and local trivializations does not change the target element of \\(\mathcal Q(X)\\).

    Well, choosing a different local trivialization \\(\varphi\_U\colon\mathcal L\|\_U\to\mathcal O\_U\\) amounts to composing with an automorphism of \\(\mathcal O\_U\\). This does not change the isomorphism class in \\(\mathcal Q(U)\\), so it does not change the underlying element of \\(\mathcal Q(X)\\).

    Thus, we may reduce our well-definedness check to showing that the target element in \\(\mathcal Q(X)\\) does not change if we refine \\(\mathcal U\\) to some open cover \\(\mathcal U'\\), using the induced trivializations (by restriction). But this process of refinement restricts component-wise, so it is exactly the map
    \\[\mathrm{\check H}^0(\mathcal U;\mathcal Q)\to\mathrm{\check H}^0(\mathcal U';\mathcal Q),\\]
    so it does not change the underlying class in \\(\mathcal Q^+(X)\\).

0. We now upgrade \\(\eta\colon\mathcal P\to\mathcal Q^+\\) to a morphism of presheaves. Well, choose a morphism \\(f\colon Y\to X\\) and a surjection \\(\pi\colon\mathcal O\_X^{n+1}\to\mathcal L\\). We may as well choose a trivializing open cover \\(\mathcal U\\) of \\(\mathcal L\\) and local trivializations \\(\varphi\_U\colon\mathcal L\|\_U\to\mathcal O\_U\\). Then \\(\eta(f^\*\pi)\\) is the element
\\[(f^\*\varphi\_{f^{-1}U}\circ f^\*\pi\|\_{f^{-1}U})\_U\in\check{\mathrm H}^0\left(f^{-1}\mathcal U;\mathcal Q\right)\\]
because \\(f^\*\varphi\_{f^{-1}U}\colon f^\*\mathcal L\to\mathcal O\_{f^{-1}U}\\) are suitable local trivializations. Similarly, \\(f^\*\eta(\pi)\\) is the element
\\[(f^\*(\varphi\_U\circ\pi\|\_U))\_U\in\check{\mathrm H}^0\left(f^{-1}\mathcal U;\mathcal Q\right).\\]
These agree by funtoriality of the pullback.

We now describe the inverse map \\(\mathcal Q^+\to\mathcal P\\), which is trickier.

0. Fix a scheme \\(X\\), and we describe a map \\(\mathcal Q^+(X)\to\mathcal P(X)\\) is surjective. Choose some element in \\(\mathcal Q^+(X)\\), which may represented as a tuple \\((\pi\_U)\_U\in\check{\mathrm H}^0(\mathcal U;\mathcal Q)\\), where \\(\mathcal U\\) is some open cover of \\(X\\).

    Let's start by constructing our line bundle. By construction, for each \\(U,V\in\mathcal U\\), there is an isomorphism \\(\varphi\_{UV}\colon\mathcal O\_V\|\_{U\cap V}\to\mathcal O\_U\|_{U\cap V}\\) satisfying \\(\pi\_U=\varphi\_{UV}\circ\pi\_V\\). In fact, \\(\varphi\_{UV}\\) is unique because \\(\pi\_V\\) is surjective and hence epic; for example, this forces \\(\varphi\_{UU}=\mathrm{id}\\) for each \\(U\\). This uniqueness also automatically implies that these comparison isomorphisms satisfy the cocycle condition, so we may glue the local sheaves \\(\mathcal O\_U\\) into a sheaf \\(\mathcal L\\), which is a line bundle because it is locally free. (One way to do this gluing is to first define \\(\mathcal L\\) as a sheaf on the base of open subsets contained in an open subset in \\(\mathcal U\\).)

    Now, the surjections \\(\pi\_U\colon\mathcal O\_U^{n+1}\to\mathcal O\_U\\) are (by construction) compatible with the isomorphisms \\(\varphi\_{UV}\\), so they glue to a morphism \\(\pi\colon\mathcal O\_X^{n+1}\to\mathcal L\\). (One way to see this is that the \\(\pi\_U\\)s first define a morphism of sheaves on a base, which then uniquely extends to a morphism of sheaves.) The map \\(\pi\\) is locally a surjection, so it is surjective and thus provides an element of \\(\mathcal P(X)\\).

0. For fixed \\(X\\), and we claim that the map \\(\mathcal Q^+(X)\to\mathcal P(X)\\) is well-defined. Namely, we need to show that the class in \\(\mathcal P(X)\\) does not depend on the choice of representative \\((\pi\_U)\\); for example, changing the isomorphism class of \\(\pi\_U\\) does nothing to our construction except adjust the local isomorphisms throughout.

    Now, by definition \\(\mathcal Q^+(X)\\), it is enough to check that the output in \\(\mathcal P(X)\\) does not change if we pass to a refinement of \\((\pi\_U)\_{U\in\mathcal U}\\), say \\((\pi\_{U'})\_{U'\in\mathcal U'}\\). For example, passing to a refinement merely restricts the comparison isomorphisms, so the same line bundle \\(\mathcal L\\) can be used as the outcome of the gluing. Similarly, the surjection \\(\pi\colon\mathcal O\_X^{n+1}\to\mathcal L\\) can be uniquely described by its restriction to any base, so the open subsets contained in an open subset of \\(\mathcal U'\\) will do just fine to determine it.

Lastly, we need to check that our maps are inverse. Fix a scheme \\(X\\).

- We claim that the composite \\(\mathcal P(X)\to\mathcal Q^+(X)\to\mathcal P(X)\\) is the identity. Well, starting from \\(\pi\colon\mathcal O\_X^{n+1}\to\mathcal L\\), we chose a trivializing open cover to produce an element in \\(\mathcal Q^+(X)\\). This trivializing open cover can then be glued straight back to the original line bundle \\(\mathcal L\\) and surjection, so the map \\(\mathcal Q^+(X)\to\mathcal P(X)\\) returns the original map \\(\pi\\).

- We claim that the composite \\(\mathcal Q^+(X)\to\mathcal P(X)\to\mathcal Q^+(X)\\) is the identity. Well, starting from some tuple \\((\pi\_U)\_{U\in\mathcal U}\\), we glued these to a surjection \\(\pi\colon\mathcal O\_X^{n+1}\to\mathcal L\\). But \\(\mathcal U\\) is a trivializing open cover for \\(\mathcal L\\) by its construction, and the construction of \\(\mathcal L\\) implies that the induced local surjection \\(\mathcal O\_U^{n+1}\to\mathcal L\|\_U\cong\mathcal O\_U\\) (for \\(U\in\mathcal U\\)) is exactly \\(\pi\_U\\). Thus, passing through the map \\(\mathcal P(X)\to\mathcal Q^+(X)\\) returns \\((\pi\_U)\_U\\) again. \\(\blacksquare\\)

> **Remark 31.**
It is not obvious from the above proof, but the sheafification map \\(\mathcal Q\to\mathcal P\\) is the natural embedding. Indeed, one takes a surjection \\(\pi\colon\mathcal O\_X^{n+1}\to\mathcal O\_X\\) to the natural one-element tuple \\((\pi)\\) in \\(\mathrm{\check H}^0(\\{X\\};\mathcal Q)\\). The construction of the map \\(\mathcal Q^+(X)\to\mathcal P(X)\\) then allows us to take this tuple back to the surjection \\(\pi\\).

> **Remark 32.**
There are easier ways to show that \\(\mathcal P\\) is the sheafification of \\(\mathcal Q\\). For example, there is already a natural embedding \\(\mathcal Q\subseteq\mathcal P\\), and one can directly show that \\(\mathcal P\\) is a sheaf without too much trouble (see Lemma 33). Then one can argue as in the proof of Theorem 27 to show that \\(\mathcal P\\) is the sheafification, once we argue that elements of \\(\mathcal P\\) are locally given by elements of \\(\mathcal Q\\). (Namely, we should prove a version of Lemma 24 by hand.)

Intermission
--

We promised that the previous section would not be logically necessary to our story, so let's directly show the only piece we will need. We know that \\(\mathcal Q\\) is a separated presheaf, but it fails to be a sheaf. The argument of Proposition 12 suggests that \\(\mathcal Q\\) is missing surjections onto sheaves which are not globally free but merely locally free. This provides alternative motivation for Definition 29, which defines the presheaf \\(\mathcal P\colon\mathrm{Sch}^{\mathrm{op}}\to\mathrm{Set}\\) by defining \\(\mathcal P(X)\\) to be the collection of isomorphism classes of surjections \\(\mathcal O\_X^{n+1}\to\mathcal L\\), where \\(\mathcal L\\) is a line bundle on \\(X\\).

> **Lemma 33.**
The presheaf \\(\mathcal P\\) is a Zariski sheaf.

*Proof.*
Let \\(\mathcal U\\) be an open cover of a scheme \\(X\\), so we want to show that the natural map
\\[\mathcal P(X)\to\operatorname{eq}\left(\prod\_{U\in\mathcal U}\mathcal P(U)\rightrightarrows\prod\_{U,V\in\mathcal U}\mathcal P(U\cap V)\right)\\]
is an isomorphism. The same argument as in Remark 11 shows that this map is injective, once one replaces the scalars \\(c\_U\\) with elements of \\(\operatorname{Hom}\_U(\mathcal L\|\_U,\mathcal M\|\_U)\\). Technically, Remark 11 only grants a global map \\(\mathcal L\to\mathcal M\\) by gluing, but this global map automatically upgrades to a surjection by compatibility with \\(\pi\\) and \\(\tau\\), which then automatically upgrades to an isomorphism by checking locally.

Thus, we are interested in checking the surjectivity of our natural map. We will be brief, but the moral is that line bundles can be glued into line bundles. We are given a family of surjections \\(\pi\_U\colon\mathcal O\_U^{n+1}\to\mathcal L\_U\\) which are isomorphic on the intersections. The isomorphisms on intersections are compatible with the surjections, which then uniquely defines them because surjections are epimorphisms. This uniqueness can be used to show that the isomorphisms on intersections satisfy the cocycle condition, so we can glue the \\(\mathcal L\_U\\)s into a line bundle \\(\mathcal L\\) on \\(X\\). The compatible surjections \\(\pi\_U\\) now glue into a surjection \\(\pi\colon\mathcal O\_X^{n+1}\to\mathcal L\\), which is the desired surjection element of \\(\mathcal P(X)\\). \\(\blacksquare\\)

Representability
--

Our next goal is to show that \\(\mathcal P\\) is represented by a scheme. As mentioned previously, it is in general difficult to prove such a result, but there are some general tools in our situation. Roughly speaking, we will be able to find an "open cover" \\(\mathcal P\\) by schemes, which then implies that \\(\mathcal P\\) is actually given by a scheme.

To make this precise, we will use the current section to say something about open covers of (pre)sheaves. To start, we should define an open embedding.

> **Definition 34.**
Fix a morphism \\(\eta\colon\mathcal F\to\mathcal G\\) of presheaves on a category \\(\mathcal C\\). Then \\(\eta\\) is *representable* if and only if the following holds: for each object \\(T\in\mathcal C\\) and morphism \\(h\_T\to\mathcal G\\), the pullback \\(h\_T\times\_{\mathcal G}\mathcal F\\) is isomorphic to \\(h\_S\\) for some \\(S\in\mathcal C\\). Given a class of morphisms \\(\mathcal M\subseteq\operatorname{Mor}\mathcal C\\) stable under isomorphisms, we say that \\(\eta\\) is *representable by \\(\mathcal M\\)* if and only if \\(\eta\\) is representable, and the induced map
\\[h\_S\cong h\_T\times\_{\mathcal G}\mathcal F\to h\_T\\]
comes from a morphism \\(S\to T\\) in \\(\mathcal M\\) (via the embedding of Corollary 6).

> **Example 35.**
Suppose the category \\(\mathcal C\\) admits finite limits. Given a morphism \\(S\to T\\) in \\(\mathcal C\\), we claim that \\(h\_S\to h\_T\\) is representable. Indeed, for any morphism \\(h\_{T'}\to h\_T\\), there is an induced map \\(T'\to T\\). The embedding of Corollary 6 preserves limits (which can be checked with some effort, using the fact that limits in \\(\mathrm{PSh}(\mathcal C)\\) are computed pointwise), so we conclude that
\\[h\_{T'}\times\_{h\_T}h\_S=h\_{T'\times\_TS}.\\]

> **Example 36.**
Because the class of open embeddings (of schemes) is preserved by base-change, an open embedding \\(U\subseteq X\\) induces a morphism \\(h\_U\to h\_X\\) which is representable by open embeddings.

In light of Example 36, it makes sense to take an "open embedding of presheaves" to mean a morphism which is representable by open embeddings. Here are some additional facts about morphisms representable by open embeddings.

> **Lemma 37.**
Suppose \\(\eta\colon\mathcal F\to\mathcal G\\) is representable by open embeddings. Then \\(\eta\\) is monic.

*Proof.*
We will show that the fiber over any \\(t\in\mathcal G(T)\\) in \\(\mathcal F(T)\\) has at most one element. Well, by the Yoneda lemma, \\(t\\) corresponds to a morphism \\(h\_T\to\mathcal G\\), and an element of the fiber amounts to a lifting of this morphism to \\(h\_T\to\mathcal F\\). Each choice of lift then uniquely induces a morphism
\\[h\_T\to h\_T\times\_{\mathcal G}\mathcal F.\\]
(Conversely, such a morphism uniquely induces a lift \\(h\_T\to\mathcal F\\).) But \\(h\_T\times\_{\mathcal G}\mathcal F\\) is represented by an open subscheme \\(U\\) of \\(T\\). Thus, it is now enough to note that the open embedding \\(U\to T\\) admits at most one section \\(T\to U\\). \\(\blacksquare\\)

> **Lemma 38.**
Suppose \\(\eta\colon\mathcal F\to\mathcal G\\) is representable by open embeddings. If \\(\mathcal G\\) is a sheaf, then \\(\mathcal F\\) is a sheaf.

*Proof.*
We proceed directly. Let \\(\mathcal U\\) be an open cover of \\(X\\), and we want to show that the natural map
\\[\mathcal F(X)\to\operatorname{eq}\left(\prod\_{U\in\mathcal U}\mathcal F(U)\rightrightarrows\prod\_{U,V\in\mathcal U}\mathcal F(U\cap V)\right)\\]
is an isomorphism. It is at least injective because everything in sight embeds into \\(\mathcal G\\) by Lemma 37 (because limits commute with limits), and \\(\mathcal G\\) is a sheaf.

It remains to show that the natural map is surjective. Choose a tuple \\((x\_U)\\) in the equalizer, which we would like to lift to \\(\mathcal F(X)\\). Because \\(\mathcal G\\) is a sheaf, the elements \\((\eta(x\_U))\_{U\in\mathcal U}\\) glue to an element \\(y\in\mathcal G(X)\\). We must show that \\(y\\) lifts to an element of \\(\mathcal F(X)\\); because \\(\eta\\) is monic, any lift will do.

To show the lifting, note that the Yoneda lemma lets us view \\(y\\) as a morphism \\(h\_X\to\mathcal G\\). Then set \\(X'\\) to be the open subscheme of \\(X\\) representing \\(h\_X\times\_{\mathcal G}\mathcal F\\), and we would like to show that \\(X'=X\\). Well, for each \\(U\in\mathcal U\\), we know that \\(y\|\_U\in\mathcal G(U)\\) is the image of \\(x\_U\in\mathcal F(U)\\), so the corresponding map \\(y\|\_U\colon h\_U\to\mathcal G\\) factors through \\(\mathcal F\\) and hence through \\(X'\\). Thus, \\(X'\\) contains each \\(U\in\mathcal U\\), so \\(X'=X\\). \\(\blacksquare\\)

Here is our notion of an open cover.

> **Definition 39.**
Fix a presheaf \\(\mathcal F\colon\mathrm{Sch}^{\mathrm{op}}\to\mathrm{Set}\\). Then a collection of sub-presheaves \\(\mathcal U\\) is an *open cover* if and only if the following holds: for each scheme \\(T\\) and morphism \\(h\_T\to\mathcal F\\),
> - for each \\(\mathcal F'\in\mathcal U\\), the fiber product \\(h\_T\times\_{\mathcal F}\mathcal F'\\) is represented by an open subscheme \\(T\_{\mathcal F'}\subseteq T\\), and
> - the open subschemes \\(\\{T\_{\mathcal F'}\\}\\) form an open cover of \\(T\\).

> **Example 40.**
An open cover \\(\mathcal U\\) of a scheme \\(X\\) induces an open cover \\(\\{h\_U\\}\_U\\) of \\(h\_X\\). Indeed, pulling back by any map \\(T\to X\\) induces open embeddings \\(U\times\_XT\to T\\) as in Example 36, and the disjoint union
\\[\bigsqcup\_{U\in\mathcal U}U\times\_XT\to T\\]
is surjective because surjections are preserved by base-change.

Morally speaking, we can glue sheaves from open covers. One cannot expect to do such gluing with presheaves (or even separated presheaves) because they are not determined locally.

> **Lemma 41.**
Fix a Zariski sheaf \\(\mathcal F\\) with an open cover \\(\mathcal U\\). Then, in the category of sheaves,
\\[\mathcal F=\operatorname{coeq}\left(\bigsqcup\_{\mathcal F',\mathcal F'{}'\in\mathcal U}\mathcal F'\times\_{\mathcal F}\mathcal F'{}'\rightrightarrows\bigsqcup\_{\mathcal F'\in\mathcal U}\mathcal F'\right).\\]
Here, the two maps are given by the left and right projections.

This is easy to see in the category of schemes (basically by the definition of an open cover), but it will require some work in our generality. For example, the Yoneda lemma does not preserve colimits in general.

*Proof.*
Enumerate \\(\mathcal U\\) as \\(\\{\mathcal F\_i\\}\_i\\) for clarity. Note that there are already natural maps \\(\mathcal F\_i\to\mathcal F\\) for each \\(\mathcal F\_i\to\mathcal F\\), and the diagram
\\[\bigsqcup\_{i,j}\mathcal F\_i\times\_{\mathcal F}\mathcal F\_j\rightrightarrows\bigsqcup\_{i}\mathcal F\_i\to\mathcal F\\]
commutes by definition of the fiber product. Thus, it remains to check the universal property.

Choose a sheaf \\(\mathcal G\\) along with morphisms \\(\varphi\_i\colon\mathcal F\_i\to\mathcal G\\) which agree on the fiber products. We would like to show that there is a unique morphism \\(\varphi\colon\mathcal F\to\mathcal G\\) commuting with the \\(\varphi\_i\\)s. To this end, choose a scheme \\(X\\), and we will try to determine the map \\(\mathcal F(X)\to\mathcal G(X)\\).

As such, let's start with some \\(x\in\mathcal F(X)\\). Then we receive an induced map \\(h\_X\to\mathcal F\\). By definition of an open cover, \\(h\_X\times\_{\mathcal F}\mathcal F\_i\\) is represented by an open subscheme \\(U\_i\\) of \\(X\\), and \\(\\{U\_i\\}\_i\\) is an open cover of \\(X\\). By the naturality of the Yoneda lemma, the composite \\(U_i\subseteq X\to\mathcal F\\) corresponds to \\(x\|\_{U\_i}\\), so we see that \\(x\|\_{U\_i}\\) actually lifts to an element \\(x\_i\in\mathcal F\_i(U\_i)\\). The moral is that the map \\(\varphi\\) is required to have
\\[\varphi\_X(x)\|\_{U\_i}=\varphi\_{U\_i}(x\|\_{U\_i})=\varphi\_i(x\_i)\\]
for each \\(i\\). Because \\(\mathcal G\\) is a sheaf (and in particular separated), this uniquely determines \\(\varphi\_X(x)\\).

We can actally use the previous paragraph to construct \\(\varphi\_X\colon\mathcal F(X)\to\mathcal G(X)\\). Continue with \\(x\in\mathcal F(X)\\). Because the elements \\(x\_i\\) agree on projections to the fiber product (because they are just restrictions of \\(x\\)), the elements \\(\varphi\_i(x\_i)\\) will also agree on intersections (by hypothesis on the morphisms \\(\varphi\_i\\)). Thus, we may glue the \\(\varphi\_i(x\_i)\\)s into a genuine element \\(\varphi\_X(x)\in\mathcal G(X)\\).

We have thus far defined maps \\(\varphi\_X\colon\mathcal F(X)\to\mathcal G(X)\\), but we should check naturality. Choose a morphism \\(f\colon Y\to X\\) and some \\(x\in\mathcal F(X)\\); we want to show \\(\varphi(f^\*x)=f^\*\varphi(x)\\). Let \\(\\{U\_i\\}\\) be the induced open cover of \\(X\\) with \\(x\_i\in\mathcal F(U\_i)\\) as before. Now, for each \\(i\\), pulling back the composite \\(U\_i\subseteq X\to\mathcal F\\) along \\(f\\), we find that \\(h\_Y\times\_{\mathcal F}\mathcal F\_i\\) is represented by \\(f^{-1}U\_i\\). Accordingly, \\(f^\*x\|\_{f^{-1}U\_i}\\) is represented by the element \\(f^\*x\_i\in\mathcal F\_i\left(f^{-1}U\_i\right)\\), and
\\[\varphi(f^\*x)\|\_{f^{-1}U\_i}=\varphi\_i(f^\*x\_i)=f^\*\varphi\_i(x\_i)=(f^\*\varphi(x))\|\_{U\_i},\\]
where the middle equality follows because \\(\varphi\_i\\) is a sheaf morphism. The desired equality now follows because \\(\mathcal G\\) is separated. \\(\blacksquare\\)

> **Remark 42.**
The proof of this lemma does not use the fact that \\(\mathcal F\\) is a sheaf in order to construct or show uniqueness of the morphism \\(\mathcal F\to\mathcal G\\). (We repeatedly use that \\(\mathcal G\\) is separated for the uniqueness of the map, and we use the fact that \\(\mathcal G\\) is a sheaf once in the construction.) But of course, for \\(\mathcal F\\) to be the coequalizer in the category of sheaves, it must actually be a sheaf!

We are now ready to state our target tool.

> **Theorem 43.**
Let \\(\mathcal F\\) be a Zariski sheaf. Suppose that \\(\mathcal F\\) admits an open cover \\(\mathcal U\\), and each \\(\mathcal F'\in\mathcal U\\) is represented by a scheme. Then \\(\mathcal F\\) is represented by a scheme.

Intuitively, sheaves should be determined by their local properties, so we are saying that a sheaf which is "locally" a scheme can glue this property to make the original sheaf "globally" a scheme.

*Proof.*
The main point is the constuction of the scheme. Enumerate \\(\mathcal U\\) as \\(\\{\mathcal F\_i\\}\_i\\) for clarity, and for each \\(i\\), let \\(U\_i\\) represent \\(\mathcal F\_i\\). By Lemma 41, we basically want to find a scheme \\(X\\) which admits an open cover by \\(\\{U\_i\\}\\) with the "same" intersections. Thus, we need to do some gluing, which we do in two steps.

1. We construct the gluing data. By definition of the open cover, the map \\(\mathcal F\_i\times\_{\mathcal F}\mathcal F\_j\to\mathcal F\_i\\) is represented by some open subscheme \\(U\_{ij}\subseteq U\_i\\). Then for each \\(i\\) and \\(j\\), there is a canonical identification
\\[U\_{ij}\stackrel{\mathrm{pr}\_i}\cong\mathcal F\_i\times\_{\mathcal F}\mathcal F\_j\stackrel{\mathrm{pr}\_j}\cong U\_{ji},\\]
which we call \\(\varphi\_{ji}\\). (In other words, \\(\varphi\_{ji}\colon U\_{ij}\to U\_j\\) is induced by a projection.) For example, \\(U\_{ii}=U\_i\\) and \\(\varphi\_{ii}=\mathrm{id}\\) by construction.

2. To glue these open subschemes along these intersections, we must check a cocycle condition. This is basically automatic. Fix indices \\(i\\), \\(j\\), and \\(k\\). Then each of \\(U\_{ij}\cap U\_{ik}\\) and \\(U\_{ji}\cap U\_{jk}\\) and \\(U\_{ki}\cap U\_{kj}\\) is canonically isomorphic to \\(\mathcal F\_i\times\_{\mathcal F}\mathcal F\_j\times\_{\mathcal F}\mathcal F\_k\\) via the various projections. For example,
\\[\begin{align}U\_{ij}\cap U\_{ik} &= U\_{ij}\times\_{U_i}\times U\_{ik} \\\\ 
&= (\mathcal F\_i\times\_{\mathcal F}\mathcal F\_j)\times\_{\mathcal F\_i}(\mathcal F\_i\times\_{\mathcal F}\mathcal F\_k) \\\\ 
&= \mathcal F\_i\times\_{\mathcal F}\mathcal F\_j\times\_{\mathcal F}\mathcal F\_k,\end{align}\\]
where the last isomorphism follows by formal properties of the fiber product. (Notably, the second isomorphism is given by projecting along the isomorphism \\(\mathcal F\_i\to U\_i\\), so we can see the composite isomorphism from the bottom to the top is given by this projection.) From here, the cocycle condition follows because the various comparison isomorphisms between our three open sets are all compatible with the canonical isomorphism to \\(\mathcal F\_i\times\_{\mathcal F}\mathcal F\_j\times\_{\mathcal F}\mathcal F\_k\\) (as we just checked).

Thus, we have a scheme \\(X\\) which admits an open cover by \\(\\{U\_i\\}\\), and the intersection inclusion \\(U\_i\cap U\_j\subseteq U\_i\\) is isomorphic to the inclusion \\(U\_{ij}\subseteq U\_i\\), which is isomorphic to the projection \\(\mathcal F\_i\times\_{\mathcal F}\mathcal F\_j\to\mathcal F\_i\\). Thus, the coequalizer diagram
\\[\bigsqcup\_{i,j}U\_i\cap U\_j\rightrightarrows\bigsqcup\_iU\_i\to X\\]
of Lemma 41 (see Example 40) is isomorphic to the coequalizer diagram
\\[\bigsqcup\_{i,j}\mathcal F\_i\times\_{\mathcal F}\mathcal F\_j\rightrightarrows\bigsqcup\_i\mathcal F\_i\to\mathcal F\\]
of Lemma 41 (again). It follows that \\(h\_X\cong\mathcal F\\), and we are done! \\(\blacksquare\\)

> **Remark 44.**
We only used the hypothesis that \\(\mathcal F\\) is a sheaf when applying Lemma 41. In particular, the construction of the candidate scheme \\(X\\) did not use the sheaf condition.

> **Remark 45.**
The proof of Theorem 43 is "effective" in the sense that it explicitly constructs the representing scheme (by gluing).

Back to \\(\mathbb P^n\_{\mathbb Z}\\)
--

We are now ready to show that there is a scheme representing our sheaf \\(\mathcal P\\).

> **Proposition 46.**
The sheaf \\(\mathcal P\\) is representable.

*Proof.*
Recall that \\(\mathcal P\\) is a sheaf by Proposition 30 or Lemma 33. Thus, by Theorem 43, it is enough to show that \\(\mathcal P\\) admits an open cover by representable (open) subsheaves.

To this end, fix an index \\(i\in\\{0,1,\ldots,n+1\\}\\) for now, and define the presheaf \\(\mathcal P\_i\\) to take a scheme \\(X\\) to the set of surjections \\(\pi\in\mathcal P(X)\\) such that the composite
\\[\mathcal O\_X\stackrel{\iota\_i}\hookrightarrow\mathcal O\_X^{n+1}\stackrel\pi\to\mathcal L\\]
is surjective, where the left map is the inclusion into the \\(i\\)th coordinate. Note that the \\(i\\)th coordinate being surjective is preserved by pullback, so \\(\mathcal P\_i\\) is in fact a sub-presheaf.

To apply Theorem 43, we now must show that each \\(\mathcal P\_i\\) is representable and that they assemble into an open cover of \\(\mathcal P\\).

- Let's start by checking that \\(\mathcal P\_i\\) is representable, where \\(i\\) is still fixed. For ease of notation, take \\(i=0\\), and we claim that \\(\mathcal P\_i\\) is represented by the affine scheme \\(\operatorname{Spec}\mathbb Z[x\_1,\ldots,x\_n]\\). Indeed, for any scheme \\(X\\), the universal property of affine schemes gives
    \\[\operatorname{Mor}\_{\mathrm{Sch}}(X,\operatorname{Spec}\mathbb Z[x\_1,\ldots,x\_n])=\operatorname{Hom}(\mathbb Z[x\_1,\ldots,x\_n],\mathcal O\_X(X)),\\]
    which is then equivalent to the data of \\(n\\) global sections \\(\\{s\_1,\ldots,s\_n\\}\\) of \\(\mathcal O\_X\\) (by taking the image of the \\(x\_i\\)s). This then produces the surjection \\((1,s\_1,\ldots,s\_n)\colon\mathcal O\_X^{n+1}\to\mathcal O\_X\\) in \\(\mathcal P\_i(X)\\). Here are our checks on this construction.

    - These maps \\(\eta\_X\colon h\_{\operatorname{Spec}\mathbb Z[x\_1,\ldots,x\_n]}(X)\to\mathcal P\_i(X)\\) are functorial in the scheme \\(X\\). Indeed, choose a morphism \\(f\colon Y\to X\\) and \\((s\_1,\ldots,s\_n)\in h\_{\operatorname{Spec}\mathbb Z[x\_1,\ldots,x\_n]}(X)\\). On one hand, \\(\eta(f^\*(s\_1,\ldots,s\_n))\\) is the surjection \\((1,f^\sharp s\_1,\ldots,f^\sharp s\_n)\\). On the other hand, \\(f^\*\eta(s\_1,\ldots,s\_n)\\) is the surjection \\(f^\*(1,s\_1,\ldots,s\_n)\\). These agree by construction of the pullback.

    - The maps \\(\eta\_X\colon h\_{\operatorname{Spec}\mathbb Z[x\_1,\ldots,x\_n]}(X)\to\mathcal P\_i(X)\\) are injective. Indeed, if the two surjections \\((1,s\_1,\ldots,s\_n)\\) and \\((1,t\_1,\ldots,t\_n)\\) are isomorphic, then there is an isomorphism \\(\sigma\colon\mathcal O\_X\to\mathcal O\_X\\) for which \\((1,s\_1,\ldots,s\_n)=\sigma\circ(1,t\_1,\ldots,t\_n)\\). The first coordinate forces \\(\sigma=1\\), so the two surjections are actually equal.

    - The maps \\(\eta\_X\colon h\_{\operatorname{Spec}\mathbb Z[x\_1,\ldots,x\_n]}(X)\to\mathcal P\_i(X)\\) are surjective. This is a little trickier. Choose some \\(\pi\colon\mathcal O\_X^{n+1}\to\mathcal L\\) in \\(\mathcal P\_i(X)\\). The main claim is that \\(\pi\circ\iota\_i\\) is an isomorphism: we may check this on affines, where \\(\pi\circ\iota\_i\\) is a surjection of projective modules of rank one over a local ring. The kernel of this map is also projective, but it must have rank zero, so it vanishes. Thus, \\(\pi\circ\iota\_i\\) is injective (on affines) and hence an isomorphism.

        To use the main cain claim, we adjust \\(\pi\\) by the isomorphism \\(\pi\circ\iota\_i\colon\mathcal O\_X\to\mathcal L\\). Thus, we may assume that \\(\mathcal L=\mathcal O\_X\\) and that \\(\pi\circ\iota\_i\\) is the identity. The remaining coordinates of \\(\pi\colon\mathcal O\_X^{n+1}\to\mathcal O\_X\\) are given by some choice of global section, so \\(\pi\\) now takes the form \\((1,s\_1,\ldots,s\_n)\\) for some global sections \\(\\{s\_1,\ldots,s\_n\\}\\).

- Continue with \\(i\\) fixed. We claim that the map \\(\mathcal P\_i\to\mathcal P\\) is representable by open embeddings. Indeed, choose a test scheme \\(X\\) and a map \\(h\_X\to\mathcal P\\), which in turn corresponds to some \\(\pi\colon\mathcal O\_X^{n+1}\to\mathcal L\\) in \\(\mathcal P(X)\\). Let \\(U\_i\subseteq X\\) be the subspace of \\(p\in X\\) where \\(\pi\circ\iota\_i\\) is surjective at \\(p\\). We will show that \\(U\_i\\) is open and that \\(U\_i=X\times\_{\mathcal P}\mathcal P\_i\\), which will complete the proof of the claim.

    - Let's check that \\(U\_i\\) is open. Choose some \\(p\in U\_i\\), and we need to find an open neighborhood of \\(p\\) contained in \\(U\_i\\). This is a local problem, so we may shrink \\(X\\). In paritcular, we may assume that \\(X\\) is affine—say \\(X=\operatorname{Spec}A\\)—and that \\(\mathcal L\\) is trivial, and we go ahead and identify \\(\mathcal L\\) with \\(\mathcal O\_X\\). Then \\(\pi\\) corresponds to a surjective map \\(A^{n+1}\to A\\), and the composite \\(\pi\circ\iota\_i\\) is surjective at the prime \\(p\\).

        Now, let \\(e\_i\in A^{n+1}\\) be the \\(i\\)th basis vector, so we are given tha \\(\pi(e\_i)\\) is a unit in \\(A\_p\\). In particular, \\(\pi(e\_i)\in A\\) is not a zero-divisor, so we may use the open subset \\(D(\pi(e\_i))\subseteq\operatorname{Spec}A\\): for each \\(q\in D(\pi(e\_i))\\) (such as \\(p\\)), we know that \\(\pi(e\_i)\\) is a unit in \\(A\_q\\), so \\((\pi\circ\iota\_i)\_q\\) is surjective, so \\(q\in U\_i\\).

    - We check that \\(U\_i=X\times\_{\mathcal P}\mathcal P\_i\\). By its construction as a union of distinguished affine open subsets in the previous point, \\(\pi\|\_{U\_i}\in\mathcal P\_i(U\_i)\\), which provides the needed projection \\(U\_i\to\mathcal P\_i\\). Indeed, choose a test scheme \\(T\\) equipped with maps \\(t\colon T\to X\\) and \\(T\to\mathcal P\_i\\) which agree in \\(\mathcal P\\). We would like to show that \\(t\colon T\to X\\) factors through \\(U\_i\\): the factorization is unique because the map \\(U\_i\subseteq X\\) is monic, and the composite \\(T\to U\_i\to\mathcal P\_i\\) must be the given map \\(T\to\mathcal P\_i\\) because the map \\(\mathcal P\_i\to\mathcal P\\) is also monic.

        Now, to show that \\(t\colon T\to X\\) factors through \\(U\_i\\), we should show that \\(t(p)\in U\_i\\) for each \\(p\\), meaning that \\((\pi\circ\iota\_i)\_{t(p)}\\) is surjective. Well, the map \\(T\to\mathcal P\\) is given by the surjection \\(t^\*\pi\in\mathcal P(T)\\), which we know is actually in the image of \\(\mathcal P\_i(T)\\). Thus, \\(t^\*\pi\circ\iota\_i\\) is surjective, so it is surjective at every point, so \\(\operatorname{im} t\subseteq U\_i\\) follows.

- Lastly, we need to check that the maps \\(\mathcal P\_i\to\mathcal P\\) assemble into an open cover as \\(i\\) varies. We will have to use Nakayama's lemma. Choose a scheme \\(X\\) along with a morphism \\(\pi\colon h\_X\to\mathcal P\\), and then define the open subscheme \\(U\_i\subseteq X\\) for each \\(i\\) as in the previous check. We must show that \\(\\{U\_i\\}\_i\\) covers \\(X\\).

    In other words, for each point \\(p\in X\\), we must show that the surjection \\(\pi\_p\colon\mathcal O\_p^{n+1}\to\mathcal L\_p\\) is surjective on some coordinate. Now, let \\(\\{e\_0,\ldots,e\_n\\}\\) be the basis vectors of \\(\mathcal O\_p^{n+1}\\). Then the elements
    \\[\\{\pi(e\_0),\ldots,\pi(e\_n)\\}\\]
    generate \\(\mathcal L\\), so they span \\(\mathcal L\_p/\mathfrak m_p\mathcal L\_p\\). The latter module is a vector space (over \\(\mathcal O\_p/\mathfrak m\_p\\)) of dimension one, so one of the elements \\(\pi(e\_i)\\) forms a basis. By Nakayama's lemma (!), this element lifts to a generator of \\(\mathcal L\_p\\), which means that \\(\pi\circ\iota\_i\\) is surjective at \\(p\\), as desired. \\(\blacksquare\\)

We could now simply define \\(\mathbb P^n\_{\mathbb Z}\\) to be the scheme constructed by Proposition 46. This then makes the proof of Theorem 1 obvious, once we remember that the data of \\(n+1\\) global sections of a line bundle \\(\mathcal L\\) is the data of a map \\(\mathcal O\_X^{n+1}\to\mathcal L\\), and saying that the global sections have no common zero is the same as saying that the map is surjective (by Nakayama's lemma).

Of course, this is not an honest proof because \\(\mathbb P^n\_{\mathbb Z}\\) admits a more classical definition by gluing affines. Let's compare these two definitions of \\(\mathbb P^n\_{\mathbb Z}\\).

*Proof of Theorem 1.*
Let \\(X\\) be the scheme constructed from Proposition 46, which we would like to show is isomorphic to \\(\mathbb P^n\_{\mathbb Z}\\). We will use Theorem 43 to describe \\(X\\) explicitly by gluing.
- For each \\(i\in\\{0,1,\ldots,n+1\\}\\), we have an open subscheme \\(U\_i\subseteq X\\) isomorphic to \\(\mathbb A^n\_{\mathbb Z}\\). We write \\(U\_i\\) as \\(\operatorname{Spec}\mathbb Z[x\_{0/i},\ldots,x\_{n/i}]\\) for psychological reasons, where \\(x\_{i/i}\\) is understood to be \\(1\\). By unwinding the proof of representability in Proposition 46, we find that the map \\(U\_i\to X\\) corresponds to the surjection
\\[(x\_{0/i},\ldots,x\_{n/i})\colon\mathcal O\_{U\_i}^{n+1}\to\mathcal O\_{U\_i},\\]
where we recall \\(x\_{i/i}=1\\).

- Next, let's compute the intersections. As in the proof of Proposition 46, the intersection \\(U\_{ij}=U\_i\times\_{X}U\_j\\) embedded in \\(U\_i\\) is exactly the locus where the surjection \\((x\_{0/i},\ldots,x\_{n/i})\\) is surjective in the \\(j\\)th coordinate. This is equivalent to \\(x\_{j/i}\\) being a unit, so we conclude that
\\[U\_{ij}=D(x\_{j/i})=\operatorname{Spec}\mathbb Z[x\_{0/i},\ldots,x\_{n/i},1/x\_{j/i}].\\]

- Lastly, we compute the transition maps. Namely, we should compute the map \\(U\_{ij}\to U\_j\\), which we know is an isomorphism onto \\(U\_{ji}\\). To this end, we note that the surjection \\((x\_{0/i},\ldots,x\_{n/i})\\) is isomorphic to the surjection \\((x\_{0/i}/x\_{j/i},\ldots,x\_{n/i}/x\_{j/i})\\) over \\(U\_{ij}\\). By the proof of Proposition 46, we see that this surjection has its \\(j\\)th coordinate equal to one and thus corresponds to the ring map
\\[\mathbb Z[x\_{0/j},\ldots,x\_{n/j}]\to\mathbb Z[x\_{0/i},\ldots,x\_{n/i},1/x\_{j/i}]\\]
defined by \\(x\_{k/j}\mapsto x\_{k/i}/x\_{j/i}\\), which in turn defines the desired transition map \\(U\_{ij}\to U\_j\\).

The above gluing data is exactly the usual construction of \\(\mathbb P^n\_{\mathbb Z}\\)! Thus, \\(X\cong\mathbb P^n\_{\mathbb Z}\\). \\(\blacksquare\\)

One indication that we have built a robust theory is that it is now not so hard to prove related results. We close the post with sketches of two such applications.

> **Remark 47.**
One can discuss Grassmannians using essentially the same arguments. For positive integers \\(d\\) and \\(n\\) with \\(d\le n\\), here are the relevant statements.
> - The sheafification of the presheaf taking a scheme \\(X\\) to the set of isomorphism classes of surjections \\(\mathcal O\_X^n\to\mathcal O\_X^d\\) is the sheaf \\(\operatorname{Gr}\_{n,d}\\) taking a scheme \\(X\\) to the set of isomorphism classes of surjections \\(\mathcal O\_X^n\to\mathcal E\\), where \\(\mathcal E\\) is a vector bundle on \\(X\\) of rank \\(d\\).
> - The sheaf \\(\operatorname{Gr}\_{n,d}\\) is representable. In fact, it admits an open covering by the affine schemes \\(\mathbb A\_{\mathbb Z}^{d(n-d)}\\).

> **Remark 48.**
Fix a vector bundle \\(\mathcal E\\) on a scheme \\(S\\), and consider the presheaf \\(\mathbb P\mathcal E\\) taking a scheme \\(X\\) to the data of a morphism \\(f\colon X\to S\\), a line bundle \\(\mathcal L\\) on \\(X\\), and a surjection \\(\pi\colon f^\*\mathcal E\to\mathcal L\\) (up to isomorphism). Then \\(\mathbb P\mathcal E\\) is representable.
> 
> Here is a sketch of an argument. One can adapt Lemma 33 to show that \\(\mathbb P\mathcal E\\) is a sheaf, so by Theorem 43, it remains to find a suitable open cover. Choose a trivializing open cover \\(\mathcal U\\) of \\(S\\) for \\(\mathcal E\\). Then for each \\(U\in\mathcal U\\), there is a natural map
\\[\mathbb P^{\operatorname{rank}\mathcal E}\_{\mathbb Z}\times U\cong\mathbb P(\mathcal E\|\_U)\to\mathbb P\mathcal E\\]
representable by open embeddings, and these maps form an open cover of \\(\mathbb P\mathcal E\\).