## Intuition :

To decay the learning rate in proportion to the update history of parameters.

Lets say if we have a parameter that is dense i.e lesser zeroes and is updating very frequently, since the input is ON most of the times hence the derivative is non zero most of the times thus weight is getting updated most of the times (as gradient flow depends on input). For such parameters we want to have small learning rate.

And in contrast we have a parameters whichis OFF most of the times , then the derivative is going to be zero most of the times, for such features we want higher learning rate because in these we are going to get a chance to learn from few inputs, thus whenever you get a chance to learn learn fast.


### AdaGrad :

![AdaGrad](https://miro.medium.com/max/1784/1*8a-kA2QHel7VbeuVIrwwUg.png)

In the second equation we can clearly see that we are dividing the learning rate by a quantity (sqrt(v_t) + e) . Lets call this quantity as 
Denominator D.

##### For Dense Features (Lesser number of Zeroes) : D sould be high, thus Reducing the learning

In equation we see thet V_t is dependent upon the derivative of loss function w.r.t weights. Thus derivetives taken at different time steps are all going to be non zero . Thus Vt will be high, making effective learning rate will be high.

##### For Sparse Features (more number of Zeroes) : D sould be low, thus increasing the learning
Similarly V_t will be low in this case because derivatives taken at different time steps are all going to be sparse. making effective learning rate high

###### Advantages Adagrad : 
Paremeters corresponding to sparse features gets better updates

######  Disadvantage Adagrad :
The disadvantage of AdaGrad is that the learning rate decays very aggressively as the denominator grows which is not good for parameters corresponding to dense features. As b gets updated, again and again, denominator D increases a lot and the effective learning rate becomes close to zero, as a result, AdaGrad is no longer able to move in the direction of b and gets stuck close to the convergence.


### RMSProp — Root Mean Square Propagation:

![RMSProp](https://miro.medium.com/max/1000/1*634Q7KTgRx4GLGypTz83Dg.png)

#### Intuition : Why not Decay the denominator and prevent its Rapid growth ?
RMSProp helps to achieve this by introducing another hyperparameter. RMSProp uses this intuition to prevent the rapid growth of the denominator for dense variables so the effective learning rate doesn’t become close to zero.

#### RMSProp Equation
In RMSProp history of gradients is calculated using an expoential decaying average unlike the sum of gradients in AdaGrad, which helps to prevent the rapid growth of the denominator for dense features.

### Adam :

![ADAM](https://miro.medium.com/max/1000/1*634Q7KTgRx4GLGypTz83Dg.png)

In Momentum based gradient descent we are using the cumulative history of gradients to move faster in the gentle surfaces and we have seen RMSProp which is also using history to decay the denominator and prevent its rapid growth. The way these algorithms uses the history is different, In Momentum GD, we use history to compute the current update whereas in case of RMSProp history was used to adjust the learning rate (shrink or boost).
Adam combines these two separate histories into one algorithm.

Adam maintains two histories, ‘mₜ’ similar to the history used in Momentum GD and ‘vₜ’ similar to the history used in RMSProp. In practice, Adam does something known as bias correction. It uses the following equations for ‘mₜ’ and ‘vₜ’,





Resources :
https://medium.com/datadriveninvestor/more-on-gradient-descent-algorithm-and-other-effective-learning-algorithms-a1222a8d6c33

https://hackernoon.com/demystifying-different-variants-of-gradient-descent-optimization-algorithm-19ae9ba2e9bc

