# Machine Learning – Introduction to Neural Networks

> Source: ENDSEM ML.docx supplied by the user. Answer text is transferred from the source in its original question order. Text and tables are retained where extractable; embedded diagram/formula images in the Word document may not appear in this Markdown transcription.

Q. What is an Artificial Neural Network (ANN)? Explain its architecture and building blocks with a suitable diagram.
(5–6 Marks)

1. Introduction

An Artificial Neural Network (ANN) is a computational model inspired by the structure and functioning of the human
brain.

It consists of interconnected processing units called neurons that learn patterns from data and perform tasks such as
classification, prediction and recognition.

ANN is an important concept in Artificial Intelligence and Deep Learning.

2. Architecture of Artificial Neural Network

An ANN generally consists of three main layers:

1. Input Layer

       Receives input data from the external environment.

       Each neuron represents an input feature.

       Passes the input values to the hidden layer.

2. Hidden Layer

       Performs computations on the input data.

       Contains neurons with weights, biases and activation functions.

       Learns complex patterns and relationships.

       An ANN can contain one or more hidden layers.

3. Output Layer

       Produces the final result of the network.

       Performs tasks such as classification or prediction.

       The number of output neurons depends on the problem.

3. ANN Architecture Diagram


The connections between neurons carry information through the network.

4. Building Blocks of ANN

1. Neurons

         Neurons are the basic processing units of an ANN.

         They receive inputs, perform calculations and produce outputs.

2. Weights

         Weights represent the strength of connections between neurons.

         They determine the importance of each input.

         Weights are adjusted during training.

3. Bias

         Bias is an additional parameter added to the weighted sum.

         It helps the neuron adjust its output independently of the input values.

4. Activation Function

         It determines whether a neuron should be activated.

         It introduces non-linearity into the network.

         Examples: Sigmoid, ReLU and Tanh.

5. Input and Output

         Input represents the data supplied to the network.

         Output represents the final prediction or classification result.

6. Learning Algorithm

         ANN learns by adjusting weights and biases.

         Backpropagation and Gradient Descent are commonly used during training.

5. Working of an Artificial Neuron

An artificial neuron performs the following calculation:

Step 1: Weighted Sum

Z = (W1 × X1) + (W2 × X2) + ... + (Wn × Xn) + b

Where:


       X = Input values

       W = Weights

       b = Bias

Step 2: Activation Function

Output = f(Z)

The activation function processes the weighted sum and produces the neuron's output.

6. Applications of ANN

    1. Image and face recognition.

    2. Speech recognition.

    3. Medical diagnosis.

    4. Stock market prediction.

    5. Handwriting recognition.

    6. Fraud detection.

7. Conclusion

Artificial Neural Network is a machine learning model inspired by the human brain. It consists of input, hidden and
output layers with interconnected neurons. By adjusting weights and biases during training, ANN learns complex
patterns and performs prediction and classification tasks.


Q. Explain the types of Artificial Neural Networks based on the number of layers. Explain the Perceptron concept
with a suitable diagram. (5–6 Marks)

1. Introduction

An Artificial Neural Network (ANN) is a computational model inspired by the human brain. It consists of
interconnected neurons that process information and learn patterns from data.

Based on the number of layers, neural networks are mainly classified into the following types.

2. Types of Artificial Neural Networks Based on Number of Layers

1. Single-Layer Neural Network

       It consists of an input layer and an output layer.

       There is no hidden layer between the input and output layers.

       Input neurons are directly connected to output neurons.

       It is suitable for simple problems that are linearly separable.

Example: Single-layer Perceptron.

Diagram:


2. Multilayer Neural Network

       It consists of an input layer, one or more hidden layers and an output layer.

       Hidden layers perform complex computations.

       It can learn non-linear relationships using suitable activation functions.

       It is used for complex classification and prediction problems.

Example: Multilayer Perceptron (MLP).

Diagram:


3. Perceptron

A Perceptron is the simplest type of artificial neuron and is considered the basic building block of a neural network.

It is a supervised learning algorithm used for binary classification. It receives input values, multiplies them by
corresponding weights, adds a bias and applies an activation function to produce the output.

4. Architecture of Perceptron

