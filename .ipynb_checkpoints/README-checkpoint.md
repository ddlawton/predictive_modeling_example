# Predictive Modeling Example

This repository contains a predictive modeling project that demonstrates various machine learning techniques to classify customer default behavior based on their credit card history. Where it started as a take-home test for a job application, this project serves as an example of my data science and predictive modeling skills.

## Project Overview

The goal of this project is to predict whether a customer will default on their credit card payment based on features such as credit limit, payment history, demographic information, and other financial indicators. 

### Dataset

The dataset used in this project is sourced from a public credit card default dataset. It includes features such as:

- `customer_id`: Unique identifier for each customer
- `limit_bal`: Credit limit
- `sex`: Gender of the customer
- `education`: Education level
- `marriage`: Marital status
- `age`: Age of the customer
- `pay_1`, `pay_2`, ..., `pay_6`: Payment status for the past six months
- `bill_amt1`, `bill_amt2`, ..., `bill_amt6`: Bill statement amount for the past six months
- `pay_amt1`, `pay_amt2`, ..., `pay_amt6`: Amount paid in the past six months
- `default_oct`: Target variable indicating if the customer defaulted (1) or not (0)

## Methodology

### 1. Data Preprocessing

The initial step involves cleaning the dataset and preparing it for modeling. The preprocessing steps include:

- Handling missing values
- Encoding categorical variables
- Splitting the data into features (`X`) and labels (`y`)

### 2. Model Selection

Several predictive models were evaluated in this project:

- **Logistic Regression**
- **Random Forest Classifier**
- **XGBoost Classifier**
- **Support Vector Classifier (SVC)**
- **K-Nearest Neighbors (KNN)**
- **Ensemble Modeling**: A combination of all the above models
- **Stacking**: A model stacking approach with a linear regression on top of the best models

### 3. Hyperparameter Tuning

Hyperparameter tuning was performed for the models using techniques such as Grid Search and Random Search to optimize their performance.

### 4. Evaluation Metrics

Each model's performance was assessed using the following metrics:

- **Log Loss**
- **Area Under the Curve (AUC)**
- **Confusion Matrix**

### 5. Final Assessment on Test Split

A global train/test split was conducted to assess the performance of each model on the final test data. The evaluation of each model provided insights into their effectiveness in predicting customer defaults.

### Confusion Matrix Analysis

- The confusion matrices for the Random Forest and Stacking models were analyzed to compare their performance in terms of true positives, false positives, true negatives, and false negatives.
- The choice of the final model was based on a balance between precision and recall.

## Usage

To run this project, clone the repository and install the required packages. The main notebook `red_venutres_take_home 3/code/take_home_answer.ipynb` contains all the code for data preprocessing, model training, and evaluation.

```bash
git clone https://github.com/yourusername/repo-name.git
cd repo-name
pip install -r requirements.txt
