# Machine Learning – Supervised Learning: Classification

> Source: ENDSEM ML.docx supplied by the user. The answer text below is transferred from the source in its original question order. Text and tables are retained where extractable; embedded diagram/formula images in the Word document may not appear in this Markdown transcription.

Q. Explain the Support Vector Machine (SVM) algorithm with a suitable diagram. Explain how SVM finds the
optimal hyperplane for classification. (5–6 Marks)

1. Introduction

Support Vector Machine (SVM) is a supervised machine learning algorithm mainly used for classification. It separates
data points belonging to different classes by finding the best possible decision boundary called a hyperplane.

SVM tries to maximize the margin between the two classes to improve classification performance on unseen data.

2. Important Terminologies

1. Hyperplane: A decision boundary that separates data points belonging to different classes. In 2D, it is a straight
line; in 3D, it is a plane.

2. Support Vectors: The data points closest to the hyperplane. They determine the position and orientation of the
optimal hyperplane.

3. Margin: The distance between the hyperplane and the nearest data points from both classes.

4. Optimal Hyperplane: The hyperplane that separates the classes while maximizing the margin between them.

3. Suitable Diagram

Support Vector Machine (SVM) in Python

reneshbedre.com

Diagram explanation:

       Different symbols represent two different classes.

       The central line represents the decision boundary or hyperplane.

       The two parallel lines represent the margin boundaries.

       The nearest data points are called support vectors.

4. Working of SVM Algorithm

    1. Input Data: Provide the labelled training dataset containing different classes.

    2. Identify Classes: Identify the data points belonging to each class.

    3. Find Hyperplane: SVM searches for a decision boundary that separates the classes.

    4. Identify Support Vectors: Find the nearest data points to the hyperplane.

    5. Calculate Margin: Calculate the distance between the hyperplane and the nearest data points.

    6. Maximize Margin: Select the hyperplane that provides the maximum possible margin.

    7. Classification: Use the selected hyperplane to classify new, unseen data points.

5. How SVM Finds the Optimal Hyperplane


SVM finds the optimal hyperplane by maximizing the margin between the two classes.

       It considers different possible separating hyperplanes.

       It identifies the nearest data points from both classes.

       These nearest points are called support vectors.

       It selects the hyperplane having the maximum margin.

       A larger margin generally helps the model generalize better to unseen data.

6. Advantages of SVM

    1. Effective in high-dimensional datasets.

    2. Works well for classification problems.

    3. Uses support vectors to determine the decision boundary.

    4. Can handle non-linear classification using kernel functions.

    5. Provides good generalization when appropriately configured.

7. Applications

       Email spam detection.

       Image classification.

       Face recognition.

       Medical diagnosis.

       Text classification.

8. Conclusion

Support Vector Machine is an effective supervised learning algorithm used for classification. It identifies an optimal
hyperplane by maximizing the margin between different classes using support vectors, helping improve classification
and generalization performance.


Q. Explain Kernel Methods used in SVM. Describe different kernel functions with suitable examples. (6 Marks)

1. Introduction

A Kernel Method in Support Vector Machine (SVM) is a technique used to handle non-linearly separable data by
transforming it into a higher-dimensional feature space where it may become linearly separable.

It uses a mathematical function called a Kernel Function to calculate similarities between data points without
explicitly performing the transformation.

This technique is also known as the Kernel Trick.

2. Why are Kernel Methods Required?

       Some datasets cannot be separated using a straight line or linear hyperplane.

       Kernel methods help SVM handle non-linear relationships.

       They transform the data into a higher-dimensional feature space.

       They help find a suitable decision boundary for classification.


Example:

Consider a dataset where one class is surrounded by another class in a circular pattern. A straight line cannot
separate these classes effectively. A suitable kernel can help SVM create a non-linear decision boundary.

3. Different Kernel Functions Used in SVM

1. Linear Kernel

        Used when data is approximately linearly separable.

        It creates a straight-line decision boundary in two dimensions.

        It is simple and computationally efficient.

Formula:

K(X, Y) = X · Y

Example: Classifying emails into spam and non-spam when the selected features are approximately linearly
separable.

2. Polynomial Kernel

        Used when the relationship between data points is non-linear.

        It considers combinations and interactions of input features.

        It can create curved decision boundaries.

Formula:

K(X, Y) = (X · Y + c)ᵈ

Where:

        c = Constant.

        d = Degree of the polynomial.

        X and Y = Input feature vectors.

Example: Classification of data that requires a curved or polynomial decision boundary.

3. Radial Basis Function (RBF) Kernel

        Also called the Gaussian Kernel.

        Used for complex non-linear datasets.

        Measures similarity based on the distance between two data points.

        It is widely used when the relationship between features is not known.

Formula:

K(X, Y) = exp(−γ × ||X − Y||²)

Where:

        γ (Gamma) = Controls the influence of individual data points.

        ||X − Y||² = Squared distance between two data points.

Example: Image classification where different classes have complex non-linear patterns.

4. Sigmoid Kernel


         Uses a sigmoid function similar to the activation function used in neural networks.

         It can create non-linear decision boundaries.

         It is related to neural network models.

Formula:

K(X, Y) = tanh(α × (X · Y) + c)

Where:

         α = Scaling parameter.

         c = Constant.

         tanh = Hyperbolic tangent function.

Example: Classification problems involving complex relationships between input features.

4. Comparison of Different Kernel Functions

Kernel        Main Characteristic                         Suitable Data

Linear        Straight-line decision boundary             Linearly separable data

Polynomial Models polynomial relationships                Non-linear data

RBF           Handles complex non-linear relationships Complex datasets

Sigmoid       Similar to neural network activation        Certain non-linear datasets

5. Advantages of Kernel Methods

      1. Handle non-linearly separable datasets.

      2. Help create flexible decision boundaries.

      3. Avoid explicitly computing higher-dimensional transformations.

      4. Support different types of data relationships.

      5. Improve classification performance when an appropriate kernel is selected.

