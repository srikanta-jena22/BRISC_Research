# 🧠 DenseNet169 — BRISC 2025 Brain Tumor Classification

## 📌 Overview

This experiment evaluates DenseNet169 (ImageNet pretrained) for multi-class brain tumor classification.

The goal was to examine whether increasing DenseNet depth (121 → 169 layers) improves representation power and classification accuracy.

---

## ⚙️ Architecture & Modifications

- DenseNet169 backbone (ImageNet pretrained)
- Partial fine-tuning (~75% layers frozen)
- Global Average Pooling
- Batch Normalization
- Dense(256) + Dropout(0.45)
- Dense(128) + Dropout(0.35)
- L2 Regularization (8e-4)
- Adam optimizer (learning rate = 3e-4)

---

## 📊 Final Performance

- **Validation Accuracy:** 94.29%
- **Macro Precision:** 94%
- **Macro Recall:** 94%
- **Macro F1-score:** 94%

---

## 📈 Training Behavior

- Training accuracy reached ~99%.
- Validation accuracy plateaued at ~94%.
- Moderate overfitting observed.
- Increasing depth did not improve performance compared to DenseNet121.

---

## 🧩 Confusion Matrix Insights
- Meningioma misclassified as No Tumor.
- Slight drop in recall for Meningioma (0.89).
- No Tumor achieved very strong recall (0.99).

---

## ⚠️ Observations & Setbacks

- Increasing DenseNet depth (121 → 169) did not improve accuracy.
- DenseNet121 (95.79%) outperformed DenseNet169 (94.29%).
- Deeper architecture increased overfitting risk.
- Residual networks remain more stable for this dataset.


## 📌 Conclusion

While DenseNet169 increases model depth and representational capacity, it does not outperform DenseNet121 or ResNet architectures on this dataset. This suggests diminishing returns with deeper dense connectivity for this classification task.
