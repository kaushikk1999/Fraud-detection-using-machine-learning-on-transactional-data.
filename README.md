# Fraud-detection-using-machine-learning-on-transactional-data.
A machine learning project to detect fraudulent financial transactions using real-time simulation data. Includes data cleaning, VIF analysis, model building, and evaluation to identify key fraud indicators.

## 📊 Project Overview

This project focuses on detecting fraudulent financial transactions using machine learning. The dataset simulates 30 days of transactions and includes over **6.3 million records** with 10 features. The goal is to build a model that can proactively detect fraudulent activity and help financial institutions take timely preventive measures.

---

## 🧠 Business Context

Fraudulent financial transactions can cause massive financial losses and compromise trust. The aim of this project is to:
- Develop a predictive model for fraud detection.
- Analyze key indicators of fraud.
- Suggest actionable insights to improve infrastructure security.
- Evaluate the effectiveness of prevention mechanisms.

---

## 📁 Dataset Information

The dataset consists of **6362620 rows and 10 columns**, simulating 30 days (744 steps) of transaction data. Each row represents a single transaction.

### 📌 Features:
- `step`: Represents hours passed (1 step = 1 hour).
- `type`: Type of transaction (`CASH-IN`, `CASH-OUT`, `DEBIT`, `PAYMENT`, `TRANSFER`).
- `amount`: Amount involved in the transaction.
- `nameOrig`: Originating customer.
- `oldbalanceOrg`: Balance before the transaction (origin).
- `newbalanceOrig`: Balance after the transaction (origin).
- `nameDest`: Destination customer.
- `oldbalanceDest`: Balance before the transaction (destination).
- `newbalanceDest`: Balance after the transaction (destination).
- `isFraud`: Target column. 1 = Fraudulent transaction, 0 = Legitimate transaction.
- `isFlaggedFraud`: Flag for illegal transfer attempts over 200,000.

---

## 🔍 Steps Performed

### 1. 📦 Data Cleaning
- Handled missing values.
- Calculated new features like `errorBalanceOrig` and `errorBalanceDest`.
- Converted time-based features (`step`) to `hour` and `day`.

### 2. 🚫 Outlier Analysis
- Outliers were not removed, as large transactions can be legitimate or fraudulent.

### 3. 🔁 Multicollinearity Check
- Variance Inflation Factor (VIF) was used.
- Highly collinear variables were dropped to avoid redundancy.

### 4. 📈 Feature Selection
Final features used:
- `type` (encoded)
- `amount`
- `oldbalanceOrg`
- `oldbalanceDest`
- `errorBalanceDest`
- `hour`

### 5. ✂️ Train-Test Split
Performed an 80/20 train-test split with stratification on `isFraud`.

---

## 🤖 Model Building

Models to be explored:
- Logistic Regression
- Random Forest
- XGBoost
- LightGBM
- Neural Networks (optional for deep learning extension)

Performance metrics:
- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC Score

---

## 📊 Insights & Interpretation

- Key fraud indicators were identified based on feature importance.
- Certain transaction types and time windows had a higher chance of fraud.
- Recommendations were made for monitoring and prevention.

---

## 🔐 Prevention Strategy

Suggested improvements for infrastructure:
- Real-time flagging of suspicious transaction patterns.
- Alert system for large amount transfers outside business hours.
- Enhanced identity verification during `TRANSFER` and `CASH-OUT`.

---

## 📉 Evaluation of Implementation

- Model accuracy will be tested on unseen validation data.
- Compare fraud rate before and after applying model-based prevention.
- A/B testing can be used in a live environment.

---

## 🧰 Tools & Libraries

- Python
- Pandas, NumPy
- Scikit-learn
- Matplotlib, Seaborn
- XGBoost, LightGBM
- Jupyter Notebook

---

## 📌 How to Run the Project

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/fraud-detection-ml.git
   cd fraud-detection-ml
