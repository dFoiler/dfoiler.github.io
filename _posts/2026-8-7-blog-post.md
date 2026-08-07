---
title: "Matsushima's Criterion"
date: 2026-8-7
author_profile: false
permalink: /posts/2026/8/matsushima-criterion/
tags:
  - algebraic geometry
  - representation theory
  - algebraic topology
---

Matsushima's criterion states that, for a reductive group \\(G\\), a subgroup \\(H\\) is reductive if and only if the quotient \\(G/H\\) is affine.

In fact, we will show only a small part of this result for simplicity in the arguments. See Remarks 9–11 for how to remove some of the extraneous assumptions, which we will not do in order to ease exposition.

> **Theorem 1** (Matsushima's criterion)**.**
Let \\(G\\) be a connected reductive group over \\(\mathbb C\\), and let \\(H\subseteq G\\) be a connected algebraic subgroup. If \\(G/H\\) is affine, then \\(H\\) is reductive.

Notably, we are assuming that the quotient \\(G/H\\) exists as a variety. We remark that it satisfies \\(G/H(\mathbb C)=G(\mathbb C)/H(\mathbb C)\\), which follows from its construction. For example, Milne's book discusses quotients of groups by subgroups.

While we're here, we note that the "converse" direction of Theorem 1 is also true.

> **Theorem 2** (Geometric invariant theory)**.**
Let \\(G\\) be a reductive group over a field \\(k\\) acting on an affine variety \\(X\\). Then there is a categorical quotient \\(X/\\!\\!/G\\) in the category of schemes, and it is affine.

> **Remark 3.**
In fact, \\(X/\\!\\!/G\\) is the affine scheme associated to the algebra of \\(G\\)-invariants of \\(\Gamma(X;\mathcal O_X)\\).

The proof of Theorem 2 is rather long and technical, perhaps the subject of a future blog post. Anyway, in the context of Theorem 1, by letting \\(H\\) act on \\(G\\) by the group multiplication, we see that \\(G/H\\) is affine when \\(H\\) is reductive.

We will prove Theorem 1 using techniques from algebraic topology. The key input will be the following.

> **Notation 4.**
For an algebraic variety \\(X\\) over \\(\mathbb C\\), we define \\(m(X)\\) to be the largest index \\(i\\) for which the \\(i\\)th Betti cohomology group \\(\mathrm H^i(X(\mathbb C);\mathbb C)\\) is nonzero.

> **Proposition 5.**
Let \\(G\\) be a connected affine algebraic group over \\(\mathbb C\\), and let \\(H\\) be a connected subgroup. Then
\\[m(G)=m(H)+m(G/H).\\]

*Proof.*
We use the Serre spectral sequence. By the construction of the complex manifold structure on \\(G(\mathbb C)/H(\mathbb C)\\) by slice charts (in \\(G(\mathbb C)\\) orthogonal to \\(H(\mathbb C)\\)), we see that
\\[H(\mathbb C)\to G(\mathbb C)\to G/H(\mathbb C)\\]
is a Serre fibration.

In order to apply the Serre spectral sequence with ease, we ought to check that \\(\pi_1(G/H(\mathbb C))\\) acts trivially on the fibers \\(\mathrm H^\bullet(H(\mathbb C);\mathbb C)\\). This is a direct calculation: a chosen \\([\gamma]\in\pi_1(G/H(\mathbb C))\\) may be first lifted to some path \\(\widetilde\gamma\colon[0,1]\to G(\mathbb C)\\) with \\(\widetilde\gamma(0)=1\\) and \\(\widetilde\gamma(1)\in H(\mathbb C)\\), and then the action of \\([\gamma]\\) on \\(H(\mathbb C)\\) is by translation by \\(\widetilde\gamma(1)\\). Thus, we are left to check that the translation action of \\(H(\mathbb C)\\) on the Betti cohomology groups \\(\mathrm H^\bullet(H(\mathbb C);\mathbb C)\\) is trivial. This is true because the action on singular cycles can be smoothly deformed to the identity by choosing any path from \\(h\in H(\mathbb C)\\) to the identity. This is the only part of the argument where we use that \\(H(\mathbb C)\\) is connected.

The previous paragraph provides us with a Serre spectral sequence
\\[E\_2^{pq}=\mathrm H^p(G/H(\mathbb C);\mathrm H^q(H(\mathbb C);\mathbb C))\Rightarrow\mathrm H^{p+q}(G(\mathbb C);\mathbb C).\\]
As just discussed, the local system \\(\mathrm H^q(H(\mathbb C);\mathbb C)\\) on the base is trivial, so this spectral sequence is in fact
\\[E\_2^{pq}=\mathrm H^p(G/H(\mathbb C);\mathbb C)\otimes_{\mathbb C}\mathrm H^q(H(\mathbb C);\mathbb C)\Rightarrow\mathrm H^{p+q}(G(\mathbb C);\mathbb C).\\]
The spectral sequence is concentrated in the box \\((p,q)\in[0,m(G/H)]\times[0,m(H)]\\), so we immediately see that \\(m(G)\le m(G/H)+m(H)\\). To achieve the equality, we note that the \\(E\_2\\) page of the spectral sequence has a nonzero term at \\((p,q)=(m(G/H),m(H))\\), and no other nonzero terms in the spectral sequence may interact with it. Thus, \\(E\_2^{m(G/H),m(H)}\\) survives to \\(E\_\infty\\), and \\(m(G)=m(G/H)+m(H)\\) follows. \\(\blacksquare\\)

> **Remark 6.**
One can relax the connectivity hypotheses from the statement of the proposition. This requires a slightly more careful analysis of the Serre spectral sequence. In particular, \\(\pi\_1(G/H(\mathbb C))\\) no longer must act trivially on cohomology; instead, it will act through the finite quotient \\(\pi\_0(H(\mathbb C))\\), so one must do a little finite group cohomology.

We will use Proposition 4 to compute \\(m(G)\\) for affine algebraic groups over \\(\mathbb C\\). Let's start with the reductive case.

> **Lemma 7.**
Let \\(G\\) be a connected reductive group over \\(\mathbb C\\). Then
\\[m(G)=\dim G.\\]

*Proof.*
This is classical, but we will give a proof using Proposition 5. Let \\(B\subseteq G\\) be a Borel subgroup. Then
\\[m(G)=m(B)+m(G/B).\\]
The easier term is \\(m(G/B)\\): recall \\(G/B\\) is a projective (flag) variety, so Poincaré duality implies \\(m(G/B)=2\dim G/B\\). Local considerations (e.g., with manifolds) verifies that \\(2\dim G/B=2\dim G-2\dim B\\).

We now turn to \\(m(B)\\). Let \\(U\subseteq B\\) be the unipotent radical, and let \\(T\subseteq B\\) be a maximal torus so that \\(B/U=T\\). Thus,
\\[m(B)=m(U)+m(T).\\]
On one hand, that \\(U\\) is a unipotent group, so \\(U(\mathbb C)\\) is diffeomorphic to affine space, so \\(m(U)=0\\). On the other hand, we see \\(T(\mathbb C)\cong\mathbb G\_m(\mathbb C)^{\dim T/2}\\), and \\(m(\mathbb G\_m)=1\\), so the Künneth formula implies \\(m(T)=\dim T\\). Thus, \\(m(B)=\dim T\\).

Collecting everything, we find that
\\[m(G)=2\dim G-2\dim B+\dim T.\\]
Because \\(B/U=T\\), we know \\(\dim B=\dim U+\dim T\\). Also, by the root decomposition, we know \\(\dim G=\dim T+2\dim U\\). Expanding everything yields \\(m(G)=\dim G\\). \\(\blacksquare\\)

> **Proposition 8.**
Let \\(G\\) be a connected affine algebraic group over \\(\mathbb C\\), and let \\(R\_uG\\) be its unipotent radical. Then
\\[m(G)=\dim G-\dim R\_uG.\\]

*Proof.*
By Proposition 5,
\\[m(G)=m(R\_uG)+m(G/R\_uG).\\]
Because \\(R\_uG\\) is a unipotent group, \\(R\_uG(\mathbb C)\\) is diffeomorphic to affine space, so \\(m(R\_uG)=0\\). Continuing, note that \\(G/R\_uG\\) is a connected reductive group, so Lemma 7 implies \\(m(G/R\_uG)=\dim G/R\_uG\\). The result follows by computing dimensions locally (e.g., as manifolds). \\(\blacksquare\\)

We are now ready to prove Theorem 1.

*Proof of Theorem 1.*
Because \\(G/H\\) is affine, it follows that \\(m(G/H)\le\dim G/H\\), so
\\[m(G/H)\le\dim G-\dim H.\\]
On the other hand, by Proposition 5, \\(m(G/H)=m(G)-m(H)\\), which by Lemma 7 and Proposition 8 expands out to
\\[m(G/H)=\dim G-\dim H+\dim R\_uH.\\]
Comparing the two inequalities yields \\(R\_uH=1\\), so \\(H\\) is reductive. \\(\blacksquare\\)

> **Remark 9.**
It is not hard to remove connectivity assumptions from Theorem 1. On one hand, to check that \\(H\\) is reductive, it is enough to check that \\(H^\circ\\) is reductive. On the other hand, once \\(G/H\\) is affine, the quotient map \\(G/H^\circ\to G/H\\) is finite, so \\(G/H^\circ\\) is also affine. The result follows.

> **Remark 10.**
By a spreading out argument, one can extend Theorem 1 from \\(\mathbb C\\) to any field \\(k\\) of characteristic zero. Indeed, \\(G\\), \\(H\\), and \\(G/H\\) can always be defined over a finitely generated field extension of \\(\mathbb Q\\), which can then be embedded into \\(\mathbb C\\). Because proving that a scheme is affine (and checking that a group is reductive) can be done after base-change by a field, the theorem follows.

> **Remark 11.**
It is even possible to work over a field of positive characteristic. One way to do this is to replace all Betti cohomology by étale cohomology. The difficulty lies in replacing some of the delicate topological arguments in Proposition 5. Such an argument has been carried out by [Borel](https://link.springer.com/article/10.1007/BF01194008).