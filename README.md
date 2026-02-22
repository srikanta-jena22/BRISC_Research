# BRISC_Research
Research and experimentation repository for the BRISC 2025 Brain Tumor Classification task. This project documents sequential deep learning model development , performance metrics, confusion matrices, learning curves, and comparative analysis. Each model version includes code, results, and detailed experiment notes.

### 🥇 ResNet50 (Baseline CNN)
ResNet50 was implemented as the first baseline model using ImageNet pretrained weights with full fine-tuning.

**Configuration Highlights:**
- Input size: 256×256
- Global Average Pooling
- Dense (256) + Dropout (0.5)
- L2 Regularization
- Adam optimizer (1e-4)
- Data augmentation applied
- EarlyStopping + ReduceLROnPlateau

**Performance:**
- Validation Accuracy: **97.19%**
- Accuracy: 96.79%
- Precision (Macro): 96.77%
- Recall (Macro): 97.03%
- F1-score (Macro): 96.85%

**Key Observations:**
- Strong performance across all classes.
- Minor confusion between Meningioma and Pituitary.
- Stable convergence with minimal overfitting.

📁 Detailed results available in: `/ResNet50`
