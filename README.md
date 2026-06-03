# Covid 19 Global Time Series Analysis
## Description
This project analyses global COVID-19 data using Microsoft Power BI to understand how confirmed cases evolved across countries and over time. The analysis focuses on identifying trends in case growth, geographic spread, and the distribution of confirmed cases, recoveries, and deaths across different time periods.

## Objective
The objective of this analysis is to explore global COVID-19 trends and evaluate how confirmed cases changed across months, quarters, and years to better understand the progression of the pandemic.

## Business Questions
The analysis was guided by the following questions:
1. What is the total number of reported COVID-19 cases in the dataset?
2. How do case counts vary across months and years?
3. How are cases distributed across different quarters of the year?
4. Which locations recorded the highest concentration of reported cases?
5. How are cases distributed across confirmed cases, recoveries, and deaths?

## Dataset Overview
The dataset used in this project consists of three global COVID-19 time series datasets obtained from COVID-19 GitHub repository. The datasets track daily reported cases across multiple countries and regions worldwide.
### Dataset Structure (Before Transformation)
Confirmed Cases
** Total Rows:** 289
** Total Columns:**1147
Recovered Cases 
** Total Rows:** 274 
** Total Columns:**1147 
Death Cases 
** Total Rows:** 288
** Total Columns:**1147

Each dataset contains the following columns:
Province/State, Country/Region, Latitude, Longitude, Date Columns; the date column datasets are stored in a **wide time series format**, where each date appears as a separate column representing the number of reported cases for that day.

### Dataset Structure (After Transformation)
During the data preparation stage in Power BI, the date columns were **unpivoted** using Power Query to convert the dataset into a **long format**, making it suitable for time series analysis and visualization.
After transformation, the dataset was structured into the following fields:
Location, Date, Cases, Status; Case Category (Confirmed, Recovered, or Deaths)

## Data Source
Confirmed Cases  
https://raw.githubusercontent.com/CSSEGISandData/COVID-19/master/csse_covid_19_data/csse_covid_19_time_series/time_series_covid19_confirmed_global.csv

Recovered Cases  
https://raw.githubusercontent.com/CSSEGISandData/COVID-19/master/csse_covid_19_data/csse_covid_19_time_series/time_series_covid19_recovered_global.csv

Death Cases  
https://raw.githubusercontent.com/CSSEGISandData/COVID-19/master/csse_covid_19_data/csse_covid_19_time_series/time_series_covid19_deaths_global.csv

GitHub Repository  
https://github.com/CSSEGISandData/COVID-19/tree/master/csse_covid_19_data/csse_covid_19_time_series

## Tools Used
Microsoft Power BI
- Power Query
- Data Transformation
- Data Modelling
- Time Series Visualization
- Dashboard Design

## Data Preparation
Four queries were created during the data preparation stage.
- Confirmed Query
Final columns: Location, Date, Cases, Status (Confirmed)
- Recovered Query
Final columns: Location, Date, Cases, Status (Recovered)
- Death Query
Final columns: Location, Date, Cases, Status (Deaths)
- Location Query
Columns include: Province/State, Country/Region, Latitude, Longitude
- Consolidated Query
This table was created by appending the Confirmed, Recovered, and Death queries.  
The consolidated table contains: Location, Date, Cases, Status.
- Date Table 
A Date table was created using **DAX** to support time based analysis in the dashboard. 
The following fields were derived from the Date column: Date, Year, Quarter, Month  
- Duplicate rows were removed from the Location table to ensure each location appears only once.

## Data Profiling
Data profiling was applied in Power Query to validate the dataset and ensure data quality.
Profiling steps included:
- Reviewing column distributions
- Identifying null values
- Verifying numeric formatting for case counts
- Validating date formats
- Reviewing distinct counts for location fields

## Dashboard
The Power BI dashboard provides an overview of global COVID-19 trends through the following visualizations:
- Total Number of Cases
- Total Number of Cases by Quarter
- Total Number of Cases by Month and Year
- Cases Distribution by Status
- Geographic Distribution of Cases by Location
<img width="1116" height="654" alt="image" src="https://github.com/user-attachments/assets/431dd910-d529-4216-b7c5-64a9f49d3d9a" />

## Key Insights
- The dataset records approximately **345bn** total reported cases, representing the combined total of confirmed cases **317bn**, recoveries **23bn**, and deaths **4bn** within the consolidated dataset.
- Case counts vary across different months and years, highlighting changes in pandemic trends over time.
- Geographic visualization shows cases recorded across multiple continents including North America, Europe, Asia, Africa, and Australia.
- Confirmed cases **317bn** represent the largest portion of reported cases, followed by recoveries **23bn** and deaths **4bn**.

## Recommendation
- Extend the analysis to compare trends across individual countries and regions. 
- Monitor case trends over time to identify periods of accelerated growth or decline. 
- Incorporate additional health indicators such as vaccination and testing data to provide broader context. 
- Perform separate analysis of confirmed, recovered, and death cases to better understand changes over time. 
- Continue updating the dataset to maintain the relevance of trend analysis.

## Conclusion
The analysis demonstrates how Power BI can transform raw time series data into a structured analytical dataset. By consolidating confirmed, recovered, and death records into a unified table, the dashboard provides insights into global COVID-19 trends across time and geographic locations.

