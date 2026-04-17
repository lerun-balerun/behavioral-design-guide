# Behavioral Design Skill — Evaluation Rubric

Six dimensions, each scored 1-5. Total per case: up to 30. Use the anchors below to prevent score drift across cases.

---

## How to score

For each dimension, pick the score whose anchor best describes the solver's output for this case. If the output is between two anchors, use the lower score unless there is a clear reason to give the higher one. **Err on the strict side** — a skill that scores 30/30 on every case tells us nothing about where it actually struggles.

When scoring, compare the solver's output to the ground truth. Things to note separately:
- What the solver got right that matches ground truth
- What the solver missed that ground truth found
- What the solver added that ground truth did not find (may be genuine value-add; note it)

**Calibration anchor: Case 04 Steady.** At the bottom of each dimension, a short "worked example" shows what a 3-score vs. a 4-score looks like *on the Steady case*. Use this as your reference point when scoring the other eight cases. If Case 04 itself comes up for scoring, use the anchors directly — the worked example is the calibration baseline, not a circular template.

---

## Dimension 1: Routing Correctness

Did the skill recommend the right diagnostic framework for this context and justify the choice?

| Score | Anchor |
|---|---|
| 1 | Wrong framework — e.g., uses 3B for a non-digital public safety case, or COM-B for a simple digital product funnel. No useful justification. |
| 2 | Partial routing — names a framework but reasoning is weak or missing. Does not match ground truth. |
| 3 | Right framework, weak justification. The skill landed on the correct path but the "why" is thin. No trade-offs noted. |
| 4 | Right framework with clear justification. Mentions at least one trade-off or alternative considered. |
| 5 | Right framework with clear justification, alternatives considered, and explicit trade-offs. Handles edge cases (two-layer, hybrid COM-B + 3B supplement) correctly if applicable. |

**Worked example (Steady):**
- **Score 3 looks like:** "Routing to 3B." No justification given, or justification restricted to "this is a digital product."
- **Score 4 looks like:** "Routing to 3B because the target behavior (bank linking) occurs inside the product, there's funnel drop-off data, and 3B's Attention/Cognitive Overload/Status Quo/Mental Models categories map cleanly onto the re-engagement moment. COM-B would also work but is heavier than needed for a single-screen choice architecture problem."

---

## Dimension 2: Diagnostic Depth

Did the skill identify the barriers that the published team found — and nothing significant they missed?

| Score | Anchor |
|---|---|
| 1 | Missed the primary barrier entirely. Generic "users lack motivation" or "users don't know about it" output. |
| 2 | Identified primary barrier but missed key secondary barriers. Or identified many barriers without prioritizing. |
| 3 | Identified primary + some secondary barriers matching ground truth. Prioritization weak or generic. |
| 4 | Identified primary + all major secondary barriers from ground truth. Prioritization reasoning sound. |
| 5 | Identified primary + secondary barriers matching ground truth, with correct prioritization, *plus* surfaced at least one genuine diagnostic insight the ground truth also found (e.g., bottom-up vs. top-down attention, mental model category mismatch, risk compensation, friction-as-opportunity). |

**Worked example (Steady):**
- **Score 3 looks like:** Identifies "users don't want to link their bank" or "friction in bank-linking" as the barrier. Talks about privacy concerns or Plaid distrust. Misses that the **choice architecture of the screen itself** — specifically "Maybe Later" as costless deferral — is the bottleneck, not bank-linking in general.
- **Score 4 looks like:** Identifies **Status Quo bias / costless "Maybe Later" deferral** as primary, with specific reference to the current screen design. Adds decision avoidance / procrastination (future/abstract benefit) as secondary. Prioritization explains why Status Quo beats other candidates for this cohort.

---

## Dimension 3: Design Quality

Did the skill design interventions with specific techniques, mechanisms, and a testable hypothesis — not generic advice?