6. Conclusion

Kernel Methods extend the capability of SVM by handling non-linear classification problems. Linear, Polynomial, RBF
and Sigmoid are commonly used kernel functions. Selecting the appropriate kernel helps SVM find an effective
decision boundary.


Q. What is Support Vector Regression (SVR)? Explain its working with a suitable example. (5 Marks)

1. Introduction

Support Vector Regression (SVR) is a supervised machine learning algorithm used for predicting continuous
numerical values.

It is an extension of Support Vector Machine (SVM) designed for regression problems.

Unlike ordinary regression, SVR tries to fit a function within a specified error margin called the Epsilon (ε) tube. It
penalizes only those prediction errors that fall outside this tube.


2. Important Terminologies

      1. Hyperplane: The regression function used to predict continuous values.

      2. Support Vectors: Data points that lie on or outside the epsilon margin and influence the regression function.

      3. Epsilon (ε): Defines the acceptable error margin around the predicted regression function.

      4. Kernel Function: Helps SVR handle non-linear relationships in the data.

      5. Margin: The region around the regression function within which errors are tolerated.

3. Working of SVR Algorithm

      1. Input Data: Provide the training dataset containing input and continuous output values.

      2. Select Regression Function: SVR tries to find a suitable regression function.

      3. Define Epsilon Tube: Set an acceptable error margin (ε) around the regression function.

      4. Identify Support Vectors: Identify data points that lie on or outside the epsilon tube boundaries.

      5. Minimize Error: Minimize errors for points outside the epsilon tube while keeping the regression function as
         simple as possible.

      6. Prediction: Use the trained model to predict continuous values for new input data.

4. Suitable Diagram


Diagram explanation:

         The central line represents the predicted regression function.

         The two parallel boundaries represent the epsilon tube.

         Data points inside the tube have no penalty for their prediction error.

         Data points outside the tube contribute to the loss function and can act as support vectors.

5. Suitable Example

Consider predicting house prices based on the area of houses.

House Area (sq. ft.) Actual Price (₹ Lakhs)

500                   25

700                   35


900                    45

1100                   60

1300                   65

Suppose the SVR model uses an epsilon value of 5 Lakhs.

         If the predicted price is within 5 Lakhs of the actual price, the error is tolerated.

         If the prediction error exceeds 5 Lakhs, the model penalizes the excess error.

         The model tries to find a regression function that balances prediction accuracy and model simplicity.

Thus, SVR predicts house prices while allowing a small acceptable prediction error.

6. Advantages of SVR

      1. Effective for high-dimensional datasets.

      2. Can handle non-linear regression using kernel functions.

      3. Less sensitive to small errors within the epsilon margin.

      4. Uses support vectors to determine the regression function.

      5. Provides good generalization when properly configured.

7. Conclusion

Support Vector Regression is an effective supervised learning algorithm for predicting continuous values. It uses an
epsilon-insensitive tube to tolerate small errors and identifies support vectors to construct an appropriate regression
function.


Q. Explain the K-Nearest Neighbour (KNN) algorithm with a suitable example. Discuss its advantages and
disadvantages. (5–6 Marks)

1. Introduction

K-Nearest Neighbour (KNN) is a supervised machine learning algorithm used for classification and regression.

It predicts the class or value of a new data point based on the K nearest data points in the training dataset.

KNN is called a lazy learning algorithm because it does not build an explicit model during training. Instead, it stores
the training data and performs calculations when a new prediction is required.

2. Working of KNN Algorithm

      1. Choose K: Select the number of nearest neighbours (K).

      2. Calculate Distance: Calculate the distance between the new data point and all training data points.

      3. Find Nearest Neighbours: Arrange the distances in ascending order.

      4. Select K Neighbours: Choose the K data points having the smallest distances.

      5. Majority Voting: For classification, count the classes of the selected neighbours.


    6. Prediction: Assign the class having the highest number of votes to the new data point.

For regression, KNN predicts the average (or a distance-weighted average) of the selected neighbours' target values.

3. Distance Calculation

KNN commonly uses Euclidean Distance to calculate the distance between two data points.

Euclidean Distance Formula:

Distance = √[(X₂ − X₁)² + (Y₂ − Y₁)²]

Where:

         (X₁, Y₁) = First data point.

         (X₂, Y₂) = Second data point.

4. Suitable Example

Consider a dataset used to classify fruits as Apples or Oranges based on weight and size.

A new fruit has the following properties:

         Weight = 150 grams

         Size = 7 cm

         K=3

Training dataset:

Fruit Weight (g) Size (cm) Class

A       140         6          Apple

B       160         8          Apple

C       145         7          Apple

D       180         9          Orange

E       170         8          Orange

Step 1: Calculate distances

For the new fruit (150, 7):

Distance from A:

Distance = √[(150 − 140)² + (7 − 6)²]

Distance = √101 = 10.05

Similarly, calculate the remaining distances.

Fruit Distance (Approx.) Class

A       10.05                Apple

B       10.05                Apple

C       5.00                 Apple

D       30.07                Orange


E       20.02                Orange

Step 2: Select K nearest neighbours

K=3

The three nearest neighbours are:

         C – Apple

         A – Apple

         B – Apple

Step 3: Majority Voting

         Apple = 3 votes

         Orange = 0 votes

Final Prediction: Apple

Therefore, the new fruit is classified as an Apple.

5. Advantages of KNN

    1. Simple and easy to understand and implement.

    2. No complex training process is required.

    3. Supports both classification and regression.

    4. Can handle multi-class classification problems.

    5. Can adapt to new training data without rebuilding a complex model.

6. Disadvantages of KNN

    1. Slow prediction for large datasets because distances must be calculated.

    2. Requires more memory to store the training dataset.

    3. Sensitive to irrelevant features and noisy data.

    4. Performance depends heavily on the selection of K.

    5. Sensitive to different feature scales, so normalization is often required.

