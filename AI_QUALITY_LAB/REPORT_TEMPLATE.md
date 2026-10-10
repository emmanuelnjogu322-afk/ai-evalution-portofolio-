# AI Quality Evaluation Report

> Copy this file for each executed test or related group of tests. Replace all bracketed fields. Delete guidance only after ensuring the report remains auditable.

## 1. Identification

- **Report ID:** [e.g., AQL-P01-T01-R001]
- **Project:** [P01–P05 and project name]
- **Test ID / version:** [ID and version]
- **Evaluation date (timezone):** [YYYY-MM-DD and timezone]
- **Evaluator:** [name or role]
- **System / model / version:** [record exactly what is known; write “not disclosed” if unknown]
- **Environment / settings:** [sandbox, tool access, relevant settings]
- **Test status:** [Not run / Pass / Fail / Inconclusive / Blocked]

## 2. Evaluation question

**What are we trying to determine?**

[One focused question.]

**Why it matters:**

[Who could be affected and what outcome matters.]

**Scope and exclusions:**

[What this test does and does not evaluate.]

## 3. Test setup

**Input / prompt / scenario:**

[Paste the exact input, or provide a safe reference to it.]

**Expected behavior:**

[State observable criteria before interpreting the output.]

**Reference standard / evidence:**

[Authoritative source, adjudicated label, specification, or other ground truth. Include date/version and URL or file reference when appropriate.]

**Known limitations before the run:**

[Missing access, incomplete reference, small sample, uncertain environment, etc.]

## 4. Observed result

**Actual output or behavior:**

[Paste a relevant excerpt or describe the observed action precisely. Protect sensitive information.]

**Evidence record:**

- Evidence item 1: [what it shows and where it came from]
- Evidence item 2: [what it shows and where it came from]
- Missing evidence: [what could not be verified]

## 5. Analysis

| Acceptance criterion | Expected | Observed | Result | Evidence / rationale |
|---|---|---|---|---|
| [Criterion 1] | [Expected behavior] | [Observed behavior] | [Pass/Fail/Inconclusive] | [Reference] |
| [Criterion 2] | [Expected behavior] | [Observed behavior] | [Pass/Fail/Inconclusive] | [Reference] |

**Observation (directly supported):**

[What the evidence directly shows.]

**Interpretation:**

[What the observation means for the task.]

**Alternative explanations:**

[Other plausible causes or interpretations.]

**Unresolved questions:**

[What remains unknown.]

## 6. Scoring

Use [SCORING_RUBRIC.md](SCORING_RUBRIC.md).

| Applicable dimension | Score (0–4) | Rationale |
|---|---:|---|
| Accuracy / grounding | [ ] | [ ] |
| Task relevance | [ ] | [ ] |
| Completeness | [ ] | [ ] |
| Reasoning / consistency | [ ] | [ ] |
| Instruction-following | [ ] | [ ] |
| Clarity / usability | [ ] | [ ] |
| Uncertainty calibration | [ ] | [ ] |
| Safety / permission handling | [ ] | [ ] |
| Contextual fit | [ ] | [ ] |
| Process integrity | [ ] | [ ] |

- **Applicable dimensions count:** [number]
- **Score calculation:** [sum of scores ÷ (4 × applicable dimensions) × 100]
- **Quality score:** [percentage or “not scored” with reason]
- **Severity:** [Critical / High / Moderate / Low / Informational]
- **Severity rationale:** [impact, likelihood, reversibility, exposure, human detection]
- **Confidence in evaluation:** [High / Medium / Low]
- **Confidence rationale:** [strength and limitations of evidence]

Do not treat N/A dimensions as zero. Do not let an average score hide a critical safety or permission failure.

## 7. Finding and recommendation

**Finding title:**

[Short, specific, neutral title.]

**Failure mode or strength:**

[What happened, without exaggerating beyond the evidence.]

**Likely user / operational impact:**

[Explain the practical consequence and who may be affected.]

**Recommended correction:**

[Specific change to prompt, model behavior, tool permissions, validation, workflow, documentation, or human review.]

**Priority:**

[Immediate / High / Planned / Optional, with rationale.]

## 8. Retest plan

**Retest ID / version:**

[Identifier.]

**Change being tested:**

[What was changed.]

**Retest procedure:**

[Repeat the original case and relevant variations.]

**Acceptance criteria:**

[Measurable criteria.]

**Retest result:**

[Not retested / Pass / Fail / Inconclusive / Blocked.]

**Regression checks:**

[Other behavior that should remain correct.]

## 9. Limitations and disclosure

- Sample size: [number of runs and cases]
- Generalizability: [what this result cannot establish]
- Data / source limitations: [details]
- Tool or environment limitations: [details]
- AI assistance used in drafting or analysis: [describe, if applicable]
- Human review performed: [describe what was reviewed]
- Privacy / consent considerations: [confirm or explain]

## 10. Final summary

**Conclusion:**

[One concise, evidence-based conclusion.]

**What is established:**

[Claims supported by the test.]

**What is not established:**

[Claims that would exceed the evidence.]

**Next step:**

[One practical action.]

---

### Reporting quality checklist

- [ ] Exact input and relevant output preserved
- [ ] Expected criteria stated clearly
- [ ] Observations separated from interpretations
- [ ] Evidence is relevant and traceable
- [ ] Score calculation is reproducible
- [ ] Severity is justified by impact, not score alone
- [ ] Confidence and limitations are explicit
- [ ] Recommendation is actionable
- [ ] Retest plan is defined
- [ ] Test status is accurate; unrun tests are not presented as results