A perceptron consists of the following components:

    1. Input: Receives input values such as X1, X2 and X3.

    2. Weights: Represent the importance of each input.

    3. Bias: Helps adjust the output of the neuron.

    4. Summation Function: Calculates the weighted sum of inputs.

    5. Activation Function: Determines the final output based on the calculated sum.

Perceptron Diagram:


5. Working of Perceptron

Step 1: Receive Inputs

The perceptron receives input values X1, X2, ..., Xn.

Step 2: Apply Weights

Each input is multiplied by its corresponding weight.

Step 3: Calculate Weighted Sum

Z = (W1 × X1) + (W2 × X2) + ... + (Wn × Xn) + b

Step 4: Apply Activation Function

The perceptron generally uses a Step Activation Function.

Output = 1, if Z ≥ 0

Output = 0, if Z < 0

Step 5: Learning

The perceptron adjusts its weights and bias based on prediction errors during training.

6. Applications of Perceptron

    1. Binary classification.

    2. Simple pattern recognition.

    3. AND and OR logic gate implementation.

    4. Basic decision-making systems.

7. Conclusion

Artificial Neural Networks can be classified into Single-Layer and Multilayer Neural Networks based on their layer
structure. A Perceptron is a basic artificial neuron that uses weighted inputs, bias and an activation function to
perform binary classification.


Q. Explain the Backpropagation Algorithm in Artificial Neural Networks. Describe its characteristics and
importance. (6–8 Marks)

1. Introduction

Backpropagation is a supervised learning algorithm used to train Artificial Neural Networks (ANNs), especially
Multilayer Perceptrons (MLPs).


It works by calculating the error between the predicted output and the actual output and propagating this error
backwards through the network to update weights and biases.

Its main objective is to minimize the network's prediction error.

2. Working of Backpropagation Algorithm

Backpropagation works in the following steps:

Step 1: Initialize Weights and Biases

       Assign small random values to weights and biases.

       These values are adjusted during training.

Step 2: Forward Propagation

       Pass input data through the input layer.

       Calculate the weighted sum at each neuron.

       Apply activation functions.

       Generate the predicted output.

Weighted Sum:

Z = (W1 × X1) + (W2 × X2) + b

Output = f(Z)

Step 3: Calculate Error

Compare the predicted output with the actual output using a loss function.

For example, Mean Squared Error:

MSE = (Actual Output - Predicted Output)²

Step 4: Backward Propagation

       Calculate the error at the output layer.

       Propagate the error backwards through the hidden layers.

       Calculate the contribution of each weight and bias to the total error using the chain rule of differentiation.

Step 5: Update Weights and Biases

Adjust weights and biases using Gradient Descent to reduce the error.

Weight Update:

New Weight = Old Weight - (Learning Rate × Gradient)

Step 6: Repeat the Process

       Repeat forward and backward propagation for multiple iterations.

       Continue until the error becomes sufficiently small or the maximum number of training iterations is reached.

3. Backpropagation Flowchart


4. Characteristics of Backpropagation

   1. Supervised Learning: Requires input data along with corresponding target outputs.

   2. Error-Based Learning: Uses prediction error to improve network performance.

   3. Backward Error Propagation: Propagates error from the output layer towards the input layer.

   4. Weight Adjustment: Updates weights and biases using calculated gradients.

   5. Gradient-Based Optimization: Commonly uses Gradient Descent to minimize the loss function.

   6. Iterative Process: Repeats training until the desired error level is achieved.

   7. Multilayer Network Support: Enables training of networks containing multiple hidden layers.

5. Importance of Backpropagation

   1. Improves Accuracy: Reduces prediction errors by adjusting network parameters.

   2. Enables Deep Learning: Makes training multilayer neural networks possible.


    3. Learns Complex Patterns: Helps networks learn non-linear relationships in data.

    4. Efficient Training: Uses gradients to determine how weights should be updated.

    5. Wide Applications: Supports image recognition, speech recognition and prediction systems.

6. Advantages and Limitations

Advantages:

       Easy to implement with gradient-based optimization.

       Efficiently calculates gradients for network parameters.

       Helps train complex multilayer neural networks.

Limitations:

       Training can be computationally expensive for large networks.

       May suffer from vanishing or exploding gradients.

       Performance depends on learning rate and network architecture.

       Can overfit training data without suitable regularization.

7. Conclusion

Backpropagation is an important algorithm for training Artificial Neural Networks. It calculates prediction errors and
propagates them backwards to update weights and biases. It helps neural networks learn complex patterns and
improve prediction accuracy.