| Score | Anchor |
|---|---|
| 1 | Generic advice ("make it easier," "add social proof," "use defaults") without specific technique or mechanism. |
| 2 | Names techniques but mechanisms are vague. No clear testable hypothesis. |
| 3 | Specific techniques matched to diagnosed barriers. Mechanism mentioned but could be sharper. Hypothesis present but imprecise. |
| 4 | Specific techniques + clear mechanism for each. Testable hypothesis in "If...then...because..." form. Technique choice defensible from Table C/D/A. |
| 5 | Specific techniques + clear mechanism + testable hypothesis *and* the intervention matches (or is a reasonable equivalent of) what the ground truth designed. APEASE filter applied and visibly used to rule in/out candidates. |

*Note for Case 7 (Mumbai):* The specific yellow-stripe solution is a creative leap beyond framework tables. Score on whether the skill identified the **need** (System 1 perceptual intervention, bottom-up salience, non-text), not whether it invented stripes.

**Worked example (Steady):**
- **Score 3 looks like:** Proposes "reduce friction" or "improve the benefits messaging" or "add social proof." Technique not specifically matched to Status Quo bias. Hypothesis present but generic.
- **Score 4 looks like:** Proposes **Forced Active Choice** (replace "Continue / Maybe Later" with "Accept / Decline") as primary, with explicit mechanism: "removing costless deferral forces an explicit decision." Hypothesis: "If we replace Maybe Later with Decline for the re-engagement cohort, then bank-link completion will increase, because costless deferral is removed and the open loop remains salient." APEASE applied (Decline passes Acceptability because choice is preserved).

---

## Dimension 4: Practical Actionability

Could a real practitioner at this organization actually execute this tomorrow?

| Score | Anchor |
|---|---|
| 1 | Theoretical — no concrete steps. Practitioner cannot act on this. |
| 2 | Some concrete steps but major gaps. Implementation plan missing key pieces (who does what, on what system, with what timeline). |
| 3 | Concrete steps for primary intervention. Implementation plan exists but gaps remain (handling of edge cases, team capacity, constraints). |
| 4 | Full implementation plan a practitioner could hand to their team. Respects stated constraints (team size, budget, data availability). |
| 5 | Full implementation plan, respects all stated constraints, sequenced by priority, with specific ownership and first-week actions. Handles the real-world messiness mentioned in the case context. |

**Worked example (Steady):**
- **Score 3 looks like:** "Run an A/B test with the re-engagement cohort. Show the new screen. Measure bank-link completion." No arms specified, no sample-size check against 15k cohort, no ownership.
- **Score 4 looks like:** Concrete 3-arm test specification: control (current screen) / FAC alone / FAC + incompleteness framing. Sample size check against 15k cohort. Uses in-app pop-up channel already mentioned. Ownership by PM + designer + analyst (the team composition given in the case). Timeline sketched.

---

## Dimension 5: Backfire Awareness

Did the skill identify the specific backfire risks for this case — not generic warnings?

| Score | Anchor |
|---|---|
| 1 | No backfire check, or a generic "this might not work" statement. |
| 2 | Mentions backfire risks but they are generic and not specific to this case. |
| 3 | At least one case-specific backfire risk flagged (e.g., risk compensation for visibility interventions; exploitative timing for friction-as-opportunity; social norm boomerang if true prevalence is low). |
| 4 | Multiple case-specific backfire risks. Full OPTIMIZE checklist run. APEASE re-applied. Friction classified correctly (sludge vs. beneficial vs. dark pattern vs. opportunity). |
| 5 | All of the above, plus guardrail metrics proposed, equity check at the subgroup level, compensating-behavior consideration, and the skill flags any case-specific ethical dimension (libertarian paternalism, vulnerable populations, autonomy preservation). |

