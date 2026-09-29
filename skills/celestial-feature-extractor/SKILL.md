---
name: "celestial-feature-extractor"
description: "Extract multi-scale visual representations and patch embeddings from astronomical image tensors."
---

# Celestial Feature Extractor Skill

## Overview
Decomposes astronomical images into high-dimensional feature embeddings using convolutional feature hierarchies and Vision Transformer tokenizers.

## Operations
1. Partitions images into $16 \times 16$ pixel spatial patches with linear projection embeddings.
2. Extracts multi-scale visual feature maps across convolutional residual stages.
3. Analyzes surface brightness radial profiles and isophotal contours.
4. Preserves spectral-band correlations across multi-wavelength astronomical exposures.
