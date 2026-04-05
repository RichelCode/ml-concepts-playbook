# 04_Logistic Regression Intuition

## Focus of this block

This block shifts from regression to classification. Logistic regression is one of the most important interview models because it is simple, interpretable, and often used as a strong baseline for binary classification.

## Core concepts

### Why linear regression is not ideal for classification

A classification problem predicts categories, not continuous values. If you apply plain linear regression to a binary target, the output can fall below 0 or above 1, which is not meaningful as a probability.

Logistic regression solves this by mapping a linear score into the interval `[0, 1]`.

### The sigmoid function

Logistic regression computes:

`z = b0 + b1x1 + ... + bnxn`

Then converts it into a probability:

`p = 1 / (1 + e^(-z))`

This sigmoid function squashes any real value into a probability-like number between 0 and 1.

### Decision boundary

The predicted probability is converted into a class using a threshold.

Typical default:
- if `p >= 0.5`, predict positive class
- else predict negative class

The threshold can be changed depending on business cost and class imbalance.

### Odds and log-odds

A good interview detail:

- **odds** = `p / (1 - p)`
- logistic regression models the **log-odds** as a linear combination of features

This is why coefficients are often interpreted in terms of how they shift the log-odds of the positive class.

### Loss function

Logistic regression is not trained with ordinary least squares. It usually uses **log loss** (cross-entropy loss), which is better suited to probability-based classification.

The intuition is:
- correct and confident predictions are rewarded
- wrong and confident predictions are penalized strongly

### Coefficient interpretation

Each coefficient changes the log-odds of the positive class when that feature increases by one unit, holding others fixed.

This is more subtle than linear regression coefficient interpretation, but it is still explainable.

### Assumptions and strengths

Logistic regression does not assume the target is linearly related to the features. Instead, it assumes the **log-odds** are approximately linear in the features.

Strengths:
- interpretable
- probabilistic output
- strong baseline
- efficient on tabular data

Limitations:
- may struggle when class boundaries are highly nonlinear
- sensitive to outliers and correlated features
- can underperform more flexible models on complex patterns

### Multiclass extension

For multiclass settings, logistic regression is commonly extended using approaches like one-vs-rest or softmax-based formulations.

You do not always need deep detail here, but it is worth knowing that logistic regression is not limited to only two classes conceptually.

## Interview-ready takeaways

- Logistic regression is a classification algorithm even though the word “regression” appears in the name.
- It predicts class probabilities through the sigmoid transformation of a linear score.
- It is often the first good baseline for binary classification problems.
- Threshold selection matters as much as the model itself in many real applications.

## Quick review questions

1. Why is linear regression a weak choice for binary classification?
2. What does the sigmoid function do?
3. What is the decision boundary?
4. What does a logistic regression coefficient represent?
5. Why is cross-entropy more suitable than MSE here?

## Keywords

`logistic regression`, `sigmoid`, `probability`, `decision boundary`, `log-odds`, `cross-entropy`, `binary classification`
