# Overfitting and underfitting in ML context

## Setting the stage

![image](https://user-images.githubusercontent.com/34986276/130934492-afcc2594-481b-4b7c-907d-1743bdbf3ed1.png)


### Accuracy of our estimator - True Risk

Our goal is to learn the best estimate of the true f(x) by using the data we have in hand, the training data. 

We know the training data carries the true signal but distorted with noise.

The question is then how do we measure the accuracy of our estimator? What is the expected prediction error for our estimator given all possible training sets?

![image](https://user-images.githubusercontent.com/34986276/130936428-393e90ec-0e94-4d6f-b5dd-916d93118d57.png)

**Bias** is the difference between the true f(x) and expected estimation over all possible training sets. In other words Bias describes how much the average estimator fitted over all datasets deviates from the underlying true f(x). 

The goal is to minimize the Bias by detecting the true signal structurally as best we can. And in that way we try to get to the true f(x) as close as possible. For example a linear relationship imposed on an exponential relationship introduces high bias. We need to prevent this high bias by detecting the form of the true signal underneath the noise. 

This is called the structural error (Bias is about form).

**Variance of the estimator** describes how much a single estimator deviates from the expected estimator over all sets. In other words how much our estimator varies per training set. 

The goal is to minimize the Variance of the estimator by resisting the influence of noise. We don't want our estimator to give too much power to noise in the observations. Rather, we want our estimator to resist the pull to deviate from the true signal. 

This is called the estimation error (Variance is about noise eroding form) 

### The goal of supervised learning: reduce Bias and Variance at the same time

We reduce Bias by structurally staying as close as possible to the form of the true signal. And we reduce Variance by not getting distracted by noise. 

![image](https://user-images.githubusercontent.com/34986276/130862105-62afe4c8-d7bc-492a-a34b-6785918cc8bf.png)

### Regularization and Generalization


![Regularisation and Generalization test 2](https://user-images.githubusercontent.com/34986276/130910089-935d0ddf-2ba1-409c-943a-4738e62d5986.png)