7. Applications

         Image recognition.

         Recommendation systems.

         Medical diagnosis.

         Pattern recognition.

         Customer classification.

8. Conclusion

KNN is a simple supervised learning algorithm that classifies new data points based on the majority class of their
nearest neighbours. It is easy to implement but can become computationally expensive for large datasets.


Q. Explain different distance metrics used in the KNN algorithm. Solve a KNN numerical problem using the given
dataset. (6 Marks)

1. Introduction

K-Nearest Neighbour (KNN) is a supervised machine learning algorithm that classifies a new data point based on its
nearest neighbours.

Distance Metrics are mathematical methods used to calculate the distance or similarity between data points. KNN
uses these distances to identify the nearest neighbours.

2. Different Distance Metrics Used in KNN

1. Euclidean Distance

       It calculates the straight-line distance between two data points.

       It is commonly used for continuous numerical data.

       It is the most frequently used distance metric in KNN.

Formula:

Euclidean Distance = √[Σ(Xᵢ − Yᵢ)²]

Example:

For points A(2, 3) and B(5, 7):

Distance = √[(5 − 2)² + (7 − 3)²]

Distance = √(9 + 16) = √25 = 5

2. Manhattan Distance

       It calculates the distance by adding the absolute differences between coordinates.

       It is also called City Block Distance.

       It is useful when movement is restricted to horizontal and vertical directions.

Formula:

Manhattan Distance = Σ|Xᵢ − Yᵢ|

Example:

For A(2, 3) and B(5, 7):

Distance = |5 − 2| + |7 − 3|

Distance = 3 + 4 = 7

3. Minkowski Distance

       It is a generalized distance metric.

       It supports different distance calculations based on the parameter p.

       Euclidean and Manhattan distances are special cases of Minkowski distance.


Formula:

Minkowski Distance = [Σ|Xᵢ − Yᵢ|ᵖ]^(1/p)

Where p is the order of the distance metric.

4. Hamming Distance

        It calculates the number of positions where two equal-length strings or categorical vectors differ.

        It is useful for binary and categorical data.

Example:

A = 10110

B = 10011

Different positions = 2

Hamming Distance = 2

3. Solved KNN Numerical Example

Question: Consider the following dataset. Classify a new data point P(5, 5) using KNN with K = 3 and Euclidean
Distance.

Point X Y Class

A       2 3 Red

B       4 4 Red

C       6 5 Blue

D       7 7 Blue

E       3 6 Red

Step 1: Given Data

        New point P = (5, 5)

        K=3

        Distance metric = Euclidean Distance

Step 2: Calculate Euclidean Distance

Distance = √[(X₂ − X₁)² + (Y₂ − Y₁)²]

Distance from P(5, 5) to A(2, 3):

D(A) = √[(5 − 2)² + (5 − 3)²]

D(A) = √(9 + 4) = √13 = 3.61

Similarly, calculate the remaining distances.

Point Calculation Distance Class

A       √(3² + 2²)   3.61       Red

B       √(1² + 1²)   1.41       Red

C       √(1² + 0²)   1.00       Blue


D       √(2² + 2²)      2.83       Blue

E       √(2² + 1²)      2.24       Red

Step 3: Select 3 Nearest Neighbours

Arrange distances in ascending order:

Rank Point Distance Class

1       C       1.00        Blue

2       B       1.41        Red

3       E       2.24        Red

Step 4: Apply Majority Voting

           Red = 2 votes

           Blue = 1 vote

Final Prediction: Red

Therefore, the new data point P(5, 5) belongs to the Red class.

4. Comparison of Distance Metrics

Distance Metric Main Use

Euclidean              Continuous numerical data

Manhattan              Grid-based or coordinate data

Minkowski              Generalized distance calculation

Hamming                Binary and categorical data

5. Conclusion

Distance metrics play an important role in the KNN algorithm because they determine the nearest neighbours of a
new data point. Euclidean, Manhattan, Minkowski and Hamming are commonly used metrics. The choice of distance
metric depends on the nature of the dataset.


Q. What is Ensemble Learning? Explain its importance and different ensemble learning methods. Differentiate
between Bagging and Boosting. (4–6 Marks)

1. Introduction

Ensemble Learning is a Machine Learning technique that combines predictions from multiple individual models
(called base learners) to produce a more accurate and reliable final prediction.

Instead of depending on a single model, ensemble learning uses multiple models to improve overall performance.

Example: Combining predictions from multiple decision trees to classify whether an email is spam or non-spam.

2. Importance of Ensemble Learning

    1. Improves Accuracy: Combines multiple models to achieve better prediction performance.

    2. Reduces Overfitting: Some ensemble methods reduce the risk of overfitting.


   3. Improves Stability: Reduces the effect of individual model errors.

   4. Handles Complex Problems: Helps solve complex classification and regression problems.

   5. Better Generalization: Can improve performance on unseen data.

   6. Reduces Bias and Variance: Different ensemble methods help control bias and variance.

3. Different Ensemble Learning Methods

1. Bagging (Bootstrap Aggregating)

       Multiple models are trained independently using different bootstrap samples of the training dataset.

       Predictions are combined using majority voting for classification or averaging for regression.

       It mainly helps reduce variance.

Example: Random Forest.

2. Boosting

       Multiple weak learners are trained sequentially.

       Each new learner focuses more on the errors made by previous learners.

       Final predictions are combined using weighted voting or weighted summation.

Examples: AdaBoost and Gradient Boosting.

3. Stacking (Stacked Generalization)

       Combines predictions from multiple different base models.

       A meta-model learns how to combine their predictions.

       It uses the strengths of different algorithms to improve performance.

Example: Combining Decision Tree, KNN and SVM predictions using Logistic Regression as a meta-model.

4. Difference Between Bagging and Boosting

Bagging                                          Boosting

Stands for Bootstrap Aggregating.                Combines weak learners sequentially.

Models are trained independently.                Models are trained sequentially.

Uses different bootstrap samples.                Later learners focus on previous errors.

