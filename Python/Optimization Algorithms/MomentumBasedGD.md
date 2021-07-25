
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

![alt text](https://miro.medium.com/max/762/1*ewQ9mtcJW00Dgp0ZJFNKmg.png)

If we look at the update rule of momentum based gradient descent , we observe that we are making two movements, one in the direction of history another in the direction of current gradient. So whynot just split this into two parts????.... First move in the direction as suggested by history i.e update the weights according to the history and at the new point now calculate the gradient at the temporary point and then move by the amount of temporary gradient. How this helps?. What if with the update provided by history itself i have reached my minima and adding the current gradient might lead to overshooting of the minima by huge amount.Consider this scenario Histpry wants you to move by 3 metres and your current gradient is asking to move by 2 metres .But your destination was 2 metre apart, combining history and current gradient you will overshoot history by 3 metres. So to avoid this move first 3 metres and then calculate the gradient at temporary point and then move in the direcstion of the temporary gradient.  





