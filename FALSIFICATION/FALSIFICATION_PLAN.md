# AetherAudit — Falsification Plan

**Status:** Phase 3 (Falsification Design) — design only, not executed.
**Date:** 2026-11-16
**Version:** 1.0.0
**Author:** Samir Baladi
**ORCID:** [0009-0003-8903-0029](https://orcid.org/0009-0003-8903-0029)
**License:** CC-BY-4.0 (this document)

---

## 0. Purpose

This document specifies how the four failure conditions (A-F1 to A-F4) of AetherAudit are to be tested. It is a **plan**, not a result. No test has been executed.

The plan is designed so that each condition can be **falsified** by evidence, not merely argued. A test that cannot, in principle, falsify a condition is not a test.

---

## 1. Failure conditions under test

| ID | Claim under test |
|:-:|---|
| A-F1 | Non-redundancy: AetherAudit is not covered by AetherRuntime, AetherPolicy, or AetherIdentity |
| A-F2 | Distinction from AetherRuntime + AetherGit: a remainder survives after composition |
| A-F3 | Decentralizability: no central audit authority is required |
| A-F4 | Observable benefit: AetherAudit yields benefit beyond existing dimensions |

A positive Phase 4 decision requires **all four** to be tested, **none** falsified, and **A-F4 supported by measured results**.

---

## 2. A-F1 — Non-redundancy

### 2.1 What would falsify A-F1

A-F1 is falsified if **all five functions** (Fn1–Fn5) are already provided by AetherRuntime, AetherPolicy, or AetherIdentity, without modification.

### 2.2 Test design

1. Take the coverage matrix from `research/RESPONSIBILITY_BOUNDARIES.md`.
2. For each function, ask: is it fully covered by Runtime, Policy, or Identity?
3. If all five are fully covered, A-F1 is falsified.
4. If at least one is not, A-F1 is **not falsified**, but the remainder must be further tested by A-F2.

### 2.3 Status

Not executed. The current reading (from RESPONSIBILITY_BOUNDARIES) suggests A-F1 is **not falsified**, but this is a documentary reading, not a test.

### 2.4 Residual risk

The reading depends on the author's interpretation of each dimension's scope. If AetherRuntime's scope is broader than currently documented, Fn1, Fn3, and Fn5 may be partially covered, weakening the remainder.

---

## 3. A-F2 — Distinction from AetherRuntime + AetherGit

### 3.1 What would falsify A-F2

A-F2 is falsified if, after composing AetherRuntime, AetherGit, and AetherProof, **no function** has a non-trivial remainder.

### 3.2 Test design

1. Compose AetherRuntime + AetherGit + AetherProof.
2. For each function, ask: is the remainder non-trivial?
3. A "non-trivial remainder" is one that cannot be expressed as (a) a new configuration of existing primitives, or (b) a feature flag in an existing dimension.
4. If no function has a non-trivial remainder, A-F2 is falsified.

### 3.3 Status

Not executed. The reading suggests:
- **Fn2 (Integrity)** is likely **foldable** into AetherProof.
- **Fn5 (Verification)** is likely **foldable** into AetherProof + AetherGovern.
- **Fn1 (Capture)** may be **partially foldable** into Runtime + Git + Policy.
- **Fn3 (Reconstruction)** is the **most likely survivor**.
- **Fn4 (Attribution)** is unclear.

### 3.4 Residual risk

If Fn3 is the only survivor, AetherAudit is a **narrow** dimension, not the broad dimension initially proposed. This is not a failure of the plan, but a **shift in the outcome**: from (A) Accept to (C) Partial.

---

## 4. A-F3 — Decentralizability

### 4.1 What would falsify A-F3

A-F3 is falsified if **audit verification cannot be performed without a central authority** or a trusted third party.

### 4.2 Test design

1. Construct a scenario (S1) in which multiple agents act in a distributed environment, no central authority is available, and one agent disputes another's action.
2. Ask: can the dispute be audited using only evidence and existing cryptographic primitives?
3. Assume an **honest auditor** who acts in good faith. If the audit succeeds under this assumption, A-F3 is **not falsified**.
4. Assume an **adversarial auditor** who may collude. If the audit succeeds under this assumption, A-F3 is **strengthened**.

### 4.3 Status

Not executed. The reading suggests A-F3 is **not falsified** for the honest-auditor case, but **falsified or weakened** for the adversarial case.

### 4.4 Residual risk

The honest-auditor assumption is a **residual**, not a result. It is threat T4. P2 (irreducible trust anchor) also suggests A-F3 may not hold in the adversarial case.

---

## 5. A-F4 — Observable benefit

### 5.1 What would falsify A-F4

A-F4 is falsified if **no observable benefit** of AetherAudit over the existing dimensions is measured.

### 5.2 Test design

1. Take the baselines B1–B5 (from Section 9 of the paper).
2. Take the scenarios S1–S6.
3. Take the metrics M1–M9.
4. For each scenario, measure each metric under each baseline and under AetherAudit.
5. Compare AetherAudit with the best baseline.
6. If no metric improves significantly in any scenario, A-F4 is falsified.

### 5.3 Status

**Not executed. No measurement has been performed.**

### 5.4 Residual risk

A-F4 is the **weakest** condition. Its non-execution means the Phase 4 decision cannot be (A) Accept — only (E) Undetermined.

---

## 6. Order of testing

Tests are performed in this order:

1. **A-F1** — before A-F2 (A-F2 presupposes a remainder).
2. **A-F2** — before A-F3 (A-F3 presupposes a function to decentralize).
3. **A-F3** — before A-F4 (A-F4 presupposes that A-F3 holds).
4. **A-F4** — last, because it requires a working definition of the candidate.

If any earlier test falsifies its condition, later tests are not performed.

---

## 7. Decision rule (restated)

| Outcome of tests | Decision |
|---|---|
| A-F1, A-F2, A-F3 not falsified; A-F4 supported by measured results | (A) Accept |
| A-F1, A-F2, A-F3 not falsified; A-F4 not executed or not supported | (E) Undetermined |
| Any of A-F1, A-F2, A-F3 falsified | (R) Reject |
| Fn1–Fn5 foldable into one existing dimension | (F) Fold |
| Tests cannot be performed for external reasons | (D) Defer |

---

## 8. What this plan does not claim

- That the tests have been executed.
- That the readings in `RESPONSIBILITY_BOUNDARIES.md` are correct.
- That A-F2 will survive composition.
- That A-F3 will hold in the adversarial case.
- That A-F4 will show a benefit.

This document is a **plan**. It states what would be tested, and how. It does not state what the result would be.

---

## 9. Next steps

1. **Internal review** of this plan (Phase 3 completeness).
2. **Independent review** of this plan and the hypothesis (Phase 2).
3. **Execution** of the tests — requires Phase 5 and 6, which are not permitted.
4. **Decision** (Phase 4) — interim until tests are executed.

---

**AetherAudit v1.0.0 — Falsification Plan**
© 2026 Samir Baladi — Ronin Institute / Rite of Renaissance
DOI: [10.5281/zenodo.24274628](https://doi.org/10.5281/zenodo.24274628)
