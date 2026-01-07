# Azure End-to-End Data Engineering Project 🚀


<img width="1920" height="1080" alt="Architecture" src="https://github.com/user-attachments/assets/7bc70fe5-df92-4cc0-8bfc-faab38556cdd" />


## 📌 Project Overview
This project demonstrates an **end-to-end Azure Data Engineering pipeline** using modern cloud data tools and best practices.  
The solution ingests data from a relational source, processes it through a **Medallion Architecture (Bronze, Silver, Gold)** using **Azure Data Factory, Azure Data Lake Gen2, Databricks, and Delta Lake**, and finally serves analytics-ready data for reporting tools.

---

## 🏗️ Architecture Overview

**Source → Ingestion → Storage → Transformation → Serving → Analytics**

### Tools & Technologies Used
- **Azure SQL Database** – Source system  
- **Azure Data Factory (ADF)** – Data ingestion & orchestration  
- **Azure Data Lake Storage Gen2 (ADLS)** – Data storage  
- **Azure Databricks** – Data transformation & processing  
- **Apache Parquet** – Storage format (Bronze & Silver)  
- **Delta Lake** – Optimized storage for Gold layer  
- **Azure Entra ID & Key Vault** – Security & secrets management  
- **Power BI** – Data visualization (optional)

---

## 🥉 Bronze Layer – Raw Data Store
- Stores **incremental data** ingested from the source
- Data is stored in **Parquet format**
- No transformations applied
- Used for **data traceability and reprocessing**


---

## 🥈 Silver Layer – Transformed Data
- Cleansed and standardized data
- Business rules applied
- Data stored as **One Big Table (OBT)**
- Ensures schema consistency and data quality


---

## 🥇 Gold Layer – Serving Layer
- Analytics-ready data
- Designed using **Star Schema**
  - Fact tables
  - Dimension tables
- Stored using **Delta Lake**
- Optimized for BI queries


---

## 🔄 Data Pipeline Flow

1. **Azure Data Factory**
   - Extracts data from Azure SQL
   - Loads incremental data into Bronze layer

2. **Azure Databricks**
   - Reads Bronze data
   - Applies transformations and data quality checks
   - Writes data to Silver and Gold layers

3. **Delta Lake**
   - Enables ACID transactions
   - Supports `MERGE`, `UPDATE`, and time travel
   - Improves performance and reliability

4. **Power BI**
   - Connects to Gold layer
   - Builds dashboards and reports

---

## 🔐 Security Implementation
- **Azure Entra ID** for authentication
- **Azure Key Vault** for secrets management
- Secure access using **Managed Identities**
- RBAC applied on ADLS and Databricks

