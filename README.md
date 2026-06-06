# CNN Optimization and Regularization Techniques on CIFAR-10

## Overview

This repository contains two deep learning projects focused on improving the performance of Convolutional Neural Networks (CNNs) on the CIFAR-10 image classification dataset.

The first project investigates the impact of different optimization algorithms on model training and convergence. The second project explores various regularization techniques designed to reduce overfitting and improve model generalization. Together, these experiments provide practical insight into two important aspects of deep learning model development: optimization and regularization.

## Dataset

Both projects use the CIFAR-10 dataset, which consists of 60,000 color images of size 32×32 pixels distributed across 10 classes:

* Airplane
* Automobile
* Bird
* Cat
* Deer
* Dog
* Frog
* Horse
* Ship
* Truck

The dataset contains 50,000 training images and 10,000 test images.

---

# Project 1: Optimization Techniques

## Objective

The goal of this project is to compare the effect of different optimization algorithms on CNN training performance.

## Optimizers Evaluated

* Stochastic Gradient Descent (SGD)
* SGD with Momentum
* RMSprop
* Adam

## Evaluation Criteria

The optimizers were compared using:

* Training Accuracy
* Validation Accuracy
* Training Loss
* Validation Loss
* Convergence Speed

## Key Findings

* Adam achieved the fastest convergence and strongest overall performance.
* RMSprop also demonstrated efficient learning but was slightly less consistent.
* SGD required more epochs to reach comparable accuracy.
* Momentum improved SGD performance by accelerating convergence and reducing oscillations.

---

# Project 2: Regularization Techniques

## Objective

The goal of this project is to study the effectiveness of different regularization techniques in reducing overfitting and improving model generalization.

## Techniques Evaluated

### Baseline CNN

A standard CNN architecture without additional regularization.

### Dropout

Randomly deactivates neurons during training to reduce co-adaptation and overfitting.

### L2 Regularization

Applies a penalty to large weight values, encouraging simpler models.

### Batch Normalization

Normalizes activations between layers to improve training stability and learning speed.

### Data Augmentation

Generates modified versions of training images through random transformations to increase dataset diversity.

### Combined Model

A CNN incorporating Dropout, L2 Regularization, Batch Normalization, and Data Augmentation simultaneously.

## Results Summary

| Model               | Training Accuracy | Validation Accuracy |
| ------------------- | ----------------- | ------------------- |
| Baseline            | 91.45%            | 70.71%              |
| Dropout             | 74.85%            | 70.71%              |
| L2 Regularization   | 76.35%            | 69.58%              |
| Batch Normalization | 98.53%            | 68.59%              |
| Data Augmentation   | 67.84%            | 66.93%              |
| Combined Model*     | 70.35%            | **72.16%**          |

* The Combined Model was trained for 40 epochs, while all other models were trained for 20 epochs.


## Key Findings

* Dropout successfully reduced overfitting while maintaining baseline validation accuracy.
* L2 Regularization improved weight control but did not outperform the baseline model.
* Batch Normalization achieved very high training accuracy but did not improve validation performance in this architecture.
* Data Augmentation increased training difficulty and required longer training to fully realize its benefits.
* The Combined Model achieved the highest validation accuracy, demonstrating that multiple regularization techniques can work together to improve generalization.

However, the Combined Model also exhibited larger fluctuations in validation performance, suggesting that combining multiple regularization methods may require careful tuning of hyperparameters and training settings.

---

# Technologies Used

* Python
* TensorFlow / Keras
* NumPy
* Matplotlib
* Google Colab
* Jupyter Notebook

---

# Repository Structure

```
├── Optimization/
│   ├── optimizer_comparison.ipynb
│   └── plots/
│
├── Regularization/
│   ├── regularization_comparison.ipynb
│   └── plots/
│
└── README.md
```

---

# Conclusion

These projects demonstrate how optimization algorithms and regularization techniques influence CNN training behavior and model performance. While optimizers primarily affect learning speed and convergence, regularization techniques focus on improving generalization and reducing overfitting. The experiments highlight the importance of selecting appropriate training strategies and show that combining complementary techniques can often produce the best overall results.