Q. Why is the Backpropagation Algorithm required in a Multilayer Neural Network? Explain its role in network
learning. (6 Marks)

1. Introduction

Backpropagation is a supervised learning algorithm used to train Multilayer Neural Networks (MLNs).

In a multilayer neural network, information passes through multiple hidden layers, making it difficult to determine
how much each weight contributes to the final prediction error.

Backpropagation solves this problem by calculating the error gradients and adjusting the weights and biases to
minimize the error.

2. Why is Backpropagation Required?

Backpropagation is required in multilayer neural networks for the following reasons:

    1. Error Calculation: It calculates the difference between the predicted output and the actual output.

    2. Weight Adjustment: It determines how much each weight contributes to the prediction error.

    3. Hidden Layer Training: It propagates error information backwards through hidden layers, allowing their
       weights to be updated.

    4. Error Minimization: It helps minimize the network's loss using gradient-based optimization.

    5. Learning Complex Patterns: It enables multilayer networks to learn complex and non-linear relationships.

    6. Improved Accuracy: Repeated weight updates improve the network's prediction performance.


3. Role of Backpropagation in Network Learning

Backpropagation plays an important role in the learning process through the following steps:

Step 1: Initialize Weights and Biases

Assign small random values to weights and biases of the neural network.

Step 2: Forward Propagation

       Input data is passed through the input layer.

       Hidden layers perform weighted calculations and apply activation functions.

       The output layer generates the predicted result.

Step 3: Calculate Error

Compare the predicted output with the actual output using a loss function.

Error = Actual Output - Predicted Output

Step 4: Backward Propagation

       Calculate the error gradient at the output layer.

       Propagate the gradients backwards through hidden layers.

       Use the chain rule to determine how each weight affects the total error.

Step 5: Update Weights and Biases

Update the weights and biases using Gradient Descent.

New Weight = Old Weight - (Learning Rate × Gradient)

Step 6: Repeat Learning Process

Repeat forward propagation and backward propagation until the error becomes sufficiently small or the stopping
condition is reached.

4. Diagram of Backpropagation in Multilayer Neural Network


The forward direction produces predictions, while the backward direction calculates gradients used to update
weights.

5. Importance of Backpropagation


      1. Makes training of multilayer neural networks possible.

      2. Helps networks learn from prediction errors.

      3. Improves classification and prediction accuracy.

      4. Supports complex pattern recognition.

      5. Provides an efficient method for calculating gradients of network parameters.

6. Conclusion

Backpropagation is essential for training multilayer neural networks because it calculates prediction error gradients
and updates weights and biases across all layers. It enables the network to learn complex patterns and gradually
improve its performance.


Q. Differentiate between Backpropagation Networks and Feed-Forward Networks. (5 Marks)

1. Introduction

A Feed-Forward Network (FFN) is an artificial neural network in which information flows only in the forward
direction, from the input layer to the output layer.

A Backpropagation Network (BPN) is a neural network trained using the backpropagation learning algorithm. It
calculates the output error and propagates it backward to update weights and biases.

2. Difference Between Backpropagation Networks and Feed-Forward Networks

Sr.
        Backpropagation Network (BPN)                              Feed-Forward Network (FFN)
No.

                                                                   It describes a network architecture in which data
1.      It uses the backpropagation algorithm for training.
                                                                   flows forward only.

        Error is propagated backward from the output layer to      Information flows from the input layer towards the
2.
        hidden layers during training.                             output layer.

        Weights are updated using calculated errors and            Forward propagation alone does not specify how
3.
        gradients.                                                 weights are updated.

        It generally consists of input, one or more hidden layers, It can consist of input, hidden and output layers, or
4.
        and output layers.                                         only input and output layers.

        It is commonly used for supervised learning and error      It is used for tasks such as classification and
5.
        minimization.                                              regression.

        Training involves forward propagation and backward         Its normal operation involves forward propagation
6.
        error propagation.                                         only.

3. Simple Diagrams

A. Feed-Forward Network


B. Backpropagation Network


4. Conclusion

A Feed-Forward Network describes the direction of information flow in a neural network, whereas a Backpropagation
Network refers to a network trained using the backpropagation algorithm to minimize prediction error.


