# 🫁 Chest X-Ray Pneumonia Detection using Deep Learning

## 📌 Project Overview
This project implements a **Deep Learning based Pneumonia Detection System** using **Chest X-Ray images**.  
A **hybrid approach** is used where a pretrained CNN is combined with a machine learning classifier to improve performance.

- **MobileNetV2 (CNN)** is used for feature extraction  
- **SVM (Support Vector Machine)** is used for classification  

The model classifies X-ray images into two classes:
- **PNEUMONIA**
- **NORMAL**

The project also includes **image quality analysis** (blur & contrast check) and **confidence-aware diagnosis**, making it more practical for real-world medical use cases.

---

## 🎯 Problem Statement
Manual diagnosis of pneumonia from chest X-rays:
- Requires expert radiologists  
- Is time-consuming  
- Can be affected by poor image quality  

This project explores how **deep learning features combined with machine learning** can automate pneumonia detection and assist medical professionals.

---

## 📂 Dataset
- Dataset: **Chest X-Ray Pneumonia Dataset**
- Source: Kaggle (`paultimothymooney/chest-xray-pneumonia`)
- Loaded using **KaggleHub**

---

## 🏋️ Model Training
- Feature Extractor: **MobileNetV2 (Pretrained, Frozen)**
- Dimensionality Reduction: **PCA**
- Classifier: **SVM (RBF Kernel)**
- Hyperparameter tuning using **GridSearchCV**

---

## 📊 Model Performance
- **Accuracy:** ~89.10%
- **Precision:** ~93.05%
- **Recall (Sensitivity):** ~89.23%
- **F1 Score:** ~91.09%
- **ROC-AUC:** ~0.9519
- **Specificity:** ~88.89%

---

## ⚖️ Threshold Optimization
- Optimized threshold used instead of default 0.5  
- **Best Threshold:** ~0.847  
- Helps balance false positives and false negatives  

---

## 🔍 Image Quality Analysis
Before prediction, image quality is checked using:
- **Blur Detection** (Laplacian Variance)
- **Contrast Analysis** (Standard Deviation)

---

## 🧠 Confidence-Aware Diagnosis
Prediction probability is interpreted as:

- `> 0.8` → 🫁 Pneumonia Detected (High Confidence)  
- `0.6 – 0.8` → Pneumonia Detected (Low Confidence – Doctor Review Recommended)  
- `0.4 – 0.6` → Uncertain Case – Further Medical Tests Needed  
- `< 0.4` → ✅ Normal (High Confidence)
