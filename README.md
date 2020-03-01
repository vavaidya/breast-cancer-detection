# breast-cancer-detection
Attempt at the [ICIAR 2018 Challenge Data](https://iciar2018-challenge.grand-challenge.org/)

This work, is an attempt to delve deeper into Deep Convolution Neural Nets and Image Classification.

## REFERENCE PAPER READ
Rakhlin, A., Shvets, A., Iglovikov, V., Kalinin, A.: Deep Convolutional Neural Networks for Breast Cancer Histology Image Analysis. arXiv:1802.00752 [cs.CV], [link](https://arxiv.org/abs/1802.00752)

## INTRODUCTION
Breast cancer is one of the main causes of cancer death worldwide. Early diagnostics significantly increases the chances of correct treatment and survival, but this process is tedious and often leads to a disagreement between pathologists. Computer-aided diagnosis systems showed potential for improving the diagnostic accuracy. Through this challenge, we tried understanding the computational approach based on deep convolution neural networks for breast cancer histology image classification. Hematoxylin and eosin stained breast histology microscopy image dataset is provided as a part of the ICIAR Grand Challenge on Breast Cancer Histology Images.

## DATA
The image dataset consists of 400 H&E stain images (2048 × 1536 pixels). All the images are digitized with the same acquisition conditions, with a magnification of 200 × and pixel size of 0.42 µm × 0.42 µm. Each image is labeled with one of the four balanced classes: *normal, benign, in situ, and invasive*, where class is defined as a predominant cancer type in the image.
![classes](https://github.com/vavaidya/breast-cancer-detection/blob/master/class_example.png)
Examples of microscopic biopsy images in the dataset: (A) normal; (B) benign; (C) in situ carcinoma; and (D) invasive carcinoma

## PRE-PROCESSING AND FEATURE EXTRACTION
To bring the microscopy images into a common space, the amount of H&E stained on the tissue is normalised. For each image, 50 random color augmentations are performed. From every image 20 random crops extracted and encoded into 20 descriptors. Then, the set of 20 descriptors is combined into a single descriptor. For features extraction, standard pre-trained ResNet-50, InceptionV3 and VGG-16 networks are used from Keras distribution.
![preprocessing](https://github.com/vavaidya/breast-cancer-detection/blob/master/Preprocessing_pipeline.png)
