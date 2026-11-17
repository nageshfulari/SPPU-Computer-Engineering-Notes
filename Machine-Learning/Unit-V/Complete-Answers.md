# Machine Learning – Unsupervised Learning

> Source: ENDSEM ML.docx supplied by the user. The answer text below is transferred from the source in its original question order. Text and tables are retained where extractable; embedded diagram/formula images in the Word document may not appear in this Markdown transcription.

Q. What is K-Fold Cross-Validation? Explain its working and discuss the effect of choosing a very large or very small
value of K. (9 Marks)

1. Introduction

K-Fold Cross-Validation is a model evaluation technique used in Machine Learning to estimate how well a model
performs on unseen data.

In this technique, the dataset is divided into K equal or nearly equal parts called folds. The model is trained and
tested K times using different folds.


2. Working of K-Fold Cross-Validation

The working process is as follows:

    1. Divide the Dataset: Divide the complete dataset into K equal or nearly equal folds.

    2. Select Training and Testing Data: In the first iteration, use one fold for testing and the remaining K-1 folds for
       training.

    3. Train the Model: Train the model using the training folds.

    4. Evaluate the Model: Test the trained model using the selected testing fold.

    5. Repeat the Process: Repeat the process K times, selecting a different fold for testing each time.

    6. Calculate Average Performance: Calculate the average of all K evaluation scores to obtain the final
       performance.

3. Diagram of 5-Fold Cross-Validation

Consider a dataset divided into five folds.


Each fold is used exactly once for testing and K-1 times for training.

4. Example

Suppose a dataset contains 1000 records and we choose K = 5.

       Total records = 1000

       Number of folds = 5

       Records in each fold = 1000 / 5 = 200

Iteration

Training Records

Testing Records


Average Accuracy:

= (85 + 90 + 88 + 87 + 90) / 5

= 440 / 5

= 88%

Therefore, the estimated model accuracy is 88%.

5. Effect of Choosing a Very Small or Very Large K

The value of K affects the training time, computational cost and reliability of model evaluation.

A. Very Small K (e.g., K = 2)

       Each model is trained using a smaller portion of the dataset.

       Training time is generally lower because fewer models are trained.

       The performance estimate may have high bias because each model uses less training data.

       Results may depend heavily on how the dataset is divided.

B. Very Large K (e.g., K = 50 or K = N)

       Each model is trained using almost the entire dataset.

       Training time and computational cost increase because many models must be trained.

       Each testing fold contains very few records.

       Evaluation results can have high variability, especially when the dataset is small.

       When K equals the total number of records (N), it is called Leave-One-Out Cross-Validation (LOOCV).

6. Advantages of K-Fold Cross-Validation

    1. Better Evaluation: Provides a more reliable estimate than a single train-test split in many situations.


    2. Efficient Data Usage: Every record is used for both training and testing.

    3. Model Comparison: Helps compare different machine learning algorithms.

    4. Overfitting Detection: Helps identify models that do not generalize well to unseen data.

    5. Hyperparameter Tuning: Helps select suitable model parameters.

7. Conclusion

K-Fold Cross-Validation is an effective technique for evaluating machine learning models. It uses different training and
testing combinations and calculates average performance. A commonly used value is K = 5 or K = 10, depending on
dataset size and computational resources.


Q. Explain the methods used for evaluating classification models. (5 Marks)

1. Introduction

Classification model evaluation is the process of measuring how effectively a machine learning model predicts class
labels.

Different evaluation methods are used to check the accuracy, reliability and generalization ability of a classification
model.

2. Methods Used for Evaluating Classification Models

1. Confusion Matrix

A confusion matrix is a table used to compare actual class labels with predicted class labels.

It consists of four values:

       True Positive (TP): Correctly predicted positive cases.

       True Negative (TN): Correctly predicted negative cases.

       False Positive (FP): Negative cases incorrectly predicted as positive.

       False Negative (FN): Positive cases incorrectly predicted as negative.

2. Accuracy

Accuracy measures the percentage of total predictions that are correct.

Formula:

Accuracy = (TP + TN) / (TP + TN + FP + FN)

3. Precision

Precision measures how many predicted positive cases are actually positive.

Formula:

Precision = TP / (TP + FP)

4. Recall (Sensitivity)

Recall measures how many actual positive cases are correctly identified.

Formula:

Recall = TP / (TP + FN)


5. F1-Score

F1-Score is the harmonic mean of Precision and Recall.

Formula:

F1-Score = 2 × (Precision × Recall) / (Precision + Recall)

6. Specificity

Specificity measures how many actual negative cases are correctly identified.

Formula:

Specificity = TN / (TN + FP)

7. K-Fold Cross-Validation

In this method, the dataset is divided into K folds. The model is trained K times, using a different fold for testing in
each iteration. The average performance is calculated to estimate model performance on unseen data.

3. Importance of Classification Model Evaluation

    1. Helps measure the performance of a classification algorithm.

    2. Identifies incorrect predictions and classification errors.

    3. Helps compare different machine learning models.

    4. Helps detect poor performance on imbalanced datasets.

    5. Helps select the most suitable model for a particular application.

4. Conclusion

Classification evaluation methods help determine how accurately and reliably a model classifies data. Metrics such as
Accuracy, Precision, Recall, F1-Score and Specificity, along with the Confusion Matrix and K-Fold Cross-Validation, are
useful for evaluating classification models.


Q. What is Clustering? Explain the K-Means Clustering algorithm with a suitable example and applications. (5–8
Marks)

1. What is Clustering?

