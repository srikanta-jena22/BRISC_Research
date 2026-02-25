# 🧠 Vision Transformer (ViT-B/16) — BRISC 2025 Brain Tumor Classification

## 📌 Overview

This experiment implements **Vision Transformer (ViT-Base Patch16-224, ImageNet pretrained)** as a transformer-based architecture for multi-class brain tumor classification.

The goal was to evaluate whether self-attention based architectures can outperform convolutional neural networks on MRI tumor classification tasks.

---

## 🗂 Dataset

- 4 Classes:
  - Glioma
  - Meningioma
  - No Tumor
  - Pituitary
- Image Resolution: 224 × 224
- Validation Samples: 1000
- Framework: PyTorch
- Custom Dataset + DataLoader

---

## ⚙️ Model Architecture

- ViT-B/16 backbone (ImageNet pretrained)
- Patch Size: 16 × 16
- 12 Transformer Encoder Layers
- 12 Attention Heads
- Hidden Dimension: 768
- Classification head replaced for 4 classes
- Full fine-tuning enabled

---

## 🔧 Training Configuration

- Optimizer: AdamW (1e-4)
- Loss: CrossEntropyLoss
- Epochs: Up to 100
- EarlyStopping with best model checkpointing
- Data Augmentation:
  - RandomResizedCrop
  - Horizontal Flip
  - Random Rotation
  - Color Jitter

---

## 📊 Final Performance

### 🔹 Validation Accuracy
**99.30%**

### 🔹 Detailed Metrics

| Class       | Precision | Recall | F1-score |
|------------|-----------|--------|----------|
| Glioma     | 0.99      | 1.00   | 0.99     |
| Meningioma | 0.99      | 0.99   | 0.99     |
| No Tumor   | 0.98      | 1.00   | 0.99     |
| Pituitary  | 1.00      | 0.99   | 0.99     |

**Overall Metrics:**

- Accuracy: 99.30%
- Precision (Macro): 99.12%
- Recall (Macro): 99.41%
- F1-score (Macro): 99.26%

---

## 📈 Training Behavior

- Rapid convergence within first few epochs.
- Extremely low validation loss.
- Very small generalization gap.
- Stable optimization with AdamW.
- No significant overfitting observed.

---

## 🧩 Confusion Matrix Insights

- Almost perfect classification across all classes.
- Very minor confusion:
  - Few Meningioma samples misclassified as No Tumor.
  - Rare Pituitary misclassification.

Compared to CNN models, ViT showed reduced inter-class confusion.

---

## ⚠️ Setbacks & Limitations

- Higher computational cost than CNN models.
- Larger memory footprint.
- Requires GPU acceleration for efficient training.
- Transformer models are heavier for deployment scenarios.

---

## 📁 Files Included

- `vit_99.3.ipynb`
- `confusion_matrix.npy`
- `metrics.csv`
- `predictions.csv`
