# Evaluator Calibration Framework

**Status:** Working framework — built from portfolio evaluation practice

## Purpose

Calibration is the process of making sure an evaluator's numerical scores and severity judgments accurately reflect the problems identified in the written analysis.

The portfolio's first case study exposed an important lesson: an evaluator can correctly detect and explain serious weaknesses while still assigning scores that are more forgiving than the written criticism suggests.

## Core principle

> **The written criticism and the numerical score should tell the same story.**

A strong criticism should not be paired with a score that implies the response is mostly sound unless the evaluator can clearly justify that distinction.

## Calibration workflow

### 1. Detect
Identify the concrete problem in the AI response.

Examples:
- unsupported claim
- contradiction
- overgeneralization
- missing evidence
- poor instruction-following
- confidence that exceeds available evidence

### 2. Diagnose
Explain why the problem matters and what part of the response it affects.

### 3. Assess impact
Ask how materially the problem affects the answer's correctness, usefulness, reliability, or task fulfillment.

### 4. Assign severity
Classify the impact rather than reacting to how dramatic the wording sounds.

- **Minor** — limited impact
- **Major** — materially affects correctness, completeness, reliability, or task fulfillment
- **Critical** — substantial risk of serious misinformation, unsafe action, or fundamental task failure

### 5. Calibrate the score
Check whether the numerical score communicates the same level of weakness described in the reasoning.

Ask:

> "If someone only saw my score, would they understand the seriousness of the problem I just described?"

### 6. Challenge the score
For each important dimension, record what would justify:

- the current score
- one level higher
- one level lower

This helps prevent scores from being chosen by instinct alone.

## Evidence before severity

Severity should follow the evidence available for the evaluation. If a serious interpretation depends on an unverified premise, record that uncertainty instead of silently treating the premise as established fact.

For research-style evaluations, distinguish between:

- a claim being unsupported
- a source being unavailable or unverified
- a source being misrepresented
- an empirical claim being fabricated
- a claim being true in a narrow context but overgeneralized

These are related but not interchangeable failure modes.

## Reviewer disagreement

When external evaluators disagree, do not average their scores automatically.

First identify **why** they disagree:

- different assumptions
- different evidence
- different definitions
- different severity thresholds
- different interpretation of the task

Then make the final judgment independently and document the reasoning.

## Calibration record

For each revised evaluation, preserve:

1. Original evaluation
2. External feedback
3. Independent reevaluation
4. Score changes
5. Reason for each material change
6. Remaining uncertainty

This keeps the portfolio focused on genuine evaluator development rather than presenting only polished final answers.

## Current lesson from QA-EVAL-006

The first case study is being retained as a working evaluation because the evaluator identified important problems but later received feedback that some numerical judgments may have been too lenient relative to the written criticism.

A future V2 will test whether the calibration framework produces a more internally consistent evaluation.
