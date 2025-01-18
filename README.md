# HR Analytics Dashboard

### Dashboard Link : https://app.powerbi.com/groups/me/reports/384d017e-e935-44dc-9e7d-1626c1a36de1/ReportSection

## Problem Statement

The HR Analytics Dashboard aims to provide insights into employee attrition and key workforce metrics. By analyzing data on factors such as education, age, salary, years at the company, and job roles, the dashboard helps HR departments identify trends in employee turnover and pinpoint areas for improvement.  

The primary objective is to reduce the attrition rate (currently 16.2%) by understanding the demographics and roles most affected. Insights drawn from this analysis can guide targeted strategies to enhance employee retention, optimize resource allocation, and improve overall workplace satisfaction.


### Steps followed 

### Steps Followed in HR Analytics Dashboard Creation  

1.  Load data into Power BI Desktop. The dataset used is a CSV file containing HR-related information.  

2. Open Power Query Editor and enable data preview options like "Column Distribution," "Column Quality," and "Column Profile" under the View tab.  

3. Set column profiling to be based on the entire dataset (by default, profiling is limited to the first 1000 rows).  

4. Inspect the dataset for errors or empty values. Identified missing or invalid values in certain columns, such as "Attrition Reason" or "Exit Feedback."  

5. Null values in key columns like "Attrition Rate" or "Salary" were either removed or ignored if they accounted for less than 1% of the data. For average calculations, these null values were excluded.  

6. In the Report view, applied a theme for visual consistency under the View tab.  

7. Added a visual representation to track employee satisfaction ratings across different parameters, such as Job Role, Work Environment, and Career Growth Opportunities, using custom visuals from the Visualizations pane.  

8. Added slicers for fields like Department, Job Role, Age Group, and Education Level to allow filtering and interactivity.  

9.  Created card visuals to represent key metrics such as:  
    - Total Employees  
    - Average Salary  
    - Attrition Rate (%)  
    - Average Years at Company  

   Null or invalid values in these calculations were ignored using basic filtering in the Filters pane.  

10.  Designed a clustered bar chart to show the distribution of attrition across departments, further segmented by gender to highlight trends.  

11.  Added satisfaction ratings visual for the following parameters:  
   - Work-Life Balance  
   - Training and Development  
   - Compensation and Benefits  
   - Work Environment  
   - Career Advancement  
   - Manager Support  

   Ratings with a value of 0 (indicating "Not Applicable") were excluded from average calculations.  

12.  In the Report view, added text boxes to display the organization's name and tagline for branding.  

13.  Added shapes and images to the report, such as a rectangle for visual organization and the company logo for branding.  

14.  Created a calculated column to group employees by age into categories. The following DAX expression was used:  
    ```DAX
    Age Group = 
    IF(HR[Age] <= 25, "0-25 (25 included)",
    IF(HR[Age] <= 50, "25-50 (50 included)",
    IF(HR[Age] <= 75, "50-75 (75 included)", 
    "75-100 (100 included)")))
    ```  

15.  Created a measure to calculate the total count of employees:  
    ```DAX
    Count of Employees = COUNT(HR[Employee ID])
    ```  
    Used a card visual to display the total employee count.  

16.  Created a measure to calculate the percentage of employees in specific departments or roles:  
    ```DAX
    % Employees = DIVIDE(COUNT(HR[Employee ID]), TOTAL_EMPLOYEES) * 100
    ```  
    Displayed the result using a card visual.  

17.  Created a measure to calculate the total years of service across all employees:  
    ```DAX
    Total Years of Service = SUM(HR[Years at Company])
    ```  
    Used a card visual to display the total years of service.  

18.  Published the finalized dashboard to Power BI Service for access by stakeholders.  

This structured approach ensured that the HR Analytics Dashboard provided actionable insights into employee attrition, satisfaction, and workforce dynamics.

# Snapshot of Dashboard (Power BI Service)

![dashboard_snapo](https://user-images.githubusercontent.com/102996550/174096257-11f1aae5-203d-44fc-bfca-25d37faf3237.jpg)

 
 # Report Snapshot (Power BI DESKTOP)

 
![Dashboard_upload](https://user-images.githubusercontent.com/102996550/174074051-4f08287a-0568-4fdf-8ac9-6762e0d8fa94.jpg)

# Insights

A single-page dashboard was created in Power BI Desktop and published to Power BI Service to analyze employee satisfaction and related HR data. The following insights were derived:



### [1] Employee Retention (Total Workforce)

Total Employees: 129,880
Satisfied Employees (Male): 28,159 (21.68%)
Satisfied Employees (Female): 28,269 (21.76%)
Neutral/Unsatisfied Employees (Male): 35,822 (27.58%)
Neutral/Unsatisfied Employees (Female): 37,630 (28.97%)
Insight: A significant portion of employees (56.55%) are neutral or unsatisfied, indicating opportunities for HR improvements.
           
### [2]  Average Satisfaction Ratings

Training & Onboarding: 3.33/5
Team Collaboration: 3.37/5
Work Environment: 3.64/5
Compensation & Benefits: 2.81/5
Leadership Effectiveness: 3.38/5
Career Growth Opportunities: 2.88/5
  
  Employees rate work environment and team collaboration higher than compensation and career growth opportunities, which may drive dissatisfaction. 
  
  ### [3] Average Working Hours (Performance Indicators) 
  
Average Hours Overdue (Arrival): 15.09 minutes
Average Hours Overdue (Departure): 14.71 minutes
Delays in task completion or meetings indicate workflow inefficiencies or capacity management issues.

 ### [4]Demographics Analysis
 
 ### Departments (Class Representation)
 
Leadership Roles: 47.87%
Mid-level Roles: 44.89%
Junior Roles: 7.25%
Insight: Most employees are in leadership or mid-level roles, with limited junior-level presence, potentially affecting talent pipeline development
 
 ### Age Group
 
0-25 years: 21.69%
25-50 years: 52.44%
50-75 years: 25.57%
75-100 years: 0.31%
Insight: A majority of employees belong to the 25-50 age group, highlighting opportunities for leadership development and retention strategies for this cohort.
         
###  Employee Type

New Hires (First-Time Employees): 18.31%
Returning Employees (Tenured Staff): 81.69%
Insight: High retention of tenured employees, but onboarding processes for new hires may require optimization.

###  Work Profiles (Travel Type Analysis)

Business-Oriented Roles: 69.06%
Personal Roles: 30.94%
Insight: Most employees are in business-critical roles, necessitating targeted engagement strategies for these employees.
