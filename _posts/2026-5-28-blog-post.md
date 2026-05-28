---
title: "Curves Over a Field"
date: 2026-5-28
author_profile: false
permalink: /posts/2026/5/curves/
tags:
  - algebraic geometry
---

We classify curves over a field.

Our arguments will follow those in Vakil. Throughout, a variety is a reduced separated scheme of finite type over a field, and a curve is a one-dimensional variety. Here is today's target.

> **Theorem 1.**
Fix a field \\(k\\). Then the following categories are equivalent.
> - The category of regular projective integral curves over \\(k\\), with morphisms given by surjections.
> - The category of integral curves over \\(k\\), with morphisms given by dominant rational maps.
> - The opposite category of finitely generated field extensions of \\(k\\) of transcendence degree \\(1\\).

The equivalence of the bottom two categories is rather formal.

> **Proposition 2.**
Fix a field \\(k\\). Then the following categories are equivalent.
> - The category of integral varieties over \\(k\\), with morphisms given by dominant rational maps.
> - The opposite category of finitely generated field extensions of \\(k\\).
> 
> Furthermore, the equivalence sends varieties of dimension \\(d\\) to field extensions of transcendence degree \\(d\\).

*Proof.*
Given an integral variety \\(X\\), then the stalk \\(K(X)\\) at the generic point is a field extension. Furthermore, a dominant rational map \\(f\colon X\to Y\\) necessarily maps the generic point to the generic point, so we induce a map \\(f^\sharp\colon K(Y)\to K(X)\\). Taking stalks is functorial, so we have defined a functor from the first point to the second. Here are our checks on this functor.
- Essentially surjective: for any finitely generated \\(k\\)-algebra \\(K\\), choose a finite set \\(S\\) of generators. Then \\(k[S]\\) is a finitely generated integral \\(k\\)-algebra, so \\(\operatorname{Spec}k[S]\\) is a suitable (affine) variety with the desired fraction field.
- Faithful: suppose two dominant rational maps \\(f,g\colon X\to Y\\) induce the same map on the fraction fields. We want to show that \\(f\\) and \\(g\\) agree on some open subscheme. Well, we may assume that \\(X\\) and \\(Y\\) are affine, say \\(\operatorname{Spec}B\\) and \\(\operatorname{Spec}A\\), respectively. Then \\(f\\) and \\(g\\) are uniquely determined by the induced algebra map \\(A\to B\\), but this map is the same for both \\(f\\) and \\(g\\) by hypothesis.
- Full: choose an algebra map \\(\varphi\colon K(X)\to K(Y)\\), which we would like to realize by a dominant rational map. Once again, we may assume that \\(X=\operatorname{Spec}B\\) and \\(Y=\operatorname{Spec}A\\). If \\(\varphi(A)\subseteq B\\), then we get a map on the associated affine schemes and win. To arrange this, note that \\(A\\) is finitely generated over \\(k\\) by some subset \\(S\subseteq A\\), so we may write \\(\varphi(s)=b\_s/b'\_s\\) for some \\(b\_s\\) and \\(b\_s'\\) in \\(B\\) for each \\(s\in S\\). Note that \\(b\_s'\ne0\\) for each \\(s\\), so \\(\varphi(S)\\) lives in the localization \\(B\_b\\), where \\(b=\prod\_sb'\_s\\). Replacing \\(Y\\) with \\(D(b)\\) completes this check.

The above checks show that we have an equivalence. The last sentence of the proposition follows because the dimension of an integral variety equals the dimension of its fraction field, and the dimension of the fraction field equals the transcendence degree. \\(\blacksquare\\)

The equivalence of the first two categories in Theorem 1 will require more work. There is certainly an inclusion from the first category to the second, so the difficulty lies in checking that it has good properties. In particular, it is not obvious that the inclusion is full or essentially surjective.

For example, for essential surjectivity, we need to be able to produce regular curves, so it will be useful to have an easy test for regularity. However, it is not too hard to achieve normality by simply passing to the normalization. Accordingly, we will use the following piece of commutative algebra.

> **Lemma 3.**
Fix a Noetherian local domain \\((A,\mathfrak m)\\) of dimension one. Then the following are equivalent.
> 1. \\(A\\) is a discrete valuation ring.
> 1. \\(A\\) is normal.
> 1. \\(\mathfrak m\\) is principal.
> 1. \\(A\\) is regular.

