# Image Annotation Learning Log — Day 1

**Date:** 2026-09-28  
**Focus:** Image annotation fundamentals  
**Status:** Foundational skills in progress  
**Learning method:** Attempt first → reason aloud → receive correction → explain back

## Objective

Build practical understanding of image-annotation terminology and decision-making for AI/ML data annotation assessments. The immediate focus is image annotation, with video annotation to be developed as a separate skill area.

## Concepts covered

### 1. Classification
Core question: **What is present?**

Typical output is a class label, such as:
- `dog`
- `cat`

Important correction:
The number of objects or visual features does **not** determine whether a task is classification. The task instruction determines what output is required.

### 2. Object detection
Core question: **What is present + where is it?**

Typical output:
- Object class
- Bounding box around each relevant object instance

Important correction:
A bounding box is normally drawn around each relevant object, not around the whole image. Multiple objects of the same class receive separate boxes when they are separate instances.

### 3. Segmentation
Core idea: identify the pixels belonging to an object or class.

Important correction:
Segmentation is not simply choosing convenient geometric shapes such as circles or rectangles. The annotation follows the object's actual visible boundaries/pixels according to the dataset's rules.

### 4. Class vs. instance

**Class = what kind of object?**  
Example: `car`

**Instance = which individual object?**  
Example:
- Car A = one instance
- Car B = another instance

A scene can therefore contain:
- 1 class: `dog`
- 5 instances: Dog 1 through Dog 5

This distinction becomes especially important in instance segmentation.

### 5. Occlusion
**Occlusion = part of an object is hidden by another object.**

Example:
A dog is behind a car and only part of the dog is visible.

### 6. Truncation
**Truncation = part of an object extends beyond the image boundary.**

Example:
A dog is at the edge of a photograph and part of its body falls outside the captured frame.

A single object can potentially be both occluded and truncated when both conditions occur.

### 7. Semantic segmentation
Core question:

> **Which pixels belong to each class?**

Different instances of the same class do not need separate instance identities.

Example:
- Dog A and Dog B are both assigned to the `dog` class.

### 8. Instance segmentation
Core question:

> **Which pixels belong to each individual object?**

Example:
- Dog A → Mask A
- Dog B → Mask B

The masks remain separate even though both objects belong to the same class.

## Key assessment principles learned

1. **Task specification controls annotation scope.**  
   Annotate what the instructions require, not every visible object.

2. **Dataset taxonomy controls labels.**  
   A real-world category does not automatically equal a dataset label. The annotation taxonomy must be checked.

3. **Do not infer unseen information without guidance.**  
   In ambiguous cases, consult the annotation guidelines instead of assuming what is outside the visible evidence.

4. **Small does not automatically mean ignorable.**  
   A small object may still be annotated when it is visible and identifiable, unless the dataset specifies a minimum size or other exclusion rule.

5. **Occlusion and truncation are different.**  
   Hidden by another object = occlusion. Cut off by the image boundary = truncation.

6. **Semantic vs. instance segmentation is about identity.**  
   Semantic segmentation groups pixels by class. Instance segmentation preserves the identity of each object instance.

7. **Guidelines determine edge cases.**  
   Questions involving partial visibility, hidden parts, minimum size, or estimated object extent should be resolved using the dataset's specification.

## Corrections from today's practice

### Initial misconception
I initially associated classification with images containing fewer features/objects.

### Correction
The annotation task—not the number of features—determines whether classification, detection, or segmentation is required.

### Initial segmentation misconception
I described segmentation using simple shapes that could fit an object.

### Correction
Segmentation follows the object's relevant pixel boundaries; the exact policy depends on the annotation specification.

### Important distinction reinforced
I initially mixed the idea of separate object identity into semantic segmentation.

### Correction
Semantic segmentation labels pixels by class without requiring separate identities for different instances of the same class. Instance segmentation explicitly separates those instances.

## Practical reasoning examples

### Example A — Animal bounding boxes
Scene:
- Dog
- Cat
- Car
- Tree
- Grass

Instruction:
> Annotate every animal and vehicle.

Expected relevant instances:
- Dog
- Cat
- Car

Expected bounding boxes:
- 3

Tree and grass are outside the annotation scope.

### Example B — Occlusion
A dog is partly hidden behind a car.

Result:
- Dog remains a candidate for annotation if the task requires animals.
- The dog is occluded.
- The exact box policy for hidden portions depends on the dataset guidelines.

### Example C — Truncation
A dog is cut off by the edge of the photograph.

Result:
- The dog is truncated.
- The missing portion is not necessarily hidden by another object.

## Current skill assessment

Self-assessed confidence before starting this training: **~80% overall**.

Current interpretation:
- Image annotation fundamentals are becoming clearer.
- Main area for continued polishing: applying terminology consistently under ambiguous visual conditions.
- Video annotation remains a separate training target.

## Next learning targets

- Polygon annotation
- Masks and annotation boundaries
- Keypoint / landmark annotation
- More difficult occlusion cases
- Ambiguous and borderline objects
- Annotation quality control
- Video annotation and temporal consistency
- Mock image/video assessment drills

## Evidence of learning

Today's work demonstrates the ability to:
- Distinguish class from instance.
- Identify occlusion vs. truncation.
- Distinguish classification, object detection, semantic segmentation, and instance segmentation at a conceptual level.
- Apply task-specific annotation scope.
- Recognize when annotation guidelines are required before making an edge-case decision.

> **Principle:** Don't guess the dataset's rules. Read the specification, then apply it consistently.
