# Behavioral Design Skill — Validation Summary

**Skill version:** v1.2
**Date:** 2026-04-16
**Cases evaluated:** 9
**Method:** Convergent validation against 9 published behavioral design cases. Solver produced structured output across all 8 skill stages for each case. Independent evaluator scored against published ground truth on 6 dimensions (routing, diagnosis, design, actionability, backfire awareness, process coherence).

---

## Score table

| Case | Route | Diag | Design | Act | Backfire | Process | Total |
|---|---|---|---|---|---|---|---|
| 01 RecoveryOne | 3 | 3 | 3 | 4 | 4 | 3 | 20/30 |
| 02 Marvin | 3 | 4 | 4 | 4 | 4 | 4 | 23/30 |
| 03 AdmitHub | 4 | 2 | 3 | 4 | 4 | 4 | 21/30 |
| 04 Steady | 4 | 5 | 4 | 4 | 4 | 5 | 26/30 |
| 05 Credit Karma | 4 | 4 | 3 | 4 | 3 | 4 | 22/30 |
| 06 EarnUp | 3 | 2 | 2 | 3 | 3 | 3 | 16/30 |
| 07 Mumbai | 3 | 2 | 3 | 3 | 3 | 3 | 17/30 |
| 08 Truancy | 4 | 3 | 4 | 4 | 4 | 4 | 23/30 |
| 09 Cafeteria | 4 | 4 | 4 | 4 | 4 | 5 | 25/30 |
| **Average** | **3.6** | **3.2** | **3.3** | **3.8** | **3.7** | **3.9** | **21.4/30** |

---

## Patterns across cases

### Consistently strong (dimensions scoring 4+ on most cases)

- **Practical Actionability** (avg 3.8, scored 4 in 7/9 cases): The skill reliably produces full implementation plans with sample size considerations, timeline sketches, constraint-respecting design, and non-behavioral prerequisite checks. Notable: Bayesian A/B correctly recommended at N=200 (Case 02); annual behavior constraint correctly handled with a learning-maximizing 3-arm design (Case 03); cluster randomization with ICC calculation at TEST (Case 09). This is the skill's most consistent strength.

- **Backfire Awareness** (avg 3.7, scored 4 in 6/9 cases): Case-specific risks are reliably identified — social norm boomerang conditions, employer-as-messenger reactance, sludge vs. beneficial friction classification, equity checks, autonomy concerns. The OPTIMIZE stage is functional and consistent. The skill scored 4 on backfire in all three digital-product cases (02, 04, 05) and in both communication cases (03, 08). The notable pattern: the skill labels friction as "opportunity" but does not always then ask the ethical mirror question (Cases 05, 06, 07 miss exploitative timing or risk compensation).

- **Process Coherence** (avg 3.9, scored 4 or 5 in 7/9 cases): Stages connect in sequence and outputs flow through the chain. Outstanding: Case 04 and Case 09 both scored 5, with proactive cross-stage linking (re-engagement vs. top-of-funnel baseline in Case 04; two-behavior structure maintained through all 8 stages in Case 09). Process edge cases — small-N Bayesian routing, annual behavior cycles, two-layer behavior structures — are recognized and handled when they appear.

### Consistently weak (dimensions scoring 3 or below on multiple cases)

- **Diagnostic Depth** (avg 3.2, scored 2 in 3/9 cases): The most variable and most important dimension. The skill produces competent barrier inventories but fails to identify the specific upstream insight the published team found in several cases. Pattern: when diagnostic behavioral data is available (Case 06), the skill defaults to theorizing barriers rather than asking "what does the data show?" When the primary barrier is a perceptual or psychological mechanism outside the common framework categories (Case 07), the skill dismisses the correct category. When the published insight is a framing-level observation about the communication itself (Case 03), the skill diagnoses the downstream practical obstacles instead.

- **Routing Correctness** (avg 3.6, scored 3 in 4/9 cases): The framework selection is often correct but the justification is thin or template-driven. Cases 01 and 02 used identical boilerplate routing rationales — the routing module is stamping rather than reasoning in digital-product cases. Case 06 inverted the 3B/COM-B hierarchy (applied in-product heuristic mechanically when the Reflective Motivation layer was primary). Case 07 routed correctly but without trade-offs named.

- **Design Quality** (avg 3.3, scored 2 in 1 case, 3 in 4 cases): The skill designs specific, well-structured interventions, but often reaches for a different mechanism than the published team selected. Recurring pattern: the solver's design is correct *for its own diagnosis* but misaligned with the published finding because the diagnosis was slightly off. In Case 03, the solver built a technically competent 5-message scaffolding sequence where the published team found a single reframed message works; in Case 06, the solver used loss framing where the published team used gain framing ("earn money"); in Case 01, a passive landing-page redesign replaced an interactive quiz that demonstrated the product.

---

### Things the skill consistently missed that ground truth found

- **Data-first diagnosis (Route A):** When existing behavioral data is available — payment history showing round-number clustering (Case 06), re-engagement cohort analytics (Case 04) — the skill does not reliably redirect to data examination before theorizing. Case 06 is the clearest failure; Case 04 partially recovered this through structural evidence (the "Maybe Later" screen), but the data-first step was not explicitly performed.

