# 🧠 ResNet50 — BRISC 2025 Brain Tumor Classification

## 📌 Overview

This experiment implements **ResNet50 (ImageNet pretrained)** as a fully fine-tuned baseline model for multi-class brain tumor classification.
The goal was to establish a strong CNN benchmark using data augmentation, regularization, and adaptive learning rate scheduling.

---

## 🗂 Dataset

- 4 Classes:
  - Glioma
  - Meningioma
  - No Tumor
  - Pituitary
- Image Resolution: 256 × 256
- Validation Split: 20%
- Validation Samples: 998

---

## ⚙️ Model Architecture

- ResNet50 backbone (ImageNet pretrained)
- Full fine-tuning enabled
- Global Average Pooling
- Batch Normalization
- Dense (256, ReLU)
- Dropout (0.5)
- L2 Regularization (0.001)
- Softmax output (4 classes)

---

## 🔧 Training Configuration

- Optimizer: Adam (1e-4)
- Loss: Sparse Categorical Crossentropy
- Epochs: 100
- EarlyStopping (patience=10)
- ReduceLROnPlateau
- Data Augmentation:
  - Rotation
  - Width/Height shift
  - Shear
  - Zoom
  - Brightness adjustment
  - Horizontal flip

---

## 📊 Final Performance

### 🔹 Validation Accuracy
**97.39%**

### 🔹 Detailed Metrics

| Class       | Precision | Recall | F1-score |
|------------|-----------|--------|----------|
| Glioma     | 0.99      | 1.00   | 0.99     |
| Meningioma | 0.98      | 0.92   | 0.95     |
| No Tumor   | 0.92      | 1.00   | 0.96     |
| Pituitary  | 1.00      | 0.98   | 0.99     |

**Overall Metrics:**

- Accuracy: 97.39%
- Precision (Macro): 97.23%
- Recall (Macro): 97.59%
- F1-score (Macro): 97.34%

---

## 📈 Training Behavior

- Rapid convergence within first 10–15 epochs.
- Validation loss stabilized after LR reduction.
- Minimal overfitting observed.
- Strong generalization across classes.

---

## 🧩 Confusion Matrix Insights

- Glioma classified perfectly.
- No Tumor achieved perfect recall.
- Minor confusion:
  - Meningioma misclassified as No Tumor (18 samples)
  - Small overlap between Pituitary and Meningioma

This suggests visual similarity between certain tumor structures.

---

## ⚠️ Setbacks & Limitations

- Meningioma shows lower recall (0.92) compared to other classes.
- Some confusion between tumor types with similar morphology.
- Full fine-tuning increases computational cost.
- Large model size may limit deployment on low-resource systems.

---

## 📁 Files Included

- `resnet50.ipynb`
- `training_curves.png`
- `confusion_matrix.png`
- `metrics.csv`
- `predictions.csv`
- `confusion_matrix.npy`
