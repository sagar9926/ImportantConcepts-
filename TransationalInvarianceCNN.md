## How are convolutional networks Transational invariant?

What is transational invariance in Neural network?
Ans : Transational invariance simply means that if we translate/shift the object in the input image slightly, CNN will still be able to detect the class of the object to which the input belongs. The standard neural networks don't have these transational invariance property,and thus performs very badly on shifted images.

Translational Invariance is a result of the pooling operation. In a traditional CNN architecture, there are three stages. In the first stage, the layer performs convolution operation on the input to give linear activations. In the second stage, the resultant activations are passed through a non-linear activation function such as sigmoid, tanh or relu. In the third stage, we perform the pooling operation to modify the output further. 
In pooling operation, we replace the output of the convnet at a certain location with a summary statistic of the nearby outputs such a maximum in case of Max Pooling. As we replace the output with the max in case of max-pooling, hence even if we change the input slightly, it won’t affect the values of most of the pooled outputs. Translational Invariance is a useful property where the exact location of the object is not required. For e.g if you are building a model to detect faces all you need to detect is whether eyes are present or not, it’s exact position is not necessary. While in segmentation tasks, the exact position is required. 

![alt text](https://miro.medium.com/max/1400/1*l8JQ2UcWGgTUCAkbHwSCNA.png)

![alt text](https://miro.medium.com/max/1400/1*34AIhDbzddRfrfhFpqRwCQ.png)


## Reference :
https://medium.com/@divsoni2012/translation-invariance-in-convolutional-neural-networks-61d9b6fa03df

https://towardsdatascience.com/translational-invariance-vs-translational-equivariance-f9fbc8fca63a
