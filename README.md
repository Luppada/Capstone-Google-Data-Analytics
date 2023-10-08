# Capstone-Google-Data-Analytics
First Capstone Project for the Google Data Analyti cs Certification 

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
Guiding Questions:
● How should you organize your data to perform analysis on it?
- 
● Has your data been properly formatted?
- The data was separated into two dataframes for analysis based on the member type. Then I have created two heatmaps with these dataframes to discover hidden relationships. 
● What surprises did you discover in the data?
- The started_month and ended_month, started_day and ended_day and started_hour and ended_hour do not always have a correlation of 1. 
  
● What trends or relationships did you find in the data?
Bikes are not always returned in the same hour or on the same day sometimes even in the same month.
● How will these insights help answer your business questions?
The return rate of bikes allows us to understand that sometimes users want to use the bikes for a month or even a few days. 

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

In the casual rider dataframe, the minimum value for the ride_time column is negative. This represents an irregularity in the data collection process as the ride time can be only zero at a minimum because time as we know is uniderctional.  For now we will focus removing these values depending how many of these values exist in the dataframe as they might skew further analysis.
I learned that the size of these rows us 117 where the size of the entire dataframe is 48480 rows long. This means that removing these rows will cause a minimal impact to the dataset.

##### Phase 4: Analyze

Surprises, trends and relationships
Summarizr the insights
##### Phase 5: Share
I
Findings, story and audience, accessibility

##### Phase 6: Act
What additional data?
![image](https://github.com/Luppada/Capstone-Google-Data-Analytics/assets/114107498/af127a28-0fdc-4683-beab-4f10a8f006bc)

For e.g. I can use the member ID to detect usage patterns. This can be both casual members or annual members.
Then I can use the member personal info like age groups, professions etc to detect which popuation  
