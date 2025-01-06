# Project_NYC_Taxi_2023

This document outlines the end-to-end data engineering pipeline for processing NYC Taxi data based on Medallion Architecture.

* Project Architecture*

![image](https://github.com/user-attachments/assets/ca6385a2-93cb-4d51-92f8-7298a5f7a5de)

* *Data Flow:* 
    * Raw data is extracted from the source and stored in ADLS bronze container using ADF.
    * Raw data is processed and transformed in Databricks and stored in ADLS silver container.
    * Delta tables are created in ADLS gold container for optimized data storage.
    * Data is visualized in Power BI using Databricks connections to ADLS.
* *Tools & Technologies:*
    * Azure Data Factory (ADF)
    * Azure Data Lake Storage (ADLS)
    * Databricks (with Delta Lake)
    * Power BI

* Data Extraction*

* *Source:* NYC Taxi website (dynamically extracted)
* *Method:* Azure Data Factory (ADF) with Linked Services
* *Destination:* Azure Data Lake Storage (ADLS) - Bronze Container
    * Raw, unprocessed data is stored in this container.

* Data Transformation*

* *Tool:* Databricks 
* *Functions:* withColumnRenamed(), withColumn(), split(), select(), etc...
* *Destination:* ADLS - Silver Container
    * Cleaned and transformed data is stored in this container.

* Data Storage & Lakehouse*

* *Tool:* Delta Lake on Databricks
* *Process:* 
    * Created Delta tables for optimized data storage and efficient queries.
    * Leveraged Delta Lake features like Data versioning & time travel.
* *Destination:* ADLS - Gold Container
    * Data is stored in this container in the form of Delta Tables.

* Data Visualization*

* *Tool:* Power BI
* *Connection:* Connected ADLS storage to Power BI using Databricks.
* *Dashboards:* Created interactive dashboards to visualize key metrics and insights from the NYC Taxi data:
![image](https://github.com/user-attachments/assets/d271f27c-cab8-49ce-ba16-4d5dc3b50c08)

