---
layout: post
tittle: Linear Regression
categories: Machine
---

# &ensp; &ensp; Linear Regression

Đầu tiên tôi sẽ đưa ra 1 mô phỏng dữ liệu giúp bạn dễ cảm nhận được dạng bài toán này

Tôi cần mua 1 căn hộ ở trung tâm thành phố Machine Learning và tôi cần biết giá trị của nó là bao nhiêu để tích cóp tiền. *Vấn đề xảy ra là tôi không biết tiền mua 1 căn hộ là bao nhiêu?*

Để giải quyết vấn đề trên tôi quyết định đi thu thập giá nhà xung quanh căn hộ tôi dự định mua và số liệu bên dưới là mô tả cho những dữ liệu mà tôi thống kê được.

|Size in feet²(x) |&ensp; Price($) in 1000(y)|
|-----------------|:-------------------------|
|2104             |&ensp;460                 |
|1416             |&ensp;232                 |
|1534             |&ensp;315                 |
|852              |&ensp;178                 |

Trong đó:
* m = số lượng traning example
* x's = input / *feature*
* y's = output / *target* variable
* (x;y) → 1 training example
* (xᶦ;yᶦ) → i training example

Cách 1 thuật toán supervised learning làm việc tương tự như sau:

![alt](https://anujdutt9.github.io/assets/images/posts/2018/SL.png)

Hypothesis (kí hiệu là **h**) là 1 hàm để biến đổi từ input x ra output y(đối với dữ liệu trên là hàm h sẽ có chức năng dự đoán giá nhà dựa trên size of feet²).

*Vậy ta biểu diễn h như thế nào?*

Đối với univariate linear regression:

<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;h_\theta&space;(x)&space;=&space;\theta_0&space;&plus;&space;\theta_1x_1" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;h_\theta&space;(x)&space;=&space;\theta_0&space;&plus;&space;\theta_1x_1" title="h_\theta (x) = \theta_0 + \theta_1x_1" /></a>

![alt](https://raw.githubusercontent.com/kangdoung/kangdoung.github.io/master/images/lineardemo_data.png)
