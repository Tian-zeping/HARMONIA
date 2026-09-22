# HARMONIA: Confidence-Gated Conservative Ownership Coupling for Source-Faithful Infrared–Visible Image Fusion


> **Abstract**
> Infrared–visible image fusion aims to preserve thermal targets while retaining source-supported structures. However, existing methods often struggle with local source preference reliability under degradation. We propose **HARMONIA**, a reliability-aware harmonic framework. It features a harmonic backbone that propagates reliability-weighted source anchors and a source-symmetric relative-evidence module. Crucially, a **confidence dead-zone** suppresses uncertain corrections, and **conservative log-odds coupling** bounds ownership updates, preventing excessive deviation from the harmonic solution. This ensures robust fusion without requiring test-time adaptation.


---

## 🔥 Highlights

*   **Reliability-Aware Harmonic Backbone:** Constructs reliability-weighted source anchors and propagates them over a source-aware latent graph, ensuring a stable fusion basis.
*   **Source-Symmetric Relative Evidence:** Estimates local IR/VIS ownership using a shared scorer, ensuring symmetric preference estimation.
*   **Confidence-Gated Conservative Coupling:** 
    *   **Confidence Dead-Zone:** Suppresses uncertain corrections to avoid disturbing stable regions.
    *   **Conservative Log-Odds Coupling:** Explicitly bounds the magnitude of ownership updates (max 12.5% deviation), preventing aggressive intervention.
*   **Robustness:** Achieves state-of-the-art performance on MSRS, LLVIP, RoadScene, and FMB benchmarks, particularly under source degradation (blur, noise, darkness), without needing degradation labels.

---

## 📊 Results

HARMONIA achieves competitive performance across multiple benchmarks. Here are the results on the MSRS and LLVIP datasets:

| Method | Venue | MSRS (Qabf↑) | MSRS (MI↑) | LLVIP (Qabf↑) | LLVIP (MI↑) |
| :--- | :---: | :---: | :---: | :---: | :---: |
| LRRNet | TPAMI'23 | 0.457 | 3.639 | 0.619 | 3.195 |
| Text-IF | CVPR'24 | 0.691 | 3.891 | 0.573 | 3.422 |
| ControlFusion | NeurIPS'25 | 0.703 | 3.789 | 0.691 | 3.874 |
| **HARMONIA (Ours)** | **ICASSP'27** | **0.726** | **4.221** | **0.678** | **3.976** |

*Note: HARMONIA is trained only on MSRS but generalizes well to unseen datasets like LLVIP and RoadScene.*


---

> **🚀 Coming Soon:** The full source code, pre-trained models, and usage instructions will be released shortly. Star this repository to get notified!

