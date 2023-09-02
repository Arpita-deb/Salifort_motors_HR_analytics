# What’ll make the employee leave the company? - A study of Employee Retention in Salifort Motors
## Capstone Project from Google Advanced Data Analytics Professional Certificated course

## Introduction:

Employee retention refers to the ability of a company to prevent employee turnover. In other words, it is the company's concerted efforts to retain their existing staff and keep their best employees on board in order to succeed as a business. Employee retention is often expressed as a statistic; the percentage of employees that remain in a company for a fixed time period (e.g. a quarter). To measure it, we use the following employee retention rate formula:

<img src="https://resources.workable.com/wp-content/uploads/2019/08/employee_retention_formula-1.png">

The Human Resource department at Salifort Motors wants to take some initiatives to improve employee satisfaction levels at the company. They collected data from employees and they want to analyse and find the answer to the question: **What’s likely to make the employee leave the company?** Predicting which employees are likely to quit, might help the company to identify factors that contribute to their leaving. A good model will help the company increase retention and job satisfaction for current employees, and save money and time training new employees.

## Tools used:
1. Python 
2. Tableau
3. Powerpoint

## Methodologies used:
1. Exploratory Data Analysis
2. Descriptive Statistics
3. Logistic regression model
4. Decision tree
5. Random forest
6. XGBoost

# (P)ACE - PLAN - UNDERSTANDING THE DATA IN THE PROBLEM CONTEXT

## About the Company:
Salifort Motors is a fictional French-based alternative energy vehicle manufacturer. Its global workforce of over 100,000 employees research, design, construct, validate, and distribute electric, solar, algae, and hydrogen-based vehicles. Salifort’s end-to-end vertical integration model has made it a global leader at the intersection of alternative energy and automobiles.    

## Key Stakeholders:
* Salifort’s senior leadership team
* Human Resources (HR) department team

## Statement of the Business Task:
Design a model that predicts whether an employee will leave the company based on their job title, department, number of projects, average monthly hours, and any other relevant data points. Analyze the key factors driving employee turnover, build an effective model, and share recommendations for next steps with the leadership team. 

## Deliverables:
1. Project Proposal
2. An executive summary with important insights and recommendations
3. A jupyter notebook with all the codes
   
## About the Data Set:
This project uses a dataset called **HR_capstone_dataset.csv**. It represents 10 columns of self-reported information from employees of a multinational vehicle manufacturing corporation. The dataset contains 14,999 rows – each row is a different employee’s self-reported information and 10 columns

### Data Dictionary:

| Column Name | Type | Description |
| :--- | :--- | :--- |
| satisfaction_level | int64 | The employee’s self-reported satisfaction level [0-1] |
| last_evaluation | int64 | Score of employee's last performance review [0–1] |
| number_project | int64 | Number of projects employee contributes to |
| average_monthly_hours | int64 | Average number of hours employee worked per month |
| time_spend_company | int64 | How long the employee has been with the company (years) |
| work_accident | int64 | Whether or not the employee experienced an accident while at work |
| left | int64 | Whether or not the employee left the company |
| promotion_last_5years | int64 | Whether or not the employee was promoted in the last 5 years |
| department | str | The employee's department |
| salary | str | The employee's salary (low, medium, or high) |

## Data Integrity and reliability

# P(A)CE - ANALYSIS -  EDA, CHECKING MODEL ASSUMPTIONS & SELECT MODEL

## Python packages used: 
1. Operational Packages
   
   * NumPy - Allows for more mathematical operations in Python, provides functions for array-like objects, etc
   * Pandas - Creation of data frames, analyzing data, cleaning data, manipulating data, performing efficient operations on large data sets

2. Visualization Packages

   * MatPlotLib - Easy-to-learn difficult-to-master graphing library for Python. Great for quick, exploratory graphs
   * Seaborn - Built on top of matplotlib, allows for easier customization of plots compare to matplotlib
   *  Plotly - Easy to create beautiful, presentation quality plots and graphs. Lots of built in functionality and can have interactive elements.

3. Machine Learning Packages
   * Sci-Kit Learn - Provides functionality for a host of machine learning models and analytical tools.


# PA(C)E - CONSTRUCT AND EVALUATE MODEL


# PAC(E) - EXECUTE- INTERPRET MODEL AND SHARE STORY
## Summary of the analysis:
## Recommendation:
## Limitation of the project:

## List of References:

* [What is Employee Retention?](https://resources.workable.com/hr-terms/what-is-employee-retention)
* [41 Employee Retention Ideas](https://thrivemap.io/employee-retention-ideas/)
* [Seaborn - A complete data visualization guide](https://www.kaggle.com/code/berkayalan/seaborn-a-complete-data-visualization-guide)
* [Matplotlib - A complete data visualization guide](https://www.kaggle.com/code/berkayalan/matplotlib-a-complete-data-visualization-guide)
* [Plotly tutorial for beginners](https://www.kaggle.com/code/kanncaa1/plotly-tutorial-for-beginners#Line-Charts)
