# 06 — Regularization Workflow and Naive Bayes

## Focus of this block

This block mixes applied workflow with probabilistic classification. First, regularized regression is treated as a practical modeling workflow. Then the focus shifts to Naive Bayes, one of the fastest and most intuitive probabilistic classifiers.

## Core concepts

### Practical workflow for Ridge and Lasso

A good regularized regression pipeline usually includes:

1. train-test split
2. scaling numeric features
3. fitting Ridge or Lasso
4. tuning the regularization strength
5. comparing train and test scores
6. inspecting which coefficients shrink most

The main idea is not only to fit the model, but to choose a penalty that improves generalization rather than training fit alone.

### What to look for in practice

With regularization, good signs include:

- reduced gap between train and test performance
- more stable coefficients
- less sensitivity to noise
- simpler feature influence pattern

Bad signs include:

- all coefficients shrinking too aggressively
- test performance getting worse due to underfitting
- blindly choosing lambda without validation

### Naive Bayes intuition

Naive Bayes uses Bayes’ theorem:

`Posterior ∝ Prior × Likelihood`

In words:
the probability of a class given the observed features depends on:

- the prior probability of the class
- how likely the observed features are under that class

### Why it is called “naive”

The model assumes features are conditionally independent given the class. That assumption is rarely fully true in real data, but the model can still perform surprisingly well.

### Variants of Naive Bayes

#### Gaussian Naive Bayes
Used when features are continuous and roughly Gaussian within each class.

#### Bernoulli Naive Bayes
Used for binary features.

#### Multinomial Naive Bayes
Often used for count-based or frequency-based features such as text word counts.

### Why Naive Bayes is popular

- fast to train
- works well on high-dimensional sparse data
- simple probabilistic interpretation
- strong baseline for text classification and spam filtering

### Limitations

- independence assumption is often unrealistic
- probability estimates may be poorly calibrated
- performance can degrade when feature dependencies matter strongly

### Laplace smoothing

A classic issue is zero probability. If a feature value never appears with a class in training, the model can assign zero likelihood. Laplace smoothing avoids complete collapse by adding a small correction.

## Interview-ready takeaways

- Regularization is not just theory; it is a workflow involving scaling, tuning, and comparing generalization.
- Naive Bayes is simple, fast, and especially useful for text-like sparse data.
- “Naive” refers to the conditional independence assumption.
- Even unrealistic assumptions can still produce useful models.

## Quick review questions

1. Why is feature scaling important before Ridge or Lasso?
2. What does Naive Bayes compute conceptually?
3. Why can Naive Bayes work well even when its assumptions are wrong?
4. When would you use Gaussian vs Multinomial Naive Bayes?
5. What problem does Laplace smoothing solve?

## Keywords

`Ridge workflow`, `Lasso workflow`, `Naive Bayes`, `Bayes theorem`, `conditional independence`, `Laplace smoothing`, `Gaussian NB`, `Multinomial NB`
