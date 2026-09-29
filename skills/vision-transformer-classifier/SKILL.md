---
name: "vision-transformer-classifier"
description: "Classify celestial objects into morphological categories using Vision Transformers and deep ensemble backbones."
---

# Vision Transformer Classifier Skill

## Overview
Executes deep learning classification workflows to categorize celestial objects into galaxies, nebulae, stars, planets, and asteroids.

## Operations
1. Computes multi-head self-attention over patch sequences to capture global morphological structure.
2. Emits calibrated class probability distributions over target celestial categories.
3. Evaluates top-1 and top-3 accuracy, macro F1, and precision-recall metrics.
4. Generates attention rollout matrices and Grad-CAM saliency visualizations.
