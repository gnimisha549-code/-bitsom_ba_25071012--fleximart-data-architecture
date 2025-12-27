# FlexiMart Data Architecture Project

**Student Name:** [Nimisha Gupta]
**Student ID:** [bitsom_ba_25071012]
**Email:** [gnimisha549@gmail.com]
**Date:** [27-12-2025]

## Project Overview

[FlexiMart Data Architecture Project processes e-commerce data from customers_raw.csv, products_raw.csv, and sales_raw.csv through complete ETL, NoSQL analysis, and data warehousing pipelines. Part 1 builds operational MySQL database with business queries, Part 2 implements MongoDB product catalog operations, and Part 3 creates star schema data warehouse for analytics. All components follow the exact repository structure and pass quality validation tests]

## Repository Structure
├── part1-database-etl/
│   ├── etl_pipeline.py
│   ├── schema_documentation.md
│   ├── business_queries.sql
│   └── data_quality_report.txt
├── part2-nosql/
│   ├── nosql_analysis.md
│   ├── mongodb_operations.js
│   └── products_catalog.json
├── part3-datawarehouse/
│   ├── star_schema_design.md
│   ├── warehouse_schema.sql
│   ├── warehouse_data.sql
│   └── analytics_queries.sql
└── README.md

## Technologies Used

- Python 3.x, pandas, mysql-connector-python
- MySQL 8.0 / PostgreSQL 14
- MongoDB 6.0

## Setup Instructions

### Database Setup

```bash
# Create databases
mysql -u root -p -e "CREATE DATABASE fleximart;"
mysql -u root -p -e "CREATE DATABASE fleximart_dw;"

# Run Part 1 - ETL Pipeline
python part1-database-etl/etl_pipeline.py

# Run Part 1 - Business Queries
mysql -u root -p fleximart < part1-database-etl/business_queries.sql

# Run Part 3 - Data Warehouse
mysql -u root -p fleximart_dw < part3-datawarehouse/warehouse_schema.sql
mysql -u root -p fleximart_dw < part3-datawarehouse/warehouse_data.sql
mysql -u root -p fleximart_dw < part3-datawarehouse/analytics_queries.sql


### MongoDB Setup

mongosh < part2-nosql/mongodb_operations.js

## Key Learnings

[ETL pipeline development taught robust data validation using pandas for real-world CSV inconsistencies. MongoDB aggregation pipelines provided flexible schema handling for product catalogs versus rigid SQL normalization. Star schema design optimized analytical queries through proper fact-dimension relationships and indexing strategies.]

## Challenges Faced

1. [ETL Data Cleaning: Handled duplicates/missing values in sales_raw.csv; implemented pandas validation generating data_quality_report.txt]
2. [MongoDB Nesting: Complex product relationships required multi-stage aggregation; solved in mongodb_operations.js with documented pipelines]

