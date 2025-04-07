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
     $$z = b + w_1x_1 + w_2x_2 + \dots + w_nx_n$$
     - \( z \): Linear output (log-odds).
     - \( b \): Bias.
     - \( w \): Weights.
     - \( x \): Feature values.
   - The logistic regression prediction is obtained by passing \( z \) through the sigmoid function:
     $$y' = \sigma(z) = \frac{1}{1 + e^{-z}}$$
     - \( y' \): Predicted probability (between 0 and 1).

### 3. **Log-Odds**
   - The linear output \( z \) is also called **log-odds**:
     $$z = \ln\left(\frac{y'}{1 - y'}\right)$$
   - This represents the logarithm of the ratio of the probability of the positive class to the probability of the negative class.

### 4. **Example: Calculating Logistic Regression Output**
   - Given:
     - Bias (\( b \)): 1
     - Weights (\( w_1, w_2, w_3 \)): 2, -1, 5
     - Input values (\( x_1, x_2, x_3 \)): 0, 10, 2
   - Step 1: Calculate \( z \):
     $$z = 1 + (2)(0) + (-1)(10) + (5)(2) = 1$$
   - Step 2: Calculate \( y' \) using the sigmoid function:
     $$y' = \frac{1}{1 + e^{-1}} \approx 0.731$$
   - Interpretation: The model predicts a 73.1% probability of the positive class.

## Key Terms
- **Logistic Regression**: A model used to predict probabilities for binary classification.
- **Sigmoid Function**: A function that maps any real number to a value between 0 and 1.
- **Log-Odds**: The logarithm of the ratio of the probability of the positive class to the probability of the negative class.
- **Binary Classification**: A problem where the output is one of two possible classes (e.g., spam or not spam).


# Logistic Regression: Loss and Regularization

## Overview
Logistic regression models are trained similarly to linear regression models, but with two key differences:
1. **Log Loss** is used instead of squared loss.
2. **Regularization** is critical to prevent overfitting.

## Key Concepts

### 1. **Log Loss**
   - **Why Log Loss?**
     - Squared loss (used in linear regression) is unsuitable for logistic regression because the sigmoid function's output changes non-linearly.
     - As the predicted probability approaches 0 or 1, small changes in the input require high precision, which squared loss cannot handle efficiently.
   - **Log Loss Formula**:
     $$\text{Log Loss} = -\frac{1}{N} \sum_{i=1}^N \left( y_i \log(y'_i) + (1 - y_i) \log(1 - y'_i) \right)$$
     - \( N \): Number of examples in the dataset.
     - \( y_i \): Actual label (0 or 1).
     - \( y'_i \): Predicted probability (between 0 and 1).
   - **Properties**:
     - Penalizes incorrect predictions more heavily as the predicted probability diverges from the actual label.
     - Ensures the model focuses on improving predictions where it is most uncertain.

### 2. **Regularization**
   - **Why Regularization?**
     - Logistic regression models can overfit, especially with a large number of features.
     - Regularization penalizes model complexity, preventing the model from driving loss to 0 by overfitting to the training data.
   - **Types of Regularization**:
     - **L2 Regularization**: Adds a penalty proportional to the square of the weights to the loss function.
     - **Early Stopping**: Limits the number of training steps to halt training while loss is still decreasing.
   - **Importance**:
     - Ensures the model generalizes well to unseen data.
     - Balances model complexity and performance.

## Key Terms
- **Log Loss**: The loss function used in logistic regression, which measures the difference between predicted probabilities and actual labels.
- **Regularization**: A technique to penalize model complexity and prevent overfitting.
- **L2 Regularization**: A type of regularization that adds a penalty proportional to the square of the weights.
- **Early Stopping**: A regularization technique that stops training when loss stops decreasing.
- **Overfitting**: When a model performs well on training data but poorly on unseen data.

## Exercise
1. **Question**: Why is Log Loss used instead of squared loss in logistic regression?
   - **Answer**: Squared loss is unsuitable for logistic regression because the sigmoid function's output changes non-linearly, requiring high precision as predictions approach 0 or 1. Log Loss handles this better by focusing on the logarithm of the error.

2. **Question**: What is the purpose of regularization in logistic regression?
   - **Answer**: Regularization prevents overfitting by penalizing model complexity, ensuring the model generalizes well to unseen data.

# Neural Networks

## Key Concepts

### 1. **Motivation for Neural Networks**
   - Neural networks excel at modeling complex, nonlinear relationships in data.
   - They can automatically learn relevant feature interactions during the training process.

### 2. **Key Components**
   - **Nodes (Neurons)**: Fundamental units that perform weighted summation of inputs and apply an activation function.
   - **Hidden Layers**: Intermediate layers of neurons that learn hierarchical representations of the input data.
   - **Activation Functions**: Nonlinear functions applied to the output of each neuron, introducing non-linearity crucial for learning complex patterns.

### 3. **Activation Functions**
   - **Sigmoid**:
     $$\sigma(x) = \frac{1}{1 + e^{-x}}$$
     - Output range: $(0, 1)$.
     - Commonly used for binary classification tasks where the output represents a probability.

   - **Tanh (Hyperbolic Tangent)**:
     $$\text{tanh}(x) = \frac{e^x - e^{-x}}{e^x + e^{-x}}$$
     - Output range: $(-1, 1)$.
     - Similar to sigmoid but centered around zero.

   - **ReLU (Rectified Linear Unit)**:
     $$\text{ReLU}(x) = \max(0, x)$$
     - Output range: $[0, \infty)$.
     - Widely used due to its simplicity and effectiveness in mitigating the vanishing gradient problem.

### 4. **Training Neural Networks (Backpropagation)**
   - An iterative optimization algorithm that uses **gradient descent** to minimize a **loss function** by adjusting the network's parameters (weights and biases).
   - The **backpropagation** algorithm efficiently computes the gradients of the loss with respect to each parameter.
   - Common challenges and mitigation strategies:
     - **Vanishing Gradients**: ReLU activation function helps maintain gradient flow.
     - **Exploding Gradients**: Techniques like **batch normalization** and careful learning rate selection can stabilize training.
     - **Dead ReLU Units**: Occur when neurons get stuck with zero output; adjusting the learning rate or using variants like LeakyReLU can help.
     - **Dropout Regularization**: A technique to reduce **overfitting** by randomly deactivating neurons during training, forcing the network to learn more robust features.

### 5. **Multi-Class Classification**
   - Handling classification problems with more than two distinct classes.
   - **One-vs.-All (OvA)**:
     - Trains multiple binary classifiers, where each classifier distinguishes one class from all other classes.
     - Typically uses a sigmoid activation in the output layer for each binary classifier.

   - **One-vs.-One (OvO)**:
     - Trains a binary classifier for each pair of classes.
     - Predictions are made by aggregating the results of all pairwise classifiers.

   - **Softmax**:
     - A function that converts a vector of raw scores into a probability distribution over multiple classes, where the probabilities sum to 1.
     - The softmax function is defined as:
       $$\text{Softmax}(z_i) = \frac{e^{z_i}}{\sum_{j=1}^{K} e^{z_j}}$$
       - Where $z_i$ is the raw score for class $i$, and $K$ is the total number of classes.

   - **Candidate Sampling**: An efficient approximation of softmax used when dealing with a very large number of output classes.

## Key Terms
- **Neural Network**: A computational model inspired by the structure and function of the human brain, composed of interconnected artificial neurons.
- **Hidden Layer**: Layers of neurons in a neural network that are not the input or output layer and learn complex intermediate representations.
- **Activation Function**: A nonlinear function applied to the output of a neuron to introduce non-linearity into the network.
- **Sigmoid/Tanh/ReLU**: Common types of activation functions with distinct output ranges and properties.
- **Backpropagation**: The algorithm used to train neural networks by propagating error gradients backward through the network to update the weights and biases.
- **Vanishing/Exploding Gradients**: Problems that can occur during the training of deep neural networks, where gradients become too small or too large, respectively, hindering learning.
- **Dropout Regularization**: A regularization technique that randomly deactivates neurons during training to prevent overfitting.
- **Multi-class Classification**: A classification problem with more than two possible class labels.
- **Softmax Function**: A function that normalizes a vector of raw scores into a probability distribution over multiple categories.

## Exercise
1. **Question**: Why can't a neural network without activation functions learn nonlinearities?
   - **Answer**: Without nonlinear activation functions, each layer in a neural network would perform a linear transformation of its input. Composing multiple linear transformations still results in a linear transformation. Therefore, the entire network would be equivalent to a single linear model, incapable of learning complex, nonlinear relationships present in most real-world data.

2. **Question**: How does the softmax function differ from sigmoid in multi-class classification?
   - **Answer**: The sigmoid function is typically used in binary classification or for independent probability estimation for multiple binary outcomes. It outputs a value between 0 and 1 for each input independently. In contrast, the softmax function is specifically designed for multi-class classification. It takes a vector of raw scores as input and transforms it into a probability distribution over all the classes, ensuring that the probabilities for all classes sum up to 1. This allows the network to directly model the likelihood of each class being the correct one.

3. **Question**: What problem does dropout regularization solve?
   - **Answer**: Dropout regularization is a technique used to address the problem of **overfitting** in neural networks. Overfitting occurs when a model learns the training data too well, including the noise and specific details, leading to poor performance on unseen data. By randomly deactivating a fraction of neurons during each training iteration, dropout prevents the network from relying too heavily on any single neuron or a small set of neurons. This encourages the network to learn more robust and generalizable features that are effective across different subsets of the network, ultimately improving the model's ability to generalize to new, unseen data.

# Embeddings

## Key Concepts

### 1. **Embeddings Overview**
   - Embeddings transform sparse, high-dimensional categorical data (e.g., one-hot encoded vectors) into dense, lower-dimensional real-valued vectors.
   - This transformation aims to capture semantic relationships between items and significantly reduces the computational complexity for subsequent machine learning tasks.

### 2. **Embedding Space**
   - The embedding space is a multi-dimensional vector space where each item is represented by its corresponding embedding vector.
   - The dimensions of this space are designed to encode underlying semantic properties or features of the items (e.g., for words, dimensions might implicitly represent concepts like "animacy," "abstractness," etc.).
   - The geometric proximity (e.g., cosine similarity, Euclidean distance) between the embedding vectors of two items in this space reflects their semantic similarity.

### 3. **Static Embeddings**
   - Static embeddings assign a single, fixed embedding vector to each unique item (e.g., each word in a vocabulary).
   - A prominent example is **word2vec**, which learns word embeddings by analyzing the local context of words in a large corpus of text.
   - **Limitation**: Static embeddings fail to capture context-dependent meanings. For instance, the word "bank" (river bank vs. financial institution) has the same embedding regardless of its usage.

### 4. **Contextual Embeddings**
   - Contextual embeddings generate different embedding vectors for an item based on its surrounding context within a given sequence (e.g., a sentence).
   - These embeddings can capture nuanced meanings and resolve polysemy by considering the relationships with other words in the context.
   - Key examples include:
     - **ELMo (Embeddings from Language Models)**: Utilizes bidirectional LSTMs to generate word embeddings that are a function of the entire input sentence. It aggregates different layers of the LSTM to capture various aspects of word meaning in context.
     - **BERT (Bidirectional Encoder Representations from Transformers)**: Employs a transformer architecture and pre-training tasks like Masked Language Modeling and Next Sentence Prediction to learn deep contextual representations.
     - **Transformer Models (e.g., GPT, Transformer XL)**: Architectures based on the attention mechanism, enabling the model to weigh the importance of different parts of the input sequence when generating embeddings for each item.

### 5. **Obtaining Embeddings**
   - **Dimensionality Reduction**: Techniques like Principal Component Analysis (PCA) can be applied to high-dimensional data to obtain lower-dimensional embeddings that preserve variance.
   - **Neural Network Training**: An **embedding layer** is a common component in neural network architectures for tasks like natural language processing and recommender systems. This layer learns the embedding vectors during the supervised training process, where the embeddings are optimized to improve performance on the specific task.
   - The dimensionality of the embedding vectors is typically chosen empirically, often based on the complexity of the data and the requirements of the downstream task.

### 6. **Applications of Embeddings**
   - **Text**: Semantic similarity analysis (e.g., finding similar documents), recommendation systems (e.g., suggesting related products based on text descriptions), machine translation, question answering.
   - **Images/Audio**: Image classification (embedding image features), similarity detection (finding visually or acoustically similar items).
   - Embeddings provide a more efficient and semantically rich representation of data, leading to improved model performance, reduced computational costs, and more effective storage.

## Key Terms
- **Embedding Vector**: A dense, low-dimensional vector representation of a categorical item.
- **Embedding Space**: The multi-dimensional vector space where embedding vectors are located, with geometric relationships reflecting semantic similarities.
- **One-hot Encoding**: A sparse, high-dimensional representation where each category is represented by a binary vector with a single '1' and the rest '0's.
- **Static Embeddings**: Embedding vectors that are fixed for each item, regardless of the context in which they appear.
- **Contextual Embeddings**: Embedding vectors that vary depending on the surrounding context of the item in a sequence.
- **Embedding Layer**: A layer in a neural network that learns to map discrete input items to dense embedding vectors.
- **BERT/ELMo**: Pre-trained deep learning models that generate high-quality contextual word embeddings.
- **Transformer Models**: Neural network architectures based on the self-attention mechanism, highly effective for processing sequential data and generating contextual embeddings.

## Exercise
1. **Question**: What are the limitations of static embeddings?
   - **Answer**: Static embeddings assign a single representation to each item, failing to capture variations in meaning based on the context in which the item appears. For example, a word with multiple senses will have the same embedding for all its uses.

2. **Question**: How do contextual embeddings improve upon static embeddings?
   - **Answer**: Contextual embeddings address the limitations of static embeddings by generating different representations for an item depending on its surrounding words or context. This allows them to capture nuanced meanings, resolve ambiguity (e.g., polysemy), and provide a more accurate semantic representation for downstream tasks.

3. **Question**: Why might embeddings created by a neural network not be intuitively understandable?
   - **Answer**: The dimensions in embeddings learned by neural networks are typically optimized algorithmically to capture statistical relationships that are beneficial for the specific task the network is trained on. These dimensions often represent complex and abstract semantic features that are not directly aligned with human intuition or easily named concepts. The network learns these features implicitly through the training process to maximize performance, rather than explicitly creating dimensions that correspond to human-understandable attributes.
  
   - 
## Reference
- Source: [Google Machine Learning Crash Course](https://developers.google.com/machine-learning/crash-course/)