Q. Explain different Activation Functions used in Neural Networks. Discuss their role and importance with
examples. (5–6 Marks)

1. Introduction

An activation function is a mathematical function applied to the weighted sum of inputs in an artificial neuron. It
determines whether and how strongly a neuron should be activated.

It introduces non-linearity into a neural network, allowing it to learn complex patterns and relationships.

The output of a neuron is:

Y = f(Z)

Where:

          Z = Σ(Wi × Xi) + b

          Wi = Weights

          Xi = Input values

          b = Bias


        f(Z) = Activation function

2. Different Activation Functions

1. Binary Step Function

        Produces either 0 or 1 depending on a threshold.

        If the input is greater than or equal to zero, output is 1; otherwise, output is 0.

        Mainly used in simple perceptron models.

Example:

f(Z) = 1, if Z >= 0

f(Z) = 0, if Z < 0

Output is either 0 or 1.

2. Sigmoid Function

        Converts input values into a range between 0 and 1.

        Commonly used in binary classification output layers.

        Its output can be interpreted as a probability.

Formula:


Example: If output is 0.9, it indicates a high probability of the positive class.

3. Tanh (Hyperbolic Tangent) Function

        Converts input values into a range between -1 and +1.

        Its output is zero-centred.

        It is useful in some neural network hidden layers.

Formula:


Example: Output of -0.8 represents a negative activation, while +0.8 represents a positive activation.

4. ReLU (Rectified Linear Unit)

        Produces zero for negative inputs and returns the input itself for positive inputs.

        It is widely used in hidden layers of deep neural networks.

        It is computationally simple and helps reduce the vanishing gradient problem compared with sigmoid and
         tanh in many cases.

Formula:

f(Z) = max(0, Z)

Example:

        If Z = -3, output = 0.


          If Z = 5, output = 5.

5. Softmax Function

          Converts a vector of values into probabilities.

          The sum of all output probabilities is 1.

          Commonly used in the output layer for multiclass classification.

Formula:


Example: For classifying an image into Cat, Dog and Bird, Softmax may produce:

Class Probability

Cat       0.70

Dog 0.20

Bird 0.10

Total 1.00

The network predicts Cat because it has the highest probability.

3. Comparison of Activation Functions

Activation Function Output Range Common Application

Binary Step              0 or 1           Simple perceptron

Sigmoid                  0 to 1           Binary classification

Tanh                     -1 to +1         Hidden layers in some networks

ReLU                     0 to infinity    Hidden layers in deep networks

Softmax                  0 to 1 (sum = 1) Multiclass classification

4. Role and Importance of Activation Functions

      1. Introduces non-linearity: Helps neural networks learn complex relationships.

      2. Controls neuron output: Determines the output produced by each neuron.

      3. Improves learning: Differentiable activation functions support gradient-based training.

      4. Supports classification: Sigmoid and Softmax help generate probability-based outputs.

      5. Improves network performance: Choosing a suitable activation function can improve learning speed and
         prediction performance.

5. Conclusion

Activation functions are essential components of neural networks. They introduce non-linearity and help networks
learn complex patterns. ReLU is commonly used in hidden layers, Sigmoid in binary classification and Softmax in
multiclass classification.


Q. Solve a numerical problem to calculate the output of a neuron using Binary Sigmoidal and Bipolar Sigmoidal
activation functions. (6 Marks)

1. Given Data

Consider a neuron with the following inputs, weights and bias:

Parameter Value

Input X1    0.5

Input X2    0.8

Weight W1 0.4

Weight W2 0.6

Bias (b)    0.2

Calculate the neuron's output using:

    1. Binary Sigmoidal Activation Function

    2. Bipolar Sigmoidal Activation Function


Activation Function Calculated Output Output Range

Binary Sigmoidal     0.707               0 to 1

Bipolar Sigmoidal    0.414               -1 to +1

6. Conclusion

For the same net input of 0.88, the Binary Sigmoidal function produces an output of approximately 0.707, while the
Bipolar Sigmoidal function produces approximately 0.414. Both functions convert the net input into a limited output
range.


Q. Explain the architecture and building blocks of Radial Basis Function (RBF) Networks. (6–8 Marks)

1. Introduction

A Radial Basis Function Network (RBFN) is a type of artificial neural network that uses radial basis functions as
activation functions in its hidden layer.

It is commonly used for function approximation, classification, prediction and pattern recognition.

