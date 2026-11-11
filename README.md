# 🛒 DMart MMR Retail Analytics & Machine Learning Pipeline (H1 2026)

An enterprise-grade end-to-end data science and analytics portfolio project simulating retail operations across the Mumbai Metropolitan Region (MMR). This project bridges raw point-of-sale (POS) data engineering, exploratory data analysis, advanced machine learning modeling, and executive-level business strategy.

---

## 📋 Table of Contents
1. [Project Overview & Business Scenario](#-project-overview--business-scenario)
2. [Data Engineering & Robust ETL Pipeline](#-data-engineering--robust-etl-pipeline)
3. [Exploratory Data Analysis (EDA)](#-exploratory-data-analysis-eda)
4. [Advanced Machine Learning Modeling](#-advanced-machine-learning-modeling)
   * [Customer Segmentation (K-Means & RFM)](#a-customer-segmentation-k-means--rfm)
   * [Customer Churn Prediction (Random Forest)](#b-customer-churn-prediction-random-forest)
   * [Market Basket Analysis (Apriori Association Rules)](#c-market-basket-analysis-apriori-association-rules)
   * [Sales Forecasting (Linear Regression)](#d-sales-forecasting-linear-regression)
5. [Strategic Business Recommendations](#-strategic-business-recommendations)
6. [Tech Stack & Repository Structure](#-tech-stack--repository-structure)

---

## 🎯 1. Project Overview & Business Scenario

* **Domain:** Retail & FMCG (Hypermarket Operations)
* **Geographic Scope:** Mumbai Metropolitan Region (MMR outlets including Dadar, Thane, Borivali, Powai, and Panvel).
* **Objective:** Address core retail challenges—specifically customer retention, basket size optimization, and inventory forecasting—by transforming raw, uncleaned transactional logs into actionable strategic intelligence.

---

## 🛠️ 2. Data Engineering & Robust ETL Pipeline

The raw dataset (`DMart_Raw_Transactions_2026`) contains ~39,000 records mirroring real-world point-of-sale anomalies. The Python ETL pipeline executes the following rigorous cleaning steps:
* **Deduplication:** Automatically drops redundant transaction rows.
* **Anomaly Filtering:** Removes negative unit prices (`Unit_Price < 0`) and invalid quantities (`Quantity <= 0`).
* **Text Standardization:** Resolves mixed casing and trailing whitespace across store cities, customer locations, and product categories.
* **Missing Value Imputation:** Imputes demographic attributes (using median for numeric age/income and mode for membership tiers).
* **Temporal Integrity:** Enforces strict H1 2026 date bounds (January 1 to June 30, 2026) to prevent month-drift and schema corruption.

---

## 📈 3. Exploratory Data Analysis (EDA)

* Analyzed over **37,100 clean transaction records** spanning H1 2026.
* Tracked monthly gross revenue trajectory, demonstrating steady upward momentum from **₹3.3M in January to ₹5.3M in June**[cite: 5].
* Evaluated average order value (AOV) and profit margins (~18–22%), identifying high-performing categories such as *Staples* and *Dairy & Bakery*.

---

## 🤖 4. Advanced Machine Learning Modeling

### A. Customer Segmentation (K-Means & RFM)
* Built an RFM (Recency, Frequency, Monetary) feature matrix.
* Applied **K-Means Clustering** to segment MMR shoppers into distinct behavioral cohorts, distinguishing high-value loyalists from occasional bargain hunters.

### B. Customer Churn Prediction (Random Forest)
* Trained a Random Forest classifier to identify dormant or at-risk customers.
* **Model Performance:** Achieved **92.5% Accuracy**, **81.5% Precision**, and **95.3% Recall**.
* **Feature Importance:** Proved that **Recency** is the overwhelming predictor of customer churn (~67% importance), followed by Monetary value and Annual Income[cite: 3].

### C. Market Basket Analysis (Apriori Association Rules)
* Extracted high-lift product pairs to understand cross-merchandising affinities.
* **Top Association:** *Surf Excel Matic 3kg $\rightarrow$ Comfort Fabric Conditioner 2L* achieved a high **Lift of ~3.9**, proving strong complementary purchase patterns[cite: 4].

### D. Sales Forecasting (Linear Regression)
* Built a regression model on monthly sales aggregates across H1 2026[cite: 5].
* **July 2026 Projection:** Successfully forecasted July gross revenue at approximately **₹5.8M**, maintaining consistent retail growth[cite: 5].

---

## 💡 5. Strategic Business Recommendations

1. **Targeted CRM Retention:** Deploy automated WhatsApp and SMS triggers via the DMart Ready app for the **28.2% High-Risk churn segment** crossing 30 days of inactivity[cite: 6].
2. **Adjacency Merchandising:** Relocate fabric softeners directly next to premium laundry detergents in MMR hypermarkets based on Apriori Lift rules[cite: 4].
3. **Tiered Loyalty Perks:** Introduce priority checkout lanes and early weekend access for top-tier K-Means segments.
4. **Supply Chain Buffers:** Pre-position high-turnover FMCG and staple inventory ahead of the projected July retail surge[cite: 5].

---

## ⚙️ 6. Tech Stack & Repository Structure

* **Language:** Python 3.12+
* **Libraries:** Pandas, NumPy, Scikit-Learn, MLxtend, Matplotlib, Seaborn
* **Visualization:** Power BI / Jupyter Notebook plots

```text
├── DMart_Raw_Uncleaned_Transactions_CleanDates_2026.csv  # Raw input dataset
├── DMart_Cleaned_Transactions_2026.csv                 # Cleaned output dataset
├── dmart_pipeline.ipynb                                # Master Jupyter Notebook
└── README.md                                           # Project Documentation