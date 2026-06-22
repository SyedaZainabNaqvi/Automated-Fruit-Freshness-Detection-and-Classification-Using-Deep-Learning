# Automated Fruit Freshness Detection and Classification Using Deep Learning

This project implements an automated fruit freshness classification system using deep learning techniques. The system classifies fruit images into six categories: fresh apples, fresh bananas, fresh oranges, rotten apples, rotten bananas, and rotten oranges.

The main goal of this project is to support automated fruit quality assessment using image classification, which can be useful in agriculture, supermarkets, warehouses, and food quality monitoring systems.

## Project Overview

Manual fruit inspection is time-consuming, subjective, and prone to human error. This project uses computer vision and deep learning to automatically identify whether a fruit is fresh or rotten from an image.

Three deep learning architectures were implemented and compared:

* Custom CNN
* ResNet-50 Transfer Learning
* CNN + Transformer Hybrid Model

The CNN-Transformer model achieved the best performance with 99.73% test accuracy.

## Dataset

The dataset contains images of fresh and rotten fruits. It includes three fruit types in both fresh and rotten conditions.

### Classes

* freshapples
* freshbanana
* freshoranges
* rottenapples
* rottenbanana
* rottenoranges

The dataset was split into training, validation, and testing sets using a 70-20-10 stratified split to preserve class distribution.

## Data Preprocessing

The preprocessing pipeline includes:

* Image resizing to 224 × 224 pixels
* Pixel normalization from 0-255 to 0-1
* Class imbalance detection
* Balanced class weight computation
* Data augmentation
* Train, validation, and test splitting
* Final batch verification

Data augmentation was applied using transformations such as rotation, zoom, shifting, flipping, and brightness variation to improve model generalization.

## Models Implemented

### 1. Custom CNN

A baseline Convolutional Neural Network was designed using multiple convolutional blocks with batch normalization, max pooling, dropout, and a softmax classification layer.

### 2. ResNet-50 Transfer Learning

A pre-trained ResNet-50 model was used with ImageNet weights. The model was trained in two phases:

* Frozen backbone training
* Fine-tuning of top layers

### 3. CNN + Transformer Hybrid

The best-performing model combined CNN-based local feature extraction with Transformer-based global attention. MobileNetV2 was used as the CNN backbone, followed by Transformer encoder blocks for improved feature representation.

## Results

| Model                       | Test Accuracy | Macro F1-Score | Mean AUC-ROC |
| --------------------------- | ------------: | -------------: | -----------: |
| Custom CNN                  |        97.90% |         0.9774 |       0.9997 |
| ResNet-50 Transfer Learning |        88.49% |         0.8824 |       0.9880 |
| CNN + Transformer           |        99.73% |         0.9972 |       1.0000 |

## Best Model

The CNN-Transformer model performed best because it combines the strengths of both CNNs and Transformers.

CNN layers are effective at learning local image features such as edges, textures, colors, and fruit surface patterns. Transformer layers help capture global relationships between different image regions, which improves the model’s ability to distinguish fresh and rotten fruits.

## Technologies Used

* Python
* TensorFlow
* Keras
* OpenCV
* Scikit-learn
* NumPy
* pandas
* Matplotlib
* seaborn
* PIL
* Google Colab

## Evaluation Metrics

The models were evaluated using:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion matrix
* AUC-ROC curves
* Prediction verification on unseen images

## Key Features

* Multi-class fruit freshness classification
* Complete preprocessing and augmentation pipeline
* Class imbalance handling using class weights
* Comparison of CNN, transfer learning, and hybrid deep learning models
* High test accuracy using CNN-Transformer architecture
* Suitable for future deployment in web, mobile, or real-time quality control systems

## Future Work

Future improvements may include:

* Developing a web application for real-time fruit freshness prediction
* Creating a mobile app for farmers, retailers, and consumers
* Adding more fruit categories such as mangoes, grapes, guavas, and strawberries
* Applying Grad-CAM or attention visualization for explainable AI
* Deploying the model using REST APIs
* Extending the system to fruit quality grading, ripeness detection, and shelf-life prediction

## Authors

* Urooj Fatima
* Zainab

## Project Type

Deep Learning Project
Department of Software Engineering
Fatima Jinnah Women University
