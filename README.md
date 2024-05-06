# IBM-capstone-project
![image](https://github.com/hb267/IBM-capstone-project/assets/93075014/392f23a4-a569-4b48-9dc6-af33202dd2e9)

## <u>Project Outline</u>

 * SoftCart primarily operates online through its website, which customers access via various devices such as laptops, mobiles, and tablets.
 * All product catalog data is stored in the MongoDB NoSQL server, while transactional data like inventory and sales are stored in the MySQL database server. These two databases exclusively power SoftCart's webserver.
 * Data from these databases is periodically extracted and transferred to the staging data warehouse, operating on PostgreSQL. The production data warehouse resides on IBM DB2 server's cloud instance.
 * The business intelligence (BI) teams utilize IBM DB2 for operational dashboard creation, employing IBM Cognos Analytics to design dashboards.
 * SoftCart employs a Hadoop cluster as its big data platform, where data collected for analytics purposes is stored. Spark is utilized to analyze this data within the Hadoop cluster.
 * To facilitate data movement between OLTP, NoSQL, and the data warehouse, ETL pipelines are employed, which are orchestrated using Apache Airflow.

 ## <u>Assignment Briefs</u>

### 1. MySQL for Real-time Transaction Handling Database:
    
SoftCart plans to employ MySQL for our real-time transactional processing needs, encompassing tasks like storing inventory and sales records. Utilizing the provided sample data, we'll devise the database structure and establish a database for housing our sales information. Additionally, we'll implement an index on the timestamp field and develop a bash script for administrative purposes, tasked with exporting sales data into a SQL file.

### 2. MongoDB NoSQL Product Catalog Database:

SoftCart has chosen MongoDB NoSQL server to house all catalog-related data. Our objective is to establish the 'catalog' database and import our electronics product dataset from catalog.json into a collection named 'electronics.' Subsequently, we'll conduct trial queries on the data and export the 'electronics' collection into a file named 'electronics.csv,' including only the '_id,' 'type,' and 'model' fields.

### 3. PostgreSQL Staging Data Repository:

SoftCart's strategy involves regularly extracting sales data from MySQL and catalog data from MongoDB, then storing it in a staging data repository hosted on PostgreSQL. This data will undergo transformation before being loaded into the production data warehouse on IBM Db2. The goal is to generate comprehensive reports, including:

 * Total sales per year per country
 * Total sales per month per category
 * Total sales per quarter per country
 * Total sales per category per country

To fulfill this, we'll design a star schema for the data warehouse using the pgAdmin ERD design tool. This schema must support the generation of reports on a yearly, monthly, daily, and weekly basis. Following design completion, the schema SQL will be exported, and a staging database will be created. The Senior Data Engineer will then evaluate the schema design, and adjustments will be made if necessary before proceeding to the subsequent phase.

### 4. IBM Db2 Production Data Warehouse:

Following the schema design adjustments, the next step involves creating an instance of IBM Db2 and loading the sample datasets into their corresponding tables. Additionally, we'll craft aggregation queries to generate insightful reports and establish a Materialized Query Table (MQT) to facilitate future report generation.

### 5. Python Script for Database Synchronization:

As part of SoftCart's daily operations, maintaining data synchronization across various databases and data warehouses is essential. One recurring task involves syncing up the staging data warehouse with the production data warehouse. To streamline this process, a Python script will be developed to automate the regular update of the DB2 instance with new records from MySQL.

This script will:

 * Establish connections to both the MySQL and DB2 databases.
 * Retrieve new records from MySQL that need to be synced.
 * Insert these new records into the corresponding tables in the DB2 instance.
 * Log any errors or exceptions encountered during the synchronization process.

By executing this script on a scheduled basis, SoftCart can ensure that its production data warehouse remains up-to-date with the latest information from MySQL.

### 6. Apache Airflow Log Analysis DAG:

SoftCart's accesslog.txt file requires analysis. An Apache Airflow DAG pipeline will be created for this purpose. The pipeline will:

 * Extract: Read accesslog.txt to extract relevant lines and fields.
 * Transform: Process the extracted data, applying necessary transformations.
 * Load: Store the transformed data in an existing file or destination for further analysis.

By automating these steps, SoftCart can efficiently analyze web server log files using Airflow.

### 7. Apache Spark Big Data Analytics:

SoftCart's team has curated a dataset comprising search terms from our e-commerce platform. To perform analytics, download the dataset and execute queries using PySpark within JupyterLab. Additionally, leverage a pre-trained sales forecasting model to predict sales for the year 2023.

 ## <u>Tools</u>

 * OLTP Database - MySQL
 * NoSql Database - MongoDB
 * Production Data Warehouse – DB2 on Cloud
 * Staging Data Warehouse – PostgreSQL
 * Big Data Platform - Hadoop
 * Big Data Analytics Platform – Spark
 * Business Intelligence Dashboard - IBM Cognos Analytics
 * Data Pipelines - Apache Airflow






   
