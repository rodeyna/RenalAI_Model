# RenalAI: Deep Learning for Kidney Disease Detection & Segmentation

This repository contains the training pipeline for a dual-model system designed to automate the diagnosis and localization of renal pathologies from axial CT scans.

## 🚀 Project Overview
The system employs a sequential pipeline to assist in clinical decision support:
1. [cite_start]**Classification:** An EfficientNet-B0 model categorizes scans into: Normal, Cyst, Stone, or Tumor[cite: 29, 91].
2. [cite_start]**Segmentation:** A UNet++ architecture with an EfficientNet-B0 encoder performs pixel-level localization of kidney stones[cite: 99].

## 📊 Model Performance
[cite_start]Both models exceed clinical thresholds (>85% Dice) for medical imaging support tools[cite: 56, 128].

| Task | Architecture | Key Metric | Result |
| :--- | :--- | :--- | :--- |
| **Classification** | EfficientNet-B0 | Test Accuracy | [cite_start]**99.89%** [cite: 126] |
| **Segmentation** | UNet++ + EffNet-B0 | Dice Score (Optimized) | [cite_start]**92.21%** [cite: 126] |

* [cite_start]**Success:** Only 2 images were misclassified out of 1,868 test images[cite: 95, 96].
* [cite_start]**Segmentation:** The model achieved 92.21% Dice using a two-phase training strategy and optimal thresholding[cite: 102, 112].

## 🛠️ Technical Highlights
* [cite_start]**Weighted Loss:** Implemented weighted cross-entropy to handle the 1:3.7 Stone-to-Normal imbalance[cite: 31, 71].
* [cite_start]**Loss Engineering:** Combined Dice Loss and Weighted BCE (pos_weight=20) to handle extreme 10,000:1 pixel imbalance[cite: 38, 86].
* [cite_start]**Preprocessing:** Applied CLAHE (Contrast Limited Adaptive Histogram Equalization) to enhance stone boundaries[cite: 76, 77].

## 📂 Datasets Used
1. [cite_start]**CT Kidney Dataset (Kaggle):** 12,446 images for classification[cite: 29].
2. [cite_start]**KSSD2025:** 838 radiologist-annotated axial CT images for segmentation[cite: 35, 145].

---
**Team 5:** Ahmid Rodyena | Boulali Djennat | [cite_start]Lallaoui Ouarda [cite: 5, 6]
[cite_start]**Academic Year:** 2024–2025 [cite: 7]
