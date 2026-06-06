# 🏥 NHS Hospital Bed Occupancy Prediction System

A machine learning project that predicts **General & Acute (G&A) hospital bed occupancy** 
across NHS Trusts in England using historical data from 2020 to 2023.

---

## 📊 Project Overview

This project analyses NHS UEC (Urgent and Emergency Care) sitrep data to predict 
how many hospital beds will be occupied. It uses three powerful machine learning 
models and compares their performance.

---

## 🗂️ Dataset

- **Source:** NHS UEC Sitrep Data (2020–2023)
- **Files:** 40+ monthly Excel files
- **Records:** 4,882 rows across 7 NHS Regions
- **Features Used:**
  - Region
  - Trust Name
  - G&A Beds Available
  - G&A Beds Occupied (Target)
  - Date

### NHS Regions Covered:
- North East and Yorkshire
- Midlands
- North West
- London
- South East
- South West
- East of England

---

## 🤖 Models Used

### 1️⃣ Random Forest Regressor
| Metric | Score |
|--------|-------|
| RMSE | 45.42 |
| MAE | 26.50 |
| MAPE | 44.86% |

After Hyperparameter Tuning:
| Metric | Score |
|--------|-------|
| RMSE | 35.91 |
| MAE | 25.24 |

Best Parameters:
- n_estimators: 200
- max_depth: 10
- min_samples_split: 10
- min_samples_leaf: 2

---

### 2️⃣ XGBoost Regressor
| Metric | Score |
|--------|-------|
| RMSE | 39.26 |
| MAE | 25.04 |
| MAPE | 57.40% |

After Hyperparameter Tuning:
- learning_rate: 0.3
- max_depth: 3
- n_estimators: 200

---

### 3️⃣ LSTM (Long Short-Term Memory Neural Network)
| Metric | Score |
|--------|-------|
| Train RMSE | 44.91 |
| Test RMSE | 47.75 |
| Train MAPE | 73.61% |
| Test MAPE | 88.10% |

Architecture:
- LSTM Layer: 150 units
- Dense Output Layer
- Optimizer: Adam
- Epochs: 30

---

## 📈 Visualisations

The project includes the following charts:

- 📊 Histogram of bed availability and occupancy
- 📦 Box plots to detect outliers
- 🔗 Correlation heatmap
- 🌍 Region vs bed count bar charts
- 📉 Actual vs Predicted comparison plots
- 🎻 Violin plots by region
- 📌 Scatter plots

---

## 🛠️ Technologies Used

| Tool | Purpose |
|------|---------|
| Python | Main programming language |
| Pandas | Data manipulation |
| NumPy | Numerical computing |
| Scikit-learn | Random Forest and GridSearchCV |
| XGBoost | Gradient boosting model |
| TensorFlow/Keras | LSTM neural network |
| Matplotlib | Data visualisation |
| Seaborn | Statistical plots |
| Google Colab | Development environment |
| Google Drive | Data storage |

---

## 🚀 How To Run

### Step 1 — Open Google Colab
Go to colab.research.google.com

### Step 2 — Mount Google Drive
```python
from google.colab import drive
drive.mount('/content/drive/')
```

### Step 3 — Upload NHS Sitrep Excel files to Google Drive
Place all monthly Excel files in:

### Step 4 — Install required libraries
```python
pip install xgboost tensorflow scikit-learn pandas numpy seaborn matplotlib
```

### Step 5 — Run the notebook cells in order:
1. Import libraries
2. Load and combine data
3. EDA and visualisations
4. Train Random Forest model
5. Train XGBoost model
6. Train LSTM model
7. Compare results

---

## 📋 Data Preprocessing Steps

1. Loaded 40+ monthly Excel files
2. Extracted year and month from filenames
3. Kept only relevant columns
4. Combined all files into one DataFrame
5. Filled missing Region values using forward fill
6. Converted bed numbers to integers
7. Applied one-hot encoding to Region and Trust Name

---

## 🏆 Model Comparison

| Model | RMSE | MAE |
|-------|------|-----|
| Random Forest (tuned) | 35.91 | 25.24 |
| XGBoost | 39.26 | 25.04 |
| LSTM | 47.75 | - |

✅ **Best Model: Random Forest after Hyperparameter Tuning**

---

## 💼 Skills Demonstrated

- Data wrangling with multiple Excel files
- Exploratory Data Analysis (EDA)
- Feature engineering and encoding
- Supervised machine learning
- Deep learning with LSTM
- Hyperparameter tuning with GridSearchCV
- Model evaluation and comparison
- Data visualisation

---

## 👨‍💻 Built By

Abdul — Data Science and AI enthusiast 🚀

---

## 📌 Note

This project was built for educational and research purposes using 
publicly available NHS England data.
