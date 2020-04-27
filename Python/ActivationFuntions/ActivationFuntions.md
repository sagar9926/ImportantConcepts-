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

* Doesnot saturate in positive region
* Computationaly inexpensive
* It is not Zero centred, Easy to compute
* Used in CNNs


![](https://miro.medium.com/max/990/1*a-6BNtyuM2NNzKmcovUTdw.png)

#### Problem with Relu : Dead Neurons

![](https://miro.medium.com/max/413/1*76BCwFsm_yCitxTQ4nwyVA.png)

The value of h1 is given by :

![](https://miro.medium.com/max/1018/1*n-nLFA-oMQPYUnVcAWRXZw.png)

Lets assume that the value of parameter b is large negative ,due to a large negative update at some point while training, then the value of a₁ changes to,

![](https://miro.medium.com/max/1182/1*HR1FmHL1H6vMagsbTTBQCQ.png)

On applying Relu on a1 , the value of h1 will become zero.

![](https://miro.medium.com/max/914/1*wLUEnTGILJikhM4-4pRb9g.png)

Not only the h1 will become zero but also the derivative oh h1 w.r.t weight , let say w1, will become zero.The weights w₁, w₂, and bias b₁ will not get updated because there will be a zero term in the chain rule and the neuron will stay dead forever. This problem is known as the **Dying ReLU**.

![](https://miro.medium.com/max/958/1*kilDNZNFc9x4Y1JTEqPgcA.png)

That means no gradients will flow back and all the weights connected to that neuron will not get updated. In practice when you train a network with ReLU, you will observe that a large fraction of neurons would die. To avoid this problem we can use other variants of ReLU like Leaky ReLU or we can initialize the weights and bias to a large positive value. By initializing the weights to a large positive value even if this large negative gradient flows through the network there is still a chance that it will not become a large negative value and hence it will not mess up the network.


## Leaky ReLU

![](https://miro.medium.com/max/1084/1*uTnswLrP0HDPKvfSl_mDhA.png)

![](https://miro.medium.com/max/1000/1*VsEnYitSk5R7W12K5zP3cw.png)

Because of the small value (0.01) proportional to the input for the negative values, the gradient would not saturate. If the input is negative gradient would be 0.01, this ensures neurons doesn’t die.

#### Advantages :

* Doesn’t saturate in the positive or negative region
* Neurons will not die (0.01x ensures that at least small gradient will flow through)
* Easy to compute
* Close to zero-centered outputs



## Summary :

![](https://i.stack.imgur.com/cQTjk.png)


References :
https://medium.com/datadriveninvestor/deep-learning-best-practices-activation-functions-weight-initialization-methods-part-1-c235ff976ed


