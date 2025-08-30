---
layout: page
title: "Scientific Foundations — Axiom Cortex™ (Audit-Ready)"
description: "Explicit math, protocols, and guardrails behind Axiom Cortex™: 44 psychometric + NLP signals, language-fairness calibration, staged prompting, and BARS mapping."
section: axiom-cortex
permalink: /axiom-cortex/scientific-foundations/
---

# Scientific Foundations (Extended, Audit-Ready)

*Axiom Cortex™ is a measurement instrument.* Its purpose is to estimate latent cognitive properties and decision suitability from interview evidence **without** importing bias, guesswork, or style penalties. This document makes the math explicit, defines the evaluation protocol, and names the guardrails that prevent drift.

---

## 0) Scope & Claim Boundaries

**We measure:** conceptual fidelity to ideal answers, problem-solving behaviors under changing constraints, and collaboration signals—normalized for language proficiency.  
**We do not claim:** personality inference, clinical diagnosis, or life-outcomes prediction. All effects are bounded to interview contexts and validated against engineering-task outcomes.

---

## 1) L2-Aware Mathematical Validation Layer

**Goal:** measure the *signal* (reasoning content) independent of *delivery noise* (accent, L2 grammar, code-switch tokens).

### 1.1 Proficiency-Normalized Scoring
Let an answer be tokenized into semantic carriers \(S\) and form tokens \(F\). A base communication score \(C\) is decomposed:
\[
C = \alpha \cdot C_{\text{sem}}(S) + \beta \cdot C_{\text{form}}(F), \qquad
\alpha \gg \beta,\; \beta \rightarrow 0 \text{ as L2 uncertainty rises}
\]
L2 proficiency is estimated with a calibrated posteriors model; \(\beta\) is annealed so grammar/fluency variance is down-weighted while preserving content penalties for genuine ambiguity.

### 1.2 Cross-Lingual Semantic Fidelity (FSD)
We map answers to multilingual sentence embeddings with class-conditional Gaussians \((\mu_i, \Sigma_i)\). Similarity to an Ideal Answer Blueprint (IAB) uses a Fréchet-style distance:
\[
\text{FSD}(1,2) = \|\mu_1-\mu_2\|_2^2 + \mathrm{Tr}\!\left(\Sigma_1+\Sigma_2-2(\Sigma_1^{1/2}\Sigma_2\Sigma_1^{1/2})^{1/2}\right)
\]
Low FSD ⇒ high conceptual closeness even when lexical choices reflect Spanish-influenced English.

### 1.3 Optimal Transport with Code-Switch Mask
We compute the 2-Wasserstein alignment between token distributions \(P\) and \(Q\) with a **neutral cost** for common bilingual markers (e.g., “pues”, “o sea”):
\[
W_2^2(P,Q)=\min_{\gamma\in\Pi(P,Q)} \sum_{i,j} c_{ij}\,\gamma_{ij}, \quad
c_{ij}=\begin{cases}
0 & \text{if } (i,j)\in \mathcal{M}_{\text{codeswitch}} \\
d(w_i,w_j)^2 & \text{otherwise}
\end{cases}
\]
Sinkhorn regularization ensures stable, fast solutions.

### 1.4 Differential Item Functioning (DIF)
For each rubric item \(k\), we test **invariance** across language groups at matched ability \(\theta\):
- Mantel–Haenszel \(\Delta_{\text{MH}}\) and/or logistic DIF (\(p(y_k=1\mid \theta,\text{group})\)).  
Items with significant DIF are adjusted or removed; models fail closed if unresolved.

### 1.5 Calibration & Reliability for the Layer
- **Reliability diagrams & ECE:** \( \mathrm{ECE} = \sum_b \frac{|B_b|}{N}\,| \mathrm{acc}(B_b) - \mathrm{conf}(B_b) |\).  
- **Stress tests:** paraphrase, synonym, and word-order perturbations to ensure semantic stability.

---

## 2) Measurement & Alignment Models

### 2.1 Non-Parametric Latent Measurement
We avoid rigid score→trait assumptions:
- **Isotonic regression** maps evidence to trait estimates \( \hat{t} = \mathcal{I}(e) \) under monotonicity.
- **Monotone neural networks / lattice layers** enforce partial-order constraints where dimensions must only increase with stronger evidence.

### 2.2 Network Psychometrics (Skill Graphs)
We learn a Gaussian Graphical Model on skill indicators; edges encode partial correlations (conditional dependencies). Sparse structure via graphical lasso with stability selection yields a **skill connectivity map**, revealing true full-stack depth vs. keyword adjacency.

