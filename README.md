# databricks-crypto-mini-Project
#Weekend Project_1
#Financial_Data

🚀 E2E Crypto Data Pipeline: Medallion Architecture on Databricks
📌 Project Overview
This project demonstrates a production-grade End-to-End (E2E) Data Pipeline built on Databricks Community Edition. It ingests real-time cryptocurrency market data from the CoinGecko API and processes it through a Medallion Architecture (Bronze → Silver → Gold) to provide actionable investment insights.

The Challenge
As an data engineer with 6 years of experience, I designed this project to showcase adaptability. When faced with DBFS root access restrictions in the Databricks free tier, I implemented a robust In-Memory Spark Ingestion strategy to bypass filesystem limitations without compromising data integrity.

🏗️ Architecture & Data Flow
The pipeline follows the Lakehouse Medallion Architecture, ensuring data quality at every stage.

    1. Bronze Layer (Raw Ingestion)
    Source: CoinGecko REST API.
    
    Process: Data is fetched via Python requests, converted into a Spark DataFrame in-memory, and persisted as a managed Delta Table.
    
    Goal: Maintain an immutable history of raw API responses with ingestion timestamps.
    
    2. Silver Layer (Cleaned & Augmented)
    Process: * Schema enforcement and type casting (e.g., converting prices to Double).
    
    Filtering out records with missing essential data.
    
    Feature engineering: Added a is_high_volume flag for market analysis.
    
    Goal: Provide a "Single Source of Truth" for downstream consumption.
    
    3. Gold Layer (Business Ready)
    Process: Aggregations focused on market distribution and average price volatility.
    
    Goal: Power high-level dashboards and executive reports.

🛠️ Tech Stack
    Language: PySpark, Python, SQL
    
    Platform: Databricks (Community Edition)
    
    Storage: Delta Lake
    
    Orchestration: Databricks Notebook Workflows
    
    Version Control: Git Folders (GitHub Integration)
