# 08 — Decision Trees in Depth

## Focus of this block

This block turns decision trees from an intuitive concept into a serious modeling tool. The goal is to understand how trees grow, how they predict, and why they are both powerful and dangerously easy to overfit.

## Core concepts

### Decision tree classification recap

A classification tree keeps splitting the data until child nodes become more pure than the parent node. The split is chosen to maximize class separation according to a criterion like gini impurity or entropy.

Important practical controls include:

- `max_depth`
- `min_samples_split`
- `min_samples_leaf`
- impurity threshold

These controls matter because a fully grown tree can memorize training noise.

### Overfitting in trees

Trees can overfit quickly because they keep partitioning the data into smaller and smaller regions.

Signs of tree overfitting:

- extremely high training score
- much weaker test score
- many small leaves
- unstable predictions when data changes slightly

### Pruning idea

Pruning cuts back unnecessary branches to improve generalization. Even if explicit pruning is not always used in every library workflow, the idea matters: **simpler trees often generalize better**.

### Decision tree regression

A regression tree predicts a numeric value by splitting the feature space into regions and assigning a constant prediction within each region, typically the mean target value of the samples inside that leaf.

Instead of purity by class labels, regression trees reduce error by choosing splits that lower variance or mean squared error.

### Why trees are flexible

Trees naturally capture:

- nonlinear relationships
- feature interactions
- threshold-based rules
- mixed feature effects without feature scaling

This is why they are strong on many tabular datasets.

### Tree strengths

- interpretable at shallow depth
- handles nonlinear patterns
- needs relatively little preprocessing
- works with both classification and regression

### Tree limitations

- high variance
- unstable under small data perturbations
- deep trees become hard to interpret
- can create sharp step-like boundaries that generalize poorly

### When to use a tree directly

A single tree is often useful when:

- interpretability matters
- you want clear rule extraction
- the dataset is not huge
- a simple nonlinear baseline is needed

But when predictive performance matters more, ensemble versions such as Random Forest and boosting are often stronger.

## Interview-ready takeaways

- A decision tree classifier splits to improve class purity; a decision tree regressor splits to reduce prediction error.
- Trees are powerful because they capture nonlinear rules without scaling.
- Their biggest weakness is high variance and easy overfitting.
- Pruning and depth control are essential to generalization.

## Quick review questions

1. Why do deep trees overfit?
2. How is a regression tree different from a classification tree?
3. Why do trees handle nonlinear interactions well?
4. Why is interpretability often lost as depth increases?
5. When would you move from a single tree to an ensemble?

## Keywords

`decision tree classifier`, `decision tree regressor`, `max_depth`, `pruning`, `variance reduction`, `nonlinear splits`, `overfitting`