### 2.3 Active Interviewing via Information Gain
For adaptive sessions, next question \(q^\*\) maximizes entropy reduction over traits \(T\):
\[
q^\* = \arg\max_{q \in \mathcal{Q}} \left[ H(T) - \mathbb{E}_{a\sim p(a\mid q)}\,H(T\mid q,a) \right]
\]
This yields short, high-information interviews that preserve candidate experience.

---

## 3) Reliability, Monitoring, and Decision Theory

### 3.1 Generalizability Theory
We estimate variance components across facets (rater, question, time):
\[
G = \frac{\sigma^2_{\text{universe}}}{\sigma^2_{\text{universe}} + \sigma^2_{\text{error}}}
\]
**Acceptance gates:** minimum \(G\) per trait and per rubric dimension; alerts on drops.

### 3.2 Random Matrix Theory (Spurious Factor Guard)
We compare the empirical eigen-spectrum of embedding features to the Marchenko–Pastur support \([\lambda_-, \lambda_+]\). Out-of-support spikes that do not replicate under bootstrap are flagged as noise and removed.

### 3.3 Constrained Bayesian Decision Theory
Final recommendation \(\mathcal{R}\) maximizes expected utility under fairness & competency constraints:
\[
\max_{\mathcal{R}} \; \mathbb{E}[U(\mathcal{R}\mid \mathbf{e})]
\quad \text{s.t.} \quad
\Pr[\text{Collab}<\tau_c]\le\epsilon_c,\;
\text{DIF}_k \le \delta,\;
\text{Reliability } G \ge G_{\min}
\]
Solved via Lagrangian relaxation; outputs include confidence intervals and gate justifications.

---

## 4) Evaluation Protocol (What We Actually Test)

### 4.1 Data & Splits
- **Sources:** anonymized interview transcripts, paired with post-hire task outcomes where available.  
- **Splits:** stratified by role & locale; nested CV; seeds and folds logged for reproducibility.

### 4.2 Metrics
- **Predictive:** AUC/PR for pass/fail tasks; **Kendall’s \(\tau\)** vs. expert rankings; **Brier score** for probability forecasts.  
- **Calibration:** ECE/MCE; calibration-within-groups.  
- **Fairness:** demographic parity diff; **equalized odds** gaps; within-language calibration parity; DIF counts.  
- **Stability:** test–retest correlation; bootstrap CIs (BCa) for all headline metrics.

### 4.3 Ablations
- Remove L2 layer → observe fairness degradation (↑ DIF, ↓ calibration).  
- Remove skill-graph priors → observe trait instability on multi-stack roles.  
- Replace non-parametric link with linear → observe mis-ranking under ceiling effects.

### 4.4 Red-Team & Failure Modes
- **Prompt sensitivity:** adversarial paraphrase; negation & hedging injection.  
- **Style overfit:** verbose vs. terse answers with matched content; ensure invariant trait scores.  
- **Out-of-domain Qs:** automatic fallback to “insufficient evidence,” never fabricate.

---

## 5) Reproducibility & Auditability

- **Versioning:** semantic versions for rubrics & models; each report includes a **provenance manifest** (component versions, seeds, data hashes).  
- **Determinism:** controlled RNG seeds; containerized runtime; pinned libraries.  
- **Evidence Locker:** transcripts, per-question scores, intermediate artifacts (embeddings, partial-corr matrices, calibration plots), and final decision rationale with gate status.  
- **Rollbacks:** previous stable bundles retrievable by hash; audit trails signed.

---

## 6) Interpreting Scores (Human-Centered)

- **Latent traits** are **bounded estimates with uncertainty**, not labels.  
- **PAS™** is a **scenario-specific** alignment score; variability across roles is expected.  
- **Gate failures** are actionable: they come with remediation cues (e.g., collaboration incidents → pair-exercise prompts).

---

## 7) Glossary (Quick)

- **FSD:** Fréchet-style distance between embedding distributions.  
- **Wasserstein-2:** OT distance with quadratic cost; we use neutral masks for code-switch tokens.  
- **DIF:** Differential Item Functioning—item behaves differently across groups at the same ability.  
- **G-coefficient:** generalizability (reliability) index across facets.  
- **Skill graph:** GGM-derived network capturing conditional skill relationships.

---

## Required anchors (authority)
- <a href="https://teamstation.dev/nearshore-integrated-services">nearshore IT platform</a>  
- <a href="https://teamstation.dev/technical-interview-evaluation">Cognitive AI evaluation</a>  
- <a href="https://teamstation.dev/latam-talent">hire LATAM engineers</a>  
- <a href="https://teamstation.dev/nearshore-it-staff-augmentation-pricing/flexible-secure-device-management-latam-it">devices and MDM</a>