Models can be trained in parallel.               Training is generally sequential.

Mainly reduces variance.                         Mainly reduces bias, though it can also affect variance.

Combines predictions using voting or averaging. Combines predictions using weighted voting or summation.

Less sensitive to noise in many applications.    Can be sensitive to noisy data and outliers.

Example: Random Forest.                          Examples: AdaBoost, Gradient Boosting.

5. Suitable Diagram


Diagram explanation:

      Bagging: Training data is divided into bootstrap samples, models are trained independently, and their
       predictions are combined.

      Boosting: Models are trained one after another, with each model focusing on errors made by previous
       models.

6. Advantages of Ensemble Learning

   1. Improves prediction accuracy.

   2. Provides better model stability.

   3. Combines strengths of multiple algorithms.

   4. Can reduce prediction errors.

   5. Applicable to both classification and regression.

7. Conclusion

Ensemble Learning combines multiple machine learning models to improve prediction performance. Bagging trains
models independently and mainly reduces variance, whereas Boosting trains models sequentially and focuses on
correcting previous errors.


Q. Explain the Random Forest algorithm with a suitable diagram and example. (5–6 Marks)

1. Introduction

Random Forest is a supervised Machine Learning algorithm used for both classification and regression problems.

It is an ensemble learning technique that combines multiple Decision Trees to produce a more accurate and reliable
prediction.

It uses two important techniques:

   1. Bootstrap Sampling: Creates multiple random training datasets by selecting samples from the original
      dataset with replacement.

   2. Feature Randomness: Selects a random subset of features when splitting nodes in each decision tree.


The final prediction is obtained by combining the predictions of all decision trees.

2. Working of Random Forest Algorithm

    1. Input Dataset: Provide the original training dataset.

    2. Bootstrap Sampling: Generate multiple random samples from the original dataset using sampling with
       replacement.

    3. Build Decision Trees: Train a separate Decision Tree on each bootstrap sample.

    4. Random Feature Selection: Select a random subset of features at each split while building the trees.

    5. Generate Predictions: Each Decision Tree independently predicts the output.

    6. Combine Predictions:

            o   Classification: Use majority voting.

            o   Regression: Calculate the average of all tree predictions.

    7. Final Output: Return the combined prediction.

3. Suitable Diagram


Diagram Explanation:

       The original dataset is divided into multiple bootstrap samples.

       Each sample is used to train a separate Decision Tree.

       All trees generate individual predictions.

       Their predictions are combined using majority voting or averaging.

       The final output is generated.

4. Suitable Example

Consider a Random Forest model used to predict whether a customer will purchase a product.

Suppose five Decision Trees generate the following predictions:

Decision Tree Prediction


Tree 1          Yes

Tree 2          Yes

Tree 3          No

Tree 4          Yes

Tree 5          No

Majority Voting:

        Yes = 3 votes

        No = 2 votes

Final Prediction = Yes

Therefore, the Random Forest model predicts that the customer will purchase the product.

5. Advantages of Random Forest

    1. Provides high prediction accuracy in many applications.

    2. Reduces overfitting compared with individual deep decision trees in many cases.

    3. Handles large datasets with multiple features.

    4. Works for both classification and regression.

    5. Handles complex relationships between input features.

    6. Provides feature importance estimates.

6. Disadvantages of Random Forest

    1. Requires more computational resources than a single decision tree.

    2. Requires more memory to store multiple trees.

    3. Less interpretable than an individual decision tree.

    4. Prediction can be slower when the forest contains many trees.

7. Applications

        Medical diagnosis.

        Fraud detection.

        Customer behaviour prediction.

        Credit risk assessment.

        Image classification.

8. Conclusion

Random Forest is a powerful ensemble learning algorithm that combines multiple Decision Trees using bootstrap
sampling and random feature selection. It improves prediction performance by combining individual tree outputs
through majority voting or averaging.


Q. Explain the AdaBoost algorithm with a suitable example. (6 Marks)

1. Introduction

AdaBoost (Adaptive Boosting) is an ensemble learning algorithm used for classification and regression problems. It
combines multiple weak learners to create a strong predictive model.

It works by training weak learners sequentially, where each new learner focuses more on the training examples
incorrectly classified by previous learners.

A weak learner is a model that performs slightly better than random guessing.

2. Working of AdaBoost Algorithm

    1. Initialize Weights: Assign equal weights to all training samples.

    2. Train Weak Learner: Train the first weak classifier using the weighted training dataset.

    3. Calculate Classification Error: Calculate the weighted error of the classifier.

    4. Update Classifier Weight: Give greater importance to classifiers having lower error.

    5. Update Sample Weights: Increase the weights of incorrectly classified samples and decrease the weights of
       correctly classified samples.

    6. Train Next Learner: Train the next weak learner using the updated sample weights.

    7. Combine Predictions: Combine the predictions of all weak learners using weighted voting to obtain the final
       prediction.

3. Suitable Diagram

Gradient Boosting

arunp77.github.io

Diagram explanation:

       Initially, all training samples receive equal weights.

       The first weak learner classifies the samples.

       Misclassified samples receive higher weights.

       The next learner focuses more on these difficult samples.

       Finally, predictions from all weak learners are combined using weighted voting.

4. Suitable Example

Consider an AdaBoost model used to classify emails as Spam or Not Spam.

Suppose the training dataset contains 5 emails.

Initial Sample Weights:

Each email receives an equal weight.

Weight of each sample = 1/5 = 0.2

First Weak Learner:

Suppose the first classifier makes the following predictions:

Email Actual Class Predicted Class Result


E1       Spam         Spam             Correct

E2       Not Spam     Spam             Incorrect

E3       Spam         Spam             Correct

E4       Not Spam     Not Spam         Correct

E5       Spam         Not Spam         Incorrect

The classifier incorrectly classifies E2 and E5.

Weight Update:

         The weights of incorrectly classified emails E2 and E5 are increased.

         The weights of correctly classified emails are decreased.

         The next weak learner focuses more on E2 and E5.

