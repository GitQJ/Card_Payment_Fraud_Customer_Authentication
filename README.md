# Card_Payment_Fraud_Customer_Authentication
Does strong customer authentication (SCA) actually catch card fraud? Using 3 years of Central Bank of Ireland open data, I found SCA status ranked near the bottom of fraud predictors, while payer PSP role and initiation channel ranked highest.

# CONTEXT
Irish fraudulent payments hit €160M in 2024 (+40.7% YoY), and 63% of fraudulent electronic payments had passed SCA. I set out to find which variables really drive fraud detection.

# MY ROLE
Academic project: data prep, dashboard, modelling and interpretation.

# WHAT I DID
• Merged 3 yearly card-payment datasets (2022-2024, ~113K records after removing confidential and duplicate-currency rows)
• Built a Tableau dashboard of fraud rates by authentication type, exemption category, region and quarterly trend
• Engineered binary targets, one-hot encoded categoricals, and used a stratified 80/20 split for class imbalance
• Compared logistic regression, decision tree, random forest and gradient boosting, tuned with 5-fold CV
• Explained models with SHAP (summary, beeswarm, dependence, waterfall)

# RESULTS
• Gradient boosting performed best: ROC-AUC 0.979, PR-AUC 0.981
• SCA transactions were ~4.11x safer by fraud rate, yet SCA fraud trended up while non-SCA fraud fell, consistent with a shift to social engineering
• Recommendation: layer transactional context and post-authentication behavioural monitoring on top of SCA

# TECH STACK
Python, pandas, scikit-learn, SHAP, Tableau