An RBF network generally consists of three layers:

    1. Input Layer

    2. Hidden Layer

    3. Output Layer

2. Architecture of RBF Network

The architecture of an RBF network is shown below:


Working of each layer:

1. Input Layer

        Receives input data from the dataset.

        Passes input values directly to the hidden layer.

        Does not perform complex computations.

2. Hidden Layer

        Contains radial basis function neurons.

        Each neuron has a centre and a spread (width).

        Calculates the distance between the input vector and its centre.

        Applies a radial basis activation function, commonly Gaussian.

3. Output Layer

        Receives outputs from the hidden layer.

        Combines them using weighted connections.

        Produces the final network output.

3. Building Blocks of RBF Network

1. Input Vector

        Represents the input features supplied to the network.

        Example: For predicting house prices, inputs may include area, number of rooms and location score.

2. Radial Basis Function (RBF)

        It is the activation function used in the hidden layer.

        Its output depends on the distance between the input and the centre of the neuron.

        Gaussian function is the most commonly used RBF.

Gaussian RBF formula:


Where:


        x = Input vector

        c = Centre of the RBF neuron

        σ = Spread or width parameter

        ||x - c|| = Euclidean distance between input and centre

3. Centre

        Each hidden neuron has a centre that represents a reference point in the input space.

        Centres are commonly selected using clustering techniques such as K-Means.

4. Spread (Width)

        Controls how far the influence of an RBF neuron extends.

        A small spread gives a narrow response.

        A large spread gives a wider response.

5. Weights

        Each hidden neuron is connected to the output neuron through a weight.

        Weights determine the contribution of each hidden neuron to the final output.

6. Output Function

The final output is calculated by combining the hidden-layer activations with their weights.

Y = Σ(Wi × φi(x)) + b

Where:

        Wi = Output weight

        φi(x) = Output of the ith RBF neuron

        b = Bias

4. Working of RBF Network

    1. The input layer receives the input data.

    2. The hidden layer calculates the distance between the input and each RBF centre.

    3. The Gaussian activation function calculates the response of each hidden neuron.

    4. The output layer multiplies each activation by its corresponding weight.

    5. All weighted outputs are added to generate the final prediction.

5. Applications of RBF Networks

    1. Pattern recognition and classification.

    2. Function approximation.

    3. Time-series prediction.

    4. Image and speech recognition.

    5. Control systems and forecasting.

6. Advantages of RBF Networks


    1. Faster training compared with some multilayer neural networks.

    2. Good performance in function approximation.

    3. Simple three-layer architecture.

    4. Can learn nonlinear relationships.

    5. Hidden-layer responses are localized around their centres.

7. Conclusion

Radial Basis Function Networks are three-layer neural networks that use radial basis functions in the hidden layer.
Their performance depends on the selection of centres, spread values and output weights. They are useful for
classification, prediction and function approximation.


Q. What is Functional Link Artificial Neural Network (FLANN)? Explain its architecture and advantages. (5 Marks)

1. Introduction

A Functional Link Artificial Neural Network (FLANN) is a type of single-layer neural network that improves its
learning capability by expanding the input features using mathematical functions.

Unlike traditional multilayer neural networks, FLANN does not require hidden layers. It uses functional expansion of
input data to learn complex nonlinear relationships.

2. Architecture of FLANN

The architecture of FLANN consists of three main components:

    1. Input Layer

    2. Functional Expansion Block

    3. Output Layer

Block Diagram:


3. Building Blocks of FLANN

1. Input Layer

        Receives the original input features from the dataset.

        Passes the input values to the functional expansion block.

2. Functional Expansion Block

        Expands the original inputs using mathematical functions.

        Generates additional features to represent nonlinear relationships.

        Common expansion functions include:

             o    Polynomial functions

             o    Sine functions

             o    Cosine functions

             o    Power functions

Example:

For an input X, the expanded input may be:

X, X², X³, sin(X), cos(X)

3. Weight Layer

        Each expanded input is multiplied by a corresponding weight.

        Weights are adjusted during training to reduce prediction error.

4. Output Layer

        Combines the weighted expanded inputs.

        Produces the final output of the network.


Output equation:


Where:

        Fi = Functionally expanded input

        Wi = Corresponding weight

        b = Bias

