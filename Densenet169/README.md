# 🧠 DenseNet169 — BRISC 2025 Brain Tumor Classification

## 📌 Overview

This experiment implements **DenseNet169 (ImageNet pretrained)** for multi-class brain tumor classification on the BRISC 2025 dataset. DenseNet architectures utilize dense connectivity, where each layer receives feature maps from all preceding layers, allowing efficient feature reuse and improved gradient propagation.

The goal of this experiment was to evaluate whether increasing DenseNet depth improves classification performance on brain MRI tumor detection.

---

## 🗂 Dataset

- 4 Classes:
  - Glioma
  - Meningioma
  - No Tumor
  - Pituitary
- Image Resolution: **224 × 224**
- Validation Split: **20%**
- Validation Samples: **998**

---

## ⚙️ Model Architecture

- DenseNet169 backbone (**ImageNet pretrained**)
- Partial fine-tuning enabled (**~50% layers trainable**)
- Global Average Pooling
- Batch Normalization
- Dense (256, ReLU)
- Dropout (0.5)
- L2 Regularization (5e-4)
- Softmax output (4 classes)

---

## 🔧 Training Configuration

- Optimizer: **Adam (7e-5)**
- Loss: **Sparse Categorical Crossentropy**
- Epochs: **100**
- EarlyStopping (patience=10)
- ReduceLROnPlateau
- Data Augmentation:
  - Rotation
  - Width shift
  - Height shift
  - Shear
  - Zoom
  - Brightness adjustment
  - Horizontal flip

---

# 📊 Final Performance

### 🔹 Validation Accuracy
**96.69%**

### 🔹 Detailed Metrics

| Class | Precision | Recall | F1-score |
|------|-----------|--------|----------|
| Glioma | 0.99 | 0.95 | 0.97 |
| Meningioma | 0.95 | 0.94 | 0.94 |
| No Tumor | 0.96 | 1.00 | 0.98 |
| Pituitary | 0.97 | 0.98 | 0.98 |

### Overall Metrics

- Accuracy: **96.69%**
- Precision (Macro): **96.72%**
- Recall (Macro): **96.75%**
- F1-score (Macro): **96.72%**

---

# 📈 Training Behavior

- Model converged steadily within the first **20 epochs**.
- Training accuracy approached **~99%**.
- Validation accuracy stabilized around **96–97%**.
- Lower learning rate helped stabilize training for the deeper architecture.

DenseNet169 showed **better generalization compared to DenseNet121**.

---

# ⚠️ Setbacks & Limitations

- Deeper DenseNet architecture increases computational cost.
- Training time was longer compared to DenseNet121.
- Dense connectivity increases GPU memory usage.
- Performance still slightly lower than top-performing ResNet models.

---

# 📁 Files Included

- `densenet169-96-69.ipynb`
- `training_curves.png`
- `confusion_matrix.png`
- `metrics.csv`
- `predictions.csv`
- `confusion_matrix.npy`
