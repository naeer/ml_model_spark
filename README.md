# Analysis of New York Taxi and Limousine Commission (TLC)

## Overview
The New York Taxi and Limousine Commission (TLC) is an agency created in 1971 with the responsibility of licensing and regulating New York City’s taxi cabs along with for-hire vehicles, commuter vans and paratransit vehicles. Since 2009, TLC has been publishing trip records for these vehicles, which now equate to millions of rows of trip records. The aim of this project is to take the dataset for both yellow and green taxi cabs from January 2019 to April 2022 and analyse it and finally build a machine learning model to predict the total fare amount of each trip.

## Data Understanding
Yellow taxi cabs are those traditional iconic taxi cabs on the streets of New York city that can be hailed from anywhere in the city. They are allowed to respond to a street hail from a passenger in all of the five boroughs.

To increase the availability of taxis in the boroughs, Green taxis were introduced in August of 2013.

The dataset for yellow and green taxi cabs from January 2019 to April 2022 were downloaded from [New York city’s official website](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page). Each month had two separate parquet files containing the trip records for yellow and green taxis for that particular month. The rows in these individual files represent one trip made during that particular month. In total, 80 files were downloaded, which made up the whole dataset for the project.

## Overall Architecture

![](https://github.com/naeer/ml_model_spark/blob/main/images/architecture.png?raw=true)

The overall architecture of the project can be described in 4 parts. They are:
1. Azure Blob Storage: At the start of the project, all the data downloaded from New York city’s official website is uploaded to the Azure Storage Container to be later mounted to Databricks.
2. Databricks: After the data has been uploaded to the Azure storage container, the storage blob
container is then mounted into the Databricks File System. This allows the user to access all the
files stored in the Azure storage container from Databricks.
3. Data Analysis: Once the storage container has been mounted into the Databricks File System,
the data is loaded, cleaned, transformed, and prepared for analysis. The data is then examined
to find valuable insights.
4. Machine Learning Model: After the data has been cleaned and prepared for analysis, it is then
cleaned and prepared for modelling. Once it has been prepared, two machine learning models, namely Linear Regression and Decision Tree Regression, are applied to predict the total fare amount of each trip.

## ML models
Two machine learning models, namely Linear Regression and Decision Tree Regression, were applied to the combined data of the yellow and green taxis to predict the total amount charged to the customer for each trip.

The data was split into train and test sets. 75% of the data were randomly taken in the train set and the rest 25% were taken in the test set.

| Model | RMSE (train set) | RMSE (test set) |
| --- | --- | --- |
| Linear Regression | 145.321 | 175.827  |
| Decision Tree Regression | 145.316| 175.824 |

Both linear regression and decision tree regression did similarly well in terms of predicting the target variable as they had similar root mean squared error in both the train and test sets. However, the linear regression model took one-third the time of the decision tree regression model to fit the model to the data. 
