<!-- Centered Cover Page -->

<div align="center">

# Project - Part #1  
## AWS Data Analytic Platform for The City of Vancouver  
 
Jaykishan Ashokkumar Patel (2237183)  

University Canada West  
BUSI 653: Cloud Computing Technologies (HBD-SUMMER24-07)  
Mahmood Mortazavi Dehkordi  
August 27, 2024  

</div>

---

# Abstract
This report presents the implementation of the Data Analytic Platform (DAP) for the City of Vancouver. The report covers the DAP design and implementation for four datasets from the City of Vancouver’s Open Data Portal:

1. 3-1-1 Service Requests Regarding "Abandoned Non-Recyclables—Small Case"
2. Business Licences in Downtown Vancouver
3. Animal Control - Lost and Found
4. Rental Standards

The proposed platform uses services provided by AWS, including S3 for data storage, AWS Glue for ETL processes, Athena for data analysis using SQL, and EC2 instances with Apache for data publishing. Key procedures like data ingestion, data cleaning, data structuring, and analysis were incorporated into the platform to improve the current system. The project is easily expandable and inexpensive to implement, with an estimated annual cost of USD 413.76, which is feasible and beneficial to improve the efficiency of waste management and decision-making.

---

# Contents

<h1 align="center">Abstract</h1>

This report presents the implementation of Data Analytic Platform (DAP) for the City of Vancouver. The report covers the DAP design and implementation for four datasets from the City of Vancouver’s Open Data Portal:

1. 3-1-1 Service Requests Regarding "Abandoned Non-Recyclables—Small Case"
2. Business Licences in Downtown Vancouver
3. Animal Control - Lost and Found
4. Rental Standards

The proposed platform uses services provided by AWS, S3 for data storage, AWS Glue for ETL processes, and Athena for data analysis using SQL and EC2 instances with Apache for data publishing. Key procedures like data ingestion, data cleaning, data structuring, and analysis were incorporated into the platform for the benefit of the current platform. The project is easily expandable and inexpensive to implement, with an approximate annual price tag of USD 413.76, which is reasonable and can be implemented to improve the effectiveness of waste management and the efficiency of decision-making.

---

<h2 align="center">Contents</h2>

- **Abstract** ............................................................ Page 2
- **Introduction** ........................................................ Page 5
- <strong>DAP Design and Implementation (Steps 1-13) by Ugochukwu Nwosu</strong>
  - Step 1: Data Analytical Question Formulation ..................... Page 7
  - Step 2: Data Discovery ................................................. Page 8
  - Step 3: Data Storage Design ........................................ Page 10
  - Step 4: Dataset Preparation ....................................... Page 11
  - Step 5: Data Ingestion (Pull data into Operational Environment) ..... Page 11
  - Step 6: Data Storage ................................................. Page 13
  - Step 7: Data Pipeline Design ........................................ Page 15
  - Step 8: Data Cleaning ................................................. Page 17
  - Step 9: Data Structuring ............................................. Page 20
  - Step 10: Data Pipeline Implementation (ETL) ...................... Page 20
  - Step 11: Data Analysis ............................................... Page 22
  - Step 12: Data Visualization .......................................... Page 24
  - Step 13: Data Publishing ............................................ Page 25
- <strong>DAP Design and Implementation (Steps 1-13) by Gurleen Kaur Khosa</strong>
  - Step 1: Data Analytical Question Formulation .................... Page 27
  - Step 2: Data Discovery ................................................. Page 29
  - Step 3: Data Storage Design ......................................... Page 29
  - Step 4: Dataset Preparation ........................................ Page 32
  - Step 5: Data Ingestion ................................................. Page 34
  - Step 6: Data Storage ................................................. Page 35
  - Step 7: Data Pipeline Design ........................................ Page 36
  - Step 8: Data Cleaning ................................................. Page 39
  - Step 9: Data Structuring ............................................. Page 40
  - Step 10: Data Pipeline Implementation .......................... Page 43
  - Step 11: Data Analysis ................................................ Page 47
  - Step 12: Data Visualization .......................................... Page 49
  - Step 13: Data Publishing ............................................. Page 51
