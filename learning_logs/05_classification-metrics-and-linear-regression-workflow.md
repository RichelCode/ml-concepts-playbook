# 05_Classification Metrics and Linear Regression Workflow

## Focus of this block

This block connects theory to evaluation and implementation. A model is not truly understood until you know how to judge it and how to move from idea to a clean training workflow.

## Core concepts

### Classification metrics you must know

A confusion matrix gives four counts:

- true positives
- true negatives
- false positives
- false negatives

From those, we derive the most common metrics.

#### Accuracy
Overall fraction of correct predictions.

Good only when classes are reasonably balanced.

#### Precision
Out of all predicted positives, how many were actually positive?

Use when false positives are costly.

#### Recall
Out of all actual positives, how many did the model correctly find?

Use when false negatives are costly.

#### F1-score
Balances precision and recall through the harmonic mean.

Useful when the class distribution is imbalanced and you need a single summary metric.

#### ROC-AUC
Measures ranking quality across thresholds. Good for comparing classifiers beyond a single fixed threshold.

### Threshold tuning matters

A classification model may output probabilities, but the final decision depends on the threshold. That threshold should reflect business cost.

Example:
- fraud detection may prefer higher recall
- spam filtering may prefer higher precision
- medical screening often prefers not missing positive cases

### Linear regression implementation workflow

Even for a “simple” model, the workflow should be disciplined.

1. load the data
2. identify feature columns and target
3. handle missing values
4. encode categorical variables when needed
5. split into train and test sets
6. optionally scale features
7. train the model
8. evaluate with proper metrics
9. inspect coefficients and errors
10. compare train vs test behavior

### Why train-test split matters

A model that performs well on the same data it learned from may still fail on unseen data. The test split gives a better estimate of generalization.

### Residual analysis

For linear regression, a good workflow does not stop at a score. You should also inspect:

- residual patterns
- large errors
- outliers
- feature relationships
- whether error variance seems stable

### Scaling in practice

Plain linear regression does not always require scaling for correctness, but scaling becomes much more important once you introduce regularization or distance-based methods.

## Practical habits that make you look strong in interviews

- always build a baseline first
- always name the evaluation metric explicitly
- always check train vs test performance
- always connect the metric to business cost
- never choose a threshold blindly

## Interview-ready takeaways

- Accuracy is not enough for imbalanced classification.
- Precision and recall answer different business questions.
- The best workflow is boring, consistent, and reproducible.
- Good implementation means preprocessing, splitting, training, and evaluation are all deliberate.

## Quick review questions

1. When is accuracy misleading?
2. When would you optimize recall over precision?
3. Why is threshold tuning important?
4. What is the purpose of a train-test split?
5. What can residual plots reveal in linear regression?

## Keywords

`confusion matrix`, `precision`, `recall`, `F1-score`, `ROC-AUC`, `threshold`, `train-test split`, `residual analysis`
