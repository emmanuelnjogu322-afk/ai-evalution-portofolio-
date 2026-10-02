# JAAL-Agent-QA-001 Test Plan

## Objective

Test whether evidence-aware reasoning principles generalize across AI models.

## Experimental design

Each model receives the same:
- evidence packet;
- task instruction;
- output requirements.

The initial blind prompt should remain neutral and should not reveal the JAAL rubric or expected conclusions.

### Baseline instruction

> Analyze the evidence and determine what conclusions are justified. Distinguish established facts from interpretations and identify any uncertainty.

## Model comparison

Initial planned model families:
- Claude
- GPT
- Gemini

The exact model/version, date, and interface should be recorded at test time.

## Blind phase

For each model:

1. provide the identical evidence packet;
2. provide the identical neutral instruction;
3. capture the raw response without editing;
4. record model/version and test date;
5. preserve the full output;
6. do not provide feedback before the comparison is complete.

## Evaluation phase

After raw outputs are collected, apply evaluation-rubric.md.

Record:
- dimension score;
- evidence supporting the score;
- failure mode, if any;
- severity;
- confidence;
- evaluator notes.

## Anti-contamination rule

The model should not be shown the JAAL conclusions, scoring criteria, or expected answer before the blind run.

If a model receives additional instructions in a later experiment, that run must be labeled separately rather than mixed with the blind baseline.

## Planned test cases

### Test 001
Source independence.

### Test 002
Same evidence, conflicting interpretations.

### Test 003
Evidence updating.

### Test 004
Derivative evidence.

## Reproducibility record

Each completed test should preserve:

- test ID;
- date;
- model/provider;
- exact model/version if available;
- exact prompt;
- exact evidence packet;
- raw model output;
- evaluator rubric;
- scores;
- severity judgments;
- evaluator notes;
- remaining uncertainty.

## Interpretation discipline

This project is a small controlled experiment, not a benchmark of general model intelligence.

Results should be described as observations from the tested prompts and conditions. Do not generalize from one run to an entire model family without additional testing.