Clustering is an unsupervised machine learning technique used to group similar data points into clusters based on
their characteristics or similarities.

       Data points within the same cluster are more similar to each other.

       Data points belonging to different clusters are less similar.

       It does not require predefined class labels.

Example: Grouping customers based on their purchasing behaviour, income and spending habits.

2. K-Means Clustering Algorithm

K-Means is an unsupervised clustering algorithm that divides a dataset into K clusters. Each cluster is represented by
its centroid (mean position of all data points in that cluster).


The main objective is to minimize the distance between data points and their assigned cluster centroids.

3. Working of K-Means Algorithm

Step 1: Select K

Choose the number of clusters (K) to be formed.

Step 2: Initialize Centroids

Randomly select K data points as initial cluster centroids.

Step 3: Assign Data Points

Calculate the distance between each data point and all centroids. Assign each point to the nearest centroid.

Euclidean Distance:

Distance = √[(x2 - x1)² + (y2 - y1)²]

Step 4: Update Centroids

Calculate the mean of all data points belonging to each cluster. Update the centroid position.

Centroid = Sum of data points in cluster / Number of data points in cluster

Step 5: Repeat

Repeat the assignment and centroid update steps until the centroids stop changing significantly or the algorithm
reaches the maximum number of iterations.

4. Flowchart of K-Means Algorithm


5. Suitable Example

Consider six data points representing customers based on their annual income and spending score.

Customer Income (X) Spending Score (Y)

A            2          3

B            3          4

C            4          3

D            8          7

E            9          8

F            10         7

Let K = 2.

Step 1: Initialize Centroids

Select initial centroids:

       C1 = (2, 3)

       C2 = (8, 7)

Step 2: Assign Data Points

Using Euclidean distance, assign each customer to the nearest centroid.

       Cluster 1: A, B, C

       Cluster 2: D, E, F

Step 3: Calculate New Centroids

For Cluster 1:

New C1 = ((2 + 3 + 4) / 3, (3 + 4 + 3) / 3)

New C1 = (3, 3.33)

For Cluster 2:

New C2 = ((8 + 9 + 10) / 3, (7 + 8 + 7) / 3)

New C2 = (9, 7.33)

Step 4: Repeat

Reassign the data points using the new centroids and repeat the process until the clusters become stable.

Final Result:

       Cluster 1: Customers A, B and C (lower income and spending scores).

       Cluster 2: Customers D, E and F (higher income and spending scores).

Thus, K-Means successfully divides customers into two groups based on their characteristics.

6. Applications of K-Means Clustering

    1. Customer Segmentation: Groups customers based on purchasing behaviour.

    2. Market Analysis: Identifies different market segments.


    3. Image Segmentation: Groups similar pixels in an image.

    4. Document Clustering: Groups similar documents or news articles.

    5. Healthcare: Groups patients based on medical characteristics.

    6. Anomaly Detection: Helps identify data points that are far from cluster centres, which may require further
       investigation.

7. Advantages and Limitations

Advantages:

       Simple and easy to implement.

       Computationally efficient for large datasets.

       Easy to understand and interpret.

Limitations:

       The value of K must be selected in advance.

       Sensitive to initial centroid selection.

       Affected by outliers.

       Works best with compact, approximately spherical clusters.

8. Conclusion

K-Means is a popular unsupervised learning algorithm that groups similar data points into K clusters using distance
calculations and centroid updates. It is widely used in customer segmentation, market analysis and image processing.


Q. Solve a numerical problem using the K-Means Clustering algorithm for the given dataset. (6 Marks)

1. Introduction

K-Means is an unsupervised machine learning algorithm used to divide a dataset into K clusters based on similarity.

It assigns each data point to the nearest centroid and repeatedly updates the centroids until the clusters become
stable.

2. Numerical Example

Consider the following dataset containing six data points:

Data Point X Y

A          2 3

B          3 4

C          4 3

D          8 7

E          9 8

F          10 7


Given:

        Number of clusters: K = 2

        Initial centroid C1 = A (2, 3)

        Initial centroid C2 = D (8, 7)

        Distance metric: Euclidean Distance

Euclidean Distance Formula:

Distance = √[(x2 - x1)² + (y2 - y1)²]

3. Step 1: Calculate Distance from Initial Centroids

Calculate the distance of every data point from C1 and C2.

Point    Distance from C1 (2,3) Distance from C2 (8,7) Assigned Cluster

A (2,3) 0                           7.21               C1

B (3,4) 1.41                        5.83               C1

C (4,3) 2.00                        5.66               C1

D (8,7) 7.21                        0                  C2

E (9,8) 8.60                        1.41               C2

F (10,7) 8.54                       2.00               C2

Therefore:

        Cluster 1 =

        Cluster 2 =

4. Step 2: Calculate New Centroids

Centroid = (Sum of coordinates) / Number of data points

For Cluster 1:

C1 = ((2 + 3 + 4) / 3, (3 + 4 + 3) / 3)

C1 = (9/3, 10/3)

C1 = (3, 3.33)

For Cluster 2:

C2 = ((8 + 9 + 10) / 3, (7 + 8 + 7) / 3)

C2 = (27/3, 22/3)

C2 = (9, 7.33)

5. Step 3: Recalculate Distances

Using the new centroids:

C1 = (3, 3.33)

C2 = (9, 7.33)


Point     Distance from C1 Distance from C2 Assigned Cluster

A (2,3) 1.05               8.02               C1

B (3,4) 0.67               6.61               C1

C (4,3) 1.37               6.67               C1

D (8,7) 6.13               1.05               C2

E (9,8) 7.54               0.67               C2

