# PatternProject
for Basic of Machine-Learning


## 01. [Taylor Approximation]

1. Define a differentiable function that maps from real number to real number.
2. Define a domain of the function.
3. Plot the function.
4. Select a point within the domain.
5. Mark the selected point on the function.
6. Define the first-order Taylor approximation at the selected point.
7. Plot the Taylor approximation with the same domain of the original function.


## 02. [Visualize average of image.]


1. Load MNIST training dataset.
2. Compute the average images for each label (digit) based on L2-norm.
3. Visualize the average images.


## 03.[ Kmeans Clustering using MNIST dataset]


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


## 04. [Kmeans Clustering on color image.]


Let $f(x)$ be a color image and $x$ be the index of image in the domain.
The values of image $f(x)$ consist of [red, green, blue] intensity.

Apply K-means algorithm to image $f(x)$ based on its color value with given number of clusters $K$ and visualize the progress of optimization and results of the algorithm for each selected number of clusters $K$.

1. Select any color image that consists of distinctive regions with different colors.
2. Apply K-means algorithm to the given image with at least 4 different choice of $K$.
3. For each $K$, plot the energy curve and the result image.

[Visualisation]

1. Input color image
2. Energy curve for each $K$
3. Output image for each $K$

[Energy]

\frac{1}{n} \sum_{x \in \Omega} \| f(x) - m_c \|^2,

where $\Omega$ denotes the image domain and the number of pixels $| \Omega |$ is $n$, and $m_c$ denotes the centroid for cluster $c$ that is the cluster label of $f(x)$.

[Output Image]

g(x) = m_c where label(x) = c

Each pixel of the output image $g(x)$ should be its centroid $m_c$ where $c$ is the cluster label of $g(x)$.


## 05. [Kmeans Clustering on the spatial domain.]


Apply K-means algorithm to the regular grid of a spatial domain in two dimension with varying number of clusters.

The spatial domain can be represented by two matrices where one matrix represents the horizontal index and the other matrix represents the vertical index.

Define a distance between each spatial point (x_i, y_i) and a centroid (c_x^k, c_y^k) for cluster k using L2-norm square and L1-norm.

Visualize the result using color coding scheme that distinguishes different clusters.

Observe the trajectory of centroid during the optimization and the shape of the clusters depending on the distance.

## 06. [Apply K-means algorithm to both image value and its spatial domain]

For a given input image (either gray or color), apply a K-means algorithm that is designed to take into consideration of both the image intensity and its spatial domain with varying parameters: the number of clusters and the trade-off between the intensity energy and the spatial energy.

The objective function is given by:

\sum_k \sum_\{ x \in I(k) \} [ \| f(x) - m_k \|^2 + a * \| x - c_k \|^2 ]

where I(k) denotes the index set of x that belongs to cluster k, m_k denotes the centroid of image intensity for cluster k, c_k denotes the centroid of spatial location for cluster k, and a determines the importance between the image intensity and the spatial relation.

- Visualize the clustering results with varying k and a using the centroid color m_k for each cluster k.

- Visualize the energy curve for both the intensity energy and the spatial energy.


## 07. [Polynomial fitting]

Solve a least square problem to find an optimal polynomial curve for a given set of two dimensional points.

Demonstrate the effect of the degree of polynomial in fitting a given set of points.

- choose a polynomial curve and generate points along the curve with random noise

- plot the generated noisy points along with its original polynomial without noise

- plot the approximating polynomial curve obtained by solving a least square problem

- plot the approximating polynomial curve with varying polynomial degree

## 08. [binary classifier to classify digit 0 against all the other digits(least square).]

Let x = (x_1, x_2, ... , x_m) be a vector representing an image in the dataset.

The prediction function f_w(x) is defined by the linear combination of data (1, x) and the model parameter w:
f_w(x) = w_0 * 1 + w_1 * x_1 + w_2 * x_2 + ... + w_m * x_m
where w = (w_0, w_1, ... , w_m)

The prediction function f_w(x) should have the following values:
f_w(x) = +1 if label(x) = 0
f_w(x) = -1 if label(x) is not 0

The optimal model parameter w is obtained by minimizing the following objective function:
\sum_i ( f_w(x^(i) - y^(i) )^2

1. Compute an optimal model parameter using the training dataset
2. Compute (1) True Positive, (2) False Positive, (3) True Negative, (4) False Negative based on the computed optimal model parameter using (1) training dataset and (2) testing dataset.


## 09. [binary classifier for each digit against all the other digits(least square).]

Let x = (x_1, x_2, ... , x_m) be a vector representing an image in the dataset.

The prediction function f_d(x; w) is defined by the linear combination of data (1, x) and the model parameter w for each digit d :
f_d(x; w) = w_0 * 1 + w_1 * x_1 + w_2 * x_2 + ... + w_m * x_m
where w = (w_0, w_1, ... , w_m)

The prediction function f_d(x; w) should have the following values:
f_d(x; w) = +1 if label(x) = d
f_d(x; w) = -1 if label(x) is not d

The optimal model parameter w is obtained by minimizing the following objective function for each digit d :
\sum_i ( f_d(x^(i); w) - y^(i) )^2

and the label of input x is given by:

argmax_d f_d(x; w)

1. Compute an optimal model parameter using the training dataset for each classifier f_d(x, w)
2. Compute (1) true positive rate, (2) error rate using (1) training dataset and (2) testing dataset.

## 10. [binary classifier based on k random feature for each digit(least square).]

Build a binary classifier based on k random features for each digit against all the other digits at MNIST dataset.

Let x = (x_1, x_2, ... , x_m) be a vector representing an image in the dataset.

The prediction function f_d(x; w) is defined by the linear combination of input vector x and the model parameter w for each digit d :

f_d(x; w) = w_0 * 1 + w_1 * g_1 + w_2 * g_2 + ... + w_k * g_k

where w = (w_0, w_1, ... , w_k) and the basis function g_k is defined by the inner product of random vector r_k and input vector x.

You may want to try to use g_k = max( inner production( r_k, x ), 0 ) to see if it improves the performance.

The prediction function f_d(x; w) should have the following values:

f_d(x; w) = +1 if label(x) = d
f_d(x; w) = -1 if label(x) is not d

The optimal model parameter w is obtained by minimizing the following objective function for each digit d :
\sum_i ( f_d(x^(i); w) - y^(i) )^2

and the label of input x is given by:

argmax_d f_d(x; w)

1. Compute an optimal model parameter using the training dataset for each classifier f_d(x, w)
2. Compute (1) true positive rate, (2) error rate using (1) training dataset and (2) testing dataset.
