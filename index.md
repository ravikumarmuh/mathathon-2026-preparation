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

**2) Your role**

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

## Current Research Directions

### Colin

Colin is currently exploring problems related to:

- positivity;
- real algebraic geometry;
- semigroups and ordered algebraic structures;
- separation arguments;
- AI-assisted proof discovery.

One current project studies divisibility in uniquely divisible \(N\)-semigroups using homomorphisms to \(\mathbb R_{>0}\).

[Read Colin's research directions](colin-directions.md)

### Ravi

Ravi is currently interested in:

- algebraic geometry;
- cohomological methods;
- derived categories;
- $A_\infty$-algebras;
- $p$-adic geometry;
- derived and prismatic methods.

[Read Ravi's research directions](ravi-directions.md)

## Joint / Crossover Problems

We are also identifying a small number of concrete problems where our different mathematical backgrounds may interact.

[See possible crossover problems](crossover-problems.md)

## AI-Assisted Mathematical Research

We are documenting concrete examples of AI-assisted mathematical work, including:

- Colin's completed research project;
- Colin's ongoing second AI-assisted project;
- experiments in proof exploration and verification;
- observations about the strengths and limitations of current LLMs in mathematics.

[Read our AI-assisted research notes](ai-assisted-research.md)

## Lean / Formal Verification

We are also experimenting with small Lean formalizations to better understand how formal proof assistants may help verify AI-generated mathematics.

[See Lean experiments](lean-notes.md)

## Mathathon Application Notes

We are keeping separate notes for material that may eventually be distilled into the final Mathathon application.

[See application notes](application-notes.md)

---

**Status:** Work in progress. This page is being actively updated during our Mathathon preparation.

$\mathcal{F}$

$H^i(X,\mathcal{F})$

$$
\text{theme}
\longrightarrow
\text{problem}
\longrightarrow
\text{plan of attack}
$$
