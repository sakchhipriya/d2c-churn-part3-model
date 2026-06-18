# Model Card

## Model Name

Customer Churn Prediction Model

## Model Type

Random Forest Classifier

## Intended Use

The model predicts whether a customer is likely to churn within the next 60 days.

The output is intended to support:

- Retention campaigns
- Customer success initiatives
- Churn-risk prioritization
- Marketing decision making

---

## Data Used

The model uses customer-level features created from:

- Customer profile data
- Order history
- Support interactions
- Web activity
- Campaign engagement

Target Variable:

- churn_next_60d

---

## Leakage Prevention

Only information available on or before the customer snapshot date was used.

No future customer behaviour was included during feature preparation.

---

## Model Approach

Two models were evaluated:

1. Logistic Regression (Baseline)
2. Random Forest (Final Model)

Random Forest was selected because it achieved superior predictive performance.

---

## Performance

| Metric | Value |
|----------|----------|
| Accuracy | 0.789 |
| Precision | 0.809 |
| Recall | 0.756 |
| F1 Score | 0.782 |
| ROC-AUC | 0.881 |

---

## Important Features

Top drivers of churn prediction include:

- Recency Days
- Last Visit Days Ago
- Monetary Value
- Purchase Frequency
- Product Views
- Discount Usage
- Sessions
- Days Since Signup

---

## Limitations

- Customer behaviour may change over time.
- Model performance may decline if data distribution shifts.
- Not all churn reasons are observable through transactional data.

---

## Ethical Risks

- Incorrect predictions may lead to unfair retention targeting.
- Over-reliance on model outputs may overlook customer context.
- Human review should be included for high-value customers.

---

## Monitoring Requirements

The model should be monitored regularly for:

- Accuracy
- Recall
- ROC-AUC
- Data drift
- Feature drift

---

## When The Model Should Not Be Used

The model should not be used as the sole basis for customer termination, pricing decisions, or eligibility decisions.

Human review is recommended for high-value and high-risk customer cases.

### Threshold Selection

A probability threshold of 0.50 was selected for churn classification.

This threshold provides a reasonable balance between Precision (80.9%) and Recall (75.6%). A lower threshold would identify more churn-risk customers but increase false positives, while a higher threshold would reduce unnecessary retention actions but risk missing actual churn customers.

From a business perspective, retaining at-risk customers is important, therefore a balanced threshold was chosen to support effective retention campaigns while controlling operational costs.

