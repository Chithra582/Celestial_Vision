# EXPLAINABILITY — Celestial Vision Agent

> **Admissibility & Transparency Report for OpenGAP / Agent Passport**  
> *Agent Name:* Celestial Vision Agent (`celestial-vision-agent`)  
> *Specification:* OpenGAP v0.1.0  
> *Domain:* Data & Analytics / Computer Vision & Astronomical Image Classification  

---

## 1. Overview & Scientific Purpose

Celestial Vision Agent is an autonomous computer vision intelligence, deep learning model auditor, and celestial object classification pipeline built for astronomical research. The underlying system operates across astronomical image datasets—including the curated **SpaceNet** benchmark—spanning thousands of labeled exposures across celestial object categories: galaxies, nebulae, stars, planets, and asteroids.

The agent's primary scientific purpose is to automate high-throughput morphological classification of celestial objects captured by wide-field survey telescopes. By deploying state-of-the-art Convolutional Neural Networks (CNNs) and Vision Transformers (ViT) equipped with attention-rollout explainability, the agent assists astrophysicists in parsing petabyte-scale sky surveys, detecting optical transients, and categorizing rare cosmological structures without manual inspection fatigue.

---

## 2. How the Agent Decides (Decision-Making Logic)

Celestial Vision Agent operates across a deterministic, multi-stage computer vision decision pipeline that grounds every prediction in verifiable morphological features:

```
[Astronomical Image Exposure] ──> [Photometric Scaling & Noise Gate] ──> [Patch Tokenization & Feature Extraction]
                                                                                               │
                                                                                               ▼
[Attribution Map & Verified Catalog Entry] <── [Entropy & Anomaly Filter] <── [Multi-Class ViT Classifier]
```

### 2.1 Astronomical Image Normalization & Optical Preprocessing
- **Decision:** Determines optimal photometric dynamic range stretching and removes detector artifacts before feature ingestion.
- **Rules:**
  - Evaluates pixel value distributions; applies non-linear arcsinh or z-scale stretches to reveal low-surface-brightness nebulosity without saturating stellar cores.
  - Detects and masks non-astronomical sensor artifacts: cosmic ray strikes, hot pixels, and optical vignetting fringes.
  - Standardizes spatial dimensions to $224 \times 224$ or $384 \times 384$ pixels using bi-cubic interpolation with anti-aliasing filters.

### 2.2 Deep Feature Extraction & Vision Transformer Attention
- **Decision:** Decomposes preprocessed images into multi-scale patch embeddings and computes global spatial-spectral correlations.
- **Rules:**
  - Partitions image tensors into non-overlapping $16 \times 16$ pixel patches and applies linear projection embeddings with positional encoding.
  - Computes multi-head self-attention across transformer layers to correlate central core morphology with diffuse peripheral halos.
  - Extracts intermediate feature representations from deep convolutional residual layers for hybrid CNN-ViT ensemble architectures.

### 2.3 Morphological Classification & Class Boundary Decision
- **Decision:** Maps extracted visual feature vectors into normalized probability distributions across target celestial classes.
- **Rules:**
  - **Galaxies:** Classified upon detecting extended non-point-spread surface brightness profiles, spiral arms, or elliptical isophotes ($P_{\text{Galaxy}} > 0.70$).
  - **Nebulae:** Classified based on diffuse, irregular emission/reflection geometries and multi-band gaseous filament structures ($P_{\text{Nebula}} > 0.70$).
  - **Stars:** Classified by matching radial Point Spread Functions (PSF) and circular diffraction patterns with compact central concentrations ($P_{\text{Star}} > 0.75$).
  - **Planets & Asteroids:** Identified through disk resolution or characteristic orbital transit streaks across sequential exposures.

### 2.4 Entropy Scoring & Optical Anomaly Flagging
- **Decision:** Identifies out-of-distribution celestial objects, lens artifacts, or ambiguous blended candidates requiring human review.
- **Rules:**
  - Computes Shannon entropy over class probability vector: $H(P) = -\sum p_i \log_2(p_i)$.
  - If entropy exceeds threshold ($H(P) > 1.25$) or top-1 class margin is narrow ($\Delta P_{1-2} < 0.15$), flags object as `AmbiguousMorphology`.
  - Generates Grad-CAM saliency heatmaps to localize the optical regions driving the uncertain classification.

