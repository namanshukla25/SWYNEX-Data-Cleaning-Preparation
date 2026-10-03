# SWYNEX - Data Cleaning & Preparation

## Project Overview

This project was completed as part of the SWYNEX Data Analyst Internship task.

The objective of this project was to inspect a raw dataset, identify data quality issues, clean and prepare the data, and save the final cleaned dataset for further analysis.

## Dataset

Dataset: Cafe Sales - Dirty Data for Cleaning Training

The dataset contains cafe transaction records with information about:

- Transaction ID
- Item
- Quantity
- Price Per Unit
- Total Spent
- Payment Method
- Location
- Transaction Date

The original dataset contains 10,000 rows and 8 columns.

## Tools Used

- Python
- Pandas
- NumPy
- Jupyter Notebook
- VS Code

## Data Quality Issues Identified

During the inspection of the raw dataset, the following issues were identified:

1. Missing values in multiple columns.
2. `UNKNOWN` and `ERROR` values in the dataset.
3. Numeric columns stored as text/object data types.
4. Transaction Date stored as text instead of a datetime format.
5. Missing values in categorical columns such as Item, Payment Method and Location.
6. Missing values in Quantity, Price Per Unit and Total Spent.
7. Duplicate rows were checked.

## Data Cleaning Performed

### 1. Handled Invalid Placeholder Values

`UNKNOWN` and `ERROR` values were converted into proper missing values using Pandas.

### 2. Converted Numeric Columns

The following columns were converted into numeric data types:

- Quantity
- Price Per Unit
- Total Spent

### 3. Converted Transaction Date

The Transaction Date column was converted into datetime format.

### 4. Handled Missing Categorical Values

Missing values in categorical columns were replaced with:

`Unknown`

This was done because the original category could not be reliably determined.

### 5. Recovered Numeric Values

Where possible, missing numeric values were recovered using the relationship:

`Total Spent = Quantity × Price Per Unit`

For example:

- Missing Quantity was calculated when Total Spent and Price Per Unit were available.
- Missing Price Per Unit was calculated when Total Spent and Quantity were available.
- Missing Total Spent was calculated when Quantity and Price Per Unit were available.

### 6. Duplicate Check

Duplicate rows were checked during the cleaning process.

No complete duplicate rows were found.

## Data Validation

The cleaned dataset was validated by checking:

- Missing values
- Duplicate records
- Data types
- Numeric values
- Transaction dates
- Relationship between Quantity, Price Per Unit and Total Spent

The calculated Total Spent was checked against:

`Quantity × Price Per Unit`

for records where the required numeric values were available.

## Final Dataset

The cleaned dataset contains:

- 10,000 rows
- 8 columns

The original raw dataset was preserved separately from the cleaned dataset.

## Project Structure

```text
SWYNEX-Data-Cleaning-Preparation
│
├── data
│   ├── dirty_cafe_sales.csv
│   └── cleaned_cafe_sales.csv
│
├── notebooks
│   └── data_cleaning.ipynb
│
└── README.md