---
title: "Multiquadratic Extensions"
date: 2025-1-20
author_profile: false
permalink: /posts/2026/1/multiquadratic/
tags:
  - number theory
  - galois theory
---

Following Kummer theory, we calculate the Galois group of multiquadratic extensions of \\(\mathbb Q\\).

I would guess that this argument is well-known, but I had a little trouble extracting it directly online, so I figured it would not be an injustice to write it down.

> **Proposition 1.**
Let \\(S\\) be a finite set of distinct primes. Then
\\[\operatorname{Gal}\left(\mathbb Q(\\{\sqrt p:p\in S\\})/\mathbb Q\right)\cong(\mathbb Z/2\mathbb Q)^{\\#S}.\\]

*Proof.*
Our goal is to turn this Galois theory problem into group cohomology.

Let's set up some notation. Set \\(K=\mathbb Q(\\{\sqrt p:p\in S\\})\\) and \\(G=\operatorname{Gal}(\overline Q/\mathbb Q)\\) for brevity. For each prime \\(p\\), let \\(\chi_p\colon G\to\\{\pm1\\}\\) denote the quadratic character given by the composite
\\[G=\operatorname{Gal}(\overline{\mathbb Q}/\mathbb Q)\twoheadrightarrow\operatorname{Gal}(\mathbb Q(\sqrt p)/\mathbb Q)\cong\\{\pm1\\}.\\]
It will also be useful to define \\(\chi\colon G\to\\{\pm1\\}^{\\#S}\\) by \\(\chi=(\chi_p)_{p\in S}\\).

We now proceed in steps.
0. We turn the theorem into a group theory problem. Here is the main point: by intersecting Galois subgroups via the Galois correspondence, we note that \\(K\\) is exactly the fixed field of
\\[\bigcap_{p\in S}\ker\chi_p\subseteq G.\\]
As such, \\(\operatorname{Gal}(\overline Q/K)\\) equals \\(\ker\chi\\). Thus, \\(\chi\\) descends to an injection
\\[\chi\colon\operatorname{Gal}(K/\mathbb Q)\to\\{\pm1\\}^{\\#S}.\\]
To prove the theorem, it is enough to show that \\(\chi\\) is a bijection, which is a group theory problem.

0. We turn the theorem into a linear algebra problem: we claim that it is enough to check that the characters \\(\\{\chi_p\\}_{p\in S}\\) are linearly independent in the \\(\mathbb F_2\\)-vector space \\(\operatorname{Hom}_{\mathrm{cts}}(G,\\{\pm1\\})\\).

    We proceed by contraposition. If \\(\chi\\) fails to be bijective, then it fails to be surjective, so its image lives in some hyperplane of \\(\\{\pm1\\}^{\\#S}\\). Such a hyperplane is cut out by an equation, which yields some equation
    \\[\prod_{p\in S}\chi_p^{a_p}=1,\\]
    where each \\(a_p\\) is in \\(\mathbb F_2\\). This equation is exactly the failure of linear independence.

0. We do a little group cohomology. We are interested in the position of some elements in the cohomology group
\\[\operatorname{Hom}\_{\mathrm{cts}}(G,\\{\pm1\\})=\mathrm H^1\_{\mathrm{cts}}(G;\\{\pm1\\}).\\]
As such, we take Galois cohomology of the Kummer short exact sequence
\\[1\to\\{\pm1\\}\to\overline{\mathbb Q}^\times\stackrel 2\to\overline{\mathbb Q}^\times\to1\\]
to show that the boundary morphism
\\[\delta\colon\mathbb Q^\times\to\mathrm H^1\_{\mathrm{cts}}(G;\\{\pm1\\})\\]
is surjective. (We have silently used Hilber't theorem 90, which asserts \\(\mathrm H^1\_{\mathrm{cts}}(G;\overline{\mathbb Q}^\times)=0\\).) Thus, there is an isomorphism
\\[\mathbb Q^\times/\mathbb Q^{\times2}\cong\mathrm H^1\_{\mathrm{cts}}(G;\\{\pm1\\}),\\]
so we will be able to pass to the more controlled \\(\mathbb F_2\\)-vector space \\(\mathbb Q^\times/\mathbb Q^{\times2}\\).

0. We complete the proof. The main point is to show that \\(\delta(p)=\chi_p\\). Indeed, the boundary map \\(\delta\\) sends \\(p\\) to the \\(1\\)-cocycle
\\[\delta(p)\colon\sigma\mapsto\frac{\sigma(\sqrt p)}{\sqrt p},\\]
which is exactly \\(\chi_p\\): our \\(\sigma\\) goes to \\(1\\) if and only if it fixes \\(\sqrt p\\).

    To complete the proof, we see that the previous step now allows us to merely prove that the elements \\(\\{p\\}_{p\in S}\\) are linearly independent in \\(\mathbb Q^\times/\mathbb Q^{\times2}\\), which is automatic from unique prime factorization in \\(\mathbb Q\\). \\(\blacksquare\\)

> **Remark 2.**
The proposition admits a straightforward generalization where primes are replaced by any set of pairwise coprime integers. Essentially the same proof works.

> **Remark 3.**
Here is an alternative, sillier way to solve the linear algebra problem. Note that
\\[\operatorname{Hom}\_{\mathrm{cts}}(G;\\{\pm1\\})=\operatorname{Hom}\_{\mathrm{cts}}(G^{\mathrm{ab}};\\{\pm1\\}).\\]
By the Kronecker–Weber theorem, this is isomorphic to
\\[\operatorname{Hom}\_{\mathrm{cts}}(\widehat{\mathbb Z}^\times,\\{\pm1\\}).\\]
We can now show linear independence in this latter vector space. In [this post](/posts/2025/11/quadratic-dirichlet/), we showed that the Galois character \\(\chi_p\\) corresponds to a quadratic Dirichlet character \\((\mathbb Z/4p\mathbb Z)^\times\to\\{\pm1\\}\\). In particular, away from \\(2\\), the \\(\chi_p\\)s are supported on different factors of
\\[\operatorname{Hom}\_{\mathrm{cts}}(\widehat{\mathbb Z}^\times,\\{\pm1\\})=\prod_p\operatorname{Hom}\_{\mathrm{cts}}(\mathbb Z_p^\times,\\{\pm1\\}),\\]
so linear independence follows.

> **Remark 4.**
The given proof of Theorem 1 is essentially an application of Kummer theory, so it will generalize well to handle cyclic (or even abelian) extensions with enough roots of unity in the base field. In contrast, Remark 3 is essentially an application of class field theory, so it could conceivably generalize to handle arbitrary abelian extensions.