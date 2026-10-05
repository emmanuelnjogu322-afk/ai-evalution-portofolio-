# Image Annotation — Day 2: Polygons, Masks & Keypoints

## Learning objective
Build practical understanding of polygon annotation, masks, keypoints, and how annotation schemas determine the correct tool and treatment of hidden points.

## Concepts learned

### 1. Bounding boxes
A bounding box is a rectangular annotation describing an object's location/extent.

**Core question:** What is the object and where is it?

### 2. Polygon annotation
A polygon uses multiple vertices to trace an object's visible boundary more precisely than a rectangle.

**Core idea:** A polygon represents a detailed boundary using connected points.

### 3. Masks
A mask represents the pixels/region assigned to an object or class. A polygon can be used as a boundary from which a filled mask is created.

**Important distinction:** Polygon = boundary representation; mask = pixel/region representation.

### 4. Keypoints
Keypoints are specific landmark coordinates, such as a person's nose, shoulder, elbow, wrist, knee, or ankle.

**Core idea:** A keypoint is a point/coordinate, not a polygon or pixel region.

For pose annotation, the schema may associate a keypoint with a visibility state such as visible or occluded. Exact states and encoding depend on the dataset.

## Semantic vs. instance segmentation

### Semantic segmentation
Assigns pixels to a class without requiring separate identities for different instances of the same class.

Example:
- Dog A + Dog B → both belong to the `dog` class.

### Instance segmentation
Separates individual objects into distinct masks even when they share the same class.

Example:
- Dog A → Mask 1
- Dog B → Mask 2

When objects overlap, instance segmentation is harder because the annotator must determine which pixels belong to each individual object.

## Occlusion vs. truncation

- **Occlusion:** part of an object/keypoint is hidden by another object within the scene.
- **Truncation:** part of an object extends beyond the image boundary and therefore was not captured.
- An object can potentially experience both.

### Keypoint-specific reasoning
If a task says to annotate keypoints and mark hidden keypoints as occluded, do not switch to polygons or segmentation. Keep the annotation primitive as a keypoint and follow the specified visibility rules.

If the instructions say **not to estimate hidden keypoint positions unless explicitly instructed**, do not infer coordinates from pose or surrounding pixels.

## Annotation taxonomy and instruction-following

Natural-language categories do not automatically equal dataset labels.

Example:
- In ordinary language, a motorcycle is a vehicle.
- A dataset may define `vehicle` to include motorcycles.
- Another dataset may use `motorcycle` as its own class.

Therefore:

> Dataset taxonomy + task instruction determine what should actually be annotated.

Likewise, a word such as **cyclist** should not automatically be interpreted as "person + bicycle" without checking the dataset's label definition.

## Assessment principles reinforced

1. Identify the annotation primitive first: box, polygon, mask, or keypoint.
2. Follow the annotation specification rather than relying on common-sense assumptions.
3. Do not estimate hidden coordinates unless the guidelines permit it.
4. Do not introduce a different annotation type to solve a problem.
5. Distinguish class identity from individual instance identity.
6. Distinguish occlusion from truncation.
7. Treat ambiguous cases according to the documented schema.

## JAAL learning notes

### Strong points
- Correctly identified keypoints as the required annotation type when instructed.
- Recognized that separate people require separate keypoint sets.
- Correctly identified a hidden wrist as an occlusion case.
- Correctly resisted estimating hidden keypoint positions without explicit permission.
- Recognized that polygon scope for a "cyclist" label depends on the dataset taxonomy.
- Correctly connected overlapping objects with the need for separate instance masks.

### Corrections made during the lesson
- A keypoint is a coordinate/landmark, not a polygon or pixel mask.
- Semantic segmentation does not require separate instance identities for objects sharing a class.
- Instance segmentation preserves individual object identities through separate masks.
- Occlusion is not the same as truncation.

## Current confidence
**Working understanding:** Good foundation, still requires visual practice.

### Next targets
- Polygon placement and boundary quality
- Mask quality
- Keypoint visibility states
- Occlusion/truncation in difficult visual cases
- Annotation errors and quality control
- Timed mock assessment

## Portfolio note
This learning log records reasoning, corrections, and uncertainty rather than claiming mastery. The objective is to demonstrate an iterative annotation-learning process and improve assessment readiness through deliberate practice.
