# What’ll make the employee leave the company? - A study of Employee Retention in Salifort Motors
## Capstone Project from Google Advanced Data Analytics Professional Certificated course

## Introduction:

Employee retention refers to the ability of a company to prevent employee turnover. In other words, it is the company's concerted efforts to retain their existing staff and keep their best employees on board in order to succeed as a business. Employee retention is often expressed as a statistic; the percentage of employees that remain in a company for a fixed time period (e.g. a quarter). To measure it, we use the following employee retention rate formula:

<img src="https://resources.workable.com/wp-content/uploads/2019/08/employee_retention_formula-1.png">

As businesses compete for top talent, employee retention is crucial. While some experts suggest that a 90% retention rate is a good goal, the reality is, it varies across different companies and industries. However, the ability to retain employees is universally beneficial for many reasons. 

Importance of employee retention -
1. Employee retention is a high priority for leading HR organizations today.
2. The most effective employee retention strategies reduce overall turnover and keep high performers on board.
3. A thoughtful and comprehensive employee retention strategy reduces the high costs associated with replacing lost employees.
   
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
The purpose of this project is to design a model that predicts whether an employee will leave the company based on their job title, department, number of projects, average monthly hours, and any other relevant data points. Our goal is to analyze the key factors driving employee turnover, build an effective model, and share recommendations for next steps with the leadership team. 

## Deliverables:
1. Project Proposal
2. An executive summary with important insights and recommendations
3. A jupyter notebook with all the codes
   
