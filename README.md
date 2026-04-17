# Behavioral Design Guide

You know the behavior you want to change. You've studied multiple frameworks, maybe already tried them on your work, personal projects or life. But when you sit down to actually try to follow the behavioral design process — define the behavior precisely, find the real barriers, pick the right intervention, et cetera — the process suddenly feels...scattered. Which framework do I use here? Am I missing something in my analysis? Is this rigorous and science-based enough?

Sounds familiar?

This skill is a thinking partner for that whole process. It walks you through a full behavioral design cycle, recommends frameworks at each step with reasoning, and supports your decisions. It's not a replacement for expertise — it's a scaffold that helps you apply what you know more systematically.

Built for UX researchers, product managers, and behavioral designers who need key BeSci frameworks all in one place.

## What It Does

The skill walks you through 8 stages of a behavioral design cycle. At each stage, it asks you questions, recommends a framework with reasoning, and produces a structured output before moving on.

| Stage | What happens | What you get |
|---|---|---|
| **DEFINE** | Nail down exactly what behavior you're changing, for whom, and when. The skill picks the right definition tool for your context and tests whether the behavior is specific enough to design for. | A precise, measurable behavior statement that passes the "can you physically mime this?" test. |
| **MAP** | Walk through what users actually do today, step by step. At each step, the skill asks what could go wrong and what data you have. | A behavioral map with barrier hypotheses at each step, plus a check that you haven't missed a layer of context (physical, social, structural). |
| **EVIDENCE CHECK** | Figure out whether you have enough data to diagnose, or need to collect first. If you have data, the skill forces you to state what the data shows before any framework is applied. | A routing decision (data-first, adjacent data, collect, or hypothesis-based) and, if data exists, a three-part summary: what the data shows, what it implies, and what it doesn't tell you. |
| **DIAGNOSE** | Find the real barriers — not just the obvious ones. The skill routes you to COM-B or 3B based on your context, walks through each component with diagnostic questions, and helps you prioritize. | A ranked barrier list with evidence quality noted for each one. The top barrier is the design target. |
| **DESIGN** | Turn the top barrier into a concrete intervention. The skill maps barriers to strategies, cross-checks against EAST, filters through APEASE ethics criteria, and helps you write a testable hypothesis. | An intervention package with a clear hypothesis: "If [intervention] among [segment], then [metric will change], because [mechanism]." |
| **OPTIMIZE** | Check whether the intervention will sustain and whether it could backfire. Includes SDT motivation check, social norm boundary conditions, friction classification, ethical mirror, and risk compensation. | A checked intervention with backfire risks flagged and mitigations designed. |
| **TEST** | Design the experiment. The skill picks the right method for your sample size and constraints, and walks you through a pre-analysis plan. | An experiment design with hypothesis, primary metric, sample size, duration, and stopping rule documented before you run anything. |
| **ANALYZE → SCALE** | Interpret results honestly (with trustworthiness checks before conclusions), then plan implementation — distinguishing system changes that scale instantly from practice changes that require buy-in. | A one-page results summary and a scaling plan with context sensitivity, effect decay, and fidelity checks. |

## How to Install

### Method 1: Upload the file in the Claude app (simplest)

