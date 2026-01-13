# Project 1: Linear Regression Diagnostics

## Objective
To understand how linear regression behaves on real-world data and identify common failure modes such as scaling issues, multicollinearity, and bias limitations.

---

## Dataset
California Housing Dataset (Kaggle)

---

## Baseline Model
- Model: Linear Regression
- Preprocessing: None (no scaling)

### Observations
- Very large negative intercept
- Coefficients with extremely different magnitudes
- Poor predictions for high-priced houses

---

## Failure Analysis
### Symptoms
- Heteroscedastic residuals
- Predictions saturated around ~$500k
- Numerical instability in coefficients

### Root Cause
- Features on very different scales
- Strong multicollinearity
- Linear model unable to capture non-linear price behavior

---

## Diagnosis
- Problem Type: Bias-limited linear model
- Not primarily a variance problem

---

## Fix Applied
- Applied StandardScaler before Linear Regression

---

## Why This Fix Worked
Scaling normalized feature magnitudes, improving numerical stability during optimization.  
This prevented dominance of large-scale features and resulted in more stable coefficients and a more reasonable intercept, without changing model capacity.

---

## Key Takeaways
- Intercept values are meaningless without feature scaling
- Multicollinearity causes coefficient instability
- Linear regression has inherent bias on non-linear targets
- Optimization should stop once model assumptions are reached

---
## Corrected False Assumptions
- At the beginning i thought a solution for multicollinearity, that is using pca, that can improve this but no r2(ridge) regression can fix this because pca can create new features by destroying the old ones whereas the r2 can limit all the corelated features

- I learnt that
    If multicollinearity causes unstable coefficients → use Ridge.
    If dimensionality is huge and structure matters → consider PCA.

- PCA ignores the target
  PCA finds directions of maximum variance, not maximum predictiveness.A high-variance direction can be: completely irrelevant for price prediction
  So PCA can:
    throw away low-variance but highly predictive features
    reduce performance silently
  Ridge never does this.