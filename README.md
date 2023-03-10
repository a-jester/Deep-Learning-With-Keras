# Deep-Learning-With-Keras

# Setup

All .ipynb files can be executed in VSCode with python3 and `Jupyter Keymap` extension

additional dependencies

```bash
$ /bin/python3 -m pip install ipykernel numpy keras tensorflow -U --user --force-reinstall
```

# Simple Neural Network Sample

This python jupyter notebook creates a simple neural network with keras that will learn how to identify handwritten
numbers. I am giving it `60,000` handwritten samples from [MNIST](http://yann.lecun.com/exdb/mnist/) that are human annotated with the correct answer. The MNIST data is separated into a training set `X_train` and a testing set `X_test` to assess performance. The Input layer consiting of a neuron for each pixel in a sample image for a total of `28 x 28 = 784 neurons`. Neurons are normalized in a range of `[0,1]` which is the intensity of the pixel divided by `255`. There are a total of 10 possible outputs, digits `0-9`. The final layer is a single neuron that implements a softmax function that squashes k-dimensional vectors of arbitrary real values into a k-dimensional vector of `[0,1]`. Once the model is defined it is then compiled and trained `200` epochs before being evaluated for the final result.

## Load Data
![Loading Data](images/load-data0.PNG "Train and Test samples loaded")

## Define the Model
![Defining the Model](images/define-model0.PNG "Model defined")

## Evaluate the Model
![Evaluating the Model](images/evaluate-model0.PNG "Model evaluated") \
The results indicate that the baseline accuracy is `92.33%` on training, `92.32%` on validation, and `92.15%` on the test.

# Improving the Neural Network Sample with Hidden Layers

The initial accuracy is good, but can be improved by adding hidden layers after the input layer. The hidden layer is not connected directly to the input or output. The first hidden layer uses Rectified Linear Unit (ReLU) which returns 0 if the input is negative, otherwise it returns the positive value back. 

## Define the Model with Hidden Layers
![Defining the Model with Hidden Layers](images/define-model1.PNG "Model defined")

## Evaluate the Model
![Evaluating the Model with Hidden Layers](images/evaluate-model1.PNG "Model evaluated") \
With the additional hidden layers, I have improved the accuracy to `96.53%` on training, `96.14%` on validation, and `96.03%` on the test.

# Further Improving the Neural Network Sample with Dropout

Dropout is another layer I can add to the process that will randomly select and discard neurons increasing the performance
and alowwing for more epoch. In this test, I increased the epoch to `250`

## Define the Model with Hidden Layers
![Defining the Model with Hidden Layers](images/define-model2.PNG "Model defined")

## Evaluate the Model
![Evaluating the Model with Hidden Layers](images/evaluate-model2.PNG "Model evaluated") \
With the added dropout, I have improved the accuracy to `98.03%` on training, `97.68%` on validation, and `97.89%` on the test.