Second Weak Learner:

The second classifier is trained using the updated sample weights and gives more attention to previously
misclassified emails.

Final Prediction:

The predictions of all weak learners are combined using weighted majority voting.

Thus, the final model produces a stronger classification result than an individual weak learner.

5. Advantages of AdaBoost

     1. Combines multiple weak learners to create a strong learner.

     2. Improves classification accuracy.

     3. Focuses on previously misclassified samples.

     4. Simple to understand and implement.

     5. Can reduce bias by combining multiple weak learners.

6. Disadvantages of AdaBoost

     1. Sensitive to noisy data and outliers.

     2. Training is sequential, so parallel training is difficult.

     3. Performance depends on the quality of weak learners.

     4. Can overfit in some situations, especially with noisy data or excessive boosting rounds.

7. Applications

         Spam email detection.

         Face detection.

         Fraud detection.

         Customer classification.

         Medical diagnosis.

8. Conclusion


AdaBoost is an ensemble learning technique that combines multiple weak learners sequentially to create a strong
predictive model. It increases the importance of incorrectly classified samples so that subsequent learners focus on
reducing previous errors.


Q. Explain the AdaBoost algorithm with a suitable example. (6 Marks)

1. Introduction

AdaBoost (Adaptive Boosting) is an ensemble learning algorithm used for classification and regression problems. It
combines multiple weak learners to create a strong predictive model.

It works by training weak learners sequentially, where each new learner focuses more on the training examples
incorrectly classified by previous learners.

A weak learner is a model that performs slightly better than random guessing.

2. Working of AdaBoost Algorithm

    1. Initialize Weights: Assign equal weights to all training samples.

    2. Train Weak Learner: Train the first weak classifier using the weighted training dataset.

    3. Calculate Classification Error: Calculate the weighted error of the classifier.

    4. Update Classifier Weight: Give greater importance to classifiers having lower error.

    5. Update Sample Weights: Increase the weights of incorrectly classified samples and decrease the weights of
       correctly classified samples.

    6. Train Next Learner: Train the next weak learner using the updated sample weights.

    7. Combine Predictions: Combine the predictions of all weak learners using weighted voting to obtain the final
       prediction.

3. Suitable Diagram


Diagram explanation:

       Initially, all training samples receive equal weights.

       The first weak learner classifies the samples.

       Misclassified samples receive higher weights.


         The next learner focuses more on these difficult samples.

         Finally, predictions from all weak learners are combined using weighted voting.

4. Suitable Example

Consider an AdaBoost model used to classify emails as Spam or Not Spam.

Suppose the training dataset contains 5 emails.

Initial Sample Weights:

Each email receives an equal weight.

Weight of each sample = 1/5 = 0.2

First Weak Learner:

Suppose the first classifier makes the following predictions:

Email Actual Class Predicted Class Result

E1       Spam        Spam             Correct

E2       Not Spam    Spam             Incorrect

E3       Spam        Spam             Correct

E4       Not Spam    Not Spam         Correct

E5       Spam        Not Spam         Incorrect

The classifier incorrectly classifies E2 and E5.

Weight Update:

         The weights of incorrectly classified emails E2 and E5 are increased.

         The weights of correctly classified emails are decreased.

         The next weak learner focuses more on E2 and E5.

Second Weak Learner:

The second classifier is trained using the updated sample weights and gives more attention to previously
misclassified emails.

Final Prediction:

The predictions of all weak learners are combined using weighted majority voting.

Thus, the final model produces a stronger classification result than an individual weak learner.

5. Advantages of AdaBoost

     1. Combines multiple weak learners to create a strong learner.

     2. Improves classification accuracy.

     3. Focuses on previously misclassified samples.

     4. Simple to understand and implement.

     5. Can reduce bias by combining multiple weak learners.

6. Disadvantages of AdaBoost


    1. Sensitive to noisy data and outliers.

    2. Training is sequential, so parallel training is difficult.

    3. Performance depends on the quality of weak learners.

    4. Can overfit in some situations, especially with noisy data or excessive boosting rounds.

7. Applications

       Spam email detection.

       Face detection.

       Fraud detection.

       Customer classification.

       Medical diagnosis.

8. Conclusion

AdaBoost is an ensemble learning technique that combines multiple weak learners sequentially to create a strong
predictive model. It increases the importance of incorrectly classified samples so that subsequent learners focus on
reducing previous errors.


Q. What is Binary Classification and Multiclass Classification? Explain the different variants of Multiclass
Classification with examples. (5–6 Marks)

1. Binary Classification

Binary Classification is a supervised machine learning technique in which the model classifies input data into exactly
two mutually exclusive classes.

Examples:

       Email classification: Spam or Not Spam.

       Medical diagnosis: Disease or No Disease.

       Loan prediction: Approved or Rejected.

2. Multiclass Classification

Multiclass Classification is a supervised machine learning technique in which the model classifies input data into
three or more mutually exclusive classes.

Examples:

       Fruit classification: Apple, Orange or Banana.

       Handwritten digit recognition: 0 to 9.

       Thyroid disorder classification:

            o     Hyperthyroid

            o     Hypothyroid

            o     Euthyroid-sick


             o   Euthyroid

3. Different Variants of Multiclass Classification

There are two commonly used approaches:

A. One-vs-Rest (OvR) / One-vs-All (OvA)

Definition: One-vs-Rest is a multiclass classification technique in which one binary classifier is trained for each class
against all the remaining classes.

Working:

    1. Identify all the classes in the dataset.

    2. Create one binary classifier for each class.

    3. Each classifier treats its selected class as positive and all other classes as negative.

    4. Train all classifiers independently.

    5. For a new input, calculate the prediction score from each classifier.

    6. Select the class with the highest score.

Example:

Consider a fruit classification problem with three classes: Apple, Orange and Banana.


Select the class with the highest score

For 3 classes, 3 binary classifiers are required.

