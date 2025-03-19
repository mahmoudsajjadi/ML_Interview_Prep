# Linear Regression Module Summary

## Key Concepts

### 1. **Linear Regression Equation**
   - The core equation for linear regression is:

     $$y' = b + w_1x_1$$

   - Where:
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
     $$y' = b + w_1x_1 + w_2x_2 + \dots + w_nx_n$$

   - Example: Predicting fuel efficiency using weight, horsepower, and acceleration.

### 4. **Graphical Representation**
   - Data points are plotted to visualize relationships (e.g., car weight vs. fuel efficiency).
   - A best-fit line represents the model.



## Key Terms
- **Bias ($b$)**: The y-intercept in the regression equation.
- **Weight ($w$)**: The slope representing the feature's importance.
- **Feature ($x$)**: Input variable (e.g., car weight).
- **Label ($y'$)**: Predicted output (e.g., fuel efficiency).
- **Linear Regression**: A statistical method for modeling relationships between variables.

## Exercise
- **Question**: What parts of the linear regression equation are updated during training?
  - **Answer**: The **bias ($b$)** and **weights ($w_1, w_2, \dots$)** are updated during training.
 
# Linear Regression: Loss

## Overview
Loss is a numerical metric that measures how wrong a model's predictions are. It quantifies the distance between the model's predictions and the actual labels. The goal of training a model is to minimize the loss, reducing it to its lowest possible value.

## Key Concepts

### 1. **What is Loss?**
   - Loss measures the difference between the predicted values and the actual values.
   - It focuses on the **distance** between the values, not the direction.
   - Example: If a model predicts 2, but the actual value is 5, the loss is 3 (distance between 2 and 5).

### 2. **Types of Loss**
   - **L1 Loss**: The sum of the absolute differences between predictions and actual values.
     - Equation: `L1 Loss = Σ |y - y'|`
   - **Mean Absolute Error (MAE)**: The average of L1 losses across a set of examples.
     - Equation: `MAE = (1/n) * Σ |y - y'|`
   - **L2 Loss**: The sum of the squared differences between predictions and actual values.
     - Equation: `L2 Loss = Σ (y - y')^2`
   - **Mean Squared Error (MSE)**: The average of L2 losses across a set of examples.
     - Equation: `MSE = (1/n) * Σ (y - y')^2`

### 3. **Choosing a Loss Function**
   - **MSE**:
     - Penalizes outliers more heavily because squaring amplifies large errors.
     - Moves the model closer to outliers.
   - **MAE**:
     - Treats all errors equally, regardless of magnitude.
     - Keeps the model closer to the majority of data points.

### 4. **Example: Calculating L2 Loss**
   - **Scenario**: A model predicts that a 2,370-pound car gets 21.5 miles per gallon, but the actual value is 24 miles per gallon.
   - **Calculation**: `L2 Loss = (24 - 21.5)^2 = 6.25`

### 5. **Graphical Representation**
   - Loss is visualized as the distance between data points and the model's predictions.
   - **MSE**: The model is tilted more toward outliers.
   - **MAE**: The model is tilted further away from outliers.

## Key Terms
- **Loss**: A measure of how wrong a model's predictions are.
- **L1 Loss**: Sum of absolute differences between predictions and actual values.
- **L2 Loss**: Sum of squared differences between predictions and actual values.
- **MAE (Mean Absolute Error)**: Average of L1 losses.
- **MSE (Mean Squared Error)**: Average of L2 losses.
- **Outlier**: A data point that is significantly different from others.

## Exercise
- **Question**: Which dataset has a higher Mean Squared Error (MSE)?
   - **Dataset 1**: A line runs through 6 of 10 points. 2 points are 1 unit above the line, and 2 points are 1 unit below the line.
   - **Dataset 2**: A line runs through 8 of 10 points. 1 point is 2 units above the line, and 1 point is 2 units below the line.
   - **Answer**: **Dataset 2** has a higher MSE because the outliers are twice as far from the line, and squaring amplifies their impact.

## Reference
- Source: [Google Machine Learning Crash Course](https://developers.google.com/machine-learning/crash-course/)

## Reference
- Source: [Google Machine Learning Crash Course](https://developers.google.com/machine-learning/crash-course/)