F (10,7) 7.13              1.05               C2

The cluster assignments remain unchanged.

6. Final Result

Converged

Cluster    Data Points Final Centroid

Cluster 1 A, B, C      (3, 3.33)

Cluster 2 D, E, F      (9, 7.33)

Since the cluster assignments do not change after recalculating the centroids, the algorithm has converged.

7. Conclusion

The K-Means algorithm successfully divides the six data points into two clusters based on their distances from the
centroids. The final clusters are and .


Q. Explain the K-Medoids Clustering algorithm. Why is K-Medoids used, and how is it different from K-Means? (5–6
Marks)

1. Introduction

K-Medoids is an unsupervised machine learning clustering algorithm used to divide a dataset into K clusters based
on similarity.

It is similar to K-Means, but instead of using the mean of data points as the cluster centre, it uses an actual data point
called a Medoid.

A medoid is the most centrally located data point in a cluster, having the minimum total distance from all other
points in that cluster.

2. Working of K-Medoids Algorithm

The working steps are:

    1. Select K: Choose the number of clusters (K).

    2. Initialize Medoids: Randomly select K data points as initial medoids.

    3. Assign Data Points: Calculate the distance between each data point and the selected medoids. Assign each
       point to its nearest medoid.

    4. Select New Medoids: Try replacing the current medoid with another data point from the same cluster.


    5. Calculate Total Cost: Calculate the total distance between all data points and their respective medoids.

    6. Update Medoids: If replacing a medoid reduces the total cost, accept the new medoid.

    7. Repeat: Continue until no replacement reduces the total cost or the algorithm reaches its stopping condition.

3. Flowchart of K-Medoids Algorithm


4. Why is K-Medoids Used?

    1. Handles Outliers: It is less sensitive to outliers because the cluster centre is an actual data point.

    2. Robust Clustering: It provides more stable cluster centres when extreme values are present.

    3. Actual Data Representation: The medoid represents a real observation from the dataset.

    4. Flexible Distance Measures: It can work with different distance or dissimilarity measures.

    5. Useful for Noisy Data: It is suitable for datasets containing noise and extreme observations.

5. Difference Between K-Means and K-Medoids

K-Means                                    K-Medoids

Uses the mean as the cluster centre.       Uses an actual data point as the cluster centre.

Cluster centre is called a centroid.       Cluster centre is called a medoid.

More sensitive to outliers.                More resistant to outliers.


Usually uses squared Euclidean distance. Can use different distance measures.

Generally faster and computationally
                                             Generally more computationally expensive.
efficient.

                                             Can work with numerical or other data when a suitable dissimilarity
Suitable for numerical datasets.
                                             measure is available.

6. Conclusion

K-Medoids is a clustering algorithm that uses actual data points as cluster centres. It is more robust to outliers than K-
Means and is useful when representative real observations are required.


Q. Explain how to select the optimal number of clusters in K-Medoids and other clustering algorithms. (6 Marks)

1. Introduction

In clustering algorithms, selecting the optimal number of clusters (K) is important because it determines how data
points are grouped.

       If K is too small, different groups may be combined into one cluster.

       If K is too large, similar data points may be divided into unnecessary clusters.

The optimal K provides meaningful and well-separated clusters.

2. Methods for Selecting the Optimal Number of Clusters

1. Elbow Method

The Elbow Method is commonly used with K-Means and can also be applied to K-Medoids.

Working:

    1. Select different values of K, such as 1, 2, 3, 4 and 5.

    2. Run the clustering algorithm for each value of K.

    3. Calculate the clustering cost for each K.

            o     For K-Means, use Within-Cluster Sum of Squares (WCSS).

            o     For K-Medoids, use the total distance between data points and their assigned medoids.

    4. Plot K against the clustering cost.

    5. Select the K value at the elbow point, where the reduction in cost starts becoming slower.

Diagram: Elbow Method


2. Silhouette Score Method

The Silhouette Score measures how well a data point fits within its assigned cluster compared with other clusters.

It considers:

        Cohesion: How close a data point is to other points in its own cluster.

        Separation: How far a data point is from points in other clusters.

Silhouette Score formula:

S = (b - a) / max(a, b)

Where:

        a = Average distance from other points in the same cluster.

        b = Average distance from points in the nearest different cluster.

The score ranges from -1 to +1.

        Close to +1: Well-clustered data point.

        Around 0: Data point lies near a cluster boundary.

        Negative value: Data point may be assigned to the wrong cluster.

The K value with the highest average Silhouette Score is generally preferred.

3. Gap Statistic Method

The Gap Statistic compares the clustering performance of the actual dataset with that of randomly generated
reference datasets.

Working:

    1. Apply clustering for different values of K.

    2. Calculate the within-cluster dispersion.

    3. Generate reference random datasets.

    4. Compare the actual clustering dispersion with the reference dispersion.

    5. Select the K value where the gap is large, following the method's selection rule.

4. Domain Knowledge


The optimal number of clusters can also be selected using knowledge of the problem.

Example: In customer segmentation, a business may require three groups: low-value, medium-value and high-value
customers.

3. Importance of Selecting Optimal K

    1. Improves the quality of clustering.

    2. Avoids unnecessary clusters.

    3. Helps identify meaningful patterns.

    4. Improves interpretation of results.

    5. Supports better decision-making.

4. Conclusion

The optimal number of clusters can be selected using methods such as the Elbow Method, Silhouette Score, Gap
Statistic and Domain Knowledge. These methods help produce meaningful and well-separated clusters in K-Medoids
and other clustering algorithms.


Q. Explain Hierarchical Clustering with a suitable example. Describe Agglomerative Clustering and Dendrogram. (6–
9 Marks)

1. Introduction

Hierarchical Clustering is an unsupervised machine learning algorithm used to group similar data points into a
hierarchy of clusters.

It creates a tree-like structure of clusters by either combining smaller clusters or dividing larger clusters.

Unlike K-Means, Hierarchical Clustering does not require specifying the number of clusters initially.

There are two main types:

    1. Agglomerative Clustering: Bottom-up approach; starts with individual data points and combines them into
       larger clusters.

    2. Divisive Clustering: Top-down approach; starts with one large cluster and repeatedly divides it into smaller
       clusters.

2. Agglomerative Clustering

Agglomerative Clustering is a bottom-up hierarchical clustering technique in which each data point initially forms a
separate cluster.

The algorithm repeatedly merges the two closest clusters until only one cluster remains or the required number of
clusters is obtained.

Working Steps:

    1. Initialize Clusters: Consider each data point as an individual cluster.

    2. Calculate Distance: Calculate the distance between all clusters using a suitable distance measure.

    3. Find Closest Clusters: Identify the two clusters having the minimum distance.


      4. Merge Clusters: Combine the closest clusters into one cluster.

      5. Update Distances: Recalculate the distances between the newly formed cluster and other clusters.

      6. Repeat: Continue merging until all points form one cluster or the desired number of clusters is obtained.

3. Suitable Example

Consider five data points:

A = 1, B = 2, C = 8, D = 9, E = 10

Assume Euclidean distance and single-linkage clustering (minimum distance between two clusters).

Step 1: Initial Clusters

,,,,

Step 2: Calculate Distances

         Distance(A, B) = |1 - 2| = 1

         Distance(C, D) = |8 - 9| = 1

         Distance(D, E) = |9 - 10| = 1

Step 3: Merge Closest Clusters

Merge A and B:

,,,

Step 4: Merge Next Closest Clusters

Merge C and D:

,,

Step 5: Merge C, D and E

Distance between cluster and E is 1.

New clusters:

,

Step 6: Final Merge

Distance between and is 6.

Finally, all points form one cluster:

Thus, the algorithm builds a hierarchy of clusters.

4. Dendrogram

A Dendrogram is a tree-like diagram used to represent the merging or splitting process in Hierarchical Clustering.

It shows:

         How individual data points are grouped into clusters.

         The order in which clusters are merged.

         The distance at which two clusters are combined.

         The number of clusters at different levels.


Simple Dendrogram:


Note: The horizontal joining levels represent the distances at which clusters are merged.

How to select clusters using a Dendrogram?

    1. Draw a horizontal line across the dendrogram at the selected distance.

    2. Count the number of vertical branches intersected by the line.

    3. This gives the number of clusters.

For example, cutting the above dendrogram between distances 1 and 6 produces two clusters:

       Cluster 1 =

       Cluster 2 =

5. Linkage Methods Used in Hierarchical Clustering

Linkage methods determine the distance between two clusters.

Linkage Method Description

Single Linkage        Minimum distance between points of two clusters.

Complete Linkage Maximum distance between points of two clusters.

Average Linkage       Average distance between all pairs of points in two clusters.

Ward's Linkage        Merges clusters that produce the smallest increase in within-cluster variance.

6. Advantages of Hierarchical Clustering

    1. Does not require specifying the number of clusters initially.

    2. Dendrogram provides a clear visual representation of clusters.

    3. Helps discover hierarchical relationships in data.

    4. Supports different distance and linkage methods.

    5. Useful for exploring small and medium-sized datasets.

7. Limitations

    1. Computationally expensive for large datasets.

    2. Sensitive to noise and outliers.

    3. Once clusters are merged or split, the decision is generally not reversed.


    4. Results depend on the selected distance and linkage method.

8. Applications

    1. Customer segmentation in marketing.

    2. Grouping similar documents and news articles.

    3. Biological classification and gene analysis.

    4. Grouping patients based on medical characteristics.

    5. Image segmentation and pattern recognition.

9. Conclusion

Hierarchical Clustering is an unsupervised learning technique that creates a hierarchy of clusters. Agglomerative
Clustering follows a bottom-up approach, while a Dendrogram visually represents the cluster formation process and
helps determine the appropriate number of clusters.


Q. Differentiate between Hierarchical Clustering and K-Means Clustering. (6 Marks)

1. Introduction

Hierarchical Clustering and K-Means are two popular unsupervised machine learning algorithms used to group
similar data points into clusters.

However, they differ in their working methods, cluster formation and computational requirements.

2. Difference Between Hierarchical Clustering and K-Means

Hierarchical Clustering                                         K-Means Clustering

1. It creates a hierarchy of clusters.                          It divides data into K separate clusters.

2. It follows a bottom-up (Agglomerative) or top-down
                                                                It follows an iterative centroid-based approach.
(Divisive) approach.

3. The number of clusters need not be specified initially.      The number of clusters (K) must be specified initially.

4. It uses a Dendrogram to represent cluster formation.         It uses centroids to represent clusters.

5. It can use different distance and linkage methods.           It commonly uses Euclidean distance.

6. Generally, it is computationally expensive for large         Generally, it is faster and more efficient for large
datasets.                                                       datasets.

                                                                Data points can be reassigned to different clusters
7. Merging or splitting decisions are generally irreversible.
                                                                during iterations.

8. Suitable for small and medium-sized datasets.                Suitable for large datasets.

9. Does not require initial centroid selection.                 Requires initial centroid selection.

