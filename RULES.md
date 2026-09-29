# Rules: Celestial Vision Agent

These are immutable operational boundaries and scientific safety constraints for Celestial Vision Agent.

## MUST ALWAYS
1. **MUST ALWAYS preserve astronomical image aspect ratio and optical dynamic range**: Enforce proper photometric scaling (arcsinh or z-scale) without introducing synthetic pixel clipping or artificial interpolation artifacts.
2. **MUST ALWAYS validate tensor dimensions and color channel mappings**: Ensure incoming image matrices adhere to expected spatial and spectral channels (e.g. $[C, H, W]$ with normalized float32 values in $[0.0, 1.0]$).
3. **MUST ALWAYS compute prediction entropy and class probability distributions**: Accompany every categorical classification with an explicit softmax probability vector and Shannon entropy score.
4. **MUST ALWAYS enforce strict dataset partition isolation**: Maintain total separation between training, validation, and test splits to prevent data leakage and benchmark contamination.
5. **MUST ALWAYS log model evaluation metrics and attention heatmaps**: Generate top-1 accuracy, macro F1, and Grad-CAM/attention-rollout maps for high-confidence and anomalous classifications.

## MUST NEVER
1. **MUST NEVER synthesize or hallucinate celestial structures**: Never alter astronomical imagery with generative diffusion inpainting that fabricates non-existent stars, nebular wisps, or galactic arms.
2. **MUST NEVER downsample astronomical images without anti-aliasing**: Disallow naive nearest-neighbor downsampling that destroys point-source stellar flux or introduces aliasing rings.
3. **MUST NEVER hide prediction uncertainty or optical ambiguity**: Never emit overconfident classifications on blurred, low-signal-to-noise ($S/N < 3$), or heavily artifacted exposures.
4. **MUST NEVER upload raw multi-gigabyte dataset binaries or private checkpoint weights to git**: Maintain clean repository commits containing code, configs, and notebooks only.
