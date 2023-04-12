# Supermarket Customer Transaction History Case Study

## Background:

A supermarket chain has provided a dataset containing transaction history for their customers. The client wishes to obtain business insights to improve customer retention, identify specific trends, and discover potential factors that can improve the supermarket's profits.

## Dataset:

The dummy dataset contains the following columns:

- Transaction_ID (integer): Unique identifier for each transaction
- Customer_ID (integer): Unique identifier for each customer
- Date (date): Date of the transaction
- Product_ID (integer): Unique identifier for each product
- Category (string): Product category (e.g., groceries, electronics, clothing)
- Quantity (integer): Quantity of items purchased
- Unit_Price (float): Price per unit of the product
- Total_Price (float): Total price of the transaction (Quantity * Unit_Price)
- Payment_Method (string): Payment method used (e.g., cash, credit card, debit card)
- Loyalty_Member (integer): Whether the customer is a loyalty program member (1 for yes, 0 for no)

## Tasks

1. **Understand data types, distribution, and descriptive statistics (measure of central tendency and spread)**: Describe the types of data in each column and calculate the mean, median, and standard deviation for numerical columns.

2. **Identify outliers and anomalies, propose data cleaning method (handling missing data) for the dataset**: Check for missing values, outliers, or any other data inconsistencies. Suggest methods for handling these issues, such as imputation or removal.

3. **Perform exploratory data analysis, identify data correlations and patterns**: Analyze the dataset for any correlations, trends, or patterns. Propose data transformation methods if needed to better understand the relationships within the data.

4. **Conduct statistical data analysis using GLMs and GBMs**: Use Generalized Linear Models (GLMs) to perform regression analysis and Gradient Boosted Machines (GBMs) to solve regression and classification problems. Test hypotheses about the relationships between variables.

5. **Propose predictive and forecasting modeling for the supermarket transaction history**: Based on your findings in the previous steps, suggest predictive models that could help the supermarket forecast future customer behavior or product sales.

6. **Interpret the results**: Discuss the results of your analyses, including the models you built, any insights you uncovered, and potential recommendations for the supermarket to improve customer retention, identify trends, and increase profits.

***Remember, you have 1 hour to complete this case study, and all questions should be answered in text format with no coding or visualization required.***

---

## Sample Answer for Task 1

Data types in the dataset are as follows:

- Transaction_ID: Integer (Discrete)
- Customer_ID: Integer (Discrete)
- Date: Date (Continuous)
- Product_ID: Integer (Discrete)
- Category: String (Categorical)
- Quantity: Integer (Discrete)
- Unit_Price: Float (Continuous)
- Total_Price: Float (Continuous)
- Payment_Method: String (Categorical)
- Loyalty_Member: Integer (Binary)

Descriptive statistics for numerical columns:
- Quantity:
  - Mean: 5.3
  - Median: 5
  - Standard Deviation: 2.1
- Unit_Price:
  - Mean: 12.4
  - Median: 11.5
  - Standard Deviation: 4.6
- Total_Price:
  - Mean: 65.8
  - Median: 62.3
  - Standard Deviation: 30.2

## Sample Answer for Task 2

Upon examining the dataset, we found the following issues:

1. Missing values: A small number of records have missing values for the 'Category' and 'Payment_Method' columns.
- Proposed solution: Since the number of missing values is small, we can either remove these records or impute the missing values with the mode of the respective columns.
2. Outliers: There are a few outliers in the 'Unit_Price' and 'Total_Price' columns, which could potentially skew our analysis.
- Proposed solution: We can use the Interquartile Range (IQR) method to identify and remove these outliers. Alternatively, we can apply data transformation methods such as log transformation to reduce the impact of outliers on our analysis.
3. Data inconsistencies: Some transactions have negative 'Quantity' values, which might indicate returned items or data entry errors.
- Proposed solution: We can treat these records as separate cases and analyze them separately or remove them from the dataset if they are determined to be data entry errors. If the negative values represent returned items, we can either analyze them separately or correct the 'Quantity' values by taking their absolute values.

After applying the proposed data cleaning methods, we will have a clean dataset to proceed with our analysis.
