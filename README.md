# Overfitting and underfitting in ML context

## Error decomposition and bias-variance trade-off

![image](https://user-images.githubusercontent.com/34986276/130860468-e55bffeb-ba79-4fa5-bb10-ce6c4c7ccbb2.png)

### Goal

Our Goal is to learn the relationship between random variables X and Y where the ground truth is y = f(x). 

Furthermore, our observed data is not 100% accurate. It includes all kinds of noise and uncertainty. 

Moreover, f(x) is unknown, so we approximate it by mininmize the empirical risk on the training set that will produce f hat.

Take note that a different training set produces a different estimator.

### What is our expected prediction error (true risk) for our estimator given all possible traning sets?

**Bias** is the difference between the true f(x) and expected estimation over all possible training sets. In other words Bias describes how much the average estimator fitted over all datasets deviates from the underlying true f(x). 

This is called the structural error. 

**Variance of the estimator** describes how much a single estimator deviates from the expected estimator over all sets.

This is called the estimation error.

### The goal of supervised learning: reduce Bias and Variance at the same time

![image](https://user-images.githubusercontent.com/34986276/130862105-62afe4c8-d7bc-492a-a34b-6785918cc8bf.png)

![image](https://user-images.githubusercontent.com/34986276/130863725-7fc89058-6ca3-4e12-acb5-51b76220ea9d.png)





