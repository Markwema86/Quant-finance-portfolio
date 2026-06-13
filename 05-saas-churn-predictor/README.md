# 05 - SaaS Churn Predictor (PE Due Diligence Tool)
 
## Objective
Build a churn prediction and explainability tool to support private equity due diligence on SaaS acquisition targets — identifying which customers are at risk of churning, why, and how much revenue is exposed.
 
## Data
- **Source:** IBM Telco Customer Churn dataset (Kaggle/public)
- **Size:** 7,043 customers, 21 features
## Methodology
1. **EDA** - analysed churn by contract type, internet service, payment method, tenure, and charges
2. **Feature engineering** - added PE-relevant features: CLV proxy (monthly charge × tenure), revenue-per-tenure-month, services-adopted count, new-customer and loyal-customer flags
3. **Model:** XGBoost classifier with `scale_pos_weight` to address class imbalance (26.5% churn rate)
4. **Explainability:** SHAP (TreeExplainer) for global feature importance and individual-customer explanations
5. **Portfolio segmentation:** customers grouped into Critical/High/Medium/Low risk tiers with revenue-at-risk quantification
## Key Results
| Metric | Value |
|---|---|
| Overall churn rate | 26.5% |
| Model ROC-AUC | 0.841 |
| Recall (churned class) | 79% |
| Revenue in Critical+High risk tiers | 47.3% of MRR |
 
**Top churn drivers (SHAP):** Contract type (especially absence of long-term contracts), tenure, and Fiber optic internet service.
 
## Headline Finding
*"The target SaaS company exhibits a 26.5% churn rate, with 47.3% of monthly recurring revenue concentrated in Critical/High-risk segments - primarily driven by contract structure and customer tenure, indicating significant post-acquisition retention risk."*
 
## Key Learning
Recall was prioritised over overall accuracy: in a due diligence context, a **false negative (missed churner)** directly overstates the stability of the revenue base being acquired, which is more costly than a false positive (flagging a stable customer as at-risk). `scale_pos_weight` was used specifically to improve recall on the minority (churn) class.
 
## Tools
Python, XGBoost, SHAP, Scikit-learn, Pandas, Matplotlib
