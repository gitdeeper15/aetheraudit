---
title: "AetherAudit: Verifiable Evidence and Accountability Infrastructure for Autonomous Agent Systems"
subtitle: "A Falsification-First Investigation of Audit, Evidence, and Responsibility in Decentralized Multi-Agent Systems"
author: "Samir Baladi"
affiliation: "Ronin Institute / Rite of Renaissance"
email: "gitdeeper@gmail.com"
orcid: "0009-0003-8903-0029"
version: "1.0.0"
date: "November 2026"
doi: "10.5281/zenodo.24274628"
license: "CC-BY-4.0"
lang: "en"
---

# AetherAudit: Verifiable Evidence and Accountability Infrastructure for Autonomous Agent Systems

**A Falsification-First Investigation of Audit, Evidence, and Responsibility in Decentralized Multi-Agent Systems**

**Samir Baladi**
Ronin Institute / Rite of Renaissance
ORCID: [0009-0003-8903-0029](https://orcid.org/0009-0003-8903-0029) · Email: gitdeeper@gmail.com
**Version:** 1.0.0 · **Date:** November 2026 · **DOI (Zenodo):** [10.5281/zenodo.24274628](https://doi.org/10.5281/zenodo.24274628)
**DOI (Figshare):** [10.6084/m9.figshare.35023519](https://doi.org/10.6084/m9.figshare.35023519)
**License:** CC-BY-4.0

---

## Abstract

AetherAudit is the tenth candidate of the Aether family. It investigates whether a decentralized audit gap genuinely exists between runtime monitoring (AetherRuntime), policy enforcement (AetherPolicy), and identity (AetherIdentity). The central question is: *how can operational evidence be produced, kept intact, and used to reconstruct what actually happened and attribute responsibility — in decentralized autonomous agent systems — independently of runtime monitoring and policy enforcement?* Five functions (Fn1–Fn5) are proposed: Evidence Capture, Evidence Integrity, Execution Reconstruction, Responsibility Attribution, and Audit Verification. Four failure conditions (A-F1–A-F4) are stated. None has been falsified by argument alone, but A-F4 (observable benefit) is untested. Two propositions are stated as proof sketches: P1 (determinism of reconstruction) is near-trivial; P2 (irreducible trust anchor) cuts against independence. The Phase 4 decision is **(E) undetermined (interim)**: the evidence is insufficient to accept AetherAudit as an independent architectural dimension, and insufficient to reject it. No implementation, test, or experiment is reported. AetherAudit is a candidate, not a result.

**Keywords:** audit, evidence integrity, accountability, autonomous agents, multi-agent systems, falsification-first methodology, architectural investigation

---

## 1. Introduction

### 1.1 The Aether family and the tenth candidate

The Aether family currently has seven foundational dimensions and two unresolved candidates. The foundational dimensions are AetherGit (storage), AetherFlow (integration), AetherProof (verification), AetherMesh (decentralization), AetherGovern (governance authority), AetherRuntime (runtime assurance), and AetherOrchestrate (orchestration). The candidates are AetherIdentity (eighth) and AetherPolicy (ninth), both of which remain unresolved. AetherAudit is proposed as the tenth candidate.

AetherAudit does not replace any existing project. It does not renumber any existing project. Its independence from the existing dimensions is not assumed; it is the subject of this investigation.

### 1.2 Why audit is not monitoring, not policy, not identity

Three questions are frequently conflated in discussions of autonomous agent systems:

- **AetherRuntime** asks: *what is happening during execution?*
- **AetherPolicy** asks: *is this action permitted by the policy?*
- **AetherIdentity** asks: *who is the acting agent?*

AetherAudit asks a different question: *what can be proven after the fact, with what evidence, and on whom does responsibility fall?*

A system can be monitored, policy-compliant, and identity-resolved, and still be **non-auditable**. The evidence required to reconstruct an action may not have been captured; the captured evidence may not have been kept intact; the identity may not be linkable to the action; and the verification procedure may depend on trust in the auditor rather than on the evidence itself.

This distinction is not new. Recent work on auditable agents (arXiv, 2026) explicitly separates accountability from auditability and from the audit process, and states five conditions for auditability: action recovery, lifecycle coverage, policy-checkability from evidence, responsibility attribution, and evidence integrity. Internet-Drafts from IETF for agent-to-agent communication (A2A) separate identity, delegation, and audit. Provenance literature and tamper-evident log literature provide primitives that an audit layer would consume.

But the existence of audit research does not establish the existence of an independent architectural dimension within Aether. That is the question this paper tests.

### 1.3 Contribution and non-contribution

This paper contributes:

1. A stated hypothesis, formulated to be falsifiable.
2. Five functions (Fn1–Fn5) proposed as an initial scope.
3. Four failure conditions (A-F1–A-F4) stated.
4. Two propositions (P1–P2) as proof sketches.
5. A Phase 4 decision of **(E) undetermined (interim)**.

This paper does **not** contribute: an implementation, a specification, an experiment, a benchmark, or a claim of independence. It does not propose an API, a schema, a protocol, or a reference architecture. It does not claim that AetherAudit is the tenth dimension; it claims that AetherAudit is the tenth candidate, and that its status is undetermined.

---

## 2. Related Work

### 2.1 Auditable agents

The recent literature on auditable agents (arXiv, 2026) distinguishes three concepts that are often conflated: **accountability** (who is responsible), **auditability** (whether the system can be audited), and **the audit process** (the procedure by which an auditor reaches a verdict). It states five conditions for auditability: (i) action recovery, (ii) lifecycle coverage, (iii) policy-checkability from evidence, (iv) responsibility attribution, and (v) evidence integrity. AetherAudit adopts these conditions as a starting point, but does not assume them to be complete or sufficient. [citation needed]

### 2.2 IETF A2A drafts

Internet-Drafts for agent-to-agent (A2A) communication separate **identity**, **delegation**, **audit**, and **provenance**. These drafts are working documents, not standards. They reinforce the point that identity and audit are distinct responsibilities; they do not resolve the architectural question of whether audit is an independent dimension within a family of dimensions. [citation needed]

### 2.3 Provenance and tamper-evident logs

The provenance literature (W3C PROV and successors) and the tamper-evident log literature (Merkle trees, transparency logs) provide primitives that AetherAudit would consume but would not replace. AetherProof is the natural home for verification primitives within the Aether family; AetherMesh is the natural home for distribution primitives. The question is whether AetherAudit adds a remainder beyond these.

### 2.4 Accountability in multi-agent systems

Accountability has been studied in multi-agent systems under **norms**, **sanctions**, and **institutions**. These frameworks describe what accountability *is*; they do not, in themselves, provide the evidence infrastructure required to *establish* accountability after the fact. The literature distinguishes attribution (who acted), responsibility (who is answerable), and liability (who bears the consequence). AetherAudit is concerned with the first two, not with liability.

### 2.5 The gap

The gap, if it exists, is not the absence of audit research. It is the absence of an architectural placement of audit responsibilities within the Aether family — specifically, a placement that is not already covered by AetherRuntime, AetherPolicy, AetherIdentity, AetherGit, AetherProof, or AetherGovern. Whether this gap is real is the subject of A-F1 and A-F2.

---

## 3. The Aether Family Context

### 3.1 Seven foundational dimensions

The seven foundational dimensions are:

| # | Project | Dimension |
|:-:|---|---|
| 1 | AetherGit | Storage and versioning |
| 2 | AetherFlow | Integration |
| 3 | AetherProof | Verification |
| 4 | AetherMesh | Decentralization |
| 5 | AetherGovern | Governance authority |
| 6 | AetherRuntime | Runtime assurance |
| 7 | AetherOrchestrate | Orchestration |

### 3.2 Candidates 8 and 9

AetherIdentity (eighth) and AetherPolicy (ninth) are candidates, not foundational dimensions. AetherIdentity has a paper and a v2.0.0 implementation, but its architectural independence is unresolved. AetherPolicy has a paper and a Phase 4 decision of (E) undetermined, and no implementation. Neither is replaced by AetherAudit.

### 3.3 Position of AetherAudit

AetherAudit is the tenth candidate. It is positioned between AetherGovern (which supplies authority to issue verdicts), AetherProof (which supplies verification primitives), AetherMesh (which supplies distribution primitives), AetherGit (which supplies storage), AetherRuntime (which supplies runtime observations), AetherPolicy (which supplies compliance decisions), and AetherIdentity (which supplies identity). The question is whether this position is a *distinct architectural dimension* or a *feature* of one or more existing dimensions.

---

## 4. Central Question and Scope

### 4.1 The question

> How can operational evidence be produced, kept intact, and used to reconstruct what actually happened and attribute responsibility — in decentralized autonomous agent systems — independently of runtime monitoring and policy enforcement?

### 4.2 Five functions (Fn1–Fn5)

| # | Function | Question |
|:-:|---|---|
| Fn1 | Evidence Capture | How is evidence about an action, in its context, captured so that it can be examined later? |
| Fn2 | Evidence Integrity | How is evidence integrity ensured, and how is tampering or deletion detected? |
| Fn3 | Execution Reconstruction | How is the execution trace — actions, transformations, and delegations — rebuilt, including when records are incomplete? |
| Fn4 | Responsibility Attribution | How is responsibility attributed to an agent, principal, or delegation chain in a defensible way? |
| Fn5 | Audit Verification | How can an independent party verify evidence and issue an audit verdict without assuming trust in the auditor? |

### 4.3 Non-assumptions

The five functions are **not** assumed to be complete, independent, or necessary. A later phase may drop one, merge two, or add a sixth. They are an initial scope, not a final list.

---

## 5. Architectural Hypothesis

### 5.1 The hypothesis

> A potentially independent architectural gap may exist between runtime monitoring, policy enforcement, and identity: the operational management of audit evidence — its capture, integrity, reconstruction, attribution, and independent verification — across decentralized autonomous agents.

This hypothesis is stated to be falsifiable. It is falsified if:

- AetherRuntime already provides all audit requirements without an additional layer (A-F1).
- AetherGit plus runtime logs plus policy decisions cover the five functions with bounded integration (A-F2).
- No independent properties of evidence integrity, reconstruction, or attribution exist (A-F2).
- The candidate is only an aggregation of existing logs under a unified interface (A-F2).
- A central audit authority is required (A-F3).
- No observable benefit is demonstrated (A-F4).

### 5.2 Boundaries with the seven foundational dimensions

| Dimension | Responsibility | Relation to AetherAudit |
|---|---|---|
| AetherGit | Storage and versioning | AetherAudit consumes evidence storage; it does not store source |
| AetherFlow | Integration | AetherAudit records integration events as evidence; it does not integrate |
| AetherProof | Verification | AetherAudit consumes verification primitives; it does not replace AetherProof |
| AetherMesh | Decentralization | AetherAudit relies on AetherMesh for distribution; it does not distribute itself |
| AetherGovern | Governance authority | AetherAudit consumes authority to issue verdicts; it does not issue it |
| AetherRuntime | Runtime assurance | AetherAudit consumes runtime observations as evidence; it does not monitor |
| AetherOrchestrate | Orchestration | AetherAudit records orchestration decisions as evidence; it does not orchestrate |

Additional boundaries with candidates:

| Dimension | Relation to AetherAudit |
|---|---|
| AetherIdentity | AetherAudit uses identity to attribute responsibility; it does not determine identity |
| AetherPolicy | AetherAudit records compliance decisions as evidence; it does not evaluate policy |

### 5.3 What the hypothesis does not claim

The hypothesis does not claim that:

- AetherAudit is an independent architectural dimension.
- The five functions are complete, independent, or necessary.
- The boundaries with the existing dimensions are sufficient.
- The gap is genuine.
- Implementation should begin.
- Any observable benefit has been demonstrated.

---

## 6. Falsification Methodology

### 6.1 Falsification-first, not confirmation-first

AetherAudit follows the falsification-first methodology of AetherPolicy. A candidate is accepted only if it survives its failure conditions, not if it accumulates supporting evidence. This is a methodological choice: it is easier to accumulate support than to demonstrate survival.

### 6.2 Failure conditions A-F1 → A-F4

| ID | Claim under test | Status |
|:-:|---|:-:|
| A-F1 | Non-redundancy: not covered by Runtime / Policy / Identity | 🟡 Not falsified (author's reading of own records) |
| A-F2 | Distinction from Runtime + Git (a remainder survives after composition) | 🟡 Not falsified (remainder may be small) |
| A-F3 | Decentralizability: no central audit authority required | 🟡 Not falsified (residuals: revocation window, honest auditor) |
| A-F4 | Observable benefit | 🔴 **Untested** |

> "Not falsified" is a weaker status than "confirmed". "Untested" is not a pass. The decision rule requires all four to be tested with none falsified, and A-F4 supported by measured results.

### 6.3 Decision rule

If any of A-F1, A-F2, or A-F3 is falsified: the candidate is **rejected**.
If all of A-F1, A-F2, A-F3 are not falsified but A-F4 is untested: the candidate is **(E) undetermined**.
If all four are not falsified and A-F4 is supported by measured results: the candidate is **(A) accepted**.
If the candidate is better classified as a feature of an existing dimension: it is **(F) folded**.
If the decision is postponed for an external reason: **(D) deferred**.

---

## 7. Propositions P1–P2

### 7.1 P1: determinism of reconstruction

**Statement.** If the evidence is complete and intact, reconstruction of the execution trace is a deterministic function of the evidence.

**Status.** Proof sketch. P1 is close to trivial: it says that a pure function of its inputs is a function of its inputs. Its content is in the conditions of **completeness** and **intactness**, which real systems can violate. The conditions (Purity1–Purity4) are not stated formally here; they are the subject of future work.

### 7.2 P2: irreducible trust anchor

**Statement.** Any deterministic, interactive audit-verification procedure rests on a trust anchor that the evidence itself cannot supply.

**Status.** Proof sketch. P2 rests on a symmetry argument: a binary verification outcome (accept / reject) requires a decision about *standing* when the evidence does not determine it. The decision about standing is plausibly a governance matter. This cuts **against** independence: if the trust anchor is AetherGovern, then audit verification is a governance function, not an independent one.

### 7.3 What P1 and P2 do not establish

P1 does not establish that reconstruction is possible in practice; it only establishes that reconstruction is a function of evidence, if evidence is complete and intact. P2 does not establish that audit verification requires a central authority; it only establishes that it requires an anchor. Neither is machine-checked.

---

## 8. Decision (Phase 4)

### 8.1 (E) Undetermined (interim)

AetherAudit is classified as **(E) undetermined (interim)**. The evidence is insufficient to accept AetherAudit as an independent dimension, and insufficient to reject it. A test is needed to decide.

### 8.2 Why not (A) accept

- A-F4 is untested: no benefit has been measured.
- A-F2 remainder may be small.
- A-F3 has residuals: revocation window, honest auditor.
- P1 is near-trivial; P2 cuts against independence.
- AetherIdentity (which supplies one of the inputs) is itself unresolved.

### 8.3 Why not (R) reject

- No failure condition has been falsified.
- The comparison found a remainder after composition with the neighbours (A-F2).
- The decentralization argument did not reach a requirement for a central decision point (A-F3).
- The rejection would rest on the same author's reading that is here judged insufficient to accept.

### 8.4 What would change the decision

To move from (E) to (A):

1. A-F4 must be supported by measured results from a scenario that exercises Fn1–Fn5.
2. A-F2 must be shown to yield a non-trivial remainder.
3. A-F3 must be shown to hold without an honest-auditor assumption.

To move from (E) to (R):

1. A-F1 or A-F2 must be falsified.

To move from (E) to (F):

1. The remainder must be shown to fit within a single existing dimension.

---

## 9. Evaluation Design (Proposal, Not Executed)

### 9.1 Scenarios S1–S6

| # | Scenario |
|---|---|
| S1 | Distributed multi-agent environment, no central audit authority |
| S2 | Missing logs — reconstruction under incomplete evidence |
| S3 | Evidence tampering — detection and integrity preservation |
| S4 | Deep delegation chain — attribution across a chain |
| S5 | Inter-agent dispute — independent audit and verdict |
| S6 | Long-term retention — audit evidence across time |

### 9.2 Metrics M1–M9

| # | Metric |
|---|---|
| M1 | Evidence completeness |
| M2 | Evidence integrity |
| M3 | Reconstruction accuracy |
| M4 | Attribution accuracy |
| M5 | Verification independence |
| M6 | Retrieval latency |
| M7 | Evidence size |
| M8 | Auditability |
| M9 | Tamper resistance |

### 9.3 Baselines B1–B5

| # | Baseline |
|---|---|
| B1 | No audit layer (runtime + Git only) |
| B2 | AetherRuntime + AetherGit, manual audit |
| B3 | AetherRuntime + AetherGit + AetherPolicy |
| B4 | AetherRuntime + AetherGit + AetherPolicy + AetherProof |
| B5 | AetherRuntime + AetherGit + AetherPolicy + AetherProof + AetherMesh |

### 9.4 Mapping scenarios → metrics → failure conditions

| Scenario | Metrics | Failure condition |
|---|---|---|
| S1 | M5, M8 | A-F3 |
| S2 | M3 | A-F2 |
| S3 | M2, M9 | A-F1 |
| S4 | M4 | A-F1, A-F2 |
| S5 | M5, M8 | A-F4 |
| S6 | M1, M7 | A-F4 |

### 9.5 No measurement has been executed

**No measurement has been executed.** Section 9 is a proposal, not a result. The mapping from scenarios to metrics to failure conditions is a design, not an evaluation.

---

## 10. Threats to Validity

| ID | Threat | Consequence |
|:-:|---|---|
| T1 | Author-on-author reasoning | A-F1–A-F3 rest on the author's reading of the author's own records |
| T2 | No independent review | Phase 2 (Hypothesis Review) has not started |
| T3 | Small A-F2 remainder | A-F2's non-falsification may reflect a small remainder rather than an independent dimension |
| T4 | Honest-auditor assumption | A-F3 assumes an honest auditor; adversarial auditors are not considered |
| T5 | Irreducible trust anchor | P2 cuts against independence, but its strength is not established |
| T6 | No measurement | A-F4 is untested |
| T7 | Unresolved AetherIdentity | The eighth project is itself unresolved |

---

## 11. Discussion

### 11.1 What AetherAudit would change if independent

If AetherAudit is accepted as independent, it would provide an architectural home for the audit responsibilities that are currently distributed across Runtime (monitoring), Policy (enforcement), Identity (attribution), Proof (verification), Mesh (distribution), and Git (storage). It would not replace any of these; it would add a placement that is currently missing.

### 11.2 What it would not change

AetherAudit would not change the responsibilities of the existing dimensions. It would not replace AetherRuntime, AetherPolicy, AetherIdentity, AetherProof, AetherMesh, AetherGit, AetherGovern, or AetherOrchestrate. It would consume their outputs and produce audit artifacts.

### 11.3 Why "undetermined" is a legitimate result

"Undetermined" is not a failure. It states that the evidence is insufficient to decide, and names what is missing. In a falsification-first methodology, "undetermined" is the correct outcome when a candidate has not been tested against its observable-benefit condition. It is the state of AetherPolicy, and it is the state of AetherAudit.

---

## 12. Conclusion

AetherAudit is the tenth candidate of the Aether family. It is a research repository, not a software repository. It contains a hypothesis, five functions, four failure conditions, and two propositions. The Phase 4 decision is **(E) undetermined (interim)**. No implementation, test, or experiment is reported. The next step is independent review, not implementation.

**AetherAudit is a candidate, not a result.**

---

## Acknowledgements

The author thanks the Ronin Institute and Rite of Renaissance for institutional support. The paper is a continuation of the falsification-first methodology developed in AetherPolicy v0.1.0.

---

## References

1. Baladi, S. (2026). *AetherPolicy: Decentralized Policy Lifecycle and Enforcement for Autonomous Agent Systems*. Zenodo. DOI: 10.5281/zenodo.24160047.
2. Auditable Agents. (2026). arXiv preprint. [citation needed]
3. IETF A2A drafts. (2026). Internet-Drafts. [citation needed]
4. Moreau, L., & Groth, P. (2013). *Provenance: An Introduction to PROV*. Morgan & Claypool.
5. Crosby, S., & Wallach, D. (2009). *Efficient Data Structures for Tamper-Evident Logging*. USENIX Security.
6. Laurie, B., Langley, A., & Kasper, E. (2013). *Certificate Transparency*. RFC 6962.
7. [citation needed] — multi-agent accountability literature.
8. [citation needed] — norms and sanctions in multi-agent systems.
9. [citation needed] — provenance in distributed systems.
10. [citation needed] — auditability in distributed systems.

*Additional references to be added in v1.0.1.*

---

## Appendix A — Aether family (10 projects)

| # | Project | Status | DOI |
|:-:|---|---|---|
| 1 | AetherGit | Foundational | 10.5281/zenodo.23976986 |
| 2 | AetherFlow | Foundational | 10.5281/zenodo.23979129 |
| 3 | AetherProof | Foundational | 10.5281/zenodo.24013124 |
| 4 | AetherMesh | Foundational | 10.5281/zenodo.24038038 |
| 5 | AetherGovern | Foundational | 10.5281/zenodo.24054524 |
| 6 | AetherRuntime | Foundational | 10.5281/zenodo.24078477 |
| 7 | AetherOrchestrate | Foundational | 10.5281/zenodo.24095399 |
| 8 | AetherIdentity | Candidate | 10.5281/zenodo.24102739 |
| 9 | AetherPolicy | Candidate | 10.5281/zenodo.24160047 |
| 10 | **AetherAudit** | **Candidate (this paper)** | **10.5281/zenodo.24274628** |

---

## Appendix B — Glossary

- **A-F1–A-F4**: Failure conditions for AetherAudit.
- **Fn1–Fn5**: Five functions proposed as initial scope.
- **P1–P2**: Two propositions stated as proof sketches.
- **(E) undetermined**: The Phase 4 decision state — insufficient to accept, insufficient to reject.
- **Evidence Bundle**: The set of artifacts captured about an action, in its context.
- **Sealed Evidence**: Evidence that has been hashed, signed, and distributed.
- **Reconstructed Trace**: The rebuilt execution sequence, derived from evidence.
- **Attribution Report**: The mapping from an action to an agent, principal, or delegation chain.
- **Audit Verdict**: The outcome issued by an independent verifier.

---

## Appendix C — Change log (v0.1.0 → v1.0.0)

**v0.1.0** (November 2026, hypothetical initial draft):
- Central question stated.
- Five functions (Fn1–Fn5) proposed.
- Four failure conditions (A-F1–A-F4) stated.
- Two propositions (P1–P2) as proof sketches.
- Decision: (E) undetermined.

**v1.0.0** (November 2026, this paper):
- Related Work expanded.
- Aether family context expanded.
- Boundaries with the seven foundational dimensions + two candidates.
- Evaluation design (Section 9) added as a proposal, not executed.
- Threats to validity (Section 10) added.
- Appendices A–C added.
- DOI assigned: 10.5281/zenodo.24274628.

---

**AetherAudit v1.0.0**
© 2026 Samir Baladi — Ronin Institute / Rite of Renaissance
DOI: [10.5281/zenodo.24274628](https://doi.org/10.5281/zenodo.24274628)
License: CC-BY-4.0

**AetherAudit is a candidate, not a result.**
