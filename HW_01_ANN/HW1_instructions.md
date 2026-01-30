Problem 1 (5 points)

Goal: Build and train an artificial neural network for a binary classification task. 

You are encouraged to use PyTorch, TensorFlow or the Keras API, but any other deep learning library (in Python, Julia or Matlab) would be acceptable for this homework assignment.

Data: The input data and their corresponding binary labels are provided in the data file, hw1data.dat Download hw1data.dat. The input data contains 1000 two-dimensional data points that lie within a square of area one. The input data and labels should be loaded by reading the data file using any choice of library. Please note that for binary classification, the -1/1 labels need to be converted into 0/1 labels.

Architecture: A typical neural network consists of densely connected layers also called fully connected layers. It means all the inputs are connected to the outputs. Define a Sequential model, wherein the layers are stacked sequentially and each layer has exactly one input tensor and one output tensor. Please build an artificial neural network by adding the following layers to the Sequential model using the configuration below.

- Input - Shape 2
- Dense - Units 5
- Dense - Units 1 - Activation Sigmoid

The initial random weights of layers can be defined by specifying weight and bias initializers. For each of the above layers, initialize the kernel weights from a Xavier/Glorot uniform distribution and set the random seed to 99. Additionally, initialize the bias vector as a zero vector. The activation function defines the node output given a set of inputs. An appropriate choice of activation function is required to allow the artificial neural network to learn a non-linear pattern. The activation functions for the first dense layer can be chosen from some of the commonly used activation functions like Rectified Linear Unit (ReLU), Hyperbolic Tangent (tanh), and Sigmoid.

Training: The model is compiled by specifying the optimizer, the loss function and metrics to be recorded at each step of the training process. For binary classification, it is a common practice to use binary cross-entropy as loss function. Popular deep learning libraries provide support for several optimization algorithms. Some of them are Stochastic gradient descent (SGD), RMSprop, ADAM. Please choose accuracy as a metric during model compilation. Finally, train the artificial neural network by fitting the input data and labels with each of the aforementioned optimizers and their respective configuration as given in the table below. The neural network should be trained until convergence is achieved.

Deliverables:

Please report the training accuracy after the training process is carried out for _every combination_ of activation function and optimizer.
Plot the loss curves to determine the number of epochs required to achieve convergence.
Report the hyperparameter tuning step.
Predict and report the binary classification results for the data point [0.8, 0.2] with the trained artificial neural network.
Discuss the influence of particular parameters on different optimizers.
It is recommended that the final results be reported in a tabular format as shown below. Please also make sure to submit your working code files along with the final results.

| Optimizer | Activation function | Required epochs | Training accuracy (%) | Prediction for [0.8, 0.2] |
|-----------|---------------------|-----------------|------------------------|----------------------------|
| SGD (Learning rate = 0.01, Momentum = [0.0, 0.1, 0.5, 0.9], discuss the impact of momentum values on the convergence behavior of the SGD optimizer) | ReLU | | | |
| SGD (Learning rate = 0.01, Momentum = [0.0, 0.1, 0.5, 0.9], discuss the impact of momentum values on the convergence behavior of the SGD optimizer) | Tanh | | | |
| SGD (Learning rate = 0.01, Momentum = [0.0, 0.1, 0.5, 0.9], discuss the impact of momentum values on the convergence behavior of the SGD optimizer) | Sigmoid | | | |
| RMSprop (Learning rate = [0.0001, 0.001, 0.01], discuss the effect of learning rates on learning curves, Epsilon = 10^-6) | ReLU | | | |
| RMSprop (Learning rate = [0.0001, 0.001, 0.01], discuss the effect of learning rates on learning curves, Epsilon = 10^-6) | Tanh | | | |
| RMSprop (Learning rate = [0.0001, 0.001, 0.01], discuss the effect of learning rates on learning curves, Epsilon = 10^-6) | Sigmoid | | | |
| ADAM (β₁=[0.85, 0.9], β₂=[0.95, 0.99], discuss the functions of the parameters β₁ and β₂) | ReLU | | | |
| ADAM (β₁=[0.85, 0.9], β₂=[0.95, 0.99], discuss the functions of the parameters β₁ and β₂) | Tanh | | | |
| ADAM (β₁=[0.85, 0.9], β₂=[0.95, 0.99], discuss the functions of the parameters β₁ and β₂) | Sigmoid | | | |

Problem 2 (5 points)

Data: Given the following data points:

- Positive class (+1): (1,3)
- Negative class (-1): (-1,4)

Task: Determine the number of updates until convergence using the perceptron algorithm. You must iterate over data points in the order: [(1,3),(-1,4)]. Your output should be the sequence of updates in the form $\mathbf{w}_i = [w_1,..,w_n]$

You are only allowed to use basic mathematical tools (such as numpy in Python, MATLAB's basic functions, etc.).

Deliverables: Please show your work step by step and plot the points and final decision boundary.

**Perceptron Algorithm:**

1. **Input:** Training data set: $\{(x_1, y_1), \ldots, (x_N, y_N)\}$

2. **Initialization:**
   - Weight vector: $\mathbf{w}^{(s)} = [0, \ldots, 0]$
   - Iteration count: $s = 0$

3. **Update Loop:**
   - While there exists an instance $i \in [N]$ such that the prediction is incorrect, i.e., $y \, \mathbf{w}^{(s)} \cdot \mathbf{x} \leq 0$:
   - Update weight:
     - For positive instances: $\mathbf{w}^{(s+1)} = \mathbf{w}^{(s)} + \mathbf{x}$
     - For negative instances: $\mathbf{w}^{(s+1)} = \mathbf{w}^{(s)} - \mathbf{x}$
   - Increment counter: $s = s + 1$

4. **Output:** Final weight vector: $\mathbf{w}^{(s)}$
