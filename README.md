# Cameramatics

## Challenge
Please have a look at the attached json file which relates to metrics collected which provide insights to driver performance and behavior.

On this platform, users rate our drivers after taking a trip (5-star rating with 1 indicating the lowest level). 

We have collected and summarized a number of key variables and aggregated into scores which are reflective of driver behavior from various perspectives, e.g. safety, profitability, client service etc.  
1. Data ETL: We'd like you to load, diagnose and clean the data, then save the output in a flat CSV file with the following attributes:

"Taxi Group Name" 
"Taxi Division Rank" 
"Driver Full Name" 
"Vehicle Brand"
"Experience Group" 
"Special Awards"
"Endurance Score"
"Profitability Score" 
"Safety Score"
"Efficiency Score"
"#of1Star Ratings"
"#of2Star Ratings"
"#of3Star Ratings"
"#of4Star Ratings"
"#of5Star Ratings"
2. Exploratory Analysis - We think the following distributions would of interest to our clients, please produce the reports accordingly: 

10 best active drivers based on any combination of driver metrics.  
List of any outlier drivers based on metrics for further investigation.
3. Insights (Bonus activity):

Does vehicle type have an influence on client satisfaction? 

## Folder and Files
1. data.json - input json file for the assessment.
2. Q1_Data_ETL.ipynb - Python jupyter file for Data ETL.
3. extracted_data.csv - CSV file with the data after parsing input json file.
4. Q2_3_Analysis.ipynb - Python jupyter file for Analysis of CSV data.
5. Q4_Extra_Data_Modelling.ipynb - Python file for creating different dimensions and fact table based on the input json file.
6. Q4-Extra-EDA.ipynb - Python file for the EDA of data. Here I am using DTale for auto visulization tool that helps getting the idea how data is correlated, description, missing analysis and feature engineering if necessary
7. requirements.txt - Use this file to install all the required libraries for this project.

## Getting Started
To install the libraries used in the project please do the following:
1. Open Terminal:
You can find Terminal in the "Utilities" folder within the "Applications" folder, or you can use Spotlight Search to find it quickly.

2. Navigate to Your Project Directory:
Use the cd command to navigate to the directory where your project is located. For example:
`cd path/to/your/project`

3. Create a Virtual Environment:
Run the following command to create a virtual environment named "env":
`python3 -m venv env`

4. Activate the Virtual Environment:

Activate the virtual environment with the following command:
`source env/bin/activate`

5. Install Libraries from requirements.txt:
Run the following command to install the libraries:
`pip install -r requirements.txt`

6. Verify Installations:
You can verify that the libraries were installed by running:
`pip list`

7. Deactivate the Virtual Environment:
When you're done working on your project, deactivate the virtual environment with:
`deactivate`


## Data ETL and Analysis
1. The given input json file was a string of dictionary without the objects separated by comma. So in the first file, prepared the json before reading it into dataframe.
2. Created different functions to extract the required data from the json file which includes recursive funtion to get to all the employee in the node of the root, teir driver profile and metrics along with the taxi organization they belong to
3. FInally did the analysis of top 10 drivers based on disabled and deleted fields in json to get active drivers, created a composite score and sentiment score based on metrics and sorted by them to get the results
4. Also analysisd the sentiment score with the vehicle brand to get the idea of customer satisfaction based on the brand of vehicle the drivers are driving

## Extra
1. Created and EDA script to get the idea of the dataset, did some plotting to see if there is missing data, fetaure analysis. For this I am using a auto EDA library called DTale which is very handy for getting the idea of your data.
2. Created a data model for the input json file. In this i have created dimensions and fact table that can be used to push data to database to get more insights
