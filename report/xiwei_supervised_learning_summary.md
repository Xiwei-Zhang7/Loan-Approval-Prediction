# Xiwei Zhang — Supervised Learning Contribution Summary

This document summarizes my supervised learning contribution to the group loan approval prediction project.

## Goal

The goal of the supervised learning section was to classify loan applications as approved or denied using applicant-level attributes.

## Models Compared

I focused on three supervised classification models:

1. Logistic regression
2. Decision tree
3. k-nearest neighbors

## Evaluation Metrics

The models were evaluated using:

- accuracy;
- precision;
- recall;
- F1 score;
- AUC.

## Main Findings

The decision tree was easy to interpret but underperformed relative to the other two models.

k-nearest neighbors achieved the highest accuracy and precision. This makes it useful when the business priority is avoiding false declines.

Logistic regression achieved the best AUC and recall. This makes it more useful when the business priority is identifying risky applications and reducing potential credit losses.

## Recommended Model

The recommended default model is logistic regression because it provides the strongest overall risk-separation ability and the best recall among the compared models.

k-nearest neighbors can be considered as an accuracy-focused second-stage model when the business priority is reducing unnecessary customer rejections.
