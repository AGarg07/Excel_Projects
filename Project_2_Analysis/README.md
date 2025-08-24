
# Project 2 Analysis

## Introduction

As an early-career seeker, I’ve always been surprised by the lack of data exploring the most optimal jobs and skills in the data science market. I set out to understand what skills top employers request and how to land more pay.

### Questions to Analyze

To understand the data science job market, I asked the following:

1. **Do more skills get you better pay?**
2. **What is the remuneration for data science jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What is the pay for the top 10 skills?**

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **Pivot Tables**
- **Pivot Charts**
- **DAX (Data Analysis Expressions)**
- **Power Query**
- **Power Pivot**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. The dataset is available via Luke Barousse's Excel course.

It includes detailed information on:

- **Job titles**
- **Salaries**
- **Locations**
- **Skills**

## 1️⃣ Do more skills get you better pay?

### Skill: Power Query (ETL)

####  Extract

- I first used Power Query to extract the original data (`data_salary_all.xlsx`) and create two queries:
    -  First one with all the data jobs information.
    -  The second listing the skills for each job ID.

####  Transform

- Then, I transformed each query by changing column types, removing unnecessary columns, cleaning text to eliminate specific words, and trimming excess whitespace.
    -  data_jobs_salary

        <img width="274" height="410" alt="analysis_1" src="https://github.com/user-attachments/assets/23fff97a-3717-431d-8ed5-32fd494a678d" />

    -  data_job_skills

       <img width="277" height="397" alt="analysis_2" src="https://github.com/user-attachments/assets/c81531dc-fd0a-41b4-a3fd-5901976b8dc2" />

####  Load

- Finally, I loaded both transformed queries into the workbook, setting the foundation for my subsequent analysis.
    -  data_jobs_salary

        <img width="1906" height="880" alt="analysis_3" src="https://github.com/user-attachments/assets/2f7e2fba-567a-44ee-9344-b8334b0ec46b" />

    -  data_job_skills

       <img width="1901" height="848" alt="analysis_4" src="https://github.com/user-attachments/assets/2f17fce4-bbed-4f86-bd93-0f469d3b2606" />

###  Analysis

####  Insights

- There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
- Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.


  <img width="740" height="430" alt="salary_analysis" src="https://github.com/user-attachments/assets/54c736b7-6271-4252-abae-7a495461c19e" />

    
####  

- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.

## 2️ What’s the salary for data jobs in different regions?

###  Skills: PivotTables & DAX

#### Pivot Table

-  I created a PivotTable using the Data Model I created with Power Pivot.
-  I moved the `job_title_short` to the rows area and `salary_year_avg` into the values area.
-  Then I added new measure to calculate the median salary for United States jobs.
    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```

####  DAX

- To calculate the median year salary I used DAX.

    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

###  Analysis

####  Insights

- Job roles like Data Engineer and Data Scientist command higher median salaries both in India and internationally, showcasing the global demand for high-level data expertise.
- The salary disparity between Indian and Non-Indian roles is particularly notable in high-tech jobs, which might be influenced by a lack of tech industries in India.

    <img width="979" height="368" alt="analysis_5" src="https://github.com/user-attachments/assets/1f3f0946-bc2e-4dbb-8ce0-aefdf00ea3df" />




- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.

## 3️⃣ What are the top skills of data professionals?

###  Skill: Power Pivot

####  Power Pivot

- I created a data model by integrating the `data_jobs_all` and `data_jobs_skills` tables into one model.
- Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

####  Data Model

- I created a relationship between my two tables using the `job_id` column.

  <img width="698" height="821" alt="analysis_6" src="https://github.com/user-attachments/assets/ad396972-e8b9-4615-ab69-8bcaba88c139" />


#### 📃 Power Pivot Menu

- The Power Pivot menu was used to refine my data model and makes it easy to create measures.


  <img width="1859" height="667" alt="analysis_7" src="https://github.com/user-attachments/assets/b5d1e578-eab3-4cfc-9d00-6b7331b11e09" />

   
### Analysis

#### Insights

-  SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
-  Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.

   <img width="592" height="351" alt="analysis_8" src="https://github.com/user-attachments/assets/128245e2-32f4-47ba-b0c2-d2f062c080e0" />




- Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides training and educational programs to focus on the most impactful technologies.

## 4️⃣ What’s the pay of the top 10 skills?

###  Skill: Advanced Charts (Pivot Chart)

####  PivotChart

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
    -  **Primary Axis:** Median Salary (as a Clustered Column)
    -  **Secondary Axis:** Skill Likelihood (as a Line with Markers)
- To customize the chart, I added a title axis title, removed the lines (skill likelihood), and changed the markers to diamonds.

###  Analysis

#### Insights

-  Higher median salaries are associated with skills like Python, Oracle, and SQL, suggesting their critical role in high-paying tech jobs.
-  Spark has the highest median salaries and lowest likelihood, indicating specialization and demand in high-salary sectors.

    <img width="888" height="468" alt="analysis_9" src="https://github.com/user-attachments/assets/b45b3309-6501-4b3b-9228-15782fadde00" />



- This chart highlights the importance of investing time in learning high-value skills like Python and SQL, which are evidently tied to higher paying roles, especially for those looking to maximize their salary in the tech industry.

## Conclusion

I created this Excel dashboard as a way to combine my passion for data analysis with a deep dive into the data science job market. Using a curated dataset of real-world job postings, I explored job titles, salaries, locations, and the skills most closely associated with higher-paying roles. By leveraging Excel’s advanced capabilities—including Power Query, PivotTables, DAX, and dynamic visualizations—I uncovered clear correlations, showing that professionals skilled in Python, SQL, and cloud technologies consistently earn higher salaries.

This project not only provided valuable insights into market trends but also served as a hands-on demonstration of my ability to design and build data-driven dashboards in Excel. It highlights my skills in transforming raw data into meaningful insights through clean design, automation, and interactivity. Data was sourced from [datanerd.tech](https://datanerd.tech/).

By leveraging Power Query, PivotTables, DAX, and dynamic charts, the dashboard reveals clear correlations between technical proficiency and higher salary brackets, with Python, SQL, and cloud technologies emerging as key drivers of compensation.

This repository is intended as a practical resource for data professionals and a portfolio project showcasing Excel’s capabilities for interactive, data-driven insights.