4. Advantages of FLANN

    1. Simple Architecture: Does not require hidden layers.

    2. Less Computational Complexity: Has a relatively simple network structure.

    3. Faster Training: Can require less training time than conventional multilayer networks in suitable problems.

    4. Nonlinear Learning: Functional expansion helps learn complex nonlinear relationships.

    5. Easy Implementation: Its architecture and learning process are comparatively simple.

    6. Reduced Network Complexity: Avoids the need to design multiple hidden layers.

5. Applications of FLANN

        Signal processing.

        Pattern recognition.

        System identification.

        Prediction and forecasting.

        Communication systems.

6. Conclusion

FLANN is a single-layer neural network that uses mathematical functional expansion to transform input features into
a higher-dimensional representation. It can learn nonlinear relationships without requiring hidden layers, making its
architecture comparatively simple.


Q. What is a Recurrent Neural Network (RNN)? Explain its architecture, working, applications and suitable
example. (5–6 Marks)

1. Introduction

A Recurrent Neural Network (RNN) is a type of artificial neural network designed to process sequential data. It has
feedback connections that allow information from previous time steps to influence the current output.

Unlike a traditional feed-forward neural network, an RNN maintains a memory of previous inputs using a hidden
state.

It is commonly used for text processing, speech recognition and time-series prediction.

2. Architecture of RNN


An RNN consists of three main components:

    1. Input Layer: Receives sequential input data at each time step.

    2. Hidden Layer: Maintains information from previous time steps and combines it with the current input.

    3. Output Layer: Produces the output based on the hidden state.

Simple RNN Architecture:


The hidden state carries information from one time step to the next.

3. Working of RNN

    1. Input Processing: The network receives the first input at time step 1.

    2. Hidden State Calculation: It processes the input and generates a hidden state.

    3. Memory Transfer: The hidden state is passed to the next time step as information from the previous input.

    4. Next Input Processing: The network combines the current input with the previous hidden state.

    5. Output Generation: The output layer generates the result at each time step or after processing the complete
       sequence.

    6. Weight Updating: During training, the network adjusts its weights using Backpropagation Through Time
       (BPTT).

The hidden state is calculated as:

ht = f(Whh × h(t-1) + Wxh × xt + bh)

Where:

        ht = Current hidden state

        h(t-1) = Previous hidden state

        xt = Current input

        Whh = Hidden-to-hidden weight

        Wxh = Input-to-hidden weight

        bh = Bias

        f = Activation function

4. Suitable Example: Next Word Prediction

Consider the sentence:


"I love machine learning"

An RNN processes the words sequentially:

Time Step Input Word Information Retained

1          I             Remembers "I"

2          love          Remembers "I love"

3          machine       Remembers "I love machine"

After processing the sequence, the RNN can predict the next word, such as "learning", based on the previous words.

This demonstrates how an RNN uses information from earlier inputs to predict the next output.

5. Applications of RNN

    1. Natural Language Processing: Text generation and language modelling.

    2. Speech Recognition: Converting spoken language into text.

    3. Machine Translation: Translating sentences from one language to another.

    4. Time-Series Prediction: Predicting stock prices, weather and sales.

    5. Sentiment Analysis: Identifying positive or negative opinions in text.

    6. Handwriting Recognition: Recognizing handwritten sequential characters.

6. Advantages of RNN

    1. Can process sequential data of varying lengths.

    2. Maintains information from previous inputs.

    3. Shares network weights across time steps.

    4. Useful for sequence prediction and language-related tasks.

7. Conclusion

Recurrent Neural Networks are designed to process sequential data by maintaining information through hidden
states. They are widely used in language processing, speech recognition, machine translation and time-series
prediction.


Q. What is a Convolutional Neural Network (CNN)? Explain its architecture and working with a suitable example. (6
Marks)

1. Introduction

A Convolutional Neural Network (CNN) is a type of deep learning neural network mainly designed to process and
analyze image data.

It automatically extracts important features such as edges, shapes, textures and objects from images using
convolutional filters.

CNNs are widely used in image classification, object detection and facial recognition.

2. Architecture of CNN


A CNN generally consists of the following layers:

    1. Input Layer

    2. Convolutional Layer

    3. Activation Function (ReLU)

    4. Pooling Layer

    5. Flattening Layer

    6. Fully Connected Layer

    7. Output Layer

CNN Architecture Diagram:


