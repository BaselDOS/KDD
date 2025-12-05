# Human Activity Recognition (HAR) – Full KDD Pipeline  
### Machine Learning • Classification • Clustering • PCA • Sensor Data Analysis

This project presents a complete implementation of the **KDD (Knowledge Discovery in Databases)** methodology applied to the well-known **Human Activity Recognition (UCI-HAR)** dataset.  
The goal is to explore, model, interpret, and extract meaningful insights from high-dimensional motion sensor data collected from smartphone accelerometer and gyroscope measurements.

---

## 📌 Project Overview

The project follows **all stages of the KDD process**, including:

1. **Selection & Understanding**  
2. **Preprocessing & Cleaning**  
3. **Transformation & Feature Engineering**  
4. **Supervised Learning (Classification)**  
5. **Unsupervised Learning (Clustering)**  
6. **Evaluation & Interpretation**

Both **classification models** and **clustering models** were built to examine whether the intrinsic structure of the dataset aligns with human activity categories — even without supervision.

---

## 📂 Dataset

**UCI Human Activity Recognition (HAR)**  
Link: https://www.kaggle.com/datasets/drsaeedmohsen/ucihar-dataset/data

- 30 participants wearing a smartphone on their waist  
- Accelerometer & gyroscope readings  
- Over **560 features extracted**  
- Activities (Target classes):
  - 1 – Walking  
  - 2 – Walking Upstairs  
  - 3 – Walking Downstairs  
  - 4 – Sitting  
  - 5 – Standing  
  - 6 – Laying  

---

## 🧹 Stage 1–3: Preprocessing, Cleaning & Feature Transformation

### ✔ Performed steps:
- Missing values check → **no missing data**
- Duplicate sample check → **no duplicates found**
- Outlier analysis using IQR  
- Standardization of all continuous features  
- Dimensionality reduction using **PCA**
- Selection of **15 dominant features** using feature variance + PCA loadings

### ✔ Visualizations:
- Histograms  
- Boxplots  
- Correlation heatmap  
- PCA explained variance  

---

## 🤖 Stage 4: Supervised Learning (Classification)

Three classification models were trained:

| Model | Accuracy | Precision | Recall | F1 | AUC |
|-------|----------|-----------|--------|----|------|
| **Decision Tree** | Good | Moderate | Moderate | Moderate | - |
| **Random Forest** | Higher | High | High | High | - |
| **SVM** | **Best** | **Highest** | **Highest** | **Highest** | **Highest** |

### ✔ Key Findings
- **SVM** achieved the strongest results across all metrics.  
- The dataset contains clear discriminative structure separating static vs. dynamic activities.  
- Decision Tree interpretability was explored via zoomed-in subtree visualizations.

---

## 🔍 Stage 5: Unsupervised Learning (K-Means Clustering)

### ✔ Optimal number of clusters: **K = 4**  
(According to the **Elbow Method**)  

### ✔ Visualizations:
- PCA 2D projection of cluster assignments  
- Dominant-feature scatter plots with KDE contours  
- t-SNE projection for improved 2D cluster separation  

### ✔ Cluster Interpretability  
Clusters showed **strong alignment** with true activity labels:

- **Cluster 0:** Sitting & Standing (static)  
- **Cluster 1:** Walking & transitions (dynamic)  
- **Cluster 2:** Walking/Walking Downstairs (dynamic)  
- **Cluster 3:** Almost entirely Laying (very pure cluster)  

---

## 🧠 Stage 6: Final Evaluation  
The unsupervised clustering results support the conclusions from classification:

- Both supervised and unsupervised models identified similar structures in the feature space.  
- Static vs. dynamic activities form well-separated groups.  
- K-Means produced **interpretable and meaningful** clusters, confirming that the dataset is highly structured.  

---

## 📊 Project Structure

