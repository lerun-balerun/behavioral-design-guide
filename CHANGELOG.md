# Changelog & Roadmap

**Current version:** v1.3 (April 17, 2026)
**License:** CC BY-NC-SA 4.0

---

## DONE in v1.2 (applied April 16, 2026)

| ID | Fix | Source |
|---|---|---|
| C1a | Table C: added Status Quo / Costless deferral → Forced active choice row | Steady walkthrough |
| C1b | Table D: added Required Active Choice to Easy techniques | Steady walkthrough |
| C2 | OPTIMIZE friction classification: each type now has a concrete example | Steady walkthrough |
| C3 | Stage 3 DIAGNOSE: tiebreaker guidance for Route B/D (hypothesis-heavy diagnosis) | Steady walkthrough |
| M1 | OPTIMIZE social norm: "8 boundary conditions" now inline with the actual 8 | Earlier analysis |
| M2 | Stage 3 DIAGNOSE: framework conflict rule rewritten to cover digital-health two-layer case | Earlier analysis |
| M3 | Intro ("How to Use This Skill"): rewritten to coach-skill style | Earlier analysis |
| CS1 | Added Communication Style block after Hard Rules — tone, structure, avoid-list, length guidance | Style review |
| CS2 | Intro tightened again: "Open every new conversation with this message" | Style review |
| V | Version bumped v1.1 → v1.2 | — |

---

## DONE in v1.3 (applied April 16, 2026, after validation)

### Validation-based fixes

| ID | Fix | Source | What it fixes |
|---|---|---|---|
| V1 | **Route A forcing function in EVIDENCE CHECK.** Mandatory 3-part output (primary pattern, intervention implication, data gap) + mandatory first line in DIAGNOSE: "Primary finding from data: [pattern]." | Validation: EarnUp 16→22 | Solver acknowledges data then drops it for framework-theorized barriers |
| V2 | **Ethical mirror checkpoint in OPTIMIZE.** If friction classified as Opportunity → flag exploitative timing risk. | Validation: Credit Karma, Mumbai | Skill labels friction as "opportunity" but doesn't flag ethical reverse |
| V3 | **Risk compensation checkpoint in OPTIMIZE.** For salience/visibility interventions: does increased salience create overconfidence? | Validation: Mumbai | Missing risk compensation for physical-environment interventions |
| V4 | **Miscalibrated Beliefs — new diagnostic category in DIAGNOSE + Table C.** Three sub-types: self-underestimation, descriptive norm error, perceptual miscalibration. | Validation: Truancy, Mumbai | Solver dismissed perceptual miscalibration; missed cumulative absence underestimation |
| V5 | **Zeigarnik / incompleteness framing added to Table C.** Status Quo → Incompleteness / open loop → Zeigarnik framing. | Validation: Steady | Missing secondary intervention component |
| V6 | **Motivational complexity check in framework conflict rule.** Presents both 3B and COM-B with honest trade-offs when behavior involves tradeoffs, value framing, or habitual patterns. | Validation: EarnUp routing 3/5 | Auto-routing to 3B for digital product when COM-B was better fit |

### Framework audit fixes

| ID | Fix | Source |
|---|---|---|
| F1 | **COM-B diagnostic prompts in DIAGNOSE.** Six components with 2-3 questions each. Previously only 3B had prompt questions. | Framework audit against published COM-B source |
| F2 | **EAST cross-check expanded in DESIGN.** Each letter explained with concrete techniques (E = defaults + friction + simplify; A = novelty + incentives; S = norms + networks + commitment; T = receptiveness + planning). | Framework audit against published EAST source |
| F3 | **SDT motivation continuum added in OPTIMIZE.** Six stages from amotivation to intrinsic. Design check: does the intervention move user toward or away from self-determined motivation? | Framework audit against published SDT source |
| F4 | **Framework Quick Reference rewritten.** Prose format with Strength + Limitation for each framework. CREATE steps explained. SIDE deliverables listed. | Framework audit |

### Licensing fix

