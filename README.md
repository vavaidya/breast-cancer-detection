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

## METHOD
In the first stage deep CNNs, trained on large and general datasets like ImageNet (10M images, 20K classes), are used for unsupervised feature extraction. This unsupervised dimensionality reduction step mitigates the risk of overfitting in the next stage of supervised learning.

In the second stage we use [LightGBM](https://lightgbm.readthedocs.io/en/latest/) as a fast, distributed, high performance implementation of gradient boosted trees for supervised classification. Gradient boosting models are being extensively used in machine learning due to their speed, accuracy, and robustness against overfitting.

## RESULTS
For 2-class non-carcinomas (normal and benign) vs. carcinomas (in situ and invasive) classification accuracy was 93.8 ± 2.3%, the area under the ROC curve was 0.973. Out of 200 carcinomas cases only 9 in situ and 5 invasive were missed. For 4-class classification accuracy averaged across all folds was 87.2 ± 2.6%.

## REPOSITORY DETAILS
1. [Edge Detection of Cells](https://github.com/vavaidya/breast-cancer-detection/blob/master/Edge%20Detection%20and%20Hough%20Circle.ipynb)
2. [CNN Feature Extractor](https://github.com/vavaidya/breast-cancer-detection/blob/master/ICIAR2018/feature_extractor.py)
3. [Light GBM](https://github.com/vavaidya/breast-cancer-detection/blob/master/ICIAR2018/train_lgbm.py)
