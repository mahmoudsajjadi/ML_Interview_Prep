
# Linear Regression Module Summary

## Overview
This module introduces **linear regression**, a statistical technique used to model the relationship between features and a label in machine learning. It covers key concepts such as loss functions, gradient descent, and hyperparameter tuning.

## Key Concepts
1. **Linear Regression Equation**:
   - Model: \( y' = b + w_1x_1 \)
     - \( y' \): Predicted label (output).
     - \( b \): Bias (y-intercept).
     - \( w_1 \): Weight (slope).
     - \( x_1 \): Feature (input).
   - Example: Predicting car fuel efficiency (miles per gallon) based on car weight.

2. **Training**:
   - The model updates **bias** and **weights** during training to minimize the loss function.
   - Gradient descent is used to find optimal parameters.

3. **Multiple Features**:
   - Models can include multiple features (e.g., engine displacement, acceleration, horsepower).
   - Equation: \( y' = b + w_1x_1 + w_2x_2 + \dots + w_nx_n \).

4. **Graphical Representation**:
   - Data points are plotted to visualize relationships (e.g., car weight vs. fuel efficiency).
   - A best-fit line represents the model.

## Learning Objectives
- Explain loss functions and gradient descent.
- Tune hyperparameters for efficient model training.
- Understand the role of bias, weights, and features in linear regression.

## Prerequisites
- Familiarity with **Introduction to Machine Learning**.

## Key Terms
- Bias
- Feature
- Label
- Linear Regression
- Parameter
- Weight

## Exercise
- **Question**: What parts of the linear regression equation are updated during training?
  - **Answer**: The **bias and weights** are updated during training.

## Reference
- Source: [Google Machine Learning Crash Course](https://developers.google.com/machine-learning/crash-course/)
