# 📺 YouTube Trending Videos Data Engineering Pipeline (AWS)

This project implements an end-to-end data engineering pipeline on AWS to analyze **YouTube trending videos** across countries. It demonstrates how to ingest, clean, store, catalog, query, and visualize semi-structured data using a modern serverless architecture.

Inspired by [Darshil Parmar's walkthrough](https://www.youtube.com/watch?v=yZKJFKu49Dk), the project provides a scalable and modular approach to building data pipelines using AWS-native services.

---

## 🎯 Project Objectives

- Automate the ingestion of YouTube trending video data (CSV/JSON)
- Convert raw JSON data into columnar Parquet format for efficiency
- Catalog metadata using AWS Glue for schema discovery
- Query cleaned data with Amazon Athena
- Visualize KPIs using Amazon QuickSight or Tableau

---
## 🧩 Architecture Overview
![architecture](https://github.com/user-attachments/assets/faead011-0035-4a2e-9a0e-df8e02dbe969)



## 🧰 Technologies & Services Used

| Service/Tool       | Purpose                                 |
|--------------------|------------------------------------------|
| **Amazon S3**       | Store raw and processed files            |
| **AWS Lambda**      | Automate JSON to Parquet conversion      |
| **AWS Glue Crawler**| Auto-detect schema & catalog metadata    |
| **Amazon Athena**   | Query Parquet files using SQL            |
| **Amazon QuickSight**| Dashboard and visualizations           |
| **Python (PySpark)**| Optional ETL/cleaning logic              |

---

## 🔄 Workflow Steps

1. **Ingest Data**  
   Upload YouTube trending JSON/CSV files by country to the S3 raw bucket.

2. **Lambda Trigger**  
   A Lambda function listens for S3 PUT events, processes new files, and writes transformed Parquet files to a clean S3 path.

3. **Glue Crawler**  
   Scheduled crawler detects schema and updates the Glue Data Catalog.

4. **Athena Queries**  
   Use SQL to query across countries, categories, view counts, likes, etc.

5. **Dashboarding**  
   Connect Athena to QuickSight or Tableau for insights:
   - Top trending categories by country
   - Daily view count trends
   - Like-dislike ratio analysis

---

## 📊 Key Features

- ✅ Event-driven pipeline (no manual trigger)
- ✅ Efficient columnar storage with Parquet
- ✅ Supports multi-region trending video ingestion
- ✅ Athena-ready for ad hoc analysis
- ✅ Extensible to any streaming JSON dataset

---

## 🚀 Future Improvements

- Add Airflow or Step Functions for orchestrating multi-step pipelines
- Integrate YouTube Data API to fetch latest data daily
- Add sentiment analysis using video titles/comments
- Deploy versioned Lambda via AWS SAM or CDK

---

## 👤 Author

**Puneeth Velivela**  
Data Analytics Engineer | George Mason University  
Inspired by [Darshil Parmar’s Project Walkthrough](https://www.youtube.com/watch?v=yZKJFKu49Dk)