3. Components of CNN

1. Input Layer

       Receives the input image in the form of pixel values.

       An image is represented using height, width and channels.

       Example: An RGB image of 64 × 64 pixels has three colour channels.

2. Convolutional Layer

       It is the main feature extraction layer of CNN.

       Applies small filters (kernels) to the input image.

       Detects features such as edges, corners, textures and patterns.

       Produces feature maps.

3. ReLU Activation Layer


       Introduces non-linearity into the network.

       Converts negative values into zero and keeps positive values unchanged.

Formula:

f(x) = max(0, x)

4. Pooling Layer

       Reduces the spatial dimensions of feature maps.

       Decreases computational complexity.

       Max Pooling selects the maximum value from a region.

Example:

Input Region       Max Pooling Output


1 3         6

2 6

5. Flattening Layer

       Converts the two-dimensional feature maps into a one-dimensional vector.

       Passes the extracted features to the fully connected layer.

6. Fully Connected Layer

       Connects extracted features to neurons.

       Performs classification based on the learned features.

7. Output Layer

       Produces the final prediction.

       Softmax is commonly used for multiclass classification.

4. Working of CNN

    1. Image Input: The input image is supplied to the CNN.

    2. Feature Extraction: Convolution filters detect important image features.

    3. Activation: ReLU removes negative values and introduces non-linearity.

    4. Pooling: Reduces the size of feature maps while retaining important information.

    5. Flattening: Converts feature maps into a one-dimensional vector.

    6. Classification: Fully connected layers process the extracted features.

    7. Prediction: The output layer predicts the image category.

5. Suitable Example: Image Classification

Consider a CNN trained to classify images into two categories: Cat and Dog.


CNN Stage          Operation


Input               Image of a cat or dog

Convolution         Detects edges, ears, eyes and other features

ReLU                Introduces non-linearity

Pooling             Reduces feature map dimensions

Flattening          Converts features into a vector

Fully Connected Identifies patterns for classification

Output              Predicts Cat or Dog

Example output:

Class Probability

Cat       0.92

Dog 0.08

The CNN classifies the image as Cat because it has the highest probability.

6. Applications of CNN

      1. Image classification and recognition.

      2. Face detection and facial recognition.

      3. Medical image analysis, such as tumour detection.

      4. Self-driving cars and object detection.

      5. Handwritten digit recognition.

      6. Video surveillance and analysis.

7. Conclusion

CNN is a powerful deep learning model used mainly for image processing. It automatically extracts features through
convolution and pooling layers and performs classification using fully connected layers.


Q. Explain the different layers used in CNN. (6 Marks)

1. Introduction

A Convolutional Neural Network (CNN) is a deep learning model mainly used for image processing and computer
vision. It consists of different layers that extract features from input images and use them to perform classification or
prediction.

2. Different Layers Used in CNN

1. Input Layer

          It receives the input image in the form of pixel values.

          An image is represented using height, width and colour channels.

          Example: An RGB image of size 64 × 64 has three colour channels.


2. Convolutional Layer

       It is the main feature extraction layer of CNN.

       It applies small filters (kernels) to the input image.

       It detects features such as edges, corners, shapes and textures.

       The output generated is called a feature map.

3. ReLU Activation Layer

       ReLU stands for Rectified Linear Unit.

       It introduces non-linearity into the network.

       It converts negative values into zero and keeps positive values unchanged.

Formula:

f(x) = max(0, x)

Example:

       If x = -5, output = 0.

       If x = 4, output = 4.

4. Pooling Layer

       It reduces the spatial dimensions of feature maps.

       It reduces computational complexity and helps retain important features.

       Two common types are:

             o     Max Pooling: Selects the maximum value from a region.

             o     Average Pooling: Calculates the average value of a region.

Example of Max Pooling:


5. Flattening Layer

       It converts the two-dimensional feature maps into a one-dimensional vector.

       It prepares extracted features for the fully connected layer.

Example:


6. Fully Connected Layer

       It connects each neuron to the neurons of the previous layer.

       It processes the extracted features to identify patterns.


       It performs classification based on the learned features.

7. Output Layer

       It produces the final prediction or classification.

       Sigmoid is commonly used for binary classification.

       Softmax is commonly used for multiclass classification.

Example: For an image containing a cat or dog, the output layer predicts the most likely class.

