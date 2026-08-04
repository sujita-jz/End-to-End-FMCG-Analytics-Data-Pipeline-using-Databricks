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

# ▶️ Pipeline Execution

Run the notebooks in the following order:

1. Setup Notebook
2. Bronze Layer Notebooks
3. Silver Layer Notebooks
4. Gold Layer Notebooks
5. SQL Analytics
6. Databricks Genie

---

# 📁 Source Data

The project uses data from two organizations.

## Parent Company (Atlikon)

Contains:

- Customers
- Products
- Monthly Sales
- Gross Price
- Pre Invoice Deductions
- Post Invoice Deductions

## Subsidiary (Sports Bar)

Contains:

- Customers
- Products
- Sales

---

# 📌 Data Engineering Concepts Implemented

- Medallion Architecture
- ETL Pipeline
- ELT Processing
- Incremental Loading
- Full Load
- Delta Lake
- Data Lakehouse
- Star Schema
- Fact & Dimension Modeling
- Slowly Changing Dimensions (SCD Type-1)
- Surrogate Key Generation
- Data Cleaning
- Data Validation
- Data Standardization
- SQL Analytics

---

# 📊 Dashboard Ready Tables

The Gold Layer provides reporting-ready datasets for visualization tools such as:

- Power BI
- Tableau
- Databricks SQL Dashboard

Typical reports include:

- Sales Dashboard
- Customer Dashboard
- Product Performance Dashboard
- Regional Sales Dashboard
- Revenue Analysis
- Discount Analysis

---

# 💡 Business Benefits

This solution provides:

- Unified analytics platform for both companies
- Automated data processing
- Faster report generation
- Improved data quality
- Better decision making
- Scalable architecture for future acquisitions
- AI-powered analytics through Databricks Genie

---

# 📸 Project Screenshots

You can include screenshots of:

- Databricks Workspace
- Bronze Layer Tables
- Silver Layer Tables
- Gold Layer Tables
- SQL Queries
- Databricks Genie
- Dashboard Outputs

---

# 📦 Requirements

- Databricks Community Edition
- Python
- PySpark
- SQL
- AWS S3
- Delta Lake

---

# 🔧 Installation

1. Clone the repository

```bash
git clone https://github.com/your-username/FMCG_Analytics_Pipeline.git
```

2. Open Databricks Community Edition.

3. Import all notebooks.

4. Upload the datasets to DBFS/AWS S3.

5. Execute the notebooks in sequence.

6. Query the Gold tables using SQL or Databricks Genie.

# 🎯 Key Learning Outcomes

Through this project, the following concepts were implemented and practiced:

- End-to-End Data Engineering Pipeline
- Medallion Architecture (Bronze → Silver → Gold)
- Delta Lake Implementation
- Incremental ETL Processing
- Data Cleaning & Standardization
- Surrogate Key Generation
- Slowly Changing Dimension (SCD Type-1)
- Star Schema Design
- Fact & Dimension Modeling
- PySpark Data Transformations
- Databricks SQL
- AWS S3 Integration
- AI-powered Analytics using Databricks Genie

---

# 📚 Future Enhancements

Possible improvements include:

- Workflow orchestration using Apache Airflow
- Real-time data ingestion with Apache Kafka
- CI/CD pipeline integration
- Automated data quality monitoring
- Power BI dashboard integration
- Deployment on Azure Databricks or AWS EMR

---
