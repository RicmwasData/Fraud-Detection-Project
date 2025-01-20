
# Fraud Detection Project

## Overview
This project aims to build a robust fraud detection system using machine learning techniques. The dataset is highly imbalanced, with fraudulent transactions being significantly rarer than legitimate ones. By leveraging various preprocessing steps, Isolation Forest, Local Outlier Factor, neural networks, and evaluation metrics, this project demonstrates a comprehensive approach to solving the fraud detection problem.

---

## Data
The dataset contains transactions made by credit cards in September 2013 by European cardholders. It spans two days, with 492 frauds out of 284,807 transactions, making fraud account for only 0.172% of all transactions. 

### Features:
- **V1 to V28:** Principal components obtained through PCA (original features are not provided for confidentiality reasons).  
- **Time:** Seconds elapsed between each transaction and the first transaction in the dataset.  
- **Amount:** The transaction amount, which can be used for cost-sensitive learning.  
- **Class:** The response variable (1 for fraud, 0 for legitimate transactions).  

Given the class imbalance, the **Area Under the Precision-Recall Curve (AUPRC)** is recommended for evaluation, as confusion matrix accuracy is less meaningful in this context.

---

## Methods

### 1. **Exploratory Data Analysis (EDA)**
EDA involves analyzing and summarizing the dataset's main characteristics, often using visual methods. It helps uncover patterns, identify anomalies, test hypotheses, and check assumptions with statistical summaries and visualizations.

### 2. **Machine Learning Techniques**
#### **Isolation Forest**
- A machine learning technique for anomaly detection based on isolating anomalies rather than profiling normal data points.
- Highly efficient for detecting outliers in high-dimensional datasets.

#### **Local Outlier Factor (LOF)**
- A density-based anomaly detection method that identifies data points with significantly lower densities than their neighbors.
- Measures the local deviation of density for a given data point compared to its neighborhood.

#### **Neural Network**
- A computational model inspired by the human brain, consisting of interconnected nodes (neurons) that process data and learn patterns to make predictions.

---

## Performance Comparison

| Metric               | Isolation Forest | Local Outlier Factor | Neural Network |
|----------------------|------------------|-----------------------|----------------|
| Outliers Detected    | 675              | 935                   | 0              |
| Accuracy             | 0.9976           | 0.9967                | 0.7767         |
| Precision (Class 1)  | 0.31             | 0.05                  | 0.35           |
| Recall (Class 1)     | 0.32             | 0.05                  | 0.78           |
| F1-Score (Class 1)   | 0.31             | 0.05                  | 0.49           |

### Observations:
1. **Isolation Forest:**
   - Performs significantly better than LOF in detecting outliers.
   - Achieves higher precision, recall, and F1-Score for Class 1 with slightly better accuracy.

2. **Local Outlier Factor:**
   - Struggles to identify outliers.
   - Very low precision and recall indicate its ineffectiveness in distinguishing outliers from normal data.

3. **Neural Network:**
   - Achieves the highest recall for Class 1 (0.78), making it the most effective model for identifying actual outliers.
   - F1-Score (0.49) is significantly higher than LOF, showing a better balance between precision and recall.

---

