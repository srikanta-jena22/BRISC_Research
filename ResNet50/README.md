# 🧠 ResNet50 — BRISC 2025 Brain Tumor Classification

## 📌 Overview
This experiment implements **ResNet50** for the BRISC 2025 brain tumor classification task.  

## 🗂 Dataset
- 4 Classes:
  - Glioma
  - Meningioma
  - No Tumor
  - Pituitary
- Input Resolution: **256 × 256**
- Validation Split: **20%**
- Total Validation Samples: **998**

## ⚙️ Model Architecture
- Backbone: `ResNet50` 
- Global Average Pooling
- Batch Normalization
- Dense (256 units, ReLU)
- Dropout (0.5)
- L2 Regularization (1e-3)
- Output Layer: Softmax (4 classes)

## 🔧 Training Configuration
- Optimizer: Adam (learning rate = 1e-4)
- Loss: Sparse Categorical Crossentropy
- Epochs: 100
- EarlyStopping (patience=10)
- ReduceLROnPlateau
- Data Augmentation:
  - Rotation
  - Width and Height Shift
  - Shear
  - Zoom
  - Brightness adjustment
  - Horizontal flip

## 📊 Final Performance
### 🔹 Validation Accuracy
**97.19%**
### 🔹 Overall Metrics
| Metric      | Score |
|-------------|--------|
| Accuracy    | 96.79% |
| Precision   | 96.77% |
| Recall      | 97.03% |
| F1-score    | 96.85% |

## 📈 Training Behavior
- Rapid convergence within first 10–15 epochs.
- Stable validation performance.
- Minimal overfitting observed.
- Learning rate reduction improved stability.

## 🧩 Confusion Matrix Analysis
- Glioma classified almost perfectly.
- No Tumor achieved perfect recall.
- Minor confusion between:
  - Meningioma ↔ Pituitary
This indicates strong feature discrimination with slight overlap between specific tumor types.

## 📁 Files in This Folder
- `resnet50.ipynb` — Full training notebook
- `training_curves.png` — Accuracy & Loss curves
- `confusion_matrix.png` — Confusion matrix heatmap
- `metrics.csv` — Detailed classification metrics

## 📌 Key Takeaways
- ResNet50 performs extremely well on this dataset.
- Fine-tuning the full network improves classification power.
- Regularization and augmentation effectively reduce overfitting.
- Suitable as a strong baseline model for comparison.

