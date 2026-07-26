### Healthcare_Patient_Analytics_ELT_Pipeline

An end-to-end **Healthcare Data Engineering** project that demonstrates how to build a modern **ELT (Extract, Load, Transform) pipeline** using **SQL Server**, **SSIS**, and **Power BI**. 

### Project Overview

Healthcare organizations collect data from multiple systems such as patient registration, diagnosis records, laboratory results, and medication prescriptions. Because these datasets are stored separately, generating meaningful insights becomes difficult. This project demonstrates how to consolidate healthcare data into a centralized SQL Server Data Warehouse using an **ELT architecture**.

### Business Problem
A hospital wants to combine patient, diagnosis, laboratory, and medication data into a centralized data warehouse to answer clinical and operational questions.

### Solution

To address this challenge, this project implements a modern **Healthcare Patient Analytics ELT Pipeline** using SQL Server, SSIS, and Power BI.

The solution extracts data from multiple healthcare CSV files, loads the raw data into SQL Server staging tables, and performs all data cleansing, validation, and transformation within the database using T-SQL stored procedures. The transformed data is then modeled into a **Galaxy Schema (Fact Constellation Schema)** consisting of shared dimension tables and multiple fact tables for patient vitals, diagnoses, laboratory results, and medications.The resulting data warehouse provides a single source of truth for healthcare reporting, enabling fast and reliable analytics through SQL queries and interactive Power BI dashboards.


#### The hospital project uses the Medallion Architecture, which organizes data into three layers: Bronze, Silver, and Gold.

#### In the Bronze layer, we load our four raw CSV files: Patients.csv, Diagnoses.csv,
Medication.csv, and Lab.csv. At this stage, the data is stored exactly as it was received without any changes.

#### In the Silver layer, we clean and prepare the data. This includes removing duplicate records, handling missing values, standardizing date formats, validating Patient IDs, and joining the datasets using the PatientID so that each patients information is connected across diagnoses, medications, and lab results.

#### Finally, in the Gold layer, we create business-ready datasets for reporting and dashboards These include a patient summary, diagnosis analytics, medication analytics, laboratory analytics, and key performance indicators such as the total number of patients, the most common diagnoses, the most prescribed medications, and the number of lab tests performed.

#### This Medallion Architecture ensures that our data moves from raw data, to clean and reliable data, and finally to meaningful insights that support hospital decision-making.


#### Data Model

The project follows a **Galaxy Schema (Fact Constellation Schema)** design.

The data warehouse contains multiple fact tables that share common dimension tables, allowing different healthcare business processes to be analyzed while maintaining a consistent and scalable data model.

### Dimension Tables

Dimension tables store descriptive information used to filter, group, and analyze the fact data.

- ** dim_patient** – Patient demographic information.
- ** dim_date** – Calendar and time attributes.
- ** dim_diagnosis** – Diagnosis codes, names, and categories.
- ** dim_medication** – Medication names, drug classes, and manufacturers.
- ** dim_lab_test** – Laboratory test names and categories.
- ** dim_visit** – Stores visit-related information such as visit type (Inpatient, Outpatient, Emergency) and provider specialty (Cardiology, General Practice, Neurology, etc.).


### Fact Tables

Fact tables store measurable clinical and operational data and link to the dimension tables for reporting and analysis.

- **fact_vitals** – Stores patient vital sign measurements such as BMI, blood pressure, heart rate, and temperature.
- **fact_diagnosis** – Stores patient diagnosis events and links patients to diagnosis information.
- **fact_lab_results** – Stores laboratory test results, reference ranges, and abnormal result indicators.
- **fact_medication** – Stores prescribed medication details, dosage, duration, and adherence information.

### Hospital Data Pipeline – Medallion Architecture

This Healthcare Patient Analytics Data Warehouse follows the Medallion Architecture, which organizes data into three logical layers: Bronze, Silver, and Gold. This layered approach improves data quality, simplifies data management, and provides reliable datasets for reporting and analytics.

##### Bronze Layer (Raw Data)
The Bronze layer stores the raw data exactly as it is received from the source systems. No transformations or validations are performed at this stage.

###### The project loads the following CSV files into the Bronze layer:

- **Patients.csv**
- **Diagnoses.csv**
- **Medication.csv**
- **Lab.csv**
  
###### Staging Tables
- **stg_dim_patient**
- **stg_dim_diagnosis**
- **stg_dim_medication**
- **stg_dim_lab_results**
- **stg_dim_visit**
   
#### Silver Layer (Cleaned and Integrated Data)

The Silver layer transforms the raw data into clean, validated, and consistent datasets. During this stage, the data is prepared for analytical use by applying several data quality checks, including:

- Removing duplicate records
- Handling missing or invalid values
- tandardizing date formats
- alidating Patient IDs
- Cleaning inconsistent text values
 
##### Data Integration
Integrating patient information across all datasets using PatientID
- clean_dim_patient
- clean_dim_diagnosis
- clean_dim_medication
- clean_dim_lab_results
- clean_dim_visit

The Silver layer provides trusted, high-quality data for downstream processing.

#### Gold Layer (Business-Ready Data)
The Gold layer contains business-ready data used for reporting, dashboards, and analytics.
Example outputs include:
- dim_patienty
- dim_diagnosis
- dim_medication
- dim_lab_results
- dim_visit
- Also all fact tables

###### Key Performance Indicators (KPIs)
- Total Patients
- Total Diagnoses
- Total Medications Prescribed
- Total Laboratory Tests
- Average BMI
- Average Heart Rate
- Average Age
- Percentage of Abnormal Lab Results
These datasets can be consumed directly by reporting tools such as Power BI for interactive dashboards and business insights.

### Tools & Technologies:

- **SQL Server** – Used for database creation and query execution  
- **SSIS (SQL Server Integration Services)** – Used for ETL process (Extract, Transform, Load)  
- **draw.io** – Used for designing the Galaxy Schema diagram  
- **VS Code** – Used for code editing and project management  
- **Git Bash** -Used to run Git commands.
- **GitHub** -Used to host and manage the project repository.

  ### Skills Demonstrated

This project demonstrates practical experience with:

- SQL Server
- T-SQL (SQL Programming)
- SQL Server Integration Services (SSIS)
- ETL/ELT Pipeline Development
- Medallion Architecture (Bronze, Silver, Gold)
- Data Cleaning, Validation, and Transformation
- Galaxy Schema Data Modeling
- Fact and Dimension Table Design
- Data Warehousing
- Stored Procedures
- Incremental inserts
- Error Handling and Rejected Record Management
- Healthcare Data Analytics
- Power BI Dashboard Development
- Git & GitHub Version Control

