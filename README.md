# :herb: 1 Generalised Linear Models (GLMs) and Gradient Boosted Machines (GBMs)

## :apple: 1.1 Generalised Linear Models (GLMs)

Generalised Linear Models (GLMs) are an extension of the traditional linear regression model, allowing for non-normal distribution of the response variable and a non-linear relationship between the predictors and the response variable. GLMs are composed of three components:

1. **Random Component**: Assumes the response variable follows a distribution from the exponential family (e.g., Gaussian, Poisson, Binomial, etc.).
2. **Systematic Component**: Represents a linear combination of the predictors ($X\beta$), where $X$ is the matrix of predictors and $\beta$ are the coefficients.
3. **Link Function**: Connects the random and systematic components by describing the relationship between the expected value of the response variable and the predictors.

The general form of a GLM can be expressed as:

$$g(E(Y)) = X\beta$$

Where $g$ is the link function and $E(Y)$ is the expected value of the response variable.

### :bread: 1.1.1 Advantages of GLMs

- Flexibility to handle non-normal response variables and non-linear relationships.
- Interpretability of model coefficients.
- Widely used in various fields, e.g., medicine, social sciences, and ecology.

## :apple: 1.2 Gradient Boosted Machines (GBMs)

Gradient Boosted Machines (GBMs) are an ensemble learning method that combines the predictions of multiple weak learners (typically decision trees) to improve predictive accuracy. GBMs iteratively build decision trees to minimize a given loss function using the gradient descent algorithm. The key idea is to add a new tree at each iteration to correct the residual errors of the previous tree.

The output of a GBM can be expressed as:

$$f(x) = \sum_{i=1}^{M} \gamma_m h_m(x)$$

Where $M$ is the number of trees, $\gamma_m$ are the learning rates, and $h_m(x)$ are the base learners (decision trees).

### :bread: 1.2.1 Advantages of GBMs

- Can handle a wide range of data types, including continuous, categorical, and ordinal variables.
- Great predictive accuracy and robustness to outliers.
- Can model complex interactions between variables and capture non-linear relationships.

However, GBMs can be prone to overfitting, especially when the number of trees is large or the trees are too deep. Regularization techniques such as shrinkage, subsampling, and early stopping can help mitigate overfitting.

### :bread: 1.2.2 Differences between GLMs and GBMs

1. **Model Complexity**: GLMs are simpler and more interpretable, while GBMs can model complex relationships and interactions.
2. **Distribution Assumption**: GLMs assume the response variable follows a distribution from the exponential family, while GBMs make no such assumption.
3. **Non-linearities**: GLMs handle non-linear relationships through the link function, while GBMs can capture non-linear relationships by combining weak learners.
4. **Predictive Accuracy**: GBMs often have better predictive accuracy than GLMs, but can be prone to overfitting.
