# Project 3: Decision Trees, Random Forest, and Boosting

## Objective
To understand why single decision trees fail, how Random Forest reduces variance, and how Boosting reduces bias by observing model behavior on a real dataset.

---

## Dataset
Credit Risk / Loan Default Dataset (Kaggle)

---

## Decision Tree (Baseline Failure)
- Model: DecisionTreeClassifier (deep / unrestricted)
- Observation:
  - Training accuracy was extremely high
  - Test accuracy dropped significantly

### Failure Analysis
The decision tree memorized noise in the training data, resulting in poor generalization.

---

## Diagnosis
- Problem Type: **High Variance**
- Cause: High model flexibility and sensitivity to training data

---

## Random Forest (Variance Reduction)
- Model: RandomForestClassifier
- Observation:
  - Training accuracy remained high
  - Test accuracy improved
  - Predictions became more stable

### Why Random Forest Helped
Random Forest reduced variance by averaging many deep but decorrelated trees trained on different bootstrap samples, canceling out individual tree errors.

---

## Boosting (Bias Reduction)
- Model: Gradient Boosting / XGBoost
- Observation:
  - Improved detection of difficult and minority-class samples
  - Different error pattern compared to Random Forest

### Why Boosting Helped
Boosting reduced bias by sequentially focusing on mistakes made by previous models, allowing the ensemble to learn more complex decision boundaries.

---

## Random Forest vs Boosting
- Random Forest is preferred when variance is the main issue and stability is important.
- Boosting is preferred when underfitting remains and reducing bias is critical, especially for hard-to-classify cases.

---

## Key Takeaways
- Single decision trees suffer from high variance
- Random Forest primarily addresses variance
- Boosting primarily addresses bias
- Model choice should depend on the failure mode, not accuracy alone
