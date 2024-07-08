# Retaining Talents, Unleashing Possibilities - A study of Employee Retention in Salifort Motors
## Capstone Project from Google Advanced Data Analytics Professional Certification Course

## Introduction:

This project is aimed to identify the factors influencing employee turnover at Salifort motors, a fictional manufacturing company. 

Here, I analyzed the human resources data, which included variables such as monthly working hours, number of projects, promotion status, department, and salary. I cleaned the data using Excel and performed Exploratory Data Analysis (EDA) using Python packages such as Numpy, Pandas, Matplotlib, Seaborn, and Sci-Kit learn. 

I've then created 5 classification models namely Logistic Regression, Decision Tree with and without hyperparameter tuning, Random Forest, and XGBoost to correctly classify employees who'll leave or stay in the company. Then I evaluated the models using metrics such as accuracy, recall, precision, f1 score, and confusion matrix. 

Finally I summarized the results and presented the recommendations for Salifort’s Senior Leadership team and Human Resources (HR) team with an Executive Summary.

## Employee Retention:

Employee retention refers to the ability of a company to prevent employee turnover. In other words, it is the company's concerted efforts to retain their existing staff and keep their best employees on board in order to succeed as a business. Employee retention is often expressed as a statistic; the percentage of employees that remain in a company for a fixed time period (e.g. a quarter). To measure it, we use the following employee retention rate formula:

<img src="https://resources.workable.com/wp-content/uploads/2019/08/employee_retention_formula-1.png">

As businesses compete for top talent, employee retention is crucial. While some experts suggest that a 90% retention rate is a good goal, the reality is, it varies across different companies and industries. However, the ability to retain employees is universally beneficial for many reasons. 

Importance of employee retention -
1. Employee retention is a high priority for leading HR organizations today.
2. The most effective employee retention strategies reduce overall turnover and keep high performers on board.
3. A thoughtful and comprehensive employee retention strategy reduces the high costs associated with replacing lost employees.
   
The Human Resource department at Salifort Motors wants to take some initiatives to improve employee satisfaction levels at the company. They collected data from employees and they want to analyse and find the answer to the question: **What’s likely to make the employee leave the company?** Predicting which employees are likely to quit, might help the company to identify factors that contribute to their leaving. A good model will help the company increase retention and job satisfaction for current employees, and save money and time training new employees.

## Tools used:
1. Excel - for initial data cleaning
2. Python - for Exploratory Data Analysis and building machine learning model
3. Google Slides - to create Project Proposal and executive summary

## Methodologies used:
1. Exploratory Data Analysis
2. Descriptive Statistics
3. Logistic regression model
4. Decision tree
5. Random forest
6. XGBoost

The entire project from collecting and validating the data, exploratory data analysis, building machine learning models to predict employee churn and communicating the results to the stakeholders is based on PACE workflow. PACE is an acronym; each one of the letters represents an actionable stage in a project: plan, analyze, construct, and execute.

