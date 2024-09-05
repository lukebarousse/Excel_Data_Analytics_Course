# Project 1 - Salary Dashboard

## Introduction

My data jobs salary dashboard was created to help people investigate salaries for their desired job title. The data is from Luke Barousse's Excel Course which provides a foundation for my analysis and Excel skills. It contains detailed information on job titles, salaries, locations, and essential skills. I used the following Excel skills:

- Charts
- Formulas and Functions
- Data Validation

## Final Dashboard

Below is my final dashboard.

![1_Salary_Dashboard.png](/0_Resources/Images/1_Salary_Dashboard.png)

## Elements of the Dashboard

### Charts

#### 📊 Bar Chart:

- 🛠️ **Excel Features:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
- 🎨 **Design Choice:** Horizontal bar chart for visual comparison of median salaries.
- 📉 **Data Organization:** Sorted job titles by descending salary for improved readability.
- 💡 **Insights Gained: This e**nables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

    ![1_Salary_Dashboard_Chart1.png](/0_Resources/Images/1_Salary_Dashboard_Chart1.png)

#### 🗺️ Map Chart

- 🛠️ **Excel Features:** Utilized Excel's map chart feature to plot median salaries globally.
- 🎨 **Design Choice:** Color-coded map for visual differentiation of salary levels across regions.
- 📊 **Data Representation:** Plotted median salary for each country with available data.
- 👁️ **Visual Enhancement:** Improved readability and immediate understanding of geographic salary trends.
- 💡 **Insights Gained:** Enables quick grasp of global salary disparities and highlights high/low salary regions.

    ![1_Salary_Dashboard_Chart2.png](/0_Resources/Images/1_Salary_Dashboard_Chart2.png)

### Formulas and Functions

#### 💰 Median Salary by Job Titles

🧮 Formula:
- 🔍 **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes zero salaries.
- 📊 **Array Formula:** Utilizes `MEDIAN()` function with nested `IF()` statement.
- 🔀 **Dynamic Analysis:** Enables flexible salary data examination across various dimensions.
- 🎯 **Tailored Insights:** Provides specific salary information for different job titles and regions.

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

📊 Populates Table
- **🔢 Formula Function:** This formula populates the table below, it returns median salary based on job title, country, and type specified.

    ![1_Salary_Dashboard_Screenshot1.png](/0_Resources/Images/1_Salary_Dashboard_Screenshot1.png)

### Data Validation

#### ⏰ Job Schedule

🧮 Formula
- **🔍 Unique List Generation:** This Excel formula below employs the FILTER() function to excluding entries containing "and" or commas, and omitting zero values.

    ```
    =FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
    ```

📊 Populates Table Below
- **🔢 Formula Function:** This formula populates the table below, which gives us a list of unique job schedule types.

    ![1_Salary_Dashboard_Screenshot2.png](/0_Resources/Images/1_Salary_Dashboard_Screenshot2.png)

🔍 Filtered List
- 🔒 **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the 'Type' option in the Data tab ensures:
    - 🎯 User input is restricted to predefined, validated schedule types
    - 🔍 Data consistency is improved across entries
    - 🚫 Incorrect or inconsistent schedule type entries are prevented
    - 👥 Overall usability of the dashboard is enhanced
    
    ![1_Salary_Dashboard_Screenshot3.png](/0_Resources/Images/1_Salary_Dashboard_Screenshot3.png)

## Conclusion

I created this dashboard to showcase insights into salary trends across various data-related job titles. Utilizing data from Luke Barousse's Excel Course, it allows users to make informed decisions about their career paths. 