# Credit Risk and Loan Default Prediction

**TS Academy Data Science Capstone | Group 01**  
**Capstone Grade: 79**

## Project Overview

This project explores how machine learning can help identify patterns associated with loan default using historical borrower and loan data.

Our group discussed the project and shared ideas at the beginning. After that, each member developed an individual notebook. After comparing our work, **my notebook was selected as the final group submission**.

## Business Problem

Lenders need to assess the risk of borrowers defaulting on loans. This project investigates how borrower and loan characteristics can help identify patterns associated with default and support more informed lending decisions.

## Dataset

- **Source:** [Kaggle Credit Risk Dataset](https://www.kaggle.com/datasets/laotse/credit-risk-dataset)
- **Original size:** 32,581 rows and 12 columns
- **Target variable:** `loan_status`

The dataset includes borrower income, age, employment length, loan amount, interest rate, loan grade, home ownership, loan purpose, and previous default history.

## Methodology

### 1. Data Exploration and SQL

- Examined the dataset's structure, missing values, distributions, and target imbalance.
- Used SQLite and SQL queries to investigate default rates across loan grades, loan purposes, and home-ownership categories.
- Removed duplicate records and addressed implausible values.

### 2. Feature Engineering and Preprocessing

- Created income bands and interaction features, including renter burden and prior-default burden.
- Applied ordinal and one-hot encoding to categorical variables.
- Used standardisation where appropriate and fitted learned preprocessing steps using training data to reduce data leakage.

### 3. Clustering

- Evaluated K-Means for K values from 2 to 10.
- Used elbow and silhouette analysis to select two clusters.
- Visualised the clusters using PCA.

### 4. Classification

Compared Logistic Regression, Decision Tree, and Random Forest against a stratified Dummy Classifier baseline.

### 5. Imbalance Handling

Evaluated class weighting and threshold tuning to understand how different approaches affect the identification of default cases.

### 6. Classification Depth Track

- Evaluated four classifiers using five-fold stratified cross-validation.
- Compared ROC curves.
- Examined permutation feature importance across models.

## Final Model and Results

My selected final model was a **Random Forest classifier** using a classification threshold of 0.50.

| Metric | Dummy Classifier | Random Forest |
|---|---:|---:|
| Accuracy | 65.42% | 93.43% |
| Precision | 20.70% | 96.79% |
| Recall | 20.52% | 72.36% |
| F1 score | 20.61% | 82.81% |
| ROC AUC | 49.26% | 92.84% |

The Random Forest substantially outperformed the dummy baseline on F1 score and ROC AUC.

The two clusters had historical default rates of 40.58% and 17.52%, indicating different risk profiles in the dataset. Feature-importance analysis also highlighted variables such as loan grade, renter burden, and personal income.

## Potential Business Applications

A model like this could help lenders flag applications for further review, investigate factors associated with default, and support portfolio-level risk analysis.

Before real-world use, it would require validation on newer data, fairness and bias assessments, ongoing monitoring, and confirmation that all predictors are available when a lending decision is made. Predictions should support responsible lending decisions rather than automatically determine them.

## Tools and Technologies

- Python
- Pandas and NumPy
- SQLite and SQL
- Scikit-learn
- Matplotlib and Seaborn
- Jupyter Notebook / Google Colab

## Key Learning Outcomes

This project strengthened my practical understanding of the end-to-end machine learning workflow, including data cleaning, feature engineering, clustering, classification, and model evaluation. It also reinforced the importance of preventing data leakage and connecting technical results to business decisions.

## Project File

`group_01_ebube_kingsley_ozue.ipynb` — the complete capstone notebook containing code, analysis, visualisations, and model evaluation.

## Acknowledgement

Completed as part of the TS Academy Data Science programme, Group 01 Credit Risk / Loan Default capstone.

**Capstone Grade: 79**
