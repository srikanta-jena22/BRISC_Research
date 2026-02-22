# 🧠 VGG16 — BRISC 2025 Brain Tumor Classification

## 📌 Overview

This experiment evaluates **VGG16 (ImageNet pretrained)** as a classical convolutional neural network architecture for multi-class brain tumor classification.

The objective was to compare an older deep CNN architecture against modern residual networks (ResNet50 and ResNet101).

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

- VGG16 backbone (ImageNet pretrained)
- Full fine-tuning enabled
- Global Average Pooling
- Batch Normalization
- Dense (256, ReLU)
- Dropout (0.5)
- L2 Regularization (0.001)
- Softmax output layer (4 classes)

---

## 🔧 Training Configuration

- Optimizer: Adam (1e-4)
- Loss: Sparse Categorical Crossentropy
- Epochs: 100
- EarlyStopping (patience=7)
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
**96.99%**

### 🔹 Detailed Metrics

| Class       | Precision | Recall | F1-score |
|------------|-----------|--------|----------|
| Glioma     | 1.00      | 0.99   | 0.99     |
| Meningioma | 0.94      | 0.95   | 0.95     |
| No Tumor   | 0.96      | 0.98   | 0.97     |
| Pituitary  | 0.98      | 0.97   | 0.97     |

**Overall Metrics:**

- Accuracy: 96.99%
- Precision (Macro): 97.01%
- Recall (Macro): 97.13%
- F1-score (Macro): 97.07%

---

## 📈 Training Behavior

- Converged steadily but slightly slower than ResNet models.
- Higher fluctuation in early validation loss.
- Stable performance after LR reduction.

---

## 🧩 Confusion Matrix Insights

- Glioma classified almost perfectly.
- Minor confusion between:
  - Meningioma and No Tumor
  - Pituitary and Meningioma
- Slightly higher inter-class confusion compared to ResNet101.

---

## ⚠️ Setbacks & Limitations

- Lower overall accuracy compared to ResNet50 and ResNet101.
- Larger parameter count without skip connections.
- More sensitive to overfitting.
- Slower convergence.
- Diminishing performance relative to model size.

---

## 📌 Comparison with Other CNN Models

| Model       | Validation Accuracy | Macro F1 |
|------------|--------------------|----------|
| ResNet101  | 🥇 97.70%          | 97.69%   |
| ResNet50   | 97.39%             | 97.34%   |
| VGG16      | 96.99%             | 97.07%   |

VGG16 performs competitively but is slightly outperformed by residual architectures.

---

## 📁 Files Included

- `vgg16.ipynb`
- `training_curves.png`
- `confusion_matrix.png`
- `confusion_matrix.npy`
- `classification_report.csv`
- `classification_report.text`
- `summary_metrics.csv`
- `predictions.csv`
