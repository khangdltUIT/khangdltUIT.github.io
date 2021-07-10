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

<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;f(x)&space;=&space;\frac{1}{1&space;&plus;&space;e^{-x}}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;f(x)&space;=&space;\frac{1}{1&space;&plus;&space;e^{-x}}" title="f(x) = \frac{1}{1 + e^{-x}}" /></a>

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

<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;f'(x)&space;=&space;\frac{e^{-x}}{(1&plus;e^{-x})^2}&space;=&space;\frac{1}{1&plus;e^{-x}}\cdot&space;\frac{e^{-x}}{1&plus;e^{-x}}&space;=f(x)(1-f(x))" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;f'(x)&space;=&space;\frac{e^{-x}}{(1&plus;e^{-x})^2}&space;=&space;\frac{1}{1&plus;e^{-x}}\cdot&space;\frac{e^{-x}}{1&plus;e^{-x}}&space;=f(x)(1-f(x))" title="f'(x) = \frac{e^{-x}}{(1+e^{-x})^2} = \frac{1}{1+e^{-x}}\cdot \frac{e^{-x}}{1+e^{-x}} =f(x)(1-f(x))" /></a>

**Đồ thị minh hoạ**

![alt](https://raw.githubusercontent.com/tuongkhangduongle/tuongkhangduongle.github.io/master/images/deriviate_sigmoid.png)

Ta thấy hàm số có đạo hàm tại mọi điểm trên đồ thị, thuận lợi cho việc tối ưu.

-------

From this graph, we see that the function has deriviates at every point in the graph, which is convinient for optimizing the loss function. 