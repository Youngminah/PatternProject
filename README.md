# PatternProject
for Basic of Machine-Learning



## 08. binary classifier to classify digit 0 against all the other digits(least square).

Build a binary classifier to classify digit 0 against all the other digits at MNIST dataset.

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