B. One-vs-One (OvO)

Definition: One-vs-One is a multiclass classification technique in which a separate binary classifier is trained for every
pair of classes.

Working:

    1. Identify all classes in the dataset.

    2. Create a binary classifier for every possible pair of classes.

    3. Train each classifier using data belonging to only those two classes.

    4. Each classifier predicts one class for a new input.

    5. Count the votes received by each class.


    6. Select the class with the maximum number of votes.

Example:

Consider a fruit classification problem with three classes: Apple, Orange and Banana.

One-vs-One approach

Fruit Dataset

Classifier 1

Apple vs Orange

Classifier 2

Apple vs Banana

Classifier 3

Orange vs Banana

Majority Voting

For 3 classes, 3 binary classifiers are required.

4. Formula for Number of Classifiers

For One-vs-Rest:

Number of classifiers = K

For One-vs-One:

Number of classifiers = K × (K − 1) / 2

Where K = Number of classes.

Example: If there are 4 classes:

       OvR = 4 classifiers.

       OvO = 4 × 3 / 2 = 6 classifiers.

5. Difference Between Binary and Multiclass Classification

Binary Classification                      Multiclass Classification

Classifies data into two classes.          Classifies data into three or more classes.

Has two possible output classes.           Has multiple possible output classes.

Uses one binary classification model. Can use OvR or OvO approaches.

Example: Spam or Not Spam.                 Example: Apple, Orange or Banana.

Simpler classification problem.            Comparatively more complex classification problem.

6. Difference Between OvR and OvO

One-vs-Rest (OvR)                                            One-vs-One (OvO)

Trains one classifier for each class.                        Trains one classifier for each pair of classes.

Each classifier separates one class from all others.         Each classifier separates two individual classes.


Requires K classifiers.                                  Requires K × (K − 1) / 2 classifiers.

Uses the highest prediction score.                       Generally uses majority voting.

Each classifier uses the complete dataset for training. Each classifier uses data from two selected classes.

Computationally simpler when there are many classes. Number of classifiers increases rapidly with classes.

7. Conclusion

Binary Classification predicts one of two classes, whereas Multiclass Classification predicts one among three or more
classes. One-vs-Rest and One-vs-One are two important approaches used to solve multiclass classification problems.


Q. Explain the problems associated with balanced and imbalanced multiclass classification. Discuss suitable
approaches for handling imbalanced datasets. (6 Marks)

1. Introduction

Multiclass Classification is a supervised machine learning technique used to classify data into three or more classes.

Based on the distribution of samples among different classes, multiclass datasets are classified into:

    1. Balanced Dataset

    2. Imbalanced Dataset

2. Balanced Multiclass Classification

A Balanced Dataset is a dataset in which all classes have approximately equal numbers of training examples.

Example:

Consider a fruit classification dataset:

Fruit Class Number of Samples

Apple       100

Orange      100

Banana      100

Problems:

    1. Some classes may still be difficult to distinguish because of overlapping features.

    2. A large number of classes increases classification complexity.

    3. The model may require more computational resources as the number of classes increases.

3. Imbalanced Multiclass Classification

An Imbalanced Dataset is a dataset in which some classes contain significantly more samples than other classes.

Example:

Consider a medical diagnosis dataset:

Disease Class Number of Samples


Class A            900

Class B            80

Class C            20

Here, Class A is the majority class, while Class B and Class C are minority classes.

Problems Associated with Imbalanced Datasets:

    1. Class Bias: The model becomes biased towards the majority class.

    2. Poor Minority Class Prediction: The model may fail to correctly identify minority class samples.

    3. Misleading Accuracy: A model may achieve high accuracy by predicting mostly the majority class.

    4. Poor Generalization: The model may not learn sufficient patterns from minority class samples.

    5. Incorrect Evaluation: Accuracy alone may not represent actual classification performance.

4. Approaches for Handling Imbalanced Datasets

1. Oversampling

         Increases the number of samples belonging to minority classes.

         Creates additional samples by duplicating existing minority class examples or generating synthetic examples.

         Helps balance the class distribution.

Example: Increasing Class C samples from 20 to 100.

2. Undersampling

         Reduces the number of samples belonging to majority classes.

         Removes selected majority class examples.

         Helps balance the dataset and reduce training time.

Example: Reducing Class A samples from 900 to 100.

3. SMOTE (Synthetic Minority Over-sampling Technique)

         A technique used to generate synthetic samples for minority classes.

         Creates new examples using existing minority class samples and their nearest neighbours.

         Helps improve minority class representation.

4. Class Weighting

         Assigns higher weights to minority classes and lower weights to majority classes during training.

         Penalizes incorrect predictions of minority class samples more heavily.

         Helps the model pay more attention to minority classes.

5. Use Suitable Evaluation Metrics

Instead of depending only on accuracy, use:

         Precision

         Recall

         F1-score


       Macro-average F1-score

       Confusion Matrix

These metrics help evaluate performance across different classes.

5. Difference Between Balanced and Imbalanced Datasets

Balanced Dataset                                    Imbalanced Dataset

Classes have approximately equal samples.           Classes have unequal sample distribution.

Less class-distribution bias.                       More chances of majority class bias.

Model gets sufficient examples from each class.     Minority classes may have insufficient examples.

Accuracy is generally more informative.             Accuracy can be misleading.

Usually requires less class-balancing intervention. May require oversampling, undersampling or class weighting.

6. Conclusion

Balanced datasets provide approximately equal representation of all classes, whereas imbalanced datasets contain
unequal class distributions. Imbalanced datasets can cause majority class bias and poor minority class prediction.
Techniques such as oversampling, undersampling, SMOTE and class weighting help improve classification
performance.


Q. Explain the Confusion Matrix and its importance in evaluating classification models. (6 Marks)

1. Introduction

A Confusion Matrix is a table used to evaluate the performance of a classification model by comparing the actual
class labels with the predicted class labels.

