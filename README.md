# 📊 Modelling Credit Defaults(Logistic Regression)
## 📌 Project Overview

This project aims to build a machine learning model that predicts whether a loan applicant will fully repay or default on a loan at the time of application. The dataset used is the well-known Lending Club Loan Dataset, which contains historical loan application data.

The goal is to assist financial institutions in making more informed lending decisions by identifying high-risk applicants early.

## 🎯 Objective

To develop a predictive classification model that can accurately determine whether a loan applicant will:
- ✔ Fully repay the loan
- ❌ Default on the loan
📂 Dataset Description
- Source: Lending Club Loan Dataset
- Original shape: 39,717 rows × 111 features
Target variable: Loan status (binary classification: Fully Paid vs Charged Off)

The dataset contains financial, demographic, and loan-related information about applicants.

## 🧹 Data Cleaning & Preprocessing

Extensive data cleaning was performed to ensure data quality and model reliability:

🔧 Key steps included:
- Removed columns with 100% missing values
- Dropped rows with more than 50% missing data
- Corrected incorrect data types
- Converted date columns to datetime format
- Converted percentage values by stripping % symbols
- Handled missing values using SimpleImputer
Removed:
- High-cardinality features (to reduce noise and dimensionality)
- Low-cardinality or uninformative features
- Leaky features (features not available at prediction time)
- Encoded categorical variables using One-Hot Encoding
- Standardized numerical features using StandardScaler
## 📊 Exploratory Data Analysis (EDA)

EDA was performed to better understand:

- Distribution of key numerical variables
- Relationship between features and loan default status
- Correlation and multicollinearity between predictors
- Impact of categorical variables on loan outcomes

This step helped in identifying:

- Redundant features
- Highly correlated variables
- Potential predictive signals
## 🤖 Model Building

A full machine learning pipeline was created using Scikit-learn, including:

🔹 Steps:
- Train-test split of the dataset
- Baseline model creation
- Feature preprocessing pipeline:
- Missing value imputation
- One-hot encoding
- Standard scaling
- Logistic Regression model training
🧠 Pipeline structure:
SimpleImputer for missing values
OneHotEncoder for categorical variables
StandardScaler for numerical variables
LogisticRegression as the classifier
## 📈 Model Evaluation

The model performed well and showed strong generalization:

- Training Accuracy: 85%
- Testing Accuracy: 86%
📌 Key insight:

The close performance between train and test sets indicates good generalization and no major overfitting.

## 🔍 Feature Importance Analysis

Feature importance was extracted from the logistic regression coefficients to interpret model behavior.

🔝 Most influential features included:
Specific categorical date-related variables
Geographic indicators (e.g., state-level features)

These features had strong predictive influence on loan repayment behavior.

📉 Least influential features:
Many sparse date-based one-hot encoded variables
Low-impact geographic categories

This suggests that some high-cardinality categorical variables may introduce noise rather than predictive value.

## 📊 Key Insights
- Loan repayment behavior is strongly influenced by specific categorical segments in the dataset
- High-cardinality categorical variables can dominate model behavior if not carefully engineered
- Proper preprocessing significantly improves model stability and performance
- Logistic Regression provides a strong baseline for classification tasks in financial risk modeling
## 🚀 Future Improvements

To further improve model performance and robustness, the following enhancements are recommended:

#### 🔧 Feature Engineering
- Extract meaningful components from date features:
Year, month, loan age, employment length trends
- Reduce reliance on one-hot encoding for high-cardinality features
#### 📈 Model Improvements
Try more advanced models:
- Decision Trees
- Random Forest
- XGBoost / LightGBM
- Gradient Boosting Machines
#### Perform hyperparameter tuning (GridSearchCV / RandomizedSearchCV)
#### ⚖️ Class Imbalance Handling
- Investigate target distribution
- Apply techniques such as: SMOTE, Class weighting
#### 🔍 Validation Strategy
- Use cross-validation instead of a single train-test split for more robust evaluation
#### 🧠 Interpretability
- Use SHAP or permutation importance for deeper feature interpretation
## 🛠️ Tech Stack
- Python 🐍
- Pandas & NumPy
- Scikit-learn
- Matplotlib / Seaborn
- Category Encoders
## 📌 Conclusion

This project demonstrates a complete end-to-end machine learning workflow—from raw financial data to a trained predictive model capable of estimating loan default risk. The model achieves strong baseline performance and provides meaningful insights into key drivers of loan repayment behavior.