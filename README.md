# PwC-Switzerland-Power-BI-Virtual-Internship
PwC Switzerland Power BI Job Simulation on Forage - March 2025

## Description
PwC Virtual Internship – Business Intelligence Analyst <br>
Client: PhoneNow <br>
Tools Used: Power BI, Excel <br>

As part of the PwC Virtual Internship, I worked on three key industrial tasks for PhoneNow, leveraging Power BI to provide data-driven insights:

### 1. Call Centre Trends Analysis
Analyzed call volumes, average handling time (AHT), and customer satisfaction (CSAT) metrics. <br>
Identified peak call hours and agent performance trends to optimize workforce allocation.<br>
Created an interactive dashboard to track key performance indicators (KPIs) and improve operational efficiency.

### 2.Customer Retention Insights
Examined churn rates, customer lifetime value (CLV), and engagement patterns.<br>
Conducted cohort analysis to identify retention trends and potential areas for improvement.<br>
Designed a Power BI report highlighting customer segments at risk of churn and actionable retention strategies.

### 3.Diversity & Inclusion Analytics
Assessed workforce diversity across gender, ethnicity, and age demographics.<br>
Evaluated hiring trends, promotion equity.<br>
Developed a visual report to showcase inclusivity progress and recommend data-driven HR policies.

Through this internship, I gained hands-on experience in data analytics, storytelling, and dashboard development, translating complex datasets into meaningful business insights.

## Project Details:

### Table of Contents:
#### • Flow of work-:

Step 1- Upload Data

Step 2-Cleaning data

Step 3-Transform data

Step 4-Load data

#### • Data Preparation

Data Modelling

Writing DAX

#### • Data Visualization

#### • Data Analysis

#### • Insights

#### 1. Call Centre Trends
Visualizing customer and agent behavior:<br>
Create a dashboard in Power BI for Call Centre Manager that reflects all relevant Key Performance Indicators (KPIs) and metrics in the dataset.

##### •Problem Statement

The purpose of this analysis is to create a dashboard in PowerBI for call canter manager that reflects all relevant Key Performance Indicators (KPIs) and metrics in the dataset. 

Possible KPIs include:

• Overall customer satisfaction

• Overall calls answered/abandoned

• Calls by time

• Average speed of answer

• Agents performance quadrant -> average handle time(talk duration) vs calls answered

##### Flow of work

##### Step 1- Upload Data

The Dataset used for this analysis was presented by PWC Switzerland and available at their official website page.

(I also Uploaded the Dataset in the Task file folder.)

##### Step 2-Cleaning data

Data transformation was done in Power Query and the dataset was loaded into Microsoft Power BI Desktop for modelling.

The call canter dataset is given by a table named:

Call Center; which has 10 columns and 5000 rows of observation.

| Column Name   | Description   | 
|------------|------------|
| Call Id | Represents every unique observation in the dataset| 
| Agent | Describes the name of the agent | 
| Date | Describes the date of the call |
| Time | Represents the time of the call |
| Topic | Describes the topic of the caller |
| Answered | (Y/N) Describes if the call was Answered or not |
| Resolved | Describes if the problem was Resolved or not |
| Speed of answer(in seconds) | Represents the speed of answer in seconds |
| AvgTalkDuration | Represents the average talk duration of call |
| Satisfaction rating | Represents the satisfaction rating of the agent during the call |

##### Step 3-Transform data

Data Cleaning and transformation for the dataset were done in power query as follows:

Unnecessary columns were removed <br>
Each of the columns in the table was validated to have the correct data type <br>
Unnecessary rows were removed

##### Data Visualization

Data visualization for the datasets was done in Microsoft Power BI Desktop:

The Call Center Manager Page: Shows KPIs including overall customer satisfaction, overall calls answered/abandoned, calls by time, average speed of answer, agents performance quadrant -> average handle time(talk duration) vs calls answered.

##### Data Analysis

Measures used in visualization are:<br>
Total Calls = COUNT(Sheet1[Call Id]) <br>
Target_Rating = 4.5 <br>
Avg Speed Answer = DIVIDE(SUM(Sheet1[Speed of answer in seconds]),<br>
                         COUNTROWS(FILTER(Sheet1, Sheet1[Answered (Y/N)]="Y")))<br>
Avg Satisfaction Rating = CALCULATE(AVERAGE(Sheet1[Satisfaction rating]),<br>
                          FILTER(Sheet1, Sheet1[Answered (Y/N)]="Y"))<br>
Avg Handle Time = AVERAGEX(FILTER(Sheet1, Sheet1[Answered (Y/N)]="Y"<br>
                           ),Sheet1[AverageTalkDurationInMinutes])<br>
Answered Calls = CALCULATE(COUNT(Sheet1[Call Id]), <br>
                  Sheet1[Answered (Y/N)]="Y") <br>
Abandoned Calls = CALCULATE(COUNT(Sheet1[Call Id]),  <br>
                  Sheet1[Answered (Y/N)]="N") <br>

Calculated Columns used in visualization are:<br>
Call Hour = HOUR(Sheet1[Time]) <br>
AverageTalkDurationInMinutes = HOUR(Sheet1[AvgTalkDuration]*60 <br>
                              + MINUTE(Sheet1[AvgTalkDuration]) <br>
                              +SECOND(Sheet1[AvgTalkDuration]/60)) <br>

