
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
![IMG-20241214-WA0013](https://github.com/user-attachments/assets/455e4625-9908-4469-8d48-b7e92f6b0c69)
This screenshot is part of a data ingestion step within the street trees project. It involves uploading and organizing CSV files into an S3 bucket to store the raw data. This data will later be used in subsequent steps of the project for processing, analysis, or reporting.
## data Profiling
![Profiling 1](https://github.com/user-attachments/assets/8aa44664-dcb2-41f0-b782-0256a32477ab)

The image shows an Amazon S3 (Simple Storage Service) interface displaying the contents of a bucket named "van-sttrs-tra-sau" under the folder path "Street_Trees/Data-Profiling/User/". The interface is in the "Objects" tab, which lists the objects stored in this directory
## data infrastructure set up
![IMG-20241214-WA0008](https://github.com/user-attachments/assets/abe802fb-87de-4d80-8bd0-a627c88e801a)

The image shows the AWS Management Console, specifically the VPC (Virtual Private Cloud) dashboard. The dashboard displays a list of VPCs under the "Your VPCs" section. There are two VPCs listed: one named "Street_Trees-vpc" with the VPC ID  and an IPv4 CIDR of "10.0.0.0/27", and another unnamed VPC with the VPC ID "vpc-01ba463659f74488f" and an IPv4 CIDR of "172.31.0.0/16". Both VPCs are in the "Available" state and have "Block Public Access" set to "Off". The left sidebar contains various options related to the VPC, such as Subnets, Route tables, Internet gateways, and more. The top bar shows the current region as "N. Virginia" and the logged-in user details. The "Create VPC" button is also visible on the top right corner.
3. **Crawler Setup**: AWS Glue crawlers are created to scan the data, infer schemas, and populate metadata in the AWS Data Catalog.
4. **Schema Creation**: The crawlers extract schemas and automatically create tables in the AWS Data Catalog.
5. **Querying Data**: Amazon Athena is used to run SQL queries on the structured data.

![Design3](https://github.com/user-attachments/assets/41308cb1-baf6-4e26-8eb3-a0661166777e)

The image shows the Amazon Web Services (AWS) Management Console, specifically the EC2 Instances dashboard. This dashboard displays a list of running EC2 instances. The relevant details include:

Two instances are listed.

Both instances are in the "Running" state.

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

![IMG-20241214-WA0021](https://github.com/user-attachments/assets/0671106f-079f-4332-9763-18c40076b005)

The image shows an AWS Glue Studio interface with a visual representation of an ETL (Extract, Transform, Load) job named "Van-StTrs-Etl-Sau." The interface includes several tabs such as Visual, Script, Job details, Runs, Data quality, Schedules, Version Control, and Upgrade analysis - preview



## data storage and organization
![Cleaning1](https://github.com/user-attachments/assets/92da8f39-8bcc-4473-befe-4c9416d69bd7)

The image is a screenshot of an Amazon S3 console, showing the contents of a bucket named "van-sttrs-tra-sau" within the folder "Street_Trees/Data-Cleaning/User/". This folder contains one object named "van-sttrs-sau_26Nov2024_1732606239969/", which is a subfolder. The console provides options to copy the S3 URI, copy the URL, download, open, delete, and perform other actions on the objects. The navigation breadcrumbs at the top indicate the path within the S3 bucket.

This screenshot is part of a data storage and organization step within the same project related to street trees. Specifically, this step involves managing and structuring the cleaned data in an Amazon S3 bucket after it has undergone transformation processes. The organized folder structure helps maintain version control and easy access to the processed datasets for further analysis or use
![Design2](https://github.com/user-attachments/assets/2f2f9ca0-828b-49b5-a524-3688637eb90d)
The image shows an Amazon S3 (Simple Storage Service) interface from AWS (Amazon Web Services). The specific view is of a bucket named "van-sttrs-tra-sau" with a folder named "Street_Trees/Planted_Trees_As_Per_Street_Side_Name/System/". The "Objects" tab is selected, displaying 
 The storage class for both files is "Standard".
The interface provides options to copy the S3 URI, copy the URL, download, open, delete, and perform other actions on the files. There are also options to create a folder and upload files. The left sidebar includes various sections such as Buckets, Access Grants, Access Points, and Storage Lens, among others.
## data management
![Profiling2](https://github.com/user-attachments/assets/dbb5767b-9994-47d0-b022-85985eef9781)

The image shows an Amazon S3 (Simple Storage Service) console interface. The specific bucket being viewed is named "van-sttrs-raw-sau." The interface displays two folders within this bucket: "ingestion_year=1991/" and "Street_Trees_ClickStreams/". The interface provides options to perform actions such as copying the S3 URI, copying the URL, downloading, opening, deleting, and creating folders. There is also an option to upload files.

![IMG-20241214-WA0015](https://github.com/user-attachments/assets/ea74a615-fd4f-4f54-a7e0-227f51795858)

The image shows a screenshot of the Amazon S3 (Simple Storage Service) management console. It specifically displays the configuration details for a bucket named "van-sttrs-raw-sau." The image highlights two main sections: Lifecycle rules and Replication rules.

1. **Lifecycle Rules:**
   - **Lifecycle rule name:** Move_To_Cheaper_Storage_Class
   - **Status:** Enabled
   - **Scope:** Entire bucket
   - **Current version action:** Transition to Glacier Flex
   - **Noncurrent version action:** (empty)
   - **Expired object delete markers:** (empty)
   - **Incomplete multipart uploads:** (empty)
   - There is a link to "View lifecycle configuration."

2. **Replication Rules:**
   - **Replication rule name:** street-trees-reprul-sau
   - **Status:** Enabled
   - **Destination bucket:** s3://van-sttrs-raw-back-sau
   - **Destination Region:** US East (N. Virginia) us-east-1
   - **Priority:** 0
   - **Scope:** Entire bucket
   - **Storage class:** Same as source
   - **Replica owner:** Same as source
   - **Replication Time Control:** Disabled
   - **KMS-encrypted objects (SSE-KMS or DSSE-KMS):** Replicate
   - **Replicate modifications sync:** Disabled


## Data security
![Ingestion3](https://github.com/user-attachments/assets/be34ffa8-90e1-490d-9c39-82be80dbb90b)

The image is a screenshot of an Amazon S3 bucket configuration page from the AWS Management Console. It shows the settings for the bucket named "van-sttrs-raw-sau" in the N. Virginia region. The "Default encryption" section indicates that server-side encryption is automatically applied to new objects stored in this bucket using AWS Key Management Service (KMS) keys (SSE-KMS). The encryption key ARN is provided, and the bucket key is enabled, which helps reduce encryption costs by lowering calls to AWS KMS. The left sidebar lists various S3 features and settings, such as General purpose buckets, Access Points, and Storage Lens. The "Intelligent-Tiering Archive configurations" section at the bottom is empty, with options to view details, edit, delete, or create a configuration.
![IMG-20241214-WA0019](https://github.com/user-attachments/assets/fab8fe7a-26bf-4c54-99da-7a7d74afcc7a)
This screenshot is part of a data security step within the street trees project. It involves creating and managing encryption keys in AWS KMS to ensure secure data handling and encryption practices. The keys created here will be used to encrypt and decrypt sensitive data, providing a layer of security for the project's data assets.

### 2. Amazon Athena Query Results
![IMG-20241214-WA0024](https://github.com/user-attachments/assets/66c67a2d-7a29-40da-b088-4523bb5b6de5)

- **Description**: The screenshot shows a SQL query executed in Amazon Athena.
- **Details**:
  - The query retrieves all rows from a table named `tra-user` in the `street_trees-datacatalog-sau` database.
  - The results include columns like `tree_id`, `civic_number`, `std_street`, `genus_name`, `species_name`, `common_name`, and neighborhood details.
  - The output confirms successful querying and displays 536 records.
## data management and cost optimization
![IMG-20241214-WA0016](https://github.com/user-attachments/assets/5d5c147e-4a24-4010-b2db-0ba35ad29f78)

The image shows the "Lifecycle configuration" page for an Amazon S3 bucket. This page allows users to manage the lifecycle of objects stored in the bucket by defining rules that specify actions such as transitioning objects to another storage class, archiving them, or deleting them after a specified period of time. The page displays one lifecycle rule named "Move_To_Cheaper_Storage_Class," which is enabled. This rule applies to the entire bucket and transitions the current version of objects to the Glacier Flexible Retrieval storage class. There are options to view details, edit, delete, and create new lifecycle rules.
This screenshot is part of a data management and cost optimization step within the street trees project. It involves configuring lifecycle rules to automate the transition of data to more cost-effective storage classes over time, ensuring efficient storage management while maintaining data accessibility and reducing costs.
## data connectivity 
![IMG-20241214-WA0020](https://github.com/user-attachments/assets/7fb90a55-d0e5-46a4-9846-8704c023aad4)

The image shows the AWS Management Console, specifically the VPC (Virtual Private Cloud) Endpoints section. The console displays details about a specific VPC endpoint named "street-trees-s3endpoint-sau."
This screenshot is part of a data connectivity step within the street trees project. This step involves configuring VPC endpoints to establish secure and efficient connections between the VPC and AWS services, in this case, Amazon S3. This ensures that data can be accessed and transferred within the private network without exposing it to the internet, enhancing security and performance
