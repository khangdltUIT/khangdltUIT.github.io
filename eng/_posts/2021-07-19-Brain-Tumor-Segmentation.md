---
layout: post
tittle: BRAIN TUMOR SEGMENTATION
categories: CV
---

This is the final project that I have finished in my Advanced Computer Vision Course. It concludes 3 parts following to the pipeline: pre-processing, the segmentation model and post-processing.

## **1. Introduction**
### **1.1 Segmentation Tasks**

The Object Segmentation problem and the Object Detection problem in the field of Computer vision both have the same common purpose to detect the area containing the object. object in the image and predict the label of the object in that area, however, Image Segmentation requires more detail than Object Detection, if for Object Detection problem we only need to predict the Bounding box including the Bounding box. around objects and their classes, in Image Segmentation, we need to predict and classify at the pixel level of each object (does that pixel belong to the object's container, and what object it is) and returns a mask representing the object.

### **1.2 Brain Tumor Segmentation**

Glioma (English name is Glioma) is a tumor that occurs in the brain and spinal cord. This glioma originates from supporting adhesion cells (glial cells) - the type of cells that surround nerves and help them carry out their functions.  

A new direction in cancer research, called radiogenomics, is aimed at finding relationships and associations between tumor genomic characteristics and medical imaging. Recent studies have found an association between tumor shape features extracted from MRI images and its dependent genotypes. However, the extraction of tumor shape features through manual MRI images is time-consuming and expensive, and each feature extractor will give different results. With the advancement of science, deep learning methods in recent times have been able to analyze images, and this achievement has greatly contributed to the analysis of medical images. economic. And being able to find tumor areas in the human brain using Deep learning methods is already possible and can be achieved with a quite high accuracy like medical imaging specialists.

So, a system of automatic predicting a tumor in medical images could save time, cost, and doctors. 

## **2. Dataset**
![alt](https://raw.githubusercontent.com/tuongkhangduongle/tuongkhangduongle.github.io/master/images/brain_tumor/dataset.png)
We used the dataset from a paper "Association of genomic subtypes of lower-grade gliomas with shape features automatically extracted by a deep learning algorithm.". The Dataset is confirmed by doctors at Duke University.

The total samples of the dataset are 3929, but 1373 is the number of samples labeled. So, we could see the high imbalance, a popular problem in medical datasets. However, this is the segmentation task, we just need masks labeled. Therefore, we selected 1373 samples labeled and split into 3 sets which are: train - validation and test with the rate are: 0.7 - 0.15 - 0.15.
![alt](https://raw.githubusercontent.com/tuongkhangduongle/tuongkhangduongle.github.io/master/images/brain_tumor/data_distribute.png)
## **3. Preprocessing**
We combined 2 methods that are skull-stripping and image processing.

### **3.1 Skull-stripping**
Skull-stripping is the high preprocessing part of brain tumor tasks. Because we have just predicted a tumor, the features of the skull are not important, and they could cause noise in the training phase. So, removing the skull could increase the model performance.  

We used this pretrained [model]() to do the first preprocessing. We did not train or fine-tuning it, just applying the model which is trained by authors to the dataset for the aiming of skull-stripping.