# Linear Regression Module Summary

## Overview
This module introduces **linear regression**, a statistical technique used to model the relationship between features and a label in machine learning. It covers key concepts such as loss functions, gradient descent, and hyperparameter tuning.

## Key Concepts
### 1. **Linear Regression Equation**
   - The core equation for linear regression is:

     $$
     y' = b + w_1x_1
     $$

     - $y'$: Predicted label (output).
     - $b$: Bias (y-intercept).
     - $w_1$: Weight (slope of the line).
     - $x_1$: Feature (input).

   - Example: Predicting car fuel efficiency (miles per gallon) based on car weight.

### 2. **Training**
   - The model updates **bias** ($b$) and **weights** ($w_1, w_2, \dots$) during training to minimize the loss function.
   - **Gradient descent** is used to find the optimal parameters.

### 3. **Multiple Features**
   - For multiple features, the equation extends to:

     $$
     y' = b + w_1x_1 + w_2x_2 + \dots + w_nx_n
     $$

   - Example: Predicting fuel efficiency using weight, horsepower, and acceleration.

### 4. **Graphical Representation**
   - Data points are plotted to visualize relationships (e.g., car weight vs. fuel efficiency).
   - A best-fit line represents the model.

## Learning Objectives
- Explain loss functions and gradient descent.
- Tune hyperparameters for efficient model training.
- Understand the role of bias, weights, and features in linear regression.

## Prerequisites
- Familiarity with **Introduction to Machine Learning**.

## Key Terms
- **Bias ($b$)**: The y-intercept in the regression equation.
- **Weight ($w$)**: The slope representing the feature's importance.
- **Feature ($x$)**: Input variable (e.g., car weight).
- **Label ($y'$)**: Predicted output (e.g., fuel efficiency).
- **Linear Regression**: A statistical method for modeling relationships between variables.

## Exercise
- **Question**: What parts of the linear regression equation are updated during training?
  - **Answer**: The **bias ($b$)** and **weights ($w_1, w_2, \dots$)** are updated during training.

## Reference
- Source: [Google Machine Learning Crash Course](https://developers.google.com/machine-learning/crash-course/)
