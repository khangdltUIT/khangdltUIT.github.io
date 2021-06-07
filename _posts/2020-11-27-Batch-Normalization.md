---
layout: post
tittle: Batch Normalization
categories: CV
---

## 1. What is the idea of Batch Normalization?  
* Assuming that:  
F = sigmoid function:
     <a href="https://www.codecogs.com/eqnedit.php?latex=\frac{1}{1&plus;e^{-x}}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\frac{1}{1&plus;e^{-x}}" title="\frac{1}{1+e^{-x}}" /></a>  
  
<a href="https://www.codecogs.com/eqnedit.php?latex=x&space;=&space;w^{T}X" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x&space;=&space;w^{T}X" title="x = w^{T}X" /></a>  

* Loss Function( Cost Funtion):  

    <a href="https://www.codecogs.com/eqnedit.php?latex=L&space;=&space;\frac{1}{2}\sum\limits_{i=0}^n(y&space;-\hat{y})^{2}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?L&space;=&space;\frac{1}{2}\sum\limits_{i=0}^n(y&space;-\hat{y})^{2}" title="L = \frac{1}{2}\sum\limits_{i=0}^n(y -\hat{y})^{2}" /></a>

With F is the sigmoid activation:
+   Move quickly to 1 -> So the derivation is qpproximately 0
+   As a consequence, *vanishing gradient occur*

**Idea of Batch Normlization:**  
Batch Norm normalizes input by transfering them to normalized format ( gaussian) in order to improve training phase in deep neural network.

## 2. How does Batch Norm work?
- Batch Norm normalizes output of a previous activation layer by subtracting the batch mean and dividing by the batch standard deviation.  

- However, after this shift/scale of activation outputs by some randomly initialized parameters, the weights in the next layer are no longer optimal. SGD ( Stochastic gradient descent) undoes this normalization if it’s a way for it to minimize the loss function.  

- Consequently, batch normalization adds two trainable parameters to each layer, so the normalized output is multiplied by a “standard deviation” parameter (gamma) and add a “mean” parameter (beta). In other words, batch normalization lets SGD do the denormalization by changing only these two weights for each activation, instead of losing the stability of the network by changing all the weights.

![alt](https://miro.medium.com/max/633/1*Hiq-rLFGDpESpr8QNsJ1jg.png)