- **Zeigarnik / incompleteness framing as a named design technique** (Cases 04): The open-loop / incomplete-task salience mechanism was the published team's second intervention component in Case 04 but was not in the solver's design tables.

- **Gain framing vs. loss framing distinction** (Case 06): The published finding that "earn money" framing outperformed "save money" framing — significant enough to drive the company rebrand to EarnUp — was not only missed but inverted; the skill proposed loss framing with confidence.

- **Exploitative timing risk as an explicit OPTIMIZE checkpoint** (Cases 05, 07): When friction is classified as "opportunity," the skill reliably applies the positive framing but does not always then flag the ethical mirror — that intervening at a moment of frustration or negative affect can cross into manipulation (Case 05), or that increasing salience can cause risk compensation (Case 07).

- **Miscalibrated beliefs as a distinct barrier category** (Cases 07, 08): In Case 08, parents' underestimation of their child's cumulative absence count and overestimation of peer absence rates were absent from the barrier list despite being the mechanism behind specific design elements. In Case 07, the perceptual miscalibration of train speed was explicitly dismissed as "not a meaningful barrier."

- **Cross-chain bridge invocation** (Case 01): The explicit 3B → Michie Reflective Motivation → Persuasion → Framing/Credible Source mapping is a process-level checkpoint the solver arrived at through general practice rather than the framework's explicit chain mechanism.

- **Framing direction calls from prior evidence** (Case 08): The published finding that negative framing outperforms positive in education-loss contexts is not surfaced; the solver chose partnership-neutral framing without naming or testing the alternative.

- **Within-year waning and booster timing** (Case 08): Effect decay within a school year is not flagged at OPTIMIZE, only at SCALE.

---

### Things the skill consistently added that ground truth did not find

**Value-add:**
- Sub-barrier decomposition within primary categories (efficacy skepticism, identity conflict sub-types) — Cases 01, 02. Practically useful for copywriting and targeting.
- Qualitative workstreams alongside quantitative tests (non-enroller interviews in Case 02) — addresses Route B data gaps proactively.
- Non-behavioral prerequisite checks (unbanked population filter in Case 04; bridge steepness in Case 07; taste/palatability in Case 09) — mature diagnostic judgment.
- "Fresh Start Effect" for timing campaigns (Case 06), REPLACE vs. START distinction with behavioral implications (Case 05), behavioral archetype segmentation (Case 07) — useful practitioner additions.
- Social norm tipping-point deployment strategy (deploy only once the true majority claim is factually supported) — Cases 07, 09.
- Cluster randomization with ICC and design-effect calculation (Case 09) — methodological value-add not required by ground truth but genuinely useful.
- Middle vs. elementary school differentiation for reactance risk (Case 09) — practical implementation guidance not in the ground truth.
- Revenue monitoring as a stopping condition (Case 09) — addresses a real institutional concern.

**Noise:**
- Elevated prioritization of secondary barriers to co-equal status with primary (Cognitive Overload elevated to match Mental Models in Case 01) — dilutes diagnostic focus without adding design value.
- Complex multi-arm experimental designs for cases where the published intervention was a simple framing reframe (Case 06) — the solver's 4-arm loss-framing email campaign is internally coherent but builds complexity around the wrong problem.

---

## Case-by-case highlights

- **Case 01 RecoveryOne:** Correctly diagnosed both ground truth barriers but reached for a passive landing-page redesign where the published team used an interactive quiz that *demonstrated* the product — a mechanistically weaker approach for category-mismatch specifically; the "Maybe Later" → explicit opt-out redesign is an independently derived value-add.
- **Case 02 Marvin:** Strongest overall run; primary barrier precisely identified, small-N Bayesian method correctly chosen, most ground truth components present; the one substantive miss — leading with emotional benefits ("be human") vs. the solver's "preventive performance" rational frame — is a coherent alternative, not an error.
- **Case 03 AdmitHub:** Clean diagnostic miss: the solver correctly identified that awareness is not the binding constraint but then diagnosed downstream practical obstacles (documents, FSA ID, form navigation) rather than the upstream framing insight (the existing reminder implies FAFSA is optional, creating an unnecessary decision point); best routing of Batch 1.
- **Case 04 Steady:** Calibration anchor case; strong diagnostic and process performance; the single gap — Zeigarnik/incompleteness framing as the published second intervention component — drops Design to 4; Process Coherence is the standout at 5/5 with proactive cross-stage linking.
- **Case 05 Credit Karma:** Correctly surfaces "friction as opportunity" and designs the timely trigger correctly; misses option-ordering as a design variable (the specific published finding) and the exploitative-timing risk as the ethical check on that same element.
- **Case 06 EarnUp:** Lowest-scoring case; a single process error (Route B instead of Route A) cascades through the entire run — the rounding pattern, Round Up framing, and gain reframe are all absent; internally coherent output that answers a different question than the case was asking.
- **Case 07 Mumbai:** Correct framework; the primary barrier (perceptual miscalibration of train speed as a System 1 error) is explicitly dismissed as "not a meaningful barrier," foreclosing the correct diagnosis; the resulting design is System 1 and environment-based — directionally right — but targets habit interruption rather than speed-perception recalibration.
- **Case 08 Truancy:** Best non-digital communication case; routing, process, and actionability all strong; gaps are diagnostic (miscalibrated beliefs not in the barrier list) and evidentiary (framing direction call not made despite published evidence).
- **Case 09 Cafeteria:** Highest-scoring run overall (25/30); the two-behavior structure (selection ≠ consumption) is the critical edge case and the solver handles it correctly at every stage; cluster randomization with ICC is correctly identified; only gaps are a missing convenience element and placement of the selection-without-consumption concern in ANALYZE rather than OPTIMIZE.

