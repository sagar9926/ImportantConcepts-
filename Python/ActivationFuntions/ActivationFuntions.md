# Activation Functions

## Why do we neeed Activation Functions :

If we dont't add Non linearities by using activation functions then our output will be only a linear funtion of input, thus making it impossible to learn complex features.It will only learn lines or planes. Thus Universal approximation theorem will not hold any more in this case.

## Sigmoid :

![Sigmoid](https://miro.medium.com/max/4384/1*6A3A_rt4YmumHusvTvVTxw.png)

![Sigmoid](https://miro.medium.com/max/1298/1*cZXcFBwhVb54D0l1-ZAZ7Q.png)


#### Saturation of Logistic Neuron :

When input is very high f(x) tends to 1, and x is very low f(x) tends to zero thus causing saturation and making the Derivative of logistic neuron zero impacting the gradient flow in back propogation. Thus suffers from ** Vanishing Gradient Issue **

![Saturation Of Sigmoid](https://miro.medium.com/max/794/1*Dtn5ZDBvNTIqB1IhMwqiZA.png)





