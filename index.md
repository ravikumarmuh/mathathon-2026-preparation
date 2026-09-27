---
layout: default
title: Caltech Mathathon 2026
---





# Caltech Mathathon 2026 — Colin Tan & Ravi Kumar

Welcome to our working page for the **Caltech Mathathon 2026**.

This page collects our current mathematical directions, AI-assisted research experiments, candidate problems, and preparation notes.

## Team

- **Colin Tan**
- **Ravi Kumar**

## Main Idea

We are interested in how frontier AI systems can contribute to mathematical research beyond simply generating candidate proofs.

Our working framework is:

$$
\text{mathematical theme}
\longrightarrow
\text{specific problem}
\longrightarrow
\text{plan of attack}
\longrightarrow
\text{AI-assisted exploration}
\longrightarrow
\text{verification}
\longrightarrow
\text{mathematical understanding}.
$$

We are especially interested in questions such as:

- Can AI help identify useful intermediate structures?
- Can it suggest non-obvious lemmas or proof strategies?
- Can it connect different mathematical theories in a useful way?
- Can it help generate examples or counterexamples?
- How should AI-generated arguments be independently verified?
- When does an AI-assisted proof genuinely improve human mathematical understanding?


---

Here is the complete text properly formatted in Markdown and LaTeX with all math delimiters converted to `$ x \(` and `\)\(x\)$` as requested, ready to copy and paste without syntax or rendering errors:

```markdown
## Refinement: 2

```

---

## (1) Plan of Attack

**Setting.** Let $A$ be a commutative unital semiring whose underlying additive semigroup $(A,+)$ is a uniquely-divisible $\mathfrak{N}$-semigroup. Its points are the $\mathbb{R}_{>0}$-rational points:

$$X(\mathbb{R}_{>0}) = \operatorname{Hom}_{\text{semiring}}(A, \mathbb{R}_{>0}).$$

| Step | Statement | Round |
| --- | --- | --- |
| (1) | Local–global principle for divisibility in uniquely-divisible $\mathfrak{N}$-semigroups | Done (Colin) |
| (2) | **Local–global principle for subtraction.** For $f, g \in A$, whether $g - f$ exists in $A$ is decided by the values $\varphi(f), \varphi(g)$ at all $\varphi \in X(\mathbb{R}_{>0})$ | **Round 1: core target** |
| (3) | Graded version of (2), for graded semirings $S = \bigoplus_{d} S_d$ of the same type | Round 1: stretch goal |
| (4) | **Geometrisation** into affine $\mathfrak{N}$-semischemes $\operatorname{Spec}_{\mathfrak{N}} A$ and projective ones $\operatorname{Proj}_{\mathfrak{N}} S$: Zariski topology on $\mathbb{R}_{>0}$-rational points, structure sheaf, gluing | **Round 1: affine case.** Round 2: projective case |
| (5) | Abstract geometric Positivstellensätze: denominator-free on affine varieties, uniform-denominator on projective varieties | Round 2 |
| (6) | Deduce the known Archimedean Positivstellensätze by specialising to toric, real and complex varieties | **Round 1: Bernstein and Pólya.** Round 2: the rest |

**Round 1 test cases.** These are the two model shapes that step (5) should produce.

* **Bernstein (1915), denominator-free.** If $f > 0$ on $[-1,1]$, then

$$f = \sum_{i,j} c_{ij}(1+x)^i (1-x)^j, \qquad c_{ij} \ge 0.$$

* **Pólya (1926), uniform-denominator.** If $f$ is homogeneous and $f > 0$ on the standard simplex $\Delta^{n-1}$, then for some $N$,

$$(x_1 + \cdots + x_n)^N f \text{ has only positive coefficients.}$$

**Full target list for (6):** Bernstein (1915), Pólya (1926), Handelman, Schmüdgen, Cimprič–Zalar, Scherer–Hol, Le–Du, Quillen (1968, *Inventiones*), Scheiderer (*manuscripta*), the algebraic content of Catlin–D'Angelo (1999), Putinar–Scheiderer (2012, *MRL*), Scheiderer–Tan (2017, *Arch. Math.*), Baldi–Sinn–Máté–Weigert (2025, preprint), Tan–To (2026, arXiv).

**Novelty.** Earlier semischeme theories allow too general a class of semirings. Their spaces lack enough points, which forces a functor-of-points definition. For $\mathfrak{N}$-semischemes, principle (1) guarantees enough $\mathbb{R}_{>0}$-rational points, so the Zariski topology is defined directly on points.

**How the AI is used.**

* Executing constructions: sheaf axioms, gluing, functoriality checks.
* Searching for and verifying certificates, such as Pólya exponents $N$.
* Hunting counterexamples to proposed definitions.

**Verification.**

* Human-verified proofs.
* An attempted Lean formalisation of the statement of (2).
* Computed certificates that can be checked independently.

---

## (2) Colin's Role: algebraic core and target theorems

* **Steps (1)–(3).** Owns the algebra: the local–global principles for divisibility and for subtraction, and the graded version. He sets the proof strategy for (2), the Round 1 core.
* **Step (5).** Formulates the abstract denominator-free and uniform-denominator Positivstellensätze once the geometry is in place.
* **Step (6).** Chooses and checks the specialisations. He knows exactly what each classical theorem (Bernstein, Pólya, Handelman, …) should look like as an output, so he defines what "recovering" a result means.
* **Certificates.** Directs the AI-assisted search for explicit positivity certificates and judges which computations actually support the conjectured statements.

