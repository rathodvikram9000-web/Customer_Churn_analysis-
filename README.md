# 📉 Customer Churn Analysis — Telco Dataset

> End-to-end customer churn analysis using Python (EDA + ML) and Power BI — identifying key drivers of churn and building a predictive model to support retention decisions.

---

## 📌 Project Overview

Customer churn is one of the most critical challenges in the telecom industry. This project analyzes a real-world Telco dataset of **7,043 customers** to:

- Uncover patterns and behavioral signals that lead to churn
- Visualize churn drivers through an interactive Power BI dashboard
- Build and evaluate a **Logistic Regression** model to predict churn

---

## 📂 Project Structure

```
Customer-Churn-Analysis/
│
├── Customer_Churn.ipynb                    # Python notebook: EDA + ML model
├── Customer_Churn_Analysis.pbix            # Power BI interactive dashboard
├── WA_Fn-UseC_-Telco-Customer-Churn.csv   # Source dataset (IBM Telco)
└── README.md
```

---

## 📊 Dataset

| Property | Details |
|---|---|
| **Source** | IBM Sample Dataset — Telco Customer Churn |
| **Records** | 7,043 customers |
| **Features** | 21 columns |
| **Target** | `Churn` (Yes / No) |

### Key Features

| Category | Columns |
|---|---|
| Demographics | `gender`, `SeniorCitizen`, `Partner`, `Dependents` |
| Services | `PhoneService`, `InternetService`, `StreamingTV`, `OnlineSecurity`, etc. |
| Account Info | `Contract`, `PaymentMethod`, `PaperlessBilling`, `tenure` |
| Charges | `MonthlyCharges`, `TotalCharges` |

---

## 🔍 Key Findings

### 📈 Churn Rate
- Overall churn rate: **26.54%** (1,869 out of 7,043 customers)

### 📋 Top Churn Drivers

| Factor | Insight |
|---|---|
| **Contract Type** | Month-to-month customers churn at **42.7%** vs only **2.8%** for two-year contracts |
| **Monthly Charges** | Churned customers have significantly higher average monthly charges |
| **Internet Service** | Fiber optic users show higher churn than DSL users |
| **Payment Method** | Electronic check users show the highest churn tendency |
| **Tenure** | Newer customers (low tenure) are far more likely to churn |

---

## 🧪 Python Notebook — Workflow

The notebook (`Customer_Churn.ipynb`) follows a complete analytics pipeline:

### 1. Data Loading & Understanding
- Loaded CSV with Pandas
- Explored shape, data types, and target distribution using `.info()`, `.describe()`, `.value_counts()`

### 2. Data Cleaning
- Converted `TotalCharges` from string to numeric
- Dropped rows with missing values (~11 rows)
- Encoded `Churn` column: `Yes → 1`, `No → 0`

### 3. Exploratory Data Analysis (EDA)
- **Churn distribution** — count plot to visualize class imbalance
- **Monthly Charges vs Churn** — box plot showing higher charges among churned customers
- **Contract Type vs Churn** — grouped count plot revealing month-to-month risk

### 4. Feature Engineering
- Applied `pd.get_dummies()` for one-hot encoding of all categorical features

### 5. Model Building
- Train/Test split: **80% / 20%**
- Feature scaling with `StandardScaler`
- Model: **Logistic Regression** (`solver='liblinear'`, `max_iter=2000`)

### 6. Model Evaluation

| Metric | Score |
|---|---|
| **Accuracy** | **78.39%** |
| Precision (Churn) | 65% |
| Recall (Churn) | 40% |
| F1-Score (Churn) | 0.50 |

---

## 📊 Power BI Dashboard

The `Customer_Churn_Analysis.pbix` file contains an interactive dashboard covering:

- Overall churn KPIs and churn rate
- Churn breakdown by contract type, payment method, and internet service
- Monthly charges distribution for churned vs retained customers
- Customer segmentation by tenure and demographics

> **To view:** Open the `.pbix` file in [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free download).

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| **Python 3** | Data analysis and ML |
| **Pandas & NumPy** | Data cleaning and manipulation |
| **Matplotlib & Seaborn** | EDA visualizations |
| **Scikit-learn** | Model building and evaluation |
| **Power BI** | Interactive business dashboard |
| **Jupyter Notebook** | Development environment |

---

## ▶️ How to Run

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### Steps
```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/Customer-Churn-Analysis.git
cd Customer-Churn-Analysis

# 2. Launch Jupyter Notebook
jupyter notebook Customer_Churn.ipynb

# 3. Make sure the CSV is in the same folder (update path in Cell 1 if needed)
```

> For the Power BI dashboard, open `Customer_Churn_Analysis.pbix` in Power BI Desktop.

---

## 💡 Business Recommendations

Based on the analysis:

1. **Target month-to-month customers** with incentives to switch to annual or two-year contracts — they churn at 15× the rate of two-year contract holders.
2. **Review fiber optic pricing** — high monthly charges combined with fiber internet correlate strongly with churn.
3. **Focus retention efforts on new customers** (tenure < 12 months) who are most at risk.
4. **Promote automatic payment methods** — electronic check users show higher churn, possibly due to payment friction.

---

## 👤 Author

**Vikram Rathod**
- 📧 [rathodvikram9000@gmail.com](mailto:rathodvikram9000@gmail.com)
- 💼 [LinkedIn](https://www.linkedin.com/in/vikram-rathod-a51812391/)
- 🐙 [GitHub](https://github.com/rathodvikram9000-web)

---

## 📄 License

This project uses the publicly available [IBM Telco Customer Churn dataset](https://www.kaggle.com/datasets/blastchar/telco-customer-churn).
