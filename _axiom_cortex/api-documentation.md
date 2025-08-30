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

**1) Normalization (z-scores)**  