- <strong>DAP Design and Implementation (Steps 1-13) by Lam Thi Thu Thao</strong>
  - Step 1: Data Analytical Question Formulation .................... Page 54
  - Step 2: Data Discovery ................................................. Page 54
  - Step 3: Data Storage Design ......................................... Page 56
  - Step 4: Dataset Preparation ........................................ Page 57
  - Step 5: Data Ingestion ................................................. Page 59
  - Step 6: Data Storage ................................................. Page 61
  - Step 7: Data Pipeline Design ........................................ Page 64
  - Step 8: Data Cleaning ................................................. Page 66
  - Step 9: Data Structuring ............................................. Page 67
  - Step 10: Data Pipeline Implementation .......................... Page 69
  - Step 11: Data Analysis ................................................ Page 70
  - Step 12: Data Visualization .......................................... Page 72
  - Step 13: Data Publishing ............................................. Page 73
- <strong>DAP Design and Implementation (Steps 1-13) by Jaykishan Ashokkumar Patel</strong>
  - Step 1: Data Analytical Question Formulation .................... Page 75
  - Step 2: Data Discovery .................................................. Page 76
  - Step 3: Data Storage Design ......................................... Page 77
  - Step 4: Dataset Preparation ......................................... Page 77
  - Step 5: Data Ingestion ................................................. Page 78
  - Step 6: Data Storage ................................................... Page 79
  - Step 7: Data Pipeline Design ........................................ Page 79
  - Step 8: Data Cleaning .................................................. Page 80
  - Step 9: Data Structuring .............................................. Page 81
  - Step 10: Data Pipeline Implementation .......................... Page 81
  - Step 11: Data Analysis .................................................. Page 82
  - Step 12: Data Visualization ............................................ Page 83
  - Step 13: Data Publishing ............................................. Page 83
- **DAP Estimated Cost** .................................................. Page 84
- **Conclusion** .......................................................... Page 85
- **References** ........................................................... Page 87
---

<h1 align="center">AWS Data Analytic Platform for The City of Vancouver</h1>

<h2 align="center">Introduction</h2>

The City of Vancouver is in an advantageous place where the proper use of data can further improve decision-making, public services, and usage of resources. The establishment of the Data Analytic Platform (DAP) is essential for the city because it provides a foundation for the integration, processing, and visualization of a massive amount of data received from different sources. Through this platform, city officials can make the right decisions for the city's betterment by considering the analyzed data on the people’s quality of living, improved service delivery, and enhanced city planning.

The value of the DAP is in its capacity to turn masses of data into usable information. Such information, gathered from different departments, can give an overall picture of the city’s functioning, reveal trends, and anticipate and plan for issues that may crop up in the future. Furthermore, a successful DAP can also help increase transparency and accountability so the city can report its achievements and programs well to the public.

The table below shows the steps that the City of Vancouver needs to take to implement its comprehensive Data Analytic Platform, which will support its mission to improve city operations and enhance the well-being of its residents.

To be able to implement and migrate a data analytic platform for The City of Vancouver to AWS, we have designed and implemented it based on the 13 steps below:

<h3 align="center">Table 1: Steps for Designing and Implementing the Platform</h3>

| Steps                          | Description |
|---------------------------------|-------------|
| **Data Analytical Question Formulation** | Identifying critical questions, the platform needs to answer, aligning with the city's strategic goals. |
| **Data Discovery**              | Identifying and gathering relevant datasets from various sources within the city's departments. |
| **Data Storage Design**         | Designing a robust storage solution, including data lakes, databases, and warehouses. |
| **Dataset Preparation**         | Cleaning and formatting data to ensure consistency and accuracy before ingestion. |
| **Data Ingestion**              | Ingesting prepared data into the platform using methods like batch processing or real-time streaming. |
| **Data Storage**                | Storing ingested data in designed storage solutions for easy access and analysis. |
| **Data Pipeline Design**        | Designing pipelines to automate data extraction, transformation, and loading (ETL). |
| **Data Cleaning**               | Further cleaning data within the platform to maintain quality and remove inconsistencies. |
| **Data Structuring**            | Structuring data into optimal formats and creating data models for analysis. |
| **Data Pipeline Implementation**| Implementing designed pipelines to ensure continuous and efficient data processing. |
| **Data Analysis**               | Extracting insights from structured data using analytical tools and methods. |
| **Data Visualization**          | Visualizing analysis results through dashboards and reports for easy understanding and action. |
| **Data Publishing**             | Publishing insights and visualizations, making them accessible to stakeholders for decision-making. |

