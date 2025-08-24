# Excel Salary Dashboard

![Dashboard_gif](https://github.com/user-attachments/assets/d1bd5e62-6596-47b7-b1c9-21ae7ac9947c)


## Introduction

This dashboard was created to investigate salaries for various Data Science jobs across countries. 

The data is from Luke Barousse's Excel course, which provides a foundation in analyzing data using this powerful tool. The data contains crucial information on job titles, salaries, locations, and essential skills that are presented here.

### Dashboard File
My final dashboard is in [Salary_Dashboard.xlsx](Salary_Dashboard.xlsx).

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **Charts**
- **Formulas and Functions**
- **Data Validation**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. The dataset is available via my Excel course, which provides a foundation for analyzing data using Excel. It includes detailed information on:

- **Job titles**
- **Salaries**
- **Locations**
- **Skills**

## Dashboard Build

###  Charts

#### Data Science Job Salaries - Bar Chart

<img width="535" height="313" alt="dashboard_1" src="https://github.com/user-attachments/assets/437bd155-5eaa-4648-8d67-7da46e524938" />

-  **Excel Features:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
-  **Design Choice:** Horizontal bar chart for visual comparison of median salaries.
-  **Data Organization:** Sorted job titles by descending salary for improved readability.
-  **Insights Gained:** This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

#### Country Median Salaries - Map Chart

<img width="635" height="344" alt="dashboard_2" src="https://github.com/user-attachments/assets/ec969184-67a6-4f90-b7dd-d19dfafe5fb1" />


-  **Excel Features:** Utilized Excel's map chart feature to plot median salaries globally.
-  **Design Choice:** Color-coded map to visually differentiate salary levels across regions.
-  **Data Representation:** Plotted median salary for each country with available data.
-  **Visual Enhancement:** Improved readability and immediate understanding of geographic salary trends.
-  **Insights Gained:** Enables quick grasp of global salary disparities and highlights high/low salary regions.

###  Formulas and Functions

####  Median Salary by Job Titles

```
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```

-  **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
-  **Array Formula:** Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.
-  **Tailored Insights:** Provides specific salary information for job titles, regions, and schedule types.
-  **Formula Purpose:** This formula populates the table below, returning the median salary based on job title, country, and type specified.

 Background Table

<img width="319" height="263" alt="dashboard_3" src="https://github.com/user-attachments/assets/5c98b99e-c218-44d2-aa4a-02f6d6d692db" />


 Dashboard Implementation

<img width="552" height="710" alt="dashboard_4" src="https://github.com/user-attachments/assets/e50ed59b-6dfd-4944-807b-a1e7814e9890" />

####  Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

-  **Unique List Generation:** This Excel formula below employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.
-  **Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule types.

 Background Table

<img width="241" height="154" alt="dashboard_5" src="https://github.com/user-attachments/assets/a3c3a695-8c9c-43a5-9cae-098b129035eb" />  


 Dashboard Implementation:

<img width="624" height="708" alt="dashboard_6" src="https://github.com/user-attachments/assets/b8c2f094-e664-4d7b-b046-8c40410afdce" />

###  Data Validation

####  Filtered List

-  **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    -  User input is restricted to predefined, validated schedule types
    -  Incorrect or inconsistent entries are prevented
    -  Overall usability of the dashboard is enhanced

![dashboard_gif2](https://github.com/user-attachments/assets/5cadea60-15be-4ac5-8cb4-acb93fa4eb10)

## Conclusion

I created this dashboard to showcase insights into salary trends across various data-related job titles. Utilizing data from Luke Barousse's Excel course, this dashboard allows users to make informed decisions about their career paths. Exploring the functionalities to understand how location and job type influence salaries. 
