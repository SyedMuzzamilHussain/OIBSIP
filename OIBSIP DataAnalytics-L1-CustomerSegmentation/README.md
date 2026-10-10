# Customer Segmentation Analysis Using K-Means

## Project Overview

This project applies customer segmentation techniques to an online retail dataset using the K-Means clustering algorithm. The objective is to group customers according to their purchasing behaviour and develop marketing recommendations for each segment.

This project was completed as part of the Oasis Infobyte Data Analytics Internship — Level 1, Task 2.

## Objectives

- Inspect and clean retail transaction data.
- Calculate Recency, Frequency, and Monetary (RFM) features.
- Standardize behavioural features using StandardScaler.
- Use the Elbow Method to select a practical number of clusters.
- Apply K-Means clustering.
- Visualize customer segments.
- Profile each cluster and recommend marketing actions.

## Tools and Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Dataset

The Online Retail dataset contains transaction records with fields including invoice number, product code, quantity, invoice date, unit price, customer ID, and country.

The original dataset contained 541,909 rows and 8 columns.

## Data Cleaning

The following steps were performed:

1. Removed exact duplicate rows.
2. Excluded transactions without a CustomerID.
3. Excluded cancelled invoices.
4. Excluded records with non-positive quantities or unit prices.
5. Created a Revenue column using Quantity multiplied by UnitPrice.

After cleaning, the dataset contained 392,692 rows and 4,338 unique customers, with no missing values remaining in the cleaned DataFrame.

**Limitation:** Returns and cancelled transactions were excluded. Therefore, monetary values represent positive purchase transactions rather than net spending after returns.

## RFM Analysis

Three customer-level behavioural features were calculated:

- **Recency:** Number of days since the customer's most recent purchase, measured relative to one day after the latest transaction in the dataset.
- **Frequency:** Number of distinct invoices associated with the customer.
- **Monetary:** Total value of positive purchase transactions for the customer.

The RFM table contained 4,338 customers.

### RFM Summary

| Metric | Mean | Median |
|---|---:|---:|
| Recency | 92.54 | 51 |
| Frequency | 4.27 | 2 |
| Monetary | 2,048.69 | 668.57 |

## Feature Scaling and Clustering

The three RFM features were standardized using `StandardScaler`.

The Elbow Method was evaluated for K values from 2 to 10. Based on the plotted curve, K = 4 was selected as an initial clustering choice.

K-Means was fitted with four clusters using `random_state=42` and `n_init=10`.

## Customer Segment Profiles

| Cluster | Customers | Average Recency | Average Frequency | Average Monetary |
|---|---:|---:|---:|---:|
| 0 | 3,054 | 43.70 | 3.68 | 1,353.63 |
| 1 | 1,067 | 248.08 | 1.55 | 478.85 |
| 2 | 13 | 7.38 | 82.54 | 127,187.96 |
| 3 | 204 | 15.50 | 22.33 | 12,690.50 |

## Customer Segmentation Insights

- **Cluster 0 — Regular customers:** The largest segment, with moderate recency and relatively low purchase frequency.
- **Cluster 1 — At-risk or inactive customers:** Customers with the longest average recency and the lowest average spending and frequency.
- **Cluster 2 — Very high-value customers:** A small segment with very recent purchases, high frequency, and exceptionally high monetary value.
- **Cluster 3 — Loyal, high-spending customers:** Customers with recent activity, relatively high frequency, and higher average monetary value.

These descriptions are interpretations of the cluster averages and should be validated against individual customer records.

## Marketing Recommendations

1. **Cluster 0:** Use relevant product recommendations, cross-selling, and loyalty rewards to encourage repeat purchases.
2. **Cluster 1:** Consider win-back campaigns and targeted reactivation offers.
3. **Cluster 2:** Provide personalized service and retention benefits, after validating the unusually high spending and purchase frequency.
4. **Cluster 3:** Offer loyalty benefits, early access to relevant products, and personalized recommendations.

## Visualizations

The project includes:

- Elbow Method plot
- Number of customers per cluster
- Recency vs Monetary scatter plot
- Frequency vs Monetary scatter plot

## Limitations and Future Improvements

- The four-cluster solution is an initial choice based on the Elbow Method.
- Monetary values are highly skewed, and Cluster 2 contains only 13 customers.
- Returns were excluded, so the analysis does not measure net spending after returns.
- Alternative values of K and outlier-handling methods could be compared to assess cluster stability and usefulness.

## How to Run the Project

1. Install Python and Jupyter Notebook.
2. Install the required libraries:

   `pip install pandas numpy matplotlib seaborn scikit-learn openpyxl jupyter`

3. Place `Online Retail.xlsx` in the appropriate location.
4. Open `Customer_Segmentation.ipynb`.
5. Update the dataset path if needed.
6. Run the notebook cells in order.

## Project Structure

```text
OIBSIP/
└── DataAnalytics-L1-CustomerSegmentation/
    ├── Customer_Segmentation.ipynb
    ├── README.md
    └── screenshots/
```

## Conclusion

This project demonstrates how customer-level RFM features and K-Means clustering can be used to identify groups with different purchasing behaviours. The resulting segments can support targeted retention, reactivation, and loyalty strategies, subject to validation of the clustering results.

**Internship:** Oasis Infobyte — Data Analytics  
**Task:** Level 1, Task 2 — Customer Segmentation Analysis