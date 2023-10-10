# Capstone-Google-Data-Analytics
First Capstone Project for the Google Data Analytics Certification 

#### **Author**: Likhith Sri Vatsa Uppada  

[More about me](https://www.linkedin.com/in/likhith-sri-vatsa-uppada-34b89a236/)

**Start Date**: October 5, 2023.

**End Date**: Work in Progress


#### Background

A data analyst(me) is working in the marketing analyst team of a Chicago-based bike-share company called Cyclistic. This company provides both annual memberships and casual (single-ride or full-day) passes. The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. The Data Analyst is tasked to create an analysis and report their insights. These insights will be used to support design a new marketing strategy to convert casua riders into annual members. Visuals will play a key role in having the new strategy approved by Cyclistic Executives.

##### Phase 1: Ask

**Identifying Stakeholders**

Stakeholders: Lily Moreno (Director of Marketing and Manager), Cyclistic executive team

**Business Task**

Analyze the data collected by Cyclistic to differentiate the bike usage between casual riders and annual customers.  

##### Phase 2: Prepare

**Dataset**
The dataset used is named as 'Divvy_Trips_2020_Q1.zip', downloaded from [this webpage](https://divvy-tripdata.s3.amazonaws.com/index.html). 

Upon downloading the zip file it is extracted and renamed as 'Trips_2020_Q1'. This dataset consists of data collected in the first quarter of 2020 (January to March).  While there are many other sources, I wanted to use the latest data that is collected for longer period of time as it can provide more insights that will allow a better understanding of how the riders are using Cyclistic bikes. 
Dataset features:
Types of errors:


##### Phase 3: Process

Data Integrity and Cleaning

After extracting the file, I have tried to open it using excel. FYI, the size of this file is 69 MB and it has over 40,000 rows. This caused a heavy load on the excel software. Therefore, I have decided to use the Pandas package in the Python to check the data integrity and for any additional processing required. Jupyter Notebook is the platform I have used to look for data integrity.

I will add the ipynb file to my for reference. 

Upon initial inspection, I have noticed that there are a two columns that have null values. Upon inspection, it was clear that only one row has missing values at in the end_station_name and end_station_id columns. I have removed this row from the dataset. 

 Then I moved forward to check how many columns have unique values less than 10 (It is an aribitrary value) to check for any attributes that we must analyze. 

 It turns out that there are only two such columns. 
 1. rideable_type - The unique values are:  ['docked_bike']
 2. member_casual - The unique values are:  ['member' 'casual'] - Refers to the type of bike user. 

Then I converted the date in 'started_at' and 'ended_at' columns into datetime datatype from object datatype.

Then I split these columns based on the month, day and hour for future analysis.
As the data is now close to being ready for analysis, I split the data based on member_casual type. 

Then I used the describe function to ensure that the everything is set to move forward with analysis.
The minimum value for the ride_time column is negative. This represents an irregularity in the data collection process as the ride time can be only zero at a minimum because time as we know is uniderctional.  For now we will focus removing these values depending how many of these values exist in the dataframe as they might skew further analysis.
I learned that the size of these rows us 117 where the size of the entire dataframe is 48480 rows long. This means that removing these rows will cause a minimal impact to the dataset.

Then I created two dataframes from the original dataframe based on the member_casual type for simpler processing.

##### Phase 4: Analyze

I have started the analysis process trying to understand the basic information, that any stakeholder will want to know. For example, the total number of bike rides in the quarter, by the month etc.

Then I have used correlation on all three dataframes (df, casual dataframe and member dataframe). I have used heatmaps to represent the variation in the correlation values.

The started_month and ended_month, started_day and ended_day and started_hour and ended_hour do not always have a correlation of 1. This means that the bikes are not always returned in the same hour or on the same day sometimes even in the same month.
● How will these insights help answer your business questions?
The return rate of bikes allows us to understand that sometimes users want to use the bikes for a month or even a few days. 

While I have used the visuals in python for analysis, I want to create my final dashboard and visuals using Tableau as it provides more aesthetic control and options for visuals.

##### Phase 5: Share

The audience - The executive team wants to know how the differently the casual members and annual members behave. We know that they are detail oriented. Giving them an option to navigate and assess changes through various features like member type and month will be useful.


The story - 

 Cyclistic recorded 426770 bike rides started in their first quarter. Out of that 48,363 rides were started by casual riders and the remaining 378,407 rides were started exclusively by the annual members.

The riders use the bikes with varying ride time that ranges from under a month to over three months. 

Below chart represents how many rides were initiated by the customers in each month of the quarter.

![image](https://github.com/Luppada/Capstone-Google-Data-Analytics/assets/114107498/95d4b3f6-9a4e-494d-9551-2fc50ee63b97)

Below chart represents how many rides were initiated by the customers in each month of the quarter.

![image](https://github.com/Luppada/Capstone-Google-Data-Analytics/assets/114107498/e908f5ec-a802-4e9f-91f1-09a158124ba3)

Below chart represents how many rides were initiated by the customers each calendar date of the month.

![image](https://github.com/Luppada/Capstone-Google-Data-Analytics/assets/114107498/dd43f135-8942-4589-b93d-0ccc7fae5fb1)

Below chart represents how many rides were initiated by the customers each hour of a day.

![image](https://github.com/Luppada/Capstone-Google-Data-Analytics/assets/114107498/0aff7192-2a69-416f-9c20-f0e0e586a5c8)

Below charts represent the ride times and the number of people using the bikes for that amount time.

Ride time in Days:
![image](https://github.com/Luppada/Capstone-Google-Data-Analytics/assets/114107498/ef7724cf-f052-46d9-b7a7-b588c90de84f)

Ride time in Hours:
![image](https://github.com/Luppada/Capstone-Google-Data-Analytics/assets/114107498/83492ec9-3b8c-48d9-95b3-94e13058403f)

Ride time in minutes:

![image](https://github.com/Luppada/Capstone-Google-Data-Analytics/assets/114107498/e20dddf6-38ff-44ac-be97-3f1abbf02ea5)

The following image shows the density of rides started by casual members in each station. 

![image](https://github.com/Luppada/Capstone-Google-Data-Analytics/assets/114107498/7a5ce9ac-c1b5-4cef-8ec0-f12d4c6dcbb4)

The following image shows the density of rides ended by casual members in each station. 

![image](https://github.com/Luppada/Capstone-Google-Data-Analytics/assets/114107498/370db1b5-f5f3-4ef5-8583-48de944e4c78)

The following image shows the density of rides ended by annual members in each station.

![image](https://github.com/Luppada/Capstone-Google-Data-Analytics/assets/114107498/1d5db379-16c8-45d3-97b7-a15aee4e931c)

The following image shows the density of rides started by annual members in each station. 

![image](https://github.com/Luppada/Capstone-Google-Data-Analytics/assets/114107498/317e442e-fd40-4c21-bc78-738f96a912aa)


##### Phase 6: Act

Insights:

- On many levels annual users are bike usage is greater than that of casual users.
- The number of rides started by casual users is increasing by the month.
- THe 

A critical part of data that is missing is the member ID. While we are able to identify the type of member, having a unique member ID, whether casual or annual member, will be helpful in understanding how often these members are returning to our services, predict churn and retaining them as well.

For e.g. I can use the member ID to detect usage patterns. This can be both casual members or annual members.

One can use the member personal information of members, such as age groups, professions, to detect which groups are morelikely to use this service.  
 
Few dates/weeks have particularly high numbers. An understanding of local events will help plan better to serve the customers. 