*Proof.*
We show the implications in sequence. This proof is long but only because there are many things to show.
- We show 1 implies 2. Suppose \\(A\\) is a discrete valuation ring with valuation \\(v\\). Rescale the valuation so that \\(v(A)=\mathbb Z\\). Then we claim that \\(A\\) is a unique factorization domain, which will complete the proof. Choose a uniformizer \\(\varpi\\) with \\(v(\varpi)=1\\). Then any \\(a\in A\\) either has \\(a/\varpi\in A\\) or \\(v(a)=0\\) (and so \\(a\in A^\times\\)), so \\((\varpi)\\) is the unique maximal ideal of \\(A\\), so \\(\varpi\\) is prime. Now, any \\(a\in A\\) can be written as \\[a=u\varpi^n\\] where \\(n=v(a)\\), which provides our factorization. For uniqueness, note that \\(u\varpi^n=u'\varpi^{n'}\\) implies \\(n=n'\\) by taking valuations and so \\(u=u'\\) by dividing.

- We show 2 implies 3. This is pretty tricky. Choose any nonzero \\(a\in\mathfrak m\\), which we would like to normalize into a generator of \\(\mathfrak m\\). Then \\(A/(a)\\) is a zero-dimensional Noetherian local ring with maximal ideal \\(\mathfrak m/(a)\\). Thus, \\(\mathfrak m/(a)\\) is the only prime, so it is the nilradical, so some power vanishes. Let \\(N\\) be the least nonnegative integer for which \\(\mathfrak m^N\subseteq(a)\\). Note \\(N>0\\) because \\(a\\) is not a unit.

  Now, choose any \\(b\in\mathfrak m^{N-1}\setminus(a)\\), and we will show that \\(a/b\\) generates \\(\mathfrak m\\). It is enough to show \\((b/a)\mathfrak m=A\\). On one hand, \\(b\mathfrak m\subseteq\mathfrak m^N\subseteq(a)\\), so \\((b/a)\mathfrak m\subseteq A\\).
  
  For the other inclusion, note \\((b/a)\mathfrak m\\) is an ideal of \\(A\\), so it is enough to show that \\((b/a)\mathfrak m\not\subseteq\mathfrak m\\). Well, \\(b\notin(a)\\) means \\(b/a\notin A\\), so \\(b/a\\) cannot even be integral over \\(A\\) by normality! But \\((b/a)\mathfrak m\subseteq\mathfrak m\\) would imply that \\(\mathfrak m\\) is a faithful, finitely generated module over \\(A[b/a]\\), forcing \\(b/a\\) to be integral, which is a contradiction.

- We show 3 and 4 are equivalent. Note \\(A\\) is regular so that \\(\dim_{A/\mathfrak m}\mathfrak m/\mathfrak m^2=1\\). So if \\(\mathfrak m\\) is principal, generated by \\((\varpi)\\), then \\(\mathfrak m/\mathfrak m^2\\) is spanned by \\((\varpi)\\) and is so one-dimensional. The converse follows from Nakayama's lemma, which explains that a basis of \\(\mathfrak m/\mathfrak m^2\\) lifts to a set of generators.

- We show 3 implies 1. We would like to use the valuation
\\[v(a):=\max\\{n\in\mathbb N:a\in\mathfrak m^n\\}.\\]
Quickly, note that \\(\bigcap_{n}\mathfrak m^n=0\\) by Nakayama's lemma (because this ideal multiplied by \\(\mathfrak m\\) is itself); thus, \\(v(a)\\) is finite when \\(a\\) is nonzero.

  To check that \\(v\\) has good properties, we claim that \\((a)=\mathfrak m^{v(a)}\\). This immediately implies that \\(v(a+b)\ge\min\\{v(a),v(b)\\}\\) and \\(v(ab)=v(a)+v(b)\\) for \\(a,b\in A\\), thereby completing the proof.
  
  It remains to show the claim. Certainly \\(a\in\mathfrak m^{v(a)}\\) by construction, so \\((a)\subseteq\mathfrak m^{v(a)}\\). For the converse, choose a generator \\(\varpi\\) of \\(\mathfrak m\\). Then \\(a\in\mathfrak m^{v(a)}\\) implies that \\(a/\varpi^{v(a)}\in A\\), but \\(a\notin\mathfrak m^{v(a)+1}\\) implies that \\(a/\varpi^{v(a)}\notin\mathfrak m\\). Thus, \\(a/\varpi^{v(a)}\in A^\times\\), so \\((a)=(\varpi)^{v(a)}\\), and the claim follows. \\(\blacksquare\\)

This is all that we will say about the essential surjectivity check for now. For the fullness check, we basically need to check that one can extend rational maps to genuine morphisms. Over curves, this is the following piece of algebraic geometry.

> **Proposition 4.**
Fix a base field \\(k\\). Let \\(C\\) be a curve, and let \\(Y\\) be a projective variety. For any normal point \\(x\in C\\), any morphism \\(C\setminus\\{x\\}\to Y\\) extends to a morphism \\(C\to Y\\).

