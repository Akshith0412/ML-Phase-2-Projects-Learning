# Customer Churn – Practical ML Notes

## Problem Framing
- Churn prediction is a decision-support problem, not just classification.
- The goal is intervention, not perfect prediction.
- Model outputs should directly inform business actions.

---

## Error Cost Asymmetry
- False negatives are more costly than false positives.
- Metric selection must reflect business loss, not model elegance.
- Recall is often more important than accuracy or precision.

---

## Baseline Pitfall
- Default thresholds (0.5) are arbitrary.
- Even strong models can be dangerous at default thresholds.
- Low recall at default settings is common in churn problems.

---

## Threshold Tuning Insight
- Threshold tuning can dramatically change model behavior.
- Adjusting thresholds can outperform switching to more complex models.
- Threshold selection is a decision-layer problem, not a modeling trick.

---

## Model Complexity Reality
- More complex models do not guarantee better outcomes.
- Data characteristics determine model effectiveness.
- Simpler models with correct thresholds can outperform complex ones.

---

## Stopping Discipline
- Optimization should stop once the decision objective is met.
- Further tuning without decision improvement is wasted effort.
- Knowing when to stop is part of ML engineering skill.
