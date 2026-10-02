# Security & Quality Policy

**Project:** AI Evaluation & Evidence Auditing  
**Status:** Active  
**Version:** 1.0  
**Last Updated:** 2026-10-02

---

## 1. Purpose

This policy defines the security, evidence-integrity, evaluation-quality, and audit standards for this project.

The project is designed around a simple principle:

> **An AI system should not receive credit for sounding convincing when the evidence does not support what it says.**

The goal is not merely to determine whether an AI response is "good" or "bad." The goal is to determine:

- whether claims are supported by evidence;
- whether the evidence actually supports the specific claim;
- whether sources are independent or merely repeating one another;
- whether the model distinguishes fact from inference;
- whether uncertainty is represented honestly;
- whether the model invents citations, evidence, events, or conclusions;
- whether the evaluation itself is reproducible and defensible;
- and whether a human auditor can trace a judgment back to observable evidence.

This policy applies to evaluation datasets, prompts, model outputs, annotations, scoring rubrics, audit reports, experiments, source collections, and related project documentation.

---

# 2. Core Quality Principles

## 2.1 Evidence Before Confidence

A confident answer is not automatically a reliable answer.

Evaluators must distinguish between:

1. **What the source explicitly states**
2. **What can reasonably be inferred**
3. **What remains unknown**
4. **What the model claims without sufficient support**

Confidence must never substitute for evidence.

---

## 2.2 Claim–Evidence Alignment

A source is not considered supporting evidence merely because it is relevant to the topic.

The evaluator must ask:

> **Does this specific source support this specific claim?**

For every important claim, evaluate:

- claim specificity;
- source relevance;
- source authority;
- temporal alignment;
- contextual alignment;
- whether the source actually entails the claim;
- whether important qualifiers were omitted.

A source discussing an event does not automatically prove that the event occurred.

A source saying that an action was **planned, requested, scheduled, proposed, or arranged** does not automatically prove that the action **occurred**.

---

## 2.3 Source Independence

Multiple sources do not necessarily constitute multiple independent pieces of evidence.

Evaluators must investigate whether sources:

- copy one another;
- cite the same underlying source;
- originate from the same institution;
- repeat the same unverified claim;
- derive from a common database;
- or independently document the event.

### Independence rule

> **Five sources repeating one unsupported claim are not equivalent to five independent confirmations.**

When source independence cannot be established, the evaluation should record that uncertainty rather than assuming independence.

---

## 2.4 Provenance Over Appearance

Every important piece of evidence should have traceable provenance where practical.

Preferred provenance information includes:

- source name;
- source type;
- publication or creation date;
- author/organization;
- URL or document identifier where appropriate;
- relevant page, section, timestamp, or passage;
- retrieval date when relevant;
- relationship to other sources.

Evidence must not be treated as verified merely because it appears in a polished report, search result, AI response, or secondary summary.

---

# 3. AI Evaluation Standards

## 3.1 Primary Evaluation Dimensions

AI responses should be evaluated across multiple dimensions rather than a single "correct/incorrect" score.

Core dimensions include:

### Accuracy
Does the response represent available evidence correctly?

### Relevance
Does it answer the actual task without unnecessary deviation?

### Completeness
Does it address the important parts of the task while avoiding unsupported additions?

### Reasoning Quality
Does the conclusion follow from the available evidence?

### Evidence Grounding
Are claims appropriately supported by sources or supplied material?

### Source Integrity
Are cited sources real, relevant, and correctly represented?

### Uncertainty Calibration
Does the model distinguish established facts from uncertainty and inference?

### Instruction Following
Did the model follow the user's explicit constraints?

### Clarity
Can a reviewer understand what the model is claiming and why?

### Reliability
Would the response remain defensible under reasonable scrutiny or a changed evidence set?

---

# 4. Evidence States

Evaluators should avoid collapsing every claim into simply "true" or "false."

Where applicable, classify claims using states such as:

- **Supported** — sufficient evidence directly supports the claim.
- **Partially Supported** — evidence supports part of the claim but not its full scope.
- **Unsupported** — available evidence does not establish the claim.
- **Contradicted** — credible evidence conflicts with the claim.
- **Unverifiable** — insufficient evidence is available to determine the status.
- **Inference** — the conclusion is derived rather than directly stated.
- **Speculation** — the claim extends beyond what the evidence reasonably permits.

