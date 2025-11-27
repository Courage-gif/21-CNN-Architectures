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

Project Structure
text
house_price_prediction/
├── data/
│   ├── final_zimbabwe.csv
│   └── images/
├── models/
│   ├── base_model.py
│   ├── model_factory.py
│   └── optimized_model.py
├── training/
│   ├── train_utils.py
│   └── evaluation.py
├── datasets/
│   └── property_dataset.py
└── notebooks/
    └── house_price_prediction.ipynb
Installation & Requirements
bash
pip install torch torchvision pandas numpy scikit-learn matplotlib seaborn pillow tqdm
Usage
Data Preparation:

Mount Google Drive (if using Colab)

Load and preprocess the dataset

Validate image paths and clean data

Feature Extraction:

Extract numeric features from CSV

Process text features using TF-IDF

Prepare image paths for CNN processing

Model Training:

Select from 21 available architectures

Configure training parameters

Monitor training progress with progress bars

Evaluation:

Test model performance on holdout set

Calculate metrics: MAE, RMSE, R², MAPE

Compare different architectures

Key Results
The optimized model achieves:

R² Score: -0.2470 (indicates need for model improvement)

Mean Absolute Error: $189,319.22

Root Mean Squared Error: $267,017.80

Mean Absolute Percentage Error: 94.41%

Critical Improvements Made
Proper Price Scaling: Applied log transformation + StandardScaler

Enhanced Data Validation: Ensured all images from CSV are properly loaded

Optimized Architecture: Used EfficientNet-B0 for CPU efficiency

Advanced Training: Implemented Huber loss, gradient clipping, and cosine annealing

Challenges & Solutions
Data Quality: Extensive cleaning pipeline to handle missing values and outliers

Image Availability: Validation system to ensure all referenced images exist

Model Complexity: Optimized architectures for CPU training while maintaining accuracy

Feature Integration: Effective fusion of image, numeric, and text features

Future Improvements
Collect more training data to improve model generalization

Experiment with different feature fusion techniques

Implement ensemble methods combining multiple architectures

Add geographic and temporal features

Optimize hyperparameters for specific architectures
# 21 CNN Architectures
House Price Prediction 
