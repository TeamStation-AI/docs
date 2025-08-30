---
layout: page
title: "Axiom Cortex™ Method Map — v3.0.0 (Science Only)"
description: "Canonical map of Axiom Cortex™: signals (44), L2 fairness, semantic chunking in RAG, staged/multi-step prompting, measurement models, BARS mapping, decision layer, reliability, protocol, and evidence."
section: axiom-cortex
permalink: /axiom-cortex/method-map/
---

# Axiom Cortex™ Method Map — v3.0.0 (Science Only)

**Purpose:** Give CTOs a single, accurate view of *how* Axiom Cortex™ works — the math and process only.  
**Not included:** No public API, no vendor integration guides, no security docs. Axiom Cortex™ runs *inside* Nearshore IT Co-Pilot™.

---

## 1) Signal System (44 total) — what we measure
Grouped, audit-ready signals extracted from interview evidence and work samples:

- **Reasoning & Problem Decomposition** — goal factoring, constraint handling, trade-off narration, hypothesis sequencing.
- **Solution Design & Architecture Thinking** — interface contracts, boundary placement, failure modes, latency/cost awareness.
- **Code Quality Behaviors** — test intent, invariants, naming semantics, refactor triggers, complexity control.
- **Debugging Strategy** — fault localization steps, observability usage, minimal reproduction, rollback discipline.
- **Data & API Literacy** — schema inference, paging/limits, idempotency, consistency guarantees.
- **Concurrency & Performance** — race awareness, backpressure, caching safety, throughput/latency balancing.
- **Security & Reliability Cues** — input hardening, key/secret hygiene (conceptual), blast-radius thinking.
- **Collaboration Signals** — turn-taking, clarification prompts, disagreement framing, commit hygiene.
- **Language-Fair Communication** — idea clarity under L2 variance, ambiguity repair, evidence referencing.
- **Meta-cognition** — uncertainty surfacing, plan revision moments, verification loops.

> The 44 signals live across these families; each has a rubric, evidence extractor, and stability test. (Full catalog appears as a separate **Signal Catalog** page in the next step.)

---

## 2) L2-Aware Fairness Layer — language-fairness calibration
- **Proficiency-normalized scoring:** \( C=\alpha C_{\text{sem}} + \beta C_{\text{form}} \) with \(\beta \to 0\) as L2 uncertainty rises.
- **Cross-lingual semantic fidelity (FSD):** Fréchet-style distance on multilingual embeddings.
- **Optimal transport with code-switch mask:** W2 with neutral costs for bilingual markers (Sinkhorn).
- **DIF checks:** Mantel–Haenszel / logistic DIF; biased items adjusted or dropped.
- **Calibration:** reliability diagrams, ECE; paraphrase/word-order stress tests.

---

## 3) Evidence Orchestration — semantic chunking & staged prompting
- **Semantic chunking in RAG:** split transcripts into meaning-bearing units aligned to rubrics and Blueprints of Ideal Answers.
- **Staged / multi-step prompting:** extract → evaluate → normalize → aggregate; adversarial paraphrase checks at each stage.
- **Flag policy:** any uncertainty or contradiction is flagged for **expert review of flags before roll-up**.

---

## 4) Measurement Models — from evidence to traits
- **Non-parametric link:** isotonic regression to keep monotonic relations (more evidence → higher trait).
- **Monotone neural / lattice layers:** partial-order constraints where applicable.
- **Network psychometrics:** Gaussian Graphical Model + stability selection → **skill connectivity map**.

---

## 5) Scoring & BARS mapping — explainable outcomes
- **Trait estimates** carry uncertainty bounds and stability notes.
- **BARS** = Behaviorally Anchored Rating Scales (ratings tied to **observable behaviors**), with role-specific anchors L1–L4.
- **Report artifacts:** per-question evidence, per-signal scores, rubric hits, and BARS summaries.

---

## 6) Decision Layer — constrained Bayesian utility
\[
\max_{\mathcal{R}} \mathbb{E}[U(\mathcal{R}\mid \mathbf{e})]\quad
\text{s.t. } \Pr[\text{Collab}<\tau_c]\le\epsilon_c,\; \text{DIF}_k\le\delta,\; G\ge G_{\min}
\]
Outputs include pass/hold/fail with justification, fairness/reliability gates, and confidence intervals.

---

## 7) Reliability & Monitoring — trust math
- **Generalizability \(G\)** across rater/question/time facets.
- **Random Matrix Theory guard:** remove non-replicating spikes outside Marchenko–Pastur support.
- **Drift & stability:** test–retest, bootstrap CIs, calibration-within-groups.

---

## 8) Protocol — how we evaluate (operational)
- **Data & splits:** anonymized interviews; stratified by role & locale; nested CV; seeded folds.
- **Metrics:** AUC/PR, Kendall’s \( \tau \), Brier score, ECE/MCE; fairness gaps (parity, equalized odds), DIF counts.
- **Ablations:** remove L2 layer / skill-graph / non-parametric link and observe degradations.
- **Red-team:** adversarial paraphrase, negation/hedging, verbosity/terseness controls; out-of-domain → “insufficient evidence”.

---

## 9) Evidence Locker — audit trail
Transcripts, embeddings, partial-corr matrices, calibration plots, gate statuses, and a **provenance manifest** (versions, seeds, hashes). Rollbacks available by bundle hash.

---

## 10) Where to read the math
- **Scientific Foundations (full math/audit):** [/docs/axiom-cortex/scientific-foundations/](/docs/axiom-cortex/scientific-foundations/)
- **Publications & Research:** [/docs/publications/](/docs/publications/)  
  SSRN: [5165433](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5165433) • [5253470](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5253470) • [5188490](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5188490)

---

## Platform context (no API exposed)
Axiom Cortex™ powers the **Nearshore IT Co-Pilot™** — one platform to hire, equip, secure, and pay LATAM engineers **under one SLA**.  
Authority links:
- [nearshore IT platform](https://teamstation.dev/nearshore-integrated-services)  
- [Cognitive AI evaluation](https://teamstation.dev/technical-interview-evaluation)  
- [hire LATAM engineers](https://teamstation.dev/latam-talent)  
- [devices and MDM](https://teamstation.dev/nearshore-it-staff-augmentation-pricing/flexible-secure-device-management-latam-it)
