# PatternProject
for Basic of Machine-Learning



## 03. Kmeans Clustering using MNIST dataset

[K-means clustering]

1. Apply K-means clustering to MNIST training dataset with different K = 5, 10, 15, 20 and present the following results for each K.
2. Visualize K centroid images for each category.
3. Plot the training energy per optimization iteration.
4. Plot the training accuracy per optimization iteration.
5. Plot the testing accuracy per optimization iteration.

[energy]

\sum_{k = 1}^K \| x_i - c_{k_i} \|^2
where $k_i$ denotes the category of $x_i$, and $c_{k_i}$ denotes the centroid of category $x_i$.

[accuracy]

\frac{\sum_{k = 1}^K m_k}{N}
where $N$ denotes the total number of data, and $m_k$ denotes the number of data with majority for category $k$.

- (training energy) is computed on the training dataset.
- (training accuracy) is computed on the training dataset.
- (testing accuracy) is computed on the testing dataset.


