# CIFAR-10 Image Classification Model (PyTorch)

A deep learning project focused on building a custom convolutional neural network architecture for image classification on the CIFAR-10 dataset.

The project explores architectural design, data augmentation, and training optimisation techniques to improve generalisation and model performance.

---

## Overview

This project implements a modular CNN using PyTorch, built from custom convolutional blocks and trained on the CIFAR-10 dataset (60,000 32x32 colour images across 10 classes).

Key goals:
- Design a flexible and reusable CNN architecture  
- Apply data augmentation to improve generalisation  
- Experiment with optimisation strategies and learning rate scheduling  
- Track training performance and evaluate test accuracy  

---

## Dataset

- **Dataset:** CIFAR-10  
- **Training Samples:** 50,000  
- **Test Samples:** 10,000  
- **Classes:** 10 (e.g. airplane, car, bird, cat, etc.)

---

## Model Architecture

The model is composed of three main parts:

### 1. Custom Convolutional Blocks
- Parallel convolutional layers (2–3 per block)
- Batch Normalisation for stable training
- LeakyReLU activation
- Dropout for regularisation
- MaxPooling for spatial reduction
- Adaptive average pooling + learned weighting mechanism

Each block dynamically combines feature maps using learned weights, allowing the model to emphasise more informative features.

---

### 2. Backbone
- Stacked sequence of 4 custom blocks  
- Progressive channel scaling:
  - 32 → 64 → 128 → 256  
- Extracts hierarchical spatial features from input images  

---

### 3. Classifier
- Global average pooling  
- Fully connected layer → 10 output classes  

---

## Data Augmentation

To improve generalisation, the training pipeline includes:

- Random horizontal flipping  
- Colour jitter (brightness, contrast, saturation, hue)  
- Random rotation (±15°)  
- Random cropping with padding  
- Normalisation  

---

## Training Setup

- **Loss Function:** CrossEntropyLoss  
- **Optimiser:** AdamW  
- **Learning Rate:** 0.001  
- **Weight Decay:** 0.01  
- **Batch Size:** 64  
- **Epochs:** 60  
- **Scheduler:** StepLR (decays LR every 20 epochs)  

---

## Performance

Final results after training:

- **Training Accuracy:** ~92.8%  
- **Test Accuracy:** ~88.5%  

---

## Training Features

- Real-time training visualisation (loss + accuracy)  
- Custom metric tracking utilities  
- GPU acceleration (CUDA support)  
- Modular training loop for experimentation  

---

## Key Learnings

- Designing custom CNN architectures beyond standard sequential models  
- Importance of data augmentation in improving model robustness  
- Effects of learning rate scheduling on convergence  
- Managing overfitting using dropout and regularisation  
- Structuring PyTorch code for clarity and reusability  

---

## Tech Stack

- **Python**
- **PyTorch**
- **Torchvision**
- **Matplotlib**
- **NumPy**