10. Examples include Agglomerative and Divisive Clustering. Example: K-Means algorithm.

3. Diagrammatic Representation

Hierarchical Clustering:


It creates a tree-like hierarchy by merging smaller clusters.

K-Means Clustering:


It groups data points around K selected centroids.

4. Conclusion

Hierarchical Clustering creates a hierarchy of clusters and represents them using a Dendrogram, whereas K-Means
divides data into a predefined number of clusters using centroids. The choice depends on dataset size, computational
requirements and the clustering problem.


Q. What is Density-Based Clustering? Explain its working, importance and different algorithms. (6 Marks)

1. Introduction

Density-Based Clustering is an unsupervised machine learning technique that groups data points based on the
density of data points in a particular region.

It forms clusters in areas where data points are closely packed and separates them from regions having low data
density.

Unlike K-Means, it does not require specifying the number of clusters in advance and can identify clusters of irregular
shapes.

2. Working of Density-Based Clustering

The working process is as follows:

    1. Identify Neighbourhood: For each data point, identify neighbouring points within a specified radius called
       Epsilon (ε).

    2. Set Parameters: Define two important parameters:

            o     Epsilon (ε): Maximum distance within which neighbouring points are considered.

            o     MinPts: Minimum number of points required within the Epsilon neighbourhood to form a dense
                  region.

    3. Identify Core Points: A point having at least MinPts points in its Epsilon neighbourhood is called a Core Point.


    4. Identify Border Points: A point that has fewer than MinPts neighbours but lies within the neighbourhood of
       a Core Point is called a Border Point.

    5. Identify Noise Points: Points that are neither Core Points nor Border Points are considered Noise or Outliers.

    6. Form Clusters: Connect density-reachable points and expand clusters until all density-connected points are
       assigned.

3. Important Terms and Diagram

         Core Point: Has at least MinPts points within its Epsilon radius.

         Border Point: Has fewer than MinPts neighbours but is within the Epsilon radius of a Core Point.

         Noise Point: Does not belong to any cluster.

Simple Density-Based Clustering Diagram:


Legend:

         ● = Core Point

         ○ = Border Point / Neighbouring Point

         × = Noise Point

4. Different Density-Based Clustering Algorithms

1. DBSCAN (Density-Based Spatial Clustering of Applications with Noise)

         Uses Epsilon and MinPts parameters.

         Identifies Core, Border and Noise points.

         Detects clusters of arbitrary shapes.

         Handles outliers effectively.

2. OPTICS (Ordering Points To Identify the Clustering Structure)

         Similar to DBSCAN.

         Produces an ordering of data points based on density reachability.

         Helps identify clusters with different density levels.

         Useful when clusters have varying densities.

3. HDBSCAN (Hierarchical Density-Based Spatial Clustering of Applications with Noise)

         Extension of DBSCAN.

         Builds a hierarchy of density-based clusters.


       Can identify clusters with varying densities.

       Helps identify noise and outliers.

5. Importance and Applications

Importance:

    1. Identifies clusters of arbitrary shapes.

    2. Does not require the number of clusters in advance.

    3. Detects noise and outliers.

    4. Works well for spatial datasets.

    5. Groups data based on density rather than distance from a centroid.

Applications:

    1. Geographic data analysis and location-based grouping.

    2. Customer behaviour analysis.

    3. Anomaly and fraud detection.

    4. Image segmentation.

    5. Identifying unusual patterns in scientific datasets.

6. Conclusion

Density-Based Clustering is an unsupervised learning technique that forms clusters based on the density of data
points. Algorithms such as DBSCAN, OPTICS and HDBSCAN are useful for identifying irregularly shaped clusters and
detecting outliers.


Q. Explain the DBSCAN algorithm and define its important terms with a suitable example. (6 Marks)

1. Introduction

DBSCAN (Density-Based Spatial Clustering of Applications with Noise) is an unsupervised machine learning clustering
algorithm.

It groups data points based on their density. It forms clusters in regions where points are closely packed and
identifies points in low-density regions as noise or outliers.

DBSCAN can identify clusters of arbitrary shapes without requiring the number of clusters in advance.

2. Important Terms Used in DBSCAN

DBSCAN uses two important parameters:

1. Epsilon (ε):

       It is the maximum radius around a data point used to identify its neighbouring points.

       Points within this radius are considered neighbours.

2. MinPts (Minimum Points):

       It is the minimum number of points required within the Epsilon neighbourhood to form a dense region.


        It helps identify core points.

Other important terms:

3. Core Point:

A point having at least MinPts points (including itself) within its Epsilon neighbourhood.

4. Border Point:

A point having fewer than MinPts points in its own neighbourhood but lying within the Epsilon neighbourhood of a
Core Point.

5. Noise Point:

A point that is neither a Core Point nor a Border Point. It is treated as an outlier.

3. Working of DBSCAN Algorithm

    1. Select Parameters: Choose Epsilon (ε) and MinPts.

    2. Select a Data Point: Choose an unvisited point from the dataset.

    3. Find Neighbours: Identify all points within its Epsilon radius.

    4. Check Density: If the number of neighbours is less than MinPts, mark the point as a possible noise point.

    5. Form Cluster: If the point has at least MinPts neighbours, mark it as a Core Point and create a new cluster.

    6. Expand Cluster: Add its neighbouring points and continue checking their neighbourhoods. Include density-
       reachable points in the cluster.

    7. Repeat: Continue until all points have been visited.

    8. Identify Noise: Points that do not belong to any cluster are classified as noise.

4. Suitable Example

