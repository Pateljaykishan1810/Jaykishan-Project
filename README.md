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

# Dataset 2: Business Licenses in Downtown Vancouver (By Gurleen Kaur Khosa)

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

