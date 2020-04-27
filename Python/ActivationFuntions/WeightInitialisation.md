
# Why not initialize all weights to zero?

Once again I have taken a simple neural network shown below and let’s focus only on pre-activation terms a₁₁ and a₁₂.

![](https://miro.medium.com/max/384/1*3Iic5ob4rLXmZVFMH1KVYQ.png)

We know that pre-activation is equal to the weighted sum of inputs and biases for simplicity ignore bias term in the equation.

![](https://miro.medium.com/max/578/1*W8yVPfqh4pAi1T0aiXpxxw.png)

If we initalise sll the weights to zero, then both activation equations above will become zero. That means all the neurons in the first layer will get the same post activation value irrespective of the non-linear activation function used.

![](https://miro.medium.com/max/329/1*TfxzjZZujjLXkt7j1HIU-A.png)

Because every neuron in the network is giving out same output, they will also have the value of the same gradient flowing back during backpropagation and undergo the exact same parameter updates.

![](https://miro.medium.com/max/784/1*CfkqVvnPUQ1XS6w0wH1c4Q.png)

In other words, the weights started off with the same value, they are going to get the same gradient update and then they remain at the same value even after getting the update using backpropagation. Once you initialize the weights to zero, in all subsequent iterations the weights are going to remain the same (they will move away from zero but they will be equal), this symmetry will never break during the training. Hence weights connected the same neuron should never be initialized to the same value. This kind of phenomenon is known as symmetry breaking problem.

The key takeaways from our discussion on symmetry breaking problem,
* Never initialize all the weights to zero
* Never initialize all the weights to the same value


#### Random Initialization - Large Values :
If the weights are large, the post-activation sum (a₁₁ and a₁₂) could take on a large value especially if there are more input neurons.

![](https://miro.medium.com/max/384/1*3Iic5ob4rLXmZVFMH1KVYQ.png)

If we pass the large aggregation value either to a logistic or tanh activation function, the function would hit saturation. As a result, there will be no updating of weights because values of gradient would be zero (or close to zero) that leads to the vanishing gradient problem.
