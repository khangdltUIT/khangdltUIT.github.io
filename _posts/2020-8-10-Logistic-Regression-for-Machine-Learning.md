---
layout: post
tittle: LOGISTIC REGRESSION FOR MACHINE LEARNING
categories: ML
---

## 1. Giới thiệu - Introduction  

Mô hình thường được giới thiệu sau Linear Regression là Logistic Regression. Khác với Linear Regression, mô hình này thường được áp dụng vào bài toán phân loại. 

----

A model introduced commonly adjacent to Linear Regression is Logistic Regression. Other than Linear Regression, this model is used in the classification.

## 2. Mô hình Logistic Regression - Logistic Regression Model

### 2.1 Biểu diễn toán học
**Công thức:**

<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\dpi{150}&space;\fn_cm&space;\LARGE&space;f(x)&space;=&space;\frac{1}{1&plus;e^(-x)}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;\dpi{150}&space;\fn_cm&space;\LARGE&space;f(x)&space;=&space;\frac{1}{1&plus;e^(-x)}" title="\LARGE f(x) = \frac{1}{1+e^(-x)}" /></a>

Trong đó:
* e: epsilon = 1e-7
* x: input

**Đồ thị minh hoạ:**

![alt](https://raw.githubusercontent.com/tuongkhangduongle/tuongkhangduongle.github.io/9aa8a71891420b37800514fba10e63b87ca0f989/images/sigmoid.svg)

* Nhận xét:

    * Hàm sigmoid bị chặn trong khoảng (0;1).
    * Xét điểm có toạ độ (0,1/2):
        * Các điểm có hoành độ lớn hơn 0 thì cho giá trị cao hơn 0.5.
        * Các điểm có hoành độ nhỏ hơn 0 thì ngược lại.
        * Giá trị của f(x) có thể xem là xác suất của biến x, nguyên nhân của việc áp dụng được vào bài toán phân lớp.  

------------

* Notes:

     * The sigmoid function is bounded in the interval (0, 1).
     * Considering a point with coordinates (0.1/2):
         * Points with a coordinate greater than 0 give a value higher than 0.5.
         * Points with coordinates less than 0, vice versa.
         * The value of f(x) can be considered as the probability of the variable x, the cause of its applicability to the classification problem.

**Đạo hàm:**

<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\dpi{150}&space;\fn_phv&space;\large&space;f'(x)&space;=&space;\frac{e^{-x}}{(1&plus;e^{-x})^2}&space;=&space;\frac{1}{1&plus;e^{-x}}\cdot&space;\frac{e^{-x}}{1&plus;e^{-x}}&space;=f(x)(1-f(x))" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;\dpi{150}&space;\fn_phv&space;\large&space;f'(x)&space;=&space;\frac{e^{-x}}{(1&plus;e^{-x})^2}&space;=&space;\frac{1}{1&plus;e^{-x}}\cdot&space;\frac{e^{-x}}{1&plus;e^{-x}}&space;=f(x)(1-f(x))" title="\large f'(x) = \frac{e^{-x}}{(1+e^{-x})^2} = \frac{1}{1+e^{-x}}\cdot \frac{e^{-x}}{1+e^{-x}} =f(x)(1-f(x))" /></a>

**Đồ thị minh hoạ**

![alt](https://raw.githubusercontent.com/tuongkhangduongle/tuongkhangduongle.github.io/master/images/deriviate_sigmoid.png)

Ta thấy hàm số có đạo hàm tại mọi điểm trên đồ thị, thuận lợi cho việc tối ưu.

-------

From this graph, we see that the function has deriviates at every point in the graph, which is convinient for optimizing the loss function. 

### 2.2 Xây dựng hàm mất mát - Loss function

Giả sử xác suất của điểm dữ liệu x thuộc vào lớp thứ nhất là f(x) thì xác suất của trường hợp còn lại là 1-f(x). Khi đó, ta có thể xây dựng hàm mất mát cho bài toán dựa trên hàm cross-entropy như sau:
----

The assumption that the probability of data point x belonging to class 1 is f(x), the other point is 1 - f(x). Therefor, we could build a loss function for the problem based on cross-entropy function:

<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\dpi{150}&space;\fn_cm&space;\LARGE&space;L(\theta&space;)=-\sum_{i=1}^m&space;(y^i&space;logP_i&plus;&space;(1-y^i)log(1-P_i))" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;\dpi{150}&space;\fn_cm&space;\LARGE&space;L(\theta&space;)=-\sum_{i=1}^m&space;(y^i&space;logP_i&plus;&space;(1-y^i)log(1-P_i))" title="\LARGE L(\theta )=-\sum_{i=1}^m (y^i logP_i+ (1-y^i)log(1-P_i))" /></a>

Theta được tính bằng cách lấy vector tham số W nhân với vector đặc trưng X. Mục tiêu là đi tìm giá trị theta sao cho hàm loss đạt cực tiểu, tức là tìm giá trị của các tham số thuộc W sao cho theta đạt cực tiểu. 

----

Theta could be computed by multiplying parameters vector W with features vector X. The goal is finding the minimum value of the loss function, meaning that finding the values of each parameter in vector W such that the function is minimized