# 🏭 Unified Analytics Pipeline — Atlikon × Sports Bar
### End-to-End Data Engineering Project on Databricks (FMCG Domain)

## 📖 Project Overview

This project delivers a **production-grade, end-to-end data engineering pipeline** on **Databricks (Free Edition)** to unify the data infrastructure of **Atlikon** (parent company, sports equipment manufacturer) and its newly acquired subsidiary **Sports Bar** (energy bar startup FMCG).

The pipeline ingests raw, fragmented data from an **AWS S3 data lake**, processes it through the **Medallion Architecture (Bronze → Silver → Gold)** using **PySpark, SQL, and Delta Lake**, and generates analytics-ready datasets for dashboards and AI-powered business insights.

The solution demonstrates modern **Lakehouse architecture**, **incremental ETL processing**, **Slowly Changing Dimensions (SCD Type-1)**, **surrogate key generation**, **data quality validation**, **star schema modeling**, and **interactive analytics using Databricks Genie**.

---

# 🎯 Business Problem

Atlikon acquired Sports Bar to expand into the FMCG market.

However, both companies maintained completely different:

- Customer IDs
- Product IDs
- File formats
- Pricing structures
- Sales systems
- Data quality standards

Business users were unable to generate unified reports because:

- Duplicate customers existed
- Product identifiers differed
- Incremental data arrived every day
- Reports required manual consolidation

The objective was to build a centralized analytics platform capable of handling both organizations seamlessly.

---

# 🏗 Solution Architecture

```
AWS S3 (Raw Files)
        │
        ▼
Bronze Layer (Raw Delta Tables)
        │
        ▼
Silver Layer
(Data Cleaning + Standardization + Business Rules)
        │
        ▼
Gold Layer
(Fact + Dimension Tables)
        │
        ▼
Power BI / SQL Analytics
        │
        ▼
Databricks Genie AI
```

---

# 📂 Project Structure

```
FMCG_Analytics_Pipeline/
│
├── README.md
│
├── Data/
│   ├── Parent Company/
│   └── Subsidiary/
│
├── Notebooks/
│   ├── Setup
│   ├── Bronze Layer
│   ├── Silver Layer
│   ├── Gold Layer
│   └── Incremental Load
│
├── SQL/
│
├── Images/
│
└── Resources/
```

---

# 🏛 Medallion Architecture

## 🥉 Bronze Layer

Purpose:

- Load raw CSV files from AWS S3
- Preserve original source data
- Perform schema inference
- Maintain historical copies
- Support Full Load & Incremental Load

Technologies:

- PySpark
- Delta Lake
- Databricks

Output:

Raw Delta Tables

---

## 🥈 Silver Layer

Purpose:

- Remove duplicate records
- Handle NULL values
- Standardize data
- Generate surrogate keys
- Merge parent and subsidiary datasets
- Implement SCD Type-1
- Apply business validation rules

Transformations:

- Customer Mapping
- Product Mapping
- Date Formatting
- Country Standardization
- Currency Alignment
- Price Validation

Output:

Cleaned Business Tables

---

## 🥇 Gold Layer

Purpose:

Generate analytics-ready datasets.

Created Tables:

Dimension Tables

- dim_customer
- dim_product
- dim_market

Fact Tables

- fact_sales_monthly
- fact_gross_price
- fact_pre_invoice_deductions
- fact_post_invoice_deductions

Business users directly query these tables.

---

# ⚙ Technologies Used

| Category | Technology |
|----------|------------|
| Cloud Storage | AWS S3 |
| Processing | PySpark |
| Platform | Databricks Community Edition |
| Storage | Delta Lake |
| SQL Engine | Databricks SQL |
| Programming | Python |
| Data Format | CSV |
| Version Control | Git & GitHub |
| AI Analytics | Databricks Genie |
