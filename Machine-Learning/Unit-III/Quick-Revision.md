# Unit III — Quick Revision
## Supervised Learning: Regression

**Subject:** Machine Learning (410242) | **SPPU 2019 Course**

## 1. Bias, Variance and Generalization

- **Bias:** Error caused by overly simple assumptions in a model.
- **Variance:** Model sensitivity to changes in training data.
- **Bias-Variance Trade-off:** Balance between bias and variance to achieve good generalization.
- **Generalization:** Ability of a trained model to perform well on unseen data.

**Recall:**
- High bias → underfitting.
- High variance → overfitting.

## 2. Underfitting vs Overfitting

| Underfitting | Overfitting |
|---|---|
| Model is too simple. | Model is too complex. |
| High training and testing error. | Low training error but high testing error. |
| Fails to learn important patterns. | Learns noise and details specific to training data. |
| Improve model complexity and features. | Use regularization, more data, cross-validation, pruning or simpler models. |

## 3. Training Error and Generalization Error

- **Training Error:** Error measured on the data used to train the model.
- **Generalization Error:** Error measured on unseen data drawn from the target data distribution.
- A large gap between training and validation/test error may indicate overfitting.

## 4. Linear Regression

Linear regression models the relationship between an independent variable X and dependent variable Y.

**Simple Linear Regression:**

`Y = a + bX`

Where:
- `a` = intercept.
- `b` = slope.
- `X` = independent variable.
- `Y` = predicted dependent variable.

**Multiple Linear Regression:**

`Y = b0 + b1X1 + b2X2 + ... + bnXn`

## 5. Least Squares Method

The least squares method finds the regression line by minimizing the sum of squared differences between actual and predicted values.

**Slope:**

`b = [n × ΣXY − (ΣX × ΣY)] / [n × ΣX² − (ΣX)²]`

**Intercept:**

`a = (ΣY − b × ΣX) / n`

**Regression line:** `Y = a + bX`

## 6. Lasso and Ridge Regression

Both are regularized linear regression methods.

- **Lasso (L1):** Adds the sum of absolute coefficient values as a penalty. It can make some coefficients exactly zero, so it can perform feature selection.
- **Ridge (L2):** Adds the sum of squared coefficient values as a penalty. It shrinks coefficients towards zero but generally does not make them exactly zero.

**Recall:** Lasso → L1 → feature selection. Ridge → L2 → coefficient shrinkage.

## 7. Gradient Descent

Gradient Descent is an iterative optimization algorithm used to minimize a cost function by updating model parameters in the direction opposite to the gradient.

**Parameter update:**

`New Parameter = Old Parameter − (Learning Rate × Gradient)`

Steps:
1. Initialize parameters.
2. Calculate predictions and cost.
3. Calculate gradients.
4. Update parameters.
5. Repeat until convergence or a stopping condition is reached.

## 8. Batch vs Stochastic Gradient Descent

| Batch Gradient Descent | Stochastic Gradient Descent |
|---|---|
| Uses the complete training dataset for one update. | Uses one training example for one update. |
| More stable updates. | Noisier updates. |
| Can be computationally expensive for large datasets. | Can make frequent, faster updates. |

## 9. Cost Function

A cost function measures how far model predictions are from actual values. Gradient Descent attempts to minimize this function.

For linear regression, a common cost function is Mean Squared Error:

`MSE = Σ(Actual − Predicted)² / n`

## 10. Regression Evaluation Metrics

Let:
- `yi` = Actual value.
- `ŷi` = Predicted value.
- `n` = Number of observations.
- `ȳ` = Mean of actual values.

**MAE (Mean Absolute Error):**

`MAE = Σ|yi − ŷi| / n`

- Average absolute prediction error.
- Expressed in the same unit as the target.

**MSE (Mean Squared Error):**

`MSE = Σ(yi − ŷi)² / n`

- Average squared prediction error.
- Penalizes larger errors more strongly.

**RMSE (Root Mean Squared Error):**

`RMSE = √MSE`

- Square root of MSE.
- Expressed in the same unit as the target.
- Sensitive to large errors.

**R² (Coefficient of Determination):**

`R² = 1 − [Σ(yi − ŷi)² / Σ(yi − ȳ)²]`

- Measures the proportion of variation in the target explained by the model.
- A value closer to 1 generally indicates a better fit.
- It can be negative when the model performs worse than predicting the mean on the evaluated data.

## 11. Stock Market Price Prediction — Case Study Outline

1. Collect historical stock data such as opening price, closing price, high, low and volume.
2. Clean missing or inconsistent values.
3. Select relevant input features.
4. Split data chronologically into training and testing sets to avoid using future information to predict the past.
5. Train a regression model using historical observations.
6. Predict stock prices for the test period.
7. Evaluate predictions using MAE, RMSE and R².

**Important:** Stock prices are influenced by many external factors. Regression predictions are estimates and do not guarantee future market prices.

## Last-Minute Recall

- Bias high → underfitting.
- Variance high → overfitting.
- Linear regression → `Y = a + bX`.
- Lasso → L1 penalty; may set coefficients to zero.
- Ridge → L2 penalty; shrinks coefficients.
- Gradient Descent → parameter update opposite to gradient.
- MAE → absolute errors.
- MSE → squared errors.
- RMSE → square root of MSE; same unit as target.
- R² → explained variation.
