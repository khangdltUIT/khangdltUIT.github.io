---
layout: post
tittle: LINEAR REGRESSION IN MACHINE LEARNING
categories: ML
---

![alt](https://raw.githubusercontent.com/khangdltUIT/khangdltUIT.github.io/master/images/Vintage%20Logotype%20Etsy%20Banner.png)
## 1. Giới thiệu - Introduction
&ensp; Hồi quy tuyến tính là mô hình mở đầu cho nhiều khóa học về Machine Learning bởi vì tính đơn giản và dễ hiểu của nó.  
&ensp; Hồi quy tuyến tính thuộc loại mô hình học tập có giám sát ( *supervised learning*), được sử dụng trong các bài toán về hồi quy.
&ensp; Ngoài ra, mô hình được ứng dụng rộng rãi trong cuộc sống như: dự báo thời tiết, giá nhà, ... và còn có thể ứng dụng trong Feature Selection do có thể đánh giá được mối liên hệ giữa thuộc tính và kết quả dự đoán.

--

&ensp;Linear Regression is a model introduced in most courses about Machine Learning because of its simplicity and ease of learning.  
&ensp;Linear Regression is a supervised learning model, which is used in regression tasks.  
&ensp; Furthermore, its model is applied in many are of life, namely: weather forecast, housing price, and in Feature Selection field, because it could measure the coefficient between features and output.  

## 2. Mô hình Linear Regression trong Machine Learning

### Biểu diễn mô hình - Model Representation
&ensp; Đầu tiên, hồi quy tuyến tính là mô hình trực quan bởi vì cách biểu diễn của nó rất đơn giản.  
&ensp; Một hàm tuyến tính sẽ đại diện cho mô hình kết hợp các dặc trưng ( features) đầu vào để dự đoán đầu ra. Kiểu dữ liệu của chúng đều là số thực. 

--

Initially, linear regression is an attractive model because of its simple model representation.  
A linear equation presenting the model combines features input for predicting the output. Both of them is numeric.

&ensp; Công thức:

<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;Y&space;=&space;W_0&space;&plus;&space;W_1\cdot&space;X" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;Y&space;=&space;W_0&space;&plus;&space;W_1\cdot&space;X" title="Y = W_0 + W_1\cdot X" /></a>

&ensp;Tuy nhiên trong các bài toán thực tế, các đặc trưng trong bộ dữ liệu có thể tăng lên đến cả hàng chục thuộc tính. Do đó, W1 có thể được hiểu là một vectơ tham số như sau: W1 = [W1,W2,..Wn]. Tương tự cho vectơ đặc trưng X.

--

However, in real-life problems, features in the dataset could be scaled up to more than 30. So, W1 could be presented by a parameters vector, like: W1 = [W1,W2,..Wn], same for features vector X.

Mô hình có thể biểu diễn lại như sau:  

<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;Y&space;=&space;\begin{bmatrix}&space;W_0\\&space;W_1\\&space;...\\&space;W_n\\&space;\end{bmatrix}&space;\cdot&space;\begin{bmatrix}&space;1\\&space;X_1\\&space;...\\&space;X_n\\&space;\end{bmatrix}&space;=&space;W^{T}\cdot&space;X" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;Y&space;=&space;\begin{bmatrix}&space;W_0\\&space;W_1\\&space;...\\&space;W_n\\&space;\end{bmatrix}&space;\cdot&space;\begin{bmatrix}&space;1\\&space;X_1\\&space;...\\&space;X_n\\&space;\end{bmatrix}&space;=&space;W^{T}\cdot&space;X" title="Y = \begin{bmatrix} W_0\\ W_1\\ ...\\ W_n\\ \end{bmatrix} \cdot \begin{bmatrix} 1\\ X_1\\ ...\\ X_n\\ \end{bmatrix} = W^{T}\cdot X" />
* ***Notes:  Bias Trick*** 
&ensp;Linear Regression thường được nói đến 1 quan hệ phức tạp hơn một chút khi có sự xuất hiện của số hạng tự do W0 ( một số tài liệu sẽ là b).  
Mối quan hệ này được gọi là *affine*.

* Nếu W0 == 0, đường thẳng y luôn đi qua gốc tọa độ.
* Nếu W0 != 0, mô hình sẽ linh hoạt hơn bằng cách bỏ ràng buộc quan hệ giữa input và output là phải luôn đi qua gốc tọa độ O. Đại lượng W0 được gọi là bias.
Kỹ thuật thêm 1 đặc trưng bằng 1 vào vector đặc trưng và ghép bias b vào vector hệ số w được gọi là bias trick. 

--  

&ensp;Linear Regression often mentioned a more little bit complex relation when it has a free parameter W0( be also called b in some materials ).
This relation is called affine.
* If W0 == 0, the regression line ưill usually cross through the origin.
* If W0 != 0, the model will be more flexible by removing the constraint relationship between features input and predicted output. The quantity W0 is called bias.
The technique of adding one feature whose value is one and concatenate bias b to parameters vector w is called the bias trick.

### Xây dựng hàm mất mát và tối ưu - Build a Loss Function and optimize.
#### *Loss Function*

&ensp;Điều ta mong muốn khi xây dựng mô hình là kết quả dự đoán sẽ có sai lệch nhỏ nhất so với grouth-truth. Hàm mất mát được xây dựng nhằm đánh giá sai số đó. Hàm mất mát được xây dựng như sau:  

<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;L_w&space;=&space;\frac{1}{2N}\sum_{i=1}^{N}(y-\hat{y})^2" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;L_w&space;=&space;\frac{1}{2N}\sum_{i=1}^{N}(y-\hat{y})^2" title="L_w = \frac{1}{2N}\sum_{i=1}^{N}(y-\hat{y})^2" /></a>

Hàm loss này được gọi là *mean squared error* (MSE). Trong đó:
* N: tổng số điểm dữ liệu
* y: grouth-truth
* \hat{y}: kết quả dự đoán.

--

&ensp; When building a linear regression model, the goal that we want is to minimize the difference between grouth-truth and predicted output. So, a loss function is built for measuring it. Formulation:  
<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;L_w&space;=&space;\frac{1}{2N}\sum_{i=1}^{N}(y-\hat{y})^2" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;L_w&space;=&space;\frac{1}{2N}\sum_{i=1}^{N}(y-\hat{y})^2" title="L_w = \frac{1}{2N}\sum_{i=1}^{N}(y-\hat{y})^2" /></a>

This loss is called *mean squared error (MSE)*. Which:
* N: total data points
* y: grouth-truth
* \hat{y}: predicted output

#### *Optimization*

&ensp; Bài toán tối ưu hóa ở đây là tối ưu hàm mất mát. Mục đích của tối ưu hàm mất mát là điều chỉnh các tham số trong vector tham số để giá trị dự đoán sai lệch ít nhất so với grouth-truth. Thông thường, Gradient Descent được sử dụng để điều chỉnh tham số.

---

The optimize problem is minimizing the value of the loss function. The goal of that is fitting parameters in the parameter vector to have the smallest difference between predicted output and griuth-truth. In general, Gradient Descent is used to fitting parameters.

### Cài đặt mô hình Linear Regression
#### Cài đặt từ đầu

* Dataset

```python

```