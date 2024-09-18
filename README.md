<!-- Centered Cover Page -->

<div align="center">

![image](https://github.com/user-attachments/assets/e66360ef-8d7c-4422-bc76-e359d30be61a)

# Project - Part 1  
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

# Dataset 2: Business Licenses in Downtown Vancouver

## DAP Design and Implementation (Steps 1-13)

### Step 1: Data Analytical Question Formulation
Formulating data analytical questions involves setting clear goals and identifying the right data to answer specific business needs. This step ensures that the analysis focuses on the right areas, helping to draw useful conclusions and take informed actions based on the data.

The breakdown of the data analysis process to improve business license issuance and compliance in Downtown Vancouver is as follows:
1. **Descriptive Metric**: Understand the current situation by analyzing the number of business licenses issued per year. *Question*: How many business licenses are issued per year?
2. **Diagnostic Metric**: Identify the reasons for business license delays by analyzing data about the reasons for the delay. *Question*: Why are there delays in issuing licenses?
3. **Predictive Metric**: Predict the likelihood of a business license renewal by analyzing past renewal patterns and influencing factors. *Question*: How likely is a business license to be renewed?
4. **Prescriptive Metric**: Recommend proactive actions to improve renewal reminders by analyzing data about successful reminders and developing new strategies. *Question*: How can we remind businesses about license renewals?

Each metric is linked to specific data sources or operational datasets, such as "Business Licence Delay Logs" for analyzing delays.

### Step 2: Data Discovery
Data discovery involves finding, understanding, and organizing data to set the stage for deeper analysis and informed decision-making. It includes:
- **Data Collection**: Gathering data from various sources such as databases, files, or external sources.
- **Data Analysis**: Understanding the structure, quality, and content of the collected data.

### Step 3: Data Storage Design
To store operational data in an analytical environment using AWS S3, follow these steps:
- **Bucket Created**: `business-businesslicences-gurleen`
- **Organize by Year**: Created folders for each year ("2023/Landing," "2024/Landing").
- **Specific Data Folders**: Within each year folder, created additional folders for different types of data:
  - `business licences application records`
  - `business licences delay logs`
  - `business licences renewal history`
  - `business licences compliance data`
  - `business licences renewal reminder logs`
  - `process efficiency metrics`
  
  Finally, uploaded the dataset files into the relevant folders to keep data organized and easy to access.

### Step 4: Dataset Preparation
Data Preparation involves arranging and preparing data from various sources to achieve the business goal. In this case, it involves retrieving Business Licenses data from the City of Vancouver’s Open Data Portal for the years 2023 and 2024.

# Dataset 2: Business Licenses in Downtown Vancouver (By Gurleen Kaur Khosa)

## DAP Design and Implementation (Steps 1-13)
## Step 1: Data Analytical Question Formulation

Firstly, it is necessary to define the data analytical questions to be posed and addressed in the Data Analytic Platform (DAP) framework for the City of Vancouver. These questions should be specific to a particular department or office within the city and address issues within that department or areas that could be improved upon. Recycle BC is the primary office involved in this project since its primary tasks are collecting, transporting, disposing of, and recycling waste within the city (Recycle BC, 2024). The dataset pertains to the 3-1-1 service requests regarding “Abandoned Non-Recyclables—Small Case” and is within this department’s jurisdiction.

The primary procedure to be examined in this analysis is the department’s response to service requests regarding abandoned non-recyclable items. More specifically, the project will highlight how well this department manages these service requests to enhance the efficiency of the waste management system in the building. The goal will be to increase response times and decrease the rates at which items are left behind, thus enhancing the cleanliness of cities and residents' satisfaction.

Notably, the project will use descriptive analysis as its primary approach. Descriptive analysis is the most straightforward and appropriate method for this stage because it focuses on understanding what has happened within the organization (IMD, 2024). The descriptive analysis will focus on answering the question: "What happened with the abandoned non-recyclable service requests in 2022?" The metric that will be employed comprehensively in this assessment is the total number of service requests concerning abandoned non-recyclables, and the total number of service requests met throughout the year. Other measures could be the mean time to respond to such calls and the distribution of such occurrences in distinct neighborhoods in Vancouver.
## Step 2: Data Discovery

In this phase, it is crucial to define the goal of the analysis and select the dataset that will be used in the Data Analytic Platform (DAP). The target dataset for this project is the 3-1-1 service requests dataset, which contains information on the ‘Abandoned Non-Recyclables—Small Case’ service requests (3-1-1 service requests, 2024). This dataset is instrumental because it explains how the City of Vancouver addresses reports of abandoned non-recyclable items concerning the people. This dataset includes service delivery requests occasioned by residents’ calls to the 3-1-1 service, primarily to report a problem that needs recognition and remedial action from a city agency (3-1-1 service requests, 2024). The dataset is focused on small cases of abandoned non-recyclable things, which are only a tiny portion of the waste management problem the city is facing.

**Figure 1**  
The Datasets from the Open Data Portal in the City of Vancouver
![image](https://github.com/user-attachments/assets/3ed1608f-1f28-4930-bf48-101dba8098db)
![image](https://github.com/user-attachments/assets/8b644620-d8f9-4cb2-bc07-6a68137550e6)
## Step 3: Data Storage Design

While considering the storage part for the City of Vancouver's Data Analytic Platform (DAP), the storage must be secure and well-arranged so that it should not be a concern during data analysis. For this purpose, Amazon S3 (Simple Storage Service) is chosen as it offers a highly scalable and durable solution vital for managing the city’s data (Nem, 2024). Therefore, an S3 bucket will be created with respective folders. The bucket is to be named the ‘RecycleBC-AbandonedNonRecyclables.’ This name identifies the office and procedure of Recycle BC, which is the former, as it is responsible for recycling and waste management in Vancouver. Then, the procedure is included to refer to the measured metric. This organization guarantees that data is stored within recognized best practices and accessible to the actors.

**Figure 2**  
The S3 Bucket with the 2023 and 2024 Folders
![image](https://github.com/user-attachments/assets/ec821465-df9d-4a5b-b398-858a5ba8894f)
## Step 4: Dataset Preparation

Data preparation is an essential element of the data analytic process as it entails cleaning, formatting, and putting the data in the correct format for the analysis. To achieve this, data from the Open Data Portal has been obtained, emphasizing the service requests for Vancouver's "Abandoned Non-Recyclables—Small Case". The selected years for analysis are 2023 and 2024 because this data would be more recent and valuable in highlighting contemporary issues in waste management. These years are worthwhile because they shed light on how the city has continued to deal with waste-related service calls and contain the growth in those requests for actual performance and trends.

**Figure 3**  
The Downloaded Datasets in The Local Environment
![image](https://github.com/user-attachments/assets/959ebac7-ceeb-4536-bc49-89ab853bf721)
Image: Authors
## Step 5: Data Ingestion (Pull data into Operational Environment)

The data ingestion process moves the prepared datasets into the operational environment and loads them into the target location in Amazon S3 (Mucci & Stryker, 2024). This is a significant step because it involves transferring data from local or external storage into the cloud environment in which the data will be used. The data for the years 2023 and 2024 are in a format that will allow them to be uploaded to the Amazon S3 service. S3 storage has been designed to fit the data analytic needs, and the data will be positioned correctly to facilitate the subsequent steps.

**Figure 4**  
The Dataset Files Pulled into the Operational Environment
![image](https://github.com/user-attachments/assets/bd3e9fef-9768-4e84-ab56-35f8943512c9)
![image](https://github.com/user-attachments/assets/dc23bc19-8559-409a-a6bc-25c53841ee2b) Image: Authors
## Step 6: Data Storage

Data storage is another step in data management, whereby datasets are stored and arranged to facilitate retrieval and use. The data storage solution for this project is to organize the data gathered within the S3 Amazon bucket by creating folders within the bucket as specified below after the ingestion phase, where datasets are uploaded.

When organizing the S3 bucket, the folder structure is designed to move data from the raw format directly to the curated format suitable for analysis without jumping through all the intermediate processes involved. The main folders consist of **Landing**, where the data is first deposited without pre-processing. For this project, the datasets for the years 2023 and 2024 were uploaded to the Landing folder under the respective paths `RecycleBC/AbandonedNonRecyclables/2023/Landing/ServiceRequests` and `RecycleBC/AbandonedNonRecyclables/2024/Landing/ServiceRequests`. The data in this folder remains in its original format as downloaded from the Open Data Portal.

The data collected undergoes the initial processing and cleaning before being transferred to the **Raw** folder. This folder contains the raw data that has gone through the cleansing process and is thus still comparatively unformatted but is accurate and uniform. They support further data processing and are also used as a source for analyzing the obtained results. 

Finally, the **Curated** folder contains information that has been processed, shaped, or enriched to best suit analysis and subsequent reporting. The curation typically involves pre-processing data sets that are almost ready to feed into analysis tools for producing insights.

**Figure 5**  
The Landing, Raw, and Curated Folders hold the Initial, Raw, and Processed Data
![image](https://github.com/user-attachments/assets/10f1e0b7-6e18-44c9-9291-a5cae708a7c9)
![image](https://github.com/user-attachments/assets/1136f739-2b9c-4f3d-bc94-d2ace18ebb47)
Image: Authors
## Step 7: Data Pipeline Design

**Figure 6**  
The Data Pipeline
![image](https://github.com/user-attachments/assets/c995588d-210b-4500-ab58-120cc273cbb9)
![image](https://github.com/user-attachments/assets/bcdf44bb-828e-4180-9b38-60a0ce6c9697)
![image](https://github.com/user-attachments/assets/aa0f712b-1cd1-4f0b-97cb-bbdbb15d34d5)
![image](https://github.com/user-attachments/assets/bd375d67-2263-410d-9240-8331770c2b9c)
Image: Authors
## Step 8: Data Cleaning

Data cleaning is essential in pre-processing because data should be accurate and free from inconsistencies before the analysis (Akram, 2024). In this project, AWS Glue DataBrew is used to clean the data. DataBrew helps prepare data by offering a graphical user interface for data cleaning, feature engineering, and handling big data, such as the City of Vancouver’s 3-1-1 service request data (AWS, 2024).

The data cleaning process was initiated by creating a project on AWS Glue DataBrew focused on the Recycle BC initiative for managing non-recyclable wastes and the trash found on the streets. The naming convention of the project was straightforward, based on the department, procedure, and dataset year. The related dataset was then linked to the project by browsing the correct folder in the S3 bucket, the Landing folder, where raw data is first stored. Once the necessary permissions were established with the LabRole, data validation was performed to examine and clean invalid and exceptional values among the datasets. Further optional modifications to the existing schema include naming the columns for easy understanding and changing the data type for the planned analytical use. After that, the cleaning and preparation jobs were established, a name was given based on the name of the dataset, and the output data type was set to CSV. This job ensures that all the cleaning steps are stored and can be repeated automatically on subsequent data to be cleaned, as well as preserving clean data for subsequent analyses.

**Figure 7**  
The Projects Created with the Respective Jobs After Cleaning
![image](https://github.com/user-attachments/assets/dbf8e849-2ed1-4163-964e-dc10c73655f6)
![image](https://github.com/user-attachments/assets/40f7e467-8a59-43e3-b0b6-d88891e7f7e9)
![image](https://github.com/user-attachments/assets/1530be4a-2fba-4a34-b3c4-f2077d08ccde)
![image](https://github.com/user-attachments/assets/ddc9f428-eab6-45c4-8c5f-d312fdecb006)
![image](https://github.com/user-attachments/assets/bfe0e115-aaa9-4053-b21e-8f47d8177abc) Image: Authors
## Step 9: Data Structuring

Data structuring goes hand in hand with data cleaning, as described in the previous step. Once the data has been cleansed and the necessary transformations made in AWS Glue DataBrew, the next step is to transform the data to fit the necessary structure for analysis (Kiely, 2023). This mainly entails formatting the data to ensure that the columns have proper and standardized names, that required data type conversions are done and that any other manipulations are done. After structuring the data, it is moved to the Raw folder in the specified S3 bucket so that the Data Analytic Platform can retrieve it for additional processing. In addition, the structuring process makes a dataset sufficiently clean. It categorizes it in a manner that can lead to querying and accurate information delivery, hence adding to the efficiency of the organization's data analytical chain.

## Step 10: Data Pipeline Implementation (ETL)

The data pipeline is an essential component of data management architecture as it organizes the extraction, transformation, and loading process to transform data from raw form to an analysed form (Stryker, 2024). In this project, AWS Glue was used to implement the ETL and the Visual ETL tool was used to ease the process. This process helps automate data flow and transformation around the Data Analytic Platform. With the proper functioning of the ETL pipeline in AWS Glue, the project contributes to the systematic preparation of raw data for analysis. It assists Recycle BC in addressing and handling service requests on discarded non-recyclables within Vancouver. It not only leads to higher quality and more standardized data but also contributes to the efficiency of the subsequent processes, allowing to quickly and accurately analyze the data at hand.

**Figure 8**  
The Project’s Visual ETL
![image](https://github.com/user-attachments/assets/36fd07bd-0b6c-4435-8aec-c6b5a8f7efb9)
![image](https://github.com/user-attachments/assets/bc0c5236-47fb-4c01-a549-3d24a5951486) Image: Authors
## Step 11: Data Analysis

This stage involves analysis of the cleaned and structured data and identifying helpful information from the data set. In this project, Amazon Athena, a serverless query service, runs the SQL queries against the data stored in the Amazon S3. This approach is suitable for analyzing the given datasets since it is not tied to specific complex structures and can be initiated when necessary. It proposes a relatively efficient and fast solution for managing abandoned non-recyclables by Recycle BC. After the data has gone through the ETL process and is in its final structured state, the next logical step is to query it using Amazon Athena. Athena also allows for SQL queries to analyze specific data elements, like patterns in service requests, trends over time, and shining the lens on specific regions seeing a higher amount of abandoned non-recyclables.

**Figure 9**  
The Query Results
![image](https://github.com/user-attachments/assets/8ed87c07-7282-45a0-914e-dc95d045a92f)
![image](https://github.com/user-attachments/assets/5282de67-456d-4db5-82eb-de8eaed5b262) Image: Authors
## Step 12: Data Visualization

**Figure 10**  
The Graph Showing the Channels Used in Making these Reports
![image](https://github.com/user-attachments/assets/16502e30-c8c3-4a49-97e7-97e14139c3f7)
Image: Authors
## Step 13: Data Publishing

This stage aims to present the analyzed data and the results achieved in a web user interface accessible to the stakeholders. For this project, Amazon EC2 instances are used as the web servers that host Apache, which hosts the website used in publishing the results of the data analysis. The EC2 instances offer a computational platform for the Apache server, thus facilitating the availability and interaction of the data, which needs scalability and security (Amazon Web Services, 2024). Apache, an open-source web server software that fulfills most of the HTTP needs of the web, is set up to display the findings in a form that the interested parties can use to navigate the data and interact with the graphical representation of the analyses in addition to downloading reports from time to time (Hernandez, 2019). By hosting the data in EC2 instances, the solution can leverage the flexibility and elasticity of AWS to manage loads and ensure availability. This process ensures that decision-makers in Recycle BC and other relevant departments in the City of Vancouver can easily access valuable insights generated from data analysis and develop sound decisions. This way, the project meets its goal of providing fast access to data and increasing information dissemination efficiency for better waste management and service delivery across the city.

**Figure 11**  
The EC2 Instance and the Web Server Process
![image](https://github.com/user-attachments/assets/6991534c-4ce8-4749-ab47-1ea288f2cf19)
![image](https://github.com/user-attachments/assets/d46943c0-5795-48e8-8c40-d2d00782adda)
##Dataset 2: Business Licences in Downtown Vancouver
##DAP Design and Implementation (Steps 1- 13)
## Step 1: Data Analytical Question Formulation

Formulating data analytical questions involves setting clear goals and identifying the right data to answer specific business needs. This step ensures that the analysis focuses on the right areas, helping to draw useful conclusions and take informed actions based on the data.

The screenshot below shows a breakdown of the data analysis process to improve business license issuance and compliance in Downtown Vancouver. It starts with a high-level goal and breaks it down into different steps.

1. **Descriptive Metric:** The first step is to understand the current situation. This involves analyzing data on the number of business licenses issued per year. *How many business licenses are issued per year?*

2. **Diagnostic Metric:** The next step is to identify the reasons for business license delays. This can be done by analyzing data about the reasons for the delay. *Why are there delays in issuing licenses?*

3. **Predictive Metric:** The goal here is to predict the likelihood of a business license renewal. This can be done by analyzing data about past renewal patterns and other factors that might influence renewals. *How likely is a business license to be renewed?*

4. **Prescriptive Metric:** Finally, the goal is to recommend proactive actions to improve renewal reminders. This involves analyzing data about successful reminders and developing new ways to ensure businesses are reminded about their licence renewal. *How can we remind businesses about license renewals?*

Each metric is linked to a specific data source or operational dataset. For example, to analyze the reasons for delays, data from "Business Licence Delay Logs" will be used. This way, the screenshot shows how data analysis can be used to achieve a specific goal by breaking it down into smaller, more manageable steps.

**Step 1: Data Analytical Question Formulation**
![image](https://github.com/user-attachments/assets/1d849355-ff8b-45ac-bba0-c09bc889e7a9)
Step 2: Data Discovery
	Data discovery is about finding, understanding, and organizing data to set the stage for deeper analysis and informed decision-making. It involves data collection which means gathering data from various sources, such as databases, files, or external sources and then analyzing the collected data to understand its structure, quality, and content.
Step 2: Data Discovery
![image](https://github.com/user-attachments/assets/418785a7-78e8-479a-9ffa-f4b470e422ef)
Step 3: Data Storage Design
In this step, we need to store our operational data in an analytical environment using S3 service in AWS. To do this, firstly, we need to create a bucket for our data storage in S3. Bucket is a place where we store objects and object could be anything be it excel file, pdf, image, json file etc.
•	Bucket Created: business-businesslicences-gurleen
•	Organize by year: Inside the bucket, created folders for each year ("2023/Landing," "2024/Landing").
•	Created folders for specific data: Within each year folder, made more folders for different types of data, like “business licences application records”, “business licences delay logs”, “business licences renewal history”, “business licences compliance data”, “business licences renewal reminder logs”, “process efficiency metrics” inside the “landing folder”.
Finally, uploaded the dataset files into those relevant folders. This helps keep data organized and easy to find later.

Step 3: Data Storage Design
![image](https://github.com/user-attachments/assets/915d3916-5ea7-4e71-98ec-e5078d89420a)
![image](https://github.com/user-attachments/assets/f1a009e6-45c2-45e2-b9ef-0aa5fda1a825)
![image](https://github.com/user-attachments/assets/40d834ad-d238-4e4a-a772-21636a14c130)
![image](https://github.com/user-attachments/assets/9fd0e900-6bfa-4574-b85d-7fb7e2764cbf)
## Step 4: Dataset Preparation

Data Preparation is basically preparing or arranging your data from various sources to achieve your business goal, which in my case was Business licences data retrieved from the City of Vancouver (Open Data Portal) for the years 2024 and 2023.

**Step 4: Dataset Preparation**
![image](https://github.com/user-attachments/assets/8ccded4e-b657-4bcb-9035-9e732ae9d964)
![image](https://github.com/user-attachments/assets/6699d37e-ce29-4e2d-8954-35eed48d7366)
![image](https://github.com/user-attachments/assets/e6d58999-c9cf-4e68-bdee-8c327101bea8)

## Step 5: Data Ingestion

Data Ingestion involves uploading your data inside your AWS bucket in specific folders. As in my case, uploading my Excel and PDF files into their relevant folders. For instance, `business_licences_application_records.xlsx` for the Business Licences Application Records folder of my business bucket and so on.

**Step 5: Data Ingestion**
![image](https://github.com/user-attachments/assets/3724811c-cb4b-42ea-9253-030683fd8f23)
![image](https://github.com/user-attachments/assets/1e508f8f-3632-47ab-8c15-f112b9d30251)
## Step 6: Data Storage

Data storage is an essential step in data analytics platforms. It involves storing the collected data into folders of S3 buckets for efficient access and analysis. After gathering data from the open data portal, it is then stored in the landing environment of S3.

**Step 6: Data Storage**
![image](https://github.com/user-attachments/assets/941191f2-3c03-4797-9d24-fc6f69a03a55)
## Step 7: Data Pipeline Design

The Data Pipeline design step is about planning how data will travel through the system, from where it starts to where it ends up. This includes deciding how data will be collected, processed, changed, and stored. The aim is to make sure data moves smoothly and is ready for analysis.

I created a visual representation of my ETL pipeline in draw.io using tables showing various stages of my design, such as removing, filtering, extracting, and grouping stages, and then finally reaching my outcome table showing “Licence Issuance Rate” calculations for the years 2024 and 2023.

**Step 7: Data Pipeline Design**
![image](https://github.com/user-attachments/assets/b754cd3e-25cc-4d2a-9524-a4b353de74cd)
![image](https://github.com/user-attachments/assets/1a1a1f0d-de90-46a5-a1f1-de189ad7e338)
![image](https://github.com/user-attachments/assets/c6775028-3ae8-4895-8ec5-9202c554b4bd)
![image](https://github.com/user-attachments/assets/2008d922-50e6-4398-9d50-a3b6b07775b6)
![image](https://github.com/user-attachments/assets/3aac0f2c-5739-4176-ba67-11a46512180a)
## Step 8: Data Cleaning

In this step, I cleaned up the dataset of business licenses application records in an AWS S3 bucket. The process involved creating a raw folder inside the landing zone and then using a data cleaning tool called AWS Glue DataBrew.

1. I created a project in AWS Glue DataBrew.
2. The project cleaned the data by removing invalid, null, or missing values using the function feature. Columns with more than 80% missing values were dropped because they were deemed unuseful for analysis.

This cleaning process ensures the accuracy of any future analysis performed on the data.

**Step 8: Data Cleaning**
![image](https://github.com/user-attachments/assets/55375c6d-2bc5-4f41-89cc-4312b8a2976b)
![image](https://github.com/user-attachments/assets/a4a7de09-8ada-47db-b0d7-ba6ea22c69eb)
## Step 9: Data Structuring

In this step, I arranged my data in a structured manner, meaning I renamed column names with relevant names with respect to the information they hold. Furthermore, I configured the “Schema” in AWS Glue DataBrew to ensure whether my dataset had relevant datatypes for specific columns and, if not, changed them accordingly. I then created and ran my job and stored the result of my cleaning and structuring inside the raw folder of my S3 bucket.

**Step 9: Data Structuring**
![image](https://github.com/user-attachments/assets/ef4f8842-7390-49c0-b100-6d0142e23086)
![image](https://github.com/user-attachments/assets/dc4bebce-1890-4ef9-a08c-1cb312140abf)
![image](https://github.com/user-attachments/assets/94709b2e-a851-4b00-8d4a-5ef114b7b1ae)
![image](https://github.com/user-attachments/assets/fd398b95-fde3-4e11-af2e-1a1a1f93cb12)
![image](https://github.com/user-attachments/assets/dc3b08a4-6533-4cc5-8c13-7f6e4e7b266f)
## Step 10: Data Pipeline Implementation

This step involves the creation of a visual ETL using AWS Glue service. This step provides us with the summarized information for our analysis. In this step, I fetched data from my raw folder (cleaned and structured data) and then performed certain operations on that dataset to extract specific information. I used aggregation, filter, and change schema functions to retrieve specific information from my dataset. I then used the join function to group my dataset and performed an average calculation to determine the “Licence Issuance Rate” for the years 2024 and 2023 using the columns “Number of business licenses issued per year” and “Total number of business license applications initiated.”

Licence Issuance Rate = (Number of business licenses issued per year / Total number of business license applications initiated) * 100

Finally, I ran my job, and my results were stored in the curated folder of my S3 bucket.

**Step 10: Data Pipeline Implementation**
![image](https://github.com/user-attachments/assets/b72acc6f-3332-4568-9e2e-56d35e442694)
![image](https://github.com/user-attachments/assets/25a876c6-bbd9-4a0a-8080-d7c3f702380e)
![image](https://github.com/user-attachments/assets/8394d8eb-8463-4b09-92cb-2c4a59f8070a)
![image](https://github.com/user-attachments/assets/cabc0056-8376-4983-9423-d30c014a613b)
![image](https://github.com/user-attachments/assets/f9aba81d-39ce-4464-bc0f-7e0770bdf7dd)
![image](https://github.com/user-attachments/assets/0e226e6a-a5f8-4009-ac21-bbffbaa8e65a)
![image](https://github.com/user-attachments/assets/1d079655-eba5-4383-839b-d73ba8910850)
## Step 11: Data Analysis

The AWS service used for executing this step is Amazon Athena. This step involved analyzing the summarized curated folder data from the S3 bucket by creating tables for specific CSV files. The table contained columns such as Year and LIR (Licence Issuance Rate) for the years 2023 and 2024. After table creation, I ran SQL queries to retrieve specific information from the table using SQL “ORDER BY”, “SELECT” and various other queries.

**Step 11: Data Analysis**
![image](https://github.com/user-attachments/assets/9d4193c6-57c4-4613-aec6-8be7c3be5b20)
![image](https://github.com/user-attachments/assets/f85b48f1-f0be-4880-8d02-e1c58d7f3d8c)
![image](https://github.com/user-attachments/assets/f4f08c0d-664d-47b0-b0a4-f455798bc677)
![image](https://github.com/user-attachments/assets/353d2aa3-2115-49b8-a2b9-9789b04277e0)
## Step 12: Data Visualization

In this step, I created visualizations
![image](https://github.com/user-attachments/assets/3f1a1bde-57d3-4b09-aae8-c75fe7ed4a71)
![image](https://github.com/user-attachments/assets/22ea1f9d-2dfe-4714-963a-efae84ec1e77)
## Step 13: Data Publishing

AWS EC2 service was used to execute this step. This step involved publishing your data files to general and web servers to be accessible by the public. To do this step, I created two EC2 instances, one for the general server and another one for the web server. For connecting my instances, I used “Remote Desktop Connection” inbuilt software in Windows and uploaded my files to the remote computer in the analysis folder in C-Drive for the general server and in the wwwroot folder for the web server. I then used the public IP address to access my uploaded files on the web browser.

Step 13: Data Publishing
![image](https://github.com/user-attachments/assets/f2f2ba7e-8494-4af9-9feb-7a3ffc9b8afa)
![image](https://github.com/user-attachments/assets/ee76fe23-533c-4657-9f82-c970c8e910f1)
![image](https://github.com/user-attachments/assets/00eec6fd-a448-4d8a-bbbe-bae5d2755ec8)
![image](https://github.com/user-attachments/assets/d6942da3-7597-4ecc-b7af-7f3d78352793)
![image](https://github.com/user-attachments/assets/0a739dc9-09b8-451c-af12-64dc267e2dc2)
## Step 1: Data Analytical Question Formulation

In the Animal Control department, identifying the Data Analysis Question Formulation needs a data analytics platform to find its goal and answer 4 types of data analysis questions regarding lost and found animals. These questions will guide how/what data we collect/process, as well as who or which department analyzes the data. Also, what decisions or actions the City of Vancouver might take based on this analysis?
![image](https://github.com/user-attachments/assets/0ae07cfd-440f-4215-95d7-0a054e9e34d1)
Picture 1: Data Analytical Question Formulation

## Step 2: Data Discovery

This includes an in-depth exploration of all operational environments to identify and locate all datasets relevant to answering the questions that will have been formulated in Step 1.

This includes the identification, assessment, and preparation of datasets for migration to AWS. Specifically:
- **Lost Animal Information 2023-2024**: Information about the animals reported to be lost, together with their descriptions, dates, IDs, names, and statuses.
- **Vancouver Animal Control Office Analysis**: Reports and metrics for internal use on handling lost animal cases.
- **Register Reports**: Time sheets of historical records of cases related to lost animals.
- **Animal Services Staff Data**: Information on the activities of staff, their performance, and preventive measures.
![image](https://github.com/user-attachments/assets/526677fe-377f-4a88-8db0-5e63c26e96b0)
Picture 2: Data Discovery
## Step 3: Data Storage Design

In Step 3, Data Storage Design focuses on organizing and securely storing datasets in AWS S3. In this step, I set up dedicated AWS S3 buckets to store different types of data related to the Lost and Found Animals domain.

- **Bucket Name**: animalcontrol-lostandfound-lamthithuthao
- **Folder: Landing/2023** – This could contain subfolders like "Lost Animal Information 2023," "Register Reports," and "Vancouver Animal Control Office Analysis."
- **Folder: Landing/2024** – Similarly, this would store data for the year 2024, such as "Lost Animal Information 2024" and other relevant datasets.
![image](https://github.com/user-attachments/assets/a520622c-2027-4953-9cda-7dad95045f03)
Picture 3: Data Storage Design - Landing/2023
![image](https://github.com/user-attachments/assets/8d16e8bf-e83d-4f85-afcf-7675c2d2fffb)
Picture 4: Data Storage Design - Landing/2024
## Step 4: Dataset Preparation

Basically, Data Preparation is the process of organizing and converting raw data into a structured format, making it ready for uploading and analysis on AWS.

For this, I downloaded the following two Lost and Found Animal data Excel files for the years 2023 and 2024 from the City of Vancouver data website. Due to the rest of the data being unavailable for this assignment, I used ChatGPT to obtain the sample data in CSV format, which is created with 10 columns and 5 rows. The sample dataset contains very relevant fields to the needed attributes in analysis, such as animal IDs, report dates, and statuses, among other key fields. Below are the areas these datasets covered:
- Animal Services Staff
- Analyzing the Vancouver Animal Control Office
- Members of Staff in the Vancouver Animal Control Office
- Register Reports.

After generating the sample datasets, I saved all the CSV files in Excel format. This facilitates more convenient manipulation, review, or sharing with team members or stakeholders.
![image](https://github.com/user-attachments/assets/cb8337f8-ffe2-4aab-94ea-f68c76885da4)
Picture 5: Dataset Preparation - 2023
![image](https://github.com/user-attachments/assets/147ea141-0733-4131-bb73-c81594fd277d)
Picture 6: Dataset Preparation - 2024
## Step 5: Data Ingestion

The main objective of Data Ingestion is to successfully and accurately migrate the prepared datasets from Step 4 into their corresponding homes within the AWS S3 bucket. To ingest data, I followed a technique of uploading the datasets by adding files to the previously created folders for each year in the Landing zone: 2023 and 2024. After uploading each dataset, I verified the upload status to ensure that each dataset was uploaded to the correct folder and transferred with no errors.
![image](https://github.com/user-attachments/assets/46c99b89-94d5-4098-bb64-12e2d03ba1e9)
![image](https://github.com/user-attachments/assets/32bb71f2-08ac-4051-8e17-d9f1a462f110)
Picture 8: Data Ingestion
![image](https://github.com/user-attachments/assets/2239bfeb-d92a-4c90-93f7-a3b938e39b34)
Picture 9: Data Ingestion
![image](https://github.com/user-attachments/assets/44171d8d-4daa-4da9-803e-9a7ac14094d9)
Picture 10: Data Ingestion
## Step 6: Data Storage

After successfully completing the upload of the datasets in Step 5, a logical follow-through would be to identify appropriate storage classes in the Properties section depending on usage patterns, helping in finding a balance between cost efficiency and performance regarding data readiness in read and write mode, as may comparatively be required for processing by the City of Vancouver's Animal Control.

The datasets were organized into specific folders within the S3 bucket structure:
•	Vancouver Animal Control Office Staff 2024 in Standard class
•	Vancouver Animal Control Office Analysis 2024 in Standard class
•	Register Reports 2024 in Standard class
•	Lost and Found Animal Information 2024 in Standard class
•	Animal Services Staff 2024 in Standard class
![image](https://github.com/user-attachments/assets/d5b30317-b57e-43eb-920d-f4b1154cfee3)
Picture 11: Data Storage
![image](https://github.com/user-attachments/assets/f72c7405-afdb-4967-88ab-537ae4ccd5ea)
Picture 12: Data Storage
![image](https://github.com/user-attachments/assets/1ed7f5e8-09cb-41ba-8869-68707244be19)
Picture 13: Data Storage
![image](https://github.com/user-attachments/assets/6fb63d17-4019-4e1d-8576-3b52323fa92b)
Picture 14: Data Storage
![image](https://github.com/user-attachments/assets/d4c9ee69-0ce2-4a78-82b4-7f8bcd70a9ec)
Picture 15: Data Storage
## Step 7: Data Pipeline Design

In Step 7, Data Pipeline Design, I created a graphical representation of the ETL process with a Data Lineage Diagram. The diagram illustrates the flow of the data from its extraction stage to the final calculation of the Lost Animal Reporting Rate. I used ChatGPT to create in writing the formula that calculates the metric from the transformed data: Lost Animal Reporting Rate. The final rate output has the benefit of enabling the City of Vancouver to understand how ground-level lost and found animal management processes are effective.
![image](https://github.com/user-attachments/assets/b59cb2e3-7a24-4cc5-857f-7a40e16e7b9b)
Picture 16: Lost Animal Reporting Rate Formula
![image](https://github.com/user-attachments/assets/dc9d5192-d357-4e67-86d4-2d7ed2e67ae3)
Picture 17: Data Design Pipeline
## Step 8: Data Cleaning

In this step, I cleaned the Lost Animal Information dataset within the 2024 folder, ensuring that there are no invalid or missing values in the data, which could affect the accuracy of any analysis performed later.

- In the 2024 folder in the S3 bucket, I created a new folder named Raw.
- Inside the Raw folder, I created another folder named Lost_Animal_Information to store the unprocessed data.
- Then, I used AWS Glue DataBrew to create a project and set the project name to `animalcontrol-lostandfound-cleaning-lamthithuthao`.
- New dataset details: `animalcontrol-lostandfound-information-lamthithuthao`.
- Selected the path for the new dataset: `AnimalControl > LostAndFound > 2024 > Landing > Lost Animal Information` folder.

After setting up the project, I received the project details for 6 columns in the dataset.
![image](https://github.com/user-attachments/assets/cc3fae28-309c-4fb0-b28e-a84560b35aa5)
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
![image](https://github.com/user-attachments/assets/a8c673b4-e0e7-42ee-8f87-c1655f55880b)
Picture 19: Data Structuring
## Step 10: Data Pipeline Implementation

In this step, I began by creating a new AWS Glue job, naming it `AniContrl-LostInfor-ETL-ThiThuThao`. 

I added several features to the ETL process:
- **Aggregate and filter function:** to focus on relevant information.
- **Rename columns and standardize formats:** to ensure consistency.
- **Join function:** to merge datasets where necessary to enrich the data.

After completing the ETL process, the final, cleaned, and transformed data was saved back into a new S3 bucket under the Curated folder. Additionally, the transformed data was stored in the `Lost-Animal-Information-Reports` folder.
![image](https://github.com/user-attachments/assets/7ca6962b-d80a-4351-8e6b-a08c74612415)
Picture 20: Data Pipeline Implementation
![image](https://github.com/user-attachments/assets/9651f387-a438-4d1a-804e-ced3beb683ba)
Picture 21: Data Pipeline Implementation - Curated folder
Step 11: Data Analysis
In this step, I used Amazon Athena to analyze the curated data from the Lost and Found Animal project.
•	Firstly, I created a new table named animalcontrol_lostandfound_table19_lamthithuthao 
•	Then, I created a new database named: animalcontrol_lostandfound_database19_lamthithuthao
•	The dataset used was from the Lost-Animal-Information-Reports folder within the Curated directory.
•	The table included key columns such as Year and APR (Annual Percentage Rate)
After setting up the table, I ran several queries to extract insights. For instance, I queried the database to list all lost animal records, sorted by their unique ID
![image](https://github.com/user-attachments/assets/dfc801be-0dfa-4667-badf-d9740dc82ed9)
Picture 22: Data Analysis – Amazon Athena
Step 12: Data Visualization
In this final step, I focused on visualizing the results of the Lost Animal Reporting Rate analysis. The process was as follows:
•	I downloaded the APR_Per_Year.csv file (in step 11), which contains the Animal Reporting Rate (APR) for the year 2024, and uploaded it to a Google Excel
•	Using Google Sheets, I created a simple bar chart to represent the APR value visually. The bar chart displayed the APR on the X-axis and the year 2024 on the Y-axis.
•	After finalizing the visualization, I exported the Google Excel document as a PDF file, ensuring that the report was easy to share and present.
•	The file was named Graph Report_LamThiThuThao.pdf to reflect its content and origin
![image](https://github.com/user-attachments/assets/587456dc-d6f3-40af-be77-5a6f4e3e2cbe)
Picture 23: Data Visualization
## Step 13: Data Publishing

This step ensures that the analytical results are accessible to team members or stakeholders who need to view or use the data for decision-making or further analysis. For this, I utilized AWS EC2.

First, I created two EC2 instances, both running the Windows operating system:
- **The first instance** is named: `animalcontrol-lost&found-GeneralServer-lamthithuthao`
- **The second instance** is named: `animalcontrol-lost&found-WebServer-lamthithuthao`

Since I am using a MacBook laptop, I connected to these instances using the Microsoft Remote Desktop protocol service. This enabled me to remotely configure and operate the servers, as well as access the necessary files.

The reports, including Graph Reports and CSV files, are hosted on these EC2 instances. By sharing the public IP address, these reports can be accessed and used by individuals with the appropriate credentials.
![image](https://github.com/user-attachments/assets/514d8498-1163-486d-b85a-f3ff0b3484e3) Picture 24: Data Publishing - EC2
![image](https://github.com/user-attachments/assets/005cb6cb-19d5-42b9-bd78-713524fbf12d) Picture 25: Data Pushlishing - General Server
## Step 13: Data Publishing

This step ensures that the analytical results are accessible to team members or stakeholders who need to view or use the data for decision-making or further analysis. For this, I utilized AWS EC2.

First, I created two EC2 instances, both running the Windows operating system:
- **The first instance** is named: `animalcontrol-lost&found-GeneralServer-lamthithuthao`
- **The second instance** is named: `animalcontrol-lost&found-WebServer-lamthithuthao`

Since I am using a MacBook laptop, I connected to these instances using the Microsoft Remote Desktop protocol service. This enabled me to remotely configure and operate the servers, as well as access the necessary files.

The reports, including Graph Reports and CSV files, are hosted on these EC2 instances. By sharing the public IP address, these reports can be accessed and used by individuals with the appropriate credentials.
![image](https://github.com/user-attachments/assets/a1d023b6-4aab-4268-adcf-5b34e0e17516)
## Step 2: Data Discovery

Data discovery in AWS involves identifying, classifying, and analyzing data resources within your AWS environment. For this project, AWS Glue Data Catalog is utilized as a serverless metadata management service. It helps in storing metadata for your data assets and has the capability to identify and index data from various sources. This ensures that all relevant datasets are properly cataloged and can be easily accessed for further analysis.
![image](https://github.com/user-attachments/assets/4127e33d-01e6-4f2a-9915-66680428e5ee)
## Step 3: Data Storage Design

Amazon S3 (Simple Storage Service) is ideal for storing large volumes of unstructured data, such as logs, backups, and media files. The focus in this step is on choosing the appropriate storage services and structuring the data in a way that ensures scalability, security, and cost-effectiveness. By using Amazon S3, you can effectively manage data growth and maintain security while optimizing for costs.
![image](https://github.com/user-attachments/assets/c7cf2d2d-0f02-48c7-b533-427cbc9c03f5)
## Step 4: Dataset Preparation

AWS Glue DataBrew is a visual data preparation tool that allows users to clean, transform, and prepare data for analytics without needing to write code. It provides a user-friendly environment to interact with the data, perform necessary transformations, and evaluate the quality of datasets, making it easier to get data ready for analysis.
![image](https://github.com/user-attachments/assets/062aab2d-2449-4355-82ae-ca8806470b9a)
## Step 5: Data Ingestion

AWS Glue is a serverless ETL tool that facilitates data extraction, transformation, and loading for data analysis. It pulls data from various sources, ingests and transforms it as required, and then loads it into a data sink such as Amazon S3, Amazon Redshift, or a relational database.
![image](https://github.com/user-attachments/assets/7f19b239-60b6-4d07-9549-bc1c85b74ad6)
## Step 6: Data Storage

Amazon S3 allows the creation of buckets for storing data files, including databases and CSV files used in analysis. These buckets provide scalable and secure storage solutions to manage large volumes of data efficiently.
![image](https://github.com/user-attachments/assets/0f89d0c0-4cf4-41b2-9afd-7b405e3000b7)
## Step 7: Data Pipeline Design

To design a data pipeline in AWS using Amazon S3, several steps are involved, and various AWS services are utilized to transfer, process, and analyze data.
![image](https://github.com/user-attachments/assets/649e1b89-b7b2-482b-8eb6-8da86d26ebee)
## Step 8: Data Cleaning

AWS Glue DataBrew is an interactive data preparation tool that helps in cleaning and transforming data without the use of code. DataBrew also performs an analysis of the data set to give information on the quality of the data. It helps to detect problems like missing values, outliers, duplicate values, and distribution of data.
![image](https://github.com/user-attachments/assets/6322d451-9b17-40fb-80bd-cb4d24038a5f)
## Step 9: Data Structuring

Organizing data in Amazon S3 is very important for storage, retrieval and analysis of data especially when dealing with big data. First, it is recommended to use the meaningful and unique names for your S3 buckets. Bucket names are unique across all AWS users, so it is advisable to incorporate your organization name, project, or environment into the bucket name.
![image](https://github.com/user-attachments/assets/b34a2ea2-181b-44e8-8e36-54acc46d7a0c)
## Step 10: Data Pipeline Implementation

The data pipeline using Amazon S3 in AWS entails several services to transfer, process, and analyze data. S3 is the storage foundation of the data pipeline. It can store original data, data that has been analyzed, and data that has been selected for specific use.
![image](https://github.com/user-attachments/assets/b6d42406-0b6e-4d1b-bbe7-7e86f5ae8155)
## Step 11: Data Analysis

Amazon Athena is an AWS service that provides the ability to query data in Amazon S3 using standard SQL. It is serverless, and you do not have to worry about any infrastructure or hardware, and you only pay for the queries that you perform.
![image](https://github.com/user-attachments/assets/03eb2c41-3747-44a8-a558-9f3444aa8627)
## Step 12: Data Visualization

Amazon QuickSight is a BI tool that allows users to create and share ad-hoc reports and dashboards without any need for IT intervention. It works well with other AWS services and supports several data types.
![image](https://github.com/user-attachments/assets/e94475c3-3235-45e6-9f18-ddeddc8e274f)
## Step 13: Data Publishing

Amazon EC2 is one of the basic services offered by AWS which provides resizable computing capacity in the cloud. It is widely used in many situations such as in publishing and delivery of content. EC2 provides flexibility to the publishers to select the operating system, storage, and instance type of their choice. This flexibility is crucial in order to achieve the best results and at the same time, minimize the expenses.
![image](https://github.com/user-attachments/assets/f57992c9-163a-4aa2-bed3-f8e60a025667)
## DAP Estimated Cost (Teamwork)

To estimate the cost of the dataset preparation phase for the above-listed projects using the AWS pricing calculator, we broke down the services used and their respective costs. The services in use include Amazon S3, AWS Glue, Amazon Athena, and Amazon EC2.

- **Amazon Simple Storage Service (S3)**
  - **Storage Used**: 527.9 GB per month
  - **Cost Estimate**: 12.14 USD per month

- **AWS Glue**
  - **DPUs Used**: Number of DPUs for Apache Spark job (10) and Number of DPUs for Python Shell job (5)
  - **Cost Estimate**: 0.14 USD per month

- **Amazon Athena**
  - **Queries and Data Scanned**: Total number of queries (7 per month), Amount of data scanned per query (varies)
  - **Cost Estimate**: 9.99 USD per month

- **Amazon EC2**
  - **Instance Types**: t2.micro
  - **Cost Estimate**: 12.21 USD per month

**Total Estimated Cost for Dataset Preparation Phase:**
- **Monthly Cost**: 34.48 USD
- **Total 12 Months Cost**: 413.76 USD
![image](https://github.com/user-attachments/assets/74765a38-d045-4d4a-8f9f-22cb34b22efa)
Picture 26: DAP Estimated Cost
## Conclusion

In conclusion, the approach for designing and implementing the Data Analytic Platform for different datasets from the City of Vancouver has been provided, including data ingestion, data cleaning, data structuring, and data analysis with AWS services. The platform supports the reception, storage, and analysis of service requests to help improve decision-making and, consequently, waste management in Vancouver. The implementation also used AWS Glue for ETL activities, S3 for scalable data storage, Amazon Athena for abstract and robust data analysis, and Elastic Compute Cloud (EC2) instances with Apache for data dissemination. It is convenient to state that the project is relatively affordable, with a total estimated annual cost of 413.76 USD, thus making the platform affordable and scalable for the clients. This procedural platform puts City of Vancouver at a more strategic vantage point to address the community's needs, thereby escalating efficiency in service provision and environmental conservation.
## References

3-1-1 service requests. (2024). Home — City of Vancouver Open Data Portal. [https://opendata.vancouver.ca/explore/dataset/3-1-1-service-requests/information/?disjunctive.department&disjunctive.service_request_type&disjunctive.status&disjunctive.closure_reason&disjunctive.local_area&disjunctive.channel&refine.service_request_type=Abandoned+Non-Recyclables-Small+Case](https://opendata.vancouver.ca/explore/dataset/3-1-1-service-requests/information/?disjunctive.department&disjunctive.service_request_type&disjunctive.status&disjunctive.closure_reason&disjunctive.local_area&disjunctive.channel&refine.service_request_type=Abandoned+Non-Recyclables-Small+Case)

Akram, B. (2024, February 20). What is data cleaning? LinkedIn. [https://www.linkedin.com/pulse/what-data-cleaning-bushra-akram-cegxf#](https://www.linkedin.com/pulse/what-data-cleaning-bushra-akram-cegxf#)

Amazon Web Services. (2024). What is Amazon EC2? [https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html)

AWS. (2024). What is AWS glue DataBrew? [https://docs.aws.amazon.com/databrew/latest/dg/what-is.html#](https://docs.aws.amazon.com/databrew/latest/dg/what-is.html#)

Hernandez, J. (2019, May 8). What is Apache? In-depth overview of Apache web server. Sumo Logic. [https://www.sumologic.com/blog/apache-web-server-introduction/](https://www.sumologic.com/blog/apache-web-server-introduction/)

IMD - International Institute for Management Development. (2024, June 5). Descriptive analytics: Importance, benefits, & examples. IMD Business School for Management and Leadership Courses. [https://www.imd.org/blog/digital-transformation/descriptive-analysis/#](https://www.imd.org/blog/digital-transformation/descriptive-analysis/#)

Kiely, T. J. (2023, March 27). The fundamentals of data structuring. Meltwater. [https://www.meltwater.com/en/blog/data-structuring](https://www.meltwater.com/en/blog/data-structuring)

Mucci, T., & Stryker, C. (2024). What is data ingestion? IBM - United States. [https://www.ibm.com/think/topics/data-ingestion#:~](https://www.ibm.com/think/topics/data-ingestion#:~)

Nem, R. (2024). Amazon Simple Storage Service (Amazon S3). Community.aws. [https://community.aws/content/2c6dBEmQPpXeGxBxdu0EHkXPXpC/amazon-simple-storage-service-amazon-s3?lang=en#](https://community.aws/content/2c6dBEmQPpXeGxBxdu0EHkXPXpC/amazon-simple-storage-service-amazon-s3?lang=en#)

Recycle BC. (2024, May 5). About Recycle BC. [https://recyclebc.ca/about/](https://recyclebc.ca/about/)

Stryker, C. (2024). What is a data pipeline? IBM - United States. [https://www.ibm.com/topics/data-pipeline#:~](https://www.ibm.com/topics/data-pipeline#:~)

Tillu, J. (2024, May 12). Understanding Amazon S3 storage classes. Medium. [https://jaytillu.medium.com/understanding-amazon-s3-storage-classes-15b7065cd080](https://jaytillu.medium.com/understanding-amazon-s3-storage-classes-15b7065cd080)














