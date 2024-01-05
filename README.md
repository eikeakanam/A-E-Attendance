# Monthly A & E Attendances and Emergency Admissions Report
## Presented by: Ekene Christian Ikeakanam
___
## INTRODUCTION AND PROBLEM STATEMENT
___
The availability and accuracy of A&E Attendances and Emergency Admissions data is of utmost importance to the NHS, Government and major healthcare stakeholders within the United Kingdom. 
Timely and efficient analytics of these data provide critical insights into the dynamics of emergency healthcare utilization, helping healthcare professionals make informed decisions, allocate resources efficiently, and enhance the overall quality of patient care.

Having previously visited and benefited from the good works of the professional staff at the A & E arm of the NHS late last year and experienced first habd what was obtainable at the department, I decided to embark on this project to obtain useful information about A&E services and its overall impact on the healthcare sector in the UK. The project is setout to answer the following questions
In line with the mayor's long term strategy, This project was embarked upon to investigate the following observations and more:
- Identify patterns and trends in monthly A&E attendances and admissions over time.
- Analyze if there are seasonal variations in A&E attendances and admissions.
- Identify the most common reasons for A&E attendances.
- Analyze average waiting times for A&E services across various types / categories.
-Evaluate performance against set benchmark for A&E attendance and admission and processing time rates.
- Investigate the impact of external factors such as major pandemics on A&E attendance
- Compare current A&E attendance and admission rates with historical data to identify trends or anomalies.

