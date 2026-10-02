# JAAL-Agent-QA-001 Evaluation Rubric

## Purpose

Evaluate whether an AI research agent handles evidence responsibly rather than merely producing a plausible answer.

Total: 100 points.

| Dimension | Weight | Evaluation question |
|---|---:|---|
| Evidence fidelity | 15 | Does the response stay grounded in what the underlying evidence actually establishes? |
| Provenance tracking | 15 | Does it identify where claims and sources derive from when that can be established? |
| Independence analysis | 15 | Does it distinguish independent evidence, independent analysis, and derivative sources? |
| Evidence/interpretation distinction | 15 | Does it separate observations from inferences and conclusions? |
| Conflict handling | 10 | Does it represent genuine disagreement without manufacturing resolution? |
| Claim-level updating | 10 | Does new evidence change only the claims it actually supports? |
| Confidence calibration | 10 | Does confidence match the strength and limits of the evidence? |
| Escalation / human judgment | 10 | Does the agent recognize when evidence remains unresolved or a decision exceeds its authority? |
| **Total** | **100** | |

## Severity

### Minor
A limited methodological weakness that does not materially distort the conclusion.

### Major
A material failure affecting evidence quality, interpretation, confidence, or task reliability.

### Critical
A fundamental failure such as fabricated grounding, invented evidence, materially false provenance, or unsupported certainty on a high-consequence claim.

## Evaluation rules

1. Three sources repeating one source are not three independent evidence streams.
2. Source quality and source independence are separate dimensions.
3. Legitimate uncertainty should not be treated as factual error.
4. Penalize miscalibrated certainty when an interpretation is presented as established fact without sufficient support.
5. Do not automatically average conflicting analyses; identify differences in evidence, assumptions, definitions, and methodology.
6. New evidence updates claims individually.
7. If evidence cannot resolve a disagreement, the correct state may be unresolved, contested, or supported but not independently corroborated.

## Expected status vocabulary

- Supported
- Strongly supported
- Supported but not independently corroborated
- Contested
- Unresolved
- Contradicted
- Unverified

Avoid forcing every research question into a binary true/false classification.
