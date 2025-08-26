# Digit Classification with Neural Networks

This project focuses on classifying handwritten digits (0–9) using neural networks. The implementation is done using Keras with TensorFlow.

## Dataset

- **Dataset:** MNIST (Modified National Institute of Standards and Technology database)  
- **Description:** Grayscale images of handwritten digits (0–9), each 28x28 pixels, stored as uint8 arrays.  
- **Source:** See the detailed description on Wikipedia: [Base de datos MNIST](https://es.wikipedia.org/wiki/Base_de_datos_MNIST) 

The dataset includes 60,000 training images and 10,000 test images, widely used in machine learning and education for benchmarking classification models.

---

## Network Architecture

- Input: Flattened 28x28 images (or using a Flatten layer)
- Hidden Layers: 3 dense layers with 512, 256, and 128 neurons
- Output: 10 neurons with softmax activation
- Activation Function: ReLU (other activations tested: Sigmoid, Tanh, Leaky ReLU)
- Optimizer: Adam (other optimizers tested: SGD, RMSprop, Adagrad)
- Regularization: Dropout (0.3–0.4), L2, Batch Normalization
- Batch Size: 64
- Early Stopping applied

## Training

- Number of epochs: 5 (initially) and extended to 30 for testing overfitting
- Validation Split: 25%
- Accuracy on training and validation: >99%
- Test Accuracy: 98.3%
- Observed overfitting when training for 30 epochs without proper regularization

## Key Observations

- Flatten layer vs. manual reshaping yields similar performance
- Increasing neurons from 256 to 1024 gives minor improvements
- ReLU provides fastest convergence and stable accuracy
- Optimizer choice affects convergence speed and stability:
  - Adam provided best trade-off between speed and accuracy
  - SGD with momentum improves precision
  - RMSprop may overfit if not properly tuned
  - Adagrad slower and less precise

## Conclusions

- Moderate hidden layer size is sufficient for MNIST classification
- Proper regularization and batch normalization help reduce overfitting
- The model achieves high generalization and stable performance across all classes

---

## Author
Selene González Curbelo  
Universidad Internacional de la Rioja (UNIR)  
Course: *Deep Learning*  
Date: 2025