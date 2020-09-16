---
layout: post
tittle: Object Recognition
categories: Computer Vision
---

## *Recap Object Localization*  
In computer vision tasks, we have 3 main tasks:  
*   Image Classification: assigning a class label to an image.  
*   Object Localization: drawing a bounding box around one or more objects in image.  
*   Object Detection: drawing a bounding box each object of interest in the image and assigning them a class label.  

Together, all of these problem referred to as object recognition.  
Additionally, one extension of computer vision tasks is object segmentation which is more challenging (also called "object instance segmentation" or "semantic segmentation"). In this task, we highlight the specific pixels of the object instead of drawing a bounding box.  

<img src="https://3qeqpr26caki16dnhd19sv6by6v-wpengine.netdna-ssl.com/wp-content/uploads/2019/05/Object-Recognition.png" alt="Overview" title="Overview of computer vision tasks" width="500" height="300" />  

### **1. Boungding Box**  
&ensp; In both object detection and localization tasks, we use a bounding box to describe object existing in image. A bounding box is a rectangular box which could be determined by x,y axis coordinates in the upper-left or lower-right in the rectangular box. Another way, we could define as x, y, w, h.
&ensp; In object detection, we not only draw a bounding box, but also assign object a class label. This is a major difference between Detection and Localization.  

#### **Evaluating via boungding box.**  

*Do you think about the measure to evaluate the performance of model?*  
&ensp; To begin with, we could use MCE ( mean classification error ) across the predicted class labels in order to evaluate the preformance of model with image classification tasks. 
&ensp; Regarding object localization, the performance of model is evaluated by using the *distance between the expected and predicted bounding box* for the expected class.  
&ensp; In the case of Object Detection ( Object Recognition), using both precision and recall across each of best matching bounding boxes.

### **2. Using CNN in Object Localization**
Pipeline of this method:  
1. Pre-trained model ( namely VGG16, Resnet50, DenseNet121,...) to classified class of object
2. Using a custom layer called "Region of Interest Pooling Layer" extracts specific feature for a given input candidate region
3. The output of model is then interpreted by a FCL (fully connected layer) then model birfucates into two outputs, one for class prediction, another with linear output for the bounding box. 

This architecture is often called "R-CNN".

<img src="https://3qeqpr26caki16dnhd19sv6by6v-wpengine.netdna-ssl.com/wp-content/uploads/2019/03/Summary-of-the-Fast-R-CNN-Model-Architecture.png" alt="overview" title = "Summarized(taken from paper Fast-RCNN" width="800" height="200" />  

