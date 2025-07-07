# 📊 Globex Retail Data Pipeline Analytics

**Tools:** Python, Pandas, Jupyter Notebook, SQL, PostgreSQL (optional), SQLAlchemy

## 🧾 Project Overview

This project focuses on performing in-depth **data cleaning, transformation, and analysis** on transactional retail data from **Globex**, a fictional retail company. The goal is to extract insights on customer behavior, product performance, discount impacts, and revenue trends — ultimately supporting business decision-making and customer segmentation.
---

## 🔧 Technologies Used

- **Python (Pandas, NumPy)** – for data cleaning, aggregation, and transformation
- **Jupyter Notebook** – for interactive analysis and step-by-step documentation
- **SQLAlchemy + PostgreSQL (optional)** – for scalable backend storage (via `.env` credentials)
- **Matplotlib / Seaborn** *(optional)* – for visualizing trends and category performance

---

## 📂 Data Source

The data used for this analysis is located in:/data/globex_retail_data.csv


Key fields include:
- `Customer_ID`
- `Order_ID`
- `Order_Date`
- `Product_Category` / `Product_Sub_Category`
- `Quantity`, `Price`, `Discount`, `Revenue`
- `Customer_Location`

---

## ✅ Key Tasks Performed

### 1. Data Cleaning
- Removed nulls from critical columns (`Order_ID`, `Revenue`, etc.)
- Converted `Order_Date` to datetime
- Dropped duplicate rows
- Validated revenue using: `Quantity * Price * (1 - Discount)`

### 2. Feature Engineering
- Extracted `Order_Month` from `Order_Date`
- Derived `Calculated_Revenue` and validated it against `Revenue`
- Created `Order_Value` column for tracking individual transaction values
- Computed average order value (`Avg_Order_Value`) per customer

### 3. Customer-Level Merge
- Merged per-customer average order value into the main dataset using `Customer_ID`
- Enabled row-level comparison and segmentation using customer insights

### 4. Customer Segmentation
- Defined **High-Value Customers** (top 20% by Avg Order Value)
- Labeled each transaction with a segment: `'High-Value'` or `'Regular'`

### 5. Business Questions Answered
- Which product categories generate the most revenue?
- What are the most profitable subcategories?
- What discount behavior is associated with high-value customers?
- Which regions have the most high-value customers?
- What are the monthly revenue trends?
- What is the impact of discounting across product categories?

---

## 📈 Sample Insights

- **Top Product Categories:** Electronics, Clothing, Sports
- **High-Value Threshold:** Avg Order Value ≥ ₤235.00
- **Avg Discount for High-Value Customers:** ~6.8%
- **Top Region for High-Value Customers:** London

---

## 🚀 How to Run

**Clone the repository:**
   ```bash
   git clone https://github.com/dibanga2800/globex-retail-analysis.git
   cd globex-retail-analysis

**🔒 Environment Variables (Optional)**
If connecting to a PostgreSQL database, create a .env file:

DB_USER=your_username
DB_PASS=your_password
DB_HOST=localhost
DB_NAME=globex_retail

**** Future Improvements***
Normalize the dataset into relational tables (e.g., Customers, Orders, Products) to improve integrity and optimize for SQL analytics or database storage.

Add visualizations using Seaborn or Plotly to enhance trend storytelling.

Deploy insights dashboard using Streamlit or Power BI.

Connect to a live PostgreSQL database for scalable querying and storage.

Automate monthly trend reporting using Python schedulers or Airflow.






