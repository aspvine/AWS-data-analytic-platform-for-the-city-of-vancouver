
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
   ![Data ingestion1](https://github.com/user-attachments/assets/1e2d8baf-2df3-49ff-a743-ce5849c81246)
as seen from the shot
![Ingestion4](https://github.com/user-attachments/assets/381cf064-cee8-4bf4-a330-3cdd2d304fbd)

The image is a screenshot of an Amazon S3 (Simple Storage Service) bucket interface from the AWS Management Console. The interface displays a list of objects within this bucket, including their names, types, last modified dates, sizes, and storage classes. Some of the objects listed are:
started 
The interface also includes options to copy the S3 URI, copy the URL, download, open, delete, and perform other actions on the selected objects. There are also options to create a folder and upload files.
## data Profiling
![Profiling 1](https://github.com/user-attachments/assets/8aa44664-dcb2-41f0-b782-0256a32477ab)

The image shows an Amazon S3 (Simple Storage Service) interface displaying the contents of a bucket named "van-sttrs-tra-sau" under the folder path "Street_Trees/Data-Profiling/User/". The interface is in the "Objects" tab, which lists the objects stored in this directory
## data infrastructure set up
![IMG-20241214-WA0008](https://github.com/user-attachments/assets/abe802fb-87de-4d80-8bd0-a627c88e801a)

The image shows the AWS Management Console, specifically the VPC (Virtual Private Cloud) dashboard. The dashboard displays a list of VPCs under the "Your VPCs" section. There are two VPCs listed: one named "Street_Trees-vpc" with the VPC ID  and an IPv4 CIDR of "10.0.0.0/27", and another unnamed VPC with the VPC ID "vpc-01ba463659f74488f" and an IPv4 CIDR of "172.31.0.0/16". Both VPCs are in the "Available" state and have "Block Public Access" set to "Off". The left sidebar contains various options related to the VPC, such as Subnets, Route tables, Internet gateways, and more. The top bar shows the current region as "N. Virginia" and the logged-in user details. The "Create VPC" button is also visible on the top right corner.
3. **Crawler Setup**: AWS Glue crawlers are created to scan the data, infer schemas, and populate metadata in the AWS Data Catalog.
4. **Schema Creation**: The crawlers extract schemas and automatically create tables in the AWS Data Catalog.
5. **Querying Data**: Amazon Athena is used to run SQL queries on the structured data.

---

## data process
###![Extraction1](https://github.com/user-attachments/assets/1bb1f7cf-77b6-4e5e-bf20-a2f7c26ee965)
 1. AWS Glue Crawlers Setup

- **Description**: The screenshot shows the list of AWS Glue Crawlers used to scan the datasets.
- **Details**:
  - Three crawlers are displayed with their respective statuses as **Ready**.
  - Each crawler scans a specific dataset and updates the table schemas.
  - The results of the last run show tables created in the Data Catalog.
### Data transformation
![Data ingestion2](https://github.com/user-attachments/assets/95ee2cec-e540-42f8-8ffa-7d3d4375ef02)
The image is a screenshot of the AWS DataBrew interface, specifically showing the "Jobs" section. It displays a list of "Recipe jobs" with one job listed. The job name is "van-sttrs-sau," and its status is marked as "Succeeded" with a green checkmark. The job's input includes a project named "van-sttrs-dtp..." and a dataset named "Street-Trees." The job output indicates "1 output." The last run of this job was 7 minutes ago, on November 25, 2024, at 11:31 PM. The job was created 9 minutes ago, on the same date, at 11:28 PM, by a user named "voclabs."
This job is part of a data transformation step within AWS DataBrew. In this step, data from the "Street-Trees" dataset is processed and transformed according to the recipe defined in the project. The purpose of this step is to clean, enrich, or restructure the raw data to prepare it for further analysis, reporting, or machine learning tasks.
## data storage and organization
![Cleaning1](https://github.com/user-attachments/assets/92da8f39-8bcc-4473-befe-4c9416d69bd7)

The image is a screenshot of an Amazon S3 console, showing the contents of a bucket named "van-sttrs-tra-sau" within the folder "Street_Trees/Data-Cleaning/User/". This folder contains one object named "van-sttrs-sau_26Nov2024_1732606239969/", which is a subfolder. The console provides options to copy the S3 URI, copy the URL, download, open, delete, and perform other actions on the objects. The navigation breadcrumbs at the top indicate the path within the S3 bucket.

This screenshot is part of a data storage and organization step within the same project related to street trees. Specifically, this step involves managing and structuring the cleaned data in an Amazon S3 bucket after it has undergone transformation processes. The organized folder structure helps maintain version control and easy access to the processed datasets for further analysis or use
![Design2](https://github.com/user-attachments/assets/2f2f9ca0-828b-49b5-a524-3688637eb90d)
The image shows an Amazon S3 (Simple Storage Service) interface from AWS (Amazon Web Services). The specific view is of a bucket named "van-sttrs-tra-sau" with a folder named "Street_Trees/Planted_Trees_As_Per_Street_Side_Name/System/". The "Objects" tab is selected, displaying 
 The storage class for both files is "Standard".
The interface provides options to copy the S3 URI, copy the URL, download, open, delete, and perform other actions on the files. There are also options to create a folder and upload files. The left sidebar includes various sections such as Buckets, Access Grants, Access Points, and Storage Lens, among others.
## Data security
![Ingestion3](https://github.com/user-attachments/assets/be34ffa8-90e1-490d-9c39-82be80dbb90b)

The image is a screenshot of an Amazon S3 bucket configuration page from the AWS Management Console. It shows the settings for the bucket named "van-sttrs-raw-sau" in the N. Virginia region. The "Default encryption" section indicates that server-side encryption is automatically applied to new objects stored in this bucket using AWS Key Management Service (KMS) keys (SSE-KMS). The encryption key ARN is provided, and the bucket key is enabled, which helps reduce encryption costs by lowering calls to AWS KMS. The left sidebar lists various S3 features and settings, such as General purpose buckets, Access Points, and Storage Lens. The "Intelligent-Tiering Archive configurations" section at the bottom is empty, with options to view details, edit, delete, or create a configuration.

This screenshot is part of a data security step within AWS, specifically focusing on the configuration and management of encryption settings for the S3 bucket to ensure data protection and compliance
The interface includes options to view details, run the job, perform actions, 
### 2. Amazon Athena Query Results
![IMG-20241214-WA0024](https://github.com/user-attachments/assets/66c67a2d-7a29-40da-b088-4523bb5b6de5)

- **Description**: The screenshot shows a SQL query executed in Amazon Athena.
- **Details**:
  - The query retrieves all rows from a table named `tra-user` in the `street_trees-datacatalog-sau` database.
  - The results include columns like `tree_id`, `civic_number`, `std_street`, `genus_name`, `species_name`, `common_name`, and neighborhood details.
  - The output confirms successful querying and displays 536 records.

