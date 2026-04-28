# Credit Risk Prediction Model
**Project-Based Internship – ID/X Partners x Rakamin Academy**

## 📌 Project Overview
This project focuses on building an **end-to-end Credit Risk Prediction Model** using machine learning to identify **bad loans (high-risk borrowers)** and support better credit decision-making.

The main objective is to **reduce Non-Performing Loan (NPL) risk**, which in the dataset exceeds regulatory thresholds, by leveraging predictive analytics and explainable models.

---

## 🎯 Business Problem
- Current **Bad Loan rate: ~11.9%**, more than **2×** the regulatory limit (5%).
- High bad loan levels threaten:
  - Liquidity
  - Profitability
  - Capital adequacy
  - Regulatory compliance
- Traditional rule-based underwriting is insufficient to detect complex risk patterns.

---

## ✅ Project Goal
Develop a **machine learning-based credit risk model** that:
- Accurately predicts **bad loans before approval**
- Prioritizes **risk mitigation over raw accuracy**
- Produces **explainable, audit-ready outputs**
- Supports **business and regulatory decision-making**

---

## 🗂 Dataset
- **Source:** Lending Club Loan Data (2007–2014)
- **Records:** 466,285 loans
- **Features:** 75 raw features (reduced to 35 after selection)
- **Target Variable:**  
  - `loan_label`  
    - 0 = Bad Loan  
    - 1 = Good Loan
- **Class Imbalance:** ~12% bad loans

---

## 🔍 Methodology (End-to-End Pipeline)

### 1. Data Understanding
- Identified class imbalance and high missing-value features
- Defined bad loan categories (Charged Off, Late, Default, etc.)

### 2. Exploratory Data Analysis (EDA)
Key risk drivers identified:
- Interest Rate
- Debt-to-Income Ratio (DTI)
- Annual Income
- Credit Grade & Sub-grade
- Credit Utilization and Inquiries

### 3. Feature Engineering
Added behavioral risk indicators:
- `has_history_delinq`
- `has_public_record`
- `is_currently_delinq`

### 4. Data Preparation
- Feature selection (dropped >30% missing, post-loan, identity features)
- Missing value handling (median & mode)
- Outlier handling using IQR (stamping, not removal)
- Label encoding for categorical variables
- Train-test split (80/20, stratified)
- Feature scaling (StandardScaler)

---

## 🤖 Modeling Approach

### Models Tested
- Logistic Regression (Baseline)
- Decision Tree
- Random Forest
- Gradient Boosting
- **XGBoost (Final Model)**

### Evaluation Metrics
- Recall (Bad Loan)
- F2-Score (Recall-focused)
- Precision
- ROC-AUC
- Confusion Matrix (Business impact lens)

---

## 🏆 Final Model: XGBoost

### Why XGBoost?
- Credit risk is a **cost-sensitive problem**
- Missing a bad loan (False Negative) is far more costly than rejecting a good one
- XGBoost provides the **best trade-off between risk protection and business growth**

### Key Performance Highlights
- **Bad Loan Recall:** ~67%  
- **>66% of total credit risk successfully retained**
- Strong ROC-AUC (~0.70)
- Stable performance across train and test data

---

## 📊 Business Impact Simulation

### Assumptions
- Average loan value: **IDR 100 million**
- False Negative cost: **100% loss**
- False Positive cost: **10% opportunity loss**

### Results (XGBoost)
- ✅ **Risk Prevented:** IDR **738.1 billion**
- ❌ **Residual Loss:** IDR **368.5 billion**
- ⚠️ **Opportunity Loss:** IDR **312.6 billion**

➡️ **Risk prevented significantly outweighs opportunity loss**

---

## 🔎 Model Explainability
- SHAP analysis confirms:
  - Interest rate is the strongest risk signal
  - Affordability and recent credit behavior dominate predictions
- The model is:
  - Transparent
  - Interpretable
  - Regulation-ready (IFRS & OJK aligned)

---

## ✅ Final Recommendations
- Deploy **XGBoost** as the core decision-support model
- Use **recall-focused thresholding**
- Apply **human-in-the-loop review** for borderline cases
- Continuously monitor performance and recalibrate thresholds

---

## 🛠 Tech Stack
- Python
- Pandas, NumPy
- Scikit-learn
- XGBoost
- SHAP
- Matplotlib, Seaborn
- Google Colab

---

## 👤 Author
**Kuntur Jalassuad**  
Junior Data Scientist | Data Analyst Associate  
📍 Jakarta, Indonesia  

- LinkedIn: https://www.linkedin.com/in/kuntur-jalassuad/
- Email: jalassuad.k@gmail.com

---

## 📎 References
- Lending Club Public Dataset
- ID/X Partners – Project-Based Internship
``
