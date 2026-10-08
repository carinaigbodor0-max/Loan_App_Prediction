# Loan Application Prediction

## Project Overview

This project builds machine learning models to predict whether a loan
application will be approved or rejected based on applicant information.

The project focuses on data preprocessing, handling missing values,
encoding categorical variables, training classification models, and
evaluating model performance.

## Dataset

The dataset is stored in:

`data/loan_data.csv`

It contains **614 rows and 13 columns**.

### Columns

  Column              Description
  ------------------- ----------------------------------------
  Loan_ID             Unique loan application identifier
  Gender              Applicant gender
  Married             Whether the applicant is married
  Dependents          Number of dependents
  Education           Applicant's education level
  Self_Employed       Whether the applicant is self-employed
  ApplicantIncome     Applicant's income
  CoapplicantIncome   Co-applicant's income
  LoanAmount          Requested loan amount
  Loan_Amount_Term    Loan repayment term
  Credit_History      Applicant's credit history
  Property_Area       Area where the property is located
  Loan_Status         Loan approval status (Y/N)

## Data Preprocessing

The following preprocessing steps were carried out:

### 1. Removing Unnecessary Columns

`Loan_ID` was removed because it is an identifier and does not provide
useful predictive information.

### 2. Encoding Categorical Variables

Categorical variables were converted into numerical values so that they
could be used by machine learning models.

Examples include:

-   Gender: Male = 0, Female = 1
-   Married: No = 0, Yes = 1
-   Dependents: 0, 1, 2, 3+
-   Self_Employed: No = 0, Yes = 1
-   Property_Area: Urban = 0, Rural = 1, Semiurban = 2

### 3. Handling Missing Values

Missing values were identified in several columns.

For numerical columns such as `LoanAmount` and `Loan_Amount_Term`,
missing values were handled using mean imputation with `SimpleImputer`.

## Target Variable

The target variable is:

`Loan_Status`

-   `Y` = Loan approved
-   `N` = Loan not approved

## Machine Learning Models

Two classification models were evaluated:

1.  Logistic Regression
2.  Decision Tree Classifier

## Model Performance

### Logistic Regression

Accuracy: **86.18%**

Classification report:

  Class     Precision   Recall   F1-score
  ------- ----------- -------- ----------
  N              0.96     0.58       0.72
  Y              0.84     0.99       0.91

Confusion matrix:

``` text
[[22 16]
 [ 1 84]]
```

### Decision Tree Classifier

Accuracy: **74.80%**

Classification report:

  Class     Precision   Recall   F1-score
  ------- ----------- -------- ----------
  N              0.58     0.66       0.62
  Y              0.84     0.79       0.81

## Model Comparison

  Model                        Accuracy
  -------------------------- ----------
  Logistic Regression            86.18%
  Decision Tree Classifier       74.80%

Based on the reported accuracy, Logistic Regression performed better
than the Decision Tree Classifier on this dataset.

## Technologies Used

-   Python
-   Pandas
-   NumPy
-   Scikit-learn
-   Jupyter Notebook
-   Matplotlib / data visualization tools

## Project Structure

``` text
Loan_App_Prediction/
│
├── data/
│   └── loan_data.csv
│
├── Loan_App_Prediction.ipynb
│
└── README.md
```

## Conclusion

This project demonstrates a basic machine learning classification
workflow for loan approval prediction.

The process included:

-   Understanding the dataset
-   Identifying missing values
-   Cleaning and preprocessing the data
-   Encoding categorical variables
-   Training classification models
-   Evaluating model performance
-   Comparing different models

Logistic Regression achieved the higher reported accuracy of **86.18%**
among the two evaluated models.
