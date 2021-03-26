---
layout: post
tittle: VinBigData Chest X-ray
categories: Computer_Vision
---

![alt](https://raw.githubusercontent.com/khangdltUIT/khangdltUIT.github.io/master/images/header_vinchest.png)

# 1. Tóm tắt
Blog sẽ giới thiệu về bài toán trong cuộc thi trên kaggle: Vin BigData Chest X-ray. Trong blog lần này, mình sẽ giới thiệu về bộ dữ liệu do Vin cung cấp, đồng thời áp dụng các mô hình detection dựa trên deep learning và phân tích độ hiệu quả của các mô hình với bộ dữ liệu này. 
# 2. Vin BigData Chest X-ray Dataset
## 2.1 Thông tin bộ dữ liệu
Bộ dữ liệu gồm khoảng 68000 ảnh theo khuôn mẫu DICOM, với danh tính bệnh nhân được ẩn đi nhằm mục đích bảo mật danh tính của bệnh nhân. Các nhãn trong ảnh được gán bởi các bác sĩ chẩn đoán có nhiều kinh nghiệm. Tổng số nhãn trong bộ dữ liệu:
0 - Aortic enlargement
1 - Atelectasis
2 - Calcification
3 - Cardiomegaly
4 - Consolidation
5 - ILD
6 - Infiltration
7 - Lung Opacity
8 - Nodule/Mass
9 - Other lesion
10 - Pleural effusion
11 - Pleural thickening
12 - Pneumothorax
13 - Pulmonary fibrosis

Bên cạnh đó nhãn "No finding" được gán cho những ảnh không tồn tại những dấu hiệu của 14 nhãn trên.
## 2.2 Thống kê bộ dữ liệu

![alt](https://raw.githubusercontent.com/khangdltUIT/khangdltUIT.github.io/master/images/statiscal_label_vinbd_chest.png)

Có thể thấy bộ dữ liệu mất cân bằng nghiêm trọng. Nhãn 14 - "No finding" chiếm lượng lớn trong bộ dữ liệu với hơn 30000 mẫu, trong khi đó nhãn 12 - "Pneumothorax" lại chiếm lượng rất ít. Điều nãy dẫn đến hiệu quả của mô hình kém. 
**Nhận xét:** Có thể áp dụng các phương pháp như *cross-validation* trong quá trình đánh giá mô hình để có thể chọn được mô hình phù hợp, đồng thời trong quá trình training có thể thực hiện các phương pháp như *data augmentation*