This structured approach ensures that the data analytic platform is both comprehensive and scalable, meeting the city's current and future data needs.

# Data Analytic Platform (DAP) for City of Vancouver

## Overview

This project focuses on designing and implementing a Data Analytic Platform (DAP) for the City of Vancouver. The platform aims to enhance the efficiency of waste management and business license issuance processes through detailed data analysis.

## Dataset 1: 3-1-1 Service Requests Regarding “Abandoned Non-Recyclables—Small Case” (By Ugochukwu Nwosu)

### Step 1: Data Analytical Question Formulation

Define the data analytical questions to address issues within the Recycle BC department, focusing on abandoned non-recyclable items. The goal is to:
- Increase response times
- Decrease the rate of abandoned items
- Enhance city cleanliness and resident satisfaction

**Descriptive Analysis Approach**: Answer the question, "What happened with the abandoned non-recyclable service requests in 2022?"

### Step 2: Data Discovery

The dataset includes 3-1-1 service requests related to "Abandoned Non-Recyclables—Small Case". It contains:
- Service delivery requests from residents
- Focus on small cases of abandoned non-recyclables

**Figure 1**: The Datasets from the Open Data Portal in the City of Vancouver

### Step 3: Data Storage Design

Use Amazon S3 for data storage:
- Bucket Name: `RecycleBC-AbandonedNonRecyclables`
- Structure: Folders for 2023 and 2024

**Figure 2**: The S3 Bucket with the 2023 and 2024 Folders

### Step 4: Dataset Preparation

Prepare data for analysis:
- Focus on years 2023 and 2024
- Highlight contemporary issues in waste management

**Figure 3**: The Downloaded Datasets in The Local Environment

### Step 5: Data Ingestion (Pull data into Operational Environment)

Move prepared datasets into Amazon S3:
- Data uploaded to `RecycleBC/AbandonedNonRecyclables/2023/Landing/ServiceRequests` and `RecycleBC/AbandonedNonRecyclables/2024/Landing/ServiceRequests`

**Figure 4**: The Dataset Files Pulled into the Operational Environment

### Step 6: Data Storage

Organize data into folders:
- `Landing` for raw data
- `Raw` for cleansed data
- `Curated` for processed data

**Figure 5**: The Landing, Raw, and Curated Folders hold the Initial, Raw, and Processed Data

### Step 7: Data Pipeline Design

**Figure 6**: The Data Pipeline

### Step 8: Data Cleaning

Use AWS Glue DataBrew for cleaning:
- Project focused on Recycle BC
- Validate and clean data

**Figure 7**: The Projects Created with the Respective Jobs After Cleaning

### Step 9: Data Structuring

Transform data to fit analysis requirements and move to the `Raw` folder.

### Step 10: Data Pipeline Implementation (ETL)

Use AWS Glue for ETL:
- Automate data flow and transformation

**Figure 8**: The Project’s Visual ETL

### Step 11: Data Analysis

Analyze data with Amazon Athena:
- Run SQL queries to identify patterns, trends, and regional data

**Figure 9**: The Query Results

### Step 12: Data Visualization

**Figure 10**: The Graph Showing the Channels Used in Making these Reports

### Step 13: Data Publishing

Host results on Amazon EC2 with Apache:
- Provides scalable and secure access to analysis results

**Figure 11**: The EC2 Instance and the Web Server Process

## Dataset 2: Business Licences in Downtown Vancouver (By Gurleen Kaur Khosa)

### Step 1: Data Analytical Question Formulation

Formulate questions to improve:
1. Business licenses issuance
2. Delay reasons
3. Renewal likelihood
4. Proactive renewal reminders

**Step 2: Data Discovery**

Organize and understand data for business licenses.

**Step 3: Data Storage Design**

