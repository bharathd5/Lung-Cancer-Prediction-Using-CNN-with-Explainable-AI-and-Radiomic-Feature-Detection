# Lung-Cancer-Prediction-Using-CNN-with-Explainable-AI-and-Radiomic-Feature-Detection
Deep learning framework integrating CNN, radiomic features, and explainable AI (Grad-CAM, LIME) for lung cancer diagnosis using CT scans.
# 🫁 Lung Cancer Prediction Using CNN with Explainable AI and Radiomic Feature Detection

This project presents a **deep learning framework** for early **lung cancer detection** using CT images.  
It integrates **Convolutional Neural Networks (CNNs)**, **radiomic feature extraction**, and **Explainable AI (XAI)** techniques (Grad-CAM & LIME) to provide interpretable, clinically meaningful predictions.

---

## 📌 Project Overview

Lung cancer is one of the most fatal diseases worldwide, and early detection greatly improves survival outcomes.  
Traditional biopsy-based diagnosis is invasive, so this project proposes a **non-invasive**, imaging-based method for diagnosis using CT scans.

The proposed model:
- Utilizes a CNN architecture for classification (benign, malignant, normal)
- Integrates **radiomic features** from **intranodular** and **perinodular** regions
- Applies **class imbalance correction (SMOTE)**
- Uses **XAI visualization** (Grad-CAM, LIME) to explain model reasoning

---

## 🧠 Objectives
- Detect and classify lung nodules using deep learning.
- Enhance performance using **radiomic feature fusion**.
- Handle class imbalance via **SMOTE oversampling**.
- Provide **explainable visual insights** for clinical interpretability.

---

## 🧪 Dataset and Preprocessing

- **Dataset:** IQ-OTH/NCCD Lung Cancer Dataset (Kaggle)
- **Total Images:** 1,097 CT images  
  - 561 Malignant  
  - 120 Benign  
  - 416 Normal
- **Preprocessing Steps:**
  - DICOM → PNG conversion  
  - Resizing to 224×224×3  
  - Normalization and histogram equalization  
  - Weak segmentation (CAUnet) for radiomic extraction

---

## 🧩 Model Architecture and Features

### 🧬 CNN Variants Tested
1. **Model 1:** CNN + Data Augmentation  
2. **Model 2:** CNN + Class Weighting  
3. **Model 3:** CNN + SMOTE (Synthetic Minority Oversampling)

### 🧮 Radiomic Features
**Intranodular Features:**
- Texture: GLCM contrast, correlation, energy, homogeneity  
- Shape: Sphericity, irregularity  
- Intensity: Mean, skewness, kurtosis  

**Perinodular Features:**
- Vascularity: Vessel orientation dispersion  
- Margins: Edge sharpness, spiculation index  
- Texture: Regional entropy, Gabor features  

---

## 🧾 Performance Summary

| Model | Accuracy | Sensitivity | Specificity | Remarks |
|--------|-----------|-------------|--------------|----------|
| CNN + Augmentation | 98.20% | 93.00% | 96.50% | Limited imbalance correction |
| CNN + Class Weighting | 99.10% | 94.20% | 94.20% | Moderate improvement |
| CNN + SMOTE | 92.00% | 91.00% | 91.00% | Optimal real-world balance |

**Final Results:**
- **SVM Model:** 83.00% accuracy  
- **Random Forest Model:** 80.00% accuracy  
- **Radiomic + CNN Integration:** Improved specificity by 3–5%  

---

## 🎯 Explainable AI (XAI)

**1️⃣ Grad-CAM:**  
Highlights regions of interest corresponding to malignant nodules.

**2️⃣ LIME:**  
Generates local, interpretable explanations of CNN predictions.

**Clinical Insight:**  
Grad-CAM and LIME highlighted the same intranodular and perinodular regions where radiomics reported high F6 (heterogeneity) and F8 (edge sharpness) scores, confirming biological plausibility.

---

## 🧰 Installation and Usage

### 🧱 Requirements
Install dependencies via:
```bash
pip install -r requirements.txt

