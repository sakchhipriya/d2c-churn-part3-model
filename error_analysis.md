# Error Analysis

## Objective

This analysis evaluates prediction errors made by the Random Forest churn prediction model.

The primary focus is on:

- False Positives
- False Negatives

---

## False Positive Analysis

False Positives are customers predicted to churn but who actually did not churn.

### Business Risk

The business may spend retention budget on customers who would have stayed without intervention.

### Sample False Positive Customers

| Customer ID | Churn Prediction Probability | Observation |
|------------|------------|------------|
| CUST00044 | 0.505 | Moderate recency and low purchase frequency may have triggered churn prediction. |
| CUST00109 | 0.668 | Lower engagement signals increased perceived churn risk. |
| CUST00192 | 0.416 | Moderate monetary value and declining activity influenced prediction. |
| CUST00335 | 0.698 | Long recency period created a strong churn signal. |
| CUST00437 | 0.897 | Very high churn probability despite remaining active. |

---

## False Negative Analysis

False Negatives are customers who actually churned but were predicted as non-churn.

### Business Risk

This is the more expensive error because no retention action is taken and the customer may be lost permanently.

### Sample False Negative Customers

| Customer ID | Churn Prediction Probability | Observation |
|------------|------------|------------|
| CUST00184 | 0.056 | Strong recent activity reduced predicted churn risk. |
| CUST00247 | 0.346 | Moderate engagement may have masked churn behaviour. |
| CUST00414 | 0.325 | Recent visits reduced model confidence. |
| CUST00438 | 0.303 | High engagement signals conflicted with churn outcome. |
| CUST00592 | 0.221 | Customer appeared active despite eventual churn. |

---

## Key Findings

- False Negatives create greater business risk than False Positives.
- Recency and web engagement strongly influence model decisions.
- Some churning customers still display active behaviour patterns, making prediction difficult.

## Recommendation

The business should continuously monitor customers with declining engagement and supplement model predictions with business rules for high-value customers.