**Worked example (Steady):**
- **Score 3 looks like:** Flags one risk (e.g., "Decline might feel aggressive"). No guardrail metrics. No friction classification.
- **Score 4 looks like:** Flags multiple specific risks — (a) reactance if "Decline" reads as hostile, (b) SDT autonomy frustration from forced choice, (c) potential "Decline" inflation if users tap it reflexively. Friction correctly classified as removing sludge ("Maybe Later" as costless deferral), not creating dark pattern. APEASE re-applied — Equity check: gig-worker cohort may be sensitive to perceived coercion.

---

## Dimension 6: Process Coherence

Did the skill's stages connect into a coherent flow — each stage's output feeding the next — and were process-level edge cases handled correctly?

This dimension evaluates the *process architecture*, not the content quality at each stage (which is scored in Dimensions 1-5). A solver can produce strong content at every stage and still score low here if the stages don't connect, or if required process-level decisions (two-layer routing, hybrid supplement, cluster randomization, annual-cycle testing, re-engagement baseline distinct from top-of-funnel baseline) were not recognized.

| Score | Anchor |
|---|---|
| 1 | Stages are disconnected. DEFINE output does not match what MAP analyzes. DIAGNOSE barriers do not drive DESIGN choices. Solver jumped from problem to solution at some point. |
| 2 | Most stages present but handoffs are mechanical — later stages don't reference or build on earlier ones. Confirmation between stages missing or performative. |
| 3 | Stages connect in sequence. Each stage's output is recognizable as input to the next. Confirmations present. No process-level edge cases to handle, or they were not recognized. |
| 4 | Stages connect cleanly, output flows through the chain, confirmations sound. At least one process-level edge case in this case was recognized and handled (e.g., two-layer behavior noted at DEFINE and carried through DIAGNOSE; hybrid COM-B + 3B supplement applied where warranted; annual cycle flagged at TEST; cluster randomization for school-level interventions; re-engagement baseline distinct from top-of-funnel baseline). |
| 5 | All of the above, and the solver proactively linked across stages — e.g., flagged at DIAGNOSE that a specific barrier would require a specific guardrail metric at ANALYZE, or noted at DESIGN that intervention type (Type 1 vs Type 2) will shape SCALE planning. Process-level edge cases (if present in this case) all recognized and handled. |

**Worked example (Steady):**
- **Score 3 looks like:** All 8 stages present, outputs connect in sequence. No flag that Steady is a **re-engagement cohort** rather than a top-of-funnel cohort, so baseline considerations at TEST are generic.
- **Score 4 looks like:** Stages connect cleanly and the solver explicitly notes at TEST that **re-engagement baseline ≠ top-of-funnel baseline** (users in this cohort are self-selected non-linkers, so baseline conversion will be lower than onboarding baseline). Or: at DESIGN the solver flags that FAC is a Type 1 change (instant scaling once shipped), which shapes the SCALE stage.

---

## Overall rating guide

- **25-30:** Excellent — skill adds genuine value, matches published practitioner work.
- **18-24:** Good — usable, some improvements needed, likely ready for beta.
- **12-17:** Needs work — significant gaps before public release.
- **Below 12:** Not ready.

---

## Output format for each case

When evaluating a single case, produce:

```
# Case N evaluation

## Scores
- Routing correctness: X/5 — [one-sentence rationale]
- Diagnostic depth: X/5 — [one-sentence rationale]
- Design quality: X/5 — [one-sentence rationale]
- Practical actionability: X/5 — [one-sentence rationale]
- Backfire awareness: X/5 — [one-sentence rationale]
- Process coherence: X/5 — [one-sentence rationale]

**Total: X/30**

## Match vs. Ground Truth
- What the solver got right: [list]
- What the solver missed that ground truth found: [list — be specific, reference the ground truth checkpoint]
- What the solver added that ground truth did not find: [list — label as "value-add" or "noise" with reasoning]

## Notable observations
- [Anything surprising, good or bad]
- [Skill issues surfaced by this case — e.g., routing failure, missing guidance, generic output]

## Overall comment
[2-3 sentences of synthesis]
```

---

*Use this rubric in the evaluator chat only. Do not show it to the solver chat.*
