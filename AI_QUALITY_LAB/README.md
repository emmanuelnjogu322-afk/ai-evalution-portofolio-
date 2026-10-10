# AI QUALITY LAB
### A five-domain framework for evaluating AI quality, reliability, and real-world usefulness

**Portfolio artifact · Version 1.0 · 10 October 2026**

> **Purpose:** Demonstrate a repeatable, evidence-aware method for testing AI systems—not merely whether an answer sounds convincing, but whether it is accurate, appropriately cautious, safe to act on, and useful in its intended context.

This lab organizes five complementary evaluation projects into one portfolio. It builds on the repository's existing AI-response evaluation work and extends the method to agents, multimodal systems, African-context localization, and end-to-end workflows.

**Status transparency:** The framework, test scenarios, rubric, and reporting template are documented here. Test scenarios are proposed evaluation cases; they must not be represented as executed experiments until actual model outputs have been collected and reviewed.

---

## The five projects

| ID | Project | Main question | Example evaluation targets |
|---|---|---|---|
| P01 | **AI Response Evaluation Lab** | Is the answer accurate, relevant, complete, and appropriately supported? | Factuality, evidence quality, reasoning, uncertainty, instruction-following |
| P02 | **Agent Reliability & Safety Lab** | Does an AI agent use tools and permissions correctly and stop when it should? | Tool selection, permission boundaries, confirmation, recovery, escalation |
| P03 | **Multimodal & Physical AI Evaluation Lab** | Does the system interpret visual and temporal evidence faithfully? | Detection, classification, segmentation, occlusion, tracking, spatial reasoning |
| P04 | **African Context & Localization Lab** | Is the output correct and useful for the actual local context? | Kenya-specific context, language meaning, local services and payments, cultural fit |
| P05 | **AI Workflow Quality Assurance Lab** | Does the whole AI-assisted process produce a dependable result? | Handoffs, process compliance, data handling, quality gates, human review, retesting |

### How they connect

The same evaluation discipline runs through every project:

1. **Define** the task, user, environment, and acceptable outcome.
2. **Design** a test with observable pass/fail criteria.
3. **Collect** the actual output or system behavior.
4. **Compare** the evidence with the criteria.
5. **Rate** quality, risk, and confidence separately.
6. **Report** the failure mode and its likely impact.
7. **Recommend** a proportionate correction.
8. **Retest** the changed system using the original test and relevant variations.

P01 examines the response. P02 examines actions. P03 examines visual or temporal interpretation. P04 examines contextual correctness. P05 examines the complete workflow.

---

## Evaluation principles

- **Evidence before confidence.** A polished tone is not proof.
- **No invented ground truth.** Mark unknowns as unknown and seek an appropriate source or reviewer.
- **Separate observation from inference.** State what was directly seen, what was inferred, and what remains uncertain.
- **Score the output, not the evaluator's preferred answer.** Use explicit criteria and preserve counterevidence.
- **Risk is not the same as quality.** A minor wording issue and an unsafe external action should not receive the same priority.
- **Human oversight is part of the system.** Define when the AI must pause, ask, escalate, or defer.
- **Context matters.** A response can be broadly plausible but locally incorrect or unusable.
- **Reproducibility matters.** Record the prompt, system/model identifier when available, date, settings, expected result, actual result, and rubric version.
- **Be honest about test status.** A test design is not an experiment result; a single example is not a general performance claim.

---

## Shared scoring model

Use the rubric in [SCORING_RUBRIC.md](SCORING_RUBRIC.md). Record these separately:

- **Quality score:** 0–100 across applicable quality dimensions.
- **Severity:** Critical / High / Moderate / Low / Informational.
- **Confidence in the evaluation:** High / Medium / Low, based on evidence strength.
- **Test status:** Not run / Pass / Fail / Inconclusive / Blocked.
- **Retest status:** Not retested / Passed retest / Failed retest.

Do not average away a critical safety failure. A high overall score cannot cancel a failure involving unauthorized action, serious misinformation, or a breached permission boundary.

---

## Repository layout

```text
AI_QUALITY_LAB/
├── README.md
├── SCORING_RUBRIC.md
├── TEST_CATALOG.md
└── REPORT_TEMPLATE.md
```

Each project can later receive its own folder for raw test records, annotated examples, analysis, and retest history.

---

## Starter test catalog

The initial test catalog contains 10 proposed tests spanning all five projects. They are designed to be executable and auditable. Do not fill in outcomes until the test is actually run.

See [TEST_CATALOG.md](TEST_CATALOG.md).

---

## Reporting a finding

For each finding, include:

- Test ID and project
- Task and expected behavior
- Environment and model/system version, if known
- Exact input and relevant output excerpt
- Evidence used to judge the result
- Expected vs. observed behavior
- Quality dimensions affected
- Severity and rationale
- Confidence and limitations
- Recommended correction
- Retest procedure and result

Use [REPORT_TEMPLATE.md](REPORT_TEMPLATE.md) to document findings consistently.

---

## Completion criteria for a project

A project is ready to be presented as an executed case study only when it has:

- [ ] A defined evaluation question and scope
- [ ] A documented test plan and acceptance criteria
- [ ] Actual outputs or behavior captured with appropriate privacy precautions
- [ ] Evidence or a defensible reference standard for judgments
- [ ] Scoring with explanations, not just numbers
- [ ] Limitations and uncertainty stated
- [ ] At least one documented failure analysis or justified pass
- [ ] A retest, or an explicit explanation of why retesting was not possible

A project may be presented as **designed** before all items are complete, but it must be labeled accurately.

---

## Ethical and practical boundaries

- Use synthetic or permissioned data for portfolio demonstrations.
- Never publish personal, confidential, or client-sensitive information.
- Do not attempt unauthorized access, tool abuse, or destructive tests against real systems.
- For tool-using agents, test against a sandbox or simulated environment whenever possible.
- Do not claim that a model is safe or reliable based on a small sample.
- Use primary or authoritative sources for factual verification where available; record source date and relevant context.
- For local-context tests, verify changing details such as fees, eligibility, operating hours, and payment methods before treating them as facts.

---

## Suggested execution order

1. **P01 — Response evaluation:** extend the repository's existing claim-verification work.
2. **P04 — African context:** apply the same evidence discipline to Kenya-specific prompts.
3. **P02 — Agent reliability:** start with simulated tools and reversible actions.
4. **P03 — Multimodal evaluation:** use licensed, public-domain, or self-created media with clear ground truth.
5. **P05 — Workflow QA:** combine the earlier methods into an end-to-end process audit.

This order reuses existing skills instead of starting five disconnected projects at once.

---

## What this artifact demonstrates

- Evaluation design and rubric development
- Factuality and evidence assessment
- Risk-based prioritization
- Test-case writing
- Structured quality reporting
- Awareness of localization and multimodal failure modes
- Reproducible, human-reviewed evaluation practices

It does **not** claim employment, certification, production deployment, or measured model performance. Those claims require separate evidence.

---

**Maintainer:** Emmanuel Njogu Wakio  
**Parent portfolio:** [AI Evaluation Portfolio](../README.md)  
**Last updated:** 10 October 2026
