---
title: "Extensions of Schur's Lemma"
date: 2026-1-23
author_profile: false
permalink: /posts/2026/1/schur-dixmier-quillen/
tags:
  - algebra
  - representation theory
---

We discuss some generalizations of Schur's lemma.

In this post, all algebras are associative and unital, but they need not be commutative. Here is the classical statement of Schur's lemma.

> **Proposition 1** (Schur's lemma)**.**
Fix an algebra \\(A\\) over a field \\(k\\), and let \\(M\\) be an irreducible \\(A\\)-module.
>   0. Then \\(\operatorname{End}_A(M)\\) is a division algebra.
>   0. If \\(M\\) is finite-dimensional, then each \\(T\in\operatorname{End}_A(M)\\) is algebraic over \\(k\\).

*Proof.*
We quickly explain how the second part follows from the first. Given that \\(M\\) is finite-dimensional over \\(k\\), it follows that \\(\operatorname{End}_A(M)\\) is a finite-dimensional division algebra over \\(k\\). Thus, for each \\(T\in\operatorname{End}_A(M)\\), we see that \\(k(T)\subseteq\operatorname{End}_A(M)\\) is some finite-dimensional field extension of \\(k\\), so \\(T\\) is algebraic over \\(k\\).

It remains to show the first part, for which we should show that any nonzero endomorphism \\(T\\) of \\(M\\) is invertible. It is enough to show that \\(T\\) is invertible as a \\(k\\)-linear map because then the inverse is automatically \\(A\\)-equivariant. Now, to show that \\(T\\) is invertible, it is enough to show that it has trivial kernel and cokernel. But this follows from irreducibility: \\(\ker T\\) and \\(\operatorname{im}T\\) are both \\(A\\)-submodules of \\(M\\) and thus must equal all of \\(M\\) by the irreducibility of \\(M\\). \\(\blacksquare\\)

> **Remark 2.**
To relate the second part to the usual formulation of Schur's lemma, note that if \\(k\\) is algebraically closed, then \\(T\in k\\) is forced. It then follows that \\(\operatorname{End}_A(M)=k\\).

This post will be interested in when the second conclusion holds without assuming that \\(M\\) is finite-dimensional. This setting is frequently of interest when studying the representation theory of non-compact topological groups (such as non-compact Lie groups or \\(p\\)-adic groups). Here is the standard example explaining why some size condition may be necessary.

> **Example 3.**
Consider the algebra \\(A=\mathbb C(x)\\) over the field \\(k=\mathbb C\\). Then the module \\(M=A\\) is irreducible over \\(A\\) because \\(A\\) is a field, but
\\[\operatorname{End}_A(M)=\mathbb C(x).\\]

> **Remark 4.**
Here is another indication that size plays a role: if \\(M\\) is small, then \\(\operatorname{End}_A(M)\\) automatically becomes smaller and hence closer to being \\(k\\). More precisely, we claim that
\\[\dim_k\operatorname{End}_A(M)\stackrel?\le\dim_kM.\\]
To see this, choose any nonzero vector \\(v\in M\\), and we claim that the map \\(\operatorname{ev}_v\colon\operatorname{End}_A(M)\to M\\) given by \\(\operatorname{ev}_v\colon T\mapsto Tv\\) is injective. Indeed, if \\(\operatorname{ev}_vT=0\\), then \\(Tv=0\\), so \\(\ker T\subseteq M\\) is a nonzero submodule, so \\(\ker T=M\\) because \\(M\\) is irreducible, so \\(T=0\\).

The problem in Example 3 turns out to be that \\(\mathbb C(x)\\) is a very large vector space.

> **Lemma 5.**
Fix a field \\(k\\). Then
\\[\dim_kk(x)=\left\|k\right\|+\aleph_0.\\]

*Proof.*
Note that \\(\dim_kk(x)\le\left\|k\right\|+\aleph_0\\) because \\(k(x)\\) has cardinality at most \\(\left\|k\right\|+\aleph_0\\). Indeed, by decomposing rational polynomials into numerators and denominators, the cardinality of \\(k(x)\\) is at most \\(k[x]\times k[x]\\), and the cardinality of \\(k[x]\\) is simply \\(\left\|k\right\|+\aleph_0\\) because \\(k[x]\\) can be identified with the countable union of finite products of \\(k\\).

It remains to show the other inequality, for which it is enough to check that \\(\left\|k\right\|\le\dim_kk(x)\\) and \\(\aleph_0\le\dim_kk(x)\\). Certainly \\(\aleph_0\le\dim_kk(x)\\) because \\(k(x)\\) contains the linearly independent elements \\(\left\\{1,x,x^2,\ldots\right\\}\\). For the other inequality, it is enough to check that the elements
\\[\left\\{\frac1{x-c}:c\in k\right\\}\\]
are linearly independent. Well, any relation
\\[\sum_{i=1}^n\frac{a_i}{x-c_i}=0\\]
can have its denominator cleared to show that \\(x\\) is the root of some nonzero polynomial in \\(k[x]\\), which is a contradiction. \\(\blacksquare\\)

We are now ready to state the usual generalization of Schur's lemma, which is Dixmier's lemma.

> **Proposition 6** (Dixmier's lemma)**.**
Fix an algebra \\(A\\) over a field \\(k\\), and let \\(M\\) be an irreducible \\(A\\)-module. Suppose that \\(\dim_kM<\left\|k\right\|\\). Then any \\(T\in\operatorname{End}_A(M)\\) is algebraic over \\(k\\).

*Proof.*
We proceed by contraposition. Suppose that we have an \\(A\\)-endomorphism \\(T\\) of \\(M\\) which is transcendental over \\(k\\); we will show that \\(\dim_kM\ge\left\|k\right\|\\). By Remark 4 and Lemma 5, it is enough to show that
\\[\dim_kk(x)\stackrel?\le\dim_k\operatorname{End}_A(M),\\]
for which it is enough to exhibit an embedding \\(k(x)\to\operatorname{End}_A(M)\\). We claim that we may define such a ring map by sending \\(x\mapsto T\\), which is then automatically injective because \\(k(x)\\) is a field. Now, to show that the canonical ring map \\(k[x]\to\operatorname{End}_A(M)\\) given by \\(x\mapsto T\\) extends to \\(k(x)\\), we have to show that the map is injective on \\(k[x]\\). This follows because \\(T\\) is transcendental over \\(k\\). \\(\blacksquare\\)

<!-- In other words, we have to show that \\(T\\) is transcendental over \\(k\\). Well, given a polynomial \\(p(x)\\) with \\(p(T)=0\\), we see that the subspace
\\[k[T]\cdot v\subseteq M\\]
is finite-dimensional for any \\(v\in M\\). It follows that \\(T\\) admits an eigenvalue \\(c\\) while acting on \\(k[T]\cdot v\\), so \\(T-c\operatorname{id}_M\\) has nontrivial kernel, so \\(T-c\operatorname{id}_M=0\\) because \\(M\\) is irreducible, so \\(T=c\operatorname{id}_M\\), which is a contradiction to the construction of \\(T\\). \\(\blacksquare\\) -->

> **Remark 7.**
Here is a convenient way to check the dimension condition in Proposition 6. We claim that any irreducible \\(A\\)-module \\(M\\) has \\(\dim_kM\le\dim_kA\\). Indeed, it is enough to exhibit a surjection \\(A\to M\\), which we define as follows: fix any nonzero vector \\(v\in M\\), and then we can define \\(A\to M\\) by \\(a\mapsto av\\). To see that this map is surjective, we note that its image is an \\(A\\)-submodule of \\(M\\) and therefore must be all of \\(M\\).

Here is the usual application of Proposition 6.

> **Example 8.**
Fix a finite-dimensional Lie algebra \\(\mathfrak g\\) over \\(\mathbb C\\). Then \\(U\mathfrak g\\) is an algebra with countable dimension, so Remark 7 implies that any irreducible representation has at most countable dimension. We conclude from Proposition 6 (and Remark 2) that
\\[\operatorname{End}_{\mathfrak g}(M)=\mathbb C\\]
for any irreducible representation \\(M\\) of \\(\mathfrak g\\).

Of course, Proposition 6 has nothing to say about Lie algebras over \\(\overline{\mathbb Q}\\), which is somewhat surprising because one would expect that the representation theory over \\(\overline{\mathbb Q}\\) and \\(\mathbb C\\) would be basically the same. Descending to \\(\overline{\mathbb Q}\\) will require a bit more work.

> **Remark 9.**
Here is an approach which does not work: fix \\(k=\overline{\mathbb Q}\\), and choose an algebra \\(A\\) over \\(k\\). Then one may try to prove \\(\operatorname{End}\_A(M)=k\\) for all irreducible \\(A\\)-modules \\(M\\) of at most countable dimension by base-changing along an embedding \\(\overline{\mathbb Q}\to\mathbb C\\) and then applying Proposition 6. But this cannot work because the claim that \\(\operatorname{End}\_A(M)=k\\) is not always true: one can take \\(A=M=k(x)\\), as in Example 3. The reason why this approach fails is because \\(M\_{\mathbb C}\\) need not be irreducible (and is not irreducible in the given counterexample).

Instead, we will follow Quillen. In contrast to Proposition 6, we will gain some control on sizes via a filtration.

> **Definition 10.**
An algebra \\(A\\) over a field \\(k\\) is *filtered* if and only if it admits an exhaustive, multiplicative, increasing filtration \\(\\{F^iA\\}_{i\in\mathbb N}\\) for which \\(k\subseteq F^0A\\).

> **Proposition 11** (Quillen's lemma)**.**
Fix a filtered algebra \\(A\\) over a field \\(k\\). Suppose that \\(\operatorname{gr}A\\) is finitely generated and commutative over \\(k\\). Then any \\(T\in\operatorname{End}_A(M)\\) is algebraic over \\(k\\).

> **Example 12.**
We extend Example 8 to \\(\overline{\mathbb Q}\\). Fix a finite-dimensional Lie algebra \\(\mathfrak g\\) over \\(\overline{\mathbb Q}\\). By the Poincaré–Birkoff–Witt theorem, the natural degree filtration on \\(U\mathfrak g\\) makes \\(\operatorname{gr}U\mathfrak g\\) into a polyomial ring generated by a basis of \\(\mathfrak g\\). It follows from Proposition 11 (and Remark 2) that
\\[\operatorname{End}_{\mathfrak g}(M)=\overline{\mathbb Q}\\]
for any irreducible representation \\(M\\) of \\(\mathfrak g\\).

The proof of Proposition 11 is based on the following result from commutative algebra.

> **Theorem 13** (Generic freeness)**.**
Fix a Noetherian domain \\(R\\), and let \\(S\\) be an algebra of finite type over \\(R\\). For any finitely generated \\(S\\)-module \\(M\\), there is a nonzero \\(f\in R\\) such that \\(M_f\\) is free over \\(R_f\\).

*Proof.*
The idea is to use Noether normalization to reduce to the case where \\(S\\) is a polynomial ring over \\(R\\) and \\(M=S\\). Quickly, we remark that we may localize all objects in sight by a nonzero element of \\(R\\) at any point and not adjust the validity of the conclusion.

0. Set \\(K\\) to be the fraction field of \\(R\\). We will proceed by induction on the Krull dimension \\(d\\) of \\(S_K\\), which we note is finite by Noether normalization (indeed, \\(S_K\\) is of finite type over \\(K\\)). For the base case, we note that if \\(S_K=0\\), then because \\(S\\) is finite type over \\(R\\), there is a nonzero \\(f\in R\\) for which \\(S_f=0\\), so it follows that \\(M_f=0\\), as required.

0. We reduce to the case where \\(S\\) is a polynomial ring over \\(R\\). We now apply Noether normalization, which grants elements \\(x_1,\ldots,x_d\\) of \\(S_K\\) such that \\(K[x_1,\ldots,x_d]\subseteq S_K\\) is a polynomial ring, and \\(S_K\\) is finite over \\(K[x_1,\ldots,x_d]\\). By clearing denominators in \\(S_K\\), we may assume that the \\(x_\bullet\\)s live in \\(S\\).

    We now hunt for some nonzero \\(c\in R\\) so that \\(S_c\\) is finite over \\(R_c[x_1,\ldots,x_d]\\). Then \\(M_c\\) will continue to be finitely generated over \\(R_c[x_1,\ldots,x_d]\\), meaning that we have indeed reduced to the case where \\(S_c\\) is a polynomial ring over \\(R_c\\). To find this \\(c\\), we write \\(S=R[s_1,\ldots,s_n]\\) for some elements \\(s_\bullet\in S\\). Each \\(s_i\\) is integral over \\(K[x_1,\ldots,x_d]\\) and therefore satisfies a monic polynomial with coefficients in \\(K[x_1,\ldots,x_d]\\). Clearing denominators, we see that \\(s_i\\) satisfies some polynomial with coefficients in \\(R[x_1,\ldots,x_d]\\) whose leading coefficient is in \\(R\\). Then let \\(c\\) be the product of all the leading coefficients (to a sufficiently high power), and we find that \\(s_i\\) will be integral over \\(R_c[x_1,\ldots,x_d]\\). It follows that \\(S_c\\) is finite type and integral over \\(R_c[x_1,\ldots,x_d]\\) and therefore finite.

0. We reduce to the case where \\(M\\) takes the form \\(S/\mathfrak q\\) for a prime \\(\mathfrak q\\) of \\(S\\). By the theory of associated primes, \\(M\\) admits a filtration
\\[0=M_0\subseteq M_1\subseteq M_2\subseteq\cdots\subseteq M_m=M\\]
for which \\(M_i/M_{i+1}\cong S/\mathfrak q_i\\) for some prime \\(\mathfrak q_i\\) of \\(S\\) for each \\(i\\). Because an extension by a free module is free (recall that free modules are projective), and localization is exact, it is enough to establish the claim for each quotient \\(M_i/M_{i+1}\\), so we have reduced to the case where \\(M\\) takes the form \\(S/\mathfrak q\\) for a prime \\(\mathfrak q\\).

0. We complete the proof, using the reductions of the previous steps. There are now two cases.
    - If \\(\mathfrak q\\) is nonzero, then \\(\dim(S/\mathfrak q)_K<\dim S_K\\) (note that \\(S\\) is a polynomial ring). Thus, we may replace \\(S\\) with \\(S/\mathfrak q\\) and conclude by the induction.
    - If \\(\mathfrak q=0\\) so that \\(M=S\\), then we are already done because the polynomial ring \\(S\\) is of course free over \\(R\\). \\(\blacksquare\\)

*Proof of Proposition 11.*
We may as well take \\(T\ne0\\). Because \\(\operatorname{End}\_A(M)\\) is a division algebra (by Proposition 1), we see that \\(k[T]\subseteq\operatorname{End}\_A(M)\\) is an integral domain. Eventually, we will show that \\(k[T]\\) is in fact a field, which we now note will complete the proof: then \\(1/T\in k[T]\\), so there is a polynomial \\(p(x)\in k[x]\\) for which \\(Tp(T)-1=0\\), which implies that \\(T\\) is algebraic.

We now proceed in steps.
0. We apply generic freeness. For any nonzero \\(v\in M\\), irreducibility implies that \\(Av=M\\). It follows that setting
\\[F^iM=k[T]\cdot F^iA\cdot v\\]
makes \\(M\\) into a finitely generated filtered module over \\(k[T]\otimes_kA\\). It follows that \\(\operatorname{gr}M\\) is finitely generated as a module over \\(k[T]\otimes_k\operatorname{gr}A\\) (by construction of the filtration), so Theorem 13 yields a nonzero \\(f\in k[T]\\) for which \\((\operatorname{gr}M)_f\\) is free over \\(k[T]_f\\).

0. We convert the freeness of \\((\operatorname{gr}M)_f\\) into a statement about \\(k[T]\\). Because localization is exact, we see that \\((\operatorname{gr}M)_f=\operatorname{gr}M_f\\), where \\(M_f\\) has been given the obvious (localized) filtration. By choosing generators of \\(\operatorname{gr}M_f\\) and arguing as in Lemma 8 of [this post](/posts/2025/11/filter-algebra/), we find that \\(M_f\\) is free over \\(k[T]_f\\).

    Now, because \\(\operatorname{End}_A(M)\\) is a division algebra, we find that the fraction field \\(k(T)\\) naturally acts on \\(M\\), so \\(M_f=M\\). In fact, because \\(k(T)\\) is a field, we see that \\(M\\) is a direct sum of copies of \\(k(T)\\) as a \\(k(T)\\)-module and hence as a \\(k[T]_f\\)-module. It follows that \\(k(T)\\) is a direct summand of a free \\(k[T]_f\\)-module, so \\(k(T)\\) is free as a \\(k[T]_f\\)-module because \\(k[T]_f\\) is a principal ideal domain. (Here, \\(k[T]_f\\) is a principal ideal domain because it is a localization of a principal ideal domain.)

0. We now complete the proof. Thus far, we have shown that \\(k(T)\\) is free as a \\(k[T]_f\\)-module, and we want to show that \\(k[T]\\) is a field. Well, any two nonzero elements \\(p_1(T)/q_1(T)\\) and \\(p_2(T)/q_2(T)\\) of \\(k(T)\\) will admit a relation over \\(k[T]_f\\), so it follows that \\(k(T)\\) is free over \\(k[T]_f\\) of rank \\(1\\). Thus, the natural ring map
\\[k[T]_f\cong k(T)\\]
is an isomorphism. It follows that \\(\dim k[T]_f=0\\), so \\(\dim k[T]=0\\), so \\(k[T]\\) is a zero-dimensional principal ideal domain, so \\(k[T]\\) is a field. \\(\blacksquare\\)