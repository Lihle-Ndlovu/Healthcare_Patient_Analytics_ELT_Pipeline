### Healthcare_Patient_Analytics_ELT_Pipeline
An end-to-end **Healthcare Data Engineering** project that demonstrates how to build a modern **ELT (Extract, Load, Transform) pipeline** using **SQL Server**, **SSIS**, and **Power BI**.  


#### The hospital project uses the Medallion Architecture, which organizes data into three layers:
Bronze, Silver, and Gold.

#### In the Bronze layer, we load our four raw CSV files: Patients.csv, Diagnoses.csv,
Medication.csv, and Lab.csv. At this stage, the data is stored exactly as it was received without any changes.

#### In the Silver layer, we clean and prepare the data. This includes removing duplicate records, handling missing values, standardizing date formats, validating Patient IDs, and joining the datasets using the PatientID so that each patients information is connected across diagnoses, medications, and lab results.

#### Finally, in the Gold layer, we create business-ready datasets for reporting and dashboards These include a patient summary, diagnosis analytics, medication analytics, laboratory analytics, and key performance indicators such as the total number of patients, the most common diagnoses, the most prescribed medications, and the number of lab tests performed.

#### This Medallion Architecture ensures that our data moves from raw data, to clean and reliable
data, and finally to meaningful insights that support hospital decision-making.

### Project Overview

Healthcare organizations collect data from multiple systems such as patient registration, diagnosis records, laboratory results, and medication prescriptions. Because these datasets are stored separately, generating meaningful insights becomes difficult. This project demonstrates how to consolidate healthcare data into a centralized SQL Server Data Warehouse using an **ELT architecture**.

### Business Problem
A hospital wants to combine patient, diagnosis, laboratory, and medication data into a centralized data warehouse to answer clinical and operational questions.

### Hospital Data Pipeline – Medallion Architecture

This Healthcare Patient Analytics Data Warehouse follows the Medallion Architecture, which organizes data into three logical layers: Bronze, Silver, and Gold. This layered approach improves data quality, simplifies data management, and provides reliable datasets for reporting and analytics.

##### Bronze Layer (Raw Data)

The Bronze layer stores the raw data exactly as it is received from the source systems. No transformations or validations are performed at this stage.

The project loads the following CSV files into the Bronze layer:

**- Patients.csv
**- Diagnoses.csv
**- Medication.csv
**- Lab.csv
### Staging Tables

**- stg_dim_patient
**- stg_dim_diagnosis
**- stg_dim_medication
**- stg_dim_lab_results
**- stg_dim_visit
#### Silver Layer
The Silver layer cleans, validates, and integrates the data.

KSilver Layer (Cleaned and Integrated Data)

The Silver layer transforms the raw data into clean, validated, and consistent datasets. During this stage, the data is prepared for analytical use by applying several data quality checks, including:

**-Removing duplicate records
**-Handling missing or invalid values
**-Standardizing date formats
**-Validating Patient IDs
**-Cleaning inconsistent text values
##### Data Integration
**-Integrating patient information across all datasets using PatientID

**- clean_dim_patient
**- clean_dim_diagnosis
**- clean_dim_medication
**- clean_dim_lab_results
**- clean_dim_visit

The Silver layer provides trusted, high-quality data for downstream processing.

##### Gold Layer (Business-Ready Data)
The Gold layer contains business-ready data used for reporting, dashboards, and analytics.
Example outputs include:
**- dim_patienty
**- dim_diagnosis
**- dim_medication
**- dim_lab_results
**-dim_visit
####  Fact Table
**- fact_vitals
**- fact_diagnosis
**- fact_lab_results
**- fact_medication

##### Key Performance Indicators (KPIs)
**-Total Patients
**-Total Diagnoses
**-Total Medications Prescribed
**-Total Laboratory Tests
**-Average BMI
**-Average Heart Rate
**-Average Age
**-Percentage of Abnormal Lab Results
These datasets can be consumed directly by reporting tools such as Power BI for interactive dashboards and business insights.

#### Technology Stack

- SQL Server
- SQL Server Management Studio (SSMS)
- SQL Server Integration Services (SSIS)
- T-SQL
- Power BI
- Git
- GitHub
