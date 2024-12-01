# Tokyo 2021 Olympics Dataset ETL Pipeline with Azure Services

## 📖 Project Overview
This project demonstrates an end-to-end ETL (Extract, Transform, Load) pipeline leveraging Microsoft Azure services to process and analyze the Tokyo 2021 Olympics dataset. The primary objective is to gain hands-on experience with Azure tools while integrating various services for data ingestion, storage, transformation, and visualization. Although this is primarily a learning-focused project, it establishes a solid framework for scalable and efficient data workflows.

---

## 📊 Dataset
The dataset includes five CSV files related to the Tokyo 2021 Olympics:

- **Athletes**: Information about athletes who participated in the Olympics.
- **Coaches**: Data about the coaches associated with various teams and events.
- **EntriesGender**: Breakdown of participants by gender.
- **Medals**: Records of medal winners categorized by event and country.
- **Teams**: Information about participating teams.

---

## 🔧 Azure Services Used

### 1. Azure Data Factory (ADF)
- A cloud-based ETL service for data ingestion.
- Pipelines were created to copy raw data from a GitHub repository into Azure Data Lake Storage Gen2 (ADLS Gen2).

### 2. Azure Data Lake Storage Gen2 (ADLS Gen2)
- Used as the central storage for both raw and transformed data.
- Data was organized into the following folders:
  - **RawData**: Contains unprocessed data directly imported from the source.
  - **TransformedData**: Stores cleaned and processed data.

### 3. Azure Databricks
- An analytics platform built on Apache Spark, used for data transformation.
- Key operations performed:
  - Schema validation.
  - Handling missing values and cleaning the dataset.
  - Writing transformed data back into ADLS Gen2.

### 4. Azure Synapse Analytics
- A data warehousing service for querying transformed data.
- Transformed data was imported into a SQL pool for structured storage and analysis.

### 5. Power BI (Visualization in Progress)
- A business intelligence tool intended for data visualization.
- Integrated with Synapse Analytics for dashboard creation (currently out of the project's scope).

---

## 🛠️ ETL Process

### 1. Data Ingestion
- Raw data was ingested from a GitHub repository via ADF pipelines.
- The data was stored in the `raw-data` folder in ADLS Gen2.

  ![Data Pipe Line ](images/Azure_Data_Factory_Data_Ingestion.jpg)

  ![Storing Raw Data](images/ADLS_RawData.png)

### 2. Data Transformation
- Performed using PySpark in Azure Databricks:
  - Loaded CSV files into PySpark DataFrames.
  - Validated schemas and cleaned missing values.
  - Transformed data was written to the `transformed-data` folder in ADLS Gen2.

### 3. Data Warehousing
- Transformed data was connected to Azure Synapse Analytics.
- Tables were created in a SQL pool to enable querying and analysis.

![ Azure Synapse Analytics.](images/ Azure Synapse Analytics.png)

## 4. Visualization

Power BI integration was initiated to create interactive dashboards. Planned reports will include:

- Medal distribution analysis.
- Gender-based participation trends.
- Team performance insights.

To load data into Power BI, we need to establish a connection between Azure Synapse Analytics and Power BI:

### Steps to Connect:
1. **Open Power BI**: Launch the Power BI application and select the option to **Import Data from SQL Server**.

![PowerBI ](images/PowerBI_Azure_Synapse_Connection_Step1.JPG)

2. **Enter Serverless SQL Endpoint**: In the popup, enter the **Serverless SQL endpoint** of the Synapse Workspace created. This will establish the connection and load data into Power BI for visualization.
 
![Import Data from SQL Server Pop Up](images/PowerBI_Azure_Synapse_Connection_Step2.JPG)

### Power BI Dashboard Example:

![PowerBI DashBoard](images/PowerBI_Dashboard.JPG)

---

## ✨ Key Features
- **Seamless Integration**: Combines Azure services for an efficient data pipeline.
- **Scalability**: Uses ADLS Gen2 and Synapse Analytics to handle large datasets.
- **Advanced Data Processing**: Utilizes PySpark for efficient transformations.
- **Analytics-Ready Data**: Prepares structured data suitable for querying and visualization.

---

## 🚀 How to Use This Repository

### Prerequisites
- An active Microsoft Azure account.
- Familiarity with Azure Data Factory, ADLS Gen2, Databricks, Synapse Analytics, and Power BI.
- Access to the Tokyo 2021 Olympics dataset.

### Steps to Recreate the Project
1. Clone this repository.
2. Set up Azure resources following the ETL pipeline steps provided here.
3. Use the provided PySpark scripts to perform data transformations in Azure Databricks.
4. Link the transformed data to Azure Synapse Analytics.
5. Build interactive dashboards in Power BI for data visualization.

---

## 🔍 Potential Improvements

### Production-Grade Enhancements
- Add comprehensive logging and monitoring to ADF pipelines.
- Implement security measures like Role-Based Access Control (RBAC).
- Optimize Databricks transformation scripts for better performance.

### Expanded Transformations
- Perform advanced cleaning, such as outlier detection.
- Add feature engineering for enhanced analytics.

### Visualization Completion
- Complete Power BI dashboards to provide actionable insights.
- Focus on medal analysis, participation trends, and team performance.

---

## 📌 Conclusion
This project illustrates the capabilities of Azure services in creating a robust and scalable ETL pipeline. It demonstrates the integration of Azure Data Factory, ADLS Gen2, Databricks, Synapse Analytics, and Power BI for processing and analyzing real-world datasets. While primarily a learning exercise, the project lays the groundwork for production-ready implementations with minor improvements.
