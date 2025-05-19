# Fraud Detection Using Machine Learning

## Objective  
To build a predictive model that accurately detects fraudulent transactions based on user behavior and financial transaction data. The focus is on real-world applicability for reducing financial risk through automated fraud detection systems.

---

## Dataset Overview  
Sourced from [Kaggle](https://www.kaggle.com/datasets/amanalisiddiqui/fraud-detection-dataset), the dataset includes both legitimate and fraudulent transactions.

- Features represent transaction metadata and user activity.
- Transaction types include `TRANSFER`, `CASH_OUT`, `PAYMENT`, etc.
- Key columns include transaction amount, balances before/after, and the `isFraud` label.
- No AI-generated features are present, ensuring no data leakage.

---

## Model Performance Summary  

**Model:** Accuracy, Precision, Recall, F1 Score, ROC AUC  

- **Random Forest Classifier:**  
  - Accuracy: ~99%  
  - Precision: High (depending on class balancing)
  - Recall: Tuned for sensitivity to fraud
  - ROC AUC: High discriminative ability

The Random Forest model performs robustly across all key metrics. It captures complex transaction patterns and handles high-dimensional data effectively.

---

## Top Predictive Features  

Identified through feature importance from the Random Forest model:

- **Transaction Type** — Fraud is highly concentrated in certain types like `TRANSFER` and `CASH_OUT`.
- **Amount** — Larger transactions tend to be more suspicious.
- **Old/New Balance Origin/Destination** — Sharp or unusual balance changes often indicate fraud.
- **Step (Time)** — Temporal trends help identify fraudulent behavior.

---

## Key Insights  

- Fraudulent transactions exhibit consistent patterns, particularly in transaction types and account balance shifts.
- Class imbalance is a major challenge—fraudulent transactions are rare (~0.1%).
- Model performance was validated: randomizing labels resulted in R² near zero, confirming genuine predictive signal.
- Tree-based models are ideal due to their ability to model non-linear relationships and feature interactions.

---

## Recommendations  

- Apply advanced resampling techniques like **SMOTE** or **undersampling** to handle class imbalance more effectively.
- Use **SHAP** for explainability to highlight what features drove each fraud prediction.
- Explore ensemble and deep learning models (e.g., XGBoost, LSTM) for even higher performance.
- Simulate real-time fraud detection by deploying the model into a live environment.
- Consider integrating additional behavioral signals (e.g., user history, device metadata).

---

## Conclusion  

This project showcases the viability of machine learning in fraud detection. With its high accuracy and strong feature interpretability, the model provides a solid foundation for deployment in real-world financial systems. Future enhancements can further improve performance and ensure robust fraud prevention at scale.
