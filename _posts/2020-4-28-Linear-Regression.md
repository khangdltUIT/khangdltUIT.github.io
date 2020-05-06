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

Giả sử rằng size in feet²(x) và price(y) phụ thuộc tuyến tính vào nhau, bạn có thể hiểu đơn giản là khi giá trị x tăng thì giá trị y tăng và ngược lại. *Vậy vấn đề tiếp theo của chúng ta là gì?*

Đó chính là ta tìm ra một hàm h sao cho với size in feet² sẽ tìm được price.

Hàm cần tìm sẽ có dạng Y = aX + b. Bài toán lúc này sẽ quy về bài toán với các cặp điểm (xᶦ;yᶦ), tìm **2 parameter(tham số) a và b**( bài toán quá quen thuộc thời phổ thông của chúng ta).

Tất cả các giai đoạn trên của ta là tìm hàm hypothesis để từ giá trị input(size in feet²) ta sẽ có output(price).
![alt](https://camo.githubusercontent.com/7cf14a413358a6a4ee293ea0443d5420ca6a8cbb/68747470733a2f2f616e756a64757474392e6769746875622e696f2f6173736574732f696d616765732f706f7374732f323031382f534c2e706e67)

Đối với bài toán trên được gọi là linear regression with one variable (univariate linear regression).
*   **Định nghĩa**:
    Trong thống kê, linear regression là 1 phương pháp mô hình hóa giữa 1 đại lượng vô hướng với 1 hay nhiều biến độc lập

    Các dạng mô hình hồi quy tuyến tính:

    <a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;h_\theta&space;(x)&space;=&space;\theta_1x_1&space;&plus;&space;\theta_2x_2&space;&plus;&space;\theta_3&space;=&space;\begin{bmatrix}\theta_1&space;\&space;\theta_2&space;\&space;\theta_3&space;\end{bmatrix}&space;\begin{bmatrix}&space;x_1\\&space;x_2\\&space;1&space;\end{bmatrix}&space;=&space;\theta^TX" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;h_\theta&space;(x)&space;=&space;\theta_1x_1&space;&plus;&space;\theta_2x_2&space;&plus;&space;\theta_3&space;=&space;\begin{bmatrix}\theta_1&space;\&space;\theta_2&space;\&space;\theta_3&space;\end{bmatrix}&space;\begin{bmatrix}&space;x_1\\&space;x_2\\&space;1&space;\end{bmatrix}&space;=&space;\theta^TX" title="h_\theta (x) = \theta_1x_1 + \theta_2x_2 + \theta_3 = \begin{bmatrix}\theta_1 \ \theta_2 \ \theta_3 \end{bmatrix} \begin{bmatrix} x_1\\ x_2\\ 1 \end{bmatrix} = \theta^TX" /></a>

    <a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;h_\theta&space;(x)&space;=&space;\theta_1x_1&space;&plus;&space;\theta_2x_2&space;&plus;&space;\theta_3x_1x_2&space;&plus;&space;\theta_4x_1^2&space;=&space;\begin{bmatrix}\theta_1&space;\&space;\theta_2&space;\&space;\theta_3&space;\&space;\theta_4&space;\end{bmatrix}&space;\begin{bmatrix}&space;x_1\\&space;x_2&space;\\x_1x_2&space;\\x_1^2&space;\end{bmatrix}&space;=&space;\theta^TX" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;h_\theta&space;(x)&space;=&space;\theta_1x_1&space;&plus;&space;\theta_2x_2&space;&plus;&space;\theta_3x_1x_2&space;&plus;&space;\theta_4x_1^2&space;=&space;\begin{bmatrix}\theta_1&space;\&space;\theta_2&space;\&space;\theta_3&space;\&space;\theta_4&space;\end{bmatrix}&space;\begin{bmatrix}&space;x_1\\&space;x_2&space;\\x_1x_2&space;\\x_1^2&space;\end{bmatrix}&space;=&space;\theta^TX" title="h_\theta (x) = \theta_1x_1 + \theta_2x_2 + \theta_3x_1x_2 + \theta_4x_1^2 = \begin{bmatrix}\theta_1 \ \theta_2 \ \theta_3 \ \theta_4 \end{bmatrix} \begin{bmatrix} x_1\\ x_2 \\x_1x_2 \\x_1^2 \end{bmatrix} = \theta^TX" /></a>

    Công thức tổng quát:

    <a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;h_\theta(x)&space;=&space;\sum\limits_{i=0}^n&space;\theta_ix_i&space;=&space;\theta^Tx" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;h_\theta(x)&space;=&space;\sum\limits_{i=0}^n&space;\theta_ix_i&space;=&space;\theta^Tx" title="h_\theta(x) = \sum\limits_{i=0}^n \theta_ix_i = \theta^Tx" /></a>

    Chú ý: cả theta và x đều là vector.

* **Cost Function(Loss Function)**:

    * **Giới thiệu**:
    
Đối với bài toán ở vd trên ta có hàm 

<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;h_\theta&space;(x)&space;=&space;\theta_0&space;&plus;&space;\theta_1x_1" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;h_\theta&space;(x)&space;=&space;\theta_0&space;&plus;&space;\theta_1x_1" title="h_\theta (x) = \theta_0 + \theta_1x_1" /></a>

Khi biểu diễn các điểm dữ liệu và hàm h(x) ta được model như hình sau:

![alt](https://raw.githubusercontent.com/kangdoung/kangdoung.github.io/master/images/demo_gr.png)


Ta nhận thấy rằng các đường thẳng h(x) không hoàn toàn đi qua các điểm dữ liệu. Mục đích của hàm mất mát chính là chọn tham số θᵢ sao cho khoảng cách từ các điểm dữ liệu đến h(x) là nhỏ nhất.

![alt](https://github.com/kangdoung/kangdoung.github.io/blob/master/images/cost_func.png?raw=true)

   * Công thức
    
<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;J(\theta)&space;=&space;\frac{1}{2m}&space;\left&space;\|&space;X\theta&space;-&space;y&space;\right&space;\|^2&space;=&space;\frac{1}{2m}&space;\sum\limits_{i=1}^m(h_{\theta}(x^{(i)})&space;-&space;y^{(i)})^2&space;=&space;\frac{1}{2m}&space;\sum\limits_{i=1}^m(\theta^Tx^{(i)}&space;-&space;y^{(i)})^2" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;J(\theta)&space;=&space;\frac{1}{2m}&space;\left&space;\|&space;X\theta&space;-&space;y&space;\right&space;\|^2&space;=&space;\frac{1}{2m}&space;\sum\limits_{i=1}^m(h_{\theta}(x^{(i)})&space;-&space;y^{(i)})^2&space;=&space;\frac{1}{2m}&space;\sum\limits_{i=1}^m(\theta^Tx^{(i)}&space;-&space;y^{(i)})^2" title="J(\theta) = \frac{1}{2m} \left \| X\theta - y \right \|^2 = \frac{1}{2m} \sum\limits_{i=1}^m(h_{\theta}(x^{(i)}) - y^{(i)})^2 = \frac{1}{2m} \sum\limits_{i=1}^m(\theta^Tx^{(i)} - y^{(i)})^2" /></a>

    *   Tìm nghiệm θ₀ của bài toán:

    Tôi biến đổi công thức J(θ) như sau(các bạn có thể tìm hiểu thêm kiến thức về toán thông qua sách Machine Learning cơ bản_Vũ Hữu Tiệp):

    <a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\large&space;J(\theta)=\frac{1}{2m}\left&space;\|&space;X\theta-y&space;\right&space;\|^2=\frac{1}{2m}(X\theta-y)^T(X\theta-y)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;\large&space;J(\theta)=\frac{1}{2m}\left&space;\|&space;X\theta-y&space;\right&space;\|^2=\frac{1}{2m}(X\theta-y)^T(X\theta-y)" title="\large J(\theta)=\frac{1}{2m}\left \| X\theta-y \right \|^2=\frac{1}{2m}(X\theta-y)^T(X\theta-y)" /></a>

    Đạo hàm:
    
    <a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\large&space;\frac{\partial&space;J}{\partial&space;\theta}=2X^TX\theta-2X^{T}y=0" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;\large&space;\frac{\partial&space;J}{\partial&space;\theta}=2X^TX\theta-2X^{T}y=0" title="\large \frac{\partial J}{\partial \theta}=2X^TX\theta-2X^{T}y=0" /></a>

    Tương đương ta có: 

    <a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\large&space;X^TX\theta=X^{T}y" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;\large&space;X^TX\theta=X^{T}y" title="\large X^TX\theta=X^{T}y" /></a>

    Giả sử <a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\large&space;X^TX" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;\large&space;X^TX" title="\large X^TX" /></a> có thể nghịch đảo, ta có:

    <a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\large&space;\theta=(X^TX)^{-1}X^Ty" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;\large&space;\theta=(X^TX)^{-1}X^Ty" title="\large \theta=(X^TX)^{-1}X^Ty" /></a>

    * ***Phân tích ưu/nhược điểm của pp này***:
        * Ưu điểm: công thức đơn giản, chỉ đưa dữ liệu vào và tính toán
        * Nhược điểm: tài nguyên tính toán ma trận nghịch đảo lớn (complexity), thực tế các bài toán hồi quy thường sử dụng **gradient descent** để tối ưu hóa Cost Function


