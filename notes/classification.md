# Classification – Practical Diagnostic Notes

## Accuracy Pitfall
- Accuracy hides error types and treats all mistakes equally.
- High accuracy can coexist with dangerous false negatives.
- Always inspect the confusion matrix before trusting accuracy.

## Metric Selection
- Metrics reflect business or domain priorities, not model quality alone.
- Recall is critical when false negatives are costly.
- Precision matters when false positives are expensive.

## Threshold Behavior
- Default threshold (0.5) is arbitrary.
- Lowering threshold increases recall but decreases precision.
- Threshold choice is a decision-making tool, not a modeling trick.

## Model vs Evaluation
- Changing metrics and thresholds can outperform switching models.
- Evaluation strategy often matters more than algorithm choice.
- A “better model” is meaningless under a wrong metric.

## Deployment Reality
- Extreme thresholds may be unacceptable in real systems.
- High recall models often require downstream verification.
- Model performance must be judged in context, not isolation.










# ROC–AUC – Practical Diagnostic Notes

## What ROC Curve Represents
- ROC curve plots True Positive Rate (Recall) vs False Positive Rate.
- It shows how model behavior changes across all possible thresholds.
- ROC does NOT depend on a single threshold like accuracy.

## Why ROC–AUC Is Useful
- Measures ranking ability, not final decisions.
- Answers: "Does the model score positive samples higher than negatives?"
- Useful when class distribution changes.

## What AUC Actually Means
- AUC = probability that a randomly chosen positive sample is ranked higher than a randomly chosen negative sample.
- AUC = 0.5 → model is no better than random.
- AUC = 1.0 → perfect ranking.

## ROC–AUC vs Accuracy
- Accuracy depends on threshold → can be misleading.
- ROC–AUC is threshold-independent.
- High accuracy can exist with poor ROC–AUC (and vice versa).

## ROC–AUC vs Precision–Recall
- ROC–AUC can look good even when precision is poor.
- Precision–Recall is more informative for heavily imbalanced datasets.
- Use ROC–AUC to compare models, PR curve to choose thresholds.

## Important Limitation
- ROC–AUC does NOT tell you which threshold to use.
- A high AUC does NOT guarantee low false negatives.
- Business context still decides the operating point.

## Key Mental Model
- ROC–AUC evaluates model discrimination.
- Threshold selection controls model decisions.
- Metric choice reflects cost of errors, not model quality alone.
