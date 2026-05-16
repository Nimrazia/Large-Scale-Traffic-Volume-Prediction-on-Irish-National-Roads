# Large-Scale Traffic Volume Prediction using Apache Spark

## Project Overview
This project was developed for the **CS6502 – Applied Big Data and Visualization** module at the **University of Limerick**. The goal of the project is to build a scalable big data and machine learning pipeline using **Apache Spark** on **Databricks** to predict hourly traffic volume on Irish national roads.

The project uses a large traffic dataset containing **7.5+ million records** from Irish national road sensors across 2019. Since the module focuses on **Big Data**, the project emphasizes:
- distributed data processing with **Apache Spark**
- scalable data cleaning and feature engineering with **Spark DataFrames / Spark SQL**
- predictive modelling with **Spark MLlib**
- evaluation and optimization of regression models for large-scale data

The target variable is:
- **`vehicle_count`** → hourly vehicle volume

---

## Team Members
- **Krithikaa Jothi Prakash** – 25287591
- **Hari Gokul Ganesan Kalavathi** – 25287613
- **Sidharthan Jayavelu** – 25110004
- **Nimra Zia** – 25009877
- **Sheetal Padmanabhan** – 25022911
- **Ishitha Prakashan** – 25181483

---

## Problem Statement
Raw traffic sensor data is very large, fine-grained, and not directly suitable for analytics or prediction. The challenge in this project is to:
1. ingest large-scale traffic data efficiently,
2. clean and preprocess it in a distributed environment,
3. engineer meaningful traffic features,
4. train regression models using Spark ML,
5. compare baseline models,
6. optimize the best-performing model.

The final objective is to accurately predict hourly traffic volume for a road sensor and lane using historical traffic characteristics and temporal features.

---

## Dataset Summary
The dataset contains Irish national road traffic sensor records for **2019**, organized into four quarterly tables.

### Key dataset characteristics
- **Source**: Irish national road traffic sensor data
- **Time period**: January 2019 – December 2019
- **Raw records**: 7,579,711
- **Records after cleaning**: ~7.5 million
- **Granularity**: Hourly aggregated observations
- **Target**: `vehicle_count`
- **Environment**: Databricks Community Edition

The dataset is large enough to justify the use of distributed data processing and Spark-based modelling.

---

## Tech Stack
- **Apache Spark**
- **PySpark**
- **Spark SQL**
- **Spark MLlib**
- **Databricks Community Edition**
- **Python**
- **Matplotlib / visualization outputs from notebooks**

---

## Project Workflow
The project follows a full big data analytics pipeline.

### 1. Data Ingestion and Aggregation
- Loaded quarterly traffic tables into Spark DataFrames
- Combined them into a single large dataset
- Aggregated sensor-level traffic observations into hourly records

### 2. Data Cleaning and Preprocessing
- Checked for duplicate records
- Handled missing values in standard deviation columns
- Performed outlier detection
- Prepared data for large-scale modelling in Spark

### 3. Exploratory Data Analysis (EDA)
- Generated summary statistics
- Studied temporal traffic patterns
- Analyzed sensor/lane-based variations
- Visualized traffic behaviour and feature distributions

### 4. Feature Engineering
Created and refined features relevant to traffic prediction, including:
- temporal attributes,
- traffic behaviour measures,
- lane/location information,
- derived categorical and numerical variables.

### 5. Feature Analysis and Selection
- Checked feature correlations
- Assessed feature importance
- Selected the most useful predictors for model training

### 6. Baseline Modelling
Implemented multiple regression models in **Spark MLlib**:
- Linear Regression
- Generalized Linear Regression
- Decision Tree Regressor
- Random Forest Regressor
- Gradient Boosted Tree Regressor

### 7. Hyperparameter Tuning
- Tuned the best-performing model
- Compared tuned performance against baseline results

### 8. Final Model Evaluation
- Measured model quality using regression metrics
- Compared models using **RMSE**, **MAE**, and **R²**
- Interpreted feature importance and prediction performance

