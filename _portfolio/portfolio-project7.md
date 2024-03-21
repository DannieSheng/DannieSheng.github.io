---
title: "Enhanced Detection and Classification of Cell Nuclei in H&E Stained Pathology Images Using Mask R-CNN"
excerpt: "October 2021 ~ December 2021<br/>This project focused on the application of Mask R-CNN, a state-of-the-art model for instance segmentation tasks, to detect and classify common types of cell nuclei in H&E (Hematoxylin and Eosin) stained pathology images of Non-Small Cell Lung Cancer (NSCLC) and Breast Cancer. 
By leveraging transfer learning and customizing the loss function of Mask R-CNN, the project aimed to address the challenges posed by incomplete labeling in the dataset and improve the model's performance in both detection and classification tasks. <br/>"
collection: portfolio
---

Key Achievements
======

Model Adaptation
------

Started with an existing Keras-based Mask R-CNN model designed for detecting six common types of cell nuclei in NSCLC (
Non-small cell lung cancers) pathology images. Through transfer learning, the model was fine-tuned to detect and classify seven common types of cell nuclei in breast cancer pathology images, achieving simultaneous segmentation and classification.

Data Labeling Challenge
------

Faced with a dataset where approximately 20% of the samples had incomplete labels—missing either the class labels (`unlabeled`) or the pixel-level mask labels—direct training was not feasible without addressing the issue.

Loss Function Redesign
------

Successfully redesigned the Mask R-CNN's loss function to selectively ignore samples with missing labels during the computation of losses. Specifically, samples lacking classification labels were excluded from classification loss calculations, and those missing mask labels were not considered in mask loss calculations.

Performance
------

The modified Mask R-CNN model, now based on the PyTorch framework, demonstrated a detection rate of 82.5% and a 7-class classification accuracy of 82.0% for breast cancer cell nuclei in H&E stained pathology images.

Why Mask R-CNN?
------
1. Precision in Instance Segmentation: 
Mask R-CNN is renowned for its high precision and accuracy in instance segmentation tasks, crucial for accurately locating and segmenting cell nuclei in tumor pathology.
2. Detailed Object Masks: 
Beyond detecting object boundaries, Mask R-CNN generates detailed instance masks, providing valuable insights into the shape and structure of tumor cell nuclei.
3. Flexibility and Customizability: The PyTorch-based implementation of Mask R-CNN offers the flexibility needed to tailor the model to specific requirements, making it ideal for handling tumor cell nuclei of varying shapes, sizes, and densities.
4. Community Support: 
Mask R-CNN benefits from extensive community support, including a wealth of resources, documentation, and pre-trained models, facilitating the development process and accelerating model training and optimization.

Conclusion
======
This project showcases the potential of advanced machine learning models like Mask R-CNN in enhancing the detection and classification of cell nuclei in pathology images, contributing to more accurate and efficient diagnostic processes in oncology.

