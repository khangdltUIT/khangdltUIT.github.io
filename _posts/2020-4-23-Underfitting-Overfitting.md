---
layout: post
categories: Machine
tittle: Overfitting
--- 
# &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp; Overfitting in Machine Learning
## &ensp;&ensp;&ensp;&ensp; Tổng quan
Overfitting là hiện tượng không mong muốn thường gặp trong quá trình xử lý model.
### Giới thiệu
Trong xử lý bài toán, ta sẽ mặc nhiên đi tìm một mô hình phù hợp với dữ liệu đầu vào. Và trong trường hợp này thì overfitting xảy ra, một model quá fit với dữ liệu -> *bạn sẽ cho rằng điều đó tốt cho model ?*

Câu trả lời sẽ là **Không**. Thực tế 1 model quá fit với dữ liệu training set có thể không biểu diễn tốt đữ liệu không được hiển thị. Model tốt phải có tính **TỔNG QUÁT(GENERALIZATION)**
 
 Theo đa thức nội suy Lagrange. Với N cặp điểm dữ liệu 
<a href="https://www.codecogs.com/eqnedit.php?latex=(x_{1},y_{1}),&space;(x_{2},y_{2}),&space;...,&space;(x_{n},y_{2})" target="_blank"><img src="https://latex.codecogs.com/gif.latex?(x_{1},y_{1}),&space;(x_{2},y_{2}),&space;...,&space;(x_{n},y_{2})" title="(x_{1},y_{1}), (x_{2},y_{2}), ..., (x_{n},y_{2})" /></a>
với các cặp xi khác nhau đôi một luôn tìm được một đa thức P() bậc không vượt quá N-1 sao cho 
<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;P(x_{i})&space;=&space;y_{i},&space;\forall&space;i&space;=&space;1,2,...,n" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;P(x_{i})&space;=&space;y_{i},&space;\forall&space;i&space;=&space;1,2,...,n" title="P(x_{i}) = y_{i}, \forall i = 1,2,...,n" /></a>

![alt](https://res.cloudinary.com/dominhhai/image/upload/ml/sin2pi.png)

1) Underfitting

2) Fit

3) Overfitting
 
Với loại dữ liệu này ta có thể áp dụng polynomial regression với feature vector là 
<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;X&space;=&space;[1,&space;x,&space;x^{2},&space;x^{3},&space;...,&space;x^{d}]^{T}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;X&space;=&space;[1,&space;x,&space;x^{2},&space;x^{3},&space;...,&space;x^{d}]^{T}" title="X = [1, x, x^{2}, x^{3}, ..., x^{d}]^{T}" /></a>

Với một đa thức bật không vượt quá (N-1) có thể fit được hoàn toàn với N điểm trong tập training set. Xét các giá trị như trong hình trên với d = 1, 3, 15.

* Với d=1, model không thực sự tốt vì predicted model quá khác so với true model, thậm chí nó có xu hướng đi xuống trong khi dữ liệu có xu hướng đi lên --> ***underfitting***

* Với d=15, model quá fit với training set. Việc quá fit trong trường hợp 16 là không tốt vì mô hình đang cố gắng mô tả nhiễu --> ***overfitting***

* Với d=4, mô hình dự đoán khá giống với mô hình thực.

Overfitting sẽ làm cho model chỉ chú trọng vào training set mà quên đi tính generalization --> mô hình không thực sự mô tả tốt dữ liệu ngoài training set.

 &ensp;Đây là hình ảnh minh họa việc overfitting ảnh hướng đến kết quả bài toán
 
 ![alt](https://i.imgur.com/2q85n9s.png)

## &ensp;&ensp;&ensp;&ensp;  KỸ THUẬT GIẢI QUYẾT
### Đánh giá
Ta cần một vài đại lượng để kiểm tra chất lượng của model trên trainning set và test set. 

y: đầu ra thực sự(có thể là vector)
<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\hat{y}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;\hat{y}" title="\hat{y}" /></a>
:đầu ra dự đoán bởi mô hình


* **Trainning error**: Đại lượng này là mức độ sai khác giữa y(đầu ra thực sự) và <a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\hat{y}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;\hat{y}" title="\hat{y}" /></a> (đầu ra dự đoán) thường là giá trị của loss function áp dụng lên model.
    * Bài toán regression, đại lượng này xác định bởi **mean squared error(MSE)**
    * Bài toán classification, trung bình cộng của **cross entropy loss**(với softmax regression) hoặc **hinge loss** (với multi class SVM)
* **Test error**: tương tự với tranning error nhưng được áp dụng vào test set

Một mô hình được xem là fit nếu cả *test error* và *tranning error* đều **thấp**. 
* Nếu test error cao và tranning error thấp -> overfitting.
* Nếu test error cao và tranning error cao -> underfitting.
* Trường hợp test error thấp trong khi tranning error cao có xác suất xảy ra rất thấp.

Có 2 kỹ thuật giúp giải quyết vấn đề này là 
1. Validation
2. Regularization
