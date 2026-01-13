# 🫁 Chest X-Ray Pneumonia Detection using Deep Learning

## 📌 Project Overview
This project implements a **Deep Learning based Pneumonia Detection System** using **Chest X-Ray images**.  
A **Convolutional Neural Network (CNN)** is trained to classify X-ray images into two classes:
- **PNEUMONIA**
- **NORMAL**

The project also includes **image quality analysis** (blur & contrast check) and **confidence-aware diagnosis**, making it more practical for real-world medical use cases.

---

## 🎯 Problem Statement
Manual diagnosis of pneumonia from chest X-rays:
- Requires expert radiologists  
- Is time-consuming  
- Can be affected by poor image quality  

This project explores how **CNNs can automate pneumonia detection** and assist medical professionals.
---
## 📂 Dataset
- Dataset: **Chest X-Ray Pneumonia Dataset**
- Source: Kaggle (`paultimothymooney/chest-xray-pneumonia`)
- Loaded using **KaggleHub**
---
## 🏋️ Model Training
- Optimizer: **Adam**
- Loss Function: **Binary Crossentropy**
- Metric Used: **Accuracy**
- Epochs: **5**
- Batch Size: **32**
---
## 📊 Training Results
After 5 epochs of training:
- **Training Accuracy:** ~91%
- **Validation Accuracy:** ~82%
- Accuracy and loss curves are plotted for:
  - Training vs Validation Accuracy  
  - Training vs Validation Loss  

## 🔍 Image Quality Analysis
Before prediction, image quality is checked using:
- **Blur Detection** (Laplacian Variance)
- **Contrast Analysis** (Standard Deviation)

## 🧠 Confidence-Aware Diagnosis
Prediction probability is interpreted as:

- `> 0.8` → 🫁 Pneumonia Detected (High Confidence)  
- `0.6 – 0.8` → Pneumonia Detected (Low Confidence – Doctor Review Recommended)  
- `0.4 – 0.6` → Uncertain Case – Further Medical Tests Needed  
- `< 0.4` → ✅ Normal (High Confidence)
