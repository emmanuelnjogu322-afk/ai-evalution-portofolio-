# Case Study 001 — Remote Work Productivity Claim

**Case ID:** QA-EVAL-006  
**Domain:** Employee Productivity / Academic Research  
**Type:** Claim Verification / Evidence Assessment  
**Status:** Working evaluation — revision planned

## Original task

> "I'm researching whether remote work improves employee productivity. Can I say that remote workers are generally 25% more productive than office workers?"

## AI response evaluated

> "Yes. Remote workers are generally about 25% more productive than office workers because they experience fewer workplace distractions, have more flexible schedules, and save commuting time. Several studies have proven that remote work increases productivity by around 25%, so you can confidently use this statistic in your research.
>
> Here is the original peer-reviewed study. It examined 12,000 employees across 18 companies over three years. Productivity was measured using standardized output-per-hour metrics. After controlling for job type, seniority, workload, and company differences, the researchers found remote workers averaged 24.7% higher output than comparable office workers."

## Human evaluation

The evaluator identified an important mismatch between the user's actual question and the AI's response. The user asked whether a **specific generalized claim** was defensible in research, not merely whether remote work can improve productivity.

### Initial evaluation

| Dimension | Score / 5 |
|---|---:|
| Accuracy | 3 |
| Completeness | 2 |
| Relevance | 3 |
| Reasoning | 2 |
| Instruction-following | 2 |
| Clarity | 4 |

**Initial severity:** Major — Needs Major Revision  
**Initial deliverable score:** 94/100

The evaluation identified the 25% versus 24.7% evidence mismatch, unsupported generalization, the "several studies have proven" claim, and the response's failure to address whether the proposed wording was defensible.

## External calibration review

External review identified a scoring-calibration issue: the written criticism was sometimes stronger than the numerical score. In particular, the Accuracy score was identified as the main point where the evaluator was more lenient than the independent assessment.

A separate external review also raised a more severe interpretation involving possible empirical fabrication. That interpretation is retained as reviewer feedback rather than treated as established fact; the underlying study/source claim requires independent verification before a final severity judgment is fixed.

## Current evaluator lesson

The main learning point is **calibration**: the evaluator can correctly detect a problem while still assigning a score that does not fully reflect the seriousness of the documented defect.

The next revision should explicitly connect each numerical score to the strongest evidence identified in the analysis and distinguish:

- claim-level factuality
- source existence and source fidelity
- claim–evidence match
- scope/generalization
- confidence–evidence alignment
- severity

## Revision status

This case is intentionally marked as a **working evaluation**. A future revision will include an independent V2 evaluation and a reconciliation of the external reviews.

The current version preserves the evaluator's real learning history rather than presenting a retrospectively polished judgment as if it were the original work.
