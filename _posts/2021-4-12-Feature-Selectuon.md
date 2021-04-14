---
layout: post
tittle: Feature Selection
categories: Machine_Learning
---
# Mục đích của Feature Selection
Mục đích của việc áp dụng các kỹ thuật feature selection nhằm tìm ra tập các đặc trưng để xây dựng một mô hình hiệu quả.
The goal of using feature selection is to find the best set of features which build a useful model.
# Phân loại:
1. Supervised Techniques:
*   Áp dụng cho các dữ liệu đã được gán nhãn và có thể nhận ra sự tương quan giữa các đặc trưng nhằm tăng độ chính xác của mô hình học có giám sát như phân loại và hồi quy
These techniques can be used for labeled data, and could identify relevant features of increasing efficient of supervised model like classification and regression.
2. Unsupervised Techniques:
*   Áp dụng cho dữ liệu không gán nhãn
These techniques can be used for unlabeled data.

![alt](https://raw.githubusercontent.com/khangdltUIT/khangdltUIT.github.io/master/images/Overview-of-Feature-Selection-Techniques3.webp
)

Tuy nhiên, người ta thường chia các cách tiếp cận trong Feature selection thành 2 hướng:

* Wrapper
* Filter

Những năm gần đây, thì xuất hiện thêm 2 hướng nữa là:

* Combined (or Hybrid)
* Embedded

3. Sự khác nhau giữa Filter và Wrapper - Differences between filter and wrapper methods:

Sự khác nhau chính giữa 2 phương pháp này là:
* Filter đo về sự tương quan giữa các đặc trưng, trong khi Wrapper đo bằng cách huấn luyện tập dữ liệu trên tập các đặc trưng.
* Filter nhanh hơn so với wrapper do nó không thực hiện huấn luyện mô hình. Bên cạnh đó, Wrapper tốn nhiều tài nguyên tính toán.
* Filter sử dụng thống kê để đánh giá độ tương quan giữa các đặc trưng trong khi Wrapper đánh giá dựa trên cross validation.
* Filter có thể không chọn ra được tập các đặc trưng tốt nhất trong khi wrapper chọn ra được tập đặc trưng tốt nhất.
* Sử dụng tập đặc trưng của Wrapper có thể dẫn đến tình trạng overfitting hơn là sử dụng tập đặc trưng của filter.

The main diffence between both methods are:
* Filter method measures the relevance of features, while Wrapper method mesures by training the data on subset of fetures and then select it.
* Filter method is faster than the other method as filter method not select subset of feature from training model.Futhermore, wrapper method could use more resource for computation.
* Filter method use statiscal to measure the relevance of features, while wrapper method use cross-validation.
* Filter could find the best subset of feature, but wrapper method always provide the best subset features.
* As the consequence, using the subset features provided by wrapper method might be lead to overfitting.

# Thuật toán Genetic Algorithms

