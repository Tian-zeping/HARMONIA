# HARMONIA: Confidence-Gated Conservative Ownership Coupling for Source-Faithful Infrared–Visible Image Fusion

HARMONIA is a reliability-aware harmonic framework for infrared–visible image
fusion. It combines structured harmonic propagation with source-symmetric
relative evidence and confidence-gated conservative ownership correction to
preserve thermal targets and source-supported structural details.

---

## Abstract

Infrared–visible image fusion must preserve thermal targets while retaining
source-supported structures and textures. Existing fusion methods can enhance
complementary information, but local source preference may become unreliable
under degradation, and aggressive ownership correction can disturb otherwise
stable fusion.

We propose **HARMONIA**, a reliability-aware harmonic framework for
source-faithful IR–VIS fusion. A harmonic backbone constructs
reliability-weighted source anchors and propagates them over a source-aware
latent graph. On top of this backbone, a source-symmetric relative-evidence
module estimates local IR/VIS ownership, while a confidence dead-zone
suppresses uncertain corrections. The accepted update is further bounded by
conservative log-odds coupling, preventing excessive deviation from the
harmonic solution.

At inference time, HARMONIA requires only the two source modalities, without
corruption labels, degradation-severity estimation, test-time statistics, or
test-time adaptation.

---

## 🔥 Highlights

- **Reliability-Guided Harmonic Fusion**  
  Constructs reliability-weighted source anchors and propagates them over a
  source-aware latent graph, providing a stable harmonic fusion backbone.

- **Source-Symmetric Relative Evidence**  
  Estimates complementary local IR/VIS preferences using a shared scoring
  mechanism, providing an explicit source-ownership correction direction.

- **Confidence-Gated Ownership Correction**  
  A confidence gate suppresses uncertain corrections, allowing source
  preference to intervene only when sufficiently supported.

- **Conservative Log-Odds Coupling**  
  Ownership correction is performed through bounded interpolation in log-odds
  space. With
  \(\alpha_i = 0.125 g_i\), at most 12.5% of the target log-odds displacement
  is injected into the harmonic ownership.

- **Source-Faithful and Robust Fusion**  
  HARMONIA preserves thermal targets and visible structures while reducing
  unnecessary intervention in weakly supported or stable regions.

- **No Test-Time Adaptation**  
  Inference requires only the infrared and visible inputs, without corruption
  labels, degradation-severity estimation, or test-time adaptation.

---

## 📊 Selected Results

HARMONIA is trained exclusively on the **MSRS training set** and directly
evaluated on MSRS, LLVIP, RoadScene, and FMB without additional fine-tuning or
adaptation.

Selected quantitative results on MSRS and LLVIP are shown below.

| Method | Venue | MSRS Qabf ↑ | MSRS MI ↑ | LLVIP Qabf ↑ | LLVIP MI ↑ |
| :--- | :---: | :---: | :---: | :---: | :---: |
| LRRNet | TPAMI'23 | 0.457 | 3.639 | 0.619 | 3.195 |
| Text-IF | CVPR'24 | 0.691 | 3.891 | 0.573 | 3.422 |
| ControlFusion | NeurIPS'25 | 0.703 | 3.789 | **0.691** | 3.874 |
| **HARMONIA (Ours)** | — | **0.726** | **4.221** | 0.678 | **3.976** |

HARMONIA achieves the best **Qabf** on MSRS and the highest **MI** on LLVIP
among the compared methods shown above, while being trained only on MSRS.

---

## 🛡️ Robustness

We further evaluate HARMONIA under controlled source degradations, including:

- Blackout
- Blur
- Contrast reduction
- Darkness
- Noise

Infrared and visible sources are degraded independently, resulting in ten
source–degradation conditions. The experiments evaluate whether ownership
correction improves robustness while preserving clean fusion behavior.

---

## 🚀 Code Release

The source code, pretrained models, configuration files, and usage instructions
will be released soon.

If you find this work useful, please consider starring the repository.
