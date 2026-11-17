# 🧑‍🤝‍🧑 AetherHuman — Research Repository

### Human Participation in Autonomous Agent Ecosystems

*A Falsification-First Investigation of Human Roles, Authority, and Intervention in Decentralized Multi-Agent Systems*

---

[![DOI Zenodo](https://zenodo.org/badge/DOI/10.5281/zenodo.24278322.svg)](https://doi.org/10.5281/zenodo.24278322)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![ORCID](https://img.shields.io/badge/ORCID-0009--0003--8903--0029-a6ce39)](https://orcid.org/0009-0003-8903-0029)
[![Status](https://img.shields.io/badge/Status-Architectural%20Investigation-blue)]()
[![Version](https://img.shields.io/badge/Version-1.0.0-green)]()
[![Phase](https://img.shields.io/badge/Phase-4%20(Undetermined)-amber)]()
[![Website](https://img.shields.io/badge/Website-aetherhuman.netlify.app-green)](https://aetherhuman.netlify.app)

---

> **Status: Architectural Investigation.**
> This is a **research repository**, not a software repository.
> No implementation is planned unless the architectural investigation supports it.
> **Decision: (E) Undetermined (interim).**
> See [`DECISIONS/INDEPENDENCE_DECISION.md`](DECISIONS/INDEPENDENCE_DECISION.md).

> *"AetherHuman is a candidate, not a result."*

---

## Table of Contents

- [Overview](#overview)
- [Central Question](#central-question)
- [Five Functions](#five-functions-initial-scope)
- [Failure Conditions](#failure-conditions-h-f1-to-h-f4)
- [Propositions](#propositions-p1-p2)
- [Decision (Phase 4)](#decision-phase-4)
- [Repository Structure](#repository-structure)
- [Phase Status](#phase-status)
- [What This Repository Does Not Claim](#what-this-repository-does-not-claim)
- [Related Work](#related-work)
- [Related Aether Projects](#related-aether-projects)
- [Figures](#figures)
- [Figure Notes](#figure-notes)
- [Evaluation Design](#evaluation-design)
- [Threats to Validity](#threats-to-validity)
- [Research Status](#research-status)
- [Author](#author)
- [License](#license)

---

## Overview

**AetherHuman** is the **eleventh project (candidate)** of the Aether family. It investigates whether a genuine architectural gap exists between human participation and the existing dimensions — particularly AetherGovern (authority), AetherIdentity (identity), and AetherRuntime (execution monitoring).

**AetherHuman is not a replacement for AetherGovern, AetherIdentity, or AetherAudit.** All remain dimensions or candidates with their own status. AetherHuman investigates whether human participation introduces operational semantics, authority relations, or constraints that cannot be adequately represented by the existing dimensions.

This repository is a **research repository**. It contains no `src/`, no `tests/`, no `experiments/`. It will not contain them unless the investigation concludes that AetherHuman is independent.

**The paper (v1.0.0) is published on Zenodo:** [10.5281/zenodo.24278322](https://doi.org/10.5281/zenodo.24278322).

**Paper length:** ~29 pages, ~11,000 words (13,600 with references and appendices), 30 references.

---

## Central Question

> How can human participation — as principal, overseer, or mandatory intervention point — be represented in a decentralized autonomous agent ecosystem, without reducing it to delegated authority or breaking the autonomy assumptions of the existing dimensions?

The central question has four clauses, mapping to the failure conditions:

| Clause | Condition |
|---|---|
| (i) Not already covered by Govern / Identity / Runtime | H-F1 |
| (ii) Does not decompose into Govern + Identity + Runtime | H-F2 |
| (iii) No central human authority required | H-F3 |
| (iv) Observable benefit | H-F4 |

A positive answer needs all four. A negative answer on any one is sufficient to reject the candidate as a separate dimension, although it might survive as a feature of another.

---

## Five Functions (Initial Scope)

| # | Function | Question |
|---|---|---|
| **Fn1** | Human Principal Representation | How is a human represented as an architectural principal (not merely an agent of a special type)? |
| **Fn2** | Authority Relation | What authority can a human exercise over autonomous agents — delegated, oversight, veto, or independent? |
| **Fn3** | Intervention Semantics | How does human intervention affect execution — optional, conditional, or mandatory non-bypassable? |
| **Fn4** | Accountability Chain | How is human responsibility attributed and traced across agent delegations? |
| **Fn5** | Human-Agent Boundary | How is the boundary between human decision and agent autonomy maintained without collapsing one into the other? |

These five are **not** assumed to be complete, independent, or necessary. The paper uses **H1–H5** as working hypotheses for each function; none is established.

---

## Failure Conditions (H-F1 to H-F4)

| ID | Claim under test | Status |
|:-:|---|:-:|
| **H-F1** | Non-redundancy: not covered by Govern / Identity / Runtime | 🟡 Not falsified (author's reading) |
| **H-F2** | Distinction from Govern + Identity + Runtime (a remainder survives) | 🟡 Not falsified (remainder may be small; **most fragile**) |
| **H-F3** | Decentralizability: no central human authority required | 🟡 Not falsified (residuals: veto, mandatory intervention) |
| **H-F4** | Observable benefit | 🔴 **Untested** |

> **"Not falsified" is a weaker status than "confirmed". "Untested" is not a pass.**
> The decision rule: the candidate is accepted as an independent dimension only if all four conditions have been tested and none falsified, with H-F4 supported by measured results. With three conditions not falsified by argument alone and one untested, the third case applies: **(E) Undetermined (interim)**.

**Residuals noted in the paper:**
- **H-F3:** veto and mandatory intervention are residual cases not yet shown to be decentralizable.
- **H-F2:** the remainder after composition with Govern + Identity + Runtime may be small.
- **H-F1:** related work outside the family (Cheng & Cheng; HDP) overlaps Fn1/Fn4, recorded as a reservation on H-F1.

---

## Propositions P1–P2

| # | Proposition | Status |
|:-:|---|---|
| **P1** | Determinism of human intervention semantics | Proof sketch (near-trivial; content in the absence rule) |
| **P2** | Irreducible human authority anchor | Proof sketch (symmetry argument; **cuts against independence**) |

**P1** states that the three intervention modes, together with a rule for the absence of a response, define the effect of an intervention on an execution by a deterministic function of the specification and the record of responses. The absence rule is the part that agent-to-agent semantics do not supply.

**P2** states that some human authority (e.g., veto, mandatory approval) cannot be fully represented as delegated agent authority, because it must be able to override the delegation chain itself. This cuts **against** independence, because the anchor is plausibly a governance matter.

Neither is machine-checked.

---

## Decision (Phase 4)

**AetherHuman is classified as (E) Undetermined (interim).**

The evidence is insufficient to accept AetherHuman as an independent dimension, and insufficient to reject it. A test is needed to decide. See [`DECISIONS/INDEPENDENCE_DECISION.md`](DECISIONS/INDEPENDENCE_DECISION.md).

**Why insufficient to accept:**
- H-F4 is untested: no benefit has been observed.
- H-F2 remainder may be small.
- H-F3 has residuals (veto, mandatory intervention).
- P1 is near-trivial; P2 cuts against independence.
- AetherGovern and AetherIdentity are themselves unresolved.

**Why insufficient to reject:**
- No failure condition has been falsified.
- The comparison found a remainder after composition with the neighbours (H-F2).
- The decentralization argument did not reach a requirement for a central decision point (H-F3).

**"Undetermined" is not a failure.** It states that the evidence is insufficient to decide, and names what is missing.

---

## Repository Structure

```text
AetherHuman/
│
├── README.md
├── ARCHITECTURAL_HYPOTHESIS.md
├── ROADMAP.md
├── CHANGELOG.md
├── PROJECT_SUMMARY.txt
├── CITATION.cff
├── AUTHORS.md
├── CONTRIBUTING.md
├── INVENTORY.md
├── VERSION
├── manifest.json
├── scientific_state.json
├── netlify.toml
├── LICENSE
│
├── research/
│   └── RESPONSIBILITY_BOUNDARIES.md
│
├── FALSIFICATION/
│   └── FALSIFICATION_PLAN.md
│
├── DECISIONS/
│   └── INDEPENDENCE_DECISION.md
│
├── REVIEW/
│   ├── INTERNAL_REVIEW.md
│   ├── INDEPENDENT_REVIEW.md
│   ├── INDEPENDENT_REVIEW_PROTOCOL.md
│   └── README.md
│
├── REFERENCES/
│   └── (30 references from the paper)
│
├── docs/
│   └── figures/
│       ├── Fig1_Eleven_Dimensions.png
│       ├── Fig2_Human_Lifecycle.png
│       ├── Fig3_Human_Functions.png
│       ├── Fig4_Boundaries.png
│       ├── Fig5_Falsification_Procedure.png
│       ├── Fig6_Phase_Status.png
│       ├── Fig7_Decision_Outcomes.png
│       ├── Fig8_Overlap_Matrix.png
│       └── Fig9_Evaluation_Design.png
│
├── paper/
│   └── AetherHuman_Research_Paper_v1.0.0.pdf
│
├── PUBLICATION/
│   └── Netlify/
│       └── public/
│
└── REPORTS/
    └── architectural_investigation/
        └── investigation_report.md
```

No src/, no tests/, no experiments/.

---

Phase Status

Phase Description Status
0 — Architectural Hypothesis The hypothesis is stated ✅ Complete (ARCHITECTURAL_HYPOTHESIS.md)
1 — Responsibility Mapping Boundaries with existing dimensions ✅ Complete (research/RESPONSIBILITY_BOUNDARIES.md)
2 — Hypothesis Review Independent review of hypothesis ⏳ Not started (REVIEW/INDEPENDENT_REVIEW.md)
3 — Falsification Design Design of H-F1 to H-F4 tests ✅ Complete (FALSIFICATION/FALSIFICATION_PLAN.md)
4 — Independence Decision (E) Undetermined (interim) ⚠️ Interim (DECISIONS/INDEPENDENCE_DECISION.md)
5 — Architectural Specification Requires positive Phase 4 ❌ Not permitted
6 — Reference Implementation Requires Phase 5 ❌ Not permitted

Note. The internal review (REVIEW/INTERNAL_REVIEW.md) is complete. The independent review (REVIEW/INDEPENDENT_REVIEW.md) has not started. The independent review protocol (REVIEW/INDEPENDENT_REVIEW_PROTOCOL.md) is ready to use. Phase 3 being complete while Phase 2 has not started is recorded as threat T2 in the paper.

---

What This Repository Does Not Claim

· That AetherHuman is an independent architectural dimension.
· That the five functions are complete, independent, or necessary.
· That the boundaries with AetherGovern, AetherIdentity, AetherRuntime, and the other dimensions are sufficient.
· That the gap is genuine.
· That implementation should begin.
· Any observed benefit (H-F4 is untested).
· Any causal effect.

---

Related Work

The paper cites 30 references. Two are the nearest recent neighbours and overlap Fn1/Fn4; they are recorded as a reservation on H-F1, not as support for the candidate:

· Cheng & Cheng (2026), arXiv:2604.23049 — a design proposal for a shared human-oversight service; no experimental evaluation reported.
· HDP Internet-Draft (draft-helixar-hdp-agentic-delegation-00) — a token format that records which human principal authorized an agentic task; the draft's header and status text give different expiry dates.

The literature on human-in-the-loop, principal-agent models, delegation calculi, and accountability is reviewed in Section 2 of the paper. The comparison with the field is treated as open and is a reservation on H-F1.

---

Related Aether Projects

# Project Status DOI
1 AetherGit Foundational 10.5281/zenodo.23976986
2 AetherFlow Foundational 10.5281/zenodo.23979129
3 AetherProof Foundational 10.5281/zenodo.24013124
4 AetherMesh Foundational 10.5281/zenodo.24038038
5 AetherGovern Foundational 10.5281/zenodo.24054524
6 AetherRuntime Foundational 10.5281/zenodo.24078477
7 AetherOrchestrate Foundational 10.5281/zenodo.24095399
8 AetherIdentity Candidate (paper + v2.0.0; independence unresolved) 10.5281/zenodo.24102739
9 AetherPolicy Candidate (Phase 4: (E) undetermined) 10.5281/zenodo.24160047
10 AetherAudit Candidate (Phase 4: (E) undetermined) 10.5281/zenodo.24274628
11 AetherHuman Candidate (this repository; Phase 4: (E) undetermined) 10.5281/zenodo.24278322

---

Figures

Figure 1 — The Eleven Dimensions of the Aether Family

docs/figures/Fig1_Eleven_Dimensions.png

Figure 2 — AetherHuman Lifecycle

docs/figures/Fig2_Human_Lifecycle.png

Figure 3 — The Five Functions of AetherHuman (Fn1–Fn5)

docs/figures/Fig3_Human_Functions.png

Figure 4 — AetherHuman and Its Boundaries

docs/figures/Fig4_Boundaries.png

Figure 5 — The Falsification Procedure (H-F1 to H-F4)

docs/figures/Fig5_Falsification_Procedure.png

Figure 6 — Phase Status (Paused at Phase 4)

docs/figures/Fig6_Phase_Status.png

Figure 7 — The Five Phase 4 Outcomes (A / R / E / F / D)

docs/figures/Fig7_Decision_Outcomes.png

Figure 8 — Coverage Matrix: Five Functions × Existing Dimensions

docs/figures/Fig8_Overlap_Matrix.png

Figure 9 — Evaluation Design: Scenarios × Metrics × Failure Conditions

docs/figures/Fig9_Evaluation_Design.png

Figures 1–9 are described in the paper (Section 3 and Section 9).

---

Figure Notes

The paper notes the following discrepancies between the supplied figures and the corrected versions:

· Fig 1 — the supplied version overprinted the AetherHuman status label and gave a count of paused candidates that its own labels did not support. Redrawn.
· Fig 2 — the first arrow pointed backwards, and the caption said "cycle" with no return path. Redrawn as a sequence.
· Fig 6 — Phase 3 is complete while Phase 2 has not started; Phase 2 was coloured amber, the legend's "in progress" colour; the legend appeared three times. Redrawn; the paper treats this as threat T2.
· Fig 9 — "Implementation" was misspelled in the side note; the metrics had no labels. Redrawn with M1–M6 added.
· Figs 3, 4, 5, 7, 8 — kept as supplied, with observations in the paper:
  · Fig 8's legend does not define the solid amber cells for Govern at Fn3 and Fn5. If they mean more than partial, Fn5 may be largely covered by Govern.
  · Fig 4 says Audit "defines accountability attribution" and Policy "defines override and veto", but Fig 8 shows only partial coverage of Fn4 for Audit, and for Policy partial Fn2 and none for Fn3. So Fn4 may be a restriction of AetherAudit's attribution.
  · The Fig 8 caption omits Git, which the matrix marks partial on Fn4.
  · Fig 5 omits Hypothesis Review and the H-F3 residuals.

---

Evaluation Design

The paper proposes an evaluation design that has not been executed. Six scenarios (S1–S6) are mapped to six metrics (M1–M6) and to the four failure conditions:

# Scenario Metric Failure Condition Tested
S1 Single human, single agent M1: Intervention latency H-F4 (benefit)
S2 Single human, multiple agents M2: Authority consistency H-F2 (remainder)
S3 Multiple humans, single agent M3: Veto resolution time H-F3 (decentralizability)
S4 Multiple humans, multiple agents M4: Accountability trace depth H-F2, H-F4
S5 Adversarial human M5: Boundary integrity H-F1, H-F3
S6 Human unavailable M6: Fallback behavior H-F3 (residuals)

Baselines: B1–B3 are defined in the paper. Hypotheses: H1–H5 are working hypotheses for the five functions; none is established. Remainders: R1–R3 are recorded as open. None of these scenarios has been executed; this is a design, not a result.

---

Threats to Validity

The paper lists seven threats to its own validity:

# Threat Description
T1 Author-on-author reasoning The hypothesis and the decision are written by the same author.
T2 No independent review Phase 2 (independent review) has not started.
T3 Small remainder The H-F2 remainder may be small.
T4 Cooperative-human assumption Most arguments assume a cooperative human; S5 (adversarial) is not covered.
T5 Irreducible trust anchor P2 states that some authority cannot be reduced; this cuts against independence.
T6 No measurement H-F4 is untested; no evaluation has been run.
T7 Unresolved Govern and Identity AetherGovern and AetherIdentity are themselves unresolved, so the Phase 4 decision may need revisiting.

---

Research Status

Item Status
Project AetherHuman — candidate eleventh project of the Aether family; does not replace AetherGovern, AetherIdentity, or AetherAudit
Phase Paused at Phase 4 (Independence Decision) — interim
Decision (E) Undetermined: insufficient to accept, insufficient to reject
Propositions P1 (near-trivial) and P2 stated as proof sketches; not machine-checked
Failure conditions H-F1, H-F2, H-F3 not falsified by argument; H-F4 untested
Paper v1.0.0, 29 pages, ~11,000 words, 30 references
Implementation None
Experiments None executed; Section 9 of the paper is a proposal
Independent review Not started (Phase 2) — protocol ready (REVIEW/INDEPENDENT_REVIEW_PROTOCOL.md)
Claims not made Independence of the dimension; completeness of the five functions; sufficiency of the boundaries; any observed benefit; any causal effect

---

Author

Samir Baladi
Interdisciplinary AI Researcher, Ronin Institute / Rite of Renaissance

 
Email gitdeeper@gmail.com
ORCID 0009-0003-8903-0029
GitHub gitdeeper15/aetherhuman
GitLab gitlab.com/gitdeeper15/aetherhuman
Codeberg codeberg.org/gitdeeper15/aetherhuman
Bitbucket bitbucket.org/gitdeeper15/aetherhuman
Website aetherhuman.netlify.app
Zenodo 10.5281/zenodo.24278322

---

License

CC-BY-4.0 (this document). MIT (code, future — none in this release).

---

AetherHuman v1.0.0 — Architectural Investigation.
© 2026 Samir Baladi — Ronin Institute / Rite of Renaissance.
DOI: 10.5281/zenodo.24278322
