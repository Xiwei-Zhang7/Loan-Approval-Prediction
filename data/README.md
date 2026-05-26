# Data

This folder contains the original loan approval dataset used in the project:

```text
LoanApprovalPrediction.csv
```

The dataset is publicly available on Kaggle and was used for an academic machine learning project.

## Dataset Structure

The dataset contains 598 observations and 13 variables:

```text
Loan_ID
Gender
Married
Dependents
Education
Self_Employed
ApplicantIncome
CoapplicantIncome
LoanAmount
Loan_Amount_Term
Credit_History
Property_Area
Loan_Status
```

The target variable is:

```text
Loan_Status
```

where:

```text
Y = approved loan application
N = denied loan application
```

## Missing Values

The original dataset contains missing values in:

```text
Dependents
LoanAmount
Loan_Amount_Term
Credit_History
```

The notebook handles missing values using simple imputation before model fitting.