| ID | Fix | Source |
|---|---|---|
| L1 | **Table D (15 strategy categories) removed.** Taxonomy was derivative of MAKE IT Toolkit, licensed CC BY-NC-ND (incompatible with skill's CC BY-NC-SA). Replaced by **Design Direction Bridges** — same barrier→technique mappings using published-literature terminology. DESIGN routing updated to Table C + EAST + APEASE (3B path), Table A + B + EAST + APEASE (COM-B path). | License audit |

---

## DONE in v1.3 publication prep (April 17, 2026)

| ID | Fix | Source |
|---|---|---|
| CS3 | **Communication Style revised.** Added: epistemic honesty rules (show uncertainty, distinguish data from inference, think through tradeoffs visibly). Bold/heading rules for diagnostic stages (bold category name only, no priority labels or parenthetical tags). Anti-report framing (address user directly, not report-style). Parenthetical skill-internal references banned. Stage transition openers (one warm sentence at start of each stage: what we'll do, what you'll get). | Style review against validation runs |
| F5 | **Quick Reference cleanup.** IL 3-Phase removed (provenance moved to 3B entry). PRIME removed (mechanisms covered by COM-B + SDT; not used in any stage). MINDSPACE expanded with full Strength + Limitation + role in skill. BCW IF+BCTs expanded with full Strength + Limitation + role in skill. | Scope review |

---

## SHOULD — defer to v1.4, prioritize based on practitioner feedback

**Source:** Validation summary recommendations + original SHOULD list items that remain relevant after v1.3.

| ID | Fix | Source | Priority | Notes |
|---|---|---|---|---|
| S-new2 | **Framing direction checkpoint at DESIGN for communication cases.** Prompt: "Is there prior evidence on loss vs. gain framing for this population and behavior type? If yes, default to evidence; if no, test both." | Validation: Cases 06, 08 | HIGH | Caused the single biggest remaining miss (EarnUp gain framing). Listed in README Known Limitations. |
| S4 | **Progressive Disclosure / Timing Redesign as dedicated DESIGN option.** | Steady walkthrough | HIGH | Came up naturally, probably recurring |
| S-new1 | **Strengthen routing justification for digital-product cases.** Cases 01 and 02 produced identical boilerplate routing rationales. | Validation: Cases 01, 02 | MEDIUM | Real pattern but not blocking |
| S-new3 | **Guardrail metrics as required OPTIMIZE output.** After backfire check, require: "Guardrail metrics: [list with thresholds]." | Validation: Cases 06, 07 | MEDIUM | Turns advice into protection |
| S-new5 | **Implementer behavior layer at SCALE for Type 2 interventions.** When SCALE = Type 2, prompt: run brief COM-B pass on implementer population's adoption barriers. | Validation: Case 07 | MEDIUM | Matters for capital-intensive deployments |
| S6 | **SCALE decision gate — pre-rollout 5-point checklist.** | Steady walkthrough | MEDIUM | Stage 7 is thin, would materially improve |
| S7 | **Equity re-verification at SCALE.** | Steady walkthrough | MEDIUM | Matters for equity-sensitive deployments |
| S9 | **Baseline for re-engagement experiments ≠ top-of-funnel baseline (Stage 5).** | Steady walkthrough | MEDIUM | Specific gotcha, practical value |
| S10 | **Stage 6 decision tree should integrate guardrail metrics, not just primary.** | Steady walkthrough | MEDIUM | Real analyst failure mode |
| S-new4 | **Secondary intervention channel completeness check at DESIGN.** Prompt: "Are there additional sensory or framing channels that could reinforce the primary mechanism?" | Validation: Cases 06, 07 | LOW | Nice to have, unclear if real practitioner need |
| S3 | **Sample size table: strengthen caveat for baseline conversion and effect size.** | Earlier analysis | LOW | Partially covered by existing low baseline caveat in TEST. Consider closing. |

**Workflow for v1.4:** Park this list. After 2-4 weeks of community feedback post-publication, re-prioritize based on what practitioners actually hit. Top candidates for v1.4: S-new2 (framing direction), S4 (progressive disclosure), S-new3 (guardrail metrics).

**Previously SHOULD, now DONE or superseded:**

| ID | Status | Reason |
|---|---|---|
| S1 | Partially addressed | Cross-chain bridge described; illustration deferred to v2 |
| S2 | Superseded by V1 | Route A forcing function is stronger than "push back on hypothesis-only" |
| S5 | Superseded by F4 | APEASE tone/emphasis improved in Quick Reference rewrite |
| S8 | Superseded by V5 | Non-behavioral prerequisite revisit at SCALE addressed by Zeigarnik and stronger OPTIMIZE |

---

## COULD — v2 (product-level additions, not single fixes)

| Item | Notes |
|---|---|
| Motivational Interviewing integration | Most-requested gap in Honest Gaps |
| Gamification depth | MAKE IT Toolkit licensing blocked integration; consider original taxonomy or partnership |
| Messaging audit mini-tool | Standalone module for communication interventions |
| Data pattern discovery prompts | Help practitioner find behavioral signals in existing analytics |
| Framing direction guidance (systematic) | Beyond the v1.4 checkpoint — a full decision tree for when loss vs. gain frame works |
| More diverse Mental Models examples | Beyond health contexts — fintech, education, workplace |
| Explicit dark-pattern guardrail in DESIGN | Pre-OPTIMIZE check, not just post-design |
| Domain-knowledge flag | Skill should tell user "I do process, you bring context" |
| Framework profiles (detailed) | Full standalone description of each framework with worked examples |
| Blind practitioner validation | Different question from convergent validation — "does it work for new practitioners?" |

---

**Last updated:** April 17, 2026, publication prep session.
