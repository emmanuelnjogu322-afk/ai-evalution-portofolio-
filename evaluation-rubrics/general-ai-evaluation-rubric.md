# General AI Evaluation Rubric

A working framework I use to evaluate AI-generated responses. It is designed to make my judgments **consistent, evidence-based, and explainable** rather than based on whether an answer simply sounds good.

> This is a practical training rubric developed through my mock evaluations. It is not presented as an industry-standard universal rubric.

---

## Core evaluation dimensions

| Dimension | Core question | What I inspect |
|---|---|---|
| **Accuracy** | Are factual claims correct and supported? | False claims, incorrect numbers, misleading statements, unsupported factual assertions |
| **Relevance** | Does the response address the actual task? | Directness, task alignment, unnecessary tangents |
| **Completeness** | Are important requirements covered? | Missing constraints, omitted parts of the request, incomplete explanations |
| **Reasoning** | Do conclusions follow logically from evidence? | Logical gaps, unsupported inferences, contradictions, reasoning leaps |
| **Clarity** | Is the response understandable and structured? | Ambiguity, organization, wording, readability |
| **Reliability** | Does it distinguish facts, uncertainty, and unsupported claims? | Overconfidence, fabricated information, weak sourcing, failure to communicate uncertainty |
| **Instruction-following** | Did it respect explicit constraints? | Format, scope, requested method, exclusions, audience, length, other explicit requirements |

---

## How I evaluate

I use a sequence rather than jumping immediately to a score:

**1. Understand the task**  
What is the user actually asking for?

**2. Identify requirements**  
What must the response contain or avoid?

**3. Inspect the response**  
Look for factual, logical, relevance, completeness, clarity, reliability, and instruction-following issues.

**4. Verify important claims**  
Where appropriate, check sources, calculations, documents, or other evidence.

**5. Identify the failure**  
Describe the specific problem instead of using vague language such as "bad answer."

**6. Assess severity**  
Determine how materially the issue affects the response.

**7. Score and justify**  
A numerical score should be supported by observable evidence.

**8. Calibrate confidence**  
Ask whether my certainty is proportional to the evidence available.

---

## Scoring guidance

I commonly use a **1–5 scale** when a task calls for numerical scoring.

| Score | General interpretation |
|---:|---|
| **5** | Strong performance with no meaningful issue on this dimension |
| **4** | Good performance with limited weaknesses |
| **3** | Mixed or adequate performance with meaningful weaknesses |
| **2** | Poor performance with substantial weaknesses |
| **1** | Severe failure on the dimension |

### Important scoring rule

A score is **not the explanation**.

For example, saying:

> "Accuracy = 2/5"

does not explain the evaluation.

A stronger evaluation identifies:

> **what claim was problematic → what evidence is missing or contradictory → why that matters → why the issue warrants the score.**

---

## Severity classification

### Minor

A limited problem that does not materially undermine the overall task.

Examples:
- small omission
- minor wording issue
- limited imprecision
- formatting problem with little practical impact

### Major

A problem that materially affects correctness, completeness, reliability, reasoning, or task fulfillment.

Examples:
- important unsupported factual claim
- substantial omission
- incorrect interpretation of the user's request
- reasoning leap that changes the conclusion
- significant instruction-following failure

### Critical

A substantial failure with serious consequences or fundamental task breakdown.

Examples may include:
- dangerous misinformation in a high-stakes context
- instructions that could reasonably cause serious harm
- fabricated evidence presented as established fact where the consequence is substantial
- fundamental failure of a safety-critical task

Severity should be judged from the **actual task context**, not from the presence of a particular keyword.

---

## Evidence hierarchy in my evaluation process

When I identify a problem, I try to distinguish:

**Claim → Evidence → Context → Scope → Conclusion**

A response can contain a true statistic and still be misleading if it applies that statistic beyond the evidence's actual scope.

This became especially important in my remote-work productivity evaluations.

### Example

Weak reasoning:

> A study reports approximately 25% higher productivity → therefore remote workers are 25% more productive.

Better evaluation reasoning:

> What population was studied? What did "productivity" mean? What methodology produced the figure? Does the evidence justify generalizing the result to remote workers generally?

---

## Confidence calibration

I treat confidence as a separate consideration from correctness.

A response can be:
- correct but poorly justified,
- incorrect but confidently written,
- uncertain but appropriately qualified,
- or well-supported and appropriately confident.

I therefore ask:

> **Is the confidence level proportional to the evidence?**

This became a specific learning point in my response-ranking exercise.

---

## Common failure patterns I look for

### 1. Overgeneralization

**Specific evidence → broad claim → unjustified certainty**

### 2. Unsupported precision

A response gives an exact number without establishing where the number came from.

### 3. Fluency bias

The answer sounds professional, so it feels correct even though the evidence is weak.

### 4. Instruction drift

The response begins with the requested task but gradually answers a different question.

### 5. Reasoning leap

The conclusion does not adequately follow from the evidence presented.

### 6. Confidence-evidence mismatch

The response communicates greater certainty than the available evidence warrants.

### 7. Incomplete task fulfillment

The answer contains useful information but misses a requirement that materially matters.

---

## Evaluator self-check

Before finalizing an evaluation, I ask myself:

- Am I evaluating the **response**, or reacting to whether I personally like it?
- Can I point to concrete evidence for my judgment?
- Did I separate factual accuracy from writing quality?
- Did I distinguish an omission from an actual error?
- Did I verify important claims where necessary?
- Am I applying the same standard across responses?
- Is my severity classification proportional to the impact?
- Is my confidence justified?
- Could I explain my judgment to another evaluator and have them reproduce the reasoning?

---

## Rubric principle

> **Do not score the vibe. Score the evidence.**

The goal of this rubric is not to make every evaluation mechanically identical. It is to make my judgments **traceable, defensible, and consistent enough to inspect and improve**.

---

## Relationship to my mock evaluations

This rubric has been applied and refined through practice cases including:

- Remote-work productivity claims
- Response ranking and confidence calibration
- Evidence verification
- Other mock AI-response evaluation exercises documented in this repository

The rubric is therefore a **living methodology**. As I encounter new failure patterns, I can add them rather than pretending the framework is finished.
