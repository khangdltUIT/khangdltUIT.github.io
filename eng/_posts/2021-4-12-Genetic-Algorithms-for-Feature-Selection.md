---
layout: post
tittle: Feature Selection
categories: ML
comments: true
---

## 1.Goal of Feature Selection
The goal of using feature selection is to find the best set of features that build a useful model.

***Note: the differences between PCA(Principal Component Analysis) and Feature Selection***  

* PCA tries to reduce data dimensionality by exploring how one part is expressed by other attributes (linear dependency).

* On the other hand, Feature Selection ranks the affection of features on the model, then selects a subset of features on those ranking.


## 2. Types of Feature Selection:
1. Supervised Techniques:  

These techniques can be used for labelled data and could identify relevant features of increasing the efficiency of supervised models like classification and regression.

2. Unsupervised Techniques:  

These techniques can be used for unlabeled data.

![alt](https://raw.githubusercontent.com/khangdltUIT/khangdltUIT.github.io/master/images/Overview-of-Feature-Selection-Techniques3.webp
)

3. Differences between filter and wrapper methods:

The main difference between both methods are:
* Filter method measures the relevance of features, while Wrapper method measures by training the data on a subset of features and then select it.
* Filter method is faster than the other method as filter method not a select subset of a feature of the training model. Furthermore, the wrapper method could use more resources for computation.
* Filter methods use statistical to measure the relevance of features, while the wrapper method use cross-validation.
* The filter could find the best subset of features, but the wrapper method always provides the best subset features.
* As a consequence, using the subset features provided by the wrapper method might be lead to overfitting.

## 3. Thuật toán Genetic Algorithms
![alt](https://raw.githubusercontent.com/khangdltUIT/khangdltUIT.github.io/master/images/genetic_algorithm.png)

Genetic algorithms(GAs) are algorithms for stochastic global optimization, which is based on Darwin.
The idea is that Gas creates random variables, then crossover them, after that combining them which is best in the group to have the best subset features.
Progress has 3 parts:
* Selection
* Crossover
* Mutation



