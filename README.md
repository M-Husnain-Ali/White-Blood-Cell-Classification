# White Blood Cell Classification using CNN

## 📌 Project Overview

This project implements a **deep learning model** to classify five types of white blood cells (WBCs) from microscopic images using a Convolutional Neural Network (CNN). Accurate classification of WBCs is essential in medical diagnostics, as variations in their distribution can be indicative of health conditions like infections, allergies, or leukemia.

---

## 🔬 WBC Classes

- Neutrophils  
- Eosinophils  
- Basophils  
- Monocytes  
- Lymphocytes  

---

## 📁 Dataset

- Source: [White Blood Cells Dataset – Kaggle](https://www.kaggle.com/datasets/paultimothymooney/blood-cells)
- Training Images: 10,175 (80/20 split for training and validation)
- Test Images: 4,339
- Total Classes: 5 (as mentioned above)

---

## ⚙️ Methodology

### 🔄 Data Preprocessing
- Resized images to `128x128`
- Normalized pixel values to `[0, 1]`
- Applied data augmentation (rotation, flips, shifts)

### 🧠 CNN Model Architecture
- **4 Convolutional Blocks** with increasing filters: `64 → 128 → 256 → 512`
- Batch Normalization after each conv block
- MaxPooling layers for downsampling
- Dropout layers to prevent overfitting: `0.25 → 0.5`
- 2 Fully Connected Layers: `1024 → 512`
- Output Layer: 5 neurons with Softmax activation

### 🏋️ Training Configuration
- Optimizer: `Adam` with learning rate `0.0005`
- Loss Function: `Categorical Cross-Entropy`
- Batch Size: `32`
- Epochs: `10`
- Callbacks: 
  - Early Stopping
  - ReduceLROnPlateau
  - Model Checkpointing

---

## 📈 Results

### 🔹 Accuracy
- **Training Accuracy:** 39.33% → **93.73%**
- **Validation Accuracy:** 6.73% → **94.94%**
- **Test Accuracy:** `95.00%`

### 🔹 Visualizations
- Confusion Matrix
- Accuracy & Loss Curves
- Sample Predictions with Confidence Scores  
  *Example:* Predicted: **Neutrophil** with **99.67%** confidence

---

## 🛠️ Challenges & Solutions

| Challenge            | Solution                                                  |
|---------------------|-----------------------------------------------------------|
| Overfitting          | Dropout layers, data augmentation                         |
| Class imbalance      | Augmented underrepresented classes                        |
| Model size & training | Used callbacks for efficient training and early stopping |

---

## ✅ Conclusion

The CNN-based architecture achieved **95% test accuracy**, demonstrating its effectiveness for white blood cell classification. This system can potentially assist medical professionals in making faster, more accurate diagnostic decisions.

---

## 🚀 Getting Started

### 📦 Requirements
```bash
tensorflow
numpy
matplotlib
scikit-learn
opencv-python
