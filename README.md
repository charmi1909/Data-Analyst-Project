# Stock Analytics & Prediction Dashboard (Codveda Internship Project)

Internship project demonstrating **data cleaning**, **exploratory data analysis (EDA)**, **regression**, and **classification** on historical stock OHLCV data using an interactive **Streamlit dashboard**.

---

## Problem Statement

Work with a real-world **stock prices dataset** containing **missing values**, **duplicate rows**, and **inconsistent formats**.

The project includes:

1. Data cleaning and preprocessing  
2. Exploratory Data Analysis (EDA)  
3. Regression model to predict stock closing price  
4. Classification model to predict next-day stock movement  

---

## Dataset

| Item | Detail |
|------|--------|
| File | `dataset/2) Stock Prices Data Set.csv` |
| Columns | `symbol`, `date`, `open`, `high`, `low`, `close`, `volume` |
| Notes | Dataset contains multiple stock symbols across time |

---

## Tech Stack

- Python  
- Pandas, NumPy  
- Matplotlib, Seaborn  
- Scikit-learn  
- Streamlit  

---

## Steps Performed

### 1. Data Cleaning
- Converted date column to datetime format  
- Converted numeric columns (OHLCV)  
- Removed duplicate rows  
- Handled missing values  

### 2. Exploratory Data Analysis (EDA)
- Summary statistics using `describe()`  
- Histogram of closing prices  
- Scatter plot (Open vs Close)  
- Correlation heatmap  

### 3. Regression Model
- Linear Regression to predict closing price  
- Features: Open, High, Low, Volume  
- Evaluation metrics:  
  - R² Score  
  - Mean Squared Error (MSE)  

### 4. Classification Model
- Logistic Regression to predict next-day movement  
- Target:  
  Target = (close.shift(-1) > close)  
- Evaluation metrics:  
  - Accuracy  
  - Precision  
  - Recall  
  - F1 Score  

---

## Dashboard

An interactive dashboard was built using **Streamlit**.

Features:
- Data visualization (histograms, scatter plots, heatmaps)  
- Stock closing price prediction  
- Next-day movement prediction  
- User input for real-time predictions  

---

## How to Run

```bash
cd /path/to/project
python -m pip install -r requirements.txt
python -m streamlit run app.py
