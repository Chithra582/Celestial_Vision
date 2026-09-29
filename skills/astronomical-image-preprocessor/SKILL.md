---
name: "astronomical-image-preprocessor"
description: "Normalize astronomical exposures, apply arcsinh dynamic range stretching, and remove optical detector noise."
---

# Astronomical Image Preprocessor Skill

## Overview
Prepares raw and compressed astronomical images for deep learning inference, applying domain-specific photometric scaling and optical noise suppression.

## Operations
1. Evaluates pixel intensity histograms and applies non-linear arcsinh / z-scale stretches.
2. Identifies and masks non-astronomical cosmic ray hits, dead pixels, and vignetting fringes.
3. Standardizes spatial resolutions using bi-cubic anti-aliased interpolation.
4. Generates data validation reports detailing signal-to-noise ratios ($S/N$) and background levels.
