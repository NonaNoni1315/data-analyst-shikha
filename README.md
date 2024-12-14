# data-analyst-shikha
---
## Project 1: AWS-Data-Analyst-UCW Registrar Office (Academic Standing Procedure) 
###### This Project includes UCW Dataset, Class Activity, Weekly Activity
---

This document has explained the UCW Dataset which analyze the students CGPA performance metrics, identify the term risk and recommend the strategies to students for enhancing their academic performance. This Analysis has used the different AWS services like AWS S3 Bucket for data ingestion, Data Brew for cleaning and profiling, Glue for ETL pipeline development, AWS Cloud platform tools.
This is using the dataset of UCW RegistrarOffice-9023p Academic Standing Procedure. It contains the student's academic performance details. It includes information about the student’s Performance with CGPA trend and academic standings. This dataset is useful for the depth analysis to achieve the goal of student improvement outcomes. Weekly activities and class participation have been conducted on weekly basis to perform the AWS services described below.

<img width="468" alt="image" src="https://github.com/user-attachments/assets/9be62de2-5ea9-48e6-b1ed-b8e15c6a8d6d" />

### *Descriptive Analytics*

#### *1. Project Description*
Analyze the student academic performance w.r.t each term to identify the performance trends and propose strategies for improving students CGPA performance.

#### *2. Project Title*
UCW Students Academic Performance Analysis and Recommendations.

#### *3. Objective*
This project goal is to identify the terms where UCW students are most at academic risks of underperformance. With the help of this UCW can highlight the CGPA trends and associate support or improvements which students require.

#### *4. Dataset Attributes*
- *Student ID:* Unique ID for each student.
- *Term:* Academic term.
- *CGPA:* Cumulative Grade Point Average.
- *Term GPA:* GPA achieved during the term.
- *Academic Standing:* Classification (e.g., Good Standing, Probation, Suspension).

### *5. Methodology*

#### Data Collection and Preparation
- Raw academic datasets were ingested into *AWS S3* under the raw directory ro-raw-shikha in structured format.
  
  <img width="468" alt="image" src="https://github.com/user-attachments/assets/2dbcbcb8-c45d-4a43-86e6-464b358a9e3f" />

- *AWS DataBrew* was used for data profiling and data cleansing both to remove the NULL values, duplicate values, column renames, created categorical column and maintain the data consistency. And then moved the cleaned data into back AWS S3 bucket under the transform directory ‘ro-prf-shikha’. The csv output stored under user folder and parquet has stored under system folder.

  <img width="468" alt="image" src="https://github.com/user-attachments/assets/1e3651df-8344-448e-ad8d-164b4557a7b0" />

- Final processed data was stored in the directory ro-cur-shikha under S3 bucket.

#### Data Enrichment
- Additional datasets, such as historical academic records were added for more enriched analysis. These datasets were cleaned using DataBrew and stored in ro-trf-shikha.
- *AWS Glue* ensured schema consistency.

#### ETL Pipeline Development
- AWS Glue services used for performing the ETL (Extract, Transform, Loading) operation. It extracts the UCW dataset from transformation folder and do the transformation to obtain the result for identify students having low CGPA as per the term registered and analyze patterns across terms and CGPA for targeted academic support.
  
  <img width="468" alt="image" src="https://github.com/user-attachments/assets/c9437720-447b-4018-ab8e-b773e085cd5e" />

#### Data Wrangling
- AWS Glue Crawlers provided unlimited query access to the transformed data and stored in the directory ro-cur-shikha under S3 bucket.
  
  <img width="468" alt="image" src="https://github.com/user-attachments/assets/b0f3719b-ffa8-4bd0-94d7-f9ab98e82bd9" />

#### Data Analysis
- *AWS Athena* executed SQL queries to extract term-wise CGPA trends and identify at-risk terms.
  
  <img width="362" alt="image" src="https://github.com/user-attachments/assets/a4a428b4-045c-4c0e-93aa-22d788099b2c" />


#### Insights and Findings
- The *Spring term* displayed the lowest average CGPA which showed that during this term the students are facing higher academic challenges. The significant risk of student’s performance identified in Spring enrollments. 

#### Data Encryption
- Data security was ensured using *AWS KMS* with the encryption key reg-scdStnd-key-shikha. This protected the data during transfer and at rest from unauthorized access.
  
  <img width="468" alt="image" src="https://github.com/user-attachments/assets/8548707a-1b5c-4861-a10c-33d15805ca13" />
  
  <img width="468" alt="image" src="https://github.com/user-attachments/assets/6650fa37-a79b-405a-80e3-1ee068aacad7" />

