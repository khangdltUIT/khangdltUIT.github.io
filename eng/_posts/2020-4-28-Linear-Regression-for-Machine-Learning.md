---
layout: post
tittle: LINEAR REGRESSION IN MACHINE LEARNING
categories: ML
---

## 1. Introduction
&ensp;Linear Regression is a model introduced in most courses about Machine Learning because of its simplicity and ease of learning.  
&ensp;Linear Regression is a supervised learning model, which is used in regression tasks.  
&ensp; Furthermore, its model is applied in many are of life, namely: weather forecast, housing price, and in Feature Selection field, because it could measure the coefficient between features and output.  

## 2. Linear Regression in ML

### Model Representation
Initially, linear regression is an attractive model because of its simple model representation.  
A linear equation presenting the model combines features input for predicting the output. Both of them is numeric.

&ensp; Formula:

<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;Y&space;=&space;W_0&space;&plus;&space;W_1\cdot&space;X" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;Y&space;=&space;W_0&space;&plus;&space;W_1\cdot&space;X" title="Y = W_0 + W_1\cdot X" /></a>

However, in real-life problems, features in the dataset could be scaled up to more than 30. So, W1 could be presented by a parameters vector, like: W1 = [W1,W2,..Wn], same for features vector X.

<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;Y&space;=&space;\begin{bmatrix}&space;W_0\\&space;W_1\\&space;...\\&space;W_n\\&space;\end{bmatrix}&space;\cdot&space;\begin{bmatrix}&space;1\\&space;X_1\\&space;...\\&space;X_n\\&space;\end{bmatrix}&space;=&space;W^{T}\cdot&space;X" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;Y&space;=&space;\begin{bmatrix}&space;W_0\\&space;W_1\\&space;...\\&space;W_n\\&space;\end{bmatrix}&space;\cdot&space;\begin{bmatrix}&space;1\\&space;X_1\\&space;...\\&space;X_n\\&space;\end{bmatrix}&space;=&space;W^{T}\cdot&space;X" title="Y = \begin{bmatrix} W_0\\ W_1\\ ...\\ W_n\\ \end{bmatrix} \cdot \begin{bmatrix} 1\\ X_1\\ ...\\ X_n\\ \end{bmatrix} = W^{T}\cdot X" />
* ***Notes:  Bias Trick*** 

&ensp;Linear Regression often mentioned a more little bit complex relation when it has a free parameter W0( be also called b in some materials ).
This relation is called affine.
* If W0 == 0, the regression line ưill usually cross through the origin.
* If W0 != 0, the model will be more flexible by removing the constraint relationship between features input and predicted output. The quantity W0 is called bias.
The technique of adding one feature whose value is one and concatenate bias b to parameters vector w is called the bias trick.

### Build a Loss Function and optimize.
#### *Loss Function*

&ensp; When building a linear regression model, the goal that we want is to minimize the difference between groundtruth and predicted output. So, a loss function is built for measuring it. Formulation:  
<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;L_w&space;=&space;\frac{1}{2N}\sum_{i=1}^{N}(y-\hat{y})^2" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;L_w&space;=&space;\frac{1}{2N}\sum_{i=1}^{N}(y-\hat{y})^2" title="L_w = \frac{1}{2N}\sum_{i=1}^{N}(y-\hat{y})^2" /></a>

This loss is called *mean squared error (MSE)*. Which:
* N: total data points
* y: groundtruth
* \hat{y}: predicted output

#### *Optimization*

The optimize problem is minimizing the value of the loss function. The goal of that is fitting parameters in the parameter vector to have the smallest difference between predicted output and griuth-truth. In general, Gradient Descent is used to fitting parameters.

### Linear Regression
#### Code from scratch

* Dataset  
    * X: height (cm)  
    * y: weight (kg)

```python
# height (cm)
X = np.array([[147, 150, 153, 158, 163, 165, 168, 170, 173, 175, 178, 180, 183]]).T # each row is a point 
# weight (kg)
y = np.array([ 49, 50, 51,  54, 58, 59, 60, 62, 63, 64, 66, 67, 68])
```
* Linear Regression Function:

```python
def linear_regression(X, y, x0)
    one = np.ones((X.shape[0], 1))
    Xbar = np.concatenate((one, X), axis = 1) # each point is one row 
    # Calculating weights of the fitting line 
    A = np.dot(Xbar.T, Xbar)
    b = np.dot(Xbar.T, y)
    w = np.dot(np.linalg.pinv(A), b)
    # weights
    w_0 = w[0]
    w_1 = w[1]

    x0 = np.linspace(145, 185, 2,endpoint=True)
    y0 = w_0 + w_1*x0

    return y0
```

-----

Read this post in Vietnamese at <a href="{{ site.baseurl }}/Hồi-quy-tuyến-tính-trong-học-máy/">here</a>
