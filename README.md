# 🦠 COVID-19 USA New Cases Prediction using Machine Learning

This project predicts **daily new COVID-19 cases in the USA** using historical pandemic data, vaccination statistics, and testing numbers.  
It demonstrates how **feature engineering (lag variables)** can significantly improve model performance over a baseline.

---

## 📂 Dataset
**Source:** Our World in Data – COVID-19 Dataset  
**Country:** USA 🇺🇸  
**Period:** Jan 2020 – Latest available date in dataset  

**Features Used:**
- `new_cases` (daily)
- `new_vaccinations`
- `new_tests`
- Lag features (`new_cases_lag1`, `new_cases_lag7`)

---

## 📜 Project Workflow

### **1️⃣ Step 1 – Load and Inspect Data**
- Imported dataset using **pandas**
- Checked data types, missing values, and date ranges
- Filtered data for **United States** only

---

### **2️⃣ Step 2 – Exploratory Data Analysis (EDA)**
- Plotted daily new COVID-19 cases trend
- Heatmap of feature correlations
- Missing value visualization

---

### **3️⃣ Step 3 – Data Preprocessing**
- Filled missing values with **forward-fill/back-fill** strategies
- Created lag features:
  - `new_cases_lag1`
  - `new_cases_lag7`
- Standardized features using **StandardScaler**

---

### **4️⃣ Step 4 – Baseline Model (Random Forest)**
- Trained a **Random Forest Regressor** using original features only

**Performance:**
- RMSE: `52121.43`
- R² Score: `-0.1633` (poor fit, baseline only)

---

### **5️⃣ Step 5 – Improved Model with Lag Features**
- Added `new_cases_lag1` and `new_cases_lag7`
- Retrained Random Forest

**Performance:**
- RMSE: `32096.95` ✅
- R² Score: `0.5619` (much better fit)

---

### **6️⃣ Step 6 – Model Comparison**

| Model                | RMSE       | R² Score |
|----------------------|-----------|----------|
| Baseline RF          | 52121.43  | -0.1633  |
| Improved RF (Lag)    | 32096.95  | 0.5619   |

**Observation:** Lag features improved both accuracy and explained variance **significantly**.

---

## 📊 Key Insights
- Historical trends (**previous cases**) are the strongest predictors of new cases
- Vaccination and testing data also contribute but less than time-based patterns
- Lag-based Random Forest outperformed the baseline by a wide margin

---

## 📁 Repository Structure
📂 covid19-prediction-usa
│── covid_cases_prediction.ipynb # Jupyter Notebook with full analysis

│── owid-covid-data.csv # Dataset (USA filtered in code)

│── requirements.txt # Python libraries

│── README.md # Project overview


---

## 🚀 Future Work
- Test **XGBoost** and **Gradient Boosting** models
- Apply **time series forecasting methods** (ARIMA, Prophet, LSTM)
- Deploy as a **Streamlit web app** for real-time case prediction

---

## 👨‍💻 Author
Developed by **Azib Malick**  
📧 Email: azibmalick25@gmail.com  
© 2025 Azib Malick. All rights reserved.
