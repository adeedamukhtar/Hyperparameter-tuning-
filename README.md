# Heart Disease Prediction Using Supervised Machine Learning

## Project Overview

This project implements and compares three supervised learning models—Support Vector Machine (SVM), Random Forest (RF), and Gradient Boosting Machine (GBM)—to predict the presence of heart disease using patient health indicators such as age, cholesterol, blood pressure, and exercise-induced angina. The goal is to evaluate model effectiveness using real-world healthcare data and understand the impact of hyperparameter tuning.

---

##  Dataset
The dataset used in this study was obtained from the UCI Machine Learning Repository (Dua & Graff, 2019).
- **Source:** [UCI Heart Disease Dataset](https://archive.ics.uci.edu/ml/datasets/Heart+Disease)
- **Used File:** `processed.cleveland.data`
- **Target Variable:** `target` (1 = heart disease present, 0 = absent)
- **Features:** `age`, `sex`, `cp`, `trestbps`, `chol`, `fbs`, `restecg`, `thalach`, `exang`, `oldpeak`, `slope`, `ca`, `thal`

---

##  Data Preparation

- Replaced `'?'` with `NaN` and converted all columns to numeric.
- Dropped rows with missing values.
- Converted target values > 0 to 1 (binary classification).
- Split dataset into 80% training and 20% testing.

---

##  Models Implemented

1. **Support Vector Machine (SVM)**
2. **Random Forest Classifier**
3. **Gradient Boosting Machine (GBM)**

---

##  Hyperparameter Tuning

- Used `GridSearchCV` to tune key parameters:
  - **SVM:** `C`, `kernel`
  - **Random Forest:** `n_estimators`, `max_depth`
  - **GBM:** `n_estimators`, `learning_rate`, `max_depth`

---

##  Model Performance

| Model             | Training Acc. | Test Acc. | Precision | Recall | F1 Score | AUC-ROC |
|-------------------|---------------|-----------|-----------|--------|----------|---------|
| **SVM**           | 0.64          | 0.85      | 0.88      | 0.79   | 0.83     | **0.96** |
| **Random Forest** | 1.00          | 0.85      | 0.88      | 0.79   | 0.83     | 0.95    |
| **GBM**           | 0.99          | 0.82      | 0.87      | 0.71   | 0.78     | 0.91    |

 **SVM had the best test AUC-ROC and generalization**, while RF and GBM slightly overfit the training data.

---

##  Challenges

- Cleaning and parsing data with missing values (`?`)
- Avoiding overfitting in ensemble models
- Balancing precision and recall due to healthcare domain sensitivity

---

##  Key Learnings

- Hyperparameter tuning significantly improved model generalization.
- AUC-ROC is more informative than accuracy for imbalanced healthcare datasets.
- Simpler models like SVM can outperform complex ones if properly tuned.

---

##  References

Dua, D., & Graff, C. (2019). UCI Machine Learning Repository: Heart Disease Data Set. University of California, Irvine, School of Information and Computer Sciences. https://archive.ics.uci.edu/ml/datasets/Heart+Disease
---


