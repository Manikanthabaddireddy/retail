
# Retail Data Pipeline

## Overview

This project demonstrates a retail data pipeline that simulates customer, product, and order data generation, ingestion, and transformation for analysis and reporting.

## Technologies Used

Django: Web framework for data generation application\
MySQL: On-premise database for storing generated data\
Azure Data Factory: Cloud-based ETL service for data ingestion and transformation\
Azure Data Lake Storage: Scalable cloud storage for landing and raw zones\
Snowflake: Cloud data warehouse for storing transformed data
## Project Structure

app (Django application):\
adf (Azure Data Factory pipelines):\
ingestion_pipeline: Defines pipeline for copying data from MySQL to Azure Data Lake\
transformation_pipeline: Defines pipeline for transforming data and loading to Snowflake\
snowflake_scripts:\
create_tables: SQL script to create OLAP tables in Snowflake
## Data Flow

Data Generation:

Users interact with Django forms to create data for customers, products, and orders.
Data is stored in the MySQL database.

Ingestion Pipeline:Azure Data Factory pipeline (ingestion_pipeline) is triggered periodically.
Data is copied from MySQL to Azure Data Lake Storage (landing zone).

Raw Zone:Data is copied from the landing zone to the raw zone in Azure Data Lake Storage.
Data is partitioned by date for efficient storage and retrieval.
Transformation:Azure Data Factory pipeline (transformation_pipeline) is triggered when new data arrives in the raw zone.
Data is transformed and prepared for loading into Snowflake OLAP tables.

Snowflake:Snowpipe automatically loads transformed data into Snowflake tables upon arrival.
Data is ready for analysis and reporting in Snowflake.
## Setup and Usage

Prerequisites:\

Azure subscription with Data Factory and Data Lake Storage Gen2 enabled
Snowflake account\
Python 3.x with Django and required libraries\
Clone the repository:\
git clone https://github.com/your-username/retail-data-pipeline.git\

Set up Azure resources and Snowflake connection:

Create Azure Data Factory and Data Lake Storage resources.\
Create Snowflake database and tables (using create_tables.sql).\
Configure connections in Azure Data Factory.\
Run the Django application:\
python manage.py runserver
Access the forms at http://127.0.0.1:8000/
Trigger Azure Data Factory pipelines:

Manually or set up a schedule.
## Additional Information

Data Model: Add a diagram or description of the data model used for customers, products, and orders.
ETL Logic: Explain any specific transformations or cleansing applied to the data.
Reporting: Describe potential use cases for the transformed data in Snowflake.
## Contributions

Pull requests are welcome!
