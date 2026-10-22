# Annotation Quality Assurance — Case Study 001

**Focus:** Image annotation QA, error classification, severity calibration, and evidence discipline  
**Artifact type:** Constructed practice case study  
**Status:** Methodology draft documented; real-image validation not yet completed  
**Scope:** Image annotation, with a proposed extension to video annotation

> **Integrity note:** This is a simulated case study created to demonstrate a structured quality-assurance approach. It does not use a real annotation submission or an inspected source image. The scenario, records, and findings below are hypothetical. The task rules are illustrative and are not represented as Turing's or any other platform's official guidelines.

## 1. Purpose

This case study demonstrates how I would review an annotation submission against a defined task specification, distinguish confirmed errors from possible issues, assess impact proportionately, and record what evidence is still needed.

The goal is not to claim production annotation experience or measured accuracy. It is to make the review process transparent and repeatable.

## 2. Illustrative task specification

For this constructed scenario, assume the task instructions say:

- Annotate every visible instance of a **person** and a **car**.
- Use one bounding box per visible instance.
- Follow the task's rules for partially visible objects.
- Do not infer attributes or objects that are not visually supported.
- If an instance or label cannot be resolved from the available visual evidence, follow the task's uncertainty or escalation procedure.
- Apply the same inclusion and localization rules consistently across the image.

These rules are examples for this exercise only. In real work, the active project guidelines and taxonomy take precedence.

## 3. Constructed scenario

Imagine a hypothetical image containing two visible people and one car. A hypothetical annotation record contains a box for Person A and a box for the car, but no record for Person B. The car box may also include substantial irrelevant background. A separate label decision is described as uncertain.

No source image, actual coordinates, annotation export, or ground-truth label set was provided for this case. Therefore, none of the potential defects can be independently confirmed here.

| Review item | Hypothetical observation | Current evidence status |
|---|---|---|
| Person B | The imagined submission omits a second visible person | Simulated only; unverified |
| Car box | The imagined box may include substantial background | Simulated only; unverified |
| Uncertain label | A label decision may not be sufficiently supported by visible evidence | Simulated only; unverified |

## 4. Potential findings and review decisions

### Finding A — Possible missed instance

**Potential error category:** Omission / false negative

**Why it matters:** If the task requires every visible person and Person B is clearly within scope, omitting that instance would make the annotation incomplete.

**QA procedure:**
1. Inspect the actual image and confirm that the instance is visible.
2. Check the task's inclusion rules, including any minimum visibility or exclusion criteria.
3. Confirm that the object belongs to the required taxonomy.
4. Add the annotation only if the visual evidence and active instructions support it.
5. Record the evidence and final disposition.

**Provisional severity:** Could be major if the omission is confirmed and materially affects task completeness; the final level depends on the project's severity rubric and downstream impact.

**Disposition:** Unresolved. No image or real submission was inspected, so this is not a confirmed false negative.

### Finding B — Possible localization defect

**Potential error category:** Bounding-box localization / excess background

**Why it matters:** A box that includes too much background may violate the project's localization rules and reduce label precision. The seriousness depends on the actual box, the object's shape and visibility, and the permitted tolerance.

**QA procedure:**
1. Compare the proposed box with the visible object and the task's box-placement rules.
2. Check whether the box crosses the project's allowed localization tolerance.
3. Correct the box if a defect is confirmed.
4. Record the reason for the correction rather than relying on visual intuition alone.

**Provisional severity:** Could be minor or major depending on the magnitude of the error and the task's acceptance criteria.

**Disposition:** Unresolved. There are no real coordinates or pixels available for inspection.

### Finding C — Label decision with insufficient evidence

**Potential error category:** Possible unsupported classification

**Why it matters:** An annotation should reflect the visible evidence and the defined taxonomy, not a guess about what an object might be.

**QA procedure:**
1. Reinspect the visible features relevant to the proposed label.
2. Compare the evidence with the project's taxonomy definitions.
3. If the label is supported, retain it and record the basis when required.
4. If it is not supported, correct it according to the instructions.
5. If the evidence remains ambiguous, use the prescribed uncertainty or escalation path.

**Provisional severity:** Undetermined until the label, visual evidence, task rules, and likely impact are known.

**Disposition:** Unresolved. Uncertainty alone is not proof that a label is wrong.

## 5. Illustrative severity framework

The following is a proposed portfolio framework, **not an official Turing rubric or a universal industry standard**. The actual project rubric should always override it.

