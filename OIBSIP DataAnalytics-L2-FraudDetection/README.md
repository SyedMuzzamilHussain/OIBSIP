# Credit Card Fraud Detection Using Machine Learning

## Project Overview

This project focuses on detecting fraudulent credit card transactions using machine learning techniques. The dataset is highly imbalanced, with fraudulent transactions representing only a small fraction of all transactions. The project addresses this challenge using SMOTE (Synthetic Minority Over-sampling Technique) and evaluates models using metrics suited to imbalanced classification.

The project was completed as part of the **Oasis Infobyte Data Analytics Internship — Level 2, Task 3**.

## Objectives

- Analyse the distribution of genuine and fraudulent transactions.
- Perform exploratory data analysis (EDA) on transaction amounts and time patterns.
- Understand why accuracy alone is misleading for imbalanced datasets.
- Apply SMOTE to the training data to address class imbalance.
- Train and compare Logistic Regression and Random Forest models.
- Evaluate models using precision, recall, F1-score, and ROC-AUC.
- Analyse confusion matrices, ROC curves, and feature importance.
- Discuss the precision–recall trade-off and production scalability.

## Dataset

**Dataset name:** Credit Card Fraud Detection

**Source:** [Kaggle — Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)

The dataset contains 284,807 transactions and 31 columns.

| Detail | Value |
|---|---:|
| Total transactions | 284,807 |
| Genuine transactions | 284,315 |
| Fraudulent transactions | 492 |
| Genuine transactions | 99.8273% |
| Fraudulent transactions | 0.1727% |
| Features | 30 |
| Target column | `Class` |

### Important Columns

- `Time`: Seconds elapsed since the first transaction in the dataset.
- `V1` to `V28`: Anonymized numerical features derived using Principal Component Analysis (PCA).
- `Amount`: Transaction amount.
- `Class`: Target variable, where `0` represents a genuine transaction and `1` represents a fraudulent transaction.

## Technologies Used

- Python
- pandas and NumPy
- Matplotlib and Seaborn
- scikit-learn
- imbalanced-learn (SMOTE)
- Jupyter Notebook

## Project Workflow

### 1. Data Loading and Exploration

- Loaded the dataset using pandas.
- Examined the dataset dimensions and sample records.
- Analysed class counts and calculated the fraud percentage.
- Investigated transaction amounts and elapsed-time patterns.

### 2. Class Imbalance Analysis

Only 0.1727% of transactions are fraudulent. A model that predicts every transaction as genuine could achieve approximately 99.83% accuracy while detecting no fraud cases.

Therefore, accuracy alone is insufficient for evaluating this project.

### 3. Data Preparation and SMOTE

- Separated input features from the target variable.
- Used a stratified 80/20 train/test split.
- Scaled features using `StandardScaler`, fitting the scaler only on the training data.
- Applied SMOTE to the training data only to oversample the minority class.
- Preserved the original class distribution in the test set for evaluation.

### 4. Model Training

Two classification algorithms were trained:

1. **Logistic Regression**
2. **Random Forest Classifier**

Both models were evaluated on the original, imbalanced test set.

### 5. Model Evaluation

The models were evaluated using:

- Precision
- Recall
- F1-score
- ROC-AUC
- Confusion matrices
- ROC curves

Random Forest feature importance was also examined to understand which features contributed most to its predictions.

## Results

The following results were obtained using the current model settings and default classification threshold.

| Metric | Logistic Regression | Random Forest |
|---|---:|---:|
| Precision | 0.0578 | 0.8710 |
| Recall | 0.9184 | 0.8265 |
| F1-score | 0.1088 | 0.8482 |
| ROC-AUC | 0.9708 | 0.9685 |

### Results Interpretation

**Logistic Regression**
- Achieved a recall of 91.84%.
- Detected a high proportion of fraudulent transactions.
- Had a low precision of 5.78%, indicating many false-positive predictions.

**Random Forest**
- Achieved a precision of 87.10%.
- Achieved an F1-score of 84.82%.
- Provided a more balanced precision–recall result at the current threshold.
- Had a recall of 82.65%, meaning some fraudulent transactions were missed.

Based on these results, Random Forest performed better in terms of precision and F1-score, while Logistic Regression achieved higher recall and slightly higher ROC-AUC.

## Why Recall and Precision Matter

Recall measures the proportion of actual fraud cases detected by the model. Higher recall can reduce missed fraud.

Precision measures the proportion of predicted fraud cases that are actually fraudulent. Higher precision can reduce unnecessary investigations and customer inconvenience.

The appropriate balance depends on the financial cost of missed fraud compared with the cost of false alarms. Classification thresholds should be tuned according to the intended use case.

## Scalability Considerations

One million transactions per hour is approximately 278 transactions per second. A production fraud detection system would require reliable, low-latency prediction and efficient feature processing.

Potential improvements include:

- Optimizing feature engineering and model inference.
- Using parallel model-serving instances and load balancing.
- Integrating a streaming platform such as Apache Kafka.
- Deploying containerized services with autoscaling.
- Monitoring latency, throughput, false positives, data drift, and model performance.
- Conducting load testing to verify the required transaction throughput.

The notebook demonstrates model training and evaluation; it does not establish that the model can already process one million transactions per hour. Production capacity would need to be validated through realistic performance testing.

## Limitations and Future Improvements

- Tune classification thresholds to achieve a suitable precision–recall balance.
- Use cross-validation and compare additional imbalance-handling techniques.
- Investigate feature scaling and model hyperparameters.
- Evaluate performance using additional metrics, such as the Precision–Recall AUC.
- Consider the financial costs of false positives and false negatives.
- Benchmark inference latency and throughput before deployment.

## How to Run the Project

1. Install Python and Jupyter Notebook.
2. Download `creditcard.csv` from the Kaggle dataset page.
3. Place the CSV file in the project directory, or update the notebook's file path.
4. Install the required libraries:

   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn jupyter
   ```

5. Open the notebook:

   ```bash
   jupyter notebook
   ```

6. Open `Fraud_Detection.ipynb` and execute the cells in order.

## Project Structure

```text
DataAnalytics-L2-FraudDetection/
├── Fraud_Detection.ipynb
├── README.md
└── screenshots/
    ├── class_distribution.png
    ├── transaction_amounts.png
    ├── confusion_matrices.png
    ├── roc_curves.png
    └── feature_importance.png
```

The screenshot filenames above are suggested names. Save the corresponding figures if you want to include them in the repository.

## Conclusion

This project demonstrates how machine learning can be applied to credit card fraud detection in a severely imbalanced dataset. SMOTE was used to address the class imbalance in the training data, and Logistic Regression and Random Forest were compared using precision, recall, F1-score, and ROC-AUC.

Random Forest produced the strongest F1-score under the tested settings, while Logistic Regression achieved higher recall. The results highlight the importance of selecting evaluation metrics based on the real-world cost of missed fraud and false alarms.

**Internship:** Oasis Infobyte  
**Track:** Data Analytics  
**Level:** Level 2  
**Task:** Task 3 — Fraud Detection