# Data-Analyst-Akshita
1. Project Description
Descriptive Analysis of Animal Services Business Licenses in Vancouver
2. Project Title
Analyzing Business License Status, Revenue & Workforce in Vancouver's Animal Services Sector
3. Objective
My goal was to analyze the City of Vancouver's Animal Services business license data to identify trends related to license statuses, total fees collected, and workforce size. I built a cloud-based data platform using AWS services to ingest, clean, and summarize this dataset so that stakeholders can make informed decisions based on real insights.
4. Dataset
The dataset was sourced from the City of Vancouver Open Data Catalog. It includes fields such as License Number, Business Name, Business Type, Status, Issued and Expiry Dates, Number of Employees, and Fee Paid. The raw data was uploaded to an S3 bucket: s3://business-raw-aks/licenses/animal-services/year=2025/server=BLGVS-AKS/
5. Methodology
Data Collection and Preparation
- Uploaded dataset to S3 with a structured path for scalability.
- Used AWS Glue DataBrew to create a project and fix CSV delimiter issues by switching to semicolons.
Data Profiling
- Performed profiling in AWS Glue DataBrew to assess structure and data quality.
- Identified missing values and irrelevant columns.
- Ensured proper column separation and type recognition.
Data Cleaning
- Removed unnecessary columns (Postal Code, Geom, etc.).
- Dropped rows with NULL or zero in FeePaid and NumberofEmployees.
- Standardized data types and date formats.
- Filtered only 'Issued' licenses under Animal Services.
Data Cataloging
- Created a Glue database: business-data-catalog-aks.
- Used Glue Crawler to catalog metadata and partitioned data by Status.
Data Summarization
- Used Athena for SQL queries to calculate:
  1. Total licenses per status.
  2. Total licensing revenue.
  3. Average employees per business type.
- Built ETL pipeline to aggregate and store summaries in the curated S3 bucket.
6. Tools and Technologies
- Amazon S3 – For raw, transformed, and curated dataset storage
- AWS Glue DataBrew – For profiling and cleaning
- AWS Glue Data Catalog – For managing metadata
- Amazon Athena – For querying with SQL
- AWS KMS – For encryption and secure access
- AWS CloudWatch & CloudTrail – For usage tracking and monitoring
7. Deliverables
- Cleaned and transformed dataset stored in S3
- SQL query results addressing the key business questions
- Data catalog with partitioned tables
- Monitoring dashboard in CloudWatch
- Security and audit logs using KMS and CloudTrail
- Estimated monthly AWS cost: $4.27 (Yearly: ~$51.24)
8. Insights and Recommendations
Insights:
- Most Animal Services businesses operate with fewer than 5 employees.
- Issued licenses dominate the dataset.
- A few business types contribute the majority of licensing revenue.
- Over 95% of expiration dates were outdated.

Recommendations:
- Improve update frequency of expiration records.
- Focus policies on high-revenue business types.
- Integrate spatial data for more geographic insights.
- Explore ML for forecasting license renewals or spotting anomalies.

This project helped me apply AWS tools in a real-world scenario, transforming raw data into valuable business insights.

— Akshita Katoch