3. Overall CNN Layer Architecture


4. Conclusion

Each CNN layer performs a specific function. Convolution and ReLU layers extract useful features, pooling reduces
dimensions, flattening converts feature maps into a vector, and fully connected and output layers perform the final
classification.


Q. What is Padding in CNN? Explain the different types of padding with suitable examples. (6 Marks)

1. Introduction

Padding in a Convolutional Neural Network (CNN) is the process of adding extra pixels, usually zeros, around the
borders of an input image before applying a convolution operation.

It is used to control the output feature map size and preserve information near the image boundaries.

2. Types of Padding in CNN

There are mainly two commonly used types of padding:


1. Valid Padding (No Padding)

        In valid padding, no extra pixels are added around the input image.

        The convolution filter operates only on positions where it completely fits inside the input.

        As a result, the output feature map becomes smaller than the input.

Example:

Consider a 5 × 5 input image and a 3 × 3 filter with stride 1.

Output size:

Output = (5 - 3) + 1 = 3

Therefore, output feature map size = 3 × 3.


2. Same Padding (Zero Padding)

        In same padding, extra pixels (usually zeros) are added around the input image.

        It is used to maintain the same spatial dimensions of input and output when stride = 1.

        It helps preserve information near image boundaries.

Example:

Consider a 5 × 5 input image and a 3 × 3 filter with stride 1.

One row and one column of zeros are added around the input (one pixel on each side).

Output size = 5 × 5.


3. Difference Between Valid and Same Padding

Sr. No. Valid Padding                                            Same Padding

1.       No extra pixels are added.                              Extra pixels are added around the input.


                                                                  Output size remains the same as input when stride =
2.       Output size is smaller than input size.
                                                                  1.

3.       Border information may be used less frequently.          Helps preserve information near image boundaries.

4.       No additional padding computation is required.           Additional padded values are processed.

         Used when reducing feature map dimensions is
5.                                                                Used when maintaining spatial dimensions is desired.
         desired.

4. Importance of Padding

      1. Controls the output feature map dimensions.

      2. Helps preserve information near image boundaries.

      3. Allows deeper CNN architectures without rapidly reducing feature map size.

      4. Provides control over spatial dimensions during convolution.

      5. Helps filters process edge and corner regions.

5. Conclusion

Padding is an important operation in CNN that controls the spatial size of feature maps. Valid padding does not add
extra pixels and reduces output dimensions, whereas same padding adds zeros to maintain the output dimensions
when stride is 1.


Q. Differentiate between Recurrent Neural Networks (RNN) and Convolutional Neural Networks (CNN). (6 Marks)

1. Introduction

Recurrent Neural Network (RNN): RNN is a type of neural network designed to process sequential data. It maintains
information from previous inputs using hidden states.

Convolutional Neural Network (CNN): CNN is a type of deep learning network mainly designed to process image
data. It extracts features using convolutional filters.

2. Difference Between RNN and CNN

Sr.
        RNN                                                         CNN
No.

1.      RNN stands for Recurrent Neural Network.                    CNN stands for Convolutional Neural Network.

2.      Mainly used for sequential data.                            Mainly used for image and spatial data.

        Uses recurrent connections to maintain information from Uses convolutional filters to extract features from
3.
        previous time steps.                                    input data.

        Contains input, hidden and output layers with recurrent     Contains convolutional, pooling, fully connected
4.
        connections.                                                and output layers.

5.      Processes sequential inputs, often one time step at a time. Processes local regions of an image using filters.

6.      Maintains a hidden state that acts as memory.               Uses feature maps to represent extracted features.

        Commonly trained using Backpropagation Through Time         Commonly trained using backpropagation and
7.
        (BPTT).                                                     gradient descent.


         Used in text generation, speech recognition and time-     Used in image classification, object detection and
8.
         series prediction.                                        facial recognition.

3. Architecture Diagrams

A. Recurrent Neural Network (RNN)


B. Convolutional Neural Network (CNN)


4. Suitable Examples

         RNN Example: Predicting the next word in a sentence by considering previously entered words.

         CNN Example: Identifying whether an image contains a cat or a dog by extracting visual features.

5. Conclusion

RNN and CNN are important neural network architectures used for different types of data. RNN is suitable for
sequential data because it maintains previous information, whereas CNN is suitable for image processing because it
automatically extracts spatial features.
