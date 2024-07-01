# Breast-Cancer-Prediction-Using-ML-models
The goal of the project is to create predictive models that can classify breast masses as malignant or benign using predefined characteristics.


## Introduction

Breast cancer is a widespread and deadly illness that impacts millions of people globally. Diagnosing at an early stage with precision is essential for enhancing patient outcomes and influencing treatment choices. Recently, especially in the past few years, machine learning techniques have gained significant attention. This project aims to implement ML models for detecting breast cancer, utilizing the Breast Cancer dataset sourced from the CCO public domain.

## Overview of the Dataset

We used a publicly available dataset, "Breast Cancer - Exploring Cell Nuclei Characteristics for Enhanced Understanding Breast Cancer," for the study. This dataset contains features computed from digitized images of breast mass fine needle aspirates, describing characteristics of cell nuclei present in the images. The target variable indicates whether the mass is malignant (M) or benign (B).

**Dataset Characteristics:**

- **Size:** 
  - The dataset comprises 569 samples and 32 features, including ID and target.
  - It has 212 malignant and 357 benign data samples.

- **Features:**
  - The dataset consists of 30 features, each representing a different aspect of breast tumor characteristics.
  - Key features include:
    - **Radius:** The average distance from the center to the boundary of the tumor cell.
    - **Texture:** The variation in grey-level intensities in the image.
    - **Perimeter:** The length of the boundary of the tumor cell.
    - **Area:** The total area occupied by the tumor cell.
    - **Smoothness:** The variation in local surface roughness of the cell boundary.
    - **Compactness:** A measure of how closely the cell resembles a sphere.
    - **Concavity:** The severity of concave portions of the tumor cell boundary.
    - **Concave Points:** The number of concave portions in the tumor cell boundary.

- **Target Variable:** 
  - The 'diagnosis' column indicates the classification as malignant or benign.

## Analysis and Conclusion

## ANOVA Test

We employed ANOVA feature selection to identify important features for distinguishing between tumor types. High F-scores indicated significant features such as radius, perimeter, and area, which provide crucial information about tumor size. Malignant tumors typically have larger radii, perimeters, and areas compared to benign ones. Features like compactness, concavity, and concave points highlight the irregular shapes of malignant tumors.

### Data Augmentation

The dataset was imbalanced with fewer malignant samples. To address this, we used SMOTETomek for oversampling, which balanced the dataset and improved model performance, especially recall for the malignant class. This led to better precision, recall, and F1-scores for both classes, reflecting improved classification accuracy.

### Best Model

We tested logistic regression, decision trees, random forests, K-nearest neighbors, and SVM using K-fold cross-validation. Before data augmentation, SVM performed best due to its ability to handle non-linear relationships:

| Model                | Accuracy |
|----------------------|----------|
| Logistic Regression  | 0.9363   |
| Decision Tree        | 0.9231   |
| Random Forest        | 0.9429   |
| K-Nearest Neighbors  | 0.9319   |
| SVM                  | 0.9473   |

After augmentation, Random Forest emerged as the best-performing model due to its ensemble learning technique, which improved its ability to generalize:

| Model                | Accuracy |
|----------------------|----------|
| Logistic Regression  | 0.9569   |
| Decision Tree        | 0.9334   |
| Random Forest        | 0.9587   |
| K-Nearest Neighbors  | 0.9371   |
| SVM                  | 0.9551   |

Random Forest's enhanced generalization ability and reduced overfitting contributed to its superior performance after augmentation, despite a small difference in accuracy (0.003%) compared to SVM.