This distinction is especially important in evidence-auditing tasks.

---

# 5. The Evidence Boundary

Every evaluation should identify the boundary between:

**Evidence → Inference → Unknown**

The evaluator must not allow a model to silently move from one category to another.

For example:

> Source: "Payment arrangements were made."

This supports:

- an arrangement existed.

It does **not automatically support**:

- payment occurred;
- money changed hands;
- the transaction was completed;
- the recipient received the funds.

A model that converts the first statement into the latter claims should receive a grounding/reasoning penalty.

---

# 6. Hallucinated Evidence & Fabricated Grounding

The following are high-severity quality failures:

- invented sources;
- fabricated quotations;
- fabricated page numbers;
- fabricated URLs;
- citations that do not contain the claimed information;
- claims attributed to sources that never made them;
- invented events;
- invented statistics;
- invented transactions;
- invented documents;
- presenting model-generated reasoning as if it were source evidence.

### Critical principle

> **The model must never manufacture the evidence required to make its answer correct.**

If evidence is missing, the correct behavior is to acknowledge the gap.

---

# 7. Citation Verification

A citation should be evaluated on more than whether a URL exists.

Reviewers should test:

1. **Existence** — Does the cited source exist?
2. **Identity** — Is it actually the source being described?
3. **Relevance** — Is it about the claim?
4. **Entailment** — Does it support the claim?
5. **Context** — Was important context or qualification omitted?
6. **Temporal validity** — Was the source appropriate for the relevant time period?
7. **Independence** — Is it genuinely independent from other cited evidence?

A technically valid citation can still be an invalid grounding citation.

---

# 8. Source Contamination

Evaluations must account for contamination between:

- the model's prior knowledge;
- retrieved information;
- supplied documents;
- evaluator assumptions;
- benchmark answers;
- other model outputs;
- and secondary sources.

When the task requires evidence from a defined source set, the model should not receive credit for importing unsupported information from outside that evidence boundary.

If external information is allowed, the evaluation should explicitly record that fact.

---

# 9. Ambiguity Policy

Ambiguous prompts and ambiguous evidence should not be silently resolved in the model's favor.

When ambiguity materially affects the answer, the preferred model behavior is to:

- identify the ambiguity;
- explain the competing interpretations;
- state what can be established;
- state what cannot be established;
- request clarification when necessary.

### Evaluation principle

> **Uncertainty is information, not failure.**

A cautious answer can be more reliable than a precise-looking answer built on assumptions.

---

# 10. Confidence Calibration

Model confidence should correspond reasonably to evidentiary strength.

High confidence with weak evidence is a quality failure.

Evaluators should specifically test for:

- unjustified certainty;
- authoritative wording unsupported by evidence;
- false precision;
- omission of uncertainty;
- certainty inflation after ambiguous evidence;
- and confidence that changes without a corresponding change in evidence.

Where possible, record both:

**Evidence strength** and **model confidence**.

A mismatch between the two should be investigated.

---

# 11. Sycophancy & Authority Bias

Evaluations should test whether a model changes its conclusion merely because a user:

- sounds confident;
- claims expertise;
- provides a preferred answer;
- pressures the model to agree;
- frames disagreement as incompetence;
- or invokes an authority without supplying supporting evidence.

The model should evaluate the evidence rather than simply mirror the user's confidence.

---

# 12. Adversarial Evaluation

The project should intentionally include difficult cases designed to expose weak evaluation behavior.

Examples include:

- plausible but unsupported claims;
- misleading citations;
- conflicting sources;
- incomplete records;
- duplicate sources;
- circular sourcing;
- ambiguous wording;
- temporal inconsistencies;
- source substitution;
- fabricated citations;
- emotionally persuasive claims;
- authority-based assertions;
- and prompts containing an implied answer.

The purpose is not to trick models for its own sake.

The purpose is to determine whether the evaluation system can distinguish:

**persuasion from proof.**

---

# 13. Human Auditor Requirements

Human evaluation remains responsible for interpreting evidence where automated scoring is insufficient.

Auditors should:

- document the reasoning behind consequential judgments;
- avoid scoring based solely on writing quality;
- separate factual correctness from stylistic quality;
- challenge their own assumptions;
- identify missing evidence;
- record uncertainty;
- distinguish source evidence from personal interpretation;
- and avoid retroactively adjusting evidence to fit a preferred conclusion.

