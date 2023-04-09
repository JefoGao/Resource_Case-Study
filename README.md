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

# :herb: 2 Application of Generalised Linear Models (GLMs) and Gradient Boosted Machines (GBMs)

GLMs and GBMs have various real-world applications in different industries, such as finance, insurance, marketing, and healthcare.

## :apple: 2.1 Applications of Generalised Linear Models (GLMs)

1. **Logistic Regression**: A type of GLM used for binary classification problems, where the response variable follows a binomial distribution, and the link function is the logit function.

   - Examples: Predicting customer churn, fraud detection, and medical diagnosis.

2. **Poisson Regression**: A type of GLM used for count data, where the response variable follows a Poisson distribution, and the link function is the log function.

   - Examples: Predicting the number of insurance claims, forecasting the number of support tickets, and modeling the number of product defects.

3. **Ordinal Regression**: A type of GLM used for ordinal response variables, where the link function is the cumulative logit, probit, or complementary log-log function.

   - Examples: Predicting customer satisfaction levels, credit rating, and survey responses.

## :apple: 2.2 Applications of Gradient Boosted Machines (GBMs)

1. **Anomaly Detection**: GBMs can be used to identify unusual patterns or outliers in data, as they can model complex interactions and capture non-linear relationships.

   - Examples: Detecting credit card fraud, network intrusion, and manufacturing defects.

2. **Predictive Modeling**: GBMs are useful for various prediction tasks, including regression, classification, and ranking problems.

   - Examples: Predicting customer lifetime value, click-through rates, and movie recommendations.

3. **Feature Selection**: GBMs can identify important features for prediction by calculating feature importances, which can help in dimensionality reduction and model interpretation.

   - Examples: Identifying key drivers of customer churn, sales, and disease risk factors.

4. **Natural Language Processing**: GBMs can be used for various NLP tasks, such as text classification, sentiment analysis, and topic modeling.

   - Examples: Classifying news articles, analyzing product reviews, and identifying trending topics on social media.

Both GLMs and GBMs are powerful and flexible tools that can be applied to a wide range of problems. However, it's essential to understand their assumptions, strengths, and limitations to select the appropriate algorithm for a specific task.
