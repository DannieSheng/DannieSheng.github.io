---
title: 'Object Detection Algorithms'
date: 2024-03-06
permalink: /posts/2024/03/object-detection-algorithms/
tags:
  - learning notes
  - deep learning
  - computer vision
  - AI
---

A summary of object detection algorithms

Faster R-CNN
======

It combines RPN (Region Proposal Network) and CNN (Convolutional Neural Network) for object classificaion and bounding box regression

### Important notes
1. RPN  
A fully convolutional network that simultaneously predicts object bounds and objectness scores at each position. 
    1. Generating region proposals by sliding a small window over the original image. 
    2. Anchor Boxes: At each sliding-window location, the RPN generates multiple region proposals simultaneously. 
    It does this by predicting multiple bounding boxes and their objectness scores. These bounding boxes are called "anchors." 
    Anchors are *predefined* and are of different scales and aspect ratios to ensure coverage of various object sizes and shapes.
    3. Bounding Box Regression and Classification: For each anchor, the RPN predicts two sets of values:
        - Bounding box regression adjustments: These values adjust the anchors to better fit potential objects.
        - Objectness scores: These scores indicate how likely each adjusted anchor is to contain an object.
    4. Non-Maximum Suppression (NMS): Since many anchors can overlap significantly, leading to multiple proposals for the same object, NMS is applied to reduce redundancy. It does this by keeping only the proposals with the highest objectness scores while removing others that have a high overlap (measured by Intersection over Union, IoU) with these top proposals.

2. ROI Pooling   
Efficiently extract **fixed-size** feature vectors from the variable-sized regions proposed by the Region Proposal Network (RPN). These fixed-size feature vectors are then used for classifying the regions into specific object categories and for refining their bounding box coordinates.

3. Object Classification and Bounding Box Regression  
Fully connected layer

### Loss Function
- Classification loss (cross entropy loss)
$$L_{cls} = -\frac{1}{N_{cls}}\sum_{i=1}^{N_{cls}}[y_ilog(p_i)+[(1-y_i)log(1-p_i)]$$
- Bounding box regression loss (smooth L1 loss)
$$L_{reg} = \frac{1}{N_{reg}}\sum_{i=1}^{N_{reg}}L_{smooth}(t_i-t_{i}^{*})$$
- Loss from the RPN
  - Classification loss:
  $$L_{cls}^{rpn} = -\frac{1}{N_{cls}}\sum_{i}[p_ilog(\hat{p_i})+(1-p_i)log(1-\hat{p_i})]$$
  - Bounding box regression loss
  $$L_{reg}^{rpn} = \frac{1}{N_{reg}}\sum_ismooth_{L1}(t_i-\hat{t_i})$$

Mask R-CNN
======
### Important notes
It extends and improves faster R-CNN by 
1) Replacing ROI pooling by ROI align to improve precision
2) Including segmentation mask for each object

### Loss Function
- Mask loss:
$$L_{mask} = -\frac{1}{N_{mask}}\sum_{i}\sum_{p}(m_{i,p}log(\hat{m_{i,p}})+(1-m_{i,p})log(1-\hat{m_{i,p}}))$$

YOLO
======
It a real-time object detection algorithm that transforms the task of object detection into a single end-to-end convolutional neural network (CNN) model. 
### Important notes
1. Grid search:  
The input images are splitted into fixed size grids and predictions are made for each grid
2. Single shot:  

3. Multi-size prediction:  
Different levels of feature maps

### Loss Function
- Classification loss
$$L_{cls} = -\frac{1}{N_{obj}}\sum_{i=1}^{N_{obj}}\sum_{c\in classes}y_{i,c}log(\hat{y_{i,c}})$$
$N_{obj}$ is the number of grids. 
- Bounding box regression loss 
$$L_{box} = \frac{1}{N_{obj}}\sum_{i=1}^{N_{obj}}\sum_{j=1}^{B}\mathbf{1}_{ij}^{obj}[(x_i-\hat{x_i})^2
+(y_i-\hat{y_i})^2
+(\sqrt{w_i}-\sqrt{\hat{w_i}})^2
+(\sqrt{h_i}-\sqrt{\hat{h_i}})^2]$$
where  
$B$: number of bbox in each grid  
$\mathbf{1}_{ij}$: an indicator function that shows whether the j-th bbox in the i-th grid has object detected  
$x_i$, $y_i$, $w_i$, $h_i$ represent for the location and size of predicted bboxes (ground-truth)  
$\hat{x_i}$, $\hat{y_i}$, $\hat{w_i}$, $\hat{h_i}$ represent for the location and size of predicted bboxes (predicted)


SSD (Single Shot MultiBox Detector)
======

RetinaNet
======

EfficientDet
======

Cascade R-CNN
======

CenterNet
======

DETR (Detection Transformer)
======

HRNet (High-Resolution Network)

------