Where disagreement occurs, preserve the disagreement rather than automatically forcing consensus.

---

# 14. Evaluation Rubric Integrity

Rubrics must be:

- explicit;
- internally consistent;
- applicable across comparable cases;
- evidence-based;
- resistant to superficial answer quality;
- and version controlled.

Scores should be accompanied by observable reasons.

A high score must not be awarded simply because a response:

- sounds professional;
- uses sophisticated vocabulary;
- cites many sources;
- is long;
- agrees with the evaluator;
- or reaches the expected conclusion.

---

# 15. Severity Framework

Quality failures should be classified according to their potential impact.

### Critical
Failures that fundamentally compromise evidence integrity.

Examples:

- fabricated evidence;
- fabricated citations;
- deliberate-looking source misrepresentation;
- major unsupported factual claims presented as established facts;
- conclusions directly contradicted by the supplied evidence.

### Major
Failures that materially affect the reliability of the answer.

Examples:

- important unsupported claims;
- incorrect interpretation of key evidence;
- major source-context omission;
- false certainty in a consequential conclusion.

### Moderate
Meaningful but limited defects.

Examples:

- incomplete qualification;
- minor reasoning gaps;
- insufficiently explicit uncertainty;
- limited omission that does not reverse the main conclusion.

### Minor
Low-impact quality issues.

Examples:

- small clarity problems;
- minor formatting issues;
- non-consequential omissions.

Severity should be determined by **impact on the reliability of the conclusion**, not merely by how noticeable the mistake is.

---

# 16. Security Principles

## 16.1 Data Minimization

Only collect and retain information necessary for the evaluation.

Avoid storing:

- unnecessary personal information;
- authentication credentials;
- private identifiers;
- financial credentials;
- secrets;
- access tokens;
- API keys;
- or unrelated personal data.

---

## 16.2 Secrets

Secrets must never be committed to the repository.

Examples include:

- API keys;
- passwords;
- access tokens;
- private keys;
- session tokens;
- credentials;
- database connection strings containing secrets.

Use environment variables or secure secret-management systems instead.

If a secret is accidentally committed, treat it as compromised and rotate/revoke it.

---

## 16.3 Sensitive Evidence

Sensitive documents should be:

- minimized;
- access-controlled;
- anonymized where appropriate;
- stored only where necessary;
- and excluded from public repositories unless publication is authorized.

Public examples should use synthetic, redacted, or legitimately public evidence whenever possible.

---

# 17. Dataset Security

Evaluation datasets should be protected against:

- accidental modification;
- unauthorized deletion;
- contamination;
- duplicated records;
- hidden answer leakage;
- benchmark leakage;
- and undocumented changes.

Where practical, maintain:

- dataset versions;
- checksums or hashes;
- change logs;
- provenance information;
- and release dates.

A changed dataset should be treated as a new evaluation condition when the change could affect results.

---

# 18. Reproducibility

A credible evaluation should be reproducible where technically possible.

Record relevant:

- model name/version;
- evaluation date;
- prompt version;
- system/developer instructions where permissible;
- tools available to the model;
- retrieval configuration;
- source set;
- rubric version;
- evaluator version;
- temperature or relevant generation settings where available;
- and important environmental constraints.

If exact reproduction is impossible, document the limitation.

---

# 19. Evaluation Independence

The evaluator must not create a circular system where:

> AI generates the evidence → AI interprets the evidence → AI validates its own interpretation → AI receives a score based on its own output.

Where automated evaluation is used, independent checks should be introduced where practical.

Human review, independent evidence, alternative evaluators, or adversarial tests can help reduce circular validation.

---

# 20. Model-to-Model Evaluation

When comparing AI systems:

- use equivalent task conditions;
- preserve the same evidence boundary;
- use the same rubric;
- avoid changing evaluation standards to favor one system;
- distinguish model capability from tool-access differences;
- record model/version information;
- and avoid interpreting a single test as definitive evidence of general performance.

A model should not be penalized for information it was explicitly not given unless the task requires it to retrieve that information.

---

# 21. Benchmark Design

A useful benchmark should contain a mixture of:

- straightforward cases;
- ambiguous cases;
- incomplete evidence;
- conflicting evidence;
- misleading evidence;
- source-independence cases;
- citation-verification cases;
- adversarial prompts;
- and cases where the correct response is to say **"the evidence is insufficient."**