Works on desktop (Mac/Windows), mobile (iOS/Android), and web at [claude.ai](https://claude.ai). Available on Free, Pro, Max, Team, and Enterprise plans.

**Step 1.** Download `SKILL.md` from this repo.

**Step 2.** Open the Claude app (or [claude.ai](https://claude.ai) in your browser).

**Step 3.** Click the **Customize** icon — it's in the bottom-left corner on desktop, or in the menu on mobile.

**Step 4.** Go to **Skills**.

**Step 5.** Click **Add Skill** (or the **+** button on mobile).

**Step 6.** Upload the `SKILL.md` file directly. Claude will read it and show you the skill name and description.

**Step 7.** Make sure the skill is toggled **on**.

**Step 8.** Start a new conversation. The skill activates automatically when you describe a behavioral design problem. You can also say: *"I want to work through a behavioral design problem"* or *"Help me design an intervention for [behavior]."*

That's it — no ZIP, no folder structure, just upload the file.

### Method 2: Upload as a ZIP

If you want to include additional files alongside the skill (e.g., your own reference materials), you can upload the whole folder as a ZIP.

**Step 1.** Download or clone this repo. You need the `behavioral-design-guide` folder containing `SKILL.md`.

**Step 2.** Create a ZIP of that folder. The ZIP must contain the folder at the root — not just the file. On Mac: right-click the folder → Compress. On Windows: right-click → Send to → Compressed folder.

Your ZIP structure should look like this:
```
behavioral-design-guide.zip
└── behavioral-design-guide/
    └── SKILL.md
```

Not like this:
```
behavioral-design-guide.zip
└── SKILL.md          ← wrong: file at root without folder
```

**Step 3.** In Claude, go to **Customize** → **Skills** → **Add Skill** → upload the ZIP.

### Method 3: Use as a Project system prompt

If you don't want to install a skill, paste the contents of `SKILL.md` as a system prompt in a Claude Project.

**Step 1.** Open [claude.ai](https://claude.ai) → **Projects** (left sidebar) → create a new project.

**Step 2.** In the project settings, find the **System prompt** (or "Project instructions") field.

**Step 3.** Copy the entire contents of `SKILL.md` and paste it in. Save.

**Step 4.** Start a conversation inside that project. The skill is active for all conversations in this project.

### Method 4: Claude Code

Place the `behavioral-design-guide` folder in your repo under `.claude/skills/`. It will be available in all Claude Code sessions for that project.

## Getting Started

Once the skill is installed and toggled on, open a new conversation. You have two ways to activate it:

**Option A — just describe your task.** Claude recognizes when the skill is relevant and activates it automatically. For example, type: *"I want to work through a behavioral design problem"* or *"Help me design an intervention for [behavior]."*

**Option B — invoke directly.** Type `/` in the message field to see your available skills, then select **behavioral-design-guide**.

Either way, Claude will open with something like this:

> I'm a behavioral design thinking partner. I'll help you work through a full design cycle — defining the target behavior, finding what actually stops people, designing an intervention, and planning a test.
>
> Before we start: would you like a quick refresher on the foundational ideas behind behavioral design (how people actually make decisions, why context matters), or jump straight to your problem? Either is fine — the process is the same.
>
> If you're ready to start, tell me what you can:
>
> 1. What behavior are you trying to change, start, or stop?
> 2. Who needs to do it, and roughly how many?
> 3. What's the context — a digital product, physical environment, communication, or something else?
> 4. What data do you have — analytics, user research, surveys, or starting from scratch?
>
> A couple of sentences on each is enough. We'll fill gaps as we go.

You don't need to answer all four questions perfectly. A rough sketch is enough — the skill will ask follow-up questions to fill gaps. For example, you might say:

> *"I'm working on a health app where patients are assigned physical therapy exercises to do at home. Most patients complete the first week but drop off by week 3. We have app usage data and some NPS survey results. The behavior is completing the daily exercise routine."*

From there, the skill takes you through the process one stage at a time. It'll start by tightening up your behavior definition, then map what users actually do, then check your data, and so on. At the end of each stage, it asks you to confirm before moving forward — you're always in control of the pace.

## Frameworks Used

The skill routes you to the right framework based on your context — digital product, physical environment, communication, or complex service — and explains the trade-offs when two frameworks could fit. Barrier→strategy mapping tables and a design direction bridge connect diagnosis to technique.

| Group | Framework | What it does | Source |
|---|---|---|---|
| Process design | **DECIDE** | Full behavioral design cycle: Define → Explore → Craft → Implement → Determine → Evaluate | Wendel (2020), *Designing for Behavior Change* |
| Process design | **SIDE** | Strategy → Insights → Design → Evaluation, with named deliverables at each stage | Wallaert (2019), *Start at the End* |
| Barrier diagnosis | **COM-B / BCW** | Six components: Physical/Psychological Capability, Physical/Social Opportunity, Automatic/Reflective Motivation | Michie, van Stralen & West (2011); Michie, Atkins & West (2014) |
| Barrier diagnosis | **3B** | Behavior + Barriers + Benefits.| Irrational Labs (2019) |
| Barrier diagnosis | **B=MAP** | Behavior = Motivation × Ability × Prompt. | Fogg (2009, 2020), *Tiny Habits* |
| Barrier diagnosis | **CREATE** | Six-step action funnel: Cue → Reaction → Evaluation → Ability → Timing → Experience | Wendel (2020) |
| Barrier diagnosis | **Wallaert Pressure Map** | Maps competing promoting and inhibiting pressures on a behavior | Wallaert (2019) |
| Intervention design | **EAST** | Four design principles: Easy, Attractive, Social, Timely. Used as design-quality cross-check | Behavioural Insights Team (2014, updated 2024) |
| Intervention design | **MINDSPACE** | Nine influence effects: Messenger, Incentives, Norms, Defaults, Salience, Priming, Affect, Commitments, Ego | Dolan, Hallsworth, Halpern, King & Vlaev (2010) |
| Intervention design | **BCW Intervention Functions + BCTs** | Evidence-based mapping: 9 Intervention Functions → 93 Behaviour Change Techniques, linked to COM-B barriers | Michie, Atkins & West (2014) |
| Sustainability & motivation | **SDT** | Three basic psychological needs (autonomy, competence, relatedness) + six-stage motivation continuum from amotivation to intrinsic | Deci & Ryan (2000) |
| Ethics & filtering | **APEASE** | Six-criteria filter: Affordable, Practicable, Effective & cost-effective, Acceptable, Side-effects/safety, Equity | Michie, Atkins & West (2014) |
| Ethics & filtering | **Regret Test** | Would the user, on reflection, judge themselves better off? | Adapted from Thaler & Sunstein (2008), *Nudge* |
| Ethics & filtering | **Social norm backfire checklist** | 8 boundary conditions before using descriptive norms (prevalence, in-group, observability, boomerang risk, etc.) | Cialdini (2003, 2006); Schultz et al. (2007); Hallsworth & Kirkman (2020) |

Full bibliographic details with open-access links where available are in the [Attribution](#attribution) section below.

## Validation

The skill was validated against 9 published behavioral design cases spanning digital products, communication interventions, physical environments, and public health.

**Method.** A solver instance (Claude Sonnet 4.6 using the skill as system prompt) worked through each case with full context. A separate evaluator instance (Claude Sonnet 4.6, no access to the skill, calibrated with worked examples) scored each run against published ground truth on 6 dimensions: behavior definition precision, diagnostic depth, intervention quality, backfire awareness, process coherence, and practical actionability.

**Results.** Average score across 9 cases at v1.2: 21.4/30. After targeted fixes to the two lowest-scoring cases (EarnUp: 16→22, Mumbai: 17→26), adjusted average at v1.3: 23.1/30.

In structured walkthroughs against these 9 published cases, the skill's diagnostic path converged on the barriers and intervention mechanisms that the published teams identified. Consistently strong areas: practical actionability, backfire awareness, process coherence. Consistently weaker: diagnostic depth — the skill produces comprehensive barrier inventories but sometimes misses specific upstream insight.

**What this validation tells you and what it doesn't.** This is convergent validation: does the skill reach the same diagnostic conclusions as expert teams who designed real interventions? It answers "does the process converge on what experts found?" — and for 9 cases, it mostly does. It does *not* answer "does the skill work well for new practitioners working on novel problems?" That requires blind practitioner testing, which is the next validation layer. If you use this skill and find places where it breaks, that data is exactly what's needed — see Feedback below.

**Caveats:**
- Evaluator is an LLM (Claude Sonnet 4.6), not a human expert panel. Calibrated with worked examples to reduce leniency bias.
- Cases are from published literature — the solver may have encountered some during training.
- 9 cases oversample digital-product and communication interventions. Physical environment and policy cases are underrepresented.
- One case (Steady, 26/30) was used as calibration anchor for the evaluator — do not treat it as an independent result.

The `validation/` folder contains the full methodology, cases, rubric, and results.

## Known Weaknesses

Things the skill tries to do but doesn't do well enough yet — found through validation:

- **Framing direction (loss vs. gain).** The skill defaults to loss framing in ambiguous cases. Published evidence sometimes shows gain framing wins. A framing direction checkpoint is planned for v1.4 — for now, if your intervention involves framing a message, check the evidence for your specific population and behavior before defaulting.
- **Diagnostic depth in complex cases.** The skill produces thorough barrier inventories but can miss the single most important upstream insight. If the diagnosis feels too broad, push back — ask the skill to prioritize harder and explain which barrier it would bet on.

## What's Not Covered

Deliberate scope boundaries — things the skill doesn't try to do:

- **Motivational Interviewing techniques.** The skill covers diagnosis and design but not the conversational techniques used in MI-based interventions. Planned for v2.
- **Gamification depth.** The skill covers basic incentive design and crowding-out risks but not detailed gamification mechanics. Planned for v2.
- **Advanced quasi-experimental methods.** The skill covers A/B, pre-post, ITS, and DiD at a practical level. For complex designs (regression discontinuity, synthetic control, instrumental variables), consult a statistician.
- **Clinical interventions.** The skill is for behavioral design, not clinical practice. If the behavior change requires clinical expertise (addiction treatment, eating disorders, PTSD), consult clinical guidelines and qualified professionals.

## Roadmap

**v1.4 (post-feedback).** Framing direction checkpoint, routing justification strengthening, guardrail metrics as required output, progressive disclosure as a design option. Prioritized based on practitioner feedback after publication.

**v2 (product-level).** MI integration, gamification depth, messaging audit mini-tool, data-pattern discovery prompts.

**Feedback-driven.** Any fix that 2+ practitioners independently request moves to the top of v1.4.

## Feedback

This skill was built by one practitioner as a scaffold she herself needs. It gets better with feedback from people who actually use it on real problems.

**→ [Share feedback (Tally form, ~2 min)](https://tally.so/r/kdRYPJ)**

**Other ways to reach me:**
- **GitHub Issues** — best for specific bugs or feature requests.
- **LinkedIn** — if you'd rather share personally: [linkedin.com/in/valeriadiatullina](https://www.linkedin.com/in/valeriadiatullina/)

## License

CC BY-NC-SA 4.0 — you can share and adapt this skill for non-commercial purposes, with attribution, under the same license.

## Attribution

This skill synthesizes published frameworks. Full credit to the original authors:

- **COM-B / BCW / BCTs / APEASE:** Michie, S., van Stralen, M. M., & West, R. (2011). The Behaviour Change Wheel: a new method for characterising and designing behaviour change interventions. *Implementation Science, 6*(1), 42. [Open access](https://implementationscience.biomedcentral.com/articles/10.1186/1748-5908-6-42). Expanded in: Michie, S., Atkins, L., & West, R. (2014). *The Behaviour Change Wheel: A Guide to Designing Interventions.* APEASE criteria for intervention appraisal are from the same source.
- **DECIDE / CREATE:** Wendel, S. (2020). *Designing for Behavior Change: Applying Psychology and Behavioral Economics* (2nd ed.). O'Reilly.
- **SIDE / Pressure Map / Behavioral Statement:** Wallaert, M. (2019). *Start at the End: How to Build Products That Create Change.* Portfolio/Penguin. Also: Wallaert, M. (n.d.). *Free Course: Interventions.* [mattwallaert.com/free-course-4-interventions](https://mattwallaert.com/free-course-4-interventions/).
- **Behavior change design for digital products:** Bucher, A. (2020). *Engaged: Designing for Behavior Change.* Rosenfeld Media.
- **3B / Key Behavior / Behavioral Map:** Irrational Labs (2019). Behavioral Design Bootcamp materials. Part of the IL 3-Phase behavioral design process.
- **EAST:** Behavioural Insights Team (2014, updated 2024). *EAST: Four Simple Ways to Apply Behavioural Insights.* Licensed CC BY-NC-SA 4.0. [Free PDF](https://www.bi.team/publications/east-four-simple-ways-to-apply-behavioural-insights/).
- **MINDSPACE:** Dolan, P., Hallsworth, M., Halpern, D., King, D., & Vlaev, I. (2010). *MINDSPACE: Influencing Behaviour through Public Policy.* Institute for Government / Cabinet Office. [Free PDF](https://www.instituteforgovernment.org.uk/publication/mindspace).
- **SDT:** Deci, E. L., & Ryan, R. M. (2000). The "what" and "why" of goal pursuits: Human needs and the self-determination of behavior. *Psychological Inquiry, 11*(4), 227–268. [JSTOR](https://www.jstor.org/stable/1449618).
- **B=MAP:** Fogg, B. J. (2020). *Tiny Habits: The Small Changes That Change Everything.* Houghton Mifflin Harcourt. Model originally published as B=MAT in Fogg (2009).
- **Social norm boundary conditions:** Cialdini, R. B. (2003, 2006). Crafting normative messages to protect the environment. *Current Directions in Psychological Science.* Schultz, P. W., Nolan, J. M., Cialdini, R. B., Goldstein, N. J., & Griskevicius, V. (2007). The constructive, destructive, and reconstructive power of social norms. *Psychological Science, 18*(5), 429–434. Hallsworth, M., & Kirkman, E. (2020). *Behavioral Insights.* MIT Press.
- **Regret Test:** Adapted from Thaler, R. H., & Sunstein, C. R. (2008). *Nudge: Improving Decisions about Health, Wealth, and Happiness.* Yale University Press.
- **Bounded rationality:** Simon, H. A. (1955). A behavioral model of rational choice. *Quarterly Journal of Economics, 69*(1), 99–118.
- **Dual process / heuristics and biases:** Kahneman, D., & Tversky, A. (1974). Judgment under uncertainty: Heuristics and biases. *Science, 185*(4157), 1124–1131. Kahneman, D. (2011). *Thinking, Fast and Slow.* Farrar, Straus and Giroux.
- **Field theory:** Lewin, K. (1936). *Principles of Topological Psychology.* McGraw-Hill. B = f(Person, Environment) — used in Foundations and as the basis for the 5-layer environment check at MAP.

---

*Behavioral Design Guide v1.3 — Valeriia with Claude — April 2026*

