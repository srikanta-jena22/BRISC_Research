# 🧠 BRISC 2025 — Brain Tumor Classification Research

## 📌 Project Overview

This repository documents structured experimentation for multi-class brain tumor classification using MRI images.

Each deep learning architecture is implemented, trained, evaluated, and analyzed independently to understand:

- Model depth vs performance
- Architectural design impact (VGG vs ResNet)
- Inter-class confusion patterns
- Generalization capability
- Computational trade-offs

The objective is not only to achieve high accuracy, but to analyze model behavior systematically.

---

# 📊 Completed CNN Experiments

## 🥇 ResNet101 — Current Best Model

- **Validation Accuracy:** 97.70%
- **Macro F1-score:** 97.69%

### Key Highlights:
- Best overall performance.
- Strong class separation.
- Reduced confusion between tumor types.
- Stable training with minimal overfitting.
- Improved performance over ResNet50.

📁 Full experiment details: `/ResNet101`

---

## 🥈 ResNet50 — Strong Baseline

- **Validation Accuracy:** 97.39%
- **Macro F1-score:** 97.34%

### Key Highlights:
- Excellent generalization.
- Near-perfect Glioma classification.
- Minor confusion between Meningioma and No Tumor.
- Efficient and stable convergence.

📁 Full experiment details: `/ResNet50`

---

## 🥉 VGG16 — Classical CNN Benchmark

- **Validation Accuracy:** 96.99%
- **Macro F1-score:** 97.07%

### Key Highlights:
- Competitive performance.
- Slightly higher inter-class confusion.
- Slower convergence compared to residual networks.
- Demonstrates effectiveness of classical CNN architectures.

📁 Full experiment details: `/VGG16`

---

# 📊 Model Comparison Summary

| Model       | Validation Accuracy | Macro F1 | Rank |
|------------|--------------------|----------|------|
| ResNet101  | 🥇 97.70%          | 97.69%   | 1 |
| ResNet50   | 97.39%             | 97.34%   | 2 |
| VGG16      | 96.99%             | 97.07%   | 3 |

### Observations:

- Increasing depth (ResNet50 → ResNet101) provides measurable improvement.
- Residual connections improve optimization stability.
- VGG16 performs competitively but lacks skip connections.
- Most confusion occurs between Meningioma and other tumor types.

---

# 📈 Evaluation Metrics

All models are evaluated using:

- Accuracy
- Precision (Macro Average)
- Recall (Macro Average)
- F1-score (Macro Average)
- Confusion Matrix Analysis
- Per-class performance metrics

---

# ⚠️ General Challenges Observed

- Visual similarity between certain tumor classes.
- Sensitivity to augmentation strategy.
- Trade-off between depth and computational cost.
- Diminishing returns with increased model complexity.
- Risk of overfitting without regularization.

---

# 🔜 Future Work

- Implement transformer-based architectures (TinyViT, MaxViT).
- Compare CNN vs Transformer performance.
- Perform hyperparameter optimization.
- Conduct deeper error analysis on misclassified samples.
- Explore deployment considerations for medical settings.

---

# 🏁 Objective

To build a reproducible, research-oriented deep learning benchmarking framework for medical image classification, analyzing architectural trade-offs while maintaining high performance and interpretability.