#### Monitoring and Controlling Operations
- *AWS CloudWatch* is used to monitor ETL jobs, S3 bucket usage, and error logs. These all metrics can be visualized in the created dashboard using AWS Cloud Watch. Cloud Watch (Monitor, Compare, Control, Metric, Logs for resource).
  
  <img width="468" alt="image" src="https://github.com/user-attachments/assets/9cfb2953-50a7-467e-bf1e-4089acbf241e" />

- *CloudTrail* was used to track activities, with logs integrated into CloudWatch. Created the cloud trail with the name ‘reg-scdmStnd-dap-users-shikha'.
  
  <img width="468" alt="image" src="https://github.com/user-attachments/assets/16a1b8e6-f0c4-4a9c-a5e4-c31eb51eb89f" />

### *6. Tools and Technology*
- *S3:* Data storage and management.
- *DataBrew:* Data cleaning and profiling.
- *Glue:* ETL pipeline development.
- *Athena:* Querying and analyzing data.
- *KMS:* Data encryption.
- *CloudWatch:* Monitoring and control.

---
## Project 2: AWS-Data-Analyst-Vancouver City Greenest City Projects
###### This Project includes City of Vancouver - Open Data Portal - Greenest City Project
---

This project analyzes Vancouver’s Greenest City Projects dataset to evaluate sustainability initiatives and their distributed goals. It identifies gaps and opportunities for improving the achievement of sustainability goals like Clean Air, Local Food, and Green Economy. AWS services were employed for efficient data storage, management, processing, and analysis. 

<img width="468" alt="image" src="https://github.com/user-attachments/assets/6a704580-7a80-433d-bb83-36159996607f" />

### *Descriptive Analytics*

#### *1. Project Description*
Analyze Vancouver’s Greenest City Projects dataset to evaluate the distribution and impact of sustainability goals aligned with the Greenest City Action Plan.

#### *2. Project Title*
Analysis for Sustainability Initiatives by Vancouver’s Greenest City Projects

#### *3. Objective*
To analyze the Vancouver’s Greenest City project dataset to evaluate the progress, underperforming category like clean air, local food and underperforming sectors like public or city of sustainability initiatives and provide the recommendations for target achievement.

#### *4. Dataset Attributes*
- *MAPID:* Unique ID for each project.
- *Name:* Project name.
- *Category1:* Project Category (e.g., City Project, Greenest City Fund).
- *Category2:* Project Goal (e.g., Clean Air, Green Economy).
- *Address:* Project location.
- *Description:* Short project description.
- *URLs:* Links for more information.
- *Geo Local Area:* Local area of the project.

### *5. Methodology*

#### Data Collection and Preparation
- The raw datasets were ingested into *AWS S3* under the raw directory shikha-greencity-raw under S3 bucket.
  
  <img width="431" alt="image" src="https://github.com/user-attachments/assets/24a7f0cb-a31f-4538-aee3-84077c292f2e" />

- *AWS DataBrew* performed the data profiling and data cleansing both to remove the NULL values, duplicate values, column renames, created categorical column and maintain the data consistency. Then moved the cleaned data into back AWS S3 bucket under the transform directory ‘shikha-greencity-trf’. The csv output stored under user folder and parquet has stored under system folder. finally, processed data into current directory ‘ro-cur-shikha’.
  
  <img width="468" alt="image" src="https://github.com/user-attachments/assets/e26632c4-206f-406f-945f-a8b2f50272b1" />

#### Data Enrichment
- Additional dataset such as ‘Greenest City Action Plan (GCAP) Metrics’ has been used for more data enrichment for further analysis. This metric provides me the more depth information related the Vancouver’s environmental and sustainability goal progress w.r.t sustainability goals (climate, green buildings, transportation, waste, and water). It helps to highlight the baseline level, target achievement percentage, challenges and future action plan w.r.t each sustainability goal. These data set has been stored under raw directory ‘shikha-greencity-raw’ of AWS S3 bucket then perform the profiling and cleansing using DataBrew service and stored into the transform directory ‘shikha-greencity-trf’ under S3 bucket. Next, AWS Glue service used for making different sources schema consistent. 

#### ETL Pipeline Development
- *AWS Glue* handled ETL (Extract, Transform, Load) processes, transforming data to identify project distribution across categories and goals. It extracts the Greencity dataset from transformation folder and do the transformation to obtain the result for identify the current distribution of projects across different categories, and how does each category contribute to the total project count.

 <img width="468" alt="image" src="https://github.com/user-attachments/assets/783d30bc-18d9-4494-a02f-ee3a016d4b56" />
 
 <img width="468" alt="image" src="https://github.com/user-attachments/assets/f43dca0d-be4b-46f5-a23d-1200a37c37a8" />

