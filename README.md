# ETL - Extract, Transform and Load
*An ETL Movies Analysis using Python, RegEx and SQL Databases*

## Project Overview

### Background
As raw data exists in multiple places and formats, such that in order to perform any kind of data analysis, we need to clean and structure it. Data pipeline process **ETL – Extract, Transform, and Load** is a fundamental concept in the analysis and cunstruction of data and subsequent dataframes, ensuring that data is consistent as well as maintains its integrity. Without consistent and robust data structure, it’s nearly impossible to perform any meaningful analysis. 


### Purpose
**The Amazing Prime**, a video streaming company, decided to sponsor a *hackathon*, where participants trying to predict which low budget movies being released will become popular. Participants of a hackathon need a clean data in order to perform analyses for their algorithms. In order to provide organized and clean dataset, this project focuses on *ETL** process and includes the following:

-	**Extracting** data from two different sources. 
    - web scrape of Wikipedia website for all movies released since 1990
    - data from Kaggle website for rating data.
-	**Transforming** data using Jupyter Notebook, Python, Pandas and Python RegEx module.
-	**Loading** data using PostgreSQL and pgAdmin to host final cleaned data set.

## Overview of the code

The goal of this analysis is to create automated pipeline that extracts, transform and loads data. This analysis consists of four parts, where each step is building up from beginning of extracting data and function testing, through transformation and cleaning process to its final step connect and load to the database. The entire process of ETL can be executed with a single call of the function ***extract_transform_load*** in the final step [ETL_create_database.ipynb](ETL_create_database.ipynb). The ETL process is broken down into four jupyter notebook files:

1.	[ETL_function_test.ipynb](ETL_function_test.ipynb)
    - Data is extracted from the website in JSON and CSV formats.
    - Data is transformed into Pandas data frames.
    - JSON file requires extra step – loading file first and then transforming into data frame.

2.	[ETL_clean_wiki_movies.ipynb](ETL_clean_wiki_movies.ipynb)
    - Function *clean_movie* combines scattered data of alternative languages into one column *alt_titles*. 
    - Its subfunction *change_column_name* organizes column names into consistent pattern.
    - In the function *extract_transform_load* the transformation process of wiki movies data begins and includes:
 
         - Python **list comprehensions**.
         - apply() and map() methods in combination with **lambda functions**.    
         - regular expressions or **RegEx**.
        
3.	[ETL_clean_kaggle_data.ipynb](ETL_clean_kaggle_data.ipynb)
    - Function *extract_transform_load* gets new tasks for cleaning Kaggle data and includes:
    
        - Changing datatypes, using methods pd.to_numeric, astype() and python comparison operators for Boolean types.
        - Filling missing values and filtering unwanted columns.
        - Merging data frames using *pd_merge* method.
        
4.	[ETL_create_database.ipynb](ETL_create_database.ipynb)
    - Finally, the function in its final step connects to the database by **sqlalchemy** library and **to_sql** method. 
    - Complete ETL process can be executed with a single function *extract_transform_load* call.



