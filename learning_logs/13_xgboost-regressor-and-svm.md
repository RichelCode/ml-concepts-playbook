# 13 —XGBoost Regressor and SVM

## Focus of this block

This block continues gradient boosting for numeric prediction and then introduces Support Vector Machines. The key idea is that strong ML interview answers compare model families by what geometry or optimization principle they rely on.

## Core concepts

### XGBoost for regression

The logic is similar to classification, but the target is continuous.

The model:
- builds trees sequentially
- each new tree corrects remaining residual structure
- combines many weak learners into a strong regressor

Why it works well:
- captures nonlinear interactions
- handles mixed feature patterns
- benefits from shrinkage and regularization
- often beats simpler models on complex structured data

### What to watch in boosting workflows

- too many trees can overfit
- too much depth can memorize noise
- too high a learning rate can destabilize training
- validation strategy matters a lot

### Support Vector Machine (SVM) intuition

SVM is a margin-based method.

Core idea:
find the decision boundary that separates classes with the **largest possible margin**.

Why margin matters:
if classes are separated with a wider buffer, the classifier may generalize better.

### Support vectors

Not every point defines the boundary. The most important points are the ones closest to the separating boundary. These are the **support vectors**.

A strong interview line:
**SVM is defined by the hard examples near the margin, not by every data point equally.**

### Hard margin vs soft margin

- **Hard margin** assumes perfect separability
- **Soft margin** allows some violations to improve robustness

Real-world data often needs soft margin.

### The C parameter

`C` controls the penalty for misclassification.

- high `C` → fewer margin violations allowed, potentially lower bias and higher variance
- low `C` → more tolerance, wider margin, potentially higher bias and lower variance

### Why feature scaling matters for SVM

SVM depends on geometric distances and margins, so features should usually be scaled.

## Interview-ready takeaways

- XGBoost regression is a boosted tree approach for continuous targets.
- SVM searches for the boundary with maximum margin.
- Support vectors are the critical training points that define the classifier.
- The parameter `C` controls the trade-off between margin width and classification errors.

## Quick review questions

1. How is XGBoost regression similar to XGBoost classification?
2. Why are support vectors so important?
3. What does maximum margin mean?
4. How does `C` affect the SVM?
5. Why does SVM usually require feature scaling?

## Keywords

`XGBoost regressor`, `boosting`, `SVM`, `maximum margin`, `support vectors`, `soft margin`, `C parameter`, `feature scaling`
