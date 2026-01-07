# Fraud_Detection_Project

# Project Overview:-
This project focuses on building a machine learning–based fraud detection system to identify fraudulent financial transactions. The objective is to proactively detect fraud while minimizing false alarms, keeping in mind real-world business constraints.
The dataset contains over 6.3 million transactions, making this a large-scale, highly imbalanced classification problem, which closely resembles real financial systems.
 
# Business Problem
Fraudulent transactions cause significant financial losses and reputational damage.
The key challenge is:
Fraud cases are extremely rare
Missing a fraud (False Negative) is far more costly than flagging a genuine transaction
Hence, the model must focus on high recall for fraud cases, not just accuracy.

# Dataset Description
Rows: 6,362,620
Columns: 10 (after preprocessing)
Target Variable: isFraud
0 → Legitimate transaction
1 → Fraudulent transaction
Fraud transactions were observed mainly in:
TRANSFER
CASH_OUT

# Data Preprocessing & Feature Engineering
The following steps were performed:
Checked for missing values and data consistency
Handled class imbalance using class weights
Removed non-informative features
Created domain-driven features such as:
amount_to_balance_ratio
origBalanceDiff
destBalanceDiff
isHighRiskType
These features helped capture abnormal transaction behavior.

# Model Development
Multiple models were evaluated, with a focus on interpretability and performance on imbalanced data.
Final Model:
Random Forest Classifier
class_weight = 'balanced'
Robust to non-linear relationships
Performs well on large datasets

# Model Evaluation
Evaluation was done using metrics suitable for imbalanced classification:
Confusion Matrix
Precision, Recall, F1-Score
ROC-AUC Score
Key Results:
ROC-AUC: ~0.99
High recall for fraud class
Model effectively identifies fraudulent transactions while maintaining stability
 
# Feature Importance Analysis
Top contributing features:
amount_to_balance_ratio
origBalanceDiff
newbalanceOrig
isHighRiskType
oldbalanceOrg
These features align well with real-world fraud patterns, such as sudden balance depletion and high-risk transaction types.

# Threshold Tuning
Instead of relying on the default probability threshold (0.5), threshold tuning was analyzed to:
Improve fraud recall

# Business Recommendations
Based on model insights:
Monitor high-risk transaction types (TRANSFER, CASH_OUT)
Flag transactions with unusually high amount-to-balance ratios
Introduce real-time transaction limits for risky behavior
Combine ML predictions with rule-based systems for better control

# Conclusion
This project demonstrates an end-to-end fraud detection pipeline, from data analysis and feature engineering to model evaluation and business interpretation.
It emphasizes practical decision-making, scalability, and alignment with real financial risk scenarios.
🛠️ Tools & Technologies
Python
Pandas, NumPy
Scikit-learn
Matplotlib
Jupyter Notebook

# Future Improvements
Advanced threshold optimization
Cost-sensitive learning
Model deployment using APIs
Real-time fraud monitoring system
Reduce the cost of missed fraud cases
Align predictions with business risk tolerance
This demonstrates a business-oriented approach rather than purely technical optimization.
