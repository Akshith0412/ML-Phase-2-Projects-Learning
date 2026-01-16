# Project 5: Customer Churn Prediction (Bridge Project)

## Objective
To test end-to-end classical ML decision-making on a realistic business problem and validate metric selection, threshold tuning, and stopping discipline before moving to Deep Learning.

---

## Dataset
Telco Customer Churn Dataset (Kaggle)

---

## Decision Problem
The goal is to predict customers who are likely to churn so that proactive retention actions (e.g., offers, discounts) can be applied.

- Churn = "Yes": customer left in the last month
- Churn = "No": customer stayed

---

## Cost of Errors
- **False Negatives (most costly):**
  Predicting a customer will stay when they actually churn results in direct revenue loss.
- **False Positives (less costly):**
  Predicting churn for a customer who stays results in unnecessary retention cost.

---

## Baseline Model
- Model: Logistic Regression
- Threshold: 0.5

### Observation
- Recall was low, indicating many churners were missed.
- Default XGBoost performed worse at the default threshold.

The baseline models were unsafe due to high false negatives.

---

## Improvement Applied
- Decision threshold was lowered from 0.5 to 0.3.

### Result
- Recall increased significantly (≈58% → ≈80%).
- Precision dropped moderately, which was an acceptable tradeoff for the business.

---

## Tradeoff Accepted
Higher recall was prioritized over precision to minimize missed churners, accepting increased false positives.

---

## Why Optimization Stopped
Threshold tuning solved the core decision problem.
Further model complexity or hyperparameter tuning would not meaningfully improve real-world outcomes.

---

## Key Takeaways
- Model choice matters less than correct problem framing.
- Metrics must reflect business cost.
- Threshold tuning can outperform model complexity.
- Knowing when to stop is a critical ML skill.
