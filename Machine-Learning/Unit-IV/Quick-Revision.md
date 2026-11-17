# Unit IV — Quick Revision
## Supervised Learning: Classification

### 1. K-Nearest Neighbour (KNN)

- KNN is a supervised, instance-based learning algorithm.
- It classifies a new data point using the majority class among its K nearest training points.
- Basic steps: choose K, calculate distances, sort distances, select K neighbours, use majority voting.
- Common distance metric: Euclidean Distance = √[Σ(xᵢ − yᵢ)²]

### 2. Support Vector Machine (SVM)

- SVM finds an optimal hyperplane that separates classes.
- It aims to maximize the margin between the nearest points of different classes.
- Support vectors are the data points closest to the separating hyperplane.
- Kernel functions help SVM handle non-linear decision boundaries.

### 3. Support Vector Regression (SVR)

- SVR predicts continuous values.
- It uses an epsilon (ε) tube around the regression function.
- Errors within the epsilon tube are tolerated; points outside the tube contribute to the loss.

### 4. Ensemble Learning

- Ensemble learning combines predictions from multiple models.
- Bagging: models are trained independently/in parallel on bootstrap samples; predictions are combined.
- Boosting: weak learners are trained sequentially; later learners focus on earlier errors.
- Random Forest: combines multiple decision trees using bootstrap sampling and random feature selection.
- AdaBoost: updates sample weights so misclassified examples receive greater attention.

### 5. Binary and Multiclass Classification

- Binary classification predicts one of two classes.
- Multiclass classification predicts one class from more than two classes.
- One-vs-Rest (One-vs-All): train one classifier per class against all remaining classes.
- One-vs-One: train classifiers for pairs of classes.

### 6. Confusion Matrix

| Actual / Predicted | Positive | Negative |
|---|---|---|
| Positive | TP | FN |
| Negative | FP | TN |

- TP: correctly predicted positive.
- TN: correctly predicted negative.
- FP: negative case incorrectly predicted positive.
- FN: positive case incorrectly predicted negative.

### 7. Classification Metrics

- Accuracy = (TP + TN) / (TP + TN + FP + FN)
- Precision = TP / (TP + FP)
- Recall = TP / (TP + FN)
- F1-Score = 2 × (Precision × Recall) / (Precision + Recall)

### 8. Micro and Macro Averaging

- Micro-average: aggregate TP, FP and FN across classes first, then calculate the metric.
- Macro-average: calculate the metric separately for each class, then take the unweighted mean.

### 9. K-Fold Cross-Validation

1. Divide the dataset into K folds.
2. Use one fold for testing and K−1 folds for training.
3. Repeat K times, changing the test fold each time.
4. Average the K evaluation scores.

### Diagrams to Revise

- [SVM maximum-margin hyperplane](Images/svm-hyperplane.svg)
- [SVR epsilon tube](Images/svr-epsilon-tube.svg)
- [Bagging vs Boosting](Images/bagging-boosting.svg)
- [Random Forest](Images/random-forest.svg)
- [AdaBoost](Images/adaboost.svg)
- [Confusion Matrix](Images/confusion-matrix.svg)
- [5-Fold Cross-Validation](Images/kfold-cross-validation.svg)

**Important:** Refer to [Complete Answers](Complete-Answers.md) for the full explanations, numerical problems and exact source wording.
