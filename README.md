# 🛒 BigMart Sales Forecasting


**Project Name**: BigMart Sales Forecasting using Machine Learning  
**Intern**: Abraraw Ayal  
**University**: Bahir Dar University  
**Domain**: Transport and Logistics (Applied in Retail Forecasting Context)  
**GitHub**: [Abre1234](https://github.com/Abre1234)  
**LinkedIn**: [Abree1234](https://www.linkedin.com/in/Abree1234)

---

## 🧠 Objective

The goal is to predict future sales of products at BigMart outlets using historical data. Accurate sales prediction helps:

- Optimize stock inventory  
- Reduce losses from under/over-stocking  
- Plan revenue and logistics efficiently

---

## 📂 Dataset

- **Source**: Kaggle (Train.csv)
- **Target Variable**: `Item_Outlet_Sales`
- **Features**: 
  - Numerical: `Item_Weight`, `Item_Visibility`, `Item_MRP`
  - Categorical: `Item_Type`, `Outlet_Type`, `Outlet_Location_Type`, etc.

---

## ✅ Workflow Steps

### 1. 📥 Data Loading & Inspection
- Loaded dataset using `pandas`.
- Checked missing values and types using `.info()` and `.describe()`.

### 2. 🧹 Data Cleaning
- Converted `Date` column.
- Imputed missing `Item_Weight` with mean.
- Replaced zero `Item_Visibility` with mean.
- Filled missing `Outlet_Size` using group-wise mode.

### 3. 🔍 Exploratory Data Analysis (EDA)
- Distribution plots for all numerical variables.
- Boxplots for outlier detection.
- Count plots for categorical features.
- Correlation heatmap.
- Price vs Sales scatter analysis showed `Item_MRP` as a strong predictor.

### 4. 🧾 Feature Engineering
- Added `Outlet_Age` = 2025 - `Outlet_Establishment_Year`.
- Created `Item_Category` from `Item_Identifier`.
- Dropped weak features based on feature importance.

### 5. 🔐 Label Encoding
- Encoded all categorical features using `LabelEncoder`.
- Saved encoders using `joblib`.

### 6. 🤖 Model Building
- Model: `XGBRegressor`
- Training Score (R²): **0.61**
- Testing Score (R²): **0.62**
- RMSE ≈ **965**

### 7. 📊 Feature Importance
- Top Influencer: `Item_MRP`
- Moderate: `Outlet_Type`, `Outlet_Age`
- Less Useful: `Outlet_Location_Type`, `Item_Category`

### 8. 💻 GUI Deployment
- GUI created using `tkinter` for offline local sales prediction.
- Accepts user input and returns predicted sales using saved model.

---

## 📦 Requirements

```bash
pip install pandas numpy matplotlib seaborn xgboost scikit-learn joblib
