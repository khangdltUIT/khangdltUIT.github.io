---
layout: post
tittle: LOGISTIC REGRESSION FOR MACHINE LEARNING
categories: ML
---

## **1. Introduction**

A model introduced commonly adjacent to Linear Regression is Logistic Regression. Other than Linear Regression, this model is used in the classification.

## **2. Logistic Regression Model**

### ***2.1 Representation***
**Formula:**

<br/><br/>
<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\dpi{150}&space;\fn_cm&space;\LARGE&space;f(x)&space;=&space;\frac{1}{1&plus;e^(-x)}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;\dpi{150}&space;\fn_cm&space;\LARGE&space;f(x)&space;=&space;\frac{1}{1&plus;e^(-x)}" title="\LARGE f(x) = \frac{1}{1+e^(-x)}" /></a>
<br/><br/>

With:
* e: epsilon = 1e-7
* x: input

**Described graph:**

![alt](https://raw.githubusercontent.com/tuongkhangduongle/tuongkhangduongle.github.io/9aa8a71891420b37800514fba10e63b87ca0f989/images/sigmoid.svg)



* Notes:

     * The sigmoid function is bounded in the interval (0, 1).
     * Considering a point with coordinates (0.1/2):
         * Points with a coordinate greater than 0 give a value higher than 0.5.
         * Points with coordinates less than 0, vice versa.
         * The value of f(x) can be considered as the probability of the variable x, the cause of its applicability to the classification problem.

**Deriviate:**

<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\dpi{150}&space;\fn_phv&space;\large&space;f'(x)&space;=&space;\frac{e^{-x}}{(1&plus;e^{-x})^2}&space;=&space;\frac{1}{1&plus;e^{-x}}\cdot&space;\frac{e^{-x}}{1&plus;e^{-x}}&space;=f(x)(1-f(x))" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;\dpi{150}&space;\fn_phv&space;\large&space;f'(x)&space;=&space;\frac{e^{-x}}{(1&plus;e^{-x})^2}&space;=&space;\frac{1}{1&plus;e^{-x}}\cdot&space;\frac{e^{-x}}{1&plus;e^{-x}}&space;=f(x)(1-f(x))" title="\large f'(x) = \frac{e^{-x}}{(1+e^{-x})^2} = \frac{1}{1+e^{-x}}\cdot \frac{e^{-x}}{1+e^{-x}} =f(x)(1-f(x))" /></a>

**Illustrative Graph:**

![alt](https://raw.githubusercontent.com/tuongkhangduongle/tuongkhangduongle.github.io/master/images/deriviate_sigmoid.png)

From this graph, we see that the function has deriviates at every point in the graph, which is convinient for optimizing the loss function. 

### ***2.2 Loss function***

The assumption that the probability of data point x belonging to class 1 is f(x), the other point is 1 - f(x). Therefor, we could build a loss function for the problem based on cross-entropy function:

<br/><br/>
<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\dpi{150}&space;L(\theta&space;)=\sum_{i=1}^m&space;(y^i&space;logP_i&plus;&space;(1-y^i)log(1-P_i))" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;\dpi{150}&space;L(\theta&space;)=\sum_{i=1}^m&space;(y^i&space;logP_i&plus;&space;(1-y^i)log(1-P_i))" title="L(\theta )=\sum_{i=1}^m (y^i logP_i+ (1-y^i)log(1-P_i))" /></a>
<br/><br/>

Theta could be computed by multiplying parameters vector W with features vector X. The goal is finding the minimum value of the loss function, meaning that finding the values of each parameter in vector W such that the function is minimized