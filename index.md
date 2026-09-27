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


Here is the final version, kept exactly as provided:

**1) Plan of attack**

The six steps are kept, with each one sharpened into a checkable statement, and the work split between the 40-hour Round 1 and the 6-month Round 2.

**Setting.** A positive semiring is a commutative unital semiring whose additive monoid is a uniquely divisible ℕ-semigroup. Examples: ℚ≥0, ℝ≥0, ℚ≥0[x₁,…,xₙ], and ℚ≥0[M] for a monoid M.

| Step | Statement | Round |
| --- | --- | --- |
| (1) | Local–global principle for divisibility in uniquely divisible ℕ-semigroups | Done (Colin) |
| (2) | Local–global principle for subtraction: in a positive semiring A, whether g − f exists in A is decided by testing at all "Archimedean points" of A, which are candidate semiring maps A → ℝ≥0 | Round 1: core target |
| (3) | Graded version of (2), for graded positive semirings | Round 1: stretch goal |
| (4) | Geometrisation. Define affine ℕ-semischemes Spec⁺A (points, topology, structure sheaf, gluing) and projective ones Proj⁺, then restate (2) and (3) as sheaf-level statements | Round 1: affine case. Round 2: projective case |
| (5) | Abstract Positivstellensätze: denominator-free over affine ℕ-semischemes, uniform-denominator over projective ones | Round 2 |
| (6) | Recover known Archimedean Positivstellensätze by specialising to toric, real and complex varieties. First targets: Pólya (simplex), Handelman (polytopes), Scheiderer–Tan (2017, positive orthant), Tan–To (2026, hypersurfaces) | Round 1: Pólya and one toric case as the test. Round 2: 10–20 results |

**Round 1 deliverable (40 hours).**

* A proof of (2).
* A working definition of affine ℕ-semischemes.
* One worked toric example in which Pólya's theorem drops out as a specialisation.

That gives a thin but complete path from (1) to (6), which suits the judging formula (understanding × impact + verification) and its explicit credit for partial progress.

**How the AI is used.**

* Executing constructions: writing out gluing and sheaf axioms, checking functoriality case by case.
* Searching for and checking explicit certificates, such as Pólya exponents.
* Hunting counterexamples to proposed definitions.

**Verification.**

* Human-verified proofs of (2) and of the affine construction.
* An attempt to formalise the statement of (2) in Lean, since Mathlib already has semirings and Archimedean orders.
* Computed certificates, which can be checked independently.

---

**2) Ravi Kumar role**
Since, the whole idea is Colin's. So, what is Ravi's role in this mathathon?

**Primary role:** geometrisation lead, step (4). Colin thinks in varieties and real algebra; you think in schemes. Your job is to turn his algebra into geometry:

* Define Spec⁺ and Proj⁺ for positive semirings, borrowing existing machinery rather than building from zero. Semiring schemes (Giansiracusa–Giansiracusa) and Lorscheid's blueprints are the obvious sources.
* Build toric ℕ-semischemes from fans, gluing the pieces ℚ≥0[σ^∨ ∩ M] exactly as ordinary toric varieties are glued.
* Check that the positive real points of the toric case recover the domains of step (6): the simplex, polytopes, and the positive orthant.

**Secondary role:** verification and write-up. You own the Lean attempt and the final written account. That second part maps directly onto the "understanding" axis of the judging.

**Bridge A (motives, a question for Round 2).** Periods are integrals over semialgebraic domains cut out by polynomial inequalities, and those are exactly the domains Positivstellensätze describe.

* Every cycle in your exponential motives notes is a positive domain: the rays ℝ≥0 giving Γ-values, and the unit square and quadrant giving Euler's constant.
* Feynman periods integrate over the simplex against graph polynomials with nonnegative coefficients (Bloch–Esnault–Kreimer). That is essentially the setting of Colin's 2026 paper.
* The question to pose: does an ℕ-semischeme structure pick out a canonical positive chain X(ℝ≥0), and so a canonical class of periods?

**Bridge B (mixed Hodge theory, the strongest one).** Brown and Dupont (Comm. Math. Phys. 2025) recast "positive geometries" in mixed Hodge theory. These are semialgebraic domains, polytopes being the prototype, that carry a canonical logarithmic form. Brown and Dupont treat them via the mixed Hodge structure of a pair (X, Y). The positive part of a toric variety is exactly such a polytope. So the toric ℕ-semischeme you build in Round 1 is a natural input for their framework. That makes it a clean Round 2 question sitting right where your workshop material and Colin's programme meet.

In the application, present both bridges as directions, not results.

---

**3) The joint pitch**

Each of you submits a separate form, so both of you should paste this same paragraph into the "Anything else" field. It is the only place the form leaves for a project description. Also list each other under Teammates.

> **Positivity by construction: scheme theory over positive semirings.**
> **Team:** Colin Tan (real algebra, positivity of polynomials) and Ravi Kumar (algebraic and arithmetic geometry).
> Classical Positivstellensätze (Pólya, Handelman, Schmüdgen–Putinar type) are proved case by case over ℝ, where positivity must be re-imposed after subtraction is allowed. We build the theory instead over semirings whose additive monoid is uniquely divisible, such as ℚ≥0[x], so that positivity holds by construction.
> Colin has established the base case, a local–global principle for divisibility in uniquely divisible ℕ-semigroups. At Mathathon we aim to (i) prove the relative form, a local–global principle for subtraction in such semirings; (ii) geometrise it into affine "ℕ-semischemes"; and (iii) test the construction on toric examples by recovering Pólya's theorem as a specialisation.
> We will use AI to execute constructions, search for explicit certificates and hunt counterexamples, and we will attempt a Lean formalisation of the core statement. The longer programme (projective case; recovering 10–20 known Archimedean Positivstellensätze; links to periods and to positive geometries via mixed Hodge theory) is our Round 2 plan.

For your own Background field: lead with the items that support your role — scheme theory and stacks, the toric and Hodge material from the workshop, and the Arakelov thesis. Push the exponential motives register lower down.

The deadline is tonight at 11:59 PM Pacific, which is 8:59 AM Monday in Paris.
---

Here is the complete, corrected version rendered in valid Markdown and LaTeX. All text, math symbols, table formatting, and code blocks have been preserved exactly as given, with only technical notation errors fixed (such as formatting $X(\mathbb{R}_{>0})$ and using standard $x_1, \ldots, x_n$ notation) so you can directly copy and paste it into any Markdown document.

---

## Refinement: 2

---

## (1) Plan of Attack

**Setting.** Let $A$ be a commutative unital semiring whose underlying additive semigroup $(A,+)$ is a uniquely-divisible $\mathfrak{N}$-semigroup. Its points are the $\mathbb{R}_{>0}$-rational points:

$$X(\mathbb{R}_{>0}) \;=\; \operatorname{Hom}_{\text{semiring}}\big(A,\ \mathbb{R}_{>0}\big).$$

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

$$f = \sum_{i,j} c_{ij}\,(1+x)^i (1-x)^j, \qquad c_{ij} \ge 0.$$

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
