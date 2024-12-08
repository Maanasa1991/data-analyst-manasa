EXPLORATORY DATA ANALYSIS

Project Description: Exploratory Data Analysis (EDA) on Building Permits for the city of Vancouver

Project Title: AWS Data Analytic Platform for the City of Vancouver

Objective: The primary goal of this project is to perform an exploratory data analysis (EDA) on Building Permits for the city of Vancouver dataset to uncover patterns, trends, and insights related to permissions given by authorities based on different categories. By analyzing various features such as Permit Number, permit elapsed days, project value, type of work, permit category, property use and location. We aim to understand the factors that influenced the likelihood of number of permissions given by City of Vancouver.

Dataset: The building permits dataset consists of applicant information from the applications received to get the permits, including details such as:

•	Permit Number: Unique identifier for each applicant

•	Permit Number Created Date: When the permit number has created

•	Permit Elapsed Days: Within how many days the permits are going to be elapsed

•	Project Value: The value of the building

•	Permit Category: Renovation - Renovation/ Demolition/ completed

•	Geo Local Area - The location of the building

Methodology:

1-	Data Collection and Preparation:

Downloaded the dataset from the below website link:
https://opendata.vancouver.ca/explore/dataset/issued-building-permits/information/?refine.issuedate=2024&refine.geolocalarea=Kensington-Cedar+Cottage&refine.specificusecategory=Single+Detached+House&dataChart=eyJxdWVyaWVzIjpbeyJjaGFydHMiOlt7InR5cGUiOiJsaW
<img width="451" alt="image" src="https://github.com/user-attachments/assets/190523f1-d9d3-41f9-8028-0af6ce58ba17">

•	Design the DAP using draw.io

<img width="452" alt="image" src="https://github.com/user-attachments/assets/066bc6ff-1c71-4187-bad1-006c062676ff">

It explains a Data Analytic Platform using AWS services for the City of Vancouver. In this I used average of both the series to find the average project value for the building permits dataset.  Initially, raw dataset is stored in Amazon S3 bucket (van-bp-raw-maan), By using AWS data brew services I did the profiling by creating project (vc-bp-prf-maan) and then cleaning job by using filter functions creating a job by using the profiled dataset (vc-bp-prj-job-maan). We can check and change by using recipe option. Once it is done, by using Data Glue service I created a visual ETL for pipeline design (vc-bp-ea-etl-maan). At the end the desired will be stored in S3 transformed bucket(vc-bp-trf-maan).

1. Data Ingestion:
   
<img width="451" alt="image" src="https://github.com/user-attachments/assets/8daa30e9-ee54-464f-ba4a-1bd18ddb72c2">

I used this step to store my raw dataset which contains building permits. Created one bucket(van-bp-raw-maan) in S3, so I can access my dataset anytime easily.

2. Data Profiling:
   
   <img width="451" alt="image" src="https://github.com/user-attachments/assets/92a6fb74-3d85-4f42-9e23-a9aed0aff8d3">
   
  In Data Profiling step, used the AWS Data Brew service to profile the raw data. It mainly involves assessing the dataset quality by identifying any missing values, duplicate values. The output of the file is in json format, it is stored in S3 transformed bucket(vc-bp-trf-maan) in Data profiling folder.
  
3.Data Cleaning:

Data cleaning for user:

<img width="452" alt="image" src="https://github.com/user-attachments/assets/a0d6959e-41df-41b5-a6a6-42586be77fb5">

Data cleaning for system:

<img width="451" alt="image" src="https://github.com/user-attachments/assets/a898a1d1-0f19-4d80-8d27-e9fbe7418127">

In Data cleaning, first step is to create separate folders for User and System in S3 under Transform bucket. In System the file type is parquet and snappy compression, For User I used CSV format compression none. Once profiling is done, by using that data created one project and, in that project, prepared some recipes to clean the dataset. My dataset has no missing values, so I created recipes for some of the columns which has numbers in it to make sure there will be no white spaces. I published the recipe as well. After applying the recipes, now the dataset is accurate, reliable and free of errors. The cleaned data sets are stored back in S3.

4. Pipeline Design:
   
 <img width="452" alt="image" src="https://github.com/user-attachments/assets/3049b044-5e11-4339-a3e5-dc40f52d5918">

  For this step, I used AWS Data Glue service. Created a visual ETL by using functions like Amazon S3 to extract the dataset, then for transform I applied Change schema, Aggregate and Filter options. Then I used join function to merge the datasets, Then applied the formula to calculate the average of Project Value by using the pipeline design. It is accurate and efficient way to get the results. I stored the results from this again in S3 but this time in transformed bucket.
  
Conclusion:

By using AWS services, I have gotten the average of the project value for buildings in City of Vancouver. I can calculate more by changing the pipeline design according to my requirements.	

Tools and Technologies used:

•	AWS - S3 - AWS Brew - AWS Glue - AWS Athena
Conclusion:
o	Discuss the implications of the findings and suggest further analyses or data-driven decisions that could be explored, such as building predictive models to classify survival based on passenger features.
	This EDA project not only demonstrates my analytical and programming skills but also highlights my ability to derive meaningful insights from data, making it a valuable addition to my data analyst portfolio.













# data-analyst-manasa
