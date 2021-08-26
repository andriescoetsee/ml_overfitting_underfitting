# Overfitting and underfitting in ML context

### Setting the stage

![image](https://user-images.githubusercontent.com/34986276/130934492-afcc2594-481b-4b7c-907d-1743bdbf3ed1.png)


### Accuracy of our estimator - True Risk

Our goal is to learn the best estimate of the true f(x) by using the data we have in hand, the training data. 

We know the training data carries the true signal but is distorted with noise.

The question is then how do we measure the accuracy of our estimator? What is the expected prediction error for our estimator given all possible training sets?

![image](https://user-images.githubusercontent.com/34986276/130936428-393e90ec-0e94-4d6f-b5dd-916d93118d57.png)

**Bias** is the difference between the true f(x) and expected estimation over all possible training sets. In other words Bias describes how much the average estimator fitted over all datasets deviates from the underlying true f(x). 

The goal is to minimize the Bias by detecting the true signal structurally as best we can. For example a linear relationship imposed on an exponential relationship introduces high bias. We need to prevent this high bias by detecting the form of the true signal underneath the noise. 

This is called the structural error (Bias is about form).

**Variance of the estimator** describes how much a single estimator deviates from the expected estimator over all sets. In other words how much our estimator varies per training set. 

The goal is to minimize the Variance of the estimator by resisting the influence of noise. We don't want our estimator to give too much power to noise in the observations. Rather, we want our estimator to resist the pull to deviate from the true signal. 

This is called the estimation error (Variance is about noise eroding form) 

### The goal of supervised learning: reduce Bias and Variance at the same time

The true risk (prediction error) is the sum of the Bias and the Variance seen in the green line below.

In order to minimize the true risk we need to learn the optimal model from the data. 
The optimal model is found as a balancing act between the Bias and the Variance which move in opposite direction as we increase or decrease the model complexity.

![image](https://user-images.githubusercontent.com/34986276/130862105-62afe4c8-d7bc-492a-a34b-6785918cc8bf.png)

Let's look at the impact on the emprical risk (prediction error in our sample data as arppoximation of the true risk) as we varies the complexity of the model.

Say we assume a complex model with many parameters. We can fit a powerful model that reduces Bias because it follows the sample data closely. 
However, this comes at a cost, because we are also picking up noise which increases the error from Variance. 
This leads to **overfitting** which means given another training set the randomness of the noise will result in a very different model.

On the other hand if we assume a simple model to reduce Variance, our power to detect the true signal is diminished. 
We will miss the true signal increasing the error from the Bias.
This leads to **underfitting** making our true risk high because our model form is missing the true form.

### Regularization and Generalization


![Regularisation and Generalization test 2](https://user-images.githubusercontent.com/34986276/130910089-935d0ddf-2ba1-409c-943a-4738e62d5986.png)