Consider a dataset containing customer locations.

Given:

        Epsilon (ε) = 2 units

        MinPts = 4

Suppose the neighbourhood of point A contains four points, including A itself.

Therefore:

        A is a Core Point because its neighbourhood contains at least four points.

        Point B has only two points in its own neighbourhood but lies within the Epsilon radius of A. Therefore, B is a
         Border Point.

        Point X is far away from all dense regions and does not belong to any cluster. Therefore, X is a Noise Point.


Diagram:


The Core Point and its density-connected neighbours form a cluster, while isolated points are treated as noise.

5. Advantages of DBSCAN

    1. Does not require the number of clusters in advance.

    2. Identifies clusters of arbitrary shapes.

    3. Detects noise and outliers effectively.

    4. Works well with spatial datasets.

    5. Does not depend on centroid calculation.

6. Limitations of DBSCAN

    1. Selecting suitable Epsilon and MinPts values can be difficult.

    2. It may not perform well when clusters have significantly different densities.

    3. Its performance can be affected by high-dimensional data.

7. Applications

    1. Geographic location and spatial data analysis.

    2. Customer segmentation.

    3. Fraud and anomaly detection.

    4. Image processing.

    5. Identifying unusual patterns in scientific datasets.

8. Conclusion

DBSCAN is a density-based clustering algorithm that identifies clusters using Epsilon and MinPts. It classifies data
points as Core, Border or Noise points and is useful for detecting irregularly shaped clusters and outliers.


Q. Explain Spectral Clustering and differentiate it from K-Means Clustering. (6 Marks)


1. Introduction

Spectral Clustering is an unsupervised machine learning clustering technique that uses the eigenvalues and
eigenvectors of a similarity matrix to group similar data points.

It converts the original dataset into a lower-dimensional representation using graph theory and then applies a
clustering algorithm such as K-Means.

It is useful for identifying complex and non-spherical clusters that traditional K-Means may not identify effectively.

2. Working of Spectral Clustering

The algorithm works in the following steps:

Step 1: Construct Similarity Matrix

        Calculate the similarity between every pair of data points.

        Similar points have higher similarity values.

        Dissimilar points have lower similarity values.

Step 2: Construct Degree Matrix

        Create a diagonal matrix containing the sum of similarities connected to each data point.

        It represents the connectivity of each point.

Step 3: Calculate Graph Laplacian

The Graph Laplacian is calculated using:

L=D-W

Where:

        L = Graph Laplacian matrix

        D = Degree matrix

        W = Similarity matrix

Step 4: Eigenvalue and Eigenvector Calculation

        Calculate the eigenvalues and eigenvectors of the Graph Laplacian.

        Select the required eigenvectors to represent the data in a lower-dimensional space.

Step 5: Apply K-Means

Apply K-Means to the selected eigenvector representation to obtain the final clusters.

3. Flowchart of Spectral Clustering


4. Example

Consider a dataset containing two circular groups of data points.

       K-Means may struggle to separate the two groups because it generally works best with compact,
        approximately spherical clusters.

       Spectral Clustering uses the similarity relationships between data points to identify the two groups.

       It can successfully separate clusters having complex or non-linear shapes when the similarity graph is
        constructed appropriately.


5. Difference Between Spectral Clustering and K-Means Clustering

Spectral Clustering                                    K-Means Clustering


1. Uses graph theory and eigenvalues/eigenvectors.      Uses centroid-based clustering.

2. Uses a similarity matrix to represent relationships. Uses distances between data points and centroids.

3. Can identify complex and non-linear cluster shapes. Works best with compact, approximately spherical clusters.

4. Performs eigenvalue and eigenvector calculations. Performs centroid assignment and updating.

5. Generally computationally expensive.                 Generally faster and computationally efficient.

6. Suitable for complex data structures.                Suitable for relatively simple and well-separated clusters.

7. Requires a similarity graph or matrix.               Requires the number of clusters and initial centroids.

6. Advantages of Spectral Clustering

    1. Identifies non-linear and complex cluster structures.

    2. Uses relationships between data points.

    3. Works well when clusters are not spherical.

    4. Can provide effective clustering for graph-based datasets.

7. Limitations of Spectral Clustering

    1. Computationally expensive for large datasets.

    2. Requires construction of a suitable similarity matrix.

    3. Performance depends on the similarity measure and its parameters.

    4. Selecting the number of clusters is still necessary.

8. Conclusion

Spectral Clustering is an unsupervised learning algorithm that uses graph theory, similarity matrices and eigenvectors
to identify clusters. Unlike K-Means, it can identify complex and non-linear cluster structures.


Q. Explain Graph-Based Clustering with a suitable example. (6 Marks)

1. Introduction

Graph-Based Clustering is an unsupervised machine learning technique that groups data points based on their
relationships and connections.

In this method, data points are represented as vertices (nodes) of a graph, and the relationships or similarities
between them are represented as edges.

Data points having strong connections are grouped into the same cluster, while weakly connected groups are
separated into different clusters.

2. Important Components of Graph-Based Clustering

    1. Vertices (Nodes): Represent individual data points.

    2. Edges: Represent connections or relationships between data points.

    3. Edge Weight: Represents the strength or similarity between two connected data points.

    4. Similarity Matrix: Stores similarity values between pairs of data points.


    5. Clusters: Groups of strongly connected nodes.

3. Working of Graph-Based Clustering

