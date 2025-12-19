![Paper](https://img.shields.io/badge/Paper-MDPI%20Diagnostics-blue)
![Status](https://img.shields.io/badge/Status-Published-success)
![Task](https://img.shields.io/badge/Task-Medical%20Image%20Segmentation-orange)
![XAI](https://img.shields.io/badge/XAI-Grad--CAM%20%7C%20Saliency-red)

# μ-Net: Colorectal Polyp Segmentation with Explainable AI

📄 **Journal**: MDPI Diagnostics (2025)  
👤 **First Author**: Mehedi Hasan Emon  
🔗 **Paper**: https://www.mdpi.com/2075-4418/15/22/2890  

---

## Overview

This repository accompanies the published paper:

> **An Integrated Architecture for Colorectal Polyp Segmentation: The μ-Net Framework with Explainable AI**  
> *Diagnostics, 2025*

We propose **μ-Net**, a novel encoder–decoder segmentation architecture designed for **accurate and robust colorectal polyp segmentation** in colonoscopy images.  
The model integrates **multi-scale feature extraction**, **residual learning**, and **attention mechanisms (CBAM)** through carefully designed architectural blocks, while also providing **Explainable AI (XAI)** visualizations to support clinical trust.

---

## Key Contributions

- Proposed **μ-Net**, an enhanced U-Net–based architecture with **multi-branch μ-blocks** for rich feature representation.
- Integrated **CBAM (Convolutional Block Attention Module)** within encoder and decoder blocks to recalibrate **spatial and channel-wise features**.
- Introduced specialized building blocks:
  - **CBRes Block**
  - **Dual Dilate-CB Block**
  - **TriDilation Attention Unit (TDAU)**
  - **SplitFusion Block**
- Achieved **94.02% Dice coefficient** on the **Kvasir-SEG** dataset, outperforming several state-of-the-art models.
- Maintained **computational efficiency** (≈39.04 GFLOPs, 15 ms inference time).
- Integrated **Explainable AI (XAI)** methods, including **Saliency Maps** and **Grad-CAM**, to visualize model attention and improve interpretability.

---

## Model Architecture

μ-Net follows an **encoder–decoder structure** with skip connections and residual learning.
The architecture is specifically optimized for capturing fine-grained polyp boundaries while maintaining global contextual awareness.

Key architectural highlights:

- **μ-block** with six parallel feature branches for multi-scale contextual learning
- **CBAM modules** embedded throughout the network for adaptive attention
- **Residual connections** to stabilize deep training
- **Nearest-neighbor upsampling** to preserve fine boundary details
- Final **Sigmoid output layer** for binary polyp segmentation

📌 *See Figures 4–10 in the paper for detailed architectural diagrams.*

---

## Dataset
All experiments were conducted following standard research and ethical guidelines for medical image analysis.
- **Kvasir-SEG Dataset**
  - 1000 colonoscopy images with pixel-wise polyp annotations
  - Publicly available:  
    https://www.kaggle.com/datasets/debeshjha1/kvasirseg

---

## Training Details

- **Framework**: TensorFlow 2.11  
- **Optimizer**: AdamW  
- **Input Resolution**: 352 × 352  
- **Epochs**: 300  
- **Batch Size**: 2  
- **Hardware**: NVIDIA GeForce RTX 3060  
- **Augmentation**: Albumentations (geometric + photometric)

---

## Evaluation Metrics

- Dice Coefficient (DSC)
- Intersection over Union (IoU)
- Precision
- Recall
- Pixel Accuracy
- FLOPs and Inference Time

---

## Explainable AI (XAI)

To enhance clinical reliability, μ-Net incorporates post-hoc explainability:

- **Grad-CAM**
- **Saliency Maps**

These methods highlight image regions contributing most to segmentation decisions, aligning model attention with clinically relevant polyp regions.

---

## Citation

If you use this work, please cite:

```bibtex
@article{Emon2025MuNet,
  title={An Integrated Architecture for Colorectal Polyp Segmentation: The μ-Net Framework with Explainable AI},
  author={Emon, Mehedi Hasan and Mondal, Proloy Kumar and others},
  journal={Diagnostics},
  volume={15},
  number={22},
  pages={2890},
  year={2025},
  publisher={MDPI}
}


## Repository Status
⚠️ The full training and evaluation code will be released after institutional approval.  
This repository currently documents the published architecture, methodology, and experimental setup.

