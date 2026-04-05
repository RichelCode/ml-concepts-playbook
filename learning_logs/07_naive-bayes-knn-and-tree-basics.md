# 07— Naive Bayes, KNN, and Tree Basics

## Focus of this block

This block closes the probabilistic classification section, introduces instance-based learning through KNN, and begins the tree-based modeling mindset. It is a shift from probabilistic reasoning to geometry and rule-based splitting.

## Core concepts

### Final Naive Bayes reminders

Naive Bayes is often best treated as:

- a fast baseline
- a strong text classifier
- a model that benefits from simple feature representations
- a model whose assumptions are strong but computational cost is low

It is often less about perfect realism and more about efficient pattern capture.

### K-Nearest Neighbors (KNN) intuition

KNN is one of the most intuitive algorithms in ML.

Core idea:
to classify a point, look at its nearest neighbors and let them vote.

For regression:
average the target values of nearby points.

This makes KNN a **lazy learner**:
it does very little during training and pushes most of the work to prediction time.

### Key design choices in KNN

#### Choice of K
- small K → flexible, high variance, sensitive to noise
- large K → smoother, higher bias, more stable

#### Distance metric
Common choices:
- Euclidean distance
- Manhattan distance
- Minkowski distance

#### Feature scaling
KNN is highly sensitive to feature magnitude. Features should usually be scaled first.

### KNN strengths

- easy to understand
- no explicit training phase
- captures local structure
- good teaching model for similarity-based learning

### KNN limitations

- slow at prediction time on large datasets
- sensitive to irrelevant features
- weak in very high dimensions
- performance depends strongly on scaling and K choice

This high-dimensional weakness is often explained by the **curse of dimensionality**: distances become less informative as feature space grows.

### Decision tree classification basics

A decision tree recursively splits the feature space into regions. At each split, it chooses a rule that increases class purity.

Common split criteria:

#### Entropy
Measures uncertainty in a node.

#### Information gain
How much uncertainty is reduced after the split.

#### Gini impurity
A simpler purity measure used frequently in CART-style trees.

### Why trees feel intuitive

Trees are appealing because they produce rule-like logic:

- if feature A is above a threshold, go left
- else go right

This makes them easier to explain than many black-box models.

## Interview-ready takeaways

- KNN is a non-parametric, similarity-based model that stores training data instead of learning explicit coefficients.
- The value of K controls the bias-variance trade-off in KNN.
- Decision trees split data by purity criteria such as entropy or gini impurity.
- KNN needs scaling; trees generally do not.

## Quick review questions

1. Why is KNN called a lazy learner?
2. What happens when K is too small?
3. Why is KNN sensitive to feature scaling?
4. What is the curse of dimensionality?
5. What do entropy and gini impurity measure?

## Keywords

`KNN`, `nearest neighbors`, `distance metric`, `curse of dimensionality`, `decision tree`, `entropy`, `gini impurity`, `information gain`