#### Data Wrangling
- AWS Glue Crawlers extracted schemas and allowed unlimited querying of data and stored in ro-cur-shikha directory under S3 bucket.

-To create the data catalog using AWS Glue service. I have created a database is ‘database-shikha’.

<img width="468" alt="image" src="https://github.com/user-attachments/assets/a38b6887-a3bb-4627-bf5c-a392514e2b3e" />

-Created  all crawler

<img width="468" alt="image" src="https://github.com/user-attachments/assets/f415c6ce-3933-44e4-a369-be116ac4fb37" />

-Verified the tables created successfully into Database “database-shikha”.

<img width="468" alt="image" src="https://github.com/user-attachments/assets/382490e8-0afc-47d8-99c8-0498fd7af858" />

- *AWS Athena* service for using the SQL queries to to calculate how many goals are below the baselines. With the query result got to know that the ‘Clean-Air’ goal is the only goal which is not achievable out of all goals.

  <img width="468" alt="image" src="https://github.com/user-attachments/assets/e738df7f-2cac-48ab-bf23-8605aa213ad0" />

#### Data Analysis
-Used AWS Athena service for using the SQL queries to to calculate how many goals are below the baselines. With the query result, I got to know that the ‘Clean-Air’ goal is the only goal which is not achievable out of all goals.



#### Insights and Findings
- The *Clean-Air* is the goal which is not achievable out of all goals in Sustainability Action Plan Goal 2020. This can be due to increase of vehicle and related pollution.
- The goal is transferred to next year goal with more initiatives to achieve.

#### Data Protection
- *AWS KMS* encryption key Protection_key_shikha was created for secure data management. Data security plays an important role for keeping data secure using AWS KMS (Key management System) service which helps to protect the S3 bucket from unauthorized access. It helps to stay data securely encrypted both during transfer and at rest.

  <img width="468" alt="image" src="https://github.com/user-attachments/assets/f49a7f74-9425-4ecb-b099-754c59079bd2" />

  <img width="468" alt="image" src="https://github.com/user-attachments/assets/e3b661c4-6d69-4720-bc5a-71c218c8c7f4" />
- Next, created the replication rule with the name ‘greencity-rule-shikha’ under ‘Management’ tab on the original bucket 'ro-raw-shikha'.

  <img width="468" alt="image" src="https://github.com/user-attachments/assets/3221d159-a6ae-4226-91a0-8154a2b6c341" />

  #### Data Governance
- *Data Governance* ensured the data follows all the compliance like quality, completeness, uniqueness, privacy, protection and control. Next, used the AWS Glue service for created ETL. This governance pipeline ensures the privacy, uniqueness and completeness of the dataset.

  <img width="468" alt="image" src="https://github.com/user-attachments/assets/b5941060-7a2b-4637-8b54-67894d809c81" />

  - This ETL stored the Passed and Failed result on the defined folder path "s3://greencity-shikha-rawtrfcurr/greencity-trf-shikha/data-quality-shikha".

    <img width="468" alt="image" src="https://github.com/user-attachments/assets/865af7fa-0bb0-489a-ac88-e4fbe258405e" />

#### Monitoring and Controlling Operations
- *AWS CloudWatch* used to monitor ETL jobs, S3 bucket usage, and error logs. These all metrics can be visualized in the created dashboard using AWS Cloud Watch. Created service name “CloudWatch service” to Monitor, Compare, Control, Metric, Logs for resources.

  <img width="468" alt="image" src="https://github.com/user-attachments/assets/bb6d954a-b9c4-4256-9955-e29d4fd166f4" />

- *CloudTrail* tracked user activities and generated logs for event history. Created the cloud trail with the name ‘greencity-UserTrail-shikha’.
  
  <img width="468" alt="image" src="https://github.com/user-attachments/assets/392513ff-1b59-46e5-b631-fc98ca979eb6" />

- Lastly, used the event history of the user under Event History of Cloud Trail to monitor the events executed by the users.

  <img width="468" alt="image" src="https://github.com/user-attachments/assets/e514847d-c71c-4166-a194-b69740aa0e60" />


### *6. Tools and Technology*
- *S3:* Data storage and management.
- *DataBrew:* Data cleaning and profiling.
- *Glue:* ETL pipeline development.
- *Athena:* Querying and analyzing data.
- *KMS:* Data encryption.
- *CloudWatch:* Monitoring and control.

