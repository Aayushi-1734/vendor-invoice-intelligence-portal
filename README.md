# Vendor Invoice Intelligence System

### Freight Cost Prediction & Invoice Risk Flagging

---

## 📌 Table of Contents

* [Project Overview](#project-overview)
* [Business Objectives](#business-objectives)
* [Data Sources](#data-sources)
* [Exploratory Data Analysis](#exploratory-data-analysis)
* [Models Used](#models-used)
* [Evaluation Metrics](#evaluation-metrics)
* [End-to-End Application](#end-to-end-application)
* [Project Structure](#project-structure)
* [How to Run This Project](#how-to-run-this-project)
* [Author & Contact](#author--contact)

---

# 📌 Project Overview

This project implements an **end-to-end Machine Learning system** designed to support finance and procurement teams by:

1. Predicting expected freight cost for vendor invoices.
2. Flagging high-risk invoices that require manual approval.
3. Reducing financial leakage caused by abnormal invoice patterns.
4. Improving operational efficiency through automated decision support.

---

# 🎯 Business Objectives

## 1. Freight Cost Prediction (Regression)

### Objective

Predict the expected freight cost for a vendor invoice using quantity, invoice value, and shipment-related information.

### Why It Matters

* Freight is a significant component of procurement cost.
* Poor freight estimation affects budgeting and forecasting.
* Accurate predictions support procurement planning and negotiation.

---

## 2. Invoice Risk Flagging (Classification)

### Objective

Predict whether a vendor invoice should be flagged for manual approval due to abnormal cost, freight, or quantity patterns.

### Why It Matters

* Manual invoice review does not scale efficiently.
* Financial leakage often occurs in high-value transactions.
* Early detection improves auditing and compliance.

---

# 📂 Data Sources

The project uses a relational SQLite database containing procurement and inventory information.

### Main Tables

* vendor_invoice – Invoice-level transaction data
* purchases – Purchase item details
* purchase_prices – Reference purchase prices
* begin_inventory – Inventory snapshots
* end_inventory – Closing inventory information

SQL aggregation is used to generate invoice-level machine learning features.

---

# 📊 Exploratory Data Analysis

The EDA phase focuses on answering business-driven questions:

* Do flagged invoices have higher financial exposure?
* Does freight increase with invoice quantity?
* Which variables influence freight costs most?
* Are there abnormal purchasing patterns?

Analysis includes:

* Distribution Analysis
* Correlation Analysis
* Outlier Detection
* Feature Relationship Visualization
* Business Rule Validation

---

# 🤖 Models Used

## Freight Cost Prediction

Regression Models Evaluated:

* Linear Regression
* Decision Tree Regressor
* Random Forest Regressor

### Best Performing Model

**Linear Regression**

Performance:

* MAE = 24.11
* RMSE = 124.72
* R² Score = 96.99%

---

## Invoice Risk Flagging

Classification Models Evaluated:

* Logistic Regression
* Decision Tree Classifier
* Random Forest Classifier

### Final Model

**Random Forest Classifier**

Performance:

* Accuracy = 88.99%
* Precision = 90%
* Recall = 89%
* F1 Score = 89%

Hyperparameter tuning was performed using GridSearchCV.

---

# 📈 Evaluation Metrics

## Freight Prediction

* Mean Absolute Error (MAE)
* Root Mean Squared Error (RMSE)
* R² Score

## Invoice Flagging

* Accuracy
* Precision
* Recall
* F1 Score
* Classification Report

---

# 🖥️ End-to-End Application

A Streamlit application demonstrates the complete machine learning workflow.

### Features

#### 🚚 Freight Cost Prediction

* Enter quantity and invoice value
* Predict expected freight cost
* Display prediction results instantly

#### 🚨 Invoice Risk Flagging

* Enter invoice details
* Predict whether an invoice requires manual approval
* Provide real-time risk assessment

#### 📊 Analytics Dashboard

* Business-friendly interface
* Interactive visualizations
* Model-driven insights

---

# 📁 Project Structure

```text
Vendor_Invoice_Intelligence_System/

│
├── app.py
│
├── models/
│   ├── predict_freight_model.pkl
│   ├── predict_flag_invoice.pkl
│   └── scaler.pkl
│
├── inference/
│   ├── predict_freight.py
│   └── predict_invoice_flag.py
│
├── train.py
├── data_preprocessing.py
├── modeling_evaluation.py
├── requirements.txt
└── README.md
```

---

# 🚀 How to Run This Project

## 1. Clone Repository

```bash
git clone https://github.com/yourusername/vendor-invoice-intelligence-system.git
```

## 2. Install Dependencies

```bash
pip install -r requirements.txt
```

## 3. Train Models

```bash
python train.py
```

## 4. Launch Application

```bash
streamlit run app.py
```

or

```bash
python -m streamlit run app.py
```

---

# 👩‍💻 Author & Contact

## Aayushi Singh

Mechanical Engineering Student | Machine Learning Enthusiast | Data Analytics

### 📧 Contact Information

* Email: [aayushisingh1734@gmail.com](mailto:aayushisingh1734@gmail.com)

### 🛠 Technologies Used

* Python
* Pandas
* NumPy
* Scikit-Learn
* Streamlit
* Plotly
* SQLite
* Joblib

### 📌 Project Focus Areas

* Freight Cost Prediction
* Invoice Risk Flagging
* Predictive Analytics
* Finance Intelligence Systems
* End-to-End Machine Learning Applications

---

⭐ If you found this project useful, consider giving it a star on GitHub.
