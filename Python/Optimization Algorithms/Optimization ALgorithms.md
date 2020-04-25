
## Limitation of Gradient Descent Algorithm :
The initial initialization of weights in Gradient descent algorithm happens randomly. In flat regions of the loss functions the derivative of loss w.r.t weights has very low value , thus the update in weights and biases is very low. Thus to escape from the flat regions will take time for the gradient descent algorithm. While in contrast the derivative of loss w.r.t weights in steep regions is very high thus the update to weights in back propogation is high. thus faster movement.

## Momentum Based Gradient Descent :

Issue with gradient descent was it takes a lot of time to navigate the regions having gentle slope because the gredient in these regions is very small.


### Intuitive solution to above problem :
If I am repeatedly being asked to go in the same direction then I should probably gain some confidence and start taking bigger steps in that direction.

![alt text](https://miro.medium.com/max/1220/1*IiHWuBju-ukNCTKSeU9VUA.png)

V_t is History. Update = V_t

![alt text](https://miro.medium.com/max/1816/1*ZDBsBanwX5jSFse4m2fxMQ.png)


At every time step we are moving in the direction of the current gradient and also in the direction of the history. Every time we give lesser and lesser importance to the gradients belonging to farther time steps because we are taking Exponentially decaying average.
Even in regions having gentle slopes, Momentum based Gradient descent is able to take large steps because of the momentum carries it along.

### Disadvantage of Momentum based GD:
1. Some time it is possible we might overshoot our goal because of the momentum it carries along due to accumulated history thus taking large steps confidently.

Thus momentum based gradient descent oscillates in and out of minima valley , taking U turns after over shooting the minima. But despite these U-turns Momentum based gradient descent converges faster than vanila gradient descent

## Nesterov Accelerated Gradient Descent :

![alt text](https://hackernoon.com/photos/rCP6qw3H5dT85YxJBzbH5ckZfjO2-eu3t3314c)







