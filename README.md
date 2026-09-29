# 📡 Celestial Vision — Celestial Object Classification

[![OpenGAP Spec 0.1.0](https://img.shields.io/badge/OpenGAP-0.1.0-blue.svg)](https://opengitagent.org)
[![GitAgent Passport](https://img.shields.io/badge/GitAgent%20Passport-Ready-brightgreen.svg)](https://app.hidevs.xyz/passport/submit)
[![Category](https://img.shields.io/badge/Category-Data%20%26%20Analytics-purple.svg)](https://app.hidevs.xyz/passport/submit)
[![Compliance](https://img.shields.io/badge/Compliance-FAIR%20%7C%20Open%20Science-orange.svg)](EXPLAINABILITY.md)

## 🚀 Task Overview
The objective of this task is to build **computer vision–based machine learning models** to classify different celestial objects such as galaxies, stars, planets, nebulae, asteroids, and more using astronomical image data.



This is an open-ended task, and participants are encouraged to explore multiple approaches, architectures, and evaluation strategies.

---

## 📂 Dataset Description
The **SpaceNet** dataset is a curated collection of thousands of labeled astronomical images spanning multiple celestial object categories.

* **Source:** [SpaceNet – Kaggle](https://www.kaggle.com/datasets/razaimam45/spacenet-an-optimally-distributed-astronomy-data)
* **Suitability:** Designed for deep learning–based image classification.
* **Diversity:** Balanced across multiple classes.
* **Compatibility:** Works with baseline CNNs and advanced architectures like **Vision Transformers (ViT)**.

> [!IMPORTANT]
> Participants must download and attach the dataset themselves. If local resources are limited, use Kaggle Notebooks and upload the `.ipynb` files here.

---

## 🤝 Contribution Guidelines 

To contribute, follow these steps:

1. **Fork the repository** to your own GitHub account.
2. **Clone your fork** locally or work directly on Kaggle Notebooks.
3. **Create a folder** inside the `participants/` directory named exactly as your enrollment number.
4. **Add your notebooks** (`.ipynb`) inside your folder.
5. **Commit** your changes to your fork.
6. **Open a Pull Request** to submit your work to the main repository.
```text
participants/
└── <your_enrollment_number>/
    ├── notebook_1.ipynb
    ├── notebook_2.ipynb
    └── ...
```



### Rules

- Create a subfolder **named exactly as your enrollment number** 
- Upload **only your notebooks** inside your folder
- Do **not** upload datasets, model weights, or large binaries
- Do **not** modify or delete other participants’ folders

### Further Details

- Any additional instructions, constraints, or evaluation criteria will be **issue-specific**
- Participants are expected to carefully read the relevant GitHub issue before making a submission





---

## 💬 Doubts & Discussions

All doubts, clarifications, and discussions related to this task will be **entertained via the Discord bot**.  
Please refrain from opening GitHub issues for general doubts unless explicitly instructed.

---

## GitAgent Passport Qualification

This repository is fully compliant with the **OpenGAP Spec 0.1.0** standard and qualified for the **HiDevs GitAgent Passport**:

- **Checkpoint 1 (Validate):** Verified OpenGAP spec 0.1.0 compliance via [`agent.yaml`](agent.yaml), [`SOUL.md`](SOUL.md), [`skills/`](skills/), and [`tools/`](tools/).
- **Checkpoint 2 (Explain):** Comprehensive 5-section transparency report in [`EXPLAINABILITY.md`](EXPLAINABILITY.md) detailing photometric arcsinh/z-scale dynamic range stretching, Vision Transformer patch tokenization, class boundary rules, and entropy-based optical anomaly filters.
- **Checkpoint 3 (Export):** Cross-framework export compatibility tested across OpenAI SDK, CrewAI, Claude Code, and Lyzr.
- **Target Category:** **`Data & Analytics`** (Astronomical Computer Vision & Deep Learning).


