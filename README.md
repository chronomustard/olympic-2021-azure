# Data Pipeline Documentation

This repository contains documentation for the data pipeline created to handle the 2021 Olympics data sourced from Kaggle. The pipeline includes steps for data extraction, loading, transformation, and storage using various Azure services.

## Data Source
The data is sourced from Kaggle's database [2021 Olympics in Tokyo](https://www.kaggle.com/datasets/arjunprasadsarkhel/2021-olympics-in-tokyo).

## Pipeline Overview

![image](https://github.com/chronomustard/olympic-2021-azure/assets/70846916/2aa6f96e-04a3-476b-8e27-ac5a376e7cab)

The data pipeline consists of the following steps:

1. **Extraction**: Data is extracted from the Kaggle database.
2. **Loading to GitHub**: Extracted data is loaded into GitHub repository.
3. **Azure Data Factory**: Data is loaded onto Azure using HTTP in the Azure Data Factory.
4. **Storage**: Raw data is stored in Azure Storage Datalake.
5. **Transformation**: Data is transformed using Azure Databricks and Apache Spark.
6. **Loading to Azure Storage Datalake**: Transformed data is loaded again to Azure Storage Datalake.

## Detailed Process

### 1. Extraction
Raw data is extracted from the Kaggle database by downloading the dataset available at [2021 Olympics in Tokyo](https://www.kaggle.com/datasets/arjunprasadsarkhel/2021-olympics-in-tokyo) in xlsx format.

### 2. Loading to GitHub
Extracted data is loaded into GitHub repository for version control and collaboration purposes.

### 3. Azure Data Factory
The extracted xlsx data is then loaded onto Azure using HTTP in the Azure Data Factory and sinked in csv format. This step ensures seamless data transfer to Azure services.

### 4. Loading Raw Data to Azure Storage Datalake

![image](https://github.com/chronomustard/olympic-2021-azure/assets/70846916/fd7350bb-beed-42cb-a32a-e34194e1d734)

Raw data is stored in Azure Storage Datalake, providing a scalable and secure storage solution for large datasets.

### 5. Transformation

![image](https://github.com/chronomustard/olympic-2021-azure/assets/70846916/537f72e5-9c94-4bc6-9e92-cb700789057c)

Data transformation is performed using Azure Databricks, leveraging the power of Apache Spark for processing large-scale data efficiently. Various transformations such as cleaning, filtering, and aggregating are applied to prepare the data for further analysis.

### 6. Loading Transformed Data to Azure Storage Datalake

![image](https://github.com/chronomustard/olympic-2021-azure/assets/70846916/a4397fc5-f55d-4502-b6f8-11f5de325547)

The transformed data is then loaded again to Azure Storage Datalake, making it available for downstream applications and analytics.

## Repository Structure
```
|- data/
   |- raw-data/
      |- Teams.xlsx  # Raw data extracted from Kaggle
      |- Medals.xlsx  # Raw data extracted from Kaggle
      |- ...  # Raw data extracted from Kaggle
   |- transformed-data/
      |- AvgGenderASC  # Transformed data
          |- AvgGenderASC.csv  # Transformed data
|- data_transformation.py  # Script for data transformation using Azure Databricks
|- README.md  # Documentation for the data pipeline
```

## Prerequisites
- Access to Kaggle dataset: [2021 Olympics in Tokyo](https://www.kaggle.com/datasets/arjunprasadsarkhel/2021-olympics-in-tokyo)
- Azure subscription with access to Azure Data Factory, Azure Storage, and Azure Databricks.

## Usage
1. Clone this repository.
2. Extract the raw data from Kaggle and place it in the `data/raw-data/` directory in your Azure Storage Datalake.
3. Configure Azure Data Factory to load data from GitHub repository.
4. Execute the data transformation script `data_transformation.py` using Azure Databricks.
5. Access the transformed data stored in `data/transformed-data/` directory in your Azure Storage Datalake.

## Contributors
- [chronomustard](https://github.com/chronomustard)

## License
This project is licensed under the [MIT License](LICENSE).
