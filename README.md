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
