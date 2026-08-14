# insurance-fraud-detection-analysis

## Project Overview

This project investigates the use of machine learning techniques to identify potentially fraudulent insurance claims.

The analysis uses two publicly available insurance datasets:

1. **Insurance Claims Dataset**
2. **Fraud Oracle Dataset**

Two machine learning models were applied to both datasets:

- Logistic Regression
- Random Forest

The project compares model performance and examines whether different insurance datasets provide complementary or contradictory insights into fraud detection.

---

## Business Problem

Insurance companies need to identify potentially fraudulent claims to reduce financial losses and support more effective claims investigations.

The objective of this project is to build machine learning models that can classify insurance claims as fraudulent or non-fraudulent based on customer, policy, accident, vehicle, and claim-related information.

---

## Datasets

### 1. Insurance Claims Dataset

- Approximately 1,000 insurance claim records
- 40 attributes
- Target variable: `fraud_reported`

The dataset includes information such as:

- Customer age
- Policy details
- Annual premium
- Incident type
- Incident severity
- Claim amounts
- Vehicle information

### 2. Fraud Oracle Dataset

- 15,420 records
- 33 attributes
- Target variable: `FraudFound_P`

The dataset includes:

- Policy information
- Vehicle characteristics
- Driver information
- Accident details
- Claim characteristics

---

## Machine Learning Models

The following models were used:

### Logistic Regression

Logistic Regression was used as a baseline classification model to predict whether an insurance claim was fraudulent.

### Random Forest

Random Forest was used to capture more complex and non-linear relationships between the variables.

---

## Data Preparation

The datasets were prepared using the following steps:

- Handling missing values
- Separating features and target variables
- Splitting data into training and testing sets
- Using an 80% training and 20% testing split
- Standardising numerical variables
- Applying one-hot encoding to categorical variables

---

## Model Evaluation

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- ROC Curve
- Area Under the Curve (AUC)

Accuracy alone can be misleading when fraudulent claims are rare. Therefore, particular attention was given to recall and F1-score.

Recall measures how many actual fraudulent claims were correctly identified, while the F1-score provides a balance between precision and recall.

---

## Results

### Insurance Claims Dataset

| Model | Accuracy | Precision | Recall | F1-score |
|---|---:|---:|---:|---:|
| Logistic Regression | 0.79 | 0.60 | 0.43 | 0.50 |
| Random Forest | 0.74 | 0.36 | 0.08 | 0.13 |

Logistic Regression performed better than Random Forest when identifying fraudulent claims.

It correctly identified approximately 43% of fraudulent claims, compared with approximately 8% for Random Forest.

---

### Fraud Oracle Dataset

| Model | Accuracy | Precision | Recall | F1-score |
|---|---:|---:|---:|---:|
| Logistic Regression | 0.94 | 0.67 | 0.01 | 0.02 |
| Random Forest | 0.94 | 1.00 | 0.01 | 0.01 |

Both models achieved high accuracy but identified very few fraudulent claims.

This demonstrates that high accuracy does not necessarily mean that a model performs well for fraud detection, particularly when the dataset is highly imbalanced.

---

## ROC Curve Results

ROC curves were used to compare the ability of Logistic Regression and Random Forest to distinguish between fraudulent and non-fraudulent claims.

### Insurance Claims Dataset

- Logistic Regression AUC: **0.82**
- Random Forest AUC: **0.84**

### Fraud Oracle Dataset

- Logistic Regression AUC: **0.81**
- Random Forest AUC: **0.85**

The ROC curves show that both models can distinguish between classes better than random classification. However, the classification results demonstrate that AUC should be considered alongside recall and F1-score, especially in imbalanced fraud detection problems.

---

## Key Findings

- Logistic Regression performed better than Random Forest based on recall and F1-score for the Insurance Claims dataset.
- Both datasets provided useful insights into insurance fraud detection.
- The Fraud Oracle dataset demonstrated the problem of relying only on accuracy when fraudulent cases are rare.
- High accuracy did not necessarily result in effective fraud detection.
- Recall and F1-score were more appropriate metrics because the objective was to identify fraudulent claims.
- The datasets provided complementary insights by demonstrating how class imbalance can significantly affect model performance.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Jupyter Notebook

---

## Repository Structure

```text
insurance-fraud-detection-analysis/
│
├── insurance_fraud_detection_analysis.ipynb
├── README.md
└── figures/
    ├── insurance_claims_roc_curve.png
    └── fraud_oracle_roc_curve.png
