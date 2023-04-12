# 1 Understand the Data

One of the first steps in data analysis is to understand the distribution of variables in the dataset. This involves identifying the data types of the variables, as well as the shape, spread, and central tendency of their distributions. By doing so, we can gain insights into the underlying patterns and relationships in the data, and make informed decisions about how to preprocess, transform, or model the data.

## 1.1 Data Types

The data types encountered in a dataset can include:

- **Categorical**: These are variables that represent discrete categories or labels, such as gender, color, or country. They can be represented using nominal or ordinal scales.
- **Numerical**: These are variables that represent continuous or discrete numeric values, such as age, income, or temperature. They can be represented using interval or ratio scales.
- **Textual**: These are variables that represent unstructured or free-form text, such as reviews, comments, or tweets. They may require natural language processing (NLP) techniques to analyze.
- **Temporal**: These are variables that represent dates, times, or durations, such as timestamps, event dates, or time-to-failure. They may require time series analysis techniques to analyze.

### ***:bulb: notes***
- *Nominal scale: A variable measured on a nominal scale is one where each observation is assigned a label, such as a name, category, or group. There is no inherent order or ranking to these labels.*
- *Ordinal scale: A variable measured on an ordinal scale is one where each observation is assigned a label that has a natural order or ranking. However, the differences between the categories are not equal.*
- *Interval scale: A variable measured on an interval scale has equal intervals between adjacent values, but there is no true zero point.*
- *Ratio scale: A variable measured on a ratio scale has equal intervals between adjacent values, and there is a true zero point, meaning that a value of zero represents the complete absence of the variable being measured.*

