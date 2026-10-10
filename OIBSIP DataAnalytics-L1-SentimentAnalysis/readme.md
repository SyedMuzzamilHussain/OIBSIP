# Sentiment Analysis of Twitter Data

## Project Overview

This project uses Natural Language Processing (NLP) and machine learning to classify Twitter text into three sentiment categories: Positive, Negative, and Neutral.

## Objectives

- Clean and preprocess Twitter text data.
- Explore the distribution of sentiment classes.
- Convert text into numerical features using TF-IDF.
- Train and compare Naive Bayes and Logistic Regression.
- Evaluate the models using classification metrics and confusion matrices.
- Visualize sentiment-related words and investigate prediction errors.

## Dataset

The project uses a Twitter sentiment dataset containing tweet IDs, entities, sentiment labels, and tweet text.

The original dataset contains 74,682 rows and four columns. The `Irrelevant` category was excluded to focus on three-class sentiment classification. Rows with missing or blank tweets and exact duplicate rows were removed during cleaning.

**Dataset source:** Add the original Kaggle dataset URL here.

## Tools and Technologies

- Python
- pandas and NumPy
- NLTK
- scikit-learn
- Matplotlib and Seaborn
- WordCloud
- Jupyter Notebook

## Methodology

1. Loaded and inspected the dataset.
2. Checked missing values, duplicate rows, and sentiment distribution.
3. Cleaned text by converting it to lowercase, removing URLs and punctuation, tokenizing, and removing stopwords while preserving important negation words.
4. Split the dataset into 80% training data and 20% testing data.
5. Used TF-IDF to convert cleaned tweets into numerical features.
6. Trained Multinomial Naive Bayes and Logistic Regression classifiers.
7. Evaluated both models using accuracy, macro precision, macro recall, macro F1-score, classification reports, and confusion matrices.
8. Created a sentiment distribution chart, three sentiment WordClouds, a model comparison chart, and an error analysis of five misclassified examples.

## Model Performance

| Metric | Naive Bayes | Logistic Regression |
|---|---:|---:|
| Accuracy | 77.47% | 83.19% |
| Macro Precision | 78.06% | 83.21% |
| Macro Recall | 76.66% | 82.79% |
| Macro F1-score | 76.80% | 82.92% |

## Conclusion

Logistic Regression performed better than Multinomial Naive Bayes across all four reported evaluation metrics, achieving 83.19% accuracy and an 82.92% macro F1-score.

The model could support customer feedback analysis, social media opinion monitoring, and general sentiment trend analysis. However, sarcasm, slang, ambiguous language, and missing context can lead to incorrect predictions.

## Future Improvements

- Tune model hyperparameters.
- Test additional classifiers.
- Explore lemmatization and improved text normalization.
- Evaluate advanced NLP models.
- Investigate misclassified examples to identify recurring errors.

## How to Run

1. Download the dataset from the source listed above.
2. Update the dataset path in the notebook if necessary.
3. Run the notebook cells in order.

## Project Author
Syed Muzzamil Hussain