The algorithm works in the following steps:

    1. Create Graph: Represent each data point as a node.

    2. Calculate Similarity: Calculate similarity or distance between data points.

    3. Create Edges: Connect similar data points using edges.

    4. Assign Edge Weights: Give weights to edges based on similarity.

    5. Identify Clusters: Apply a graph partitioning or community detection method to identify groups of strongly
       connected nodes.

    6. Generate Final Clusters: Separate the graph into different clusters based on connection strength.

4. Suitable Example

Consider a social network containing six users: A, B, C, D, E and F.

Users who frequently interact with each other are connected through edges.

Suppose the connections are:

       Group 1: A, B and C

       Group 2: D, E and F

Graph Representation:


Explanation:

       A, B and C have strong connections with each other.

       D, E and F also have strong connections with each other.

       Connections between the two groups are weak or absent.

       Therefore, the algorithm forms two separate clusters.

Thus, Graph-Based Clustering identifies groups based on relationships between data points.

5. Different Graph-Based Clustering Methods

1. Spectral Clustering

       Uses a similarity matrix and graph Laplacian.

       Calculates eigenvalues and eigenvectors.

       Groups data points based on graph structure.

2. Community Detection

       Identifies groups of strongly connected nodes.


       Commonly used in social networks.

       Example: Identifying communities of users with common interests.

3. Minimum Spanning Tree (MST)-Based Clustering

       Constructs a minimum spanning tree connecting all data points.

       Removes selected long edges to separate the graph into clusters.

6. Advantages of Graph-Based Clustering

    1. Identifies complex and non-spherical clusters.

    2. Considers relationships between data points.

    3. Useful for network and social media analysis.

    4. Can identify groups with complex connectivity patterns.

    5. Supports different graph partitioning techniques.

7. Applications

    1. Social Networks: Identifying communities of users.

    2. Recommendation Systems: Grouping users with similar interests.

    3. Biological Networks: Identifying related genes and proteins.

    4. Image Segmentation: Grouping similar image regions.

    5. Web Analysis: Grouping related web pages.

8. Conclusion

Graph-Based Clustering is an unsupervised learning technique that groups data points based on their connections
and similarity. It is useful for identifying complex relationships and communities in social networks, biological
networks and recommendation systems.


Q. What is Outlier Analysis in Clustering? Explain its importance and different techniques used for handling
outliers. (5–6 Marks)

1. Introduction

Outlier Analysis is the process of identifying data points that are significantly different from the majority of data
points in a dataset.

In clustering, outliers are data points that do not belong to any well-defined cluster or are located far away from the
cluster centres.

Such data points are also called anomalies or noise points.

Example: In a customer transaction dataset, a customer making an unusually large transaction compared to others
may be considered an outlier.

2. Importance of Outlier Analysis in Clustering

    1. Improves Clustering Accuracy: Prevents unusual data points from affecting cluster formation.


    2. Detects Anomalies: Helps identify unusual patterns and abnormal behaviour.

    3. Improves Data Quality: Removes unwanted noise from datasets.

    4. Better Decision-Making: Helps organizations identify fraud and suspicious activities.

    5. Improves Model Performance: Reduces the negative influence of extreme values on clustering algorithms.

3. Different Techniques Used for Outlier Detection and Handling

1. Distance-Based Method

       Calculates the distance between data points.

       Points located far away from most other points are considered outliers.

       Example: Identifying customers whose spending behaviour is significantly different from others.

2. Density-Based Method (LOF)

LOF stands for Local Outlier Factor.

       It compares the local density of a data point with the density of its neighbouring points.

       Points having significantly lower local density than their neighbours are considered outliers.

       Useful for detecting outliers in datasets with different density regions.

3. Isolation Forest

       Uses multiple random decision trees to isolate data points.

       Outliers are generally isolated using fewer splits than normal data points.

       Useful for detecting anomalies in large datasets.

4. Statistical Method (Z-Score)

       Measures how far a data point is from the mean in terms of standard deviations.

       A very high positive or negative Z-score may indicate an outlier.

Formula:

Z = (X - Mean) / Standard Deviation

Generally, values with |Z| greater than 3 are considered potential outliers when the data is approximately normally
distributed.

5. Clustering-Based Method

       Uses clustering algorithms such as K-Means or DBSCAN.

       Points far from cluster centres or classified as noise may be treated as outliers.

       DBSCAN identifies isolated points as noise.

4. Techniques for Handling Outliers

After detecting outliers, different methods can be used:

    1. Removal: Remove outliers if they are caused by data-entry errors or irrelevant observations.

    2. Capping: Replace extreme values with specified upper or lower limits.

    3. Transformation: Apply logarithmic or other transformations to reduce the effect of extreme values.


    4. Replacement: Replace outliers using suitable statistical values such as median.

    5. Separate Analysis: Keep genuine unusual observations and analyse them separately.

5. Applications of Outlier Analysis

    1. Credit card fraud detection.

    2. Network intrusion detection.

    3. Medical abnormality detection.

    4. Financial transaction monitoring.

    5. Customer behaviour analysis.

6. Conclusion

Outlier Analysis is an important part of clustering that identifies unusual data points. Techniques such as LOF,
Isolation Forest, Z-Score and DBSCAN help detect outliers, while removal, capping and transformation help handle
them effectively.


Q. Explain Local Outlier Factor (LOF) with its advantages and disadvantages. (5–6 Marks)

1. Introduction

Local Outlier Factor (LOF) is an unsupervised anomaly detection algorithm used to identify outliers in a dataset.

It identifies outliers by comparing the local density of a data point with the local densities of its neighbouring points.

If a data point has significantly lower density than its neighbours, it is considered a potential outlier.

2. Working of Local Outlier Factor (LOF)

