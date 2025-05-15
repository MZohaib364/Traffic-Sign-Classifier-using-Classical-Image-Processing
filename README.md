# Traffic Sign Classification Using Classical Image Processing

This project implements a complete rule-based traffic sign classifier using classical digital image processing techniques without relying on machine learning or pre-trained models.

## Project Overview

The system processes cropped traffic sign images and classifies them into one of several predefined categories using color, shape, and geometric features. All image processing operations are implemented from scratch using NumPy, focusing on fundamental image processing principles.

## Dataset

The project uses a subset of traffic sign images from the provided dataset. The working dataset consists of:
- 700 images across 7 traffic sign classes
- Approximately 100 images per class
- Images in PNG format

## Pipeline Components

### 1. Image Reading
- Images are loaded using either OpenCV or PIL
- Further processing is done exclusively with NumPy operations

### 2. Preprocessing and Filtering
Custom implementations of the following filters:
- Mean Filter (3×3)
- Gaussian Filter
- Median Filter
- Adaptive Median Filter
- Unsharp Masking/High-Boost Filtering

### 3. Color Space Conversion and Segmentation
- Manual RGB to HSV conversion
- Color-based segmentation for red and blue signs
- Post-processing with binary thresholding, morphological operations, noise removal, and hole filling

### 4. Edge Detection
Custom implementation of the Canny edge detection algorithm:
- Gradient computation using Sobel operators
- Non-maximum suppression
- Double thresholding and edge tracking

### 5. Geometric Normalization
Custom affine transformations using NumPy:
- Rotation correction for upright orientation
- Scaling to fixed dimensions (200×200 pixels)
- Optional perspective transform

### 6. Feature Extraction
Extraction of the following features:
- Corner count using Harris Corner Detection
- Circularity (4π × Area / Perimeter²)
- Aspect ratio of the bounding box
- Extent (region area / bounding box area)
- Average hue

### 7. Rule-Based Classification
- Logic-based classification using the extracted features
- Rules incorporating both color and shape characteristics
- Customized rules for distinguishing visually similar signs

## Usage

1. Clone the repository:
```bash
git clone https://github.com/username/traffic-sign-classifier.git
cd traffic-sign-classifier

2. Make sure you have all required dependencies:
pip install numpy pillow opencv-python matplotlib

3. Run Notebook Cells

## Results
The classification performance is evaluated using:

- Overall accuracy
- Class-wise precision, recall, and F1-score
- Confusion matrix visualization

Implementation Notes

- All image processing operations are implemented from scratch using NumPy
- The classifier uses interpretable rule-based logic rather than statistical models

