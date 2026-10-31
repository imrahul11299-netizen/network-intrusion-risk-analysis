# Network Intrusion Risk Analysis

Capstone Project | Masai School × IIM Sirmaur

## Problem
Traditional intrusion detection relies on manual monitoring and static rules, which are slow to catch evolving threats. This project asks: can session-level network data (login behavior, IP reputation, encryption) reliably predict whether a session is an attack?

## Data
- **Source:** Kaggle, Cybersecurity Intrusion Detection Dataset
- **Size:** 9,537 network sessions, 11 columns (1 identifier, 9 predictors, 1 target)
- **Target:** `attack_detected` (1 = attack, 0 = normal); attacks make up 44.7% of sessions
- **Note:** Missing values in `encryption_used` (20.6%) were treated as "no encryption"

## Tools
- PSPP (Logistic Regression on the full dataset, 5 predictors)
- Orange Data Mining (Logistic Regression with Ridge L2, class balancing, stratified 80/20 train-test split, 9 predictors)

## Results

| Metric | PSPP | Orange |
|---|---|---|
| Accuracy | 72.9% | 74.1% |
| Attack recall | 65.6% | 73.9% |
| Attack precision | 71.5% | 69.9% |
| AUC | - | 0.814 |

Orange results are on a held-out test set of 1,907 sessions. PSPP was evaluated on the same data it was trained on, so its accuracy may be optimistic.

## Key Findings
- **IP reputation score** was the strongest predictor of attacks (odds ratio 22.95).
- **Failed logins** (odds ratio 2.56) and **login attempts** (odds ratio 1.48) were also strong predictors.
- **Network packet size** had no significant effect (p = 0.810).
- Both tools agreed on the main drivers, which adds credibility to the findings.

## Business Recommendations
1. Prioritize IP reputation checks as the primary risk signal.
2. Set automated alerts and lockouts or step-up authentication on failed login thresholds.
3. Deprioritize low-value features such as packet size.
4. Use the Orange model for operational use, since it catches more real attacks.
5. Use a tiered response: block high-risk, review medium-risk, allow low-risk sessions.

## Limitations
- The Orange model still misses about 26% of real attacks, so it should not be the only security layer.
- The PSPP model has no train-test split and uses only 5 of 9 predictors.
- Explanatory power is moderate (Nagelkerke R² = 0.34, MCC = 0.48).

## Full Report
[Read the full report (PDF)](network-intrusion-risk-analysis.pdf)
