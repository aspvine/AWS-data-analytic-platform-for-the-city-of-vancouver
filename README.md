
# AWS Data Analytic Platform for The City of vancouver
## Project Overview
This project focuses on analyzing data related to street trees using AWS Glue, Amazon Athena, and AWS Data Catalog. The workflow includes data ingestion, schema creation, and querying the data to derive insights.

---

## Tools and Technologies
- **AWS Glue**: For ETL (Extract, Transform, Load) processes and data cataloging.
- **Amazon Athena**: For querying the data stored in AWS Data Catalog.
- **AWS Data Catalog**: For organizing and maintaining metadata of the datasets.
- **S3 Storage**: The primary data source for storing raw data.

---

## Project Workflow
1. **Data Ingestion**: Raw data is stored in Amazon S3 buckets.
2. **Crawler Setup**: AWS Glue crawlers are created to scan the data, infer schemas, and populate metadata in the AWS Data Catalog.
3. **Schema Creation**: The crawlers extract schemas and automatically create tables in the AWS Data Catalog.
4. **Querying Data**: Amazon Athena is used to run SQL queries on the structured data.

---

## Screenshots and Explanations

### 1. AWS Glue Crawlers Setup
![AWS Glue Crawlers](screenshot1.png)
- **Description**: The screenshot shows the list of AWS Glue Crawlers used to scan the datasets.
- **Details**:
  - Three crawlers are displayed with their respective statuses as **Ready**.
  - Each crawler scans a specific dataset and updates the table schemas.
  - The results of the last run show tables created in the Data Catalog.

### 2. Amazon Athena Query Results
![IMG-20241214-WA0024](https://github.com/user-attachments/assets/66c67a2d-7a29-40da-b088-4523bb5b6de5)

- **Description**: The screenshot shows a SQL query executed in Amazon Athena.
- **Details**:
  - The query retrieves all rows from a table named `tra-user` in the `street_trees-datacatalog-sau` database.
  - The results include columns like `tree_id`, `civic_number`, `std_street`, `genus_name`, `species_name`, `common_name`, and neighborhood details.
  - The output confirms successful querying and displays 536 records.

