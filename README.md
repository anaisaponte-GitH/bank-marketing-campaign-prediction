# Bank Marketing Campaign Prediction

## Overview

This project applies Machine Learning classification techniques to predict whether a customer is likely to subscribe to a term deposit offered through a bank marketing campaign.

The objective is not only to maximize overall accuracy, but to improve the identification of potential customers who are more likely to respond positively to the campaign.

This is especially relevant in marketing contexts where conversion rates are usually low and business value depends on identifying high-potential leads.

---

## Business Problem

Marketing campaigns can be expensive and often reach thousands of customers with very low conversion rates.

Being able to identify customers with a higher probability of subscribing to a financial product allows organizations to:

- Improve campaign effectiveness.
- Reduce acquisition costs.
- Prioritize high-value leads.
- Optimize marketing resources.
- Increase return on investment (ROI).

This project demonstrates how Machine Learning can support data-driven marketing decisions.

---

## Dataset

The project uses the Bank Marketing Dataset, which contains customer demographic information, financial data and campaign-related variables.

Examples of features include:

- Age
- Job
- Marital status
- Education
- Housing loan
- Personal loan
- Contact type
- Previous campaign outcomes

### Target Variable

- **Yes** → Customer subscribed to the term deposit.
- **No** → Customer did not subscribe.

---

## Methodology

### 1. Exploratory Data Analysis (EDA)

The dataset was explored to understand:

- Customer demographics.
- Class distribution.
- Feature relationships.
- Potential data quality issues.
- Variables that could introduce data leakage.

### 2. Data Preparation

Data preprocessing included:

- Categorical feature encoding.
- Train/Test split.
- Feature scaling using StandardScaler.
- Handling class imbalance.
- Removal of variables that could introduce data leakage, such as `duration`.

### 3. Baseline Logistic Regression Model

A baseline Logistic Regression model was trained to evaluate the initial classification performance.

Although the baseline model achieved high overall accuracy, it performed poorly when identifying customers who actually subscribed to the campaign.

This highlighted the importance of looking beyond accuracy in imbalanced classification problems.

### 4. Class Imbalance Handling

The dataset was highly imbalanced, with significantly fewer customers subscribing to the term deposit.

To address this, a class-balanced Logistic Regression model was trained using:

```python
class_weight='balanced'
```

This significantly improved the model's ability to detect the positive class (`yes`), which is more relevant from a marketing perspective.

### 5. Hyperparameter Optimization

GridSearchCV was used to optimize the Logistic Regression model.

The search focused on improving recall for the positive class (`yes`), since identifying potential subscribers was more valuable than simply maximizing overall accuracy.

Best parameters found:

```text
C = 0.01
solver = liblinear
```

### 6. Threshold Analysis

Different classification thresholds were evaluated to understand the trade-off between precision and recall.

This step was important because, in a marketing campaign, the business may prefer contacting more potential customers even if this increases the number of false positives.

---

## Model Evaluation

### Performance Comparison

| Model | Accuracy | Precision (Yes) | Recall (Yes) | F1-Score (Yes) |
|---|---:|---:|---:|---:|
| Baseline Logistic Regression | 0.90 | 0.71 | 0.21 | 0.32 |
| Scaled Logistic Regression | 0.90 | 0.69 | 0.22 | 0.34 |
| Class-Balanced Logistic Regression | 0.84 | 0.37 | 0.65 | 0.47 |
| GridSearchCV Optimized Model | 0.83 | 0.36 | 0.65 | 0.46 |

### ROC AUC

```text
ROC AUC: 0.8007
```

---

## Threshold Evaluation

The optimized model was also evaluated using different decision thresholds.

| Threshold | Accuracy | Precision (Yes) | Recall (Yes) | F1-Score (Yes) |
|---|---:|---:|---:|---:|
| 0.3 | 0.89 | 0.51 | 0.44 | 0.47 |
| 0.4 | 0.90 | 0.59 | 0.32 | 0.41 |
| 0.5 | 0.90 | 0.69 | 0.22 | 0.34 |
| 0.6 | 0.90 | 0.74 | 0.18 | 0.28 |

---

## Final Model Selection

After evaluating multiple approaches, the class-balanced and optimized Logistic Regression models showed the most relevant improvement for the business objective.

The baseline model achieved higher overall accuracy, but it failed to identify most customers who subscribed to the campaign.

By applying class balancing, recall for the positive class increased from approximately 0.21 to 0.65.

This means the model became significantly better at identifying potential subscribers, even at the cost of lower precision.

For this business problem, this trade-off is acceptable because missing a potential customer can be more costly than contacting a customer who does not subscribe.

---

## Key Findings

- Accuracy alone was not a sufficient metric due to class imbalance.
- The baseline model achieved high accuracy but had very low recall for the positive class.
- Class balancing was the most impactful improvement.
- GridSearchCV confirmed a valid optimized configuration but did not significantly improve performance beyond class balancing.
- Threshold tuning helped analyze the trade-off between precision and recall.
- For campaign optimization, recall is more relevant than overall accuracy.

---

## Results

The project demonstrated how Logistic Regression can be used to support marketing campaign optimization.

The final approach improved the model's ability to identify customers likely to subscribe to a term deposit, making the solution more useful from a business perspective.

This project highlights the importance of aligning Machine Learning evaluation metrics with business objectives rather than relying only on generic performance indicators.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-Learn
- Matplotlib
- Seaborn
- Logistic Regression
- StandardScaler
- GridSearchCV
- ROC AUC
- Jupyter Notebook
- Joblib

---

## Repository Structure

```text
bank-marketing-campaign-prediction/
│
├── README.md
│
├── raw/
│   └── bank-marketing-campaign-data.csv
│
└── src/
    └── 01-logistic-regression-bank-marketing-campaign-data.ipynb
```

---

## Key Learnings

- End-to-end Machine Learning workflow.
- Binary classification for customer response prediction.
- Handling imbalanced datasets.
- Logistic Regression optimization.
- Hyperparameter tuning with GridSearchCV.
- Threshold tuning for business objectives.
- Avoiding data leakage during model preparation.
- Translating model performance into business value.

---

## Author

**Anaís Aponte**

Senior Product Owner | Agile Delivery | Data & AI

GitHub: https://github.com/anaisaponte-GitH

LinkedIn: https://linkedin.com/in/anaisaponte
