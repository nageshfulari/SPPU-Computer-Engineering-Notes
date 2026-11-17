# Unit VI — Quick Revision
## Introduction to Neural Networks

### 1. Artificial Neural Network (ANN)

- ANN is a computing model inspired by the working of biological neural networks.
- Main building blocks: neurons, weights, bias, activation function, input/output and learning algorithm.
- A neuron calculates a weighted sum and applies an activation function.
- Weighted sum: Z = (W1 × X1) + (W2 × X2) + ... + (Wn × Xn) + b
- Output: Y = f(Z)

### 2. Types of Networks and Perceptron

- Single-Layer Network: input is connected directly to output; no hidden layer.
- Multilayer Network: contains input, one or more hidden layers and output layer.
- Perceptron: basic artificial neuron used for simple binary classification.
- Perceptron applies weights, bias, summation and an activation function.

### 3. Backpropagation

1. Initialize weights and biases.
2. Perform forward propagation.
3. Calculate prediction error using a loss function.
4. Propagate error gradients backwards through the network.
5. Update weights and biases using gradient descent.
6. Repeat until the error is sufficiently small or a stopping condition is reached.

Weight update: New Weight = Old Weight − (Learning Rate × Gradient)

### 4. Feed-Forward and Backpropagation Networks

- Feed-Forward describes information flow from input towards output without feedback loops.
- Backpropagation is a training algorithm that propagates error gradients backwards to update network weights.
- These terms describe different concepts: network information flow versus learning procedure.

### 5. Activation Functions

- Step: produces a threshold-based output.
- Binary Sigmoid: output range 0 to 1.
- Bipolar Sigmoid / Tanh-style: output range −1 to +1.
- ReLU: f(x) = max(0, x).
- Activation functions introduce non-linearity and help networks learn complex relationships.

### 6. RBF Network

- Input layer receives data.
- Hidden layer applies radial basis functions, commonly Gaussian, around selected centres.
- Output layer combines hidden activations using weights.

### 7. Functional Link ANN (FLANN)

- Expands input features using functional transformations.
- Uses direct links from expanded input to output.
- Does not require a hidden layer.
- Examples of expansion terms: x, x², sin(x), cos(x).

### 8. Recurrent Neural Network (RNN)

- Designed for sequential data.
- Recurrent connections pass hidden-state information from one time step to the next.
- Applications include sequence and time-series processing, language and speech tasks.

### 9. Convolutional Neural Network (CNN)

Typical flow:
Input Image → Convolution → Activation (ReLU) → Pooling → Flatten → Fully Connected Layer → Output

- Convolution extracts local features.
- ReLU introduces non-linearity.
- Pooling reduces spatial dimensions.
- Flatten converts feature maps into a vector.
- Fully connected layers produce final predictions.

### 10. CNN Padding

- Valid Padding: no extra pixels are added; output spatial size decreases.
- Same Padding: zeros are added around the input to preserve output spatial size (for stride 1).

### Diagrams to Revise

- [ANN Architecture](Images/ann-architecture.svg)
- [Perceptron](Images/perceptron-architecture.svg)
- [Backpropagation Flow](Images/backpropagation-flow.svg)
- [Activation Functions](Images/activation-functions.svg)
- [RBF Network](Images/rbf-network.svg)
- [FLANN Architecture](Images/flann-architecture.svg)
- [RNN Architecture](Images/rnn-architecture.svg)
- [CNN Architecture](Images/cnn-architecture.svg)
- [CNN Padding](Images/cnn-padding.svg)

**Important:** Refer to [Complete Answers](Complete-Answers.md) for the full explanations, numerical problems, tables and source wording.
