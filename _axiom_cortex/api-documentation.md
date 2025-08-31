---
layout: page
title: "Evaluation Overview — Axiom Cortex™ (No Public API)"
description: "Proprietary, internal evaluation inside Nearshore IT Co-Pilot™. Methods, signals, and math—no external endpoints."
section: axiom-cortex
permalink: /axiom-cortex/api-documentation/
---

# Evaluation Overview — Axiom Cortex™ (No Public API)

**What it is:** Axiom Cortex™ is a **proprietary, internal evaluation service** inside the Nearshore IT Co-Pilot™ platform. There is **no public API**. All evaluations run inside our platform to align and predict talent performance using **44 psychometric + NLP signals** on top of LLMs with **semantic chunking in RAG and staged/multi-step prompting**. We apply **language-fairness calibration** (judge ideas and reasoning, not accent/phrasing) and perform **expert review of flags before roll-up**. Results map to **BARS** (*Behaviorally Anchored Rating Scales = ratings tied to observable behaviors*).

---

## Inputs (plain English)

- **Role & level** (e.g., Senior Backend L3, domain context)  
- **Tech stack** (languages, frameworks, cloud)  
- **Work artifacts** (code/PRs/tickets/design notes)  
- **Scenario tasks** (staged reasoning + coding prompts)  
- **Communication samples** (written/async)  
- **Operational signals** (security, reliability, cost awareness)

---

## Method core

- **Semantic chunking in RAG** — split artifacts into meaningful chunks; retrieval guided by role/stack so prompts aren’t one-size-fits-all.  
- **Staged / multi-step prompting** — plan → subgoals → verification; require chain integrity before scoring.  
- **Language-fairness calibration** — normalize signal distributions across language cohorts so phrasing/accents don’t depress scores.  
- **Expert review of flags before roll-up** — only flagged anomalies go to experts; decisions apply **before** final aggregation.

---

## The 44 Signals (executive view)

**A. Alignment (5)**  
1) Problem–schema match • 2) Stack coverage • 3) Complexity bandwidth • 4) Domain transfer • 5) Requirements fidelity

**B. Analysis (7)**  
6) Chain integrity • 7) Error-mode awareness • 8) Counterfactuals • 9) Causal linkage • 10) Evidence binding • 11) Numeracy checks • 12) Ambiguity handling

**C. Synthesis (6)**  
13) Composability • 14) Architectural tradeoffs • 15) Edge-case coverage • 16) Observability planning • 17) Dependency hygiene • 18) Migration/rollback planning

**D. Code Quality (6)**  
19) Semantic diff quality • 20) Static risks • 21) Runtime realism • 22) Test intent/coverage • 23) Debug vectoring • 24) Complexity control

**E. Communication & Collaboration (6)**  
25) Instruction uptake • 26) Audience targeting • 27) Decision log clarity • 28) Review acumen • 29) Ticket hygiene • 30) Documentation atomics

**F. Systems & Ops (5)**  
31) Reliability thinking (SLOs) • 32) Cost–performance • 33) Release safety • 34) Infra-as-code • 35) Telemetry interpretation

**G. Risk & Security (5)**  
36) Sensitive-data handling • 37) License hygiene • 38) Supply-chain care • 39) Threat-modeling reflex • 40) Secrets/access discipline

**H. Robustness & Agreement (4)**  
41) Adversarial resistance • 42) Cross-model agreement • 43) Self-consistency • 44) Hallucination index

---

## Processing & formulas (transparent math, plain English)

> We keep formulas readable here and reserve proofs/derivations for **Scientific Foundations**.

**1) Normalization (z-scores)**  
Each raw signal \(s_i\) is normalized within role/level cohorts:  
`z_i = (s_i − μ_role,level) / σ_role,level` (robust μ/σ with outlier guards).  
This keeps scores comparable across roles and seniorities.

**2) L2-aware weighting**  
We decompose communication into semantic vs. form carriers with weights \(\alpha\) and \(\beta\):  
`Score_comm = α·SemContent + β·Form`, with `β → 0` as L2 uncertainty rises (estimated from stable markers).  
Meaning: grammar/fluency noise is down-weighted; ambiguous content is still penalized.

**3) Cross-lingual semantic fidelity (FSD)**  
We compare answer embeddings to an Ideal Answer Blueprint distribution via a Fréchet-style distance.  
Lower FSD ⇒ closer to the target concept even with Spanish-influenced English.

**4) Optimal transport (W2) with code-switch mask**  
Token alignment uses W2 distance with **neutral cost** for common bilingual markers (e.g., “pues”, “o sea”).  
This prevents code-switch tokens from inflating “distance” when the substantive idea matches.

**5) DIF checks & correction**  
For each rubric item, we test **Differential Item Functioning** across language cohorts at matched ability.  
Items with significant DIF are adjusted or removed; if unresolved, the model **fails closed** for that item.

**6) Aggregation (monotone link)**  
Signals roll up through constrained aggregators:  
- **Isotonic regression / monotone lattice** ensure stronger evidence doesn’t produce weaker scores.  
- **Skill graph priors** (network psychometrics) stabilize multi-stack profiles.

**7) Uncertainty & calibration**  
Every composite score includes uncertainty (bootstrap CIs / calibrated posteriors).  
We monitor Expected Calibration Error (ECE) and produce reliability diagrams by cohort.

**8) BARS mapping (human-readable)**  
Final scores map to **BARS** (ratings tied to observable behaviors) so feedback is specific, fair, and actionable.

**9) Decision layer (constrained utility)**  
Recommendations maximize expected utility **subject to** fairness/reliability gates:  
`maximize E[U | evidence]  s.t.  DIF ≤ δ,  G ≥ G_min,  P[Collab < τ_c] ≤ ε_c`  
Lagrangian relaxations provide gate-aware choices with justifications.

---

## Outputs you see (inside the platform)

- **Per-dimension evidence** with human-readable rationales  
- **Uncertainty bounds** and cohort-level calibration notes  
- **Gate status** (fairness/reliability) and any expert-review outcomes  
- **BARS-anchored feedback** and promotion signals (L1–L4)

---

## Publications & research

- SSRN: [Redesigning Human Capacity in Nearshore IT Staff Augmentation (5165433)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5165433) — DOI [10.2139/ssrn.5165433](https://doi.org/10.2139/ssrn.5165433)  
- SSRN Working Paper: [abstract_id=5253470](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5253470)  
- SSRN Working Paper: [abstract_id=5188490](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5188490)  
- Google Scholar — TeamStation AI: <https://scholar.google.com/citations?user=aNol-ycAAAAJ>

More: **[Publications page](/publications/)**

---

## Platform context (no external endpoints)

Axiom Cortex™ powers the **Nearshore IT Co-Pilot™**—one platform to hire, equip, secure, and pay LATAM engineers **under one SLA**. There is **no external API**.

**Authority anchors:**  
- [nearshore IT platform](https://teamstation.dev/nearshore-integrated-services)  
- [Cognitive AI evaluation](https://teamstation.dev/technical-interview-evaluation)  
- [hire LATAM engineers](https://teamstation.dev/latam-talent)  
- [devices and MDM](https://teamstation.dev/nearshore-it-staff-augmentation-pricing/flexible-secure-device-management-latam-it)
