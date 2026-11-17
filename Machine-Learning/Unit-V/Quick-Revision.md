# Unit V — Quick Revision
## Unsupervised Learning

### 1. Clustering

Clustering is an unsupervised learning technique that groups similar data points into clusters without using predefined class labels.

### 2. K-Means Clustering

- Select K initial centroids.
- Assign each point to its nearest centroid.
- Recalculate each centroid as the mean of points in its cluster.
- Repeat assignment and centroid update until convergence.
- Sensitive to initial centroid selection and outliers.

### 3. K-Medoids

- Uses actual data points as cluster centres (medoids).
- Assigns points to the nearest medoid.
- Tries medoid swaps and keeps changes that reduce total clustering cost.
- More robust to outliers than K-Means.

### 4. Selecting the Number of Clusters

- Elbow Method: plot WCSS against K and identify the point where the reduction starts slowing.
- Silhouette Score: S = (b − a) / max(a, b), where a is average within-cluster distance and b is average distance to the nearest other cluster.
- Gap Statistic: compares observed clustering dispersion with reference random datasets.
- Domain knowledge can help choose a meaningful K.

### 5. Hierarchical Clustering

- Agglomerative: bottom-up; starts with individual points and repeatedly merges clusters.
- Divisive: top-down; starts with one cluster and repeatedly splits it.
- Dendrogram: tree diagram showing cluster merges/splits at different distances.
- Linkage methods include Single, Complete, Average and Ward's Linkage.

### 6. Density-Based Clustering / DBSCAN

- Forms clusters in dense regions and treats sparse isolated points as noise.
- Epsilon (ε): neighbourhood radius.
- MinPts: minimum neighbours required for a core point.
- Core Point: has at least MinPts points in its epsilon neighbourhood.
- Border Point: has fewer than MinPts neighbours but lies within a core point's neighbourhood.
- Noise Point: belongs to no cluster.

### 7. Spectral and Graph-Based Clustering

- Represent points using a similarity graph.
- Spectral Clustering uses a similarity matrix and graph Laplacian, then eigenvectors to obtain a lower-dimensional representation for clustering.
- Graph-Based Clustering groups strongly connected nodes.

### 8. Outlier Analysis

- Identifies observations significantly different from the majority.
- LOF compares the local density of a point with the local density of its neighbours.
- A significantly higher LOF score indicates a potential outlier.
- Isolation Forest isolates observations using random partitions; anomalies tend to be isolated in fewer splits.

### 9. Clustering Evaluation

- Intrinsic evaluation uses only the dataset and clustering result (e.g., Silhouette Score, Davies-Bouldin Index).
- Extrinsic evaluation compares clusters with known class labels (e.g., Adjusted Rand Index, Normalized Mutual Information, Purity).

### 10. Cluster Optimization

Aim to improve cohesion within clusters and separation between clusters while considering K selection, initialization, noise, cluster shape and computational cost.

### Diagrams to Revise

- [K-Means](Images/kmeans-clustering.svg)
- [K-Medoids flowchart](Images/kmedoids-flowchart.svg)
- [Elbow Method](Images/elbow-method.svg)
- [Hierarchical Dendrogram](Images/hierarchical-dendrogram.svg)
- [DBSCAN](Images/dbscan-core-border-noise.svg)
- [Spectral vs K-Means](Images/spectral-vs-kmeans.svg)
- [Graph-Based Clustering](Images/graph-based-clustering.svg)
- [LOF](Images/lof-outlier.svg)
- [Isolation-based Outlier Detection](Images/isolation-forest.svg)

**Important:** Refer to [Complete Answers](Complete-Answers.md) for full explanations, numerical problems, tables and source wording.
