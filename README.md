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

# Introduction
The City of Vancouver stands in a position where data-driven insights can significantly enhance decision-making, public service delivery, and resource utilization. The Data Analytic Platform (DAP) provides a foundation for integrating, processing, and visualizing vast datasets collected from different sources. Through this platform, city officials can make informed decisions that will improve the lives of residents, enhance city planning, and improve public services.

The DAP enables the transformation of large datasets into actionable insights. By aggregating data from various departments, the city can gain a comprehensive view of operations, identify trends, and anticipate challenges. The platform also promotes transparency and accountability by offering easy access to city achievements and programs.

The following steps detail the implementation and migration of the Data Analytic Platform to AWS:

### Table 1: Steps for Designing and Implementing the Platform

| Steps                                    | Description |
|------------------------------------------|-------------|
| **Data Analytical Question Formulation** | Identifying critical questions the platform needs to answer, aligning with the city's strategic goals. |
| **Data Discovery**                       | Identifying and gathering relevant datasets from various sources within the city's departments. |
| **Data Storage Design**                  | Designing a robust storage solution, including data lakes, databases, and warehouses. |
| **Dataset Preparation**                  | Cleaning and formatting data to ensure consistency and accuracy before ingestion. |
| **Data Ingestion**                       | Ingesting prepared data into the platform using batch processing or real-time streaming. |
| **Data Storage**                         | Storing ingested data in designed storage solutions for easy access and analysis. |
| **Data Pipeline Design**                 | Designing pipelines to automate data extraction, transformation, and loading (ETL). |
| **Data Cleaning**                        | Further cleaning data within the platform to maintain quality and remove inconsistencies. |
| **Data Structuring**                     | Structuring data into optimal formats and creating data models for analysis. |
| **Data Pipeline Implementation**         | Implementing designed pipelines to ensure continuous and efficient data processing. |
| **Data Analysis**                        | Extracting insights from structured data using analytical tools and methods. |
| **Data Visualization**                   | Visualizing analysis results through dashboards and reports for easy understanding and action. |
| **Data Publishing**                      | Publishing insights and visualizations, making them accessible to stakeholders for decision-making. |

---

# Example Data Analysis Process - Dataset 1: 3-1-1 Service Requests (By Ugochukwu Nwosu)

## Step 1: Data Analytical Question Formulation
The main analytical question for this dataset is how well the City of Vancouver handles abandoned non-recyclable service requests. This dataset is relevant to the city's waste management program, particularly for non-recyclable items.

<!-- Include images here as needed, for example: -->
![S3 Bucket Example](https://github.com/yourusername/yourrepository/blob/main/images/s3-bucket.png)

---

# Conclusion
The AWS-based Data Analytic Platform for the City of Vancouver is designed to enhance efficiency, reduce costs, and offer valuable insights into the city's operations. This project lays a scalable and flexible foundation for future data-driven decisions.

# References
- Recycle BC. (2024). "Annual Waste Management Report."
- IMD. (2024). "Descriptive Data Analysis: A Guide."

---

