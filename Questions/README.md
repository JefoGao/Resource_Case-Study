# 1 Prerequisite: Understand the Distribution of Variables in a Dataset

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

# 2 Handle Missing Data
- Missing data refers to observations or values that are not present in the dataset.
- Missing data can occur for various reasons such as non-response, data entry errors, or faulty measurements.

## 2.1 Detection of Missing Data
- Visual inspection of the dataset to identify missing data through heatmaps, bar plots, or line graphs.
- Using built-in functions in python libraries like pandas.isnull() or numpy.isnan().

## 2.2 Handling Missing Data
- Removal of missing data:
    - Listwise deletion (removing entire rows with missing values).
    - Pairwise deletion (removing specific column/variable if any missing values exist).
- Imputation of missing data:
    - Mean imputation (replacing missing values with the mean of the available data).
    - Mode imputation (replacing missing values with the mode of the available data).
    - Median imputation (replacing missing values with the median of the available data).
    - Regression imputation (replacing missing values with predicted values using regression models).
    - KNN imputation (replacing missing values with predicted values using KNN algorithm).

## 2.3 Imputation of Missing Data

Imputation of missing data involves filling in the missing values using a method that takes into account the remaining data in the dataset.

|Advantages|Disadvantages|
|--|--|
|<ul><li>Utilizes all the available data.</li><li>Preserves the variability of the data.</li><li>Enables the use of more advanced statistical methods.</li></ul>|<ul><li>May introduce bias if the method used is not appropriate for the dataset.</li><li>Can affect the distribution of the data.</li><li>Can inflate standard errors or confidence intervals.</li></ul>|

### 2.3.1 Imputation Methods Use Case

|Method|Use Case|
|--|--|
|Mean Imputation|<ul><li>Replacing missing values with the mean of the available data.</li><li>Works well when the data is normally distributed or symmetric.</li></ul>|
|Mode Imputation|<ul><li>Replacing missing values with the mode (most common value) of the available data.</li><li>Works well for nominal or ordinal data.</li></ul>|
|Median Imputation|<ul><li>Replacing missing values with the median of the available data.</li><li>Works well for data with a skewed distribution or outliers.</li></ul>
|Regression Imputation|<ul><li>Replacing missing values with predicted values using regression models.</li><li>Works well when there is a linear relationship between the missing variable and other variables in the dataset.</li><li>However, regression imputation assumes a linear relationship between the variables and may not work well for non-linear relationships or interactions between variables.</li></ul>|

### 2.3.2 Regression Models
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

### 2.3 Handling Missing Data based on Data Type and Distribution
- For nominal or ordinal data with low missing data percentage, removal or mode imputation can be used.
- For interval or ratio data with low missing data percentage, mean, median or regression imputation can be used.
- For bimodal or skewed data, median imputation can be used.
- For a large dataset with a high percentage of missing data, KNN imputation can be used.
- In some cases, it is necessary to consider the reason why the data is missing and use domain knowledge to impute or remove the missing data.



How would you detect and handle missing data in the dataset?
Can you identify any outliers or anomalies in the dataset? How would you handle them?
Can you identify any correlations or patterns in the dataset?
Can you perform any predictive modeling or forecasting based on the dataset?
Can you calculate any summary statistics, such as mean, median, or standard deviation, for specific variables in the dataset?
Can you perform any data transformations, such as normalization or scaling, on the dataset?
Can you create any visualizations or graphs to better understand the dataset?
How would you approach feature selection for a machine learning model based on the dataset?
Can you identify any potential biases or limitations in the dataset, and how would you address them?
