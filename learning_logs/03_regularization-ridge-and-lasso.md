# 03 — 01:00 to 01:30 — Regularization: Ridge and Lasso

## Focus of this block

This block introduces regularization: the idea that a model can be made more stable by discouraging overly large coefficients. The main problem being addressed is overfitting, especially when the model becomes too sensitive to the training data.

## Core concepts

### Why regularization is needed

A linear model can fit the training data well but still generalize poorly. This often happens when:

- the model is too flexible for the data size
- features are noisy
- features are highly correlated
- the model chases small fluctuations instead of real signal

Regularization adds a penalty term to the loss function so the model does not rely too heavily on large weights.

### Ridge regression (L2 regularization)

Ridge modifies the loss:

`Loss = RSS + lambda * sum(w_j^2)`

What it does:

- shrinks coefficients toward zero
- usually keeps all features in the model
- helps when multicollinearity is high
- reduces variance at the cost of some bias

Ridge is strong when many features contain a little useful information.

### Lasso regression (L1 regularization)

Lasso modifies the loss:

`Loss = RSS + lambda * sum(|w_j|)`

What it does:

- shrinks coefficients toward zero
- can drive some coefficients exactly to zero
- performs implicit feature selection
- is useful when only some features are truly important

Lasso is attractive when you want a simpler, sparser model.

### The role of lambda

`lambda` controls the penalty strength.

- small lambda → model behaves more like ordinary linear regression
- large lambda → stronger shrinkage
- too large lambda → underfitting

This is why lambda must usually be tuned, often with cross-validation.

### Ridge vs Lasso

Use **Ridge** when:

- many features contribute a little
- multicollinearity is a major issue
- you do not want coefficients dropping out completely

Use **Lasso** when:

- feature selection matters
- you suspect many features are irrelevant
- you want a more compact model

A useful interview line:
**Ridge shrinks; Lasso shrinks and can select.**

### Why scaling matters

Regularization penalties depend on coefficient magnitude. If features are on very different scales, the penalty becomes uneven. That is why standardization is usually done before Ridge or Lasso.

### Bias-variance perspective

Regularization intentionally adds some bias to reduce variance.

That trade-off is often good because:

- a slightly biased model can generalize better
- a highly flexible model can memorize noise

This is one of the most important mental models in all of machine learning.

## Common interview questions

### Does regularization fix everything?
No. It helps with model complexity and stability, but it does not replace good features, clean data, or the right problem framing.

### Can Lasso be unstable?
Yes. When correlated features compete with each other, Lasso may choose one and suppress others somewhat arbitrarily.

### Is Elastic Net worth knowing?
Yes. Elastic Net combines L1 and L2 penalties and is often useful when you want both shrinkage and sparse selection.

## Interview-ready takeaways

- Ridge and Lasso are extensions of linear regression designed to reduce overfitting.
- Ridge is usually better for correlated features; Lasso is useful when feature selection is desired.
- Regularization strength must be tuned rather than guessed.
- Scaling before regularization is usually essential.

## Quick review questions

1. Why do large coefficients often signal overfitting risk?
2. What is the difference between L1 and L2 regularization?
3. Why can Lasso set coefficients exactly to zero but Ridge usually does not?
4. Why should features be scaled before Ridge or Lasso?
5. How does regularization connect to the bias-variance trade-off?

## Keywords

`regularization`, `Ridge`, `Lasso`, `L1`, `L2`, `lambda`, `overfitting`, `bias-variance trade-off`