|![image](https://user-images.githubusercontent.com/19381768/231322355-313586f0-4233-48e9-a051-ce1b6742c204.png)|
|:--:|
|Different types of scales|


## 1.2 Distribution Shapes

The shape of a distribution refers to the pattern or form that the data takes when plotted as a histogram or density plot. Common distribution shapes include:

- **Normal**: This is a bell-shaped distribution that is symmetric around the mean. It is characterized by its mean and standard deviation, and often arises in nature and random processes.
- **Skewed**: This is a distribution that is not symmetric, but rather skewed to the left or right. It is characterized by its median and skewness, and can indicate the presence of outliers or a non-normal underlying process.
- **Bimodal**: This is a distribution that has two distinct peaks or modes. It can indicate the presence of two underlying processes or populations.
- **Uniform**: This is a distribution that is flat or rectangular, with equal probability across the range of values. It is characterized by its minimum and maximum values, and can indicate a lack of structure or randomness in the data.

### ***:bulb: notes***
- *A distribution is bimodal if it has two peaks or modes, meaning that there are two values that occur with the highest frequency in the dataset.*

## 1.3 Measures of Central Tendency and Spread

The central tendency and spread of a distribution are important descriptive statistics that summarize the location and variability of the data. Common measures include:

- **Mean**: This is the arithmetic average of the data values. It is sensitive to outliers and can be biased by non-normal distributions.
- **Median**: This is the middle value of the data when sorted in ascending order. It is more robust to outliers and non-normal distributions than the mean. (*Too many 0s will affact median, remember to remove*)
- **Mode**: This is the most common value or values in the data. It can be useful for categorical or discrete variables.
- **Standard deviation**: This is a measure of the spread or variability of the data around the mean. It is sensitive to outliers and can be biased by non-normal distributions.
- **Range**: This is the difference between the maximum and minimum values in the data. It can be useful for detecting outliers or unusual data points.

# 2 Data Cleaning

## 2.1 Missing Data
- Missing data refers to observations or values that are not present in the dataset.
- Missing data can occur for various reasons such as non-response, data entry errors, or faulty measurements.

### 2.1.1 Detection of Missing Data
- Visual inspection of the dataset to identify missing data through heatmaps, bar plots, or line graphs.
- Using built-in functions in python libraries like pandas.isnull() or numpy.isnan().

### 2.1.2 Handling Missing Data
- Removal of missing data:
    - Listwise deletion (removing entire rows with missing values).
    - Pairwise deletion (removing specific column/variable if any missing values exist).
- Imputation of missing data:
    - Mean imputation (replacing missing values with the mean of the available data).
    - Mode imputation (replacing missing values with the mode of the available data).
    - Median imputation (replacing missing values with the median of the available data).
    - Regression imputation (replacing missing values with predicted values using regression models).
    - KNN imputation (replacing missing values with predicted values using KNN algorithm).

## 2.2 Imputation of Missing Data

Imputation of missing data involves filling in the missing values using a method that takes into account the remaining data in the dataset.

|Advantages|Disadvantages|
|--|--|
|<ul><li>Utilizes all the available data.</li><li>Preserves the variability of the data.</li><li>Enables the use of more advanced statistical methods.</li></ul>|<ul><li>May introduce bias if the method used is not appropriate for the dataset.</li><li>Can affect the distribution of the data.</li><li>Can inflate standard errors or confidence intervals.</li></ul>|

### 2.2.1 Imputation Methods Use Case

|Method|Use Case|
|--|--|
|Mean Imputation|<ul><li>Replacing missing values with the mean of the available data.</li><li>Works well when the data is normally distributed or symmetric.</li></ul>|
|Mode Imputation|<ul><li>Replacing missing values with the mode (most common value) of the available data.</li><li>Works well for nominal or ordinal data.</li></ul>|
|Median Imputation|<ul><li>Replacing missing values with the median of the available data.</li><li>Works well for data with a skewed distribution or outliers.</li></ul>
|Regression Imputation|<ul><li>Replacing missing values with predicted values using regression models.</li><li>Works well when there is a linear relationship between the missing variable and other variables in the dataset.</li><li>However, regression imputation assumes a linear relationship between the variables and may not work well for non-linear relationships or interactions between variables.</li></ul>|

### 2.2.2 Regression Models
#### :one: Choose a Model
- Simple Linear Regression: suitable for one missing variable and one or more predictor variables.
- Multiple Linear Regression: suitable for more than one missing variable and one or more predictor variables.
- Logistic Regression: suitable for binary or categorical missing variables.

#### :two: How to Use Regression Imputation
- Divide the dataset into two parts: one with complete data and another with missing data.
- Use the complete data to build the regression model and predict the missing values.
- Check the quality of the imputed values using diagnostic plots or goodness-of-fit tests.

#### :three: When Not to Use Regression Imputation
- When there is no linear relationship between the missing variable and other variables in the dataset.
- When there are too many missing values or missing values are clustered in a particular subset of the dataset.
- When the imputation introduces a significant amount of bias or affects the distribution of the data.

#### ***:bulb: solution***
*Generalized Linear Models (GLM) can be used for regression imputation. GLM is an extension of linear regression that can handle non-normal error distributions and non-linear relationships between variables. It allows the use of different types of response variables, such as binary, count, or continuous variables, and can be used for both simple and multiple regression imputation. However, GLM requires careful selection of appropriate link functions and distributions to model the relationship between the missing variable and the predictor variables.*

### 2.2.3 Handling Missing Data based on Data Type and Distribution
- For nominal or ordinal data with low missing data percentage, removal or mode imputation can be used.
- For interval or ratio data with low missing data percentage, mean, median or regression imputation can be used.
- For bimodal or skewed data, median imputation can be used.
- For a large dataset with a high percentage of missing data, KNN imputation can be used.
- In some cases, it is necessary to consider the reason why the data is missing and use domain knowledge to impute or remove the missing data.

## 2.3 Identifying Outliers and Anomalies
Outliers or anomalies are data points that are significantly different from the other data points in the dataset. They can occur due to measurement errors or other sources of variation. Outliers can be identified using the following methods:

- Box plots: A box plot can be used to visualize the distribution of the data and identify any outliers. Outliers are defined as data points that fall outside the whiskers of the box plot.
- Z-score: A z-score can be used to identify outliers. Data points that have a z-score greater than 3 or less than -3 are considered outliers.
- Visual inspection: Outliers can be identified by visual inspection of the data.

Once outliers have been identified, there are several ways to handle them:

- Remove them: Outliers can be removed from the dataset if they are the result of measurement errors or other sources of variation.
- Adjust them: Outliers can be adjusted to be closer to the other data points in the dataset.

# 3 Data Exploration

After cleaning and preprocessing the data, the next step is to explore the data. This involves identifying any patterns or trends in the data and understanding the relationships between variables. 

## 3.1 Visualizing the data

One common way to explore the data is through visualizations such as charts or graphs. Some common types of visualizations include:

- **Scatter plots**: used to explore the relationship between two continuous variables.
- **Line charts**: used to visualize trends over time.
- **Bar charts**: used to compare values between different categories.
- **Histograms**: used to visualize the distribution of a single variable.

Visualizations can be created using tools such as Matplotlib, Seaborn, or Plotly.

## 3.2 Exploratory data analysis (EDA)

EDA involves using statistical techniques to explore the data and identify patterns or relationships between variables. Some common techniques include:

- **Clustering**: used to group data points with similar characteristics.
- **Dimensionality reduction**: used to reduce the number of variables in the data while preserving important information.
- **Correlation analysis**: used to identify relationships between variables.

Tools such as NumPy, Pandas, and Scikit-learn can be used to perform EDA.

### 3.2.1 Clustering
- Clustering is a technique used to group similar data points together. It can help identify patterns or groups in the data.
- Types of clustering: k-means, hierarchical clustering, etc.
- Example: use k-means clustering to group similar customers together based on their purchasing behavior.

### 3.2.2 Dimensionality reduction
- Dimensionality reduction is a technique used to reduce the number of variables in the data. It can help simplify the data and make it easier to analyze.
- Types of dimensionality reduction: principal component analysis (PCA), t-SNE, etc.
- Example: use PCA to reduce the number of variables in a dataset containing many correlated features.

### 3.3.3 Correlation analysis
- Correlation analysis is a technique used to identify the strength of the relationship between two variables.
- Types of correlation analysis: Pearson correlation coefficient, Spearman rank correlation coefficient, etc.
- Example: calculate the Pearson correlation coefficient between the target variable and each feature to identify potential predictors.

## 3.3 Correlations and Patterns

Correlations and patterns in the dataset can be identified using the following methods:

- Correlation matrix: A correlation matrix can be used to identify correlations between variables in the dataset.
- Scatter plots: Scatter plots can be used to visualize the relationship between two variables in the dataset.
- Heat maps: Heat maps can be used to visualize the relationships between multiple variables in the dataset.

Once correlations and patterns have been identified, they can be used to perform predictive modeling or forecasting based on the dataset.

## 3.4 Data transformation

Before applying machine learning algorithms, it may be necessary to transform the data. Common transformations include:

- **Scaling**: used to rescale data to a specific range.
- **Normalization**: used to transform data to have a Gaussian distribution.
- **Feature engineering**: creating new features from existing features to improve model performance.

Tools such as Scikit-learn and TensorFlow can be used to perform data transformations. 

Overall, exploring the data is a crucial step in the data analysis process. It allows us to gain insights into the data and understand the relationships between variables, which can inform the development of machine learning models.

# 4 Statistical Data Analysis

Statistical analysis is a key step in any data analysis project. It involves selecting and performing appropriate statistical analysis techniques to answer the research questions or hypotheses. Some common statistical analysis techniques include:
- **Regression analysis**: This is used to model the relationship between one or more independent variables and a dependent variable. One common type of regression analysis is the Generalized Linear Model (GLM), which is used to model the relationship between a dependent variable and a set of independent variables.
- **Hypothesis testing**: This is used to test a hypothesis or research question using statistical methods. It involves formulating a null hypothesis and an alternative hypothesis, collecting data, and then using statistical methods to determine whether to reject or fail to reject the null hypothesis.
- **Machine learning algorithms**: These are used to automatically learn patterns and relationships in data, and to make predictions or classifications based on those patterns. One common machine learning algorithm is the Gradient Boosted Machine (GBM), which is a type of decision tree algorithm that builds a model by iteratively adding decision trees to the model.

## 4.1 Regression Analysis and GLMs
GLMs are a class of regression models that generalize linear regression to accommodate response variables that have error distributions other than the normal distribution. GLMs are widely used in many fields, including biology, social sciences, engineering, and economics.

The general form of a GLM is:

$$g(\mathbb{E}(Y))=\beta_0+\beta_1X_1+\beta_2X_2+\cdots+\beta_pX_p$$

where $\mathbb{E}(Y)$ is the expected value of the response variable, $g(.)$ is the link function, $\beta_0$ is the intercept, $\beta_1, ..., \beta_p$ are the coefficients for the predictor variables $X_1, ..., X_p$, respectively.

The link function is used to link the expected value of the response variable to the linear combination of the predictor variables. Some commonly used link functions include the logit link for binary data, the identity link for continuous data, and the log link for count data.

## 4.2 Hypothesis Testing
Hypothesis testing is a statistical technique used to determine whether an observed effect is statistically significant or is likely to have occurred by chance. The process of hypothesis testing involves setting up a null hypothesis and an alternative hypothesis, calculating a test statistic, and comparing the test statistic to a critical value to determine whether to reject or fail to reject the null hypothesis.

## 4.3 Machine Learning Algorithms and GBMs
Machine learning algorithms are a class of algorithms that can be used to build predictive models from data. Machine learning algorithms are widely used in many fields, including finance, healthcare, and marketing.

Some common machine learning algorithms include decision trees, random forests, support vector machines, and neural networks. These algorithms can be used for both regression and classification problems and are known for their high predictive accuracy.

Gradient Boosted Machines (GBMs) are a class of machine learning algorithms that are used for both regression and classification problems. GBMs combine the strengths of decision trees and boosting to create a powerful and flexible modeling approach.

GBMs work by iteratively adding decision trees to the model, with each tree trying to correct the errors of the previous tree. The output of the model is the weighted sum of the outputs of all the trees.

GBMs can be used for both regression and classification problems, and are known for their high predictive accuracy and robustness to outliers.

## 4.4 Predictive Modeling and Forecasting

Predictive modeling and forecasting can be performed using machine learning algorithms such as:

- Linear regression: A linear regression model can be used to predict the value of a dependent variable based on one or more independent variables.
- Decision trees: Decision trees can be used to predict the value of a dependent variable based on a set of independent variables.
- Random forests: Random forests can be used to predict the value of a dependent variable based on a set of independent variables.

Before performing predictive modeling or forecasting, it is important to split the dataset into training and testing sets to avoid overfitting the model to the data. Once the model has been trained, it can be used to make predictions on new data.

# 5 Interpret the Results
Interpreting the results is a crucial step in the data analysis process. Here are some important points to keep in mind:

- Look for statistical significance: In many cases, statistical tests are used to determine whether the results are significant. This means that the observed differences or relationships are unlikely to be due to chance. It is important to interpret the p-values and confidence intervals associated with these tests in order to determine whether the results are statistically significant.
- Consider effect sizes: Even if the results are statistically significant, it is important to consider the size of the effect. Small effect sizes may not be practically significant, while large effect sizes may be of great practical importance.
- Consider limitations and potential confounding factors: It is important to consider any potential limitations or sources of bias in the analysis. This may include issues such as missing data, confounding variables, or selection bias. It is important to discuss these limitations when presenting the results.
- Draw conclusions based on the findings: Based on the results of the analysis, draw conclusions about the research questions or hypotheses. It is important to present these conclusions clearly and concisely, and to avoid overstating the results or making conclusions that are not supported by the data.
- Discuss implications for future research: Finally, it is important to discuss the implications of the results for future research. This may include recommendations for further studies, suggestions for alternative analysis methods, or discussion of potential practical applications of the findings.

|![image](https://user-images.githubusercontent.com/19381768/231360614-d7b298b4-a305-4b87-881b-6c6e68d97f85.png)|
|:--:|
|Confounding Variables|
|![image](https://user-images.githubusercontent.com/19381768/231360883-4493bdde-d9da-4bf3-8b7e-2cf4eff5f7f8.png)|
|Selection Bias|