---

## (3) Ravi's Role: geometrisation, verification, and bridges

**Primary role: step (4), geometrisation lead.**

* Build $\operatorname{Spec}_{\mathfrak{N}} A$ on classical lines: the set $X(\mathbb{R}_{>0})$, basic opens $D(f)$, the Zariski topology, the structure sheaf $\mathcal{O}$, and gluing into general affine and then projective $\mathfrak{N}$-semischemes.
* Pin down exactly where (1) and (2) supply the enough-points property the construction needs.
* Build $\operatorname{Proj}_{\mathfrak{N}} S$ for the graded case (3).
* Write the comparison with earlier semischeme theories: why they need the functor of points and why $\mathfrak{N}$-semischemes do not.

**Secondary role: verification and write-up.** Owns the Lean attempt and the final written account, which is what the understanding axis of the judging measures.

**Bridge A, periods (Round 2 question).** Periods are integrals over semialgebraic domains, and the cycles in exponential motives are positive domains: rays $\mathbb{R}_{>0}$ for $\Gamma$-values, and $[0,1]^2$ and $[1,\infty)^2$ for Euler's constant $\gamma$. Feynman periods integrate over $\Delta^{n-1}$ against graph polynomials with nonnegative coefficients. The question is whether an $\mathfrak{N}$-semischeme structure singles out a canonical positive chain, and with it a canonical class of periods.

**Bridge B, mixed Hodge theory (the strongest bridge).** Brown and Dupont (*Comm. Math. Phys.* 2025) recast positive geometries (semialgebraic domains with a canonical logarithmic form, with polytopes as the prototype) in the mixed Hodge theory of pairs $(X, Y)$. For a projective toric variety $X_P$, the positive points $X_P(\mathbb{R}_{>0})$ form the interior of the polytope $P$. So toric $\mathfrak{N}$-semischemes are natural inputs to their framework.

Present both bridges as directions, not results.

---

## (4) Joint Pitch

> **$\mathfrak{N}$-semischemes and a unified Archimedean Positivstellensatz**
> Team: Colin Tan (real algebra, positivity of polynomials) and Ravi Kumar (algebraic and arithmetic geometry).
> Positivstellensätze from Bernstein (1915) and Pólya (1926) to Handelman, Schmüdgen and Putinar–Scheiderer certify that polynomials strictly positive on semialgebraic sets admit manifestly positive representations. They are proved one at a time over $\mathbb{R}$, where positivity must be recovered after subtraction is allowed. We develop a geometry in which positivity holds by construction: $\mathfrak{N}$-semischemes, modelled locally on commutative unital semirings whose underlying additive semigroup is a uniquely-divisible $\mathfrak{N}$-semigroup, with points given by $\mathbb{R}_{>0}$-rational points.
> Earlier notions of semischemes allow too general a class of semirings and lack enough points, forcing a functor-of-points definition. Colin's local–global principle for divisibility shows that $\mathfrak{N}$-semischemes have enough points and therefore carry a genuine Zariski topology.
> At Mathathon we aim to (i) prove the relative local–global principle for subtraction (Colin); (ii) construct affine $\mathfrak{N}$-semischemes with their Zariski topology and structure sheaf (Ravi); and (iii) recover Bernstein's and Pólya's theorems as specialisations. We will use AI to execute constructions, search for certificates and hunt counterexamples, and we will attempt a Lean formalisation of the core statement.
> Round 2: the graded and projective case; abstract denominator-free and uniform-denominator Positivstellensätze; and deducing 10–20 known results, through Tan–To (2026), by specialising to toric, real and complex varieties.

The application form is plain text and won't render LaTeX, so here is the same pitch ready to paste:

```text
𝔑-semischemes and a unified Archimedean Positivstellensatz

Team: Colin Tan (real algebra, positivity of polynomials) and Ravi Kumar (algebraic and arithmetic geometry).

Positivstellensätze from Bernstein (1915) and Pólya (1926) to Handelman, Schmüdgen and Putinar–Scheiderer certify that polynomials strictly positive on semialgebraic sets admit manifestly positive representations. They are proved one at a time over ℝ, where positivity must be recovered after subtraction is allowed. We develop a geometry in which positivity holds by construction: 𝔑-semischemes, modelled locally on commutative unital semirings whose underlying additive semigroup is a uniquely-divisible 𝔑-semigroup, with points given by ℝ_{>0}-rational points.

Earlier notions of semischemes allow too general a class of semirings and lack enough points, forcing a functor-of-points definition. Colin's local–global principle for divisibility shows that 𝔑-semischemes have enough points and therefore carry a genuine Zariski topology.

At Mathathon we aim to (i) prove the relative local–global principle for subtraction (Colin); (ii) construct affine 𝔑-semischemes with their Zariski topology and structure sheaf (Ravi); and (iii) recover Bernstein's and Pólya's theorems as specialisations. We will use AI to execute constructions, search for certificates and hunt counterexamples, and we will attempt a Lean formalisation of the core statement.

Round 2: the graded and projective case; abstract denominator-free and uniform-denominator Positivstellensätze; and deducing 10–20 known results, through Tan–To (2026), by specialising to toric, real and complex varieties.

```

```

```
