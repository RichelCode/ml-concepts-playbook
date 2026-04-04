# 02— Linear Regression Core Ideas

## Focus of this block

This block is about the first major supervised learning model: linear regression. The goal is to understand not only the formula, but also why it works, what it assumes, and how to judge whether it is the right model.

## Core concepts

### What linear regression tries to do

Linear regression models the relationship between features and a continuous target.

A standard form is:

`y_hat = b0 + b1x1 + b2x2 + ... + bnxn`

Where:

- `y_hat` is the predicted value
- `b0` is the intercept
- `b1 ... bn` are coefficients
- `x1 ... xn` are features

The model assumes the target changes approximately linearly with the features.

### Simple vs multiple linear regression

- **Simple linear regression** uses one input feature.
- **Multiple linear regression** uses several features.

The logic is the same. Multiple regression simply adds more explanatory variables.

### Residuals and the learning objective

A **residual** is:

`actual value - predicted value`

The model tries to make residuals as small as possible.

A common objective is to minimize:

- **RSS**: residual sum of squares
- **MSE**: mean squared error

Squaring the errors prevents positive and negative residuals from cancelling each other out and penalizes large errors more heavily.

### Ordinary Least Squares intuition

Ordinary Least Squares (OLS) finds the line or hyperplane that minimizes the squared residuals. The fitted line is the one with the smallest total squared distance from the observed data points.

This is why linear regression is often introduced as “best fit line,” but the stronger explanation is:
**it is the line that minimizes squared prediction error on the training data.**

### Interpreting coefficients

Each coefficient tells you the expected change in the predicted target for a one-unit increase in that feature, holding other features constant.

Example:
If the coefficient for area is `250`, then increasing area by 1 unit increases the prediction by about 250 units of the target, assuming other features stay fixed.

### Important assumptions

Linear regression works best when key assumptions are approximately true:

- **Linearity**: relationship between features and target is roughly linear
- **Independence**: observations are not strongly dependent on each other
- **Homoscedasticity**: residual variance stays reasonably constant
- **Residual normality**: useful for some inference settings
- **Low multicollinearity**: features should not be excessively correlated with each other

These assumptions do not mean the model becomes impossible when violated, but performance and interpretation can degrade.

### Metrics to know

#### MAE
Average absolute error. Easy to interpret and less sensitive to outliers than MSE.

#### MSE
Average squared error. Penalizes large mistakes more.

#### RMSE
Square root of MSE. Useful because it is in the same unit as the target.

#### R²
Measures how much variance in the target is explained by the model.

#### Adjusted R²
Useful when multiple features are present because it penalizes unnecessary complexity.

## Common pitfalls

- Outliers can distort the fitted line
- Correlated features can make coefficients unstable
- Linear models can miss nonlinear relationships
- High R² on training data does not guarantee strong generalization
- Extrapolation far outside the training range is risky

## Interview-ready takeaways

- Linear regression is usually the first strong baseline for continuous prediction.
- Coefficients are only meaningful when preprocessing, scale, and multicollinearity are handled properly.
- A high training score is not enough; always compare with validation or test performance.
- Linear regression is attractive because it is fast, interpretable, and easy to debug.

## Quick review questions

1. What is a residual?
2. Why do we square errors in MSE?
3. What is the difference between R² and Adjusted R²?
4. What happens when multicollinearity is high?
5. Why can linear regression fail even when the training fit looks good?

## Keywords

`linear regression`, `OLS`, `residuals`, `MSE`, `RMSE`, `R-squared`, `Adjusted R-squared`, `multicollinearity`