| Level | Working definition | Example in principle |
|---|---|---|
| Minor | A limited defect with low impact that does not materially undermine the record | A small localization inconsistency within otherwise acceptable work, if the task's tolerance and policy classify it as minor |
| Major | A defect that materially reduces completeness, correctness, or usability | A confirmed omission of an in-scope object, where completeness is central to the task |
| Critical | A defect that makes the output unusable or creates a serious downstream risk under the applicable policy | A widespread or systematic failure that invalidates a batch, if the project's criteria define that impact as critical |

Severity should be justified by the task requirements, the extent of the defect, and its likely impact—not by dramatic wording. A reviewer should not assign a definitive level when key evidence is missing.

## 6. Repeatable QA workflow

1. **Read the active instructions.** Identify the required classes, instance rules, visibility criteria, permitted annotation types, and escalation path.
2. **Check coverage.** Compare the visible in-scope instances with the submitted annotations.
3. **Check class correctness.** Confirm that each label matches the visible evidence and allowed taxonomy.
4. **Check geometry.** Inspect box or mask placement against the project's localization rules.
5. **Check consistency.** Apply the same rules to comparable objects throughout the sample.
6. **Classify each issue.** Separate omissions, incorrect labels, localization defects, duplicates, and unresolved cases.
7. **Assess severity.** Use the project's rubric; document the impact and rationale.
8. **Record evidence and action.** Preserve the relevant visual reference, guideline version, correction, and final status where the workflow permits.
9. **Escalate uncertainty.** Do not invent details to force a confident answer.
10. **Recheck corrections.** Verify that a fix resolves the issue without introducing a new one.

## 7. Video annotation: proposed extension

For video tasks, the same evidence-first approach can be extended to additional checks:

- **Temporal coverage:** Are relevant events represented across the required interval?
- **Action accuracy:** Does the label describe the action actually visible?
- **Temporal consistency:** Do labels remain consistent while an object or action continues?
- **Timestamps and boundaries:** Do event start/end times follow the task's tolerance rules?
- **Transitions and scene changes:** Are relevant changes captured when the instructions require them?
- **Visibility changes:** Are occlusion, truncation, entry, and exit handled according to the guidelines?
- **Evidence discipline:** Are descriptions limited to what the frames support?

These are proposed validation targets, not completed video tests or claims of measured performance.

## 8. Suggested audit record

For a real practice task, I would maintain a record with fields such as:

| Field | Purpose |
|---|---|
| Sample ID | Identifies the image or clip without exposing unnecessary personal data |
| Task and guideline version | Establishes which instructions govern the review |
| Expected output | Defines the requirement against which the submission is checked |
| Submitted output | Records what was actually annotated |
| Visual evidence | Points to the relevant object, region, frame, or timestamp |
| Error category | Makes the issue type explicit |
| Severity and rationale | Connects impact to the applicable rubric |
| Corrective action | States the change made or recommended |
| Final status | Confirmed, corrected, accepted, or unresolved |
| Reviewer notes | Captures limitations and any escalation decision |

For an actual exercise, this record should be populated from the image or clip and the real annotation output. Hypothetical details must not be entered as observed results.

## 9. Results and limitations

This artifact documents a proposed review method and shows how potential annotation defects could be assessed without overstating the available evidence.

It does **not** establish:
- Professional or paid annotation experience.
- Accuracy on a real image or video dataset.
- A validated inter-annotator agreement score.
- A measured error rate or reduction in errors.
- Proficiency with a particular commercial annotation platform.
- Compliance with a platform's private or unpublished guidelines.

The three scenario findings remain hypothetical and unresolved because no source image or annotation record was supplied.

## 10. Validation plan

The next step is to run a small, clearly labelled practice exercise using a legally usable image and a written task specification:

1. Select an image whose use is permitted and define a narrow taxonomy.
2. Record the exact annotation rules before annotating.
3. Create the annotation output using an available tool or a documented manual method.
4. Review object coverage, class choices, and geometry against those rules.
5. Record only defects that can be demonstrated from the image and annotation output.
6. Separate confirmed errors from uncertain decisions.
7. Correct the output and document the reason for each change.
8. Repeat with a short video only after the image exercise has a complete evidence trail.

Only after this exercise is actually completed should the portfolio add screenshots, annotation examples, counts, or performance metrics.

## Closing principle

**Good annotation QA is accurate, guideline-led, reproducible, and honest about uncertainty.** The reviewer should be able to trace each finding to visual evidence and a task rule—and should be equally clear when the available evidence is not enough to decide.
