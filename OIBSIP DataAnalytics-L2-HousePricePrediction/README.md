# House Price Prediction with Linear Regression

## 1. Project Overview

This project builds and evaluates machine learning regression models to predict house prices based on property characteristics and location information.

The main objective is to understand the complete machine learning workflow, from exploratory data analysis (EDA) and data preprocessing to model training, evaluation, visualization, and interpretation.

## 2. Objectives

- Explore the dataset and analyze house-price distributions.
- Identify potential predictors of house prices.
- Investigate correlations between numerical features and prices.
- Handle invalid target values and prepare features for modeling.
- Encode categorical variables using One-Hot Encoding.
- Train a Linear Regression model using an 80/20 train/test split.
- Evaluate performance using MSE, RMSE, and R².
- Analyze actual versus predicted prices, residuals, and model coefficients.
- Compare Linear Regression with Ridge Regression.

## 3. Dataset

The dataset contains 4,600 records and 18 columns.

The target variable is `price`. Features include:

- **Property size:** `sqft_living`, `sqft_lot`, `sqft_above`, `sqft_basement`
- **Property characteristics:** `bedrooms`, `bathrooms`, `floors`, `condition`, `view`, `waterfront`
- **Property age:** `yr_built`, `yr_renovated`
- **Location:** `city`, `statezip`, `country`

The dataset had no missing values or exact duplicate rows. However, 49 records had a price of zero. These records were excluded from modeling because zero was not considered a meaningful house-sale price for this task.

The modeling dataset therefore contained 4,551 records.

**Dataset source:** Add the original dataset URL here.

## 4. Technologies Used

- Python
- pandas
- NumPy
- scikit-learn
- Matplotlib
- Seaborn
- Jupyter Notebook

## 5. Project Workflow

### Exploratory Data Analysis

- Inspected dataset dimensions, columns, and descriptive statistics.
- Checked missing values and duplicate rows.
- Examined zero-price records and unusually high prices.
- Visualized the distribution of house prices.
- Created a correlation heatmap to investigate relationships between numerical features and the target.

### Data Preprocessing

- Excluded zero-price records.
- Selected numerical property features and categorical location features.
- Excluded the raw `date` and `street` columns from the initial model.
- Used median imputation for numerical features and most-frequent imputation for categorical features.
- Applied One-Hot Encoding to categorical features.
- Used a scikit-learn preprocessing pipeline to avoid fitting preprocessing steps on the test data.

### Model Training

The dataset was divided into:
- 80% training data
- 20% testing data

Two regression models were evaluated:

1. Linear Regression
2. Ridge Regression with `alpha=1.0`

### Evaluation Metrics

- **Mean Squared Error (MSE):** Average squared prediction error.
- **Root Mean Squared Error (RMSE):** Square root of MSE, expressed in the target's units.
- **R² Score:** Measures how much variation in the test-set target is explained by the model.

## 6. Model Results

| Metric | Linear Regression | Ridge Regression |
|---|---:|---:|
| MSE | 54,014,042,107.23 | 68,365,370,000 approximately |
| RMSE | 232,409.21 | 261,467.72 |
| R² Score | 0.6369 | 0.5405 |

Linear Regression performed better than Ridge Regression with the tested settings, achieving a lower RMSE and a higher R² score.

## 7. Visualizations and Interpretation

The notebook includes:

- House-price distribution histogram.
- Numerical-feature correlation heatmap.
- Actual versus predicted house-price scatter plot.
- Residual plot and residual distribution.
- Analysis of the largest positive and negative model coefficients.
- Comparison of Linear Regression and Ridge Regression.

The coefficient analysis helps show how the fitted model associates individual features with predicted prices, holding other encoded features constant. Coefficients indicate model relationships, not necessarily causal effects.

## 8. Conclusion

The Linear Regression model achieved an R² score of 0.6369 and an RMSE of 232,409.21 on the test set. This suggests that it explained approximately 63.69% of the variation in observed test-set house prices, although prediction errors remained substantial.

Ridge Regression with `alpha=1.0` performed less effectively on the same test split. Future improvements could include tuning the regularization parameter, investigating extreme-price records, engineering date-related features, and evaluating additional regression algorithms.

This project demonstrates the practical use of regression, feature preprocessing, evaluation metrics, and model interpretation for house-price prediction.

## 9. How to Run

1. Install the required Python libraries.
2. Download the dataset from the original source listed above.
3. Update the dataset path in the notebook.
4. Open `House_Price_Linear_Regression.ipynb` in Jupyter Notebook.
5. Run the notebook cells in order.

## 10. Project Structure

```text
DataAnalytics-L2-HousePricePrediction/
├── House_Price_Linear_Regression.ipynb
├── README.md
└── screenshots/
```

## 11. Future Improvements

- Tune Ridge Regression using cross-validation.
- Investigate unusual or extreme target values.
- Explore additional feature engineering.
- Compare other regression algorithms.
- Evaluate model performance across different test splits.

## 12. Internship Track

Oasis Infobyte — Data Analytics, Level 2

**Project:** Predicting House Prices with Linear Regression