# Project Title: Street Trees Data Analysis with AWS Glue and Amazon Athena

## Project Overview
This project focuses on analyzing street tree data using AWS Glue for data cataloging and Amazon Athena for querying and exploration. The primary goal is to streamline data processing, enable efficient querying, and gain insights into the attributes and distribution of trees across various neighborhoods.

## Tools and Technologies Used
- **AWS Glue**: Used for creating crawlers, building the Data Catalog, and preparing datasets for analysis.
- **Amazon Athena**: A serverless query service used to run SQL queries on data stored in AWS Glue Data Catalog.
- **Data Sources**: Street tree datasets containing attributes like tree species, location (civic number, street), plant area, and neighborhood.

---

## Project Steps
### 1. **Data Catalog Creation using AWS Glue**
In this phase, AWS Glue Crawlers were created to automatically discover and catalog the datasets. The crawlers successfully scanned the data, extracted the schema, and created metadata tables in the AWS Glue Data Catalog.

**Screenshot Details:**
- **Crawlers**: Three crawlers (`street-trees-1991-c`, `street-trees-1991-r`, `street-trees-trncra`) were created and ran successfully, resulting in the creation of metadata tables.
- **State**: All crawlers are in the "Ready" state, and the last run status shows "Succeeded".
- **Tables Created**: 7 and 8 tables were added to the catalog by respective crawlers.

---

### 2. **Data Querying and Exploration using Amazon Athena**
In this step, Amazon Athena was used to run SQL queries on the data cataloged by AWS Glue. The query editor was utilized to explore the dataset.

**Screenshot Details:**
- **Query Executed**: `SELECT * FROM "tra-user"`
- **Database**: `street_trees-datacatalog-sau`
- **Results**: The query returned 536 rows, showing key columns such as:
  - `tree_id`
  - `civic_number`
  - `std_street`
  - `genus_name`, `species_name`, `cultivar_name`
  - `common_name`
  - `neighbourhood_name`
- **Query Performance**: The query completed in 1.024 seconds, scanning approximately 127.28 KB of data.

---


