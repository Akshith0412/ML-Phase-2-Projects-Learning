# Anchor Project: Linear Regression from Scratch

## Objective
This project was built to deeply understand how learning happens in machine learning models by implementing linear regression and gradient descent from scratch using NumPy.

This is an **anchor project**, meant to build intuition for:
- loss functions
- gradients
- gradient descent
- training instability
- learning rate behavior
- feature scaling

It is intentionally simple and educational, not a production or resume project.

---

## Dataset
Synthetic dataset generated using:
y = 3x + 5 + noise

The true relationship is known so learning dynamics can be observed clearly.

---

## What “Learning” Means Here
Learning means **iteratively updating model parameters (weights and bias) in response to feedback from the loss function**, so that predictions become less wrong over time.

The model does not “know” the correct line — it corrects itself using error signals.

---

## Training Process
- Model: ŷ = wx + b
- Loss function: Mean Squared Error (MSE)
- Optimization: Gradient Descent (manual implementation)
- No sklearn, no autograd, no optimizers beyond plain GD

---

## Key Experiments Performed
- Normal learning rate vs very high learning rate
- Very small learning rate (slow convergence)
- Unscaled vs scaled input data
- High-noise data

These experiments were used to observe:
- convergence
- oscillation
- divergence
- optimization stability

---

## Key Insights
- Gradient descent is a controlled error-correction process.
- Loss provides feedback, not a fix.
- Learning rate controls stability, not intelligence.
- Feature scaling improves optimization geometry, not generalization.
- Training failure modes are as important as success cases.

---

## Why This Project Matters
This project serves as a mental foundation for:
- backpropagation
- neural networks
- deep learning training dynamics

Every neural network is a scaled version of this idea.
