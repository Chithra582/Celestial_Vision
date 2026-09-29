---
name: "multispectral-uncertainty-evaluator"
description: "Compute prediction entropy, detect blended sources, and flag optical anomalies for human astronomer review."
---

# Multispectral Uncertainty Evaluator Skill

## Overview
Evaluates classification reliability across astronomical exposures, quantifying prediction entropy and detecting anomalous celestial candidates.

## Operations
1. Computes Shannon entropy over class probability vectors to identify ambiguous morphology.
2. Detects overlapping or blended celestial sources in crowded astronomical fields.
3. Flags optical artifacts, telescope diffraction spikes, and saturated stellar halos.
4. Compiles visual explainability dossiers for astronomer-in-the-loop verification.
