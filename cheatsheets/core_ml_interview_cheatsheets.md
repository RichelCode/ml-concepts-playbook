# Core ML Interview Cheat Sheet

## 1) Start every answer with the problem type

Before naming an algorithm, classify the problem:

- **Regression** → predict a continuous number
- **Classification** → predict a discrete label
- **Clustering** → discover groups without labels
- **Ranking / recommendation / anomaly detection** → special problem framing

A strong interview answer starts with:  
**“First I would identify the target type, data size, feature types, interpretability needs, and evaluation metric.”**

## 2) Algorithm selection at a glance

| Situation | Good first choices | Why |
|---|---|---|
| Simple numeric prediction with interpretable coefficients | Linear Regression, Ridge, Lasso | Fast, explainable, strong baseline |
| Binary classification with interpretable probabilities | Logistic Regression | Easy to explain, probabilistic output |
| Text classification baseline | Naive Bayes, Logistic Regression | Strong on sparse high-dimensional data |
| Small/medium tabular data with nonlinear patterns | Decision Tree, Random Forest, XGBoost | Capture nonlinear interactions well |
| Fast baseline for tabular classification/regression | Random Forest | Strong default, low preprocessing |
| Highest performance on many tabular datasets | XGBoost | Powerful boosting with regularization |
| Similarity-based local reasoning | KNN | Intuitive, no training phase |
| Clear margin separation / high-dimensional data | SVM | Strong margin-based classifier |
| Unknown groups in unlabeled data | K-Means, Hierarchical, DBSCAN | Three distinct clustering families |

## 3) Core differences you should be able to say quickly

### AI vs ML vs DL vs Data Science

- **AI** is the broad field of building systems that perform tasks associated with intelligence.
- **ML** is a subset of AI where systems learn patterns from data.
- **DL** is a subset of ML based on deep neural networks.
- **Data Science** is broader than modeling alone: data cleaning, analysis, visualization, experimentation, and communication.

### Regression vs Classification

- **Regression** predicts a number.
- **Classification** predicts a class label or class probability.

### Bagging vs Boosting

- **Bagging** builds models independently and aggregates them to reduce variance.
- **Boosting** builds models sequentially so each new learner corrects earlier mistakes.

## 4) Key formulas worth remembering

### Linear Regression
`y_hat = b0 + b1x1 + b2x2 + ... + bnxn`

### Logistic Regression
`p = 1 / (1 + e^(-z))`

### Ridge
`Loss = RSS + lambda * sum(w_j^2)`

### Lasso
`Loss = RSS + lambda * sum(|w_j|)`

### Gini Impurity
`Gini = 1 - sum(p_i^2)`

### Entropy
`Entropy = -sum(p_i * log2(p_i))`

### Silhouette Score
`(b - a) / max(a, b)`

## 5) Metrics you should never mix up

### Regression metrics

- **MAE**: average absolute error; robust and interpretable
- **MSE**: squares larger errors more heavily
- **RMSE**: square root of MSE; same unit as target
- **R²**: fraction of variance explained
- **Adjusted R²**: penalizes unnecessary features

### Classification metrics

- **Accuracy**: correct predictions / total predictions
- **Precision**: out of predicted positives, how many were truly positive
- **Recall**: out of actual positives, how many were found
- **F1-score**: harmonic mean of precision and recall
- **ROC-AUC**: ranking quality across thresholds

### Clustering validation

- **Inertia** for K-Means: lower is better but always decreases with larger K
- **Silhouette score**: balance of tight clusters and clear separation

## 6) Standard interview traps

### Why not use accuracy alone?
Because imbalanced datasets can make a weak model look strong.

### Why scale features?
Distance-based models and margin-based models are sensitive to feature magnitude. KNN, K-Means, regularized linear models, and SVM usually need scaling.

### Why does KNN struggle in high dimensions?
Distances become less informative as dimensions grow. This is the **curse of dimensionality**.

### Why does a decision tree overfit easily?
It can keep splitting until leaves memorize noise in the training set.

### Why is Random Forest stronger than a single tree?
Averaging many diverse trees reduces variance and improves robustness.

### Why is Lasso useful for feature selection?
L1 regularization can shrink some coefficients exactly to zero.

### Why is Naive Bayes called “naive”?
It assumes features are conditionally independent given the class, which is often unrealistic but still useful.

### Why is XGBoost so popular?
It combines boosting with regularization, shrinkage, and efficient tree building, giving strong performance on tabular data.

## 7) When each algorithm shines

### Linear / Ridge / Lasso
Use when interpretability matters, relationships are close to linear, and you want a strong baseline.

### Logistic Regression
Use for binary classification when you want probabilities and interpretable coefficients.

### Naive Bayes
Use for text or very fast baseline classification.

### KNN
Use when local similarity matters and the dataset is not too large.

### Decision Trees
Use when you want interpretability and rule-like logic.

### Random Forest
Use when you want a reliable baseline on tabular data with little preprocessing.

### AdaBoost
Use when weak learners can be improved sequentially and noise is not too dominant.

### K-Means
Use when clusters are roughly spherical and you can choose K reasonably.

### Hierarchical Clustering
Use when you want a cluster hierarchy and a dendrogram.

### DBSCAN
Use when clusters may have irregular shapes and you want explicit noise handling.

### XGBoost
Use when you want high-performance gradient boosting on structured/tabular data.

### SVM
Use when classes are separable with a margin, data is high-dimensional, or kernels can help.

## 8) A clean answer structure for “Which model would you choose?”

Use this sequence:

1. define the task
2. check data size and feature types
3. decide if interpretability matters
4. pick a simple baseline
5. choose metric based on business objective
6. compare stronger candidates with cross-validation
7. explain trade-offs, not just the final model

## 9) Final one-minute revision list

Before an interview, make sure you can explain clearly:

- regression vs classification
- overfitting vs underfitting
- bias vs variance
- Ridge vs Lasso
- precision vs recall
- entropy vs gini
- bagging vs boosting
- Random Forest vs XGBoost
- K-Means vs DBSCAN
- SVM margin, C, and kernel idea