![Pace](https://github.com/Arpita-deb/Salifort_motors_HR_analytics/assets/139372731/a392c404-8909-4167-ba55-da276f42a830)

# (P)ACE - PLAN - UNDERSTANDING THE DATA IN THE PROBLEM CONTEXT

## About the Company:
Salifort Motors is a fictional French-based alternative energy vehicle manufacturer. Its global workforce of over 100,000 employees research, design, construct, validate, and distribute electric, solar, algae, and hydrogen-based vehicles. Salifort’s end-to-end vertical integration model has made it a global leader at the intersection of alternative energy and automobiles.    
## Key Stakeholders:
* Salifort’s Senior Leadership team
* Human Resources (HR) department team

## Statement of the Business Task:
The purpose of this project is to design a model that predicts whether an employee will leave the company based on their job title, department, number of projects, average monthly hours, and any other relevant data points. Our goal is to analyze the key factors driving employee turnover, build an effective model, and share recommendations for next steps with the leadership team. 

## Deliverables:
1. [Project Proposal](https://github.com/Arpita-deb/Salifort_motors_HR_analytics/files/12567932/Salifort.Motors.Project.Proposal.pptx)
2. [An executive summary with important insights and recommendations](https://github.com/Arpita-deb/Salifort_motors_HR_analytics/assets/139372731/10d137c5-8e37-4b88-8b2c-ffde573f68f9)
3. A jupyter notebook with all the codes
   
## About the Data Set:
This project uses a dataset called **HR_capstone_dataset.csv** from [Kaggle](https://www.kaggle.com/datasets/mfaisalqureshi/hr-analytics-and-job-prediction?select=HR_comma_sep.csv). It represents 10 columns of self-reported information from employees of a multinational vehicle manufacturing corporation. The dataset contains 14,999 rows – each row is a different employee’s self-reported information and 10 columns.

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
The dataset was created 2 years ago. Clearly it is outdated.

# P(A)CE - ANALYSIS -  EDA, CHECKING MODEL ASSUMPTIONS & SELECT MODEL

## Data Cleaning:

For spellchecking and fixing column names I've used Google sheet.

* Changed the column names *Work_accident*, *Department* and *time_spend_company*  to *work_accident*, *department* and *tenure* respectively.
* Using Find and Replace changed the lower case department and salary names to proper case, so that the names are shown properly in graphs.
* Checked for white space using trimming.
* Saved the new dataset as **salifort_employee_retention_data** to use it for the analysis.

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

### Summary of the Exploratory Data Analysis: 

1. The dataset doesn't contain any missing value but has 3008 duplicated values. We've removed those and created a new dataset df_raw with 11991 rows.

2. In the last_evaluation column, the minimum score was 0.36, it doesn't contain the score below 0.36. In the average_monthly_hours column, it has a very large standard deviation as well as the range. The tenure has a similar situation as the last_evaluation column, there is no data for employees who worked less than 2 years.

3. 'left' will be our target variable. We realize the majority class is about 83.4% of the data set, it is moderately imbalanced (~20%).

4. There are 10 Departments in this dataset. The department of Sales has the highest number of employee churn.

![dept](https://github.com/Arpita-deb/Salifort_motors_HR_analytics/assets/139372731/78609a75-0f5b-4de2-b30a-d80466dcd04b)

5. There are 3 salary levels in this dataset. Majority of the left employees have a low salary level, followed by medium and high. When the salary level goes up, the possibility of leaving is decreased.

![salary](https://github.com/Arpita-deb/Salifort_motors_HR_analytics/assets/139372731/11a7d3f0-49e5-4ef2-add2-2955f207f0ca)

6. The employees who left the company tended to have lower satisfaction levels than the employees who stayed in the company. The lowest satisfaction level scores were more likely given by the employees who have left the company, but we still see numbers of stayed employees given very low satisfaction scores.

![satisfaction level](https://github.com/Arpita-deb/Salifort_motors_HR_analytics/assets/139372731/09b9f197-3dcf-43d4-a212-1872a51ec556)

7. The employees who left the company had a similar but an average higher score in the last performance than the employees who stayed in the company. Majority of the employees stayed has a evaluation higher than 0.5. There are some employees who have low evaluation score, still they're working in the company. Majority of the employees who've left have a low evaluation score between 0.45 to 0.6 But some of them have higher evaluation score as well.

![evaluate score](https://github.com/Arpita-deb/Salifort_motors_HR_analytics/assets/139372731/dcbfc9c7-93cd-4397-b564-d6497fa3b149)

![performance score](https://github.com/Arpita-deb/Salifort_motors_HR_analytics/assets/139372731/876fd2d0-06d8-4e60-bf24-3e315455b0df)

8. When the employees only have 2 projects, the possibility of turnover is the most compared to other numbers of projects. When the employees have 3 projects, the possibilities of turn over is smallest. In addition, all the employees are left when they have 7 projects. The chance of turn over increases as employees are tasked with more projects.

![project](https://github.com/Arpita-deb/Salifort_motors_HR_analytics/assets/139372731/4b588a20-c55a-4a08-8a69-2624dbab2c4a)

9. In the histogram of Satisfaction Level, we saw some employees who've left the company giving higher scores of satisfaction. When the employees leave the company, the satisfaction level is very low, except when they have 7 projects. So the employees who've 7 projects were satisfied with the company but nonetheless left the company because of some other reasons.
    
10. The employees who left the company had more average monthly work hours than the employees who stayed in the company. By checking the average_monthly_hour, we can find 96 was the minimum monthly working hour, and 310 was the maximum monthly working hour. 149 and 156 are the most frequent monthly working hours.

![hours](https://github.com/Arpita-deb/Salifort_motors_HR_analytics/assets/139372731/3bcb4876-3eb8-4c77-bc7a-09a5eccc0541)

11. There is 63% of employees who worked over 176 hours/month. The percentage of employee who worked over 176 hours/month and left the company is around 14.56%.

12. Working overtime can be a reason of low satisfaction level in employees and it might influence an employee's decision to leave.

![scatterplot](https://github.com/Arpita-deb/Salifort_motors_HR_analytics/assets/139372731/f089d6fe-ad74-4430-8c1f-202c085a821c)

13. The employees who work in the company longer(tenure) tend to have more possibility of leaving.

![tenure](https://github.com/Arpita-deb/Salifort_motors_HR_analytics/assets/139372731/1153cdee-4a46-4305-b87e-9e489328c1c8)

14. The employees who didn't experience an accident while at work were more likely to stay in the company.

![accident](https://github.com/Arpita-deb/Salifort_motors_HR_analytics/assets/139372731/4453b455-e16f-494f-a4ae-baca2fca202d)

15. The employees who were promoted in the last 5 years were more likely to stay in the company.

![promotion](https://github.com/Arpita-deb/Salifort_motors_HR_analytics/assets/139372731/5a365ec3-8ef0-46ac-9f2d-6c1ece7e0cd1)

16. 'satisfaction_level' has more relationship with left, compared to other variables. We see the lowest satisfaction level is below 0.1, and it has a large number of employees who had the similar rate. Other than that, there are also a large number of the employees who had a satisfaction level higher than 0.56.

### Recommendations based on EDA on Employee Retention:

1. Sales department of Salifort Motors has the lowest retention rate. The leadership and HR team should look into the matter further.
2. If the company wants to keep the talent in the company, they must reduce the working hours for overworked employees.
3. They should look into the matter when employees with high satisfaction level and evaluation score still leaving the company.

### Some questions for further research:

The HR department can look further into the matter by asking the following questions:
1. Why 63% of the total employees worked overtime? Is overtime a reason for low satisfaction level among the employees?
2. Why do sales department has lowest retention rate?
3. Is number of project and promotions are given unjustly to employees?
4. Why employees with high satisfaction level and evaluation score still left the company? Is there other factors affecting the employee retention?

###  Selecting models for the project:
Since our predictor variable 'left' is a binary/categorical variable (i.e., with only 2 possibilities, either 0 if stayed or 1 if left) we'll go for a classification model. 
We'll build 4 models -
1. Logistic Regression
2. Decision Trees
3. Random Forest
4. XGBoost model

We'll choose the one with highest evaluation scores and implement it to predict whether an employee will leave or not.

# PA(C)E - CONSTRUCT AND EVALUATE MODEL

## Steps taken to build the models: 
1. Import packages, functions, and classes
2. Get data to work with and, if appropriate, transform it
3. Create a classification model and train (or fit) it with existing data
4. Predicting the test result
5. Test accuracy of the result(Creation of Confusion matrix)

## Evaluation metrics:

1. **Accuracy score** :  Refers to the proportion of data points that were correctly categorized. Accuracy is an appropriate metric to use when the data is balanced, in other words, when the data has a roughly equal number of positive examples and negative examples. Otherwise, accuracy can be biased.
2. **Recall score**: The proportion of positives the model was able to identify correctly. 
3. **Precision Score**: The proportion of positive predictions that were true positives. 
4. **F1 score**: It’s a harmonic mean of “precision” & “recall”, taking both the metrics into account.
5. **Confusion matrix**: A graphical representation of how accurate a classifier is at predicting the labels for a categorical variable*
   * True negatives: The count of observations that the classifier correctly predicted as False (0). In this case, the classifier will correctly predict the employees who didn't leave.

   * True positives: The count of observations that a classifier correctly predicted as True (1) i.e. the classifier will correctly predict the employees who left.

   * False positives: The count of observations that a classifier incorrectly predicted as True (1) i.e. the classifier will predict employees as left but in reality, who stayed.

   * False negatives: The count of observations that a classifier incorrectly predicted as False (0). In this case, the classifier will incorrectly predict employees as stayed but in reality, who left.

The False negatives may cause the company to spend more resources on an employee who decides to leave. The False positives may cause the company to think an employee will leave and won't put resources on this employee. False negatives will be worse for the company, false positives will be worse for employees.

## Results of the models:
| Model | Accuracy | Recall | Precision | F1 Score | Confusion matrix |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Logistic Regression | 0.871 | 0.239 | 0.973 | 0.383 | ![Screenshot (603)](https://github.com/Arpita-deb/Salifort_motors_HR_analytics/assets/139372731/bf77a579-5ff5-4ed1-811a-e2865d86c9ea) |
| Single Decision tree without Hyperparameter tuning and Grid Search | 0.967 | 0.920 | 0.884 | 0.902 | ![dt wo grid](https://github.com/Arpita-deb/Salifort_motors_HR_analytics/assets/139372731/13bda057-1db3-441e-b606-474acf79a941) |
| Decision Tree with Hyperparameter tuning and Grid Search | 0.982 | 0.932 | 0.961 | 0.946 | ![cm dt with grid (2)](https://github.com/Arpita-deb/Salifort_motors_HR_analytics/assets/139372731/96a86fc7-05e8-4de8-9a71-853bcefe2f74) |
| Random Forest | 0.984 | 0.916 | 0.987 | 0.950 | ![cm random forest (2)](https://github.com/Arpita-deb/Salifort_motors_HR_analytics/assets/139372731/4975e7e2-771f-4092-aaa2-a1084e92821a) |
| XG Boost Model | 0.985 | 0.928 | 0.979 | 0.953 | ![cm xgboost (2)](https://github.com/Arpita-deb/Salifort_motors_HR_analytics/assets/139372731/781987b6-0c9a-4df5-b0e0-32c7044b6a4e) |

Now from the results of each model, we can see XGBoost model performed well with an f1 score of 0.953. We're using f1 score as our key evaluation matrix as it takes into account both recall and precision. Moreover, since our data is highly imbalanced (it contains more data on employees who stayed than who actually left), we do not emphasize on accuracy. Since majority of the datapoints consists of stayed employees, the models will naturally predict correctly the stayed employees. But we want to predict which employee will leave, i.e. on True Positives.

We can see from the confusion matrices, that XGBoost which correctly predicted 462 left employees with only 10 false positives, is only next to a Single Decision Tree with Hyperparameter tuning which correctly predicted 464 left employees, but with more false positives (19).

Therefore, between XGBoost and a single Decision Tree with Hyperparameter tuning, we'll opt for the former, as it has correctly classified 98.5% of the total data points.

# PAC(E) - EXECUTE- INTERPRET MODEL AND SHARE STORY

![Screenshot (621)](https://github.com/Arpita-deb/Salifort_motors_HR_analytics/assets/139372731/df242505-5c64-4e38-b906-8092bf98794b)

## Summary of the analysis:

In this project we've - 
1. Performed Exploratory Data Analysis on the HR_capstone_dataset provided by the HR team of Salifort Motors.
2. Visualized the relations between various variables and found out our predictor variable 'left'.
3. We've created 4 different models whose performance is evaluated by how many employees they've correctly predicted as left and stayed.
4. Among the models, Logistic Regression model performed worst with an f1 score of 0.383.
5. The best performing model is a Gradient boosted decision tree or an XGBoost model with f1 score of 0.953, which is a good evaluation score for a prediction model.
6. From the graph of Feature Importance we can clearly see which feature(variable) influences most the employee retention in the company. Average_monthly_hours, satisfaction_level and last_evaluation are the top 3 important features for predicting if an employee will leave or not.
7. Compared to different salary levels, the employees who have a low salary are most likely to leave the company.
8. Compared to different departments, the employees in Sales are most likely to leave the company.

## Recommendations:

* Our dataset has much less data for the employees who were left than the employees who stayed. It also impacts our evaluation results and confusion matrix. We recommend gaining more data for the employees who left before implementing the model in use.

* We only have 10 departments in this dataset, it's better to know whether there are other departments in the company.

* For the salary, it's better to build this feature with numerical data that shows how much the employee earns in a certain period of time. The level of salary is not clear enough.

* As we mentioned above, average_monthly_hours is the most important feature to drive employees' retention. Combining the EDA results, we found that 63% of employees in the company worked over time. Plus the employees who left the company had more average monthly work hours than the employees who stayed in the company. We recommend significant reducing in the chance of working over time.

* The employees who left the company usually spent more time on the project, the reason can be:
  1) less investment on training, and upskilling the employees
  2) get more complicated projects that need more time of working
  3) less familiarity with the project
  We need to find the reasons in order to reduce the high rate of turnover. We are concerned about whether the projects have been given to employees fairly. We recommend the company to setup a policy that can overlook the entire wellbeing and performance of the employees.

* In satisfaction_level, we knew the employees who left the company tended to have lower satisfaction levels than the employees who stayed in the company. And satisfaction level is the second important feature of driving employees' retention. Other than the points we just mentioned, we also recommend working on analysing the trends of satisfaction_level, to find out its correlation with other variables which hasn't been done in this project.

  Some ways the company can increase employee's job satisfaction are -
   * by providing opportunities for career advancement and growth
   * by fostering a positive work culture that values respect, diversity, and feedback
   * by recognizing and rewarding employee achievements and contributions
   * by offering competitive compensation and benefits packages
   * by ensuring job security and stability
   * by promoting work-life balance and wellness initiatives

* As the low level of salary is likely to lead to the retention of the company, we can work with this group more in order to increase their satisfaction level.

* We also recommend increasing the chances of promotion across the departments and the salary levels.

## Limitation of the project:
1. Our dataset is imbalanced (~83%, i.e., 83% of total employees stayed at the company and only 17% left the company) i.e. it has much less data for the employees who left than the employees who stayed. It also impacts our evaluation results and confusion matrix. Class Imbalance can be a huge disadvantage for building advanced machine learning models.
2. The data hasn't been cross-validated before implementing the models. Before testing the models on test data, they should be vigorously tested on training and validation set to ensure accurate and trustworthy performance of the models.
3. We've used only 5 matrices for evaluating the performances of the models. There are many more hyperparameters and  matrices that will help us tune and evaluate a better performing model.  

# List of References:
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
* [Seaborn Heatmap](http://seaborn.pydata.org/generated/seaborn.heatmap.html)
* [Seaborn Boxplot](https://seaborn.pydata.org/generated/seaborn.boxplot.html)

Phase 3 - Construct
1. Logistic Regression
   * [Confusion Matrix](https://youtu.be/Kdsp6soqA7o?si=5fiS9byN5i13ODRx)
   * [Logistic Regression Explained](https://youtu.be/yIYKR4sgzI8?si=IEurObJZiTn75BWV)
   * [What Is Logistic Regression? Equation, Assumptions, Types, and Best Practices](https://www.spiceworks.com/tech/artificial-intelligence/articles/what-is-logistic-regression/amp/)
   * [Assumptions of Logistic Regression](https://www.statology.org/assumptions-of-logistic-regression/)
   * [Reference guide for interpreting the logistic regression model](https://docs.google.com/document/d/1Pi3JxADgy0-JGO_mcRvBPWPavyS6kR8jEQtVIemHkt4/edit?usp=sharing)
   * [Reference guide for common Logistic Regression metrics in Python](https://docs.google.com/document/d/1HZoQyvdeGq0rJiMSos3bMC2hDt6vBgs41hQYEk8RSeI/edit?usp=sharing)
2. Decision Tree
   * [Decision Learning Model Learning](https://www.coursera.org/articles/decision-tree-machine-learning)
   * [Machine Learning decision tree classification algorithm](https://www.javatpoint.com/machine-learning-decision-tree-classification-algorithm)
3. Random Forest Classifier
   * [Machine Learning Random Forest classification algorithm](https://www.javatpoint.com/machine-learning-random-forest-algorithm)
   * [StatQuest: Random Forests Part 1 - Building, Using and Evaluating](https://youtu.be/J4Wdy0Wc_xQ?si=S0u2sWWOTNjOcjRC)
   * [StatQuest: Bootstrapping Main Ideas!!!](https://youtu.be/Xz0x-8-cgaQ?si=pqVVwhfUYOQ8-jQ6)
   * [Ensembles - Kaggle Notebook](https://www.kaggle.com/code/kashnitsky/topic-5-ensembles-part-1-bagging/notebook)
3. XGBoost
   * [XGBoost Parameters](https://xgboost.readthedocs.io/en/latest/parameter.html)
  
