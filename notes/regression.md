# Linear Regression – Practical Diagnostic Notes

## Intercept Behavior
- Large positive or negative intercept usually indicates unscaled features.
- Intercept value has no real-world meaning when features are unscaled.
- Intercept magnitude alone does not indicate underfitting or overfitting.

## Feature Scaling
- Features with large magnitudes dominate optimization when unscaled.
- Coefficient comparison is meaningless without scaling.
- Scaling improves numerical stability but does not increase model capacity.

## Multicollinearity
- Highly correlated features cause unstable coefficients.
- Multicollinearity may not hurt RMSE but harms interpretability.
- Ridge regression is the correct fix when interpretability matters.

## Bias vs Variance
- Linear regression is often bias-limited on non-linear targets.
- Consistent prediction errors indicate bias, not variance.
- Stop optimizing once remaining error is due to model assumptions.

## Residual Patterns
- Heteroscedastic residuals indicate violated linear model assumptions.
- Scaling reduces numerical artifacts but does not fix structural bias.
