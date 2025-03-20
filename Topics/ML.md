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

# Linear Regression: Hyperparameters

## Overview
Hyperparameters are variables that control the training process of a model. Unlike model parameters (e.g., weights and bias), hyperparameters are set by the user before training begins. Key hyperparameters include **learning rate**, **batch size**, and **epochs**.

## Key Concepts

### 1. **Learning Rate**
   - **Definition**: A floating-point number that controls the step size during gradient descent.
   - **Role**:
     - If the learning rate is **too low**, the model takes a long time to converge.
     - If the learning rate is **too high**, the model may never converge and instead bounce around the optimal values.
   - **Ideal Learning Rate**:
     - Problem-dependent; must be tuned for each dataset and model.
   - **Impact on Training**:
     - **Too Low**: Slow convergence
     - **Too High**: Loss fluctuates or increases
     - **Ideal**: Loss decreases steadily and converges quickly

### 2. **Batch Size**
   - **Definition**: The number of examples processed before updating the model's weights and bias.
   - **Types**:
     - **Full Batch**: Uses the entire dataset for each update (not practical for large datasets).
     - **Stochastic Gradient Descent (SGD)**: Uses **one example per batch**.
       - Pros: Fast updates.
       - Cons: Noisy loss curve
     - **Mini-Batch SGD**: Uses a **subset of examples per batch** (e.g., 10, 100).
       - Pros: Balances noise and computational efficiency
   - **Choosing Batch Size**:
     - Depends on the dataset and available compute resources.
     - Smaller batches behave like SGD; larger batches behave like full-batch gradient descent.

### 3. **Epochs**
   - **Definition**: One full pass through the entire training dataset.
   - **Role**:
     - Training typically requires multiple epochs for the model to converge.
     - More epochs generally improve the model but increase training time.
   - **Example**:
     - Dataset: 1,000 examples.
     - Batch size: 100 examples.
     - Iterations per epoch: 10.
     - Total updates for 20 epochs: 200.

### 4. **Hyperparameter Relationships**
   - **Batch Size vs. Updates**:
     - **Full Batch**: Updates occur once per epoch.
     - **SGD**: Updates occur after every example.
     - **Mini-Batch SGD**: Updates occur after each batch.
   - **Learning Rate vs. Convergence**:
     - A well-tuned learning rate ensures the model converges quickly without bouncing or stalling.

## Key Terms
- **Learning Rate**: Controls the step size during gradient descent.
- **Batch Size**: Number of examples processed before updating weights and bias.
- **Epoch**: One full pass through the training dataset.
- **Stochastic Gradient Descent (SGD)**: Updates weights after each example.
- **Mini-Batch SGD**: Updates weights after processing a subset of examples.
- **Hyperparameter**: User-defined variables that control training.
- **Parameter**: Model variables (e.g., weights, bias) learned during training.

## Exercise
1. **Question**: What is the ideal learning rate?
   - **Answer**: The ideal learning rate is problem-dependent and varies for each dataset and model.

2. **Question**: What's the best batch size when using mini-batch SGD?
   - **Answer**: It depends on the dataset and available compute resources.

3. **Question**: Which statement is true?
   - **Statement**: Doubling the learning rate can slow down training.
   - **Answer**: True. A learning rate that is too large can cause the model to bounce around, increasing convergence time.

# Logistic Regression

## Overview
Logistic regression is a machine learning model used to predict the probability of a given outcome. Unlike linear regression, which predicts continuous values, logistic regression is designed for binary classification problems (e.g., "Will it rain today?" or "Is this email spam?").

## Key Concepts

### 1. **Sigmoid Function**
   - The sigmoid function transforms the output of a linear equation into a probability value between 0 and 1.
   - Formula:
     $$\sigma(z) = \frac{1}{1 + e^{-z}}$$
   - Properties:
     - Output approaches 0 as \( z \) approaches \(-\infty\).
     - Output approaches 1 as \( z \) approaches \(+\infty\).
     - Always outputs a value between 0 and 1.

### 2. **Logistic Regression Equation**
   - The linear component of logistic regression is:
     $$
     z = b + w_1x_1 + w_2x_2 + \dots + w_nx_n
     $$
     - \( z \): Linear output (log-odds).
     - \( b \): Bias.
     - \( w \): Weights.
     - \( x \): Feature values.
   - The logistic regression prediction is obtained by passing \( z \) through the sigmoid function:
     $$
     y' = \sigma(z) = \frac{1}{1 + e^{-z}}
     $$
     - \( y' \): Predicted probability (between 0 and 1).

### 3. **Log-Odds**
   - The linear output \( z \) is also called **log-odds**:
     $$
     z = \ln\left(\frac{y'}{1 - y'}\right)
     $$
   - This represents the logarithm of the ratio of the probability of the positive class to the probability of the negative class.

### 4. **Example: Calculating Logistic Regression Output**
   - Given:
     - Bias (\( b \)): 1
     - Weights (\( w_1, w_2, w_3 \)): 2, -1, 5
     - Input values (\( x_1, x_2, x_3 \)): 0, 10, 2
   - Step 1: Calculate \( z \):
     $$
     z = 1 + (2)(0) + (-1)(10) + (5)(2) = 1
     $$
   - Step 2: Calculate \( y' \) using the sigmoid function:
     $$
     y' = \frac{1}{1 + e^{-1}} \approx 0.731
     $$
   - Interpretation: The model predicts a 73.1% probability of the positive class.

## Key Terms
- **Logistic Regression**: A model used to predict probabilities for binary classification.
- **Sigmoid Function**: A function that maps any real number to a value between 0 and 1.
- **Log-Odds**: The logarithm of the ratio of the probability of the positive class to the probability of the negative class.
- **Binary Classification**: A problem where the output is one of two possible classes (e.g., spam or not spam).

## Exercise
1. **Question**: What is the value of \( z \) for the given input values?
   - **Answer**: \( z = 1 \).

2. **Question**: What is the logistic regression prediction for these input values?
   - **Answer**: \( y' \approx 0.731 \).

## Reference
- Source: [Google Machine Learning Crash Course](https://developers.google.com/machine-learning/crash-course/)
