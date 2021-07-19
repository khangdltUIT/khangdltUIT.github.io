---
layout: post
tittle: LINEAR REGRESSION IN MACHINE LEARNING
categories: ML
---

## 1. Giới thiệu - Introduction
&ensp; Hồi quy tuyến tính là mô hình mở đầu cho nhiều khóa học về Machine Learning bởi vì tính đơn giản và dễ hiểu của nó.  
&ensp; Hồi quy tuyến tính thuộc loại mô hình học tập có giám sát ( *supervised learning*), được sử dụng trong các bài toán về hồi quy.
&ensp; Ngoài ra, mô hình được ứng dụng rộng rãi trong cuộc sống như: dự báo thời tiết, giá nhà, ... và còn có thể ứng dụng trong Feature Selection do có thể đánh giá được mối liên hệ giữa thuộc tính và kết quả dự đoán.

## 2. Mô hình Linear Regression trong Machine Learning

### Biểu diễn mô hình - Model Representation
&ensp; Đầu tiên, hồi quy tuyến tính là mô hình trực quan bởi vì cách biểu diễn của nó rất đơn giản.  
&ensp; Một hàm tuyến tính sẽ đại diện cho mô hình kết hợp các dặc trưng ( features) đầu vào để dự đoán đầu ra. Kiểu dữ liệu của chúng đều là số thực. 

&ensp; Công thức:

<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;Y&space;=&space;W_0&space;&plus;&space;W_1\cdot&space;X" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;Y&space;=&space;W_0&space;&plus;&space;W_1\cdot&space;X" title="Y = W_0 + W_1\cdot X" /></a>

&ensp;Tuy nhiên trong các bài toán thực tế, các đặc trưng trong bộ dữ liệu có thể tăng lên đến cả hàng chục thuộc tính. Do đó, W1 có thể được hiểu là một vectơ tham số như sau: W1 = [W1,W2,..Wn]. Tương tự cho vectơ đặc trưng X.

Mô hình có thể biểu diễn lại như sau:  

<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;Y&space;=&space;\begin{bmatrix}&space;W_0\\&space;W_1\\&space;...\\&space;W_n\\&space;\end{bmatrix}&space;\cdot&space;\begin{bmatrix}&space;1\\&space;X_1\\&space;...\\&space;X_n\\&space;\end{bmatrix}&space;=&space;W^{T}\cdot&space;X" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;Y&space;=&space;\begin{bmatrix}&space;W_0\\&space;W_1\\&space;...\\&space;W_n\\&space;\end{bmatrix}&space;\cdot&space;\begin{bmatrix}&space;1\\&space;X_1\\&space;...\\&space;X_n\\&space;\end{bmatrix}&space;=&space;W^{T}\cdot&space;X" title="Y = \begin{bmatrix} W_0\\ W_1\\ ...\\ W_n\\ \end{bmatrix} \cdot \begin{bmatrix} 1\\ X_1\\ ...\\ X_n\\ \end{bmatrix} = W^{T}\cdot X" />

* Nếu W0 == 0, đường thẳng y luôn đi qua gốc tọa độ.
* Nếu W0 != 0, mô hình sẽ linh hoạt hơn bằng cách bỏ ràng buộc quan hệ giữa input và output là phải luôn đi qua gốc tọa độ O. Đại lượng W0 được gọi là bias.
Kỹ thuật thêm 1 đặc trưng bằng 1 vào vector đặc trưng và ghép bias b vào vector hệ số w được gọi là bias trick. 

### Xây dựng hàm mất mát và tối ưu - Build a Loss Function and optimize.
#### *Loss Function*

&ensp;Điều ta mong muốn khi xây dựng mô hình là kết quả dự đoán sẽ có sai lệch nhỏ nhất so với groundtruth. Hàm mất mát được xây dựng nhằm đánh giá sai số đó. Hàm mất mát được xây dựng như sau:  

<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;L_w&space;=&space;\frac{1}{2N}\sum_{i=1}^{N}(y-\hat{y})^2" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;L_w&space;=&space;\frac{1}{2N}\sum_{i=1}^{N}(y-\hat{y})^2" title="L_w = \frac{1}{2N}\sum_{i=1}^{N}(y-\hat{y})^2" /></a>

Hàm loss này được gọi là *mean squared error* (MSE). Trong đó:
* N: tổng số điểm dữ liệu
* y: groundtruth
* \hat{y}: kết quả dự đoán.
#### *Optimization*

&ensp; Bài toán tối ưu hóa ở đây là tối ưu hàm mất mát. Mục đích của tối ưu hàm mất mát là điều chỉnh các tham số trong vector tham số để giá trị dự đoán sai lệch ít nhất so với groundtruth. Thông thường, Gradient Descent được sử dụng để điều chỉnh tham số.


### Cài đặt mô hình Linear Regression
#### Không sử dụng thư viện - from scratch

* Dataset  
Dữ liệu được định nghĩa như sau:  
    * X: chiều cao (cm)  
    * y: cân nặng (kg)

```python
# height (cm)
X = np.array([[147, 150, 153, 158, 163, 165, 168, 170, 173, 175, 178, 180, 183]]).T # each row is a point 
# weight (kg)
y = np.array([ 49, 50, 51,  54, 58, 59, 60, 62, 63, 64, 66, 67, 68])
```
* Cài đặt hàm Linear Regression:

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
