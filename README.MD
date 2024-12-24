# **Bank Loan Defaulter Prediction**
Create Bank Load Defaulter Prediction using machine learning and deploy it in Hugging Face.


## **Table of Contents**
1. [Introduction](#introduction)
2. [Data Overview](#data-overview)
3. [Background](#background)
4. [Methodology](#methodology)
5. [Machine Learning Models Employed](#machine-learning-models-employed)
6. [Model Analysis](#model-analysis)
7. [Conclusion](#conclusion)
8. [Model Deployment](#model-deployment)
9. [About Me](#about-me)


## **Introduction**
In the banking sector, lending is a key revenue source, but defaults can cause significant financial losses. Manual credit assessments are inefficient due to complex customer profiles and large data volumes. Predictive models can improve credit decision accuracy by identifying high-risk customers, minimizing losses, and enhancing operational efficiency. However, data imbalance, where defaults are rare, poses a challenge, often leading to model bias. To address this, a classification model optimized for recall score and minimizing False Negatives (FN) is essential. This approach helps avoid financial losses by accurately detecting high-risk customers and supports informed credit decision-making.


## **Data Overview**
This dataset obtained from [Kaggle](https://www.kaggle.com/datasets/ankitkalauni/bank-loan-defaulter-prediction-hackathon) and consist 34 features to determine whether a customer will default. The target variable is `Loan Status`, which indicates whether a customer is a **defaulter** (1) or **non-defaulter** (0). 

Here's a summary of the columns in the dataset.

Column | Data Type | Description
------ | :-------: | ----------
ID | Int | unique ID of representative
Loan Amount | Int| loan amount applied
Funded Amount | Int| loan amount funded
Funded Amount Investor | Float | loan amount approved by the investors
Term | Int | term of loan (in months)
Batch Enrolled | Object | batch numbers to representatives
Interest Rate | Float | interest rate (%) on loan
Grade | Object | grade by the bank
Sub Grade | Object | sub-grade by the bank
Employment Duration | Object | duration 
Home Ownership | Float | Owner ship of home
Verification Status | Object | Income verification by the bank
Payment Plan | Object | if any payment plan has started against loan
Loan Title | Object | loan title provided 
Debit to Income | Float | ratio of representative's total monthly debt repayment divided by self reported monthly income excluding mortgage
Delinquency - two years | Int | number of 30+ days delinquency in past 2 years
Inquires - six months | Int | total number of inquiries in last 6 months
Open Account | Int | number of open credit line in representative's credit line
Public Record | Int | number of derogatory public records
Revolving Balance | Int | total credit revolving balance
Revolving Utilities | Float | amount of credit a representative is using relative to revolving_balance
Total Accounts | Int | total number of credit lines available in representatives credit line
Initial List Status | Object | unique listing status of the loan - `W(Waiting)`, `F(Forwarded)`
Total Received Interest | Float | total interest received till date
Total Received Late Fee | Float |  total late fee received till date
Recoveries | Float | post charge off gross recovery
Collection Recovery Fee | Float | post charge off collection fee
Collection 12 months Medical | Int | total collections in last 12 months excluding medical collections
Application Type | Object | indicates when the representative is an individual or joint
Last week Pay | Int | indicates how long (in weeks) a representative has paid EMI after batch enrolled
Accounts Delinquent | Int | number of accounts on which the representative is delinquent
Total Collection Amount | Int | total current balance from all accounts
Total Current Balance | Int | total current balance from all accounts
Total Revolving Credit Limit | Int | total revolving credit limit
Loan Status | Int | `1 = Defaulter`, `0 = Non Defaulters` (Target feature)


## **Background**
Developing a model that can classify whether a customer will default or not based on the customer's data and characteristics, to be used as an initial analysis for determining whether to grant credit to the customer using a minimum Recall Score of 60%.


## **Methodology**
The methodology consists of the following steps:
1. **Data Loading and Inspection**: Load the dataset and inspect key details like column names, data types, and value ranges to ensure data quality and readiness for analysis.
2. **Exploratory Data Analysis (EDA)**: Analyze the dataset to uncover patterns, correlations, and trends.
3. **Feature Engineering**: Prepare the dataset by transforming variables, handling cardinality,  data balancing, and creating new features.
4. **Model Definition**: Utilize machine learning algorithms to train models and predict default.
5. **Model Evaluation**: Assess the model performance using key evaluation metrics **recall** to reduce false negative.
6. **Model Optimization and Deployment**: Fine-tune the best model and deploy it for reliable loan approval predictions.


## **Machine Learning Models Employed**
- K-Nearest Neighbours (KNN)
- Support Vector Machine (SVM)
- Decision Tree
- Random Forest
- XGBoost


## **Model Analysis**
The evaluation of the Random Forest model after hyperparameter tuning shows suboptimal performance. The recall value of 0.66 on the training data and 0.63 on the test data indicate moderate model performance with room for improvement. The model shows a strong bias toward class 1, with higher recall values for positive class detection (0.66 on train, 0.63 on test). However, recall for class 0 is much lower (0.38 on both train and test), suggesting poor detection of the negative class.

This may be due to feature selection based only on correlation with the target variable, using p-values less than 0.05. Many features were dropped, limiting the model’s ability to detect class 0. To improve, consulting with domain experts could help identify important features, rather than relying solely on statistical correlation.

## **Conclusion**
The banking data analysis aims to predict customer defaults through preprocessing steps like reducing data cardinality, balancing imbalanced classes, and feature selection using statistical methods. Five models will be tested, with the recall score used to minimize False Negatives (FN), which represent incorrect non-default predictions leading to potential financial losses.

The Random Forest classifier shows the most stability and will be tuned further to achieve a 60% recall score. Its strength lies in handling outliers due to its ensemble nature. However, the model is biased towards detecting **defaulters** (class 1) and struggles with **non-defaulters** (class 0), likely due to feature selection based solely on statistical correlations, potentially missing important domain-relevant features.

Improvement can be made by consulting domain experts to identify additional relevant features and better capture default risk patterns.


## **Model Deployment**
You can explore the deployed model in HuggingFace at the following link:
[HuggingFace Deployment](https://huggingface.co/spaces/abdul-aziz/loan-predictor)


## **About Me**
Abdul Aziz <br>
LinkedIn: [Abdul Aziz](https://www.linkedin.com/in/abdul-aziz-data-enthusiast/)


