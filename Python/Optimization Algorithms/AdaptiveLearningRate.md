## Intuition :

To decay the learning rate in proportion to the update history of parameters.Lets say if we have a parameter that is dense i.e lesser zeroes and is updating very frequently, since the input is on most of the times hence the derivative is non zero most of the times thus weight is getting updated most of the times (as gradient flow depends on input). For such parameters we want to have small learning rate.

And in contrast we have a parameters whichis off most of the times , then the derivative is going to be zero most of the times, for such features we want higher learning rate because in these we are going to get a chance to learn from few inputs, thus whenever you get a chance to learn learn fast.

!(https://miro.medium.com/max/1784/1*8a-kA2QHel7VbeuVIrwwUg.png)
