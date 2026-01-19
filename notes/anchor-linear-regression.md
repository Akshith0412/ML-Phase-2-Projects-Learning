# Anchor Notes: Linear Regression from Scratch

## Core Mental Model
Learning is not “finding the best values.”
Learning is **iterative error correction guided by the loss function**.

Parameters change because the loss tells them:
- how wrong they are
- and in which direction to move

---

## Key Lessons Learned

### 1. Loss Is Feedback, Not a Fix
Loss does not improve the model.
It only measures how bad the current parameters are.

Improvement happens only through parameter updates guided by gradients.

---

### 2. Gradient Direction Matters More Than Formulas
The gradient always points in the direction of **maximum increase in loss**.
Moving in the opposite direction guarantees local loss reduction.

Sign confusion disappears once this intuition is clear.

---

### 3. Learning Rate Controls Stability
- Too high → oscillation or divergence
- Too low → very slow convergence
- Proper value → smooth learning

Learning rate is about **step size**, not intelligence.

---

### 4. Feature Scaling Helps Optimization, Not Generalization
❌ Initial misconception:
Scaling prevents overfitting.

✅ Correct understanding:
Scaling improves the **shape of the loss surface**, allowing gradient descent to move smoothly instead of zig-zagging.

This is an optimization issue, not a bias/variance issue.

---

### 5. Training Failure Is a Feature, Not a Bug
Breaking the model (bad learning rate, unscaled data, noise) is necessary to understand:
- why training becomes unstable
- why deep learning is sensitive to hyperparameters

Failure cases taught more than success cases.

---

## Mistakes I Made (And Fixed)

### Mistake 1: Gradient Sign Confusion
I got confused by:
MSE = (ŷ − y)² vs (y − ŷ)²

This led to uncertainty about gradient signs.

Resolution:
The gradient direction matters, not the algebraic form.
Once the concept of “worst direction” is clear, the confusion disappears.

---

### Mistake 2: Thinking Scaling Prevents Overfitting
Initially believed scaling reduces model bias or overfitting.

Correction:
Scaling only improves optimization dynamics, not generalization.

This distinction is critical for deep learning.

---

## Connection to Neural Networks
- Linear regression = single neuron without activation
- Neural networks = many such units stacked
- Backpropagation = automated gradient computation via chain rule

This project removed fear around backprop and training.
