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

## 🥇 ResNet101 — Current Best CNN

ResNet101 (ImageNet pretrained, fully fine-tuned) achieved:

- **97.70% Validation Accuracy**
- 97.69% Macro F1-score

### Improvements Over ResNet50:
- Slightly better overall accuracy.
- Improved class separation.
- Reduced inter-class confusion.

Although performance gains are modest, deeper feature extraction provided measurable improvements.

📁 Full experiment details available in `/ResNet101`

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
