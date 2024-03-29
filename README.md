# Monthly A & E Attendances and Emergency Admissions Report
## Presented by: Ekene Christian Ikeakanam
___
## INTRODUCTION AND PROBLEM STATEMENT
___

![_127932691_photo08-12-2022104927](https://github.com/eikeakanam/A-E-Attendance/assets/75729930/44077a56-a6b9-4d90-98b5-9a4d119c5b6c)

The availability and accuracy of A&E Attendances and Emergency Admissions data is of utmost importance to the NHS, Government and major healthcare stakeholders within the United Kingdom. 
Timely and efficient analytics of these data provide critical insights into the dynamics of emergency healthcare utilization, helping healthcare professionals make informed decisions, allocate resources efficiently, and enhance the overall quality of patient care.

Having previously visited and benefited from the good works of the professional staff at the A & E arm of the NHS late last year and experienced first habd what was obtainable at the department, I decided to embark on this project to obtain useful information about A&E services and its overall impact on the healthcare sector in the UK. The project is setout to answer the following questions
- Identify patterns and trends in monthly A&E attendances and admissions over time.
- Analyze if there are seasonal variations in A&E attendances and admissions.
- Identify the most common reasons for A&E attendances.
- Analyze average waiting times for A&E services across various types / categories.
- Evaluate performance against set benchmark for A&E attendance and admission and processing time rates.
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

![modell](https://github.com/eikeakanam/A-E-Attendance/assets/75729930/b8a8d95d-571c-4de2-bbb7-5260b863a9b8)

## 3. ANALYSIS AND VISUALIZATION

The A&E Monthly Attendances and Emergency project comprises four insightful reports: Attendance, Emergency, Performance, and Booking.

A pictorial overview of both reports is displayed below:
|Attendance|Booking|
|----------|--------------|
|![AE Activity](https://github.com/eikeakanam/A-E-Attendance/assets/75729930/4d581b4c-defa-482f-b9b2-817592e1ae15)|![A&E Booking](https://github.com/eikeakanam/A-E-Attendance/assets/75729930/63ad65df-2b58-457f-9378-b73d246b8297)|

|Performance|Emergency|
|----------|--------------|
|![AE Performance](https://github.com/eikeakanam/A-E-Attendance/assets/75729930/a7223743-c73f-4c60-b630-4b6f96c5ce0e)|![Emergencyy](https://github.com/eikeakanam/A-E-Attendance/assets/75729930/95a19462-e826-4810-a057-2701e59e2042)|

### LINK TO DETAILED POWER BI REPORT >>> [A&E ATTENDANCES REPORT](https://app.powerbi.com/groups/me/reports/db2fcf57-2b48-4030-a49f-5138290ed862?ctid=ac5ac3e2-e369-4329-952c-a36e8474e997&pbi_source=linkShare&bookmarkGuid=5618445d-2970-4f79-9868-3dea1e9cbcb4)
___

**ATTENDANCE REPORT**
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

**PERFORMANCE REPORT**
The Performance report provides detailed insights into the number, percentage, and trends of patients admitted, transferred, or discharged within or beyond the four-hour benchmark period from patients' arrival time.

**Key Insights**
- **Total Discharged, Transferred, or Admitted Attendances (Jan - Nov 2023):**
The cumulative number of attendances discharged, transferred, or admitted between January and November 2023 (YTD) stands at 16,114,039. This reflects an approximate 10.2% increase compared to the corresponding period last year.

- **Monthly Performance (November 2023):**
In November 2023, a total of 1,508,000 patients were discharged, transferred, or admitted. This marks a 3.3% decline from the previous month (October 2023) and a 12.5% increase compared to November 2022.

![pm 1](https://github.com/eikeakanam/A-E-Attendance/assets/75729930/2b1cef76-b1d6-4d39-a26d-12d209a7c37f)

- **Delayed Attendances (November 2023):**
Notably, 654,122 attendances experienced delays in being discharged, transferred, or admitted after 4 hours in November 2023. This represents a 0.95% decline from October 2023 and an 8.6% increase compared to November 2022.

- **Performance Trends (Type 1, Type 2, and Type 3 Attendances):**
Performance for Type 2 and 3 attendances has consistently remained above the 90% mark. However, there has been a notable decline in performance for Type 1 attendances over the past 5 years.

- **Type 1 Performance (November 2023):**
In November 2023, only 55% of Type 1 attendances were discharged, transferred, or admitted within 4 hours. This represents a 1% decrease compared to the previous month (October 2023).

- **Overall Performance (November 2023):**
The overall performance for November 2023 is 60.9%, reflecting a 0.7% decline compared to November 2022 and a 0.5% decrease compared to the previous month (October 2023).

- **Annual Performance Averages (Jan - Nov 2023):**
Throughout the calendar year (January - November 2023), the average performance rating for Type 1 attendances was 58%, while the overall performance (inclusive of Type 2 and 3) currently stands at approximately 73%. Both figures fall considerably short of the 95% benchmark performance rate.

![pm 2](https://github.com/eikeakanam/A-E-Attendance/assets/75729930/08d98b12-dd15-4c51-b82a-7a239fc7a18c)

![pm 3](https://github.com/eikeakanam/A-E-Attendance/assets/75729930/40e141b8-6b6a-457b-8a0c-c39242de202c)

**BOOKING REPORT**
The Booking report offers detailed information and analytics on all booked attendances and relevant performance metrics.

- **Total Booked Attendances (Current Period):**
As of this report, the total booked attendances stand at 2,598,252, showing a remarkable annual growth rate of 42.2%.

![bk1](https://github.com/eikeakanam/A-E-Attendance/assets/75729930/b1d31611-934d-45f3-b657-6984e6f3db5e)

- **Annual Performance Growth (2023 vs. 2022):**
The total booked attendances for the current year (2023) reached 770,701, indicating a 2.5% increase compared to the same period in the previous year, 2022.

- **Monthly Booked Attendances (November 2023):**
Booked attendances for November 2023 totaled 71,557, reflecting a 0.5% increase compared to October 2023 and a substantial 4.31% increase compared to November 2022.

- **Performance Trends (November 2023):**
The overall performance for November 2023 is reported at 87.27%, which is 0.49% less than the previous month (October 2023) but represents a 0.24% increase compared to November 2022.

![bk2](https://github.com/eikeakanam/A-E-Attendance/assets/75729930/ec77403f-7d4c-4b93-abd5-96581f054a85)

- **Average Overall Performance (Jan - Nov 2023):**
The average overall performance rating for booked attendances in the current year (January - November 2023) is 89.4%, reflecting a 1.2% increase compared to the previous year, 2022. However, this figure still falls short of the 95% benchmark set for attendances.

- **Type Distribution (2023):**
Over 57% of booked attendances in the year 2023 were attributed to Type 3, while Type 1 accounted for approximately 42% of booked appearances.

![bk3](https://github.com/eikeakanam/A-E-Attendance/assets/75729930/8ebe408e-05a5-4101-9166-ec00e2cfef96)

**EMERGENCY REPORT:**
THE emergency report provides detailed information about emergency admissions via A and E and Others as well as the recorded performances in processing admissions within the admissible timeframe.

**Key Insights**

- **Total Emergency Admissions (Jan - Nov 2023):**
The total number of emergency admissions for the current year is 5,732,146, reflecting a notable 5.0% increase compared to the same period in the previous year, 2022.

![em1](https://github.com/eikeakanam/A-E-Attendance/assets/75729930/2686043d-b207-442a-9261-c66ead1202e0)

- **Admission Distribution (Jan - Nov 2023):**
Of the total admissions in the year (January - November 2023), approximately 74% (4,247,879) were admissions via A&E, while the remaining 26% were admissions not conducted via A&E.

- **Type 1 Emergency Admissions (2023):**
Type 1 Emergency admissions account for about 73% of the total admissions in the year 2023.

![em3](https://github.com/eikeakanam/A-E-Attendance/assets/75729930/1ef8d748-7a34-4bb0-a09e-f8bc282d5115)

- **Monthly Emergency Admissions (November 2023):**
Total emergency admissions for November 2023 reached 545,636, indicating a slight 0.36% decrease compared to the previous month (October 2023) and a significant 5.8% increase compared to the total admissions in November 2022. 
Additionally, the emergency admissions for November 2023 are approximately 14% higher than the average monthly emergency admissions (478,440) recorded over the period.

- **Admission Timing Trends (2023 vs. 2022):**
About 79% of patients were admitted within approximately 4 hours following the decision to admit, while 21% were admitted over 12 hours after the decision to admit in the year 2023. This contrasts with the previous year, 2022, where approximately 82% of patients were admitted within the first four hours following the decision to admit.

![EM2](https://github.com/eikeakanam/A-E-Attendance/assets/75729930/c028d474-d62e-471e-8b25-6e1f64a5f852)


## 4. Publish Report and Creation of Dashboard
___
The A&E Attendance and Admissions report was initially developed in Power BI Desktop and later published to my Workspace on Power BI Service. 

Following this, a dashboard was created within my Power BI Service workspace, by pinning visuals from the report

## 5. Conclusion and Recommendation
___

Based on the insights gathered from the A&E Attendance and Admissions report, here are some possible recommendations:

- **Performance Improvement for Type 1 Attendances:**
Given the consistent decline in performance for Type 1 attendances over the last five years, it is advisable to implement strategies aimed at improving processing times and ensuring a higher percentage of Type 1 attendances are admitted, transferred, or discharged within the four-hour benchmark.

- **Enhanced Resource Allocation:**
Considering the significant increase in overall attendances and emergency admissions, there may be a need for reassessing and potentially increasing resource allocations, particularly staffing and facilities, to manage the higher demand effectively.

- **Targeted Improvement for Type 2 and 3 Attendances:**
While Type 2 and 3 attendances have maintained performance levels above the 90% mark, continual efforts should be made to sustain and potentially improve these high-performance rates.

- **Continuous Monitoring and Adaptation:**
Regularly monitor performance metrics, emergency admissions, and attendance trends. Implement an agile approach to adapt strategies based on changing circumstances, ensuring the healthcare system remains responsive and effective.
