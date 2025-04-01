## BigData-ETL-Pipelines-Ecommerce

### Project Description
This project is a comprehensive Big Data ETL pipeline specifically designed to process and analyze Brazilian e-commerce data. It implements data ingestion, transformation, and storage using technologies like Apache Spark, Hadoop, SQL, and cloud services such as Azure and Databricks. The project is structured to ensure scalable and efficient data processing, allowing for advanced analytics and insights.

### Project Flow and Architecture
The architecture of the pipeline follows a hybrid model combining Azure Data Factory for data ingestion, Azure Databricks for data transformation, and Azure Synapse for data visualization. The system leverages the Lakehouse Medallion Architecture on Databricks to ensure structured data flow from raw ingestion to refined insights.

#### Pipeline Flow
1. **Data Ingestion:**
   - Data is ingested from multiple sources including GitHub (via HTTP) and SQL tables.
   - Azure Data Factory is used to move the data to Azure Data Lake Storage Gen2 (ADLS Gen2).

2. **Data Transformation:**
   - Azure Databricks cleans and transforms the data.
   - MongoDB data is used to enrich the information during transformation.
   - The transformed data is stored back in ADLS Gen2.

3. **Data Storage and Visualization:**
   - Data from ADLS Gen2 is processed using Azure Synapse Analytics.
   - Data is visualized using tools like Power BI, Tableau, and Fabric.

#### Architecture Diagram
![Architecture Diagram](Architecture%20Diagram.png)

### Data Handling with Medallion Architecture
The pipeline leverages the Delta Lakehouse Medallion Architecture on Databricks to organize data in three layers:

1. **Bronze Layer:**
   - Raw data ingestion without schema enforcement.
   - Acts as a landing zone for batch and streaming data.

2. **Silver Layer:**
   - Data is cleaned, enriched, and structured.
   - Schema enforcement is applied during transformation.

3. **Gold Layer:**
   - Aggregated data for business insights.
   - High-quality, ready-for-analysis data.

![Medallion Architecture](lakehouse-medallion-architecture.jpeg)

### Data Sources
- **MySQL-DB-Data:**
  - Contains structured data from relational databases.
  - Example screenshot:
  ![MySQL Data](Screenshot%20(14).png)

- **MongoDB-Data:**
  - Contains semi-structured product category data.
  - Example screenshot:
  ![MongoDB Data](Screenshot%20(15).png)

### Building Pipelines on Azure Cloud
The ETL pipeline is hosted and orchestrated using Azure services:
- **Azure Data Factory:** Data movement and orchestration.
- **Azure Databricks:** Data transformation using Spark.
- **Azure Synapse:** Data aggregation and visualization.

![Azure Pipeline](Screenshot%20(23).png)

### Final Data Transformation View
- The final view of the data pipeline shows the processed data in the Gold Layer, ready for analysis and visualization.

![Gold Layer View](Screenshot%20(29).png)

### Usage Instructions
1. **Clone the repository:**
   ```bash
   git clone https://BigData-ETL-Pipelines-Ecommerce.git$###
   ```
2. **Setup Environment:**
   - Install Apache Spark, Hadoop, and required libraries.
   - Configure Azure and Databricks integration.
3. **Run Data Transformation:**
   - Use Databricks notebooks to execute the ETL tasks.

### Results and Visualization
Data processed through this pipeline can be visualized using Power BI, Tableau, or Fabric, allowing for comprehensive insights and business intelligence applications.

### Contribution Guidelines
Contributions to improve data processing efficiency, scalability, or analytics features are welcome. Please open a pull request with a detailed description of changes.

### License
This project is licensed under the MIT License.

