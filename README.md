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

## 4️⃣ DenseNet121 — Dense Connectivity Experiment

- **Validation Accuracy:** 95.59%
- **Macro F1-score:** 95.70%

### Key Observations:

- Dense connectivity allowed efficient feature reuse.
- Performance remained competitive but lower than ResNet architectures.
- Training accuracy reached ~99% while validation stabilized near ~96%.
- Meningioma remained the most difficult class to classify.
- DenseNet required stronger regularization to control overfitting.

📁 Full experiment details: `/DenseNet121`

---

## 5️⃣ DenseNet169 — Deeper Dense Architecture

- **Validation Accuracy:** 94.29%
- **Macro F1-score:** 94%

### Key Observations:
- Increasing DenseNet depth (121 → 169) reduced performance.
- Training accuracy reached ~99% but validation plateaued at ~94%.
- Clear signs of moderate overfitting.
- Meningioma recall dropped compared to other architectures.
- Deeper dense connectivity did not yield performance gains.

📁 Full experiment details: `/DenseNet169`

---

# 📊 Model Comparison Summary

| Rank | Model        | Validation Accuracy | Macro F1 |
|------|-------------|--------------------|----------|
| 🥇 1 | ResNet101   | 97.70% | 97.69% |
| 🥈 2 | ResNet50    | 97.39% | 97.34% |
| 🥉 3 | VGG16       | 96.99% | 97.07% |
| 4    | DenseNet121 | 95.59% | 95.70% |
| 5    | DenseNet169 | 94.29% | 94% |

---

# 🔍 Comparative Insights

- Increasing depth improves ResNet performance (50 → 101).
- Increasing depth in DenseNet (121 → 169) degraded performance.
- Residual connections outperform dense connectivity on this dataset.
- VGG16 remains competitive despite lacking skip connections.
- Dense architectures required heavier regularization.
- Meningioma consistently shows the highest misclassification rate across models.

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
- Risk of overfitting in deeper models without careful regularization.

---

# 🔬 Key Architectural Insight

This benchmarking study reveals that:

- Residual learning scales better with depth.
- Dense connectivity does not necessarily benefit from deeper stacking.
- Optimal depth is architecture-dependent.
- Model complexity does not guarantee improved generalization.

---

# 🔜 Future Work

- Implement transformer-based architectures.
- Compare CNN vs Transformer performance.
- Conduct deeper misclassification analysis.
- Explore lightweight deployment-ready models.
- Investigate ensemble strategies.

