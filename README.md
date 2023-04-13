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
1. An optimized loss function: has to be differentiable; Regression: squared error; Classification: logarithmic loss.
3. A weak learner: decision trees; trees are designed greedily, selecting the best split points based on purity scores like Gini
4. An additive model that reduces failure cases. Update the value by adding a new tree to reduce the residual loss.

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

# :herb: 3 Python and R: Experience and Comfort Level

Python and R are popular programming languages for data analysis and machine learning. Both languages have extensive libraries and tools to support various data analysis tasks.

## :apple: 3.1 Python

### :bread: 3.1.1 Core Libraries

1. **NumPy**: Provides support for numerical operations and working with arrays.
2. **Pandas**: Offers data manipulation and analysis tools, such as DataFrame and Series.
3. **Matplotlib**: A plotting library for creating static, animated, and interactive visualizations.
4. **Seaborn**: A statistical data visualization library based on Matplotlib.

### :bread: 3.1.2 Machine Learning Libraries

1. **Scikit-learn**: A library for machine learning, featuring various algorithms, preprocessing tools, and model evaluation techniques.
2. **TensorFlow**: An open-source library for machine learning and deep learning, developed by Google.
3. **Keras**: A high-level neural networks API, running on top of TensorFlow or other deep learning frameworks.
4. **PyTorch**: A deep learning framework developed by Facebook, offering tensor computations and deep neural networks.

## :apple: 3.2 R

### :bread: 3.2.1 Core Packages

1. **dplyr**: Provides tools for data manipulation, such as filtering, sorting, and aggregating.
2. **ggplot2**: A popular visualization package based on the Grammar of Graphics.
3. **tidyr**: Offers tools for cleaning and reshaping data.
4. **readr**: Facilitates reading and writing data from various file formats.

### :bread: 3.2.2 Machine Learning Packages

1. **caret**: A package for classification and regression training, streamlining the model training process.
2. **randomForest**: Implements the random forest algorithm for classification and regression tasks.
3. **xgboost**: An optimized and scalable implementation of gradient boosting, designed for speed and performance.
4. **glmnet**: Offers tools for fitting generalized linear models via penalized maximum likelihood.

When discussing your experience and comfort level with Python and R, be prepared to mention specific libraries and tools you've used, as well as any projects or applications you've developed. Also, be ready to compare and contrast the two languages, discussing their strengths, weaknesses, and use cases.

# :herb: 4 Tabular Data Structures

Tabular data structures are row-column representations of data where each row represents an observation or record, and each column represents a variable or attribute. Understanding tabular data structures is crucial for efficient data manipulation and analysis.

## :apple: 4.1 Key Concepts

1. **Rows**: Each row in a tabular data structure represents a single observation or record.
2. **Columns**: Each column in a tabular data structure represents a specific attribute or variable associated with the observations.
3. **Indices**: Rows and columns can be indexed to facilitate efficient data manipulation and retrieval.

## :apple: 4.2 Data Manipulation Operations

1. **Selection**: Extracting specific rows, columns, or cells from a dataset.
2. **Filtering**: Selecting rows based on specific conditions or criteria.
3. **Sorting**: Rearranging rows in a dataset based on the values of one or more columns.
4. **Aggregation**: Summarizing data by grouping it based on one or more categorical columns and applying an aggregation function (e.g., sum, mean, count) to the remaining columns.
5. **Joining**: Combining two or more datasets based on shared key columns.
6. **Reshaping**: Changing the structure of a dataset by pivoting, melting, or stacking.

## :apple: 4.3 Popular Libraries for Tabular Data Manipulation

### :bread: 4.3.1 Python

1. **Pandas**: A powerful library for data manipulation and analysis, providing DataFrame and Series data structures for handling tabular data.

   - Selection: `df['column_name']`, `df.loc[]`, `df.iloc[]`
   - Filtering: `df[df['column_name'] > value]`
   - Sorting: `df.sort_values(by='column_name')`
   - Aggregation: `df.groupby('column_name').agg({'other_column': 'sum'})`
   - Joining: `pd.merge(df1, df2, on='key_column')`
   - Reshaping: `df.pivot()`, `df.melt()`

### :bread: 4.3.2 R

1. **dplyr**: A library for data manipulation, providing tools for working with tabular data.

   - Selection: `select(df, column_name)`
   - Filtering: `filter(df, column_name > value)`
   - Sorting: `arrange(df, column_name)`
   - Aggregation: `summarise(group_by(df, column_name), sum(other_column))`
   - Joining: `inner_join(df1, df2, by = 'key_column')`
   - Reshaping: `spread()`, `gather()`

When discussing your understanding of tabular data structures, be prepared to explain key concepts, data manipulation operations, and any experience you have using relevant libraries, such as pandas in Python or dplyr in R.

# :herb: 5 Industry-specific Applications

Data analysis techniques can be applied to various industries to address specific challenges, such as driving customer retention, analyzing trends, or identifying factors contributing to observed behaviors.

## :apple: 5.1 Key Considerations

1. **Understanding the Industry**: Familiarize yourself with industry-specific terms, concepts, and business processes.
2. **Identifying Challenges**: Recognize the unique challenges and problems faced by companies within the industry.
3. **Selecting Data Analysis Techniques**: Choose appropriate data analysis techniques to address industry-specific challenges.
4. **Interpreting Results**: Interpret the results of your analysis and communicate insights that are relevant to the industry.

## :apple: 5.2 Industry Examples

### :bread: 5.2.1 Banking

- Challenge: Predicting customer churn to improve retention rates.
- Approach: Use machine learning techniques, such as logistic regression or random forests, to identify factors that contribute to customer churn.

### :bread: 5.2.2 Retail

- Challenge: Analyzing sales trends to optimize inventory management.
- Approach: Apply time series analysis methods, such as ARIMA or seasonal decomposition, to forecast sales and inform inventory decisions.

### :bread: 5.2.3 Insurance

- Challenge: Identifying factors that contribute to insurance claims.
- Approach: Employ Generalized Linear Models (GLMs) or Gradient Boosted Machines (GBMs) to analyze the relationship between policyholder characteristics and claim frequency or severity.

When discussing industry-specific applications, be prepared to explain how you would approach a problem or question related to a specific industry, such as banking, retail, or insurance. This could involve explaining how you would use data analysis techniques to address a particular challenge and interpreting the results in the context of the industry.