---

## Recommendations for the skill author

Based on patterns observed across all 9 cases, the following changes are recommended for v1.3:

1. **Add a mandatory Route A gate at Evidence Check.** Cases 06 and 04 show the skill does not reliably redirect to data examination when behavioral data is described as available. Route A should require a specific named step: "Before theorizing barriers, what does the existing behavioral data show? Are there patterns in the data (clustering, timing, segmentation) that reveal the intervention directly?" A decision rule for triggering Route A — explicit if user provides usage data, payment history, funnel analytics, A/B results, or observational records — would prevent the Case 06 failure class.

2. **Add an explicit OPTIMIZE checkpoint for exploitative timing / risk compensation.** The skill reliably identifies friction as "opportunity" but does not have a named checkpoint for the ethical reverse question. After classifying friction as "opportunity," the skill should ask: "Does this intervention surface at a moment of negative affect, frustration, or vulnerability? Could it be experienced as coercive or manipulative?" Add risk compensation specifically for visibility interventions in physical environments ("Does increased salience create overconfidence?"). This would address Cases 05, 06, and 07.

3. **Strengthen the routing justification module for digital-product cases.** Cases 01 and 02 produced identical boilerplate routing rationales ("digital product with enrollment funnel; target behavior occurs inside the product"). The routing module needs to generate case-specific justifications: which specific features of *this* behavior map to *this* framework's diagnostic categories, and what is the closest alternative that was considered and set aside. A template that requires filling in at least one case-specific feature and naming one alternative would prevent the stamp-and-proceed pattern.

4. **Add Zeigarnik / incompleteness framing to the design table and ensure miscalibrated beliefs is a distinct diagnostic category.** Zeigarnik was the second intervention component in Case 04 (a calibration case) and was absent. Miscalibrated beliefs — systematic errors in factual beliefs about one's own behavior (Case 08: parents underestimating absence count) or others' behavior (erroneous descriptive norms) — is a distinct barrier category from Reflective Motivation generally and should appear as a named option in the DIAGNOSE framework, with specific design techniques linked to it (e.g., personalized feedback, descriptive norm correction, social comparison).

5. **Add a framing-direction decision checkpoint at DESIGN for communication cases.** Cases 02, 03, 06, and 08 all involved messaging framing choices where the skill made a confident direction call without referencing prior evidence or flagging the alternative. The skill should prompt: "Is there prior evidence on loss vs. gain framing for this population and behavior type? If yes, default to the evidence; if no, test both as a dimension." This would have caught the Case 06 loss-framing inversion and the Case 08 neutral-vs.-negative framing question.

---

## Honest caveats

- **Validation tests the skill's diagnostic and design output given full case context.** It does not test the skill's dialogue behavior (clarifying questions, handling of incomplete or ambiguous user input). Dialogue quality requires separate practitioner testing.
- **Evaluator is Claude Sonnet 4.6 calibrated against published ground truth using worked examples on Case 04 Steady.** Scores are more reliable relative to each other than in absolute terms.
- **Cases are from the published behavioral science literature.** The solver may have seen some of them during training; the validation tests whether the skill's process leads to the published answer, not whether the solver can recall it.
- **The 9 cases oversample digital-product and communication intervention types.** Physical-environment cases (07 Mumbai, 09 Cafeteria) and data-first cases (06 EarnUp) are underrepresented. Skill performance in these categories should be treated as indicative, not definitive, until more cases are added.

---

## Overall assessment

The skill is operating in the Good–Excellent range across most cases (average 21.4/30), with clear strengths in practical actionability, backfire awareness, and process coherence — the dimensions most valuable to a practitioner who needs to execute. The diagnostic depth dimension is the most variable and the most consequential: when the primary barrier is a specific upstream insight (a framing property, a perceptual mechanism, or a pattern in existing data), the skill sometimes defaults to a comprehensive but generic barrier inventory rather than finding the specific finding. Two systematic gaps are identifiable and fixable: the Evidence Check stage does not function as a true Route A/B discriminator, and the OPTIMIZE stage lacks named checkpoints for exploitative timing and risk compensation. The skill is ready for public beta with the 5 targeted changes above, with the honest caveat that practitioners should expect the strongest performance on digital-product funnel cases with clear barrier evidence, and should apply more scrutiny when the input includes existing behavioral data or involves physical-environment perceptual mechanisms.