It shows the number of correct and incorrect predictions made by the model. It is mainly used to calculate evaluation
metrics such as Accuracy, Precision, Recall and F1-Score.

2. Confusion Matrix for Binary Classification

A confusion matrix for binary classification contains four values:

Actual / Predicted Predicted Positive Predicted Negative

Actual Positive     True Positive (TP) False Negative (FN)

Actual Negative     False Positive (FP) True Negative (TN)

Explanation of terms:

    1. True Positive (TP): Model correctly predicts the positive class.

    2. True Negative (TN): Model correctly predicts the negative class.

    3. False Positive (FP): Model incorrectly predicts positive when the actual class is negative. Also called Type I
       Error.

    4. False Negative (FN): Model incorrectly predicts negative when the actual class is positive. Also called Type II
       Error.


3. Example

Consider a disease prediction model tested on 100 patients.

Actual / Predicted Disease No Disease

Disease              40 (TP) 10 (FN)

No Disease           5 (FP)   45 (TN)

From the matrix:

         TP = 40

         TN = 45

         FP = 5

         FN = 10

         Total predictions = 100

4. Evaluation Metrics Calculated Using Confusion Matrix

1. Accuracy: Measures the proportion of total correct predictions.

Accuracy = (TP + TN) / (TP + TN + FP + FN)

= (40 + 45) / 100 = 85%

2. Precision: Measures how many predicted positive cases are actually positive.

Precision = TP / (TP + FP)

= 40 / (40 + 5) = 88.89%

3. Recall (Sensitivity): Measures how many actual positive cases are correctly identified.

Recall = TP / (TP + FN)

= 40 / (40 + 10) = 80%

4. F1-Score: Harmonic mean of Precision and Recall.

F1-Score = 2 × (Precision × Recall) / (Precision + Recall)

= 2 × (0.8889 × 0.80) / (0.8889 + 0.80)

= 0.8421 or 84.21%

5. Importance of Confusion Matrix

    1. Performance Evaluation: Helps measure the classification model's performance.

    2. Error Identification: Identifies false positive and false negative predictions.

    3. Metric Calculation: Provides values required to calculate Accuracy, Precision, Recall and F1-Score.

    4. Model Comparison: Helps compare different classification algorithms.

    5. Imbalanced Dataset Handling: Helps identify poor performance on minority classes, even when accuracy is
       high.

    6. Decision Making: Helps select a model based on the cost of different classification errors.

6. Conclusion


A confusion matrix is an important evaluation tool for classification models. It provides a detailed view of correct and
incorrect predictions and helps evaluate model performance using different metrics.


Q. Explain classification evaluation metrics with suitable examples and numericals. (6–8 Marks)

1. Introduction

Classification evaluation metrics are used to measure how effectively a classification model predicts the correct class
labels.

These metrics are calculated using the Confusion Matrix, which contains four values:

       True Positive (TP): Correctly predicted positive cases.

       True Negative (TN): Correctly predicted negative cases.

       False Positive (FP): Negative cases incorrectly predicted as positive.

       False Negative (FN): Positive cases incorrectly predicted as negative.

2. Important Classification Evaluation Metrics

1. Accuracy

Accuracy measures the percentage of total predictions that are correct.

Formula:

Accuracy = (TP + TN) / (TP + TN + FP + FN)

2. Precision

Precision measures how many predicted positive cases are actually positive.

Formula:

Precision = TP / (TP + FP)

3. Recall (Sensitivity)

Recall measures how many actual positive cases are correctly identified by the model.

Formula:

Recall = TP / (TP + FN)

4. Specificity

Specificity measures how many actual negative cases are correctly identified.

Formula:

Specificity = TN / (TN + FP)

5. F1-Score

F1-Score is the harmonic mean of Precision and Recall. It provides a balance between both metrics.

Formula:

F1-Score = 2 × (Precision × Recall) / (Precision + Recall)


3. Numerical Example

Consider a disease prediction model tested on 100 patients. Its confusion matrix is:

Actual / Predicted Disease No Disease

Disease                 40 (TP) 10 (FN)

No Disease              5 (FP)   45 (TN)

Given:

         TP = 40

         TN = 45

         FP = 5

         FN = 10

         Total = 100

Step 1: Calculate Accuracy

Accuracy = (TP + TN) / Total

= (40 + 45) / 100

= 85 / 100 = 85%

Step 2: Calculate Precision

Precision = TP / (TP + FP)

= 40 / (40 + 5)

= 40 / 45 = 88.89%

Step 3: Calculate Recall

Recall = TP / (TP + FN)

= 40 / (40 + 10)

= 40 / 50 = 80%

Step 4: Calculate Specificity

Specificity = TN / (TN + FP)

= 45 / (45 + 5)

= 45 / 50 = 90%

Step 5: Calculate F1-Score

F1-Score = 2 × (Precision × Recall) / (Precision + Recall)

= 2 × (0.8889 × 0.80) / (0.8889 + 0.80)

= 84.21%

4. Summary of Results

Evaluation Metric Result

Accuracy                85%


Precision           88.89%

Recall              80%

Specificity         90%

F1-Score            84.21%

5. Importance of Classification Metrics

    1. Performance Measurement: Measures how accurately a model classifies data.

    2. Error Analysis: Helps identify false positive and false negative predictions.

    3. Model Comparison: Helps compare different classification algorithms.

    4. Imbalanced Datasets: Precision, Recall and F1-Score provide better insights when class distribution is
       unequal.

    5. Decision Making: Helps select a model based on the application. For example, recall is important in disease
       detection because missing an actual disease case can be serious.

6. Conclusion

Classification evaluation metrics help measure the effectiveness of classification models. Accuracy, Precision, Recall,
Specificity and F1-Score provide different perspectives on model performance and help select a suitable classification
algorithm.


Q. Explain the relationship between Precision and Recall with a suitable example. (4 Marks)

1. Introduction

Precision and Recall are two important evaluation metrics used to measure the performance of classification models,
especially in binary classification.

