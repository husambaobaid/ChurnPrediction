📊 Customer Churn Prediction
🎯 Objective

The goal of this project is to predict customer churn using machine learning, so businesses can identify at-risk customers and take proactive retention measures.

📂 Dataset

Source: Telecom customer dataset (simulated).

Size: ~700 rows (after preprocessing, train/test split = 80/20).

Target: Churn (1 = churned, 0 = retained).

Challenge: Dataset is imbalanced (more non-churners than churners).

🔎 Methodology

We followed a structured 7-step ML workflow:

Data Cleaning & Exploration

Handled missing values and data inconsistencies.

Verified categorical and numerical distributions.

Baseline Models

Logistic Regression & Random Forest.

Accuracy ~44–47%, ROC-AUC ~0.44 (weak baseline).

Class Imbalance Handling

Used class_weight='balanced'.

Slight improvement (ROC-AUC ~0.45).

Feature Engineering

New features:

ChargesPerService

AvgMonthlySpend

TenureBucket

Result: Random Forest ROC-AUC ~0.54.

Model Tuning

Hyperparameter search (Random Forest & Logistic Regression).

Best model: Random Forest, ROC-AUC ~0.54.

Model Interpretation

Random Forest (Feature Importance):

Top drivers: ChargesPerService, tenure, AvgMonthlySpend.

Logistic Regression (Coefficients):

Risk ↑ with Month-to-month contracts, PaperlessBilling.

Risk ↓ with Two-year contracts, longer tenure.

Evaluation

Best Model: Random Forest.

Confusion matrix: balanced predictions.

ROC-AUC: ~0.54 (proof-of-concept).

📌 Key Insights

Customers on month-to-month contracts are much more likely to churn.

High per-service charges and high monthly charges increase churn risk.

Tenure strongly reduces churn — long-term customers are loyal.

Demographics (like gender) have less influence compared to contract and service features.

💡 Business Recommendations

Targeted retention offers for high-risk groups (month-to-month, high spend, low tenure).

Provide loyalty incentives for switching to longer contracts.

Improve billing communication, especially for paperless billing users.

🚀 Next Steps

Collect more data to strengthen predictions.

Test advanced models like XGBoost, LightGBM, CatBoost.

Explore survival analysis (predict when churn happens).

Deploy as a web app API for real-time scoring.

📌 This project demonstrates a full ML workflow: from data preprocessing and feature engineering to model selection, interpretation, and business recommendations.