## About the Data Set:
This project uses a dataset called **HR_capstone_dataset.csv** from [kaggle](https://www.kaggle.com/datasets/mfaisalqureshi/hr-analytics-and-job-prediction?select=HR_comma_sep.csv). It represents 10 columns of self-reported information from employees of a multinational vehicle manufacturing corporation. The dataset contains 14,999 rows – each row is a different employee’s self-reported information and 10 columns

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

## Data Integrity:

### Reliability and Originality:
There is no information how the data is collected or preprocessed. Since this dataset has been provided by Coursera in this capstone project we can assume its reliability and originality.

### Comprehensiveness:
The data contains information that may help us find the answer to the key question **What’s likely to make the employee leave the company?**. But there are many more reasons for an employee to leave a company. For example, personal reasons (relocating for a spouce, family or health issues), work-life balance, incompatility between employer and employee, lack of opportunity, financial reasons etc. 

### Citation:
There is no external citation for this dataset. You can visit [kaggle](https://www.kaggle.com/datasets/mfaisalqureshi/hr-analytics-and-job-prediction?select=HR_comma_sep.csv) for basic informations.

### Current:
The dataset is created 2 years ago. Clearly it is outdated.

# P(A)CE - ANALYSIS -  EDA, CHECKING MODEL ASSUMPTIONS & SELECT MODEL

## Data Cleaning:

For spellchecking and fixing column names I've used Google sheet.

* Changed the column names *Work_accident*, *Department* and *time_spend_company*  to *work_accident*, *department* and *tenure* respectively.
* Using Find and Replace changed the lower case department and salary names to proper case, so that the names are shown properly in graphs.
* Checked for white space using trimming.
* Saved the new dataset as **salifort_employee_retention_data** and I'm going to use it for the analysis.

## Python packages selected: 
1. Operational Packages
   
   * NumPy - Allows for more mathematical operations in Python, provides functions for array-like objects, etc
   * Pandas - Creation of data frames, analyzing data, cleaning data, manipulating data, performing efficient operations on large data sets

2. Visualization Packages

   * MatPlotLib - Easy-to-learn difficult-to-master graphing library for Python. Great for quick, exploratory graphs
   * Seaborn - Built on top of matplotlib, allows for easier customization of plots compare to matplotlib
   *  Plotly - Easy to create beautiful, presentation quality plots and graphs. Lots of built in functionality and can have interactive elements.

3. Machine Learning Packages
   * Sci-Kit Learn - Provides functionality for a host of machine learning models and analytical tools.

## Exploratory Data Analysis:

### Steps taken:
1. Loaded the required python packages and the dataset.
2. Had a general sense of the data using head(), info(), shape() functions.
3. Performed descriptive statistics and calculated the mean,median, mode, maximum and minimum value of the numerical variables.
4. Checked for null and duplicate values. Removed the duplicates and saved the data in a new dataframe.
5. Checked for class imbalance.
6. Visualized the distributions of numerical and categorical variables.
7. Created Correlation matrix and Heatmap to find relations between the variables.
8. Created visualizations like boxplot, histogram, scatterplot, bar charts and regplot to get detailed view of the dataset.
9. Saved the data frame as a csv file to work later for regression analysis and model building.

## Summary of the Exploratory Data Analaysis: 

1. The dataset doesn't contain any missing value but has 3008 duplicated values. We've removed those and created a new dataset df_raw with 11991 rows.

2. In the last_evaluation column, the minimum score was 0.36, it doesn't contain the score below 0.36. In the average_monthly_hours column, it has a very large standard deviation as well as the range. The tenure has a similar situation as the last_evaluation column, there is no data for employees who worked less than 2 years.

3. 'left' will be our target variable. We realize the majority class is about 83.4% of the data set, it is moderately imbalanced (~20%).

4. There are 10 Departments in this dataset. The department of Sales has the highest number of employee retention.

5. There are 3 salary levels in this dataset. Majority of the left employees have a low salary level, followed by medium and high. When the salary level goes up, the possibility of leaving is decreased.

6. The employees who left the company tended to have lower satisfaction levels than the employees who stayed in the company. The lowest satisfaction level scores were more likely given by the employees who have left the company, but we still see numbers of stayed employees given very low satisfaction scores.

7. The employees who left the company had a similar but an average higher score in the last performance than the employees who stayed in the company. Majority of the employees stayed has a evaluation higher than 0.5. There are some employees who have low evaluation score, still they're working in the company. Majority of the employees who've left have a low evaluation score between 0.45 to 0.6 But some of them have higher evaluation score as well.

8. When the employees only have 2 projects, the possibility of turnover is the most compared to other numbers of projects. When the employees have 3 projects, the possibilities of turn over is smallest. In addition, all the employees are left when they have 7 projects. The chance of turn over increases as employees are tasked with more projects.

9. In the histogram of Satisfaction Level, we saw some employees who've left the company giving higher scores of satisfaction. When the employees leave the company, the satisfaction level is very low, except when they have 7 projects. So the employees who've 7 projects were satisfied with the company but nonetheless left the company because of some other reasons.

10. The employees who left the company had more average monthly work hours than the employees who stayed in the company. By checking the average_monthly_hour, we can find 96 was the minimum monthly working hour, and 310 was the maximum monthly working hour. 149 and 156 are the most frequent monthly working hours.

11. There is 63% of employees who worked over 176 hours/month. The percentage of employee who worked over 176 hours/month and left the company is around 14.56%.

12. Working overtime can be a reason of low satisfaction level in employees and it might influence an employee's decision to leave.

13. The employees who work in the company longer(tenure) tend to have more possibility of leaving.

14. The employees who didn't experience an accident while at work were more likely to stay in the company.

15. The employees who were promoted in the last 5 years were more likely to stay in the company.

16. 'satisfaction_level' has more relationship with left, compared to other variables. We see the lowest satisfaction level is below 0.1, and it has a large number of employees who had the similar rate. Other than that, there are also a large number of the employees who had a satisfaction level higher than 0.56.

### Recommendations based on EDA on Employee Retention:

1. Sales department of Salifort Motors has the highest retention rate. The leadership and HR team should look into the matter further.
2. If the company wants to keep the talent in the company, they must reduce the working hours for overworked employees.
3. They should look into the matter when employees with high satisfaction level and evaluation score still leaving the company.

### Some questions for further research:

The HR department can look further into the matter by asking the following questions:
1. Why 63% of the total employees worked overtime? Is overtime a reason for low satisfaction level among the employees?
2. Why do sales department has highest retention rate?
3. Is number of project and promotions are given unjustly to employees?
4. Why employees with high satisfaction level and evaluation score still left the company? Is there other factors affecting the employee retention?

# PA(C)E - CONSTRUCT AND EVALUATE MODEL

## 1. Logistic Regression Model
The goal of this project is to find out which factor(s) will make the employee leave the company. From Exploratory Data Analysis we've found that 'left' is our predictor variable, i.e. we want to figure out whether or not an employee will leave the company. It is clearly a categorical variable.  Moreover, from correlation matrix and heatmap we found out that satisfactory level is positively correlated with left variable. So we'll create a logistic regression model with satisfaction level as our independent variable and left as our dependent/predictor varaiable.

The assumptions of Logistic Regression Model:
1. The dependent variable is categorical and binary / dichotomous.
2. There is little or no multicollinearity between the independent variables.
3. There is linear relationship of variables to log odds.
4. Requires sufficiently large sample size
5. There are no extreme outliers.
6. We have independent observations.

Steps taken: 
1. Import packages, functions, and classes
2. Get data to work with and, if appropriate, transform it
3. Create a classification model and train (or fit) it with existing data
4. Predicting the test result
5. Test accuracy of the result(Creation of Confusion matrix)

Interpretation of the result:

Limitation of the model and ethical considerations:



## 2. 

# PAC(E) - EXECUTE- INTERPRET MODEL AND SHARE STORY
## Summary of the analysis:
## Recommendation:
## Limitation of the project:

## List of References:
Phase 1 - Planning
* [What is Employee Retention?](https://resources.workable.com/hr-terms/what-is-employee-retention)
* [41 Employee Retention Ideas](https://thrivemap.io/employee-retention-ideas/)
* [Employee Retention metrics](https://www.netsuite.com/portal/resource/articles/human-resources/employee-retention-metrics.shtml)
* [How do you measure employee retention rate and why is it important?](https://www.linkedin.com/advice/3/how-do-you-measure-employee-retention-rate?utm_source=share&utm_medium=member_android&utm_campaign=share_via)

Phase 2 - Analysis
* [11 essential code blocks exploratory data analysis](https://www.kdnuggets.com/2021/03/11-essential-code-blocks-exploratory-data-analysis.html)
* [10 things to do when conductiong your exploratory data analysis](https://medium.com/data-folks-indonesia/10-things-to-do-when-conducting-your-exploratory-data-analysis-eda-7e3b2dfbf812)
* [Seaborn - A complete data visualization guide](https://www.kaggle.com/code/berkayalan/seaborn-a-complete-data-visualization-guide)
* [Matplotlib - A complete data visualization guide](https://www.kaggle.com/code/berkayalan/matplotlib-a-complete-data-visualization-guide)
* [Plotly tutorial for beginners](https://www.kaggle.com/code/kanncaa1/plotly-tutorial-for-beginners#Line-Charts)
* [Seaborn Heatmap](http://seaborn.pydata.org/generated/seaborn.heatmap.html)
* [Seaborn Boxplot](https://seaborn.pydata.org/generated/seaborn.boxplot.html)

Phase 3 - Construct
* [Confusion Matrix](https://youtu.be/Kdsp6soqA7o?si=5fiS9byN5i13ODRx)
* [Logistic Regression Explained](https://youtu.be/yIYKR4sgzI8?si=IEurObJZiTn75BWV)
* [What Is Logistic Regression? Equation, Assumptions, Types, and Best Practices](https://www.spiceworks.com/tech/artificial-intelligence/articles/what-is-logistic-regression/amp/)
* [Assumptions of Logistic Regression](https://www.statology.org/assumptions-of-logistic-regression/)
* [Reference guide for interpreting the logistic regression model](https://docs.google.com/document/d/1Pi3JxADgy0-JGO_mcRvBPWPavyS6kR8jEQtVIemHkt4/edit?usp=sharing)
* [Reference guide for common Logistic Regression metrics in Python](https://docs.google.com/document/d/1HZoQyvdeGq0rJiMSos3bMC2hDt6vBgs41hQYEk8RSeI/edit?usp=sharing)
