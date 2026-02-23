# 🧠 BRISC 2025 — Brain Tumor Classification Research

## 📌 Project Overview

This repository documents structured experimentation for multi-class brain tumor classification using MRI images.

Each deep learning architecture is implemented, trained, evaluated, and analyzed independently to understand:

- Model depth vs performance
- Architectural design impact (VGG vs ResNet vs DenseNet)
- Inter-class confusion patterns
- Generalization capability
- Computational trade-offs

The objective is not only to achieve high accuracy, but to systematically analyze architectural behavior and performance trends.

---

# 📊 Completed CNN Experiments

## 🥇 ResNet101 — Current Best Model

- **Validation Accuracy:** 97.70%
- **Macro F1-score:** 97.69%

### Key Highlights:
- Best overall performance.
- Strong class separation.
- Reduced inter-class confusion.
- Stable convergence with minimal overfitting.
- Incremental improvement over ResNet50.

📁 Full experiment details: `/ResNet101`

---

## 🥈 ResNet50 — Strong Baseline

- **Validation Accuracy:** 97.39%
- **Macro F1-score:** 97.34%

### Key Highlights:
- Excellent generalization.
- Near-perfect Glioma classification.
- Minor confusion between Meningioma and No Tumor.
- Efficient and stable training.

📁 Full experiment details: `/ResNet50`

---

## 🥉 VGG16 — Classical CNN Benchmark

- **Validation Accuracy:** 96.99%
- **Macro F1-score:** 97.07%

### Key Highlights:
- Competitive performance.
- Slightly higher inter-class confusion.
- Slower convergence compared to residual networks.
- Demonstrates effectiveness of traditional CNN architectures.

📁 Full experiment details: `/VGG16`

---

## DenseNet121 — Dense Connectivity Experiment

- **Validation Accuracy:** 95.79%
- **Macro F1-score:** 95.51%

### Additional Changes Explored:
- Partial freezing (~70% layers frozen)
- Two fully connected layers (256 → 128)
- Stronger L2 regularization
- Modified dropout rates
- Tuned learning rate (3e-4)
- Adjusted augmentation strategy

### Key Observations:
- Required additional tuning compared to other models.
- Higher confusion in Meningioma class.
- Dense connectivity did not outperform residual architectures.
- Slightly less stable training behavior.

📁 Full experiment details: `/DenseNet121`

---

# 📊 Model Comparison Summary

| Model        | Validation Accuracy | Macro F1 | Rank |
|-------------|--------------------|----------|------|
| ResNet101   | 🥇 97.70%          | 97.69%   | 1 |
| ResNet50    | 97.39%             | 97.34%   | 2 |
| VGG16       | 96.99%             | 97.07%   | 3 |
| DenseNet121 | 95.79%             | 95.51%   | 4 |

---

# 🔍 Comparative Insights

- Increasing depth (ResNet50 → ResNet101) provides measurable performance gain.
- Residual connections outperform dense connectivity on this dataset.
- VGG16 remains competitive but lacks optimization advantages of skip connections.
- DenseNet required additional architectural tuning but did not exceed ResNet performance.
- Meningioma consistently shows the highest confusion across all models.

---

# 📈 Evaluation Metrics

All models are evaluated using:

- Accuracy
- Precision (Macro Average)
- Recall (Macro Average)
- F1-score (Macro Average)
- Confusion Matrix Analysis
- Per-class performance breakdown

---

# ⚠️ General Challenges Observed

- Visual similarity between tumor classes.
- Sensitivity to augmentation parameters.
- Trade-off between model depth and computational cost.
- Diminishing returns with increasing architectural complexity.
- Risk of overfitting without proper regularization.

---

# 🔜 Future Work

- Implement transformer-based architectures.
- Compare CNN vs Transformer performance.
- Conduct deeper misclassification analysis.
- Explore lightweight deployment-ready models.