The benchmark should not reward models merely for producing an answer.

It should reward models for producing an **appropriately supported answer**.

---

# 22. Regression Testing

When a model, prompt, rubric, retrieval system, or evaluation pipeline changes, previously tested cases should be rerun where practical.

Regression testing should look for:

- newly introduced hallucinations;
- increased confidence without increased evidence;
- citation degradation;
- changes in ambiguity handling;
- changes in instruction following;
- source-independence failures;
- and score instability.

A system should not be considered improved merely because its average score increased.

The **failure profile** also matters.

---

# 23. Quality Gates

An evaluation release should be reviewed before publication when it contains consequential claims.

Minimum quality gates:

- [ ] Sources are identifiable.
- [ ] Important citations have been checked.
- [ ] Claims are distinguished from evidence.
- [ ] Unsupported claims are flagged.
- [ ] Ambiguity is documented.
- [ ] Source independence has been considered.
- [ ] Model/version information is recorded.
- [ ] Rubric version is recorded.
- [ ] Major evaluation decisions are traceable.
- [ ] Sensitive information has been removed or protected.
- [ ] No secrets are present.
- [ ] Results have been reviewed for obvious evaluator bias or scoring inconsistencies.

---

# 24. Incident Response

Potential evaluation or security incidents include:

- leaked credentials;
- exposed private data;
- fabricated evidence discovered after publication;
- incorrect citations;
- corrupted datasets;
- benchmark contamination;
- scoring errors;
- or material evaluation methodology errors.

Response should generally follow:

1. **Identify** the incident.
2. **Contain** the affected material.
3. **Preserve** relevant evidence and logs.
4. **Assess** the scope and impact.
5. **Correct** the underlying issue.
6. **Document** the correction.
7. **Re-run** affected evaluations where necessary.
8. **Disclose corrections** when previously published results are materially affected.

Corrections should be transparent rather than silently rewritten.

---

# 25. Version Control & Change Management

Changes to:

- evaluation rubrics;
- datasets;
- prompts;
- scoring rules;
- evidence standards;
- model configurations;
- or audit methodology

should be version controlled.

A score produced under one rubric should not be presented as directly equivalent to a score produced under a materially different rubric without explanation.

---

# 26. Audit Trail

For important evaluations, preserve enough information for another reviewer to reconstruct the judgment.

A useful audit record may include:

```text
Evaluation ID:
Date:
Task:
Model:
Model Version:
Prompt Version:
Evidence Set:
Sources:
Claim Under Review:
Evidence Supporting Claim:
Evidence Against Claim:
Source Independence:
Model Response:
Detected Failure:
Severity:
Score:
Evaluator Reasoning:
Confidence:
Open Questions:
Final Status:
```

The audit trail should record **why** a judgment was made, not only the final score.

---

# 27. Evaluation Philosophy

This project treats evaluation as an investigation rather than a popularity contest.

The central questions are:

> **What does the evidence actually establish?**

> **What does the model claim?**

> **Where do those two diverge?**

> **What assumptions are required to bridge the gap?**

> **Would the conclusion survive if one source were removed?**

> **Is the apparent agreement between sources genuinely independent?**

> **Does the model know when it does not know?**

A strong evaluator does not reward an answer for being persuasive.

A strong evaluator tests whether the answer is **defensible**.

---

# 28. Security & Quality Standard

The project adopts the following default standard:

> **No claim should receive evidentiary credit merely because it is plausible, confidently stated, frequently repeated, professionally written, or supported by a citation that has not been checked.**

Evidence must be examined at the level of the actual claim.

When evidence is insufficient, the evaluation should preserve that uncertainty.

When evidence conflicts, the conflict should be documented.

When sources are dependent, that dependency should be recorded.

When the model is wrong, the evaluation should explain **how and why** it became wrong.

When the evaluator is uncertain, that uncertainty should also be visible.

---

# 29. Final Principle

## Evidence First. Claims Second. Confidence Last.

The objective of this project is not to make AI look intelligent.

It is to determine whether an AI system can produce conclusions that remain reliable when its claims are challenged against evidence.

**Accuracy matters.  
Grounding matters.  
Independence matters.  
Uncertainty matters.  
Human judgment matters.  
And the audit trail matters.**
