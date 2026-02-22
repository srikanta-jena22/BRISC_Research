# 🧠 BRISC 2025 — Brain Tumor Classification Research

## 📌 Project Overview

This repository documents structured experimentation for multi-class brain tumor classification using MRI images.

Each model is implemented, trained, evaluated, and analyzed independently to understand:

- Model depth vs performance
- CNN vs Transformer behavior
- Inter-class confusion patterns
- Generalization capability

---

# 📊 Completed Experiments

## 🥇 ResNet50 — Current Baseline

ResNet50 (ImageNet pretrained) was fully fine-tuned and achieved:

- **97.39% Validation Accuracy**
- 97.34% Macro F1-score

### Key Observations:
- Strong overall generalization.
- Perfect Glioma classification.
- Minor confusion between Meningioma and No Tumor.
- Stable training with minimal overfitting.

📁 Full experiment details available in `/ResNet50`

---

# 📈 Evaluation Metrics

All models are evaluated using:

- Accuracy
- Precision (Macro)
- Recall (Macro)
- F1-score (Macro)
- Confusion Matrix

---

# ⚠️ General Challenges Observed

- Visual similarity between certain tumor classes.
- Sensitivity to augmentation strategy.
- Trade-off between model depth and computational cost.
- Risk of overfitting in deeper architectures.

---

# 🏁 Objective

To build a reproducible, research-oriented deep learning benchmarking framework for medical image classification.