Create S3 bucket and folders:
- Bucket Name: `business-businesslicences-gurleen`
- Structure: Folders for each year and data type

**Step 4: Dataset Preparation**

Prepare and arrange data from the Open Data Portal for 2023 and 2024.

**Step 5: Data Ingestion**


 
 

Step 6: Data Storage
Data storage is an essential step in data analytics platforms. It involves storing the collected data into folders of S3 buckets for efficient access and analysis. After gathering data from open data portal, it is then stored to the landing environment of S3.

Step 6: Data Storage
 

Step 7: Data Pipeline Design
	The Data Pipeline design step is about planning how data will travel through the system, from where it starts to where it ends up. This includes deciding how data will be collected, processed, changed, and stored. The aim is to make sure data moves smoothly and is ready for analysis. I created visual representation of my ETL pipeline in draw.io using tables showing various stages of my design such as removing, filtering, extracting and grouping stage and then finally, reaching to my final outcome table showing “Licence Issuance Rate” calculations for year 2024 and 2023.

Step 7: Data Pipeline Design
     

Step 8: Data Cleaning
In this step cleaned up the dataset of business licences application records in an AWS S3 bucket. The steps involve creating raw folder inside landing zone and and then using a data cleaning tool called AWS Glue DataBrew, I created a project. The project then cleaned the data by removing invalid, null or missing values using function feature inside it depending upon the percentage of missing values in the column, which will ensure the accuracy of any future analysis performed on the data. If had more than 80% missing values, I dropped that column because it was of no use.

Step 8: Data Cleaning
 
 

Step 9: Data Structuring
	In this step, I arranged my data in structured manner meaning renamed columns names with relevant names with respect to the information they hold in them. Furthermore, I configured “Schema” in AWS Glue DataBrew to ensure whether my dataset had relevant datatypes for specific columns and if not changes them accordingly. Furthermore, I created and ran my job and stored the result of my cleaning and structuring inside the raw folder of my S3 bucket.

Step 9: Data Structuring
 
 
   

Step 10: Data Pipeline Implementation
	This step involves creation of visual ETL using AWS Glue service. This step provides us with the summarized information for our analysis. In this step, I fetched data from my raw folder (cleaned and structured data) and then performed certain operations to that dataset to extract specific information. I used aggregation, filter and change schema to retrieve specific information from my dataset. Then I used to join function to group my dataset and performed average calculation on my dataset to get “Licence Issuance Rate” for year 2024 and 2023 using columns “Number of business licence issued per year” and “Total number of business licence applications initiated”.
Licence Issuance Rate = (Number of business licence issued per year/ Total number of business licence applications initiated) *100
Finally, I run my job, and my results were stored in the curated folder of my S3 bucket.

Step 10: Data Pipeline Implementation
     
 
 

Step 11: Data Analysis
	The AWS service used for executing this step is Amazon Athena. This step involved analyzing the summarized curated folder data from S3 bucket by creating tables for specific CSV files. The table contained columns such as Year and LIR (Licence Issuance Rate) for the years 2023 and 2024. After table creation, I ran SQL queries to retrieve specific information from the table using SQL “ORDER BY”, “SELECT” and various other queries.

Step 11: Data Analysis
  
  

Step 12: Data Visualization
	In this step, I created visualizations for my Athena downloaded data file for Licence Issuance Rate containing 2024 and 2023 data. I made my visualizations for this step in excel using recommended charts and then downloaded that file in pdf format and renamed it as Graph_Report.

Step 12: Data Visualization
 
 

Step 13: Data Publishing
	AWS EC2 service was used to execute this step. This step involved publishing your data files to general and web servers to be accessible by the public. To do this step, I created two EC2 instances, one for general server and another one for web server. For connecting my instances, I used “Remote desktop connection” inbuild software in windows and uploaded my files to remote computer in analysis folder in C-Drive for general server and in wwwroot folder for web server and then using public IP address, I accessed my uploaded files on the web browser.

Step 13: Data Publishing
 
    

