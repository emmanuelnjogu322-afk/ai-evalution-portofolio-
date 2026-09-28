# Tool Selection

## Concept

Tool selection means matching a task to the capability that can perform it reliably.

A prompt is not a substitute for a missing capability.

### My analogy: a toolbox

If I need to measure a wall, I reach for a tape measure.

If I need to drive a screw, I reach for a screwdriver.

I do not ask whether the screwdriver is "good enough at measuring." I ask whether it is the correct tool for the task.

The same principle applies to AI systems.

---

## Capability → task matching

| Task requirement | Appropriate capability |
|---|---|
| Current or externally verifiable information | Web/search |
| Information already contained in a known document | Retrieval/file tools |
| Arithmetic or numerical transformation | Calculator |
| Structured quantitative analysis | Data analysis |
| Image understanding | Vision/image capability |
| Audio transcription | Speech-to-text |
| Repetitive external action | Appropriate automation/API/tool |

The exact tools available depend on the system, but the reasoning principle remains the same.

---

## My decision test

Before selecting a tool, I ask:

1. What information or action does the task require?
2. Can the model answer reliably from the context already available?
3. Is the information current?
4. Does the task require external evidence?
5. Is there a specialized capability that reduces error?
6. What is the cost of using the tool?
7. How will I verify the tool's result?

The key phrase for me is:

> **"Does this tool materially improve correctness, evidence quality, or task completion?"**

---

## Practical example: factual research

If I am investigating a historical claim and the answer depends on sources, relying only on model memory is weaker than retrieving and comparing evidence.

A better workflow is:

**Define claim → identify needed evidence → retrieve sources → compare → note uncertainty → synthesize**

The tool is useful because it changes the evidence available to the reasoning process.

---

## Practical example: arithmetic

If the task is:

> Calculate a date 90 days after a given date.

I do not need elaborate prompting. A calculator/date capability is more reliable and faster.

This taught me an important lesson:

> **Good prompt engineering sometimes means knowing when not to prompt harder.**

---

## Tool selection and verification

Using a tool does not automatically make an answer correct.

A search result can be outdated.
A retrieved document can be incomplete.
A calculator can receive the wrong input.
A data query can use the wrong population or grain.

Therefore:

**Tool → result → validation**

is more reliable than:

**Tool → blindly trust result**

---

## Tool selection versus prompt chaining

These techniques solve different problems.

### Prompt chaining
Breaks **one complex task** into useful stages.

### Tool selection
Chooses the **capability** needed for a particular task.

They can work together:

**Define task → select tool → process result → verify → continue chain**

---

## Current lesson

I am learning to think of AI systems as more than a text box.

The useful question is not:

> "How do I write a cleverer prompt?"

It is:

> **"What combination of instructions, context, tools, and verification gives this task the most reliable path to completion?"**

That shift connects prompt engineering directly to AI evaluation and quality assurance.
