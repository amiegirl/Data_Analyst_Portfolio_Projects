# Introduction
This case study is a fictitious dataset from a tech company called Atlas Labs and was provided by datacamp for the course "Data Analyst with Power BI".
The dataset provide information about employees hired between 2012 and 2022 
# Objectives
Provide actionable insight for company growth and uncover possible factors responsible for employee attrition.<br>
Entire dataset and dashboard can be found [here](https://app.powerbi.com/links/qvL4Pd4OD_?ctid=8ca3a6b3-2d7d-4262-829b-e19ec50db6ff&pbi_source=linkShare)
# Approach
* Processing and Cleaning the dataset
* Overview:<br>
  identify active and inactive employees.<br>
  Visualize employees hiring trend overtime.<br>
  visualize active employees by department and job role.<br>
* Demographics:<br>
  Identify oldest and youngest employee.<br>
  Visualize employees by age, gender and marital status.<br>
  Visualize average salary by ethnic group.<br>
* Performance Tracker:<br>
  Track employees start date, last review and next review.<br>
  Track employee self rating and manager rating.<br>
  Track employee satisfaction level by job, environment, relationship and work life balance.<br>
* Attrition:<br>
  identify company attrition rate.<br>
  Visualize attrition rate by tenure, overtime requirement and Travel frequency.<br>
  Visualize attrition rate by job role and department.<br>
  Track attrition rate overtime.<br>
  # Data Modelling
* I established relationships between the tables.<br>
![HR Analytics in PowerBI_Model](https://github.com/amiegirl/Data_Analyst_Portfolio_Projects/assets/81017006/7c3ca98c-cbcf-444c-b961-425053298fa0)<br>

* A new table that contain different measures were created and added to the model.<br>
![HR Analytics in PowerBI_CALCULATE_EnvironSatisfaction](https://github.com/amiegirl/Data_Analyst_Portfolio_Projects/assets/81017006/1c924615-55ae-4dfa-9c18-9aeb2844e0e9)<br>
![HR Analytics in PowerBI_CALCULATE_Self_rating](https://github.com/amiegirl/Data_Analyst_Portfolio_Projects/assets/81017006/a5fcc04e-b3cc-4000-892f-abc05a318c59)<br>
![HR Analytics in PowerBI_LastReviewDate](https://github.com/amiegirl/Data_Analyst_Portfolio_Projects/assets/81017006/1fb6b4d8-e4b8-4235-9a1d-920a3d77dc00)<br>
![HR Analytics in PowerBI_NextReviewDate](https://github.com/amiegirl/Data_Analyst_Portfolio_Projects/assets/81017006/7d826986-45f0-4b07-b2fa-a00f06d2159f)<br>

# Dashboard
![HR Analytics in PowerBI_OVERVIEW](https://github.com/amiegirl/Data_Analyst_Portfolio_Projects/assets/81017006/bc151f2f-f777-4660-8809-a793caa0e7a3)<br>
![HR Analytics in PowerBI_DEMOGRAPHICS](https://github.com/amiegirl/Data_Analyst_Portfolio_Projects/assets/81017006/36490274-2b94-4b05-b402-2ebcd73d3fe1)<br>
![HR Analytics in PowerBI_PERFORMANCE TRACKER](https://github.com/amiegirl/Data_Analyst_Portfolio_Projects/assets/81017006/904623a3-5c40-4995-a2ed-0ba7c99d5809)<br>
![HR Analytics in PowerBI_ATTRITION](https://github.com/amiegirl/Data_Analyst_Portfolio_Projects/assets/81017006/a2dba2d8-bbb4-4cbe-aefb-c01e87c4e738)<br>
# Insights and Recommendation
* A total of 1470 employees were hired between 2012 and 2022 with 1233 active employees and 237 inactive employees.
* The most common job role is software engineering which is in the technology department.
* The majority of the employees are aged between 20 and 29 years.
* There are generally more males than females.
* The average salaries of the white and native hawaiian race are higher than other races.
* Sales representatives and recruiters job roles have the highest attrition rate.
* Attrition rate is high among employees that work overtime. Discuss needs to review employees policies on overtime requirements.
* Organize a meeting with employees with low manager ratings to discuss needs and create an improvement plan.
* Frequent travelers have the highest attrition rate of 24.9%. I suggest a review in the travel requirements policies among employees.
