# 🧠 DenseNet121 — BRISC 2025 Brain Tumor Classification

## 📌 Overview

This experiment implements **DenseNet121 (ImageNet pretrained)** for multi-class brain tumor classification on the BRISC 2025 dataset. DenseNet architectures use dense connectivity, where each layer receives feature maps from all previous layers, enabling efficient feature reuse and improved gradient flow.

The goal of this experiment was to evaluate whether dense connectivity improves classification performance compared to residual architectures such as ResNet.

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

- DenseNet121 backbone (**ImageNet pretrained**)
- Partial fine-tuning enabled (**~40% layers trainable**)
- Global Average Pooling
- Batch Normalization
- Dense (256, ReLU)
- Dropout (0.4)
- L2 Regularization (1e-4)
- Softmax output (4 classes)

---

## 🔧 Training Configuration

- Optimizer: **Adam (1e-4)**
- Loss: **Sparse Categorical Crossentropy**
- Epochs: **100**
- EarlyStopping (**patience=10**)
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
**95.59%**

### 🔹 Detailed Metrics

| Class | Precision | Recall | F1-score |
|------|-----------|--------|----------|
| Glioma | 0.99 | 0.96 | 0.97 |
| Meningioma | 0.93 | 0.92 | 0.92 |
| No Tumor | 0.94 | 1.00 | 0.97 |
| Pituitary | 0.97 | 0.96 | 0.96 |

### Overall Metrics

- Accuracy: **95.59%**
- Precision (Macro): **95.66%**
- Recall (Macro): **95.80%**
- F1-score (Macro): **95.70%**

---

# 📈 Training Behavior

- Model converged within the first **15–20 epochs**.
- Training accuracy approached **~99%**, while validation stabilized near **95–96%**.
- Validation loss fluctuations indicate mild overfitting.
- Dense connectivity improves feature reuse but did not outperform residual networks in this task.

---

# 🧩 Confusion Matrix Insights

- **Glioma classification remains highly accurate.**
- **No Tumor achieved perfect recall (1.00).**
- Most misclassifications occur in the **Meningioma class**.

Minor confusion patterns observed:

- Meningioma predicted as **No Tumor**
- Pituitary predicted as **Meningioma**

This reflects the **visual similarity between certain tumor structures in MRI scans**.

---

# ⚠️ Setbacks & Limitations

- DenseNet architecture required stronger regularization.
- Slightly higher inter-class confusion compared to ResNet models.
- Dense connectivity increases memory consumption.
- Performance improvement from dense connections was limited for this dataset.

---

# 📁 Files Included

- `densenet121-95-9.ipynb`
- `training_curves.png`
- `confusion_matrix.png`
- `metrics.csv`
- `predictions.csv`
- `confusion_matrix.npy`