Dataset 3: Animal Control - Lost and Found (By Lam Thi Thu Thao)
DAP Design and Implementation (Steps 1- 13)
Step 1: Data Analytical Question Formulation
In the Animal Control department, identify the Data Analysis Question Formulation needs a data analytics platform to find its goal and answer 4 types of data analysis questions regarding lost and found animals. These questions will guide how/what data we collect/process, as well as who or which department analyzes the data. Also, what decisions or actions the City of Vancouver might take based on this analysis?

 
Picture 1: Data Analytical Question Formulation

Step 2: Data Discovery
This includes an in-depth exploration of all operational environments to identify and locate all datasets relevant to answering the questions that will have been formulated in Step 1.
This includes the identification, assessment, and preparation of datasets for migration to AWS. Specifically:
•	Lost Animal Information 2023-2024: Information about the animals reported to be lost, together with their descriptions, dates, IDs, names, and statuses.
•	Vancouver Animal Control Office Analysis: Reports and metrics for internal use on handling lost animal cases.
•	Register Reports: Time sheets of historical records of cases related to lost animals.
•	Animal Services Staff Data: Information on the activities of staff, their performance, and preventive measures.

 
Picture 2: Data Discovery

Step 3: Data Storage Design
In Step 3, Data Storage Design focuses on organizing and securely storing datasets in AWS S3. In this step, I set up dedicated AWS S3 buckets to store different types of data related to the Lost and Found Animals domain.
•	Bucket Name: animalcontrol-lostandfound-lamthithuthao
•	Folder: Landing/2023 – This could contain subfolders like "Lost Animal Information 2023," "Register Reports," and "Vancouver Animal Control Office Analysis."
•	Folder: Landing/2024 – Similarly, this would store data for the year 2024, such as "Lost Animal Information 2024" and other relevant datasets.

 
Picture 3: Data Storage Design - Landing/2023

 
Picture 4: Data Storage Design - Landing/2024

Step 4: Dataset Preparation
Basically, Data Preparation is the process of organizing and converting in structured format the raw data obtained, which will then make it ready for uploading and analysis on AWS.
For this, I downloaded the following two Lost and Found Animal data Excel files for the years 2023 and 2024 from the City of Vancouver data website. Due to the rest of the data being unavailable to be extracted for this assignment, I used ChatGPT to obtain the sample data in CSV format, which is created with 10 columns and 5 rows. The sample dataset contains very relevant fields to the needed attributes in analysis, such as animal IDs, report dates, and statuses, among other key fields. Below are the areas these datasets covered:
•	Animal Services Staff
•	Analyzing the Vancouver Animal Control Office
•	Members of Staff in the Vancouver Animal Control Office
•	Register Reports.
After generating the sample datasets, I saved all the CSV files in Excel format. In this way, it will facilitate more convenient manipulation, review, or sharing with team members or stakeholders.

 
 Picture 5: Dataset Preparation - 2023

 
Picture 6: Dataset Preparation - 2024

Step 5: Data Ingestion
The main objective of Data Ingestion is to successfully and accurately migrate the prepared datasets from Step 4 into their corresponding homes within the AWS - S3 bucket. To ingest data, I followed a technique of uploading the datasets by adding files to previously created folders for each year in the Landing zone: 2023 and 2024. After uploading each dataset, I verified the upload status to ensure that each dataset was uploaded to the correct folder and transferred with no errors.

 
Picture 7: Data Ingestion

 
Picture 8: Data Ingestion

 
Picture 9: Data Ingestion

 
Picture 10: Data Ingestion

Step 6: Data Storage
After successfully completing the upload of the datasets in Step 5, a logical follow-through would be to identify appropriate storage classes in the Properties section depending on usage patterns, helping in finding a balance between cost efficiency and performance regarding data readiness in read and write mode, as may comparatively be required for processing by the City of Vancouver's Animal Control.
The datasets were organized into specific folders within the S3 bucket structure:
•	Vancouver Animal Control Office Staff 2024 in Standard class
•	Vancouver Animal Control Office Analysis 2024 in Standard class
•	Register Reports 2024 in Standard class
•	Lost and Found Animal Information 2024 in Standard class
•	Animal Services Staff 2024 in Standard class

 
Picture 11: Data Storage

 
Picture 12: Data Storage

 
Picture 13: Data Storage

 
Picture 14: Data Storage

 
Picture 15: Data Storage

