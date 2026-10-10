Exploratory Data Analysis on Retail Sales Data

Project Overview

This project performs Exploratory Data Analysis (EDA) on a retail sales dataset using Python. The objective is to understand sales trends, customer demographics, product category performance, and purchasing patterns to derive useful business insights.

This project was completed as part of the Oasis Infobyte Data Analytics Internship — Level 1, Task 1.

Objectives

Inspect the dataset structure, data types, missing values, and duplicate records.

Calculate descriptive statistics for numerical variables.

Analyze monthly and quarterly sales trends.

Explore customer age groups and gender distribution.

Analyze transactions and revenue by product category.

Visualize correlations between numerical variables.

Identify additional insights from average transaction amounts by gender and category.

Provide actionable business recommendations.

Tools and Technologies

Python

Pandas

NumPy

Matplotlib

Seaborn

Jupyter Notebook

Dataset Information

The dataset contains 1,000 retail transactions with the following columns:

Transaction ID

Date

Customer ID

Gender

Age

Product Category

Quantity

Price per Unit

Total Amount

Data Quality Checks

No missing values were found in the inspected columns.

No duplicate rows were found.

No duplicate Transaction IDs were found.

Dates were converted to datetime format, with no invalid dates detected.

Customer ages ranged from 18 to 64.

Analysis Performed

1. Descriptive Statistics

Calculated the mean, median, mode, and standard deviation for numerical variables, including age, quantity, price per unit, and total amount.

2. Monthly Sales Analysis

Highest monthly sales: May 2023 — 53,150.

Lowest month in 2023: September — 23,620.

January 2024 recorded 1,530 in sales and requires a data-completeness check.

3. Quarterly Sales Analysis

Q1 2023: 108,500

Q2 2023: 123,735

Q3 2023: 96,045

Q4 2023: 126,190

Q1 2024: 1,530

Q4 2023 recorded the highest total sales among the quarters shown for 2023.

4. Customer Demographics

Gender distribution

Female: 510 transactions (51%)

Male: 490 transactions (49%)

Age groups

18–25: 169 transactions

26–35: 205 transactions

36–45: 202 transactions

46–55: 229 transactions

56–64: 195 transactions

The 46–55 age group recorded the highest number of transactions.

5. Product Category Analysis

Transaction counts

Clothing: 351

Electronics: 342

Beauty: 307

Total revenue by category

Electronics: 156,905

Clothing: 155,580

Beauty: 143,515

Electronics generated the highest total revenue, while Clothing had the highest transaction count.

6. Correlation Analysis

The correlation heatmap showed:

Price per Unit and Total Amount: 0.85

Quantity and Total Amount: 0.37

Age and Total Amount: -0.06

Quantity and Price per Unit: 0.02

These values describe linear relationships and do not establish causation.

7. Additional Insights

Average transaction amounts by gender and category:

Category

Female

Male

Beauty

450.78

487.13

Clothing

467.10

419.80

Electronics

451.38

466.10

Female customers had a higher average transaction amount in Clothing, while male customers had higher averages in Beauty and Electronics.

Business Recommendations

Improve inventory planning: Review demand and stock availability for Clothing and Electronics using both transaction counts and revenue.

Investigate sales fluctuations: Examine the reasons for the strong performance in May and the decline in September 2023.

Evaluate profitability: Compare product costs and profit margins before making inventory or marketing decisions.

Understand customer preferences: Investigate category-level purchasing patterns before developing targeted promotions.

Monitor sales regularly: Track monthly revenue, transaction counts, average transaction value, and category performance.

Validate incomplete data: Confirm whether January 2024 represents a complete month before making comparisons.

Limitations

The dataset contains product categories but does not contain individual product names. Therefore, a genuine ranking of the top 10 individual products could not be calculated.

January 2024 has a very low recorded sales total and requires a completeness check.

The dataset's currency has not been verified.

Observed relationships do not prove causation.

How to Run the Project

Install Python and Jupyter Notebook.

Install the required libraries:

pip install pandas numpy matplotlib seaborn jupyter

Place the dataset CSV file in the appropriate project directory.

Open Retail_Sales_Eda.ipynb in Jupyter Notebook.

Update the CSV file path in the data-loading cell if necessary.

Run the notebook cells in order to reproduce the analysis and visualizations.

Project Structure

OIBSIP/

└── DataAnalytics-L1-EDARetailSales/

├── Retail_Sales_Eda.ipynb

├── README.md

└── screenshots/

Conclusion

This project demonstrates how Python-based EDA can be used to examine retail sales, understand customer transaction patterns, identify category-level performance differences, and develop data-driven business recommendations.

Internship: Oasis Infobyte — Data Analytics

Task: Level 1, Task 1 — EDA on Retail Sales Data
