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

The goal to reduce the Bias and Variance at the same time is not possible because of noise in the training data. 

Let's look at the graph below: the true risk (prediction error) is the sum of the Bias and the Variance seen in the green line below.

In order to minimize the true risk we need to learn the optimal model from the data. 
The optimal model is found as a balancing act between the Bias and the Variance which move in opposite directions as we increase or decrease the model complexity.
This is also called the Bias-Variance tradeoff. 

![image](https://user-images.githubusercontent.com/34986276/130862105-62afe4c8-d7bc-492a-a34b-6785918cc8bf.png)
```
Graph from edx MITx 6.86x Machine Learning with Python-From Linear Models to Deep Learning
```
Let's look at the impact on the emprical risk (prediction error in our sample data as appoximation of the true risk) as we varies the complexity of the model.

Say we assume a complex model with many parameters. We can fit a powerful model that reduces Bias because it follows the sample data closely. 
However, this comes at a cost, because we are also picking up noise which increases the error from Variance. 
This leads to **overfitting** which means given another training set the randomness of the noise will result in a very different model.

On the other hand if we assume a simple model to reduce Variance, our power to detect the true signal is diminished. 
We will miss the true signal, increasing the error from the Bias.
This leads to **underfitting** making our true risk high because our model form is missing the true form.

### Regularization and Generalization

In Machine Learning the optimal model is learnt by minimizing the true risk. 
However, because we don't know the ground truth y=f(x) we need to make use of the empirical risk based on the sample data as an approximation of the true risk. 
Then the machine learning objective is to minimize the emprical risk which is defined as a Loss function that needs to be minimized. 
The Loss function comes in many shapes and forms for example Mean Squared Error, Mean Absolute Error, Hinge Loss etc. 

Furthermore, in Machine Learning the Loss function includes a regularization parameter which is a penalty term that increases the empirical risk. 
This forces the model to learn harder (making more effort to detect the true signal behind the noise) by controling the model complexity. 
This helps in the model fiting process to avoid the power of noise pulling our estimator towards overfitting (high Variance, high true risk/prediction error)

In short regularisation helps solving overfitting, making our model generalize well when seeing new data, which is what we want!

The way this is done is by using a training dataset and a validation dataset to find the optimal hyperparameters (regularization parameters).
See graph below for how this works in a Tree Regression example.

![Regularisation and Generalization test 2](https://user-images.githubusercontent.com/34986276/130910089-935d0ddf-2ba1-409c-943a-4738e62d5986.png)
```
Graph from https://www.kaggle.com/dansbecker/underfitting-and-overfitting
```
The graph shows that the training error continues dropping as the model complexity increases, depth of the tree. 
However, there is a point of overfitting that shows in the validation error increasing. 
The sweet spot is that regularization parameter value that prevents both overfitting and underfitting. 
That sweet spot is at that point where the model starts learning noise causing the validation error to increase.
When our validation error increase it means our model will no longer generalize well when seeing new data causing high prediction error or low accuracy. 

The same principle can be applied to KNN algorithm where the complexity of the model increases as K decreases (relying increasingly on closer neighbours to make predictions). 

<img width="576" alt="KNN" src="https://user-images.githubusercontent.com/34986276/130950118-4205412b-8d8a-4354-bb96-8377f47dacf9.png">

```
Graph from: An Introduction to Statistical Learning by Gareth James, Daniela Witten, Trevor Hastie, Robert Tibshirani
```


