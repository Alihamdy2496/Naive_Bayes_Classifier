
# Naive_Bayes_Classifier

### Naïve bayes classifier is a probabilistic Generative Model that Learns likelihood and prior probabilities then calculate the classes condition probability ​
$$
p(c_1|x) = \frac{p(x|c_1)p(c_1)}{p(x)}
$$
Defining the likelihood of the data as the probability of observing the data under the assumptions:​

1.  Gaussian distribution for class-conditional densities​
    
2.  Shared covariance matrix for all classes (so that the posterior probability would be a linear function of the input data)​
    
3.  Input data points independence (so that the likelihood function would be the product of the joint probabilities of the input data and their given classes)

$$
P(X) = \Pi \pi P(X|C_1) \Pi (1-\pi) P(X|C_2)
$$

$$
P(C_1|X)=\sigma (XW_1+W_0)
$$

$$
W_1 = \frac{1}{2}(\Sigma_1^{-1}\mu_1-\Sigma_2^{-1}\mu_2)
$$

$$
W_0=-\frac{1}{2}\mu_1^T\Sigma_1^{-1}\mu_1+\frac{1}{2}\mu_2^T\Sigma_2^{-1}\mu_2+ \log(\frac{P(C_1)}{P(C_2)}) 
$$
If shared covariance matrix assumption is relaxed, so that the quadratic terms of the input data won't cancel each other according to **pattern recognition book by Christopher bishop** page 199.
$$
P(C_1|X)=\sigma(X^TW_2X+XW_1+W_0)
$$

$$
W_2=\frac{1}{2}(\Sigma_2^{-1}-\Sigma_1^{-1})
$$

$$
W_1=\frac{1}{2}(\Sigma_1^{-1}\mu_1-\Sigma_2^{-1}\mu_2)
$$

$$
W_0=-\frac{1}{2}\mu_1^T\Sigma_1^{-1}\mu_1+\frac{1}{2}\mu_2^T\Sigma_2^{-1}\mu_2+\frac{1}{2}\log(\frac{|\Sigma_2|}{|\Sigma_1|}) + \log(\frac{P(C_1)}{P(C_2)}) 
$$
## the Data

The used data is the [**Credit Card Approvals**](https://www.kaggle.com/datasets/samuelcortinhas/credit-card-approval-clean-data) 
The correlation matrix of the data features shows that there is a high correlation between Married and Bank Customer​

Features, so I discarded the Married -since it has lower correlation with the approval outcome- so that the 3rd ​assumption becomes valid​

![correlation matrix](/files/corr.png)

## The Results

the class conditional probabilities for both classes and the decision boundary for the shared covariance solution

![correlation matrix](/files/res1p1.png)

![correlation matrix](/files/res1p2.png)

the class conditional probabilities for both classes and the decision boundary for the separate covariance solution

![correlation matrix](/files/res2p1.png)

![correlation matrix](/files/res2p2.png)
