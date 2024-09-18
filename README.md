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

<h2 align="center">Dataset 1: 3-1-1 Service Requests Regarding "Abandoned Non-Recyclables—Small Case"</h2>

### By Ugochukwu Nwosu

<h3 align="center">DAP Design and Implementation (Steps 1-13)</h3>

**Step 1: Data Analytical Question Formulation**  
Define the data analytical questions specific to a department. Recycle BC will analyze service requests for abandoned non-recyclables, focusing on improving waste management efficiency by examining how service requests were handled in 2022.

**Step 2: Data Discovery**  
Select and gather relevant datasets, specifically the 3-1-1 service requests regarding abandoned non-recyclables from the Open Data Portal in Vancouver.

![Figure 1](URL)  
*Image: Authors*

**Step 3: Data Storage Design**  
Use Amazon S3 to design the storage solution, creating a bucket named `RecycleBC-AbandonedNonRecyclables` to store data securely.

![Figure 2](URL)  
*The S3 Bucket with the 2023 and 2024 Folders*

**Step 4: Dataset Preparation**  
Clean and format datasets for 2023 and 2024 for analysis, focusing on abandoned non-recyclables.

![Figure 3](URL)  
*The Downloaded Datasets in The Local Environment*

**Step 5: Data Ingestion (Pull data into Operational Environment)**  
Move the prepared data into S3 storage, ensuring it is accessible for further processing.

![Figure 4](URL)  
*The Dataset Files Pulled into the Operational Environment*

**Step 6: Data Storage**  
Organize the S3 bucket with `Landing`, `Raw`, and `Curated` folders to manage the data workflow.

![Figure 5](URL)  
*The Landing, Raw, and Curated Folders*

**Step 7: Data Pipeline Design**  
Design the data pipeline to automate data movement and transformation.

![Figure 6](URL)  
*The Data Pipeline*

**Step 8: Data Cleaning**  
Use AWS Glue DataBrew for cleaning the dataset, handling invalid values, and ensuring data quality.

![Figure 7](URL)  
*The Projects Created with the Respective Jobs After Cleaning*

**Step 9: Data Structuring**  
Structure the cleaned data to fit analytical needs and move it to the `Raw` folder in S3.

**Step 10: Data Pipeline Implementation (ETL)**  
Implement the ETL pipeline in AWS Glue, automating data processing for Recycle BC’s non-recyclable waste service requests.

---

Repeat this format for all remaining steps and datasets. The images should be uploaded and the correct links added where the URLs are mentioned.
