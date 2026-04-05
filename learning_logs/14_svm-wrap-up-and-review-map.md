# 14— SVM Wrap-Up and Review Map

## Focus of this block

This final block completes the SVM story and gives you a compact map for revision. The goal is to end the course with selection logic, not just algorithm names.

## Core concepts

### Kernel idea

A linear boundary is not always enough. The **kernel trick** lets SVM operate as if data were transformed into a higher-dimensional space without explicitly computing that transformation.

Common kernels:
- **linear** — simple and fast
- **polynomial** — captures curved relationships
- **RBF** — highly flexible and widely used

### Gamma intuition

For kernels like RBF, `gamma` controls how far the influence of a single point extends.

- high gamma → very local influence, more flexible boundary, higher overfitting risk
- low gamma → smoother boundary, lower flexibility

### SVM strengths

- powerful in high-dimensional spaces
- strong when margin separation matters
- effective with proper kernel choice
- often solid on medium-sized datasets

### SVM limitations

- scaling is important
- tuning `C` and kernel parameters can be sensitive
- large datasets can be computationally expensive
- probability calibration may need extra care depending on setup

### Fast final selection map

Use:

- **Linear Regression / Ridge / Lasso** for interpretable numeric prediction
- **Logistic Regression** for interpretable classification probabilities
- **Naive Bayes** for fast probabilistic text-style baselines
- **KNN** for similarity-based local decisions
- **Decision Trees** for rule-like nonlinear logic
- **Random Forest** for robust tabular baselines
- **AdaBoost / XGBoost** for boosted performance on structured data
- **K-Means / Hierarchical / DBSCAN** for different clustering assumptions
- **SVM** when margin-based separation or kernelized boundaries are attractive

## Interview-ready takeaways

- `C` controls error tolerance; `gamma` controls locality in kernelized SVMs.
- SVM is strongest when the boundary can be explained through margin separation.
- Algorithm choice should always be justified through data shape, scale, interpretability, and metric.
- The best final revision habit is to compare models by assumptions, strengths, weaknesses, and failure modes.

## Quick review questions

1. What problem does the kernel trick solve?
2. What happens when gamma is too high?
3. How do `C` and `gamma` interact in practice?
4. When would you choose SVM over logistic regression?
5. Which three algorithms would you choose as strong baselines for tabular data, and why?

## Keywords

`kernel trick`, `linear kernel`, `RBF kernel`, `gamma`, `C`, `margin`, `model selection`, `interview revision`
