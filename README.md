# Loan Approval Prediction: Supervised Learning Models

This repository focuses on my individual **supervised learning** contribution to a group academic project on loan approval prediction.

The task is a binary classification problem:

> Can we classify loan applications as approved or denied based on applicant attributes?

The target variable is `Loan_Status`.

## Contribution Note

This was originally a group academic project by **Lening Gao, Selina Salameh, and Xiwei Zhang**.

This repository focuses on my individual contribution: the **supervised learning** section. My work focused on fitting, evaluating, and interpreting three classification models:

- logistic regression;
- decision tree;
- k-nearest neighbors.

Other parts of the original group project, such as visualization, PCA, logistic PCA, and unsupervised clustering, are not the main focus of this repository.

## Project Overview

In financial services, predicting loan approval decisions is important for risk management and lending decisions. This project uses applicant-level information such as income, loan amount, credit history, education, marital status, property area, and loan approval outcome to classify loan applications as approved or denied.

The supervised learning workflow includes:

1. loading the loan approval dataset;
2. handling missing values;
3. encoding categorical variables;
4. splitting the data into training and testing sets;
5. balancing the training data;
6. fitting classification models;
7. evaluating models using accuracy, precision, recall, F1 score, and AUC;
8. interpreting the business trade-off between catching risky applications and avoiding false declines.

## Dataset

The dataset used in the original project is a publicly available loan approval dataset that can be found on Kaggle. The full dataset is not redistributed in this repository.

The expected variables are:

- `Loan_ID`
- `Gender`
- `Married`
- `Dependents`
- `Education`
- `Self_Employed`
- `ApplicantIncome`
- `CoapplicantIncome`
- `LoanAmount`
- `Loan_Amount_Term`
- `Credit_History`
- `Property_Area`
- `Loan_Status`

The target variable is `Loan_Status`, where `Y` indicates an approved loan application and `N` indicates a denied loan application.

A small synthetic sample file is included only to demonstrate the expected column structure.

## Models

The supervised learning section compares three classification models.

### Logistic Regression

Logistic regression estimates the probability of a loan application being denied or approved based on applicant attributes. It is interpretable and works well as a baseline model for credit-risk classification.

### Decision Tree

The decision tree is easy to explain because it produces rule-based splits, but it underperformed relative to the other models in the original project.

### k-Nearest Neighbors

k-nearest neighbors achieved strong overall accuracy and precision in the original project, but it had lower recall for risky applications. This makes it more suitable when reducing false declines is the priority.

## Main Results

The original project reported the following model-performance summary:

| Model | Accuracy | Precision | Recall | F1 Score | AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 0.7395 | 0.5714 | 0.6486 | 0.6076 | 0.7956 |
| k-Nearest Neighbors | 0.8067 | 0.8182 | 0.4865 | 0.6102 | 0.7189 |
| Decision Tree | 0.6639 | 0.4667 | 0.5676 | 0.5122 | 0.6374 |

The decision tree is easiest to interpret but has weaker predictive performance.

k-nearest neighbors achieves the highest accuracy and precision, which is useful when the priority is avoiding false declines.

Logistic regression provides the best AUC and recall, making it the preferred default model when the priority is identifying risky applications more effectively.

## Repository Structure

```text
.
├── README.md
├── .gitignore
├── data/
│   ├── README.md
│   └── sample_loan_data.csv
├── notebooks/
│   └── supervised_learning_models.Rmd
├── results/
│   └── model_performance_summary.csv
└── report/
    └── supervised_learning_summary.md
```

## Files

- `notebooks/supervised_learning_models.Rmd`: R Markdown workflow for supervised learning models.
- `data/README.md`: data availability note and expected data format.
- `data/sample_loan_data.csv`: small synthetic sample showing the expected structure.
- `results/model_performance_summary.csv`: model-performance summary from the original project.
- `report/supervised_learning_summary.md`: short written summary of my supervised learning contribution.

## Software

The project is written in **R**.

Main packages include:

- `dplyr`
- `readr`
- `caret`
- `pROC`
- `rpart`
- `ggplot2`

A basic installation command is:

```r
install.packages(c("dplyr", "readr", "caret", "pROC", "rpart", "ggplot2"))
```

## How to Run

Download the full loan approval dataset from Kaggle and place it locally as:

```text
data/loan_data.csv
```

Then open and run:

```text
notebooks/supervised_learning_models.Rmd
```

The sample file in `data/sample_loan_data.csv` is only for showing the expected column names and cannot reproduce the full empirical results.

## Skills Demonstrated

This project demonstrates:

- supervised classification;
- logistic regression;
- decision tree modeling;
- k-nearest neighbors;
- train/test evaluation;
- class balancing through undersampling;
- confusion-matrix interpretation;
- model evaluation using accuracy, precision, recall, F1 score, and AUC;
- business interpretation for loan approval and credit-risk decisions.

## Limitations

This repository focuses on the supervised learning part of a group academic project. It is not a production credit-risk system.

Important limitations include:

- the dataset is relatively small;
- the project does not include deployment;
- no model-monitoring pipeline is included;
- fairness and regulatory validation are not fully developed;
- threshold tuning could be improved for different business objectives.

## Possible Extensions

Future improvements could include:

- adding probability-threshold tuning;
- adding fairness metrics by demographic group;
- comparing random forest and gradient boosting models;
- adding a Shiny dashboard;
- rewriting the workflow in Python using pandas and scikit-learn.