---

## Notebook Structure
The project is organized into the following notebooks:

1. **`1_traffic_count_data_aggregator.ipynb`**  
   Aggregates raw traffic data into modelling-ready hourly records.

2. **`2_DATA_PREPROCESSING.ipynb`**  
   Handles cleaning, missing values, and preprocessing steps.

3. **`3_FEATURE_ANALYSIS_IMPORTANCE_SELECTION.ipynb`**  
   Performs correlation analysis, feature importance analysis, and selection.

4. **`4_EDA.ipynb`**  
   Contains exploratory data analysis and visualizations.

5. **`5_BASELINE_MODELLING.ipynb`**  
   Trains and evaluates baseline Spark ML regression models.

6. **`6_HYPERPARAMETER_TUNING_OPTIMISATION.ipynb`**  
   Tunes model hyperparameters for improved performance.

7. **`7.FINAL MODEL.ipynb`**  
   Builds and evaluates the final optimized model.

---

## Model Performance Summary
Among the tested Spark ML regression models, **Gradient Boosted Tree Regressor (GBT)** performed best overall.

### Best model
- **Model**: Gradient Boosted Tree Regressor
- **Why it performed best**:
  - captures non-linear traffic patterns,
  - handles complex feature interactions,
  - performs strongly on structured tabular traffic data.

### Evaluation metrics used
- **RMSE** – Root Mean Squared Error
- **MAE** – Mean Absolute Error
- **R²** – Coefficient of Determination

The tuned final model improved over baseline performance and provided the strongest predictive accuracy in the project.



## How to Run the Project
### Prerequisites
- Databricks Community Edition or another Spark environment
- Access to the source traffic dataset/tables
- PySpark and Spark ML support

### General execution order
Run the notebooks in this order:
1. `1_traffic_count_data_aggregator.ipynb`
2. `2_DATA_PREPROCESSING.ipynb`
3. `4_EDA.ipynb`
4. `3_FEATURE_ANALYSIS_IMPORTANCE_SELECTION.ipynb`
5. `5_BASELINE_MODELLING.ipynb`
6. `6_HYPERPARAMETER_TUNING_OPTIMISATION.ipynb`
7. `7.FINAL MODEL.ipynb`


## Outputs
The project produces:
- cleaned and transformed Spark DataFrames
- exploratory visualizations
- feature analysis outputs
- baseline model comparisons
- tuned model results
- final performance metrics
- academic report and supporting documentation


## Learning Outcomes
This project demonstrates practical understanding of:
- big data preprocessing with Spark,
- distributed analytics,
- Spark SQL and DataFrame transformations,
- large-scale feature engineering,
- regression modelling with Spark MLlib,
- model evaluation and hyperparameter tuning,
- presenting end-to-end analytics in an academic report.


## Future Improvements
Possible extensions for this project include:
- incorporating real-time traffic streams,
- adding external data such as weather and incidents,
- testing advanced ensemble or deep learning methods,
- deploying the pipeline as an end-to-end traffic analytics application,
- building interactive dashboards for real-time monitoring.


## Module Context
This project was completed as part of:
**CS6502 – Applied Big Data and Visualization**  
**University of Limerick**

It reflects module themes such as:
- distributed data processing,
- Spark-based analytics,
- machine learning at scale,
- big data visualization,
- end-to-end data pipeline design.


## Repository Contents
- `1_traffic_count_data_aggregator.ipynb`
- `2_DATA_PREPROCESSING.ipynb`
- `3_FEATURE_ANALYSIS_IMPORTANCE_SELECTION.ipynb`
- `4_EDA.ipynb`
- `5_BASELINE_MODELLING.ipynb`
- `6_HYPERPARAMETER_TUNING_OPTIMISATION.ipynb`
- `7.FINAL MODEL.ipynb`
- project report
- supporting visuals / outputs

