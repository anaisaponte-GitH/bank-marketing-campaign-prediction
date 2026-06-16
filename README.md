# Bank Marketing Campaign Prediction

## Overview

This project applies Machine Learning techniques to predict whether a customer is likely to subscribe to a term deposit offered through a bank marketing campaign.

The objective is not simply to maximize prediction accuracy, but to improve the identification of potential customers who are more likely to respond positively to marketing efforts, helping financial institutions optimize campaign performance and resource allocation.

---

## Business Problem

Marketing campaigns can be expensive and often reach thousands of customers with very low conversion rates.

Being able to identify customers with a higher probability of subscribing to a product allows organizations to:

- Improve campaign effectiveness.
- Reduce acquisition costs.
- Prioritize high-value leads.
- Optimize marketing resources.
- Increase return on investment (ROI).

This project demonstrates how Machine Learning can support data-driven marketing decisions.

---

## Dataset

The project uses the **Bank Marketing Dataset**, which contains customer demographic information, financial data and campaign-related variables.

Examples of features include:

- Age
- Job
- Marital status
- Education
- Housing loan
- Personal loan
- Contact type
- Campaign duration
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

### 2. Data Preparation

Data preprocessing included:

- Feature encoding.
- Feature scaling using StandardScaler.
- Train/Test split.
- Handling class imbalance.

### 3. Logistic Regression Modeling

Several Logistic Regression models were evaluated:

- Baseline model.
- Class-balanced model.
- Hyperparameter-tuned model using GridSearchCV.

### 4. Threshold Optimization

Different classification thresholds were analyzed to improve recall and better identify customers likely to subscribe.

### 5. Model Evaluation

Performance was assessed using:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC Curve
- Confusion Matrix

---

## Results

The project highlighted the importance of balancing business objectives against traditional performance metrics.

While the baseline model achieved high overall accuracy, it struggled to identify customers who actually subscribed.

By applying class balancing and threshold optimization:

- Recall increased significantly.
- More potential subscribers were correctly identified.
- The model became more useful from a business perspective.

### Key Insight

For marketing campaigns, missing a potential customer can be more costly than contacting a customer who ultimately declines the offer.

For this reason, improving recall was prioritized over maximizing overall accuracy.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-Learn
- Matplotlib
- Seaborn
- GridSearchCV

---

## Repository Structure

```text
bank-marketing-campaign-prediction/
│
├── README.md
│
├── src/
│   └── 01-logistic-regression-bank-marketing-campaign-data.ipynb
│
└── raw/
    └── bank-marketing-campaign-data.csv
```

---

## Key Learnings

- End-to-end Machine Learning workflow.
- Customer response prediction.
- Handling imbalanced datasets.
- Logistic Regression optimization.
- Threshold tuning for business objectives.
- Translating model performance into business value.

---

## Author

**Anaís Aponte**

Senior Product Owner | Agile Delivery | Data & AI

GitHub: https://github.com/anaisaponte-GitH

LinkedIn: https://linkedin.com/in/anaisaponte
