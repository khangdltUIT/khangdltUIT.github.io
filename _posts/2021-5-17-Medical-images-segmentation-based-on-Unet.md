---
layout: post
tittle: Medical images segmentation based on Unet
categories: CV
---

Bài viết trình bày chi tiết và giải thích về các phương pháp đã áp dụng để xử lí bài toán "Brain Tumor Segmentation". 

------------------------------

The blog describes details and explains about methods implemented to solve the problem " Brain Tumor Segmentation".

## 1. Tổng quan - Abstract  
Gần đây, số bài báo nghiên cứu trong lĩnh vực xử lý ảnh y sinh đang tăng cao cho thấy sự thu hút trong lĩnh vực này. Sự phát triển ấy nhanh đến nỗi mọi người đã đặt ra câu hỏi " Bác sĩ chẩn đoán có còn cần thiết nữa hay không ?". Một trong các bài toán đang được nghiên cứu là phân đoạn ảnh y sinh, với mục đích là giúp xác định chính xác các khối u trong cơ thể trên từng pixel. Bài toán này được tôi áp dụng đầy đủ các bước xử lý từ tiền xử lý (skull-stripping) , áp dụng mô hình phân đoạn (unet và uent++) cho đến hậu xử lý(removing small holes). Sau cùng, tổng kết và thống kê các hàm mất mát hiệu quả như thế nào đối với bài toán này. 

-----

Nowadays, numerous papers in medical images processing increased dramatically shows that it is an interesting area. This improvement is high enough for people to ask a question "Do we need diagnostic doctors ?". One of many problems in this field is the segmentation of medical images, with aiming to detect more accurate tumors over pixels. My project was implemented full steps from image preprocessing, selected segmentation models to image post-processing. Finally, we summary and statistical loss functions to know how they affected the segmentation model.  
## 2. Giới thiệu - Introduction  

## 3. Bài toán Segmentation - Segmentation Problem

## 3. Dữ liệu - Dataset

## 4. Phương pháp - Methods
### 4.1 Tiền xử lí - Preprocessing
### 4.2 Mô hình phân đoạn - Segmentation Model
### 4.3 Hậu xử lí - Post-processing