---

## 3. Data Sources & Inputs Used

| Data Input | Source | Purpose | Data Handling & Privacy |
|---|---|---|---|
| **SpaceNet Astronomical Images** | SpaceNet Dataset / Kaggle | Training and benchmarking deep learning celestial classifiers | Curated public scientific imagery; loaded into memory as normalized tensors |
| **Spectral Channel Bands** | Wide-field survey optical filters ($u, g, r, i, z$) | Providing multi-wavelength observational inputs for morphology | Ingested as multi-channel image arrays; normalized to $[0.0, 1.0]$ floating-point |
| **Celestial Taxonomy Labels** | Curated Astronomical Ground Truth | Training targets (galaxies, stars, nebulae, planets, asteroids) | Standardized taxonomy mapped to SIMBAD / NASA NED astronomical catalogs |
| **Model Architectures & Weights** | PyTorch / torchvision / HuggingFace ViT | Executing convolutional and transformer inference | Pre-trained vision backbones fine-tuned with deterministic scientific seeds |

Celestial Vision Agent complies with scientific integrity and open data standards:
- **Zero Sensitive Personal Data:** Operates exclusively on telescopic celestial imagery; no human subject or personally identifiable information (PII) is involved.
- **FAIR Data Governance:** Image augmentation pipelines, train/test splits, and benchmark results adhere to Findable, Accessible, Interoperable, and Reusable (FAIR) scientific standards.
- **Strict Reproducibility:** Training workflows enforce deterministic random seeds, fixed image interpolation kernels, and environment requirements compatible with Kaggle and Colab.
- **Clean Repository Standards:** Heavy binary datasets and model checkpoints are excluded from git tracking, maintaining lightweight, reproducible notebook code.

---

## 4. Known Limitations & Failure Modes

Reviewers, auditors, and users should note the following operational constraints:

1. **Diffraction Spikes and Saturated Stellar Halos:**
   - *Limitation:* Bright foreground stars create diffraction spikes and scattering rings that can be misidentified as linear galactic structures or planetary disks.
   - *Mitigation:* The agent applies point-spread function (PSF) circularity checks and flags images containing extreme pixel saturation for targeted mask filtering.

2. **Low Surface Brightness & High Background Noise:**
   - *Limitation:* Faint dwarf galaxies and diffuse nebulae observed under low exposure times suffer from low signal-to-noise ratios ($S/N < 3$), degrading ViT attention focus.
   - *Mitigation:* An automated signal-to-noise gate evaluates background variance, routing low-confidence exposures through specialized contrast-enhancement before classification.

3. **Overlapping and Blended Celestial Targets:**
   - *Limitation:* Dense star clusters or gravitationally lensing galaxy clusters project overlapping visual profiles onto a single 2D exposure.
   - *Mitigation:* When high entropy is detected, the agent generates Grad-CAM attention heatmaps and marks the target as a `BlendedCandidate` for de-blending algorithms.

4. **Domain Shift Across Telescopic Instruments:**
   - *Limitation:* Models trained on a specific telescope filter set (e.g., SpaceNet) may exhibit accuracy drops when applied to exposures from other ground or space observatories.
   - *Mitigation:* The agent employs color-space standardization and encourages domain-adversarial fine-tuning before cross-instrument transfer.

---

## 5. Verification, Safety & Human Oversight

- **Astronomical Peer Review Gate:** Classifications flagged with high entropy ($H(P) > 1.25$) or potential cosmological anomalies generate an explainability dossier for human astrophysicist review.
- **Human-in-the-Loop Governance:** The agent functions as an automated research assistant; discoveries of rare transients or newly cataloged objects remain subject to human confirmation.
- **Deterministic Quality Gates:** Input image matrices are validated for shape, channels, and numerical range prior to model inference.
- **Kill Switch & Immutable Audit Logging:** The pipeline can be interrupted instantly via configuration flags; all predictions, entropy scores, and saliency maps are recorded in structured JSON logs.
