# FIFA Player Value Prediction using Machine Learning ⚽

## Project Overview

This project focuses on predicting FIFA players' **market value** and **performance tier** using Machine Learning models.

The goal is to compare different machine learning approaches and build an optimized ensemble model that can learn complex patterns from player statistics.

---

## Dataset

The dataset contains FIFA player information such as:

* Age
* Overall Rating
* Potential
* Position
* Player attributes
* Market Value

### Data Preprocessing

The following preprocessing steps were applied:

* Removed players with zero market value
* Dropped unnecessary columns
* Applied One-Hot Encoding for categorical features
* Handled outliers using IQR clipping
* Applied StandardScaler normalization
* Split data into training and testing sets

---

# Machine Learning Tasks

## 1. Regression Task

### Objective:

Predict FIFA player market value.

### Models Used:

* KNN Regressor
* Support Vector Regression (SVR) with RBF Kernel
* Random Forest Regressor

Evaluation Metrics:

* R² Score
* MAE
* RMSE

---

## 2. Classification Task

### Objective:

Classify players into performance tiers.

Classes:

* Low
* Mid
* High
* Elite

### Models Used:

* KNN Classifier
* SVC with RBF Kernel
* Random Forest Classifier

Evaluation Metric:

* Accuracy

---

# Ensemble Learning

To improve performance, different ensemble techniques were applied.

## Bagging

Combines multiple decision trees trained on different samples to reduce overfitting.

Result:

**R² Score: 0.9152**

---

## Voting Regressor

Combines predictions from:

* KNN
* SVR
* Random Forest

The final prediction is based on averaging model outputs.

Result:

**R² Score: 0.6834**

---

## AdaBoost

A boosting technique that trains models sequentially and focuses on previous prediction errors.

Result:

**R² Score: 0.8736**

---

## Stacking Regressor (Best Model)

Stacking combines multiple base models and uses a meta-model to learn the best combination.

Base Models:

* KNN
* SVR
* Random Forest

Meta Model:

* Ridge Regression

Optimization:

* GridSearchCV

Final Performance:

**R² Score: 0.9478 (94.7%)**

---

# Unified Prediction Pipeline

A complete inference pipeline was created to predict both:

1. Player market value
2. Performance tier

The pipeline:

* Applies preprocessing automatically
* Aligns features with training data
* Uses trained models for prediction
* Supports batch prediction for multiple players

Example output:

```json
[
 {
  "predicted_value": 85.5,
  "performance_tier": "Elite"
 }
]
```

---

# Model Stability Evaluation

5-Fold Cross Validation was used to evaluate model reliability.

The evaluation included:

* Mean score
* Standard deviation
* 95% Confidence Interval

This ensures the model performance is stable across different data splits.

---

# Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Matplotlib
* Seaborn
* Jupyter Notebook

---

# Project Structure

```
FIFA-Player-Value-Prediction

│
├── FIFA_Model_Selection.ipynb
├── Fifa.csv
└── README.md
```

---

# How to Run

Clone the repository:

```bash
git clone repository-link
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```
FIFA_Model_Selection.ipynb
```

---

# Author

Hanin Ahmed Galal

Computer and Data Science Student
