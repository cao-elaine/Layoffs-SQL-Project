# Layoffs SQL Project

## Overview
This project involves cleaning and analyzing a dataset of company layoffs from 2022 onwards. The analysis provides insights into layoff trends across different industries, countries, and time periods. The project was completed using MySQL following [Alex The Analyst's](https://www.youtube.com/c/AlexTheAnalyst) SQL tutorial series.

## Data Source
The dataset was sourced from [Kaggle's Layoffs 2022 dataset](https://www.kaggle.com/datasets/swaptr/layoffs-2022), which contains information about company layoffs including:
- Company name
- Location
- Industry
- Total number of employees laid off
- Percentage of workforce laid off
- Date of layoff
- Company stage (e.g., Seed, Series A, Post-IPO)
- Country
- Total funds raised (in millions)

## Project Objectives
1. Clean and prepare the layoffs dataset for analysis
2. Perform exploratory data analysis to uncover insights about layoff trends
3. Practice SQL data manipulation and analysis techniques

## Data Cleaning Methodology
The data cleaning process involved several key steps:

1. **Removing Duplicates**
   - Used ROW_NUMBER() with PARTITION BY to identify duplicate records
   - Created a staging table to work with the data
   - Removed records with duplicate values across all relevant fields

2. **Standardizing Data**
   - Trimmed whitespace from company names
   - Standardized industry names (e.g., consolidated "Crypto" variations)
   - Removed trailing periods from country names
   - Converted date strings to proper DATE format

3. **Handling Null and Blank Values**
   - Identified records with NULL values in critical fields
   - Populated missing industry values where possible using data from other records of the same company
   - Removed records with NULL values in both total_laid_off and percentage_laid_off fields

4. **Removing Unnecessary Fields**
   - Dropped temporary columns used during the cleaning process

## Exploratory Data Analysis
The analysis explored several aspects of the layoffs data:

1. **Companies with Highest Layoffs**
   - Identified companies that laid off the most employees
   - Analyzed companies that laid off 100% of their workforce

2. **Industry Analysis**
   - Determined which industries experienced the most layoffs
   - Examined the relationship between industry and layoff percentages

3. **Geographical Trends**
   - Analyzed layoffs by country
   - Identified regions most affected by workforce reductions

4. **Temporal Analysis**
   - Tracked layoff trends over time (by year and month)
   - Created rolling totals to visualize cumulative layoffs

5. **Company Stage Analysis**
   - Examined how company stage (Seed, Series A, Post-IPO, etc.) relates to layoff numbers

6. **Funding Relationship**
   - Investigated the relationship between funds raised and layoff numbers

## Technologies Used
- MySQL for data cleaning and analysis
- SQL queries including:
  - Window functions (ROW_NUMBER, SUM OVER)
  - Common Table Expressions (CTEs)
  - Aggregate functions
  - Date manipulation
  - String functions
  - Joins for data enrichment

## How to Use This Project
1. Import the `layoffs.csv` file into your MySQL database
2. Run the `Data cleaning.sql` script to clean and prepare the data
3. Execute queries from `Exploratory Data Analysis.sql` to reproduce the analysis
4. Modify or create new queries to explore additional aspects of the data

## Key Findings
- Companies in certain industries (like Tech) experienced more significant layoffs
- Post-IPO companies tended to have larger layoff events
- Layoff trends showed distinct patterns over time, with certain months showing higher activity
- There's a complex relationship between company funding and layoff decisions

## Acknowledgments
- [Alex The Analyst](https://www.youtube.com/c/AlexTheAnalyst) for the excellent SQL tutorial that guided this project
- [Kaggle](https://www.kaggle.com/) for providing the layoffs dataset
