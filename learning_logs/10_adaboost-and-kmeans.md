# 10 —AdaBoost and K-Means

## Focus of this block

This block covers two very different ideas. AdaBoost shows how weak learners can be chained sequentially to correct mistakes. K-Means introduces clustering, where there are no labels and the goal is to group similar observations together.

## Core concepts

### Boosting intuition

Unlike bagging, boosting does not train models independently. It trains them sequentially.

Core idea:
each new learner focuses more on examples that earlier learners handled poorly.

This often creates a stronger final model from a series of weak learners.

### AdaBoost

AdaBoost typically uses shallow trees (often decision stumps) as weak learners.

The algorithm:
1. starts with equal sample weights
2. fits a weak learner
3. increases the weights of misclassified points
4. fits the next learner with more attention to hard cases
5. combines learners by weighted voting

### Strengths of AdaBoost

- elegant and powerful
- often improves weak learners substantially
- can perform well with simple base estimators
- highlights the logic of sequential correction

### Limitations of AdaBoost

- sensitive to noisy labels and outliers
- can focus too much on hard or corrupted examples
- usually needs thoughtful tuning

### Why boosting differs from bagging

- **Bagging**: trains models independently and averages them
- **Boosting**: trains models sequentially and corrects mistakes over time

That one-line difference matters a lot in interviews.

### K-Means clustering intuition

K-Means is a centroid-based clustering algorithm. It tries to partition the data into `K` clusters such that points in a cluster are close to that cluster’s centroid.

Basic loop:
1. choose `K`
2. initialize centroids
3. assign each point to the nearest centroid
4. recompute centroids
5. repeat until assignments stabilize

### What K-Means optimizes

K-Means tries to reduce within-cluster variation, commonly measured through inertia or within-cluster sum of squares.

### Choosing K

There is no universal perfect rule, but common heuristics include:

- elbow method
- silhouette score
- domain knowledge

The elbow method looks for a point where adding more clusters yields diminishing returns.

### K-Means assumptions and limitations

K-Means works best when clusters are:

- roughly spherical
- reasonably similar in scale
- separable by distance

It struggles when:

- clusters have irregular shapes
- densities vary strongly
- outliers distort centroids
- the data is not scaled

## Interview-ready takeaways

- Boosting improves weak learners sequentially; bagging averages independent learners.
- AdaBoost changes sample emphasis after each round.
- K-Means is an unsupervised algorithm that groups points around centroids.
- K-Means usually needs scaled features and a thoughtful choice of K.

## Quick review questions

1. How does boosting differ from bagging?
2. Why is AdaBoost sensitive to noise?
3. What is a centroid in K-Means?
4. Why does K-Means need the value of K in advance?
5. When can K-Means fail badly?

## Keywords

`AdaBoost`, `boosting`, `weak learner`, `sample weights`, `K-Means`, `centroid`, `inertia`, `elbow method`
