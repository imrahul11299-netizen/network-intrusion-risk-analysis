# Network Intrusion Risk Analysis

Capstone project | Masai School × IIM Sirmaur

## Problem
Can session-level network data (login behavior, IP reputation, encryption) predict whether a session is an attack?

## Data
9,537 network sessions, 9 predictors. Source: Kaggle - Cybersecurity Intrusion Detection Dataset.

## Tools
PSPP, Orange Data Mining (Logistic Regression)

## Key Findings
- IP reputation score (odds ratio 22.95), failed logins and login attempts were the strongest predictors of attacks.
- Orange model: 74.1% accuracy, 73.9% attack recall, 0.814 AUC on a held-out test set.
- Recommended a tiered response: block high-risk, review medium-risk, allow low-risk sessions.

## Report
See Capstone_Report.pdf
