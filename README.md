# RenalAI: Deep Learning for Kidney Disease Detection & Segmentation

This repository contains the training pipeline for a dual-model system designed to automate the diagnosis and localization of renal pathologies from axial CT scans.

## 🚀 Project Overview
The system employs a sequential pipeline to assist in clinical decision support:
1. **Classification:** An EfficientNet-B0 model categorizes scans into: Normal, Cyst, Stone, or Tumor
2. **Segmentation:** A UNet++ architecture with an EfficientNet-B0 encoder performs pixel-level localization of kidney stones

## 📊 Model Performance
[cite_start]Both models exceed clinical thresholds (>85% Dice) for medical imaging support tools

| Task | Architecture | Key Metric | Result |
| :--- | :--- | :--- | :--- |
| **Classification** | EfficientNet-B0 | Test Accuracy |**99.89%** |
| **Segmentation** | UNet++ + EffNet-B0 | Dice Score (Optimized) |**92.21%**  |

**Success:** Only 2 images were misclassified out of 1,868 test images
**Segmentation:** The model achieved 92.21% Dice using a two-phase training strategy and optimal thresholding

## 🛠️ Technical Highlights
**Weighted Loss:** Implemented weighted cross-entropy to handle the 1:3.7 Stone-to-Normal imbalance
**Loss Engineering:** Combined Dice Loss and Weighted BCE (pos_weight=20) to handle extreme 10,000:1 pixel imbalance
**Preprocessing:** Applied CLAHE (Contrast Limited Adaptive Histogram Equalization) to enhance stone boundaries

## 📂 Datasets Used
1. **CT Kidney Dataset (Kaggle):** 12,446 images for classification
2. **KSSD2025:** 838 radiologist-annotated axial CT images for segmentation

---
**Team 5:** Ahmid Rodyena | Boulali Djennat |Lallaoui Ouarda
