# Cleaning Data with SQL 

## Overview
The purpose of this exercise was to demonstrate my data cleaning skills in SQL using an [automobiles dataset](https://archive.ics.uci.edu/ml/datasets/Automobile) from the UCI Machine Learning Repository. The CSV file automobile_data was uploaded into PostgreSQL, reviewed, and cleaned. Following, the cleaned data was exported back into a new CSV file titled, cleaned_automobile_data. 

The creation of the data table in PostgreSQL is stored as the "Schema" file. All SQL queries and edits to the data are stored in the "Cleaning" file. 

## Analysis
The automobile_data CSV file contains 26 attributes for 205 car models. Data categories include the following: make, fuel type, number of doors, body style, wheel drive, engine location, wheel base, length, width, height, curb weight, engine type, number of cylinders, engine size, fuel system, compression ratio, horesepower, city mileage, highway mileage, and price.  

#### Fill in missing number of doors data
A review of the num_of_doors column indicates that there are two blank entries. After confirming the number of doors for each of these entries is four, the null values for the two rows were updated to reflect this information. 

#### Identify potential errors in number of cylinders data
A query was run to look at the distinct types of cylinders. This query indicated that there were two entries for two cylinders, however, one of the entries was mispelled as "tow". The mispelled cylinder type was updated.

####  Spot potential errors in compression ratio data
According to the data description, all values in the compression_ratio column should fall within the range of 7 to 23. A query of the minimum and maximum values in the range for this column indicates that there is one entry in which the compression ratio is 70. After consideration, it was determined that the best course of action for this entry was to delete the entire row. This row was removed from the data set.  

#### Ensure consistency in the wheel drive data
A query of the wheel_drive column was run to identify the distinct types of wheel drive. Two entries were returned for four wheel drive. A length statement was used to determine that one entry was input as "4wd" while the other was input as "4wd ". To standardize the entries for four wheel drive, the TRIM function was used to remove the space from the "4wd " entries. 

## Summary
Data cleaning is a critical component of analysis. Data cleaning enables you to find missing data, spot errors and typos, and to standandarize entries for consistency. Properly cleaned data strengthens the validity of any analysis and allows you to feel more confident in your conclusions. 