Both metrics focus on the correct identification of positive cases, but they measure different aspects of model
performance.

2. Precision

Precision measures how many of the cases predicted as positive are actually positive.

Formula:

Precision = TP / (TP + FP)

        High precision means fewer false positive predictions.

        It is important when false positive predictions are costly.

3. Recall

Recall measures how many actual positive cases are correctly identified by the model.

Formula:

Recall = TP / (TP + FN)


         High recall means fewer false negative predictions.

         It is important when missing a positive case is costly.

4. Relationship Between Precision and Recall

    1. Precision and Recall are often inversely related.

    2. Increasing Recall may increase False Positives, which can reduce Precision.

    3. Increasing Precision may reduce the number of positive predictions, potentially increasing False Negatives
       and reducing Recall.

    4. The required balance depends on the application.

    5. F1-Score is used to balance Precision and Recall.

F1-Score = 2 × (Precision × Recall) / (Precision + Recall)

5. Suitable Example

Consider a disease detection model tested on 100 patients.

Actual / Predicted Disease No Disease

Disease              40 (TP) 10 (FN)

No Disease           5 (FP)   45 (TN)

Precision:

= TP / (TP + FP)

= 40 / (40 + 5)

= 88.89%

Recall:

= TP / (TP + FN)

= 40 / (40 + 10)

= 80%

This means:

         Out of all patients predicted to have the disease, 88.89% actually have it.

         The model correctly identifies 80% of all patients who actually have the disease.

6. Conclusion

Precision focuses on the correctness of positive predictions, whereas Recall focuses on identifying all actual positive
cases. A good classification model should maintain a suitable balance between both metrics according to the
application.


Q. Explain Micro-Average and Macro-Average Precision, Recall and F-score. Solve a numerical problem using a
multiclass confusion matrix. (6 Marks)


1. Introduction

In multiclass classification, a model predicts one class from more than two possible classes.

Micro-Average and Macro-Average are techniques used to calculate overall Precision, Recall and F1-Score across
multiple classes.

They help evaluate the performance of multiclass classification models, especially when the dataset has an unequal
number of samples in different classes.

2. Micro-Average

Micro-Average calculates evaluation metrics by adding the TP, FP and FN values of all classes first and then calculating
the overall metric.

Formulas:

Micro-Precision = Total TP / (Total TP + Total FP)

Micro-Recall = Total TP / (Total TP + Total FN)

Micro-F1 = 2 × (Micro-Precision × Micro-Recall) / (Micro-Precision + Micro-Recall)

Characteristics:

        Gives equal importance to every individual prediction.

        Considers the total number of correct and incorrect predictions.

        Suitable when overall classification performance is important.

3. Macro-Average

Macro-Average calculates Precision, Recall and F1-Score separately for each class and then takes their arithmetic
mean.

Formulas:

Macro-Precision = (P1 + P2 + ... + Pk) / k

Macro-Recall = (R1 + R2 + ... + Rk) / k

Macro-F1 = (F1₁ + F1₂ + ... + F1ₖ) / k

Where:

        P = Precision of a class

        R = Recall of a class

        F1 = F1-Score of a class

        k = Total number of classes

Characteristics:

        Gives equal importance to every class.

        Helps evaluate performance on minority classes.

        Useful for imbalanced datasets.

4. Numerical Example Using Multiclass Confusion Matrix

Consider a classification model that classifies 3 types of fruits: Apple, Banana and Orange.

The confusion matrix is:


Actual / Predicted Apple Banana Orange

Apple               40     5          5

Banana              3      30         7

Orange              2      8          40

Total samples = 140

5. Calculate Class-Wise Metrics

For each class, consider that class as Positive and all other classes as Negative.

Class    TP FP FN

Apple    40 5 10

Banana 30 13 10

Orange 40 12 10

Step 1: Calculate Precision, Recall and F1-Score

For Apple:

Precision = 40 / (40 + 5) = 0.8889

Recall = 40 / (40 + 10) = 0.8000

F1 = 2 × (0.8889 × 0.8000) / (0.8889 + 0.8000)

= 0.8421

For Banana:

Precision = 30 / (30 + 13) = 0.6977

Recall = 30 / (30 + 10) = 0.7500

F1 = 2 × (0.6977 × 0.7500) / (0.6977 + 0.7500)

= 0.7231

For Orange:

Precision = 40 / (40 + 12) = 0.7692

Recall = 40 / (40 + 10) = 0.8000

F1 = 2 × (0.7692 × 0.8000) / (0.7692 + 0.8000)

= 0.7843

6. Calculate Macro-Average

Macro-Precision:

= (0.8889 + 0.6977 + 0.7692) / 3

= 0.7853 = 78.53%

Macro-Recall:

= (0.8000 + 0.7500 + 0.8000) / 3

= 0.7833 = 78.33%


Macro-F1:

= (0.8421 + 0.7231 + 0.7843) / 3

= 0.7832 = 78.32%

7. Calculate Micro-Average

Total TP = 40 + 30 + 40 = 110

Total FP = 5 + 13 + 12 = 30

Total FN = 10 + 10 + 10 = 30

Micro-Precision:

= 110 / (110 + 30)

= 78.57%

Micro-Recall:

= 110 / (110 + 30)

= 78.57%

Micro-F1:

= 2 × (0.7857 × 0.7857) / (0.7857 + 0.7857)

= 78.57%

8. Comparison Between Micro and Macro Average

Micro-Average                                      Macro-Average

Calculates metrics using total TP, FP and FN.      Calculates metrics separately for each class.

Gives equal importance to individual predictions. Gives equal importance to each class.

Influenced more by classes with more samples.      Treats minority and majority classes equally.

Useful for overall model performance.              Useful for evaluating imbalanced datasets.

9. Conclusion

Micro-Average measures the overall classification performance by combining results of all classes, whereas Macro-
Average calculates the average performance of individual classes. Both methods are useful for evaluating multiclass
classification models.
