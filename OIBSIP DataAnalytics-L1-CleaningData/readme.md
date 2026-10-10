# Titanic Dataset — Data Cleaning and Quality Analysis

## Project Overview

This project demonstrates a systematic data cleaning workflow using Python, Pandas, and NumPy. The Titanic dataset was inspected and transformed to improve data quality and prepare it for further analysis.

This project was completed as part of the Oasis Infobyte Data Analytics Internship — Level 1, Task 3.

## Objectives

- Generate an initial data quality report.
- Identify and handle missing values.
- Check and remove duplicate rows where necessary.
- Standardize categorical values and data types.
- Detect potential outliers using the IQR method.
- Document cleaning decisions.
- Compare data quality before and after cleaning.
- Export the cleaned dataset to a new CSV file.

## Tools and Technologies

- Python
- Pandas
- NumPy
- Jupyter Notebook

## Dataset

The project uses the Titanic training dataset containing 891 passenger records and 12 original columns.

## Initial Data Quality Findings

| Column | Missing Values | Missing Percentage |
|---|---:|---:|
| Age | 177 | 19.87% |
| Cabin | 687 | 77.10% |
| Embarked | 2 | 0.22% |

No exact duplicate rows were found in the original dataset.

## Data Cleaning Steps

### 1. Missing Values

- **Age:** Missing values were filled with the median age.
- **Cabin:** Missing values were represented as `Unknown`.
- **Cabin_Missing:** An indicator column was created to preserve the original cabin-missing information.
- **Embarked:** Missing values were filled with the mode.

### 2. Duplicate Verification

Exact duplicate rows were checked. Since none were found, no rows were removed for duplication.

### 3. Standardization and Data Types

Categorical formatting was standardized for `Sex` and `Embarked`. Numeric fields were checked, and identifier/code columns were represented using suitable data types.

### 4. Outlier Detection

The Interquartile Range (IQR) method was applied to `Age`, `SibSp`, `Parch`, and `Fare`.

Potential outliers were reviewed rather than automatically removed. Unusual values may be legitimate passenger records.

### 5. Before-versus-After Comparison

A summary table was prepared to compare row count, column count, duplicate rows, missing values, and other quality indicators before and after cleaning.

## Cleaning Decisions

| Column | Treatment | Reason |
|---|---|---|
| Age | Median imputation | Robust to extreme values |
| Cabin | Fill with `Unknown` | Preserves records without inventing cabin information |
| Cabin_Missing | Binary indicator | Retains information about originally missing cabins |
| Embarked | Mode imputation | Only two values were missing |
| Potential outliers | Retained unless invalid | Statistical outliers are not automatically errors |

## Output

The cleaned dataset was exported as:

`Titanic_Cleaned.csv`

The original dataset was kept separate from the cleaned output.

## How to Run the Project

1. Install Python and Jupyter Notebook.
2. Install the required libraries:

   `pip install pandas numpy jupyter`

3. Place the original `train.csv` file in the project directory.
4. Open `Data_Cleaning.ipynb`.
5. Update the input and output file paths if necessary.
6. Run the notebook cells in order.

## Project Structure

```text
OIBSIP/
└── DataAnalytics-L1-CleaningData/
    ├── Data_Cleaning.ipynb
    ├── README.md
    ├── Titanic_Cleaned.csv
    └── train.csv
```

## Conclusion

This project demonstrates how a structured data cleaning workflow can improve data quality and prepare a dataset for analysis. Missing values, data types, categorical formatting, duplicates, and potential outliers were reviewed systematically, with decisions documented for transparency and reproducibility.

**Internship:** Oasis Infobyte — Data Analytics  
**Task:** Level 1, Task 3 — Cleaning Data