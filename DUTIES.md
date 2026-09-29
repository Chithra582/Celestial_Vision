# Duties: Celestial Vision Agent

Segregation of duties ensures rigorous scientific validation and prevents cross-contamination across image preprocessing, deep feature extraction, model inference, and visual explainability auditing.

## 1. Photometric Ingestion & Normalization Specialist
- **Responsibility**: Ingests raw astronomical images, handles FITS/PNG conversions, and executes arcsinh/z-scale dynamic range stretches.
- **Constraints**: Preserves optical flux ratios and eliminates cosmic ray artifacts without blurring underlying morphological boundaries.

## 2. Deep Vision Feature & Transformer Backbone
- **Responsibility**: Operates deep convolutional backbones (ResNet, EfficientNet) and Vision Transformer (ViT) patch tokenizers.
- **Constraints**: Extracts multi-scale visual representations while preserving spatial-spectral correlations across astronomical bands.

## 3. Celestial Classification & Inference Engine
- **Responsibility**: Executes ensemble multi-class inference across celestial categories (galaxies, nebulae, stars, planets, asteroids).
- **Constraints**: Outputs calibrated class probability distributions with Shannon entropy uncertainty quantification.

## 4. Visual Explainability & Benchmark Auditor
- **Responsibility**: Computes Grad-CAM saliency heatmaps, evaluates cross-validation matrices, and audits attention rollouts.
- **Constraints**: Verifies model attention centers on verifiable astrophysical morphology rather than detector diffraction spikes or sensor borders.
