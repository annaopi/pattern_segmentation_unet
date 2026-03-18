# Pattern Image Segmentation using U-Net (TensorFlow)

## Overview

This project implements an image segmentation pipeline using a convolutional neural network based on the U-Net architecture.

The goal is to detect patterns in images and generate binary segmentation masks. The project demonstrates a complete computer vision workflow including data preprocessing, model training, evaluation, and visualization of results.


## Features

- Image preprocessing using OpenCV  
- Automatic mask generation using thresholding  
- Image normalization (pixel values scaled to [0, 1])  
- Train/validation split (80/20)  
- Image segmentation using a U-Net convolutional neural network  
- Model training using TensorFlow/Keras  
- Evaluation using accuracy and Intersection over Union (IoU)  
- Visualization of predictions and training metrics  


## Technologies

- Python  
- TensorFlow / Keras  
- OpenCV  
- NumPy  
- scikit-learn  
- Matplotlib  


## Dataset

The dataset contains `.jpg` images with patterns on a white background stored in the following folder:
```bash
dataset-patterns/
```
Binary masks are generated automatically using image thresholding:

1. Convert image to grayscale  
2. Apply threshold segmentation  
3. Separate foreground object from background  

Background pixels - 0  
Object pixels - 1  


## Training Configuration

- Image resolution: 696 × 496  
- Batch size: 4  
- Epochs: 20  

Early stopping is used during training to prevent overfitting.


## Model Architecture

The model is based on the U-Net architecture and consists of:

- Encoder (convolution + max pooling)  
- Bottleneck  
- Decoder (upsampling with skip connections)  

The final layer uses a sigmoid activation function to produce binary segmentation masks.


## Evaluation

Model performance is evaluated using:

- Accuracy (during training)  
- Intersection over Union (IoU) calculated after training  

IoU measures the overlap between predicted masks and ground-truth masks:
IoU = Intersection / Union

Higher IoU values indicate better segmentation performance.
The average IoU score is calculated across the validation dataset.


## Visualization

The project visualizes:

- Original images  
- Ground-truth segmentation masks  
- Predicted segmentation masks  

It also plots:

- Training and validation loss  
- Training and validation accuracy  
- Histogram of IoU scores  


## Running the Project

Clone the repository:
```bash
git clone https://github.com/your-username/pattern-segmentation-unet
cd pattern-segmentation-unet
```
Install dependencies:
```bash
pip install tensorflow opencv-python numpy matplotlib scikit-learn
```
(If using Google Colab)
```bash
unzip dataset-patterns.zip
```
Place the dataset in the project folder:
```bash
dataset-patterns/
```
Then run the notebook.


## Project Structure
```bash
pattern-segmentation-unet
│
├── dataset-patterns
├── segmentacija-sablona.ipynb
├── README.md
└── requirements.txt
```
## Possible Improvements

Data augmentation
Dice loss function
Larger datasets
Hyperparameter tuning
GPU optimization
Additional evaluation metrics (Precision, Recall, F1-score)

## Author

Student machine learning project demonstrating image segmentation using TensorFlow and Python.
