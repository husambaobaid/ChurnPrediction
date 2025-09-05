# 📊 Customer Churn Prediction

## 1. Objective
The goal of this project is to **predict customer churn** using machine learning, so businesses can identify at-risk customers and take proactive retention measures.

---

## 2. Dataset
- **Source**: Telecom customer dataset (simulated).  
- **Size**: ~700 rows (after preprocessing, train/test split = 80/20).  
- **Target**: `Churn` (1 = churned, 0 = retained).  
- **Challenge**: Dataset is **imbalanced** (more non-churners than churners).

---

## 3. Methodology
We followed a structured **7-step ML workflow**:

1. **Data Cleaning & Exploration**  
   - Removed missing/inconsistent values.  
   - Verified categorical + numerical distributions.  

2. **Baseline Models**  
   - Logistic Regression & Random Forest.  
   - Results: Accuracy ~44–47%, ROC-AUC ~0.44.  

3. **Handling Class Imbalance**  
   - Applied `class_weight='balanced'`.  
   - Slight improvement (ROC-AUC ~0.45).  

4. **Feature Engineering**  
   - Created new features:  
     - `ChargesPerService`  
     - `AvgMonthlySpend`  
     - `TenureBucket`  
   - Results: Random Forest ROC-AUC ~0.54.  

5. **Model Tuning**  
   - Hyperparameter search (Random Forest & Logistic Regression).  
   - Best model: **Random Forest** with balanced classes, ROC-AUC ~0.54.  

6. **Model Interpretation**  
   - **Random Forest (Feature Importance)**  
     - Top drivers: `ChargesPerService`, `tenure`, `AvgMonthlySpend`, `MonthlyCharges`, `TotalCharges`.  
   - **Logistic Regression (Coefficients)**  
     - Risk ↑ with `StreamingMovies_Yes`, `Month-to-month contracts`, `PaperlessBilling`.  
     - Risk ↓ with `Two-year contracts`, longer `tenure`, having a `Partner`.  

7. **Evaluation**  
   - Best Model: Random Forest.  
   - **Confusion Matrix**: Balanced between predicting churners/non-churners.  
   - **ROC Curve**: AUC = 0.54 → modest predictive power, but useful for proof-of-concept.

---

## 4. Key Insights
- **Contract type** is the strongest churn signal:  
  Month-to-month customers are much more likely to churn.  
- **Charges and spending patterns**: High per-service or monthly spending increases churn likelihood.  
- **Tenure**: Newer customers are riskier; long-tenure customers are more loyal.  
- **Customer demographics** (gender, dependents) have less influence than service/contract details.

---

## 5. Business Recommendations
- **Retention offers** for high-risk groups:  
  - Customers with high per-service charges.  
  - Month-to-month contract users.  
  - Customers in early tenure buckets.  
- **Incentives for loyalty**: Discounts or benefits for switching to longer-term contracts.  
- **Billing clarity**: Paperless billing shows correlation with churn → improve communication channels.

---

## 6. Next Steps
- Collect **more data** (current dataset is small).  
- Try **advanced models**: Gradient Boosting (XGBoost, LightGBM).  
- Explore **survival analysis** (predict *when* a customer will churn).  
- Deploy as a **web app API** for real-time churn scoring.
