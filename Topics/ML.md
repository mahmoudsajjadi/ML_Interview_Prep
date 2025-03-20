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

# Linear Regression: Gradient Descent

## Overview
Gradient descent is a mathematical technique used to iteratively find the optimal weights and bias that minimize the loss in a linear regression model. It is a core optimization algorithm in machine learning.

## Key Concepts

### 1. **What is Gradient Descent?**
   - Gradient descent is an iterative process that:
     1. Starts with randomized weights and biases near zero.
     2. Calculates the loss using the current weights and bias.
     3. Determines the direction to adjust the weights and bias to reduce loss.
     4. Moves the weights and bias a small amount in that direction.
     5. Repeats the process until the loss is minimized.

### 2. **Steps of Gradient Descent**
   - **Step 1**: Initialize weights and bias to small random values (often near zero).
   - **Step 2**: Calculate the loss (e.g., Mean Squared Error) using the current weights and bias.
   - **Step 3**: Compute the derivatives of the loss function with respect to the weights and bias.
     - **Weight Derivative**:
       $$\frac{\partial \text{Loss}}{\partial w} = \frac{2}{n} \sum_{i=1}^n (y_i' - y_i) \cdot x_i$$
     - **Bias Derivative**:
       $$\frac{\partial \text{Loss}}{\partial b} = \frac{2}{n} \sum_{i=1}^n (y_i' - y_i)$$
   - **Step 4**: Update the weights and bias:
     $$w_{\text{new}} = w_{\text{old}} - \alpha \cdot \frac{\partial \text{Loss}}{\partial w}$$
     $$b_{\text{new}} = b_{\text{old}} - \alpha \cdot \frac{\partial \text{Loss}}{\partial b}$$
     - Where \( \alpha \) is the **learning rate** (a small value, e.g., 0.01).
   - **Step 5**: Repeat until the loss converges (stops decreasing significantly).

### 4. **Model Convergence**
   - **Loss Curve**: A graph of loss vs. iterations shows how the loss decreases over time.
     - Initially, the loss decreases rapidly.
     - Eventually, the loss flattens out, indicating convergence.
   - **Convex Loss Surface**: Linear regression loss functions are convex, ensuring gradient descent finds the global minimum.

### 5. **Visualizing Gradient Descent**
   - **Initial Model**: High loss, poor fit to data.
   - **Mid-Training Model**: Loss decreases, model improves.
   - **Converged Model**: Lowest loss, best fit to data.

## Key Terms
- **Gradient Descent**: An iterative optimization algorithm used to minimize loss.
- **Learning Rate (\( \alpha \))**: A small value that controls the step size during updates.
- **Convergence**: When the loss stops decreasing significantly.
- **Loss Curve**: A graph showing how loss changes over iterations.
- **Convex Function**: A function with a single global minimum (e.g., linear regression loss).

## Exercise
- **Question**: What is the role of gradient descent in linear regression?
  - **Answer**: Gradient descent is an iterative process that finds the best weights and bias to minimize the loss.

## Reference
- Source: [Google Machine Learning Crash Course](https://developers.google.com/machine-learning/crash-course/)
