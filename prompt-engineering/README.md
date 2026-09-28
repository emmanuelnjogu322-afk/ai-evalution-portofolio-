# Prompt Engineering — Learning Record

> A living record of my prompt-engineering development: concepts I learned, how I made sense of them, practical experiments, mistakes, and lessons I can reuse.

## Why this folder exists

I do not want prompt engineering to become a collection of copied definitions. I want evidence that I can **understand a prompting technique, explain it in my own words, apply it to a real task, inspect the result, and improve the prompt**.

This folder therefore records both concepts and practice.

---

## My learning model

My approach is based on four habits:

1. **Attempt first** — I try to solve or explain the problem before asking AI to finish it.
2. **Refine and test** — I use AI to challenge gaps, ambiguity, and weak assumptions.
3. **Explain back** — I restate the concept in my own words or with an analogy.
4. **Loop** — I apply the idea again in a new situation instead of treating one correct answer as mastery.

The goal is not prompt memorization. It is developing judgment about **what the model needs, what the task actually requires, and how to verify the result**.

---

## The 4Ds I use when prompting

### 1. Description
Describe the task clearly.

Instead of:
> "Explain this."

I should specify the subject, desired outcome, context, audience, constraints, and useful output format.

### 2. Delegation
Decide what work should be handed to the model and what remains my responsibility.

AI can draft, transform, compare, classify, brainstorm, or analyze. I still need to define the objective and judge whether the result is trustworthy.

### 3. Discernment
Inspect the response instead of automatically accepting it.

Questions I ask:
- Is the answer actually addressing the task?
- What assumptions did the model make?
- Are claims supported?
- Did it follow the constraints?
- Is confidence justified?

### 4. Diligence
Verify important claims and refine the process.

For factual or high-stakes work, I should use appropriate evidence, tools, or independent checks rather than treating fluent language as proof.

---

## My core analogy

### Prompt engineering as briefing a skilled assistant

A weak briefing might say:

> "Handle this."

A useful briefing tells the assistant:
- what the mission is,
- what context matters,
- what constraints exist,
- what the finished result should look like,
- and what must be checked before delivery.

The model's intelligence does not remove the need for a good briefing. Better task framing gives the model a better operating target.

---

## Prompt engineering is not just "writing a good prompt"

My understanding has shifted from:

**"Find the magic wording."**

toward:

**"Design a reliable interaction between the task, the model, the available context, the tools, and verification."**

That shift matters because the same wording can work well for one task and poorly for another.

---

## Techniques studied so far

- Prompt description and task framing
- Role prompting
- Prompt chaining
- Tool selection
- Iterative refinement
- Evaluation-oriented prompting
- Evidence and verification
- Distinguishing model fluency from factual reliability

---

## Practical progression

### Prompt chaining
I learned to break complex work into purposeful stages rather than asking one prompt to do everything at once.

Analogy:

> **A production line, not a single giant machine.**

Each stage should produce something useful for the next stage.

Example workflow for an AI evaluation task:

**Understand task → extract criteria → inspect response → identify errors → classify severity → justify judgment → produce final evaluation**

The important lesson is that chaining is useful when the stages have different purposes. More prompts are not automatically better.

### Tool selection
I learned that a prompt cannot compensate for using the wrong capability.

Analogy:

> **A toolbox. A hammer is not "bad" because it cannot measure a wall.**

The task determines the appropriate tool.

Examples:
- Current external facts → web/search
- Known document content → retrieval/file tools
- Arithmetic → calculator
- Structured datasets → data analysis
- Image/video understanding → vision or annotation capability

The question I now ask is:

> **"What capability materially improves correctness or task completion here?"**

---

## Evaluation connection

Prompt engineering and AI evaluation reinforce each other.

A prompt can be technically clear but still produce an unreliable answer. Evaluation asks whether the resulting answer actually satisfies the task.

My evaluation dimensions include:
- accuracy
- relevance
- completeness
- reasoning quality
- clarity
- reliability
- instruction following
- severity of errors

This makes prompting a feedback loop:

**Prompt → Output → Inspect → Diagnose → Refine → Re-test**

---

## My practical learning principle

> **Do not optimize the prompt before understanding the task.**

I first ask:
1. What is the actual objective?
2. What information does the model need?
3. What constraints matter?
4. What could go wrong?
5. What evidence or tool is appropriate?
6. How will I know the answer is good?

Only then do I optimize the wording.

---

## Current development status

My study progressed through the Prompt Engineering curriculum into **Prompt Chaining** and **Tool Selection**, with practical question-based exercises.

I have also started connecting prompting with AI response evaluation. This is important because my goal is not only to make AI produce better-looking answers; it is to develop the judgment required to determine whether those answers are actually useful and trustworthy.

---

## What I am still improving

- Choosing between one strong prompt and a multi-step chain
- Designing useful intermediate outputs
- Knowing when a tool adds real value
- Reducing unnecessary prompt complexity
- Making verification explicit
- Testing prompts against edge cases
- Separating confidence from evidence
- Avoiding over-reliance on fluent model output

---

## Evidence of practice

This repository is intended to grow with actual exercises rather than become a static notes page. Future entries should record:

- the task
- my initial approach
- the prompt or prompt sequence
- the model output
- what worked
- what failed
- how I revised the approach
- what I learned
- how I would test it again

That structure makes the portfolio demonstrate **applied prompt-engineering judgment**, not just familiarity with terminology.
