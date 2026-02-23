# 🧠 DenseNet121 — BRISC 2025 Brain Tumor Classification

## 📌 Overview

This experiment evaluates DenseNet121 (ImageNet pretrained) for multi-class brain tumor classification.

The objective was to explore whether dense connectivity improves feature reuse and classification performance compared to residual architectures.

---

## ⚙️ Architectural Modifications

Additional experimentation was performed compared to previous models:

- Partial freezing (~70% layers frozen)
- Two fully connected layers (256 → 128)
- Stronger L2 regularization (8e-4)
- Higher learning rate (3e-4)
- Adjusted dropout rates (0.45 / 0.35)
- Modified augmentation parameters

---

## 📊 Final Performance

- Validation Accuracy: **95.79%**
- Macro Precision: 95.47%
- Macro Recall: 95.61%
- Macro F1-score: 95.51%

---

## 🔍 Observations

- DenseNet required more tuning compared to ResNet models.
- Higher confusion observed for Meningioma.
- Performance did not exceed residual architectures.
- Additional regularization did not significantly improve results.

---

## ⚠️ Limitations

- Lower accuracy compared to ResNet50/101.
- More sensitive to learning rate.
- Dense connectivity did not translate into superior performance on this dataset.

---

## 📁 Files Included

- `densenet121-95-4.ipynb`
- `metrics.csv`
- `predictions.csv`
- `confusion_matrix.npy`
