# 🧠 ResNet101 — BRISC 2025 Brain Tumor Classification

## 📌 Overview

This experiment evaluates **ResNet101 (ImageNet pretrained)** as a deeper residual network for multi-class brain tumor classification.
The objective was to analyze whether increased network depth improves feature extraction and classification performance compared to ResNet50.

---

## 🗂 Dataset

- 4 Classes:
  - Glioma
  - Meningioma
  - No Tumor
  - Pituitary
- Input Resolution: 224 × 224
- Validation Split: 20%
- Validation Samples: 998

---

## ⚙️ Model Architecture

- ResNet101 backbone (ImageNet pretrained)
- Full fine-tuning enabled
- Global Average Pooling
- Batch Normalization
- Dense (256, ReLU)
- Dropout (0.5)
- L2 Regularization (1e-3)
- Softmax output (4 classes)

---

## 🔧 Training Configuration

- Optimizer: Adam (1e-4)
- Loss: Sparse Categorical Crossentropy
- Epochs: 100
- EarlyStopping (patience=15)
- ReduceLROnPlateau
- Data Augmentation:
  - Rotation
  - Shift
  - Shear
  - Zoom
  - Brightness adjustment
  - Horizontal flip

---

## 📊 Final Performance

### 🔹 Validation Accuracy
**97.70%**

### 🔹 Detailed Metrics

| Class       | Precision | Recall | F1-score |
|------------|-----------|--------|----------|
| Glioma     | 1.00      | 0.99   | 0.99     |
| Meningioma | 0.97      | 0.95   | 0.96     |
| No Tumor   | 0.95      | 0.99   | 0.97     |
| Pituitary  | 0.99      | 0.98   | 0.99     |

**Overall Metrics:**

- Accuracy: 97.70%
- Precision (Macro): 97.63%
- Recall (Macro): 97.77%
- F1-score (Macro): 97.69%
- Validation Loss: 0.4127

---

## 📈 Training Behavior

- Slightly slower convergence than ResNet50 due to increased depth.
- Stable validation accuracy after learning rate reduction.
- No significant overfitting observed.
- Smooth training and validation curves.

---

## 🧩 Confusion Matrix Insights

- Glioma classified almost perfectly.
- No Tumor maintained very high recall.
- Reduced confusion between Meningioma and No Tumor compared to ResNet50.
- Minor residual overlap between Meningioma and Pituitary.

---

## ⚠️ Setbacks & Limitations

- Increased computational cost compared to ResNet50.
- Longer training time.
- Slightly diminishing returns in performance gain relative to added complexity.
- Larger model size may limit real-world deployment.

---

## 📌 Comparison with ResNet50

| Model       | Validation Accuracy | Macro F1 |
|------------|--------------------|----------|
| ResNet50   | 97.39%             | 97.34%   |
| ResNet101  | **97.70%**         | **97.69%** |

ResNet101 shows a modest but consistent improvement over ResNet50, confirming that deeper feature extraction benefits this dataset.

---

## 📁 Files Included

- `resnet101.ipynb`
- `confusion_matrix.npy`
- `metrics.csv`
- `predictions.csv`
