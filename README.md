House Price Prediction using 21 CNN Architectures
Project Overview
This project implements a comprehensive deep learning system for predicting house prices in Zimbabwe using property images and metadata. The system trains 21 different CNN architectures to extract visual features from property images and combines them with numeric and text features for accurate price prediction.

Key Features
Multi-Modal Approach: Combines CNN-extracted visual features with numeric property data and text features

21 CNN Architectures: Implements and compares 21 different neural network architectures

Comprehensive Data Processing: Extensive data cleaning, feature engineering, and image preprocessing

Optimized Training: Includes advanced techniques like mixed precision training, learning rate scheduling, and early stopping

Dataset
The project uses a Zimbabwe property dataset containing:

Property images (WEBP format)

Numeric features: building area, land area, bedrooms, bathrooms, image count

Text features: property titles, locations, descriptions

Price information in USD

Data Cleaning Process
Removed invalid/extreme prices ($1,000 - $7,500,000 range)

Validated and filtered missing image files

Handled missing values using median/mode imputation

Extracted derived features (area ratios, quality indicators, location encoding)

Model Architectures
The project implements the following 21 CNN architectures:

AlexNet

NIN (Network in Network)

ZFNet

VGG

GoogleNet

Inception-V3

Highway Network

Inception-V4

ResNet

Inception-ResNet-v2

FractalNet

WideResNet

Xception

Residual Attention Neural Network

Squeeze-and-Excitation Networks

DenseNet

Competitive Squeeze and Excitation Network

MobileNet-v2

CapsuleNet

HRNetV2

EfficientNet

Feature Engineering
Numeric Features
Building area, land area, bedrooms, bathrooms

Image count (log-transformed)

Area ratios and derived metrics

Location one-hot encoding

Text Features
TF-IDF vectorization of combined text (title + location + property type + quality keywords)

N-gram range (1,2) with max features limit

Image Features
CNN-extracted visual features from property images

Data augmentation: random crops, flips, rotations, color jittering

Training Configuration
Device: CPU/GPU optimized with mixed precision training

Batch Size: 8 (optimized for CPU training)

Image Size: 224x224 (resized from 256x256)

Epochs: 15-30 with early stopping

Loss Function: Huber Loss (robust to outliers)

Optimizer: AdamW with weight decay

Learning Rate: Cosine annealing with warm restarts

 
Add geographic and temporal features

Optimize hyperparameters for specific architectures
# 21 CNN Architectures
House Price Prediction 