## Dataset and Source of Data
___
The Monthly A&E Attendances and Emergency Admissions dataset is provided by The NHS, England and accessible at [A&E Attendance Dataset](https://www.england.nhs.uk/statistics/statistical-work-areas/ae-waiting-times-and-activity/). It consists of an aggregation of the total number of attendances over the period August 2010 - November 2023 and comprises of records for all A&E types, including Urgent Treatment Centres, Minor Injury Units and Walk-in Centres, as well as the number of patients admitted, discharged or transferred within four hours of arrival.

Additionally, the dataset contains information on emergency admissions, performance metrics, admission processing times, and booked attendances.

The dataset is contained within a single Excel file, comprising three distinct tables or sheets:

- **Activities:**
This table aggregates A&E attendances and emergency admissions across all three types (Type 1-3). Key fields encompass details about periods, records of attendance across major A&E departments, and performance values measured by various time metrics.

- **Performance:**
This table encompasses data related to waiting and processing times, tracking the duration from a patient's arrival to admission, transfer, or discharge.

- **Booking:**
This table contains records of attendances booked prior to A&E visits, along with corresponding performance metrics measuring the time from arrival to admission, transfer, or discharge.

Common fields, consistent across all three tables, include Period, records of attendance across the three major A&E departments (Type 1-3), and performance values utilizing diverse time metrics.

## Demonstrated Skills
___

## 1. Data Gathering and Preparation

### Import Datasets
The dataset, saved on an excel file was imported using the Get Data feature in Power BI desktop thereafter, all three required tables were selected and loaded onto Power Query editor for transformation. This was done using the import storage mode as there wouldnt be any need for data refreshes and loaded to the Power Query editor.

### Merging of Tables
The 'Activity" and "Performance" tables were merged as a new query using the Period column as the key identifier and disabled query load of the existing table. Upon successful merger of both tables, was left with two distinct fact tables "Activity" and "Booking".

### Data Cleaning and Transformation: 
Several data transformation procedures were applied to enhance the quality of the dataset, including:
- Identification and removal of unwanted columns to minimize the model size
- Rename columns and update data types as required
- Creation of additional columns: Season (Summer, Winter, Autumn or Spring) using the Period column. This was added to investigate the impact of weather conditions or seasons on the A&E attendance and admissions
- Cleaning of data by dealing with missing / null values, removal of duplicates and ensured only valid records were added to the model.
- Checked the quality and distribution of data using Column Quality, Profile and Distribution feature in Power Query Editor.

## 2. Data Modelling

The data modeling process involved several key steps to structure and relate the fact tables ("Activity" and "Booking") and the dimension table (Date). Here's a concise overview:

**Fact Table Modeling (Activity and Booking):**

- Column Selection:
Identified and selected relevant columns from the "Activity" and "Booking" tables to include in the model.
- Data Type Optimization:
Ensured that data types were appropriate for each column, optimizing for accuracy and efficiency.
- Naming and Renaming:
Applied clear and concise naming conventions to enhance model readability.
Renamed columns as needed for consistency and user-friendliness.

**Dimension Table Creation (Date):**
- Date Table Generation:
Created a dedicated Date table to serve as a dimension in the model, containing a comprehensive range of dates covering the dataset period.
- Date Hierarchy Establishment:
Established a date hierarchy within the Date table to facilitate time-based analyses and visualizations.

**Relationship Establishment:**

- Key Identification:
Identified the common key between tables, which was the Period column, representing the time dimension.
- Relationship Creation:
Established relationships between the fact tables ("Activity" and "Booking") and the Date table using the Period column as the primary key.
- Referential Integrity:
Ensured referential integrity by configuring relationships to properly reflect the associations between the tables.
Bidirectional Cross-Filtering:
- Configured bidirectional cross-filtering where necessary to enable seamless navigation and analysis across related tables.

By systematically applying these data modeling steps, the resulting model provided a foundation for robust analysis, efficient queries, and meaningful visualizations, required to derive actionable insights from the dataset.

## 3. ANALYSIS AND VISUALIZATION

The A&E Monthly Attendances and Emergency project comprises four insightful reports: Aggregation, Emergency, Performance, and Booking.

A pictorial overview of both reports is displayed below:
|Aggregation|Booking|
|----------|--------------|
|![AE Activity](https://github.com/eikeakanam/A-E-Attendance/assets/75729930/4d581b4c-defa-482f-b9b2-817592e1ae15)|![A&E Booking](https://github.com/eikeakanam/A-E-Attendance/assets/75729930/63ad65df-2b58-457f-9378-b73d246b8297)|

|Performance|Emergency|
|----------|--------------|
|![AE Performance](https://github.com/eikeakanam/A-E-Attendance/assets/75729930/a7223743-c73f-4c60-b630-4b6f96c5ce0e)|!![A E EMergency](https://github.com/eikeakanam/A-E-Attendance/assets/75729930/194cf571-621c-4a4a-b1fc-91515b2d6942)|


**Aggregation Report:**
The Aggregation report offers a comprehensive analysis of total monthly attendance and emergency admissions trends across all NHS regions and providers in England from August 2010 to November 2023. Key performance indicators (KPIs) provide stakeholders with valuable insights for informed decision-making.

**Key Insights:**

- The total number of A&E attendances from January 2023 to November 2023 is 23,389,390, indicating a 2.2% increase compared to the same period in the previous year 2022.
- The current month, November 2023 witnessed a total attendance of 2,162,122, showing a 2.59% decline from the previous month, October 2023 and a 0.77% decline compared to the same month last year, November 2022.
  
  ![Activity KPI](https://github.com/eikeakanam/A-E-Attendance/assets/75729930/a867e22f-1e33-4706-836f-ac750019f873)
  
- The annual growth rate for A&E attendances across all departments is 8.8% from 2010 - 2023, with an average monthly attendance of 1,912,604. November 2023 experienced a 13% increase compared to the average monthly  attendance.
- Similar to the previous year (2022), the lowest attendance occurred in February 2023, while December and May recorded the highest attendances in both years respectively.

  ![Activity 1](https://github.com/eikeakanam/A-E-Attendance/assets/75729930/99d3c62f-80f0-4e3d-aee2-ca07e2420376)

- Type 1 attendances accounted for 63% of total A&E visits in the year 2023, representing a 3% decline over the same period in the previous year.
- Total Type 1 attendances for November 2023 were 1,385,701, indicating a 1.97% decrease from October 2023 and a 0.68% decline compared to November 2022.
- Seasonal variations show minimal differences, with Autumn slightly leading at 25.49%, closely followed by Summer at 25.39%.
  
![Activity 2](https://github.com/eikeakanam/A-E-Attendance/assets/75729930/fd123a3c-62a4-4f62-910f-d18dfde073db)


Performance Report:
The Performance report provides detailed insights into the number, percentage, and trends of patients admitted, transferred, or discharged within or beyond the four-hour benchmark period from patients' arrival time.

Booking Report:
The Booking report offers detailed information and analytics on all booked attendances and relevant performance metrics.

These reports collectively empower stakeholders with valuable information for strategic decision-making and further analytics.
