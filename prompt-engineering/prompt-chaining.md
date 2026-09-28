# Prompt Chaining

## Concept

Prompt chaining breaks a complex task into sequential stages where the output of one stage becomes useful input for another.

The goal is not to create more prompts for the sake of complexity. The goal is to give each stage a **clear job**.

### My analogy: a production line

I think of prompt chaining like a production line:

**Raw material → preparation → processing → quality check → finished product**

If one worker is asked to perform every operation simultaneously, errors become harder to isolate. A staged workflow makes intermediate results visible and easier to inspect.

---

## How I reason about a chain

Before creating a chain, I ask:

1. Is the task genuinely complex?
2. Are there distinct subtasks?
3. Does each subtask have a different objective?
4. Does one stage produce information needed by the next?
5. Where should verification happen?
6. Would chaining improve reliability, or just add unnecessary overhead?

This last question matters. **More steps do not automatically mean better prompting.**

---

## Practical example: AI response evaluation

Instead of asking:

> "Evaluate this AI answer."

I can separate the work:

### Stage 1 — Understand the task
Identify the user's actual request and constraints.

### Stage 2 — Extract evaluation criteria
Determine which dimensions matter: accuracy, relevance, completeness, reasoning, clarity, reliability, and instruction following.

### Stage 3 — Inspect the response
Check the answer against those criteria.

### Stage 4 — Diagnose
Identify specific errors, unsupported claims, omissions, or instruction-following failures.

### Stage 5 — Classify severity
Determine whether each issue is minor, major, or otherwise consequential according to the evaluation rubric.

### Stage 6 — Justify
Give evidence for the judgment instead of relying on a vague impression.

### Stage 7 — Produce the final evaluation
Present the result in the required format.

The value of this chain is that it separates **understanding, inspection, diagnosis, and reporting**.

---

## Practical example: research / investigation

For a research question, I can use:

**Question → clarify scope → gather evidence → compare sources → synthesize → identify uncertainty → answer**

This is especially useful when I do not want the model to jump straight from a question to a confident conclusion.

---

## What I learned

A useful chain should preserve important information between stages.

Bad chain:

> Prompt 1 → Prompt 2 → Prompt 3 → Prompt 4

without knowing why each step exists.

Better chain:

> **Task definition → targeted transformation → inspection → verification → final output**

Every arrow should have a reason.

---

## Failure modes

### 1. Unnecessary chaining
A simple task becomes slower and more complicated.

### 2. Information loss
An important constraint disappears between stages.

### 3. Error propagation
A wrong intermediate result becomes the foundation for later steps.

### 4. False confidence
Multiple agreeing model outputs can look like independent verification when they are not.

### 5. Over-engineering
The workflow becomes harder to maintain than the original task.

---

## My current rule

> **Chain when the task has meaningful stages that benefit from separation; do not chain merely because chaining sounds advanced.**

---

## Connection to evaluation

A chain should itself be evaluated.

I can ask:
- Did each stage perform its intended function?
- Did later stages receive the necessary context?
- Did the chain reduce errors?
- Where did an error first appear?
- Could one stage be removed without reducing quality?

This turns prompt chaining into an engineering problem rather than a formatting trick.
