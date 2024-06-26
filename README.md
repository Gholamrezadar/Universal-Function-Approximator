# Shallow NNs are Universal Function Approximators!

In this educational project, I'm going to explore the capabilities of shallow neural networks (NNs) as universal function approximators. I'll start by showing how a simple NN with n neurons is a piecewise linear function with n joints and n+1 pieces. Then, I'll demonstrate how a shallow NN can approximate any continuous function (sin(x) for example) to any desired degree of accuracy.

![what is a snn](images/snn.png)

Read this book for more information: [Understanding Deep Learning](https://udlbook.github.io/udlbook/)

## Manual Shallow NN
Here you can see that each neuron models a line. 

When these lines are passed through ReLU activation functions, then multiplied by some weights, and finally summed, they can create a piecewise linear function. **ANY PIECEWISE LINEAR FUNCTION!**

![mr1](images/manual_relu_1.png)

![mr1w](images/manual_relu_1_w.png)

Summing `w0 + w1*ReLU(h1) + w2*ReLU(h2) + w3*ReLU(h3)` we get y.

![mr1y](images/manual_relu_1_y.png)

It's a piecewise linear function constructed from 4 segments (black curve). Dashed lines show the x in which each neuron crossed the x-axis. these points create the joints in our resulting function.

**3 neurons, 3 joints, 4 segments.**


## Manual Shallow NN (Another Function)
![mr2](images/manual_relu_2.png)

![mr2w](images/manual_relu_2_w.png)

![mr2y](images/manual_relu_2_y.png)

As we can see, by changing the parameters(10 in this case) we can model any function that can be constructed using 4(3+1) linear segments.


## Identity instead of ReLU
Shows the importance of non-linearity

![mi](images/manual_identity_1.png)

![miw](images/manual_identity_1_w.png)

![miy](images/manual_identity_1_y.png)

**without non-linearity this model is just another line!** (properties of linear functions)

In the next part, we try to approximate sin(x) using a shallow neural network but this time we update the weights using gradient descent instead of manually changing them.

## Approximating Sine

![sin2pix](images/sin2pix.png)

A model with 25 Neurons:

![loss25](images/loss_function_25_neurons.png)
![prediction 25neurons](images/Prediction_25_neurons.png)

A model with 250 Neurons:

![loss25](images/loss_function_250_neurons.png)
![prediction 25neurons](images/Prediction_250_neurons.png)

Bah Bah!!!!