# 01 — Foundations and Problem Framing

## Focus of this block

This block builds the vocabulary and mental map needed for the rest of machine learning. If the foundations are weak, every later algorithm feels like a memorization problem. If the foundations are clear, later algorithms feel like different tools solving different kinds of prediction problems.

## Core concepts

### AI vs ML vs DL vs Data Science

- **Artificial Intelligence (AI)** is the umbrella field for building systems that act intelligently.
- **Machine Learning (ML)** is a subset of AI where models learn patterns from data instead of following only hand-written rules.
- **Deep Learning (DL)** is a subset of ML that uses multi-layer neural networks to learn representations automatically.
- **Data Science** is broader than modeling. It includes data cleaning, analysis, visualization, experimentation, storytelling, and decision support.

A clean way to explain the relationship:

- AI = the big goal
- ML = a major approach inside AI
- DL = a specific family inside ML
- Data Science = the practical discipline that uses data end-to-end, often including ML but not limited to it

### When traditional ML is usually enough

Traditional machine learning is often the better first choice when:

- the dataset is tabular and not extremely large
- interpretability matters
- training time and infrastructure should stay light
- the feature engineering burden is manageable
- you need a strong baseline quickly

Deep learning becomes more attractive when the data is large, unstructured, and rich in patterns that are hard to hand-engineer, such as images, text, speech, and video.

### Types of machine learning

#### Supervised learning
You have inputs and correct outputs. The model learns a mapping from features to target values.

Examples:
- house price prediction
- spam detection
- churn prediction

#### Unsupervised learning
You have inputs but no labels. The goal is to find structure inside the data.

Examples:
- customer segmentation
- anomaly patterns
- document grouping

#### Reinforcement learning
An agent learns by interacting with an environment and receiving rewards or penalties.

Examples:
- game playing
- robotics
- sequential decision systems

### Regression vs classification

This is one of the most basic distinctions in ML and one of the most common interview questions.

#### Regression
Predict a continuous numeric value.

Examples:
- salary
- sales
- demand
- temperature

#### Classification
Predict a category or class probability.

Examples:
- fraud / not fraud
- disease / no disease
- churn / no churn
- sentiment class

A good habit is to ask this question first:
**“Is my target numeric or categorical?”**

That question immediately narrows the model family.

### A practical ML workflow

Most ML work follows a loop like this:

1. define the business problem
2. identify the target variable
3. collect and understand the data
4. clean and preprocess features
5. split data into train and test sets
6. build a baseline model
7. evaluate with the right metric
8. improve the model
9. deploy only if it is useful and stable
10. monitor performance after deployment

### What makes a model useful

A model is not useful just because it is mathematically elegant. It must balance:

- predictive performance
- interpretability
- speed
- data requirements
- maintenance cost
- fairness and reliability

That trade-off mindset matters in interviews more than memorizing a long list of algorithms.

## Interview-ready takeaways

- Machine learning is about learning patterns from data to make predictions or decisions.
- Deep learning is not “better by default”; it is just a different family of models with different trade-offs.
- The first framing step is to decide whether the problem is regression, classification, or unsupervised learning.
- A good ML answer always connects model choice to data type, business need, and evaluation metric.

## Quick review questions

1. How would you explain the difference between AI, ML, DL, and Data Science in under a minute?
2. When would you prefer a simpler ML model over deep learning?
3. What is the difference between regression and classification?
4. What is the first thing you check before choosing an algorithm?
5. Why is a strong baseline model important?

## Keywords

`AI`, `machine learning`, `deep learning`, `data science`, `supervised learning`, `unsupervised learning`, `regression`, `classification`
