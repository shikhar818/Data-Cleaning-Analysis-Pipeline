# 🧹 Data Cleaning & Analysis Pipeline

A portfolio of end-to-end data analysis projects demonstrating real-world data cleaning, exploratory data analysis, and machine learning on two distinct datasets.

---

## 📁 Projects

### 1. 🛍️ Black Friday Sales — Cleaning, EDA & Purchase Prediction
**File:** `black_friday_portfolio.ipynb`

Retail transaction data from a Black Friday sales event with 550,000+ records. The goal is to clean raw demographic and product data, explore purchasing patterns, and build models to predict individual purchase amounts.

**Key Steps:**
- Dropped irrelevant identifiers (`User_ID`)
- Binary encoded `Gender`, ordinal encoded `Age` ranges
- One-hot encoded `City_Category` to avoid multicollinearity
- Stripped and cast `Stay_In_Current_City_Years` from string to integer
- Mode imputation for `Product_Category_2` and `Product_Category_3` missing values
- EDA across age, gender, occupation, and product categories
- Regression modelling: Linear Regression, Random Forest, XGBoost with full metric comparison

**Dataset:** [Black Friday Sales — Kaggle](https://www.kaggle.com/datasets/sdolezel/black-friday)

---

### 2. 🍽️ Zomato Restaurants — Cleaning & EDA
**File:** `zomato_eda_portfolio.ipynb`

Global restaurant data from Zomato covering 9,500+ restaurants across 15 countries. The goal is to clean and enrich the dataset, then uncover insights about ratings, delivery availability, and cuisine popularity.

**Key Steps:**
- Identified and dropped rows with null `Cuisines` values (<0.1% of data)
- Validated rating ranges, vote counts, and binary feature values
- Stripped whitespace from column names to prevent key errors
- Merged with a country code lookup table to enrich geographic data
- EDA on country/city distribution, rating patterns, delivery availability, and top cuisines by votes

**Dataset:** [Zomato Restaurants — Kaggle](https://www.kaggle.com/datasets/shrutimehta/zomato-restaurants-data)

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.11 | Core language |
| Pandas | Data manipulation & cleaning |
| NumPy | Numerical operations |
| Matplotlib / Seaborn | Visualisation |
| Scikit-learn | Machine learning models & evaluation |
| XGBoost | Gradient boosting regression |

---

## 🚀 Getting Started

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost openpyxl
```
Then open either notebook and run all cells top to bottom.

### Folder Structure
```
├── black_friday_portfolio.ipynb
├── zomato_eda_portfolio.ipynb
├── black_fri_dataset/
│   ├── train.csv
│   └── test.csv
├── zomato_dataset/
│   ├── zomato.csv
│   └── Country-Code.xlsx
└── README.md
```

> **Note:** Datasets are not included in this repository due to size. Download them from the Kaggle links above and place them in the folders shown.

---

## 📊 Key Findings

**Black Friday**
- Male customers consistently outspend female customers across all age groups and occupations
- The 26–35 age group records the highest average purchase amount
- XGBoost outperforms Linear Regression and Random Forest on RMSE and R²

**Zomato**
- India accounts for ~94% of restaurant listings — the platform's primary market
- A significant share of restaurants have no user ratings, indicating low engagement
- Online delivery is only available in India and the UAE
- North Indian cuisine leads all categories by total votes
