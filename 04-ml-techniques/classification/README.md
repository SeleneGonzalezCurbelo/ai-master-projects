# Classification: Support Vector Machines and Random Forest

## Overview

This repository contains implementations and analyses of **classification tasks** using two popular machine learning models:

1. **Support Vector Machine (SVM)** – A supervised model that finds the optimal hyperplane to separate classes.
2. **Random Forest (100 Trees)** – An ensemble learning method that builds multiple decision trees for improved classification accuracy and robustness.

The goal is to compare both models, evaluate their performance on multiclass datasets, and analyze how they handle imbalanced classes.

---

## Datasets
The experiments are conducted on the **Covertype Dataset** from the UCI Machine Learning Repository: [Covertype Dataset](https://archive.ics.uci.edu/dataset/31/covertype)

- Contains cartographic variables to predict forest cover type.
- Original data without sensor inputs, with binary variables for qualitative attributes (wilderness areas, soil types).
- Objective: predict the forest cover type for a given observation.

---
## Key Features
- Data preprocessing including handling categorical and binary features.
- Feature scaling for SVM.
- Analysis of class imbalance and its effect on model performance.
- Comparison of models using metrics such as accuracy, F1-score, recall, and misclassification rate.

## Implementation

- **Support Vector Machine (SVM)**: Trained without class balancing. Evaluated using accuracy and F1-scores for each class.
- **Random Forest**: Trained with 100 trees. Evaluated using the same metrics, with a focus on performance for both majority and minority classes.

## Results

| **Metric**                       | **SVM (Unbalanced)** | **Random Forest (100 Trees)** |
|---------------------------------|--------------------|-------------------------------|
| **Accuracy**                     | 69.51%             | 72.28%                        |
| **Mean F1-score**                | 0.4717             | 0.5673                        |
| **Well-classified classes**      | Class 1: 0.7561, Class 2: 0.7110 | Class 2: 0.7692 |
| **Performance on minority classes** | Class 4: 0.3717, Class 5: 0.1979, Class 6: 0.3591 | Class 4: 0.4524, Class 5: 0.3221, Class 6: 0.4131 |
| **Misclassification rate**       | 30.49%             | 27.72%                        |
| **Correctly classified examples** | 80,775            | 83,995                        |
| **Incorrectly classified examples** | 35,428           | 32,208                        |

- Random Forest outperforms SVM in overall accuracy, mean F1-score, and classification of minority classes.
- SVM performs well for the majority classes (Class 1 and 2) but struggles with minority classes.
- Random Forest provides a more balanced and robust model across all classes, with lower misclassification rates.


---

## Author
Selene González Curbelo  
Universidad Internacional de la Rioja (UNIR)  
Course: *Machine Learning Techniques*  
Date: 2024