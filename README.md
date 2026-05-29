## Refining a Stock Clearance File for Retail Analysis

## PROJECT OVERVIEW 

This document provides an overview of the transformation of a raw stock clearance dataset into a clean, higher efficiency dataset for the purpose of retail analysis. There are numerous steps taken as part of this transformation including extraction, unpacking, unzipping, data loading, and data cleaning, and high-efficiency data and functional enhancements through feature engineering and memory optimization. 

## DATASET OVERVIEW 

SOURCE FILE = archive.zip (unpacked to Combined_dataset.csv) 

ORIGINAL DATASET DIMENSIONS = 1,000 rows x 2 4 columns 

FINAL DATASET DIMENSIONS = 1,000 rows x 1 3 columns 

FINAL OUTPUT FILE = fully_optimized_shopping_data.csv 

## DATA CLEANING AND FUNCTIONAL ENHANCEMENTS 

## Extract & Load

Uncompressed the raw file and resolved pathing issues prior to creating a Pandas DataFrame of the contents.

## Handling of Missing Values

0.0 values were assigned to all null discount values. 

All text fields without any ‘name’ or ‘key’ were populated with the phrase “Not Available.” 

## Text standardisation

All product title and category fields were changed to Title Case. 

Regex was used to remove all hyphen and special character occurrences throughout the entire dataset for improved readability. 

## Removing Duplicates

The product_id was used as the unique key to verify and validate all of the product records to ensure that each product had only one entry.

## Derived Feature Engineering 

Calculated total_amount based on the price and random quantity column.

Created price_segments (Budget, Mid Range, Premium) using vectorised binning of product price.

Created rating_classifications (Low, Average, High) using customer feedback for each product.

Calculated discount_pct and savings data points for all records.

## Removed Outliers 

Prices that were outside the IQR range for each product were flagged for follow-up.

## Memory Optimisation 

Changed category from a high cardinality string type to the category data type to reduce memory usage from approximately 187kb to approximately 84kb.
Changed category from a high cardinality string type to the category data type to reduce memory usage from approximately 187kb to approximately 84kb.