LOF works using the following steps:

    1. Select K: Choose the number of nearest neighbours (K) for each data point.

    2. Find Neighbours: Calculate the distance between data points and identify their K nearest neighbours.

    3. Calculate K-Distance: Determine the distance to the Kth nearest neighbour.

    4. Calculate Reachability Distance: Calculate the reachability distance between a point and its neighbour.

    5. Calculate Local Reachability Density (LRD): Estimate the local density of each point based on its neighbours.

    6. Calculate LOF Score: Compare the local density of a point with the average density of its neighbours.

    7. Identify Outliers: Points having significantly higher LOF scores are considered outliers.

3. LOF Score and Interpretation

LOF Score = Average Local Reachability Density of Neighbours / Local Reachability Density of the Point

Interpretation:

LOF Score                    Meaning

Approximately 1              Point has similar density to its neighbours; generally normal.

Greater than 1               Point has lower density than its neighbours; may be an outlier.


Significantly greater than 1 Strong indication of an outlier.

Less than 1                  Point has higher density than its neighbours.

4. Suitable Example

Consider a dataset containing customer transaction amounts.

Most customers make transactions between ₹500 and ₹5,000.

However, one customer makes a transaction of ₹1,00,000.

LOF compares the local density of this customer's transaction with neighbouring transactions.

       Normal transactions have similar local densities.

       The unusual transaction has a significantly lower local density than its neighbours.

       Therefore, it receives a higher LOF score and may be identified as an outlier.

Simple Diagram:


5. Advantages of LOF

    1. Detects Local Outliers: Identifies outliers based on local density rather than global distance.

    2. Handles Different Densities: Can detect outliers in datasets containing clusters with different density levels.

    3. Unsupervised Technique: Does not require labelled training data.

    4. Flexible: Can be used with different distance measures.

    5. Effective Anomaly Detection: Useful for identifying unusual patterns in complex datasets.

6. Disadvantages of LOF

    1. Parameter Selection: Performance depends on the selection of K nearest neighbours.

    2. Computational Cost: Distance calculations can be expensive for large datasets.

    3. High-Dimensional Data: Performance may decrease when the number of dimensions is very high.

    4. Sensitive to Data Quality: Noise and irrelevant features can affect the results.

    5. Score Interpretation: LOF scores do not provide a universal threshold for identifying outliers.

7. Applications

    1. Credit card fraud detection.


    2. Network intrusion detection.

    3. Medical abnormality detection.

    4. Financial transaction monitoring.

    5. Customer behaviour analysis.

8. Conclusion

Local Outlier Factor is a density-based anomaly detection algorithm that identifies unusual data points by comparing
their local density with neighbouring points. It is particularly useful for detecting local outliers in datasets containing
clusters of different densities.


Q. What is the Isolation Factor Model? Explain its working with a suitable example. (5 Marks)

1. Introduction

The Isolation Forest (iForest) is an unsupervised machine learning algorithm used for detecting outliers and
anomalies in a dataset.

It is based on the principle that anomalies are different from normal data points and can be isolated more easily
using random partitioning.

The algorithm uses multiple random decision trees called Isolation Trees (iTrees) to identify unusual data points.

2. Working of Isolation Forest

The algorithm works in the following steps:

    1. Select Random Samples: Select random subsets of data from the complete dataset.

    2. Construct Isolation Trees: Build multiple isolation trees using the selected samples.

    3. Select Random Features: Randomly select a feature from the dataset.

    4. Select Random Split Value: Choose a random split value between the minimum and maximum values of the
       selected feature.

    5. Partition Data: Divide the data into two groups based on the selected split value.

    6. Repeat Splitting: Continue splitting until each data point is isolated or a maximum tree depth is reached.

    7. Calculate Path Length: Measure the number of splits required to isolate each data point.

    8. Identify Outliers: Points requiring fewer splits are more likely to be anomalies.

3. Flowchart of Isolation Forest


4. Suitable Example

Consider a dataset containing the following monthly transaction amounts:

Customer Transaction Amount

A         ₹1,000

B         ₹1,200

C         ₹1,500

D         ₹1,800

E         ₹1,300

F         ₹1,00,000

Most transactions are between ₹1,000 and ₹1,800, whereas customer F has an unusually large transaction of
₹1,00,000.


Working:

    1. The algorithm randomly selects transaction amounts and features.

    2. It creates multiple isolation trees using random splits.

    3. Normal transactions require more splits to isolate because they are grouped closely together.

    4. Customer F is isolated using fewer splits because its transaction amount is significantly different.

    5. Therefore, customer F receives a higher anomaly score and is identified as a potential outlier.

5. Important Terms

1. Isolation Tree (iTree): A random decision tree used to isolate individual data points.

2. Path Length: Number of splits required to isolate a data point.

3. Anomaly Score: A score indicating how likely a data point is to be an outlier. A higher score indicates a stronger
possibility of an anomaly.

6. Advantages of Isolation Forest

    1. Efficient for detecting anomalies in large datasets.

    2. Does not require labelled training data.

    3. Handles high-dimensional datasets reasonably well.

    4. Requires fewer splits to identify unusual data points.

    5. Can handle multiple features simultaneously.

7. Applications

    1. Credit card fraud detection.

    2. Network intrusion detection.

    3. Unusual financial transaction detection.

    4. Industrial equipment failure detection.

    5. Healthcare anomaly detection.

8. Conclusion

Isolation Forest is an efficient unsupervised anomaly detection algorithm that identifies outliers using random
partitioning. Anomalies generally require fewer splits to isolate than normal data points.
