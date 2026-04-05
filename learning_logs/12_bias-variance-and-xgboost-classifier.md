# 12 — Bias-Variance and XGBoost Classifier

## Focus of this block

This block ties together a major theoretical theme and a high-performance practical algorithm. Bias and variance explain model behavior. XGBoost shows how powerful gradient boosting can be when it is regularized and engineered well.

## Core concepts

### Bias and variance

These two ideas explain a huge part of model behavior.

#### High bias
The model is too simple and misses real patterns.

Symptoms:
- poor training performance
- poor test performance

This is usually **underfitting**.

#### High variance
The model is too sensitive to training data.

Symptoms:
- very strong training performance
- much weaker test performance

This is usually **overfitting**.

### Why the trade-off matters

Improving one side can hurt the other:

- simpler models often reduce variance but increase bias
- more flexible models often reduce bias but increase variance

The goal is not “lowest bias” or “lowest variance” alone. The goal is the best generalization.

### Ways to control bias and variance

To reduce **bias**:
- increase model complexity
- add informative features
- reduce overly strong regularization

To reduce **variance**:
- simplify the model
- regularize
- collect more data
- use bagging or better validation

### XGBoost intuition

XGBoost is a gradient boosting algorithm built around decision trees.

Core idea:
- train a tree
- measure remaining error
- train the next tree to improve on what is still wrong
- repeat while controlling complexity carefully

It is stronger than plain boosting because it adds:

- regularization
- shrinkage / learning rate
- tree constraints
- efficient optimization

### Why XGBoost is strong on tabular data

- captures nonlinear interactions
- often performs extremely well on structured datasets
- handles missing values well in many practical settings
- supports fine-grained control of complexity

### Important XGBoost parameters

- `n_estimators` — number of boosting rounds
- `learning_rate` — how strongly each tree contributes
- `max_depth` — depth of each tree
- `subsample` — fraction of rows per round
- `colsample_bytree` — fraction of features per tree
- regularization terms — help control overfitting

### XGBoost for classification

For classification, the ensemble predicts class scores or probabilities and optimizes a classification loss.

It is often chosen when:
- tabular performance matters
- feature interactions are complex
- you are ready to tune hyperparameters

## Interview-ready takeaways

- Bias and variance explain underfitting and overfitting.
- XGBoost is a regularized, high-performance gradient boosting algorithm.
- It is often one of the strongest candidates on structured/tabular datasets.
- More power also means more tuning responsibility.

## Quick review questions

1. What is the difference between high bias and high variance?
2. How do bagging and regularization affect variance?
3. Why is XGBoost stronger than a single tree?
4. What does learning rate do in XGBoost?
5. Why can XGBoost overfit if not tuned carefully?

## Keywords

`bias`, `variance`, `underfitting`, `overfitting`, `XGBoost`, `gradient boosting`, `learning rate`, `tabular data`
