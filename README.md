## Motivation
Machine Learning(ML) models can memorize training datasets. So, training ML models over private datasets can violate the privacy of individuals.
For Example, Model Inversion Attacks can extract training data from a ML model.

![My Image](redpic.png)

In model inversion attacks, an adversary attempts to recover the private dataset used to train a ML model.

## What I did in this project?
I developed a differentially private classifier based on logistic regression. The hypothetical training dataset contains two medical features of 100 individuals. And labels classify individuals to high risk and low risk of developing a disease. My goal is to make the logistic regression algorithm, differentially private.

## What is Differential Privacy?
Differential Privacy(DP) is a formal mathematical standard for protecting individuals privacy. DP ensures that the output of a computation will be roughly unchanged whether or not an individual’s data is used, thus limiting an adversary’s ability to infer about individuals’ data points. The main idea for satisfying this condition is to perturb the computation by injecting a calibrated amount of noise to mask the contribution of each individual in the dataset. In the following, I present the
formal definition of DP and a couple of remarks about this notion.

![My Image](dpdef.png)

The aforementioned definition is about the behavior of M and promises that no individual’s data has a large impact on the output. More formally, when an ϵ−differentially private algorithm runs on two neighboring datasets, the resulting distributions over the output space will be very similar,and this similarity is captured by a multiplicative factor e^ϵ. The required noise for satisfying DP is calibrated based on the global sensitivity of the computation. We formalize the mathematical definition of the global sensitivity in the following.

![My Image](dpdef2.png)



















## Non - Private Logistic Regression
The decision boundary of the classifier is sensitive to the individual data points in the training set.

![My Image](adv.png)

## Private Logistic Regression
We apply Gaussian mechanism for privatizing the updating rule of the gradient descent

![My Image](alg.png)

We make every iteration of gradient descent differentially private by adding callibrated Gaussian noise to the gradient computation in each iteration..

## Results

In this section we investigate the intrinsic trade-off between accuracy and privacy in an differentially private logistic regression. Also now we can quantize the level of privacy in our ML model.

We control the level of privacy with parameter epsilon.
