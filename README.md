# Network Intrusion Risk Analysis

**Capstone project | Data Analytics Programme, IIM Sirmaur × Masai**

## Overview

This project studies whether session-level network data can help classify potentially malicious network activity. Logistic Regression was evaluated using the Orange data-mining environment and PSPP.

## Problem Statement

Security teams need ways to prioritize network sessions for investigation. This project explores how a classification model can distinguish recorded attack sessions from non-attack sessions and how its errors should be interpreted.

## Dataset and Files

- `cybersecurity_intrusion_data.csv` — dataset used for the analysis.
- `network-intrusion-risk-analysis.pdf` — capstone report and supporting documentation.

The project materials report **9,537 sessions**. Verify the dataset's source, label definitions, and any licensing restrictions before redistribution.

## Tools and Methods

- Orange Data Mining
- PSPP
- Logistic Regression
- Classification evaluation
- Confusion-matrix analysis

## Workflow

1. Inspect the dataset, fields, missing values, and target label.
2. Identify input variables and the target outcome.
3. Prepare data for classification.
4. Fit and evaluate a Logistic Regression model.
5. Examine accuracy, attack recall, and AUC alongside class-specific errors.
6. Translate the findings into cautious, tiered investigation recommendations.

## Results Reported in the Project

The project summary reports:
- Accuracy: **74.1%**
- Attack recall: **73.9%**
- Area Under the ROC Curve (AUC): **0.814**

These figures should be verified against the final report and evaluation setup before being quoted in an interview. Metrics depend on the target definition, class balance, data split, and threshold.

## Why the Metrics Matter

- **Accuracy** is the proportion of all predictions that are correct.
- **Attack recall** is the proportion of actual attack sessions identified by the model.
- **AUC** summarizes how well the model ranks positive cases above negative cases across classification thresholds.

For an intrusion-detection use case, missed attacks and false alarms have different costs. Precision, confusion-matrix counts, threshold selection, and validation on unseen data are important complements to accuracy.

## Potential Operational Relevance

A model like this could be explored as a triage aid that prioritizes sessions for human review. It should not be presented as an autonomous security control without further testing, monitoring, and security review.

## Limitations

- A coursework evaluation does not prove effectiveness in a live network.
- Results may be affected by class imbalance, data leakage, or differences between the dataset and real traffic.
- Thresholds should reflect the relative costs of missed attacks and false positives.
- Performance should be checked on a separate, representative dataset before operational use.

## Project Status

**Academic capstone / prototype.** No live production deployment or operational security impact is claimed.

## Learning Outcomes

Classification workflow, model evaluation, interpreting recall and AUC, and translating analytical findings into risk-management questions.

## Author

Rahul | [GitHub Profile](https://github.com/imrahul11299-netizen)

