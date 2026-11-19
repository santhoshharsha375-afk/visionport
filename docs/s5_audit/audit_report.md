# VisionPort dataset audit

Annotation file : data\idd\annotations\instances.json
Image folder    : data\idd\images

## 1. Overview
Images: 3 | Annotations: 8 | Categories: 5
Images with no annotation: 0 []
Image sizes in the JSON: 1280x720 (3)

## 2. Class distribution
 id  class          count   share
  1  car                2   25.0%  ############
  2  motorcycle         2   25.0%  ############
  3  pedestrian         1   12.5%  ######
  4  bus                2   25.0%  ############
  5  truck              1   12.5%  ######
Imbalance ratio (largest / smallest class): 2.0 : 1
Rare classes (under 5% of annotations): none

## 3. Annotation validation
- duplicate annotation id: 6  e.g. annotation ids [1, 3, 4, 1, 3]

## 4. Image files and quality
- file missing: 0  e.g. image ids []
- file cannot be opened (corrupt): 0  e.g. image ids []
- size differs from the JSON: 0  e.g. image ids []
- too dark (mean brightness under 50): 0  e.g. image ids []
- blurry (sharpness under 100): 3  e.g. image ids [1, 2, 3]

## 5. Object size mix (COCO definition by pixel area)
small (under 32x32): 0 | medium (under 96x96): 0 | large: 8

## 6. Summary
Annotations with at least one problem: 3 of 8
Images with at least one problem     : 3 of 3
Suggested actions: remove or repair the flagged annotations, replace missing or corrupt images, review dark and blurry images by eye, and collect more examples of rare classes before training.
