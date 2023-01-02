# Analysis of New York Taxi and Limousine Commission (TLC)

## Overview
The New York Taxi and Limousine Commission (TLC) is an agency created in 1971 with the responsibility of licensing and regulating New York City’s taxi cabs along with for-hire vehicles, commuter vans and paratransit vehicles. Since 2009, TLC has been publishing trip records for these vehicles, which now equate to millions of rows of trip records. The aim of this project is to take the dataset for both yellow and green taxi cabs from January 2019 to April 2022 and analyse it and finally build a machine learning model to predict the total fare amount of each trip.

## Data Understanding
Yellow taxi cabs are those traditional iconic taxi cabs on the streets of New York city that can be hailed from anywhere in the city. They are allowed to respond to a street hail from a passenger in all of the five boroughs.

To increase the availability of taxis in the boroughs, Green taxis were introduced in August of 2013.

The dataset for yellow and green taxi cabs from January 2019 to April 2022 were downloaded from [New York city’s official website](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page). Each month had two separate parquet files containing the trip records for yellow and green taxis for that particular month. The rows in these individual files represent one trip made during that particular month. In total, 80 files were downloaded, which made up the whole dataset for the project.
