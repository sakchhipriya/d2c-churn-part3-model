# D2C Customer Churn Capstone - Part 3

## Churn Prediction Model & Model Card

### Project Objective

The objective of this project is to predict whether a customer is likely to churn within the next 60 days. The model is intended to support proactive retention strategies and customer risk management.

---

## Dataset

The analysis uses the provided D2C Customer Churn modeling dataset.

The target variable is:

* `churn_next_60d`

---

## Leakage Prevention

Only features available on or before the customer snapshot date were used for model training.

No future customer behaviour or target-window information was included as model input.

---

## Modeling Approach

### Baseline Model

* Logistic Regression

### Strong Model

* Random Forest Classifier

Random Forest was selected as the final production candidate because it achieved superior predictive performance across all major evaluation metrics.

---

## Model Performance

| Metric    | Value |
| --------- | ----- |
| Accuracy  | 0.789 |
| Precision | 0.809 |
| Recall    | 0.756 |
| F1 Score  | 0.782 |
| ROC-AUC   | 0.881 |

### Selected Threshold

* 0.50

This threshold provides a balance between precision and recall while supporting practical retention decision-making.

---

## Important Features

Top predictive features include:

* recency_days
* last_visit_days_ago
* monetary_180d
* frequency_180d
* product_views_30d
* avg_discount_pct_180d
* sessions_30d
* days_since_signup
* category_diversity_180d
* avg_rating_180d

---

## Repository Contents

* `churn_model.ipynb`
* `model.pkl`
* `metrics.json`
* `error_analysis.md`
* `model_card.md`
* `requirements.txt`

---

## Loading the Saved Model

The trained Random Forest model can be loaded using the following code:

```python
import joblib

model = joblib.load("model.pkl")
```

Example prediction:

```python
prediction = model.predict(X_new)
probability = model.predict_proba(X_new)
```

---

## Tools & Libraries

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Joblib

---

## Outcome

The final Random Forest model achieved strong classification performance and provides a practical framework for identifying customers at risk of churn, enabling targeted retention interventions.
