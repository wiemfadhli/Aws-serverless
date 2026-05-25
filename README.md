# ☁️ Aws serverless data pipeline

![AWS](https://img.shields.io/badge/AWS-Cloud-orange)
![S3](https://img.shields.io/badge/S3-Data%20Lake-blue)
![Glue](https://img.shields.io/badge/AWS-Glue-blue)
![Terraform](https://img.shields.io/badge/Terraform-IaC-purple)
![ETL](https://img.shields.io/badge/ETL-Pipeline-green)

---
## Project Overview
This project implements a **scalable cloud-based data pipeline** using AWS services and Infrastructure as Code (Terraform).

It follows a modern **Data Lake architecture**, where data is processed through multiple stages:

The objective is to simulate a **production-grade data engineering system** using fully managed, cloud-native tools.

## Architecture
The pipeline is designed using the **Medallion Architecture (Bronze / Silver / Gold)**:
## Dataset Description
The dataset contains information about companies, including their identity, industry, and operational details.

Each row represents a **single organisation**, and each column describes a specific attribute.

### Columns Explanation

 - index: Unique row identifier for each record.
 - organization_id: Unique identifier for each company (used as a primary key).
 - name: Name of the organisation or company.
 - website: Official website URL of the company.
 - country: Country where the company is located.
 - description: Short business description of the company.
 - founded: Year the company was established.
 - industry: Business sector in which the company operates.
 -  number_of_employees: Total number of employees in the company.
 - company_age: Age of the company (in years).
 #### Example Record
 index: 1 
 organization_id: FAB0d41d5b5d22c
  name: Ferrell LLC
  country: Papua New Guinea 
  industry: Plastics 
  number_of_employees: 3498 
  company_age: 36

## Data Lake (Amazon S3)

Amazon S3 is used as a **centralised Data Lake storage system**, enabling scalable and durable storage for all pipeline data.

### 📁 Data Lake Structure


s3://data-lake-bucket/
│
├── raw/         # 🥉 Bronze Layer → Raw ingested data
├── processed/   # 🥈 Silver Layer → Cleaned & transformed data
└── trusted/     # 🥇 Gold Layer → Final validated dataset


## ETL Pipeline

### 1.  Data Ingestion (Bronze Layer)

 - Raw data is ingested into the **S3 raw/** directory
 - Data is stored in its original format (CSV/JSON)
 
### 2. Data Transformation (Silver Layer)
 - AWS Glue ETL jobs process and clean the data
 - Transformations include:  Handling missing values , Data formatting,Schema standardisation
### 3. Data Validation (Gold Layer)
 - Data quality checks are applied using AWS Glue
 - Ensures:Data consistency,No missing critical fields,Valid schema
 
 ###  4.Infrastructure as Code (Terraform)
All AWS resources are provisioned using **Terraform**, ensuring reproducibility and automation.
 #### Managed Resources:
 
 - S3 Buckets (Data Lake)
 - AWS Glue Jobs
 - IAM Roles & Policies
  #### Tech Stack
 - **Cloud:** AWS
 - **Storage:** Amazon S3
 - **ETL:** AWS Glue
 - **IaC:** Terraform
 - **Language:** PySpark 
 #### How to Run
 ###  1. Clone the repository
git clone https://github.com/wiemfadhli/cloud-data-pipeline.git 
cd cloud-data-pipeline
### 2. Deploy infrastructure
terraform init 
terraform apply
### 3. Upload data
Upload files to: s3://data-lake-bucket/raw/



 

 
 