Step 7: Data Pipeline Design
In Step 7, Data Pipeline Design, I created a graphical representation of the ETL process with a Data Lineage Diagram. The diagram illustrates the flow of the data from its extraction stage to the final calculation of the Lost Animal Reporting Rate. I used ChatGPT to create in writing the formula that calculates the metric from the transformed data: Lost Animal Reporting Rate. The final rate output has the benefit of enabling the City of Vancouver to understand how ground-level lost and found animal management processes are effective.

 
Picture 16: Lost Animal Reporting Rate Formula

 
Picture 17: Data Design Pipeline

Step 8: Data Cleaning
In this step, I cleaned the Lost Animal Information dataset within the 2024 folder, ensuring that there are no invalid or missing values in the data, which could affect the accuracy of any analysis performed later.
•	In the 2024 folder in S3 bucket, I created a new folder named Raw.
•	Inside the Raw folder, I created another folder named Lost_Animal_Information to store the unprocessed data.
•	Then, I used AWS Glue DataBrew to create a project and set the project name to animalcontrol-lostandfound-cleaning-lamthithuthao
•	New dataset details: animalcontrol-lostandfound-information-lamthithuthao
•	Selected the path for the new data set: AnimalControl > LostAndFound > 2024 > Landing > Lost Animal Information folder.
After setting up the project, I received the project details for 6 columns in the dataset.

 
Picture 18: Data Cleaning

Step 9: Data Structuring
I renamed the columns in the Lost Animal Information dataset to make them more descriptive and aligned with the specific context of the Lost and Found Animal domain.
•	Breed => LostAnimalBreed
•	Color => LostAnimalColor
•	Date => LostAnimalDate
•	Name => LostAnimalName
•	Sex => LostAnimalSex
•	State => LostAnimalState
Then, I clicked on SCHEMA in AWS Glue DataBrew to review the structure of the dataset and verify that all columns were correctly identified and there were no schema-related issues.
Afterward, I created a job to finalize the structuring process, storing the newly organized dataset in the appropriate Raw folder of the S3 bucket year 2024.

 
Picture 19: Data Structuring

Step 10: Data Pipeline Implementation
In this step, I began by creating a new AWS Glue job, naming it AniContrl-LostInfor-ETL-ThiThuThao
I added some features to the ETL, such as:
•	Aggregate and filter function: to focus on relevant information.
•	Rename columns and standardizing formats.
•	Join function to merge datasets where necessary to enrich the data.
After finishing, the final, cleaned, and transformed data was saved back into a new S3 bucket, under the Curated folder. Also, the transformed data was stored in the Lost-Animal-Information-Reports folder.

 
Picture 20: Data Pipeline Implementation

 
Picture 21: Data Pipeline Implementation - Curated folder

Step 11: Data Analysis
In this step, I used Amazon Athena to analyze the curated data from the Lost and Found Animal project.
•	Firstly, I created a new table named animalcontrol_lostandfound_table19_lamthithuthao 
•	Then, I created a new database named: animalcontrol_lostandfound_database19_lamthithuthao
•	The dataset used was from the Lost-Animal-Information-Reports folder within the Curated directory.
•	The table included key columns such as Year and APR (Annual Percentage Rate)
After setting up the table, I ran several queries to extract insights. For instance, I queried the database to list all lost animal records, sorted by their unique ID.

 
Picture 22: Data Analysis – Amazon Athena

Step 12: Data Visualization
In this final step, I focused on visualizing the results of the Lost Animal Reporting Rate analysis. The process was as follows:
•	I downloaded the APR_Per_Year.csv file (in step 11), which contains the Animal Reporting Rate (APR) for the year 2024, and uploaded it to a Google Excel
•	Using Google Sheets, I created a simple bar chart to represent the APR value visually. The bar chart displayed the APR on the X-axis and the year 2024 on the Y-axis.
•	After finalizing the visualization, I exported the Google Excel document as a PDF file, ensuring that the report was easy to share and present.
•	The file was named Graph Report_LamThiThuThao.pdf to reflect its content and origin.

 
Picture 23: Data Visualization

