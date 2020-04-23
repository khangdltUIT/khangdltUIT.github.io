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
 
 Theo đa thức nội suy Lagrange. Với N cặp điểm dữ liệu (x_{1}, y_{1})
