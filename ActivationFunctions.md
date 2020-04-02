# ImportantConcepts-

## What is the importance of activation functions in DNN?

![Image of Yaktocat](https://pythonmachinelearning.pro/wp-content/uploads/2017/09/Single-Perceptron.png.webp)

As we can clearly see in the above perceptron image, without any activation function the NN output is just the linear weighted sum of inputs, thus it behaves like a linear regression model, which has limited power and does not performs good most of the times hence fails to learn any complex features present in image, text etc.

Activation functions introduces non linearities thus our model is able to learn high dimensional decision boundaries.Hence it all comes down to this, we need to apply a Activation function f(x) so as to make the network more powerfull and add ability to it to learn something complex and complicated form data and represent non-linear complex arbitrary functional mappings between inputs and outputs. Hence using a non linear Activation we are able to generate non-linear mappings from inputs to outputs.

Also another important feature of a Activation function is that it should be differentiable. We need it to be this way so as to perform backpropogation 
