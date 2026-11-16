# AetherAudit — Responsibility Boundaries

**Status:** Phase 1 (Responsibility Mapping) — work in progress.
**Date:** 2026-11-16
**Version:** 1.0.0
**Author:** Samir Baladi
**ORCID:** [0009-0003-8903-0029](https://orcid.org/0009-0003-8903-0029)
**License:** CC-BY-4.0 (this document)

---

## 0. Purpose

This document maps the surface of the existing Aether dimensions against the five functions of AetherAudit (Fn1–Fn5). It is the first test of the hypothesis stated in `ARCHITECTURAL_HYPOTHESIS.md`.

It does **not** conclude that AetherAudit is independent. It provides the material from which A-F1 and A-F2 can be tested. The mapping is a **first reading**; it is not a result.

---

## 1. Method

For each existing dimension (seven foundational, two candidates), and for each function (Fn1–Fn5), we ask:

- Does this dimension **provide** the function?
- Does it **partially** provide it?
- Does it **not** provide it?

The coverage is recorded in a matrix. The matrix is then examined for:

- **Full coverage** by a single existing dimension — if any function is fully covered, A-F1 is weaker for that function.
- **Composition** — if two or more existing dimensions together cover a function, A-F2 must be tested for a remainder.
- **Gaps** — functions not covered by any existing dimension. These are the potential remainders.

The matrix is **not** an experiment. It is a documentary reading by the author. Its confidence is limited by threat T1 (author-on-author reasoning).

---

## 2. Coverage Matrix

Legend:
- ● Full coverage (the dimension provides the function directly)
- ◐ Partial coverage (the dimension provides part of the function)
- ○ No coverage

| Dimension | Fn1 Capture | Fn2 Integrity | Fn3 Reconstruction | Fn4 Attribution | Fn5 Verification |
|---|:-:|:-:|:-:|:-:|:-:|
| **AetherGit** | ◐ | ◐ | ○ | ○ | ○ |
| **AetherFlow** | ◐ | ○ | ○ | ○ | ○ |
| **AetherProof** | ○ | ● | ○ | ○ | ◐ |
| **AetherMesh** | ◐ | ◐ | ○ | ○ | ○ |
| **AetherGovern** | ○ | ○ | ○ | ◐ | ◐ |
| **AetherRuntime** | ◐ | ○ | ◐ | ○ | ○ |
| **AetherOrchestrate** | ◐ | ○ | ○ | ○ | ○ |
| **AetherIdentity** | ○ | ○ | ○ | ◐ | ○ |
| **AetherPolicy** | ◐ | ○ | ○ | ○ | ○ |
| **AetherAudit** (candidate) | ● | ● | ● | ● | ● |

This matrix is a **reading**. It is not a measurement.

---

## 3. Reading by function

### 3.1 Fn1 — Evidence Capture

- **AetherGit** provides storage for evidence artifacts, but not the capture semantics.
- **AetherFlow** provides integration events that may serve as evidence, but not full evidence capture.
- **AetherMesh** provides distribution channels, but not capture.
- **AetherRuntime** provides runtime observations that may serve as raw evidence, but not the capture policy.
- **AetherOrchestrate** provides coordination decisions that may serve as evidence, but not capture.
- **AetherPolicy** provides compliance decisions that may serve as evidence, but not capture.

**Reading.** No existing dimension fully covers Fn1. The composition of Runtime + Git + Policy may provide partial coverage. Whether the remainder is non-trivial is a question for A-F2.

### 3.2 Fn2 — Evidence Integrity

- **AetherProof** provides verification primitives (hashing, signatures, Merkle proofs) and is the natural home for integrity primitives.
- **AetherGit** provides version integrity for stored artifacts.
- **AetherMesh** provides distribution, with integrity properties inherited from the underlying transport.

**Reading.** AetherProof comes closest to full coverage. If AetherProof is extended to cover evidence integrity, Fn2 may be **folded** into AetherProof, not AetherAudit. This is the **strongest challenge** to AetherAudit's independence.

### 3.3 Fn3 — Execution Reconstruction

- **AetherRuntime** provides runtime observations, but not reconstruction of traces from incomplete evidence.
- **AetherGit** provides storage of records, but not reconstruction logic.

**Reading.** No existing dimension fully covers Fn3. The remainder is potentially non-trivial. This is the **most favorable** function for AetherAudit.

### 3.4 Fn4 — Responsibility Attribution

- **AetherIdentity** provides identity, but not attribution to a delegation chain.
- **AetherGovern** provides authority to assign responsibility, but not the evidence-based attribution procedure.

**Reading.** Composition of Identity + Govern may provide partial coverage. The remainder may be small, or may be an independent problem.

### 3.5 Fn5 — Audit Verification

- **AetherProof** provides verification of artifacts.
- **AetherGovern** provides authority to issue verdicts.

**Reading.** Composition of Proof + Govern may cover Fn5. If so, AetherAudit's Fn5 is **folded** into the composition, not an independent function.

---

## 4. The key tension: A-F2

A-F2 asks whether a **remainder** survives after composing the existing dimensions. The matrix shows:

| Function | Closest existing dimension | Remainder |
|---|---|---|
| Fn1 | Runtime + Git + Policy | Likely non-trivial, but untested |
| Fn2 | AetherProof | Small; likely foldable |
| Fn3 | AetherRuntime | Potentially non-trivial |
| Fn4 | Identity + Govern | Unclear; depends on attribution semantics |
| Fn5 | Proof + Govern | Likely foldable |

**Reading.** The strongest challenge to AetherAudit is **Fn2**: AetherProof is already the natural home for evidence integrity, and extending AetherProof may cover Fn2 without a new dimension.

The strongest support for AetherAudit is **Fn3**: execution reconstruction from incomplete evidence is not covered by any existing dimension.

If A-F2 is to be resolved, it must be resolved function by function, not at the level of the whole candidate.

---

## 5. Possible decompositions

Three decompositions are possible, and none is ruled out:

### 5.1 Decomposition A — AetherAudit is independent

All five functions survive composition. AetherAudit is a separate dimension.

### 5.2 Decomposition B — AetherAudit folds into AetherProof

Fn2 (and possibly Fn5) are absorbed into AetherProof. Fn1, Fn3, Fn4 are distributed across Runtime, Git, Identity, Govern. AetherAudit is not a separate dimension.

### 5.3 Decomposition C — Partial independence

Fn3 (and possibly Fn4) survive composition. AetherAudit is a **narrower** dimension than initially proposed — covering reconstruction and attribution, but not capture, integrity, or verification.

Decomposition C is the most plausible outcome given the current reading. It is not the outcome; it is a hypothesis about the outcome.

---

## 6. What this document does not claim

- That AetherAudit is independent.
- That the coverage matrix is accurate.
- That the reading by function is correct.
- That the decompositions are exhaustive.
- That A-F2 is resolved.

This document is a **first mapping**. It provides material for A-F1 and A-F2. It does not decide them.

---

## 7. Next steps

In order:

1. **Independent review** of this mapping (Phase 2).
2. **Falsification design** for A-F1 and A-F2 (Phase 3).
3. **Measurement** of the remainder for each function (Phase 9, if permitted).

Stopping after step 1 is a legitimate outcome.

---

**AetherAudit v1.0.0 — Responsibility Boundaries**
© 2026 Samir Baladi — Ronin Institute / Rite of Renaissance
DOI: [10.5281/zenodo.24274628](https://doi.org/10.5281/zenodo.24274628)
