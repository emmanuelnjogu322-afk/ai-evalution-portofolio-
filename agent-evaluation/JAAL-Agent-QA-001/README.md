# JAAL-Agent-QA-001 — Evidence-Aware Agent Evaluation

## Status

Foundation phase. Live model testing has not yet been conducted.

## Research question

> Can an AI research agent reason responsibly about evidence, provenance, interpretation, uncertainty, and conflicting conclusions?

This project extends the portfolio from evaluating AI responses to evaluating AI agent behavior when reasoning over evidence.

## Core model

The evaluation traces:

**source → provenance → underlying evidence → analysis → interpretation → conclusion → confidence**

The agent should not treat a polished conclusion as sufficient. It must preserve the distinction between what the evidence establishes, what a researcher infers, and what remains unresolved.

## Initial test sequence

### Test 001 — Source Independence

Tests whether an agent distinguishes:
- multiple sources from independent evidence;
- reliable sources from independent sources;
- derivative reporting from genuinely separate evidential paths.

### Test 002 — Same Evidence, Conflicting Interpretations

Tests whether an agent can:
- identify shared underlying evidence;
- separate evidence from interpretation;
- represent competing analyses accurately;
- avoid selecting a winner without sufficient support;
- preserve unresolved disagreement.

### Test 003 — Evidence Updating

Tests whether new evidence changes only the claims it actually supports.

### Test 004 — Derivative Evidence

Tests whether an apparently new source adds genuinely new evidence or merely repeats an earlier source through a new interpretation.

## Working principles

1. Source count is not evidence count.
2. Source quality and source independence are separate dimensions.
3. Evidence and interpretation are not interchangeable.
4. Independent analyses can disagree while using the same underlying evidence.
5. New evidence should update confidence at the claim level.
6. New wording is not automatically new evidence.
7. Unknown should not become verified through inference.
8. Uncertainty is not itself an error; miscalibrated certainty is.
9. When evidence remains unresolved, the agent should preserve the uncertainty.
10. Human review is required when the remaining judgment exceeds the agent's authority.

## Research discipline

The live model phase will use the same evidence packet and neutral task instructions for each model tested.

The models will not be given the JAAL conclusions or rubric in advance. The rubric will be applied after collecting the raw outputs.

This separation is intended to distinguish the model's unaided evidence reasoning from compliance with an evaluator-provided rubric.

## Authenticity

This is an experimental learning project. Results will be recorded as observed model behavior, not presented as evidence of professional experience or universal model capability.
