# data-analyst-shikha
# Project Portfolio

---

## Project 1: AWS-Data-Analyst-UCW Registrar Office (Academic Standing Procedure)
- *Category:* (UCW Dataset, Class Activity, Weekly Activity)

This document explains the UCW Dataset used to analyze students' CGPA performance metrics, identify term risk, and recommend strategies to enhance academic performance. The analysis employs AWS services, such as S3 Bucket for data ingestion, DataBrew for cleaning and profiling, Glue for ETL pipeline development, and other AWS Cloud platform tools.

### Dataset Overview
The dataset, titled *UCW RegistrarOffice-9023p Academic Standing Procedure*, contains details on students’ academic performance. It includes CGPA trends and academic standings to support in-depth analysis and achieve the goal of improving student outcomes. Weekly activities and class participation were conducted to perform the AWS services described below.

<img width="468" alt="image" src="https://github.com/user-attachments/assets/bdf979de-badb-4b86-b2b7-5d8fc72fb12a" />

### *Descriptive Analytics*

#### *1. Project Description*
Analyze student academic performance per term to identify performance trends and propose strategies for improving CGPA.

#### *2. Project Title*
UCW Students Academic Performance Analysis and Recommendations

#### *3. Objective*
To identify terms where students are most at academic risk and propose strategies to support and improve student outcomes.

#### *4. Dataset Attributes*
- *Student ID:* Unique ID for each student.
- *Term:* Academic term.
- *CGPA:* Cumulative Grade Point Average.
- *Term GPA:* GPA achieved during the term.
- *Academic Standing:* Classification (e.g., Good Standing, Probation, Suspension).

---

### *5. Methodology*

#### Data Collection and Preparation
- Raw academic datasets were ingested into *AWS S3* under the directory ro-raw-shikha.
  <img width="468" alt="image" src="https://github.com/user-attachments/assets/2dbcbcb8-c45d-4a43-86e6-464b358a9e3f" />

- *AWS DataBrew* was used for data profiling and cleansing, removing NULL values, duplicates, and ensuring consistency. Cleaned data was moved to ro-prf-shikha.
- Final processed data was stored in the ro-cur-shikha directory.

#### Data Enrichment
- Additional datasets, such as historical academic records, were added for more enriched analysis. These datasets were cleaned using DataBrew and stored in ro-trf-shikha.
- *AWS Glue* ensured schema consistency.

#### ETL Pipeline Development
- AWS Glue performed ETL operations, transforming the UCW dataset to analyze patterns and identify students with low CGPA.

#### Data Wrangling
- AWS Glue Crawlers provided unlimited query access to the transformed data, stored in the directory ro-cur-shikha.

#### Data Analysis
- *AWS Athena* executed SQL queries to extract term-wise CGPA trends and identify at-risk terms.

#### Insights and Findings
- The *Spring term* displayed the lowest average CGPA, highlighting academic challenges during this period.

#### Data Encryption
- Data security was ensured using *AWS KMS* with the encryption key reg-scdStnd-key-shikha. This protected the data during transfer and at rest.

#### Monitoring and Controlling Operations
- *AWS CloudWatch* monitored ETL jobs, S3 bucket usage, and error logs. Metrics were visualized in CloudWatch dashboards.
- *CloudTrail* was used to track activities, with logs integrated into CloudWatch.

---

### *6. Tools and Technology*
- *S3:* Data storage and management.
- *DataBrew:* Data cleaning and profiling.
- *Glue:* ETL pipeline development.
- *Athena:* Querying and analyzing data.
- *KMS:* Data encryption.
- *CloudWatch:* Monitoring and control.

---

### *Project Image*
[![AWS Data Analyst UCW Project](https://example.com/images/ucw-academic-standing.jpg)](https://example.com/ucw-project-details)

---

## Project 2: AWS-Data-Analyst-Vancouver City Greenest City Projects
- *Category:* (City of Vancouver - Open Data Portal - Greenest City Project)

This project analyzes Vancouver’s Greenest City Projects dataset to evaluate sustainability initiatives and their distributed goals. It identifies gaps and opportunities for improving the achievement of sustainability goals like Clean Air, Local Food, and Green Economy. AWS services were employed for efficient data storage, management, processing, and analysis.

---

### *Descriptive Analytics*

#### *1. Project Description*
Analyze Vancouver’s Greenest City Projects dataset to evaluate the distribution and impact of sustainability goals aligned with the Greenest City Action Plan.

#### *2. Project Title*
Analysis for Sustainability Initiatives by Vancouver’s Greenest City Projects

#### *3. Objective*
To evaluate progress and underperformance in sustainability goals and provide recommendations for target achievement.

#### *4. Dataset Attributes*
- *MAPID:* Unique ID for each project.
- *Name:* Project name.
- *Category1:* Project Category (e.g., City Project, Greenest City Fund).
- *Category2:* Project Goal (e.g., Clean Air, Green Economy).
- *Address:* Project location.
- *Description:* Short project description.
- *URLs:* Links for more information.
- *Geo Local Area:* Local area of the project.

---

### *5. Methodology*

#### Data Collection and Preparation
- Raw datasets were ingested into *AWS S3* under the directory shikha-greencity-raw.
- *AWS DataBrew* performed data cleansing and consistency checks. Cleaned data was stored in shikha-greencity-trf.

#### Data Enrichment
- Additional datasets, such as Greenest City Action Plan metrics, were added for deeper analysis. These metrics were cleansed using DataBrew and stored in the transform directory.

#### ETL Pipeline Development
- *AWS Glue* handled ETL processes, transforming data to identify project distribution across categories and goals.

#### Data Wrangling
- AWS Glue Crawlers extracted schemas and allowed unlimited querying of data, stored in ro-cur-shikha.

#### Data Analysis
- *AWS Athena* queries identified goals below baseline levels, such as the *Clean-Air* goal, which was underachieved.

#### Insights and Findings
- The *Clean-Air* goal remains unachievable due to increased pollution. It has been transferred to the next year for further initiatives.

#### Data Protection
- *AWS KMS* encryption key Protection_key_shikha was created for secure data management. A replication rule greencity-rule-shikha was added to enhance protection.

#### Monitoring and Controlling Operations
- *AWS CloudWatch* monitored S3 bucket usage, ETL jobs, and error logs. A dashboard visualized metrics for smooth operations.
- *CloudTrail* tracked user activities and generated logs for event history.

---

### *6. Tools and Technology*
- *S3:* Data storage and management.
- *DataBrew:* Data cleaning and profiling.
- *Glue:* ETL pipeline development.
- *Athena:* Querying and analyzing data.
- *KMS:* Data encryption.
- *CloudWatch:* Monitoring and control.

---

### *Project Image*
[![Vancouver Greenest City Project](https://example.com/images/vancouver-greenest-city.jpg)](https://example.com/vancouver-project-details)
