# Activation Functions

## Why do we neeed Activation Functions :

If we dont't add Non linearities by using activation functions then our output will be only a linear funtion of input, thus making it impossible to learn complex features.It will only learn lines or planes. Thus Universal approximation theorem will not hold any more in this case.

## Sigmoid : 

It is not Zero-centred function.(Zero centred means output sometimes positive and sometimes negetive)

![Sigmoid](https://miro.medium.com/max/4384/1*6A3A_rt4YmumHusvTvVTxw.png)

![Sigmoid](https://miro.medium.com/max/1298/1*cZXcFBwhVb54D0l1-ZAZ7Q.png)


#### Saturation of Logistic Neuron :

When input is very high f(x) tends to 1, and x is very low f(x) tends to zero thus causing saturation and making the Derivative of logistic neuron zero impacting the gradient flow in back propogation. Thus suffers from **Vanishing Gradient Issue**

![Saturation Of Sigmoid](https://miro.medium.com/max/794/1*Dtn5ZDBvNTIqB1IhMwqiZA.png)


#### Logistic Function is non zero centred :
The logistic function is not zero-centered what I mean by that is, that the value of logistic function always lies between 0 and 1. So the average cannot be 0, it will always be a value above zero. The zero centered function would be a function where its output some times would be greater than 0 and less than 0.

![Non Zero Centred](https://miro.medium.com/max/1072/1*RvoLOQn5H4hx2wjFABHb5w.png)

Now to apply the gradient descent rule and the update the parameters of the neuron present in the second last layer, we need to compute the gradient for ‘dw₁’ and ‘dw₂’ with respect to the loss function. Assuming that you know the chain rule

![aa](https://miro.medium.com/max/606/1*rajvDNJUPUmfo5-Y-lSJKw.png)

The terms in red are common for both the weights and the chain rule changes for blue terms. The value of a₃ is given by,

![xx](https://miro.medium.com/max/674/1*5WEk83XkrHFuFQyKeRyLjA.png)

By Substituting the ‘a₃’ in the above chain rule, we would get the following equation.

![xxx](https://miro.medium.com/max/626/1*oTx4cQ_DofTy9rp-n3sV0Q.png)

Remember that h₂₁ and h₂₂ are outputs from the logistic function so both of them would always be positive. Suppose the red quantity in the above figure is negative then the both these gradients would be negative similarly if the red quantity is positive then both these gradients would be positive. **Essentially, either all the gradients connected the same neuron in a layer are positive or all the gradients in a layer are negative**.

![](https://miro.medium.com/max/1228/1*lmow9ZxJL5Jyfwy84SN_nw.png)

This restricts the possible update directions i.e… gradients can move only in the first quadrant and the third quadrant. What this means is that because the algorithm is not allowed to take certain movements or directions. As a result, it would take a lot of time to converge.

#### Logistic function is computationally expensive as it requires to calculate exp(x)


## TanH :

![](https://miro.medium.com/max/1134/1*1FuDQCq9EPlPDMId4nmbNw.png)

* TanH ranges from -1 to 1
* Again When TanH saturates the derivatives will be Zero
* It is computationally expensive as it requires to calculate exp(x)

![](https://miro.medium.com/max/1218/1*__Skz8FEhSxJcgWN57PZsw.png)

Thus we can comment that TanH also suffers from **Vanishing Gradient** But the advantage of using TanH above logistic neuron is that it is **Zero Centred** thus It won't restrict the gradient movement in certain direction.


## Relu — Rectified Linear Unit: 

![](https://miro.medium.com/max/990/1*a-6BNtyuM2NNzKmcovUTdw.png)











References :
https://medium.com/datadriveninvestor/deep-learning-best-practices-activation-functions-weight-initialization-methods-part-1-c235ff976ed