*Proof.*
This follows from the valuative criteria of properness, but we will give a direct argument. The idea is to arrange ourselves into a position where we can "clear denominators" in the definition of our morphism \\(\varphi\colon C\setminus\\{x\\}\to Y\\). Accordingly, we have many reductions.
1. By gluing morphisms, we may at any point pass to an open neighborhood of \\(x\\). For example, we may assume that \\(C\\) is affine and connected.
1. We reduce to the case \\(Y=\mathbb P^n\\). Start by choosing an embedding \\(Y\subseteq\mathbb P^n\\). Then we are given an extension of \\(\varphi\colon C\setminus\\{x\\}\to\mathbb P^n\\) to a map \\(\widetilde\varphi\colon C\to\mathbb P^n\\). We will be done if \\(\widetilde\varphi\\) factors through \\(Y\\). Well, by shrinking \\(C\\), we may assume that \\(\widetilde\varphi\\) outputs to a standard affine open subset \\(\mathbb A^n\subseteq\mathbb P^n\\). Then any function vanishing on \\(Y\cap\mathbb A^n\\) pulls back (via \\(\widetilde\varphi\\)) to a function vanishing on \\(C\setminus\\{x\\}\\) and in particular on all generic points of \\(C\\), so these functions must actually fully vanish on \\(C\\), so \\(C\\) maps to \\(Y\\).
1. We choose a special uniformizer at \\(x\\). (We will use this to clear denominators.) Because \\(x\\) is a normal point, \\(\mathcal O\_x\\) is a discrete valuation ring by Lemma 3; thus, we may choose a uniformizer \\(\varpi\in\mathcal O\_x\\). By shrinking \\(C\\), we may assume that \\(\varpi\\) is actually a global function on \\(C\\). Note that the zero set \\(V(\varpi)\\) is a proper closed subset (containing \\(x\\)), so it is zero-dimensional, so it is finite; by further shrinking \\(C\\), we may assume that \\(V(\varpi)=\\{x\\}\\).
1. We explicate \\(\varphi\\). Because \\(\varphi\\) is a morphism to projective space, it is given by a choice of line bundle \\(\mathcal L\\) on \\(C\\) and \\((n+1)\\) sections \\(\\{s\_0,\ldots,s\_n\\}\\) which do not vanish simultaneously anywhere on \\(C\setminus\\{x\\}\\). By shrinking \\(C\\), we may assume that \\(\mathcal L=\mathcal O_C\\).

We now complete the proof. By the last step, the sections \\(\\{s\_0,\ldots,s\_n\\}\\) are some regular functions on \\(C\\), and they fail to vanish simultaneously on \\(C\setminus\\{p\\}\\). We can now divide out these sections by
\\[t^{\min_i\\{v\_x(s\_i)\\}}.\\]
This does not change the subspace spanned by these sections over \\(C\setminus\\{p\\}\\) because \\(t\\) is a unit there, so we have not changed the morphism \\(\varphi\\). However, there is not a section \\(s\_i\\) with \\(v\_x(s\_i)=0\\), so the sections do not simultaneously vanish at \\(x\\), so \\(\varphi\\) extends to a map on \\(C\\)! \\(\blacksquare\\)

We are now ready to prove Theorem 1.

*Proof of Theorem 1.*
The bottom two categories are equivalent by Proposition 2, so it is enough to show that the top two categories are equivalent. There is a natural inclusion functor, which we would like to show is an equivalence.
- Faithful: if two surjective morphisms \\(f,g\colon X\to Y\\) agree as rational maps, then they agree on an open subset. But these are varieties, so they locus where they agree is a closed subset of \\(X\\), so \\(f=g\\) follows.

- Full: fix a dominant rational map \\(f\colon X\to Y\\) of regular projective curves. We would like to show that \\(f\\) extends to a surjective morphism. Well, \\(f\\) is already defined over an open subset \\(U\subseteq X\\), which is cofinite because \\(X\\) is a curve. Thus, one can inductively use Proposition 4 to extend \\(f\\) to a dominant morphism \\(X\to Y\\). (Notably, all points are regular and hence normal by Lemma 3.) Lastly, \\(f\\) is surjective because \\(X\\) is projective and hence proper, which implies that the image of \\(f\\) must be closed.

- Essentially surjective: we need to show that any integral curve \\(C\\) is birational to a smooth projective one. We start by passing to an affine open subset of \\(C\\), which means that there is a closed embedding \\(C\subseteq\mathbb A^n\\). Thus, there is a locally closed embedding \\(C\subseteq\mathbb P^n\\). Then \\(C\\) is open in its closure, so we may pass from \\(C\\) to the closure, making \\(C\\) projective.

  Lastly, let \\(X\\) be the normalization of \\(C\\). On affine open subschemes, this process is given by taking the normalization in the fraction field, so \\(X\to C\\) does not change the fraction field, so \\(X\to C\\) is birational by Proposition 2. Furthermore, \\(X\to C\\) is finite and hence projective, so \\(X\\) is projective. Lastly, \\(X\\) being normal implies that \\(X\\) is regular by Lemma 3. \\(\blacksquare\\)
