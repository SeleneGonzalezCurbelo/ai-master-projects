# Convolutional Neural Networks (CNN) with CIFAR-10

This project explores the use of **Convolutional Neural Networks (CNNs)** for image classification on the [CIFAR-10 dataset](https://www.cs.toronto.edu/~kriz/cifar.html).  
The dataset contains **60,000 color images** (32x32 pixels) divided into 10 classes of animals and vehicles.

Experiments are conducted with multiple CNN architectures to analyze the impact of **depth, regularization, batch normalization, dropout, and data augmentation** on model performance.

## Dataset

- **Name:** CIFAR-10  
- **Source:** [CIFAR-10 Dataset](https://www.cs.toronto.edu/~kriz/cifar.html)  
- **Description:** 60,000 color images in 10 balanced classes (airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck).  
- **Splits:**  
  - Training set: 40,000 images  
  - Validation set: 10,000 images  
  - Test set: 10,000 images  
- **Image size:** 32 × 32 pixels 

---

## Models Tested

### **Model 1 – Simple CNN**
- 2 convolutional layers (32, 64 filters, kernel size 3×3)  
- MaxPooling after each conv layer  
- Dense layer: 128 units + Dropout (0.5)  
- Batch Normalization enabled  
- Optimizer: Adam (LR = 0.001)  
- **Test Accuracy:** 72.7%  

---

### **Model 2 – Deep CNN with Regularization**
- 3 convolutional layers (32, 64, 128 filters)  
- Dense layer: 256 units  
- Dropout applied after each block  
- Batch Normalization in both conv and dense layers  
- Optimizer: Adam (LR = 0.001)  
- **Test Accuracy:** 77.9%  

---

### **Model 3 – CNN without Batch Normalization**
- 2 convolutional layers (64, 128 filters)  
- Dropout: 0.5  
- No Batch Normalization  
- Optimizer: Adam (LR = 0.0005)  
- **Test Accuracy:** 72.1%  

---

## Model Comparison

| Model                  | Test Accuracy | Test Loss | Errors (out of 10k) |
| ----------------------- | ------------- | --------- | ------------------- |
| Model 1 – Simple CNN    | 72.7%         | 0.7834    | 2734                |
| Model 2 – Deep CNN      | 77.9%         | 0.6397    | 2205                |
| Model 3 – No BatchNorm  | 72.1%         | 0.8179    | 2789                |

**Best Model:** Deep CNN with Dropout + Batch Normalization → higher accuracy and better generalization, especially in difficult classes (cat, dog, bird).

---

## Hyperparameter Exploration

Experiments were run with different **dropout rates** (0.3, 0.5) and **learning rates** (0.001, 0.0005):

| Dropout | LR     | Test Accuracy | Errors | Best Performing Classes |
| ------- | ------ | ------------- | ------ | ----------------------- |
| 0.3     | 0.001  | 70.98%        | 3005   | airplane, car           |
| 0.3     | 0.0005 | 75.29%        | 2589   | car, frog               |
| 0.5     | 0.001  | 70.23%        | 2940   | ship, frog              |
| 0.5     | 0.0005 | 70.34%        | 3041   | truck, ship             |

**Best trade-off:** Dropout = 0.3, LR = 0.0005  

---

## CNN vs. MLP Baseline

| Model         | Accuracy | Errors | F1-score | Best Classes        |
| ------------- | -------- | ------ | -------- | ------------------- |
| CNN (best)    | 74.1%    | 2589   | 0.74     | ship, car, frog     |
| MLP baseline  | 69.3%    | 3073   | 0.69     | airplane, car, ship |

CNN significantly outperforms the MLP baseline, especially in complex classes.

---

## Final Analysis

- **Dropout:** Effective for regularization, best when combined with BatchNorm.  
- **Batch Normalization:** Improves convergence and generalization.  
- **Data Augmentation:** Increases dataset diversity, reduces overfitting, boosts performance.  
- **Network Depth:** Deeper models (≥3 conv layers) perform better if paired with proper regularization.  
- **Best Model:** Deep CNN + Dropout + BatchNorm + Data Augmentation.  
  - Achieved validation accuracy: **87.6%** with reduced loss.  

---

## Author
Selene González Curbelo  
Universidad Internacional de la Rioja (UNIR)  
Course: *Deep Learning*  
Date: 2025