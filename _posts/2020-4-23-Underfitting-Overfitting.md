---
layout: Machine Learning
tittle: Underfitting and Overfitting
--- 
## Tổng quan
Overfitting là hiện tượng không mong muốn thường gặp trong quá trình xử lý model.
### Giới thiệu
Trong xử lý bài toán, ta sẽ mặc nhiên đi tìm một mô hình phù hợp với dữ liệu đầu vào. Và trong trường hợp này thì overfitting xảy ra, một model quá fit với dữ liệu -> *bạn sẽ cho rằng điều đó tốt cho model ?*

Câu trả lời sẽ là **Không**. Thực tế 1 model quá fit với dữ liệu training set có thể không biểu diễn tốt đữ liệu không được hiển thị. Model tốt phải có tính **TỔNG QUÁT(GENERALIZATION)**

![alt](https://res.cloudinary.com/dominhhai/image/upload/ml/sin2pi.png)
 
 Theo đa thức nội suy Lagrange. Với N cặp điểm dữ liệu <a href = "https://www.codecogs.com/eqnedit.php?latex=\inline&space;h_\theta&space;(x)&space;=&space;\theta_1x_1&space;+&space;\theta_2x_2&space;+&space;\theta_3x_1x_2&space;+&space;\theta_4x_1^2&space;=&space;\begin{bmatrix}\theta_1&space;\&space;\theta_2&space;\&space;\theta_3&space;\&space;\theta_4&space;\end{bmatrix}&space;\begin{bmatrix}&space;x_1\\&space;x_2&space;\\x_1x_2&space;\\x_1^2&space;\end{bmatrix}&space;=&space;\theta^TX"/></a>
