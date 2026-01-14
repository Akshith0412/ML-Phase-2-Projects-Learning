# Project 2: Classification Metrics & Thresholds

## Objective
To understand why accuracy can be misleading in classification problems and how metric selection and decision thresholds directly affect real-world outcomes.

---

## Dataset
Heart Disease Dataset (Kaggle)

---

## Baseline Model
- Model: Logistic Regression
- Threshold: 0.5
- Metric used initially: Accuracy

### Observations
- Accuracy was ~80–83%
- Confusion matrix revealed a significant number of false negatives
- Model appeared good numerically but failed in a critical way

---

## Why Accuracy Failed
Accuracy treated false positives and false negatives equally.  
In a medical diagnosis context, false negatives (missing a patient with heart disease) are far more dangerous than false positives, making accuracy an inappropriate primary metric.

---

## Correct Metric
- Primary metric: **Recall**
- Reason: Minimizing false negatives is critical in medical diagnosis
- Precision was intentionally sacrificed to improve recall

---

## Threshold Analysis
- Default threshold (0.5) resulted in unacceptable false negatives
- Lowering the threshold increased recall significantly
- At a very low threshold, recall reached 100% with a large drop in precision

This demonstrated the explicit tradeoff between precision and recall and showed that model behavior can be changed without changing the model itself.

---

## Model Comparison
- Compared Logistic Regression with SVM (after scaling)
- Model choice affected performance, but:
  - Metric selection and threshold tuning had a larger impact than switching algorithms

---

## Key Takeaways
- High accuracy does not imply a safe or useful model
- Confusion matrix is essential for understanding failures
- Metric choice encodes real-world cost assumptions
- Threshold tuning can be more impactful than model complexity
