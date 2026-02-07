# 💳 Galactic Bank: Credit Default Prediction Analysis

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg) ![Machine Learning](https://img.shields.io/badge/ML-Random%20Forest-green.svg) ![Status](https://img.shields.io/badge/Project-Completed-brightgreen.svg)

## 📌 Project Overview
Historically, **Galactic Bank** has faced profitability challenges due to high credit default rates and a reactive approach to collections. This project utilizes machine learning to transition from reactive recovery to **proactive risk management**. 

By analyzing customer demographics and 6 months of historical transaction data, we developed a predictive model to identify high-risk individuals **one month before they default.**

---

## 📊 Dataset & Background
The analysis is based on the "Default of Credit Card Clients" dataset.
* **Size:** 30,000 observations.
* **Features:** Gender, Education, Marital Status, Age, Credit Limit, and 6-month history of billing and payments (April–Sept 2005).
* **Target Variable:** `default.payment.next.month` (Binary: 1 = Default, 0 = No Default).
* **Base Default Rate:** 22.12%.



---

## 🛠️ Methodology

### 1. Data Processing
* **Cleaning:** Rectified categorical inconsistencies in `EDUCATION` and `MARRIAGE` features.
* **Feature Engineering:** Created high-impact behavioral variables to capture risk:
    * `MAX_DELAY_STATUS`: The worst payment status recorded across the 6-month history.
    * `PAY_BILL_RATIO`: Relationship between monthly payments and bill amounts.
    * `EXCEED_LIMIT_NUM`: Frequency of a customer exceeding their assigned credit limit.

### 2. Model Selection
We implemented a **Random Forest Classifier**. This ensemble method was chosen for its ability to handle non-linear relationships and provide clear feature importance rankings.

### 3. Key Performance Metrics
| Metric | Value |
| :--- | :--- |
| **Accuracy** | 78.3% |
| **Recall (Defaulters)** | 57.0% |
| **Precision** | 51.6% |
| **F1-Score** | 0.54 |



---

## 💡 Key Takeaways & Analysis
* **Behavior > Demographics:** Recent payment history and "Max Delay Status" are significantly stronger predictors of default than age, gender, or education.
* **The "At-Risk" Profile:** Customers with a high `EXCEED_LIMIT_NUM` and a decreasing `PAY_BILL_RATIO` show the highest correlation with future defaults.
* **Predictive Power:** The model successfully flagged 761 out of 1,327 actual defaulters in the test set, allowing the bank to intervene early.

---

## 🚀 Strategic Recommendations

### 🔴 Risk Mitigation (Watch List)
Generate a monthly "High-Risk Watch List" for customers flagged by the model. 
* **Intervention:** Automated "friendly" payment reminders.
* **Financial Health:** Proactive outreach to offer flexible restructuring plans *before* the default occurs.

### 🟢 Strategic Growth (Prime Expansion)
Identify "Prime Customers" who maintain low credit utilization and consistent on-time payments.
* **Incentives:** Offer pre-approved limit increases and premium upgrades.
* **Marketing:** Target these users for higher-tier financial products to increase the bank's "Wallet Share."

---

## 💻 Technologies Used
* **Language:** Python
* **Libraries:** Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn
* **Environment:** Kaggle / Jupyter Notebook

---

## 📂 File Structure
```text
├── data/                   # Dataset source files
├── notebooks/              # Exploratory Data Analysis & Modeling
├── presentation/           # The pitch deck for key insights
└── README.md               # Project documentation
