# Movies-ETL project
## `-Contents-`	
	
- [Overview of the Project](#overview-of-the-creation-an-automated-pipeline)	
- [Resources](#resources)	
- [The result of the creation an automated pipeline](#the-result-of-the-creation-an-automated-pipeline)	
  - [1. Writing an ETL Function to Read Three Data Files](#Writing-an-ETL-Function-to-Read-Three-Data-Files)	
  - [2. The ETL the Wikipedia Data](#The-extraction-and-transformation-the-Wikipedia-Data)
  - [3. The ETL the Kaggle Data](#The-extraction-and-transformation-the-Kaggle-Data)
  - [4. The creation the Movie Database](#The-creation-the-Movie-Database)
	
## `Overview of the creation an automated pipeline`	
	
The purpose is to create an automated pipeline that takes in new data, performs the appropriate transformations, and loads the data into existing tables by creating one function that takes in the three files—Wikipedia data, Kaggle metadata, and the MovieLens rating data—and performs the ETL process by adding the data to a PostgreSQL database.

## `Resources`	
The automated pipeline is created by using following resources:	
  - Data Source: [Resources](./Resources/)	
  - Software: Python 3.8.8, Pandas 1.2.4, Jupyter-notebook 6.3.0, PostgreSQL 11.12 and pgAdmin 5.5.	
## `The result of the creation an automated pipeline`
#### `1. Writing an ETL Function to Read Three Data Files`
  The creation an function that reads in the three data files and creates three separate DataFrames is in the [ETL_function](./ETL_function_test.ipynb) file.

  Based on the result of the function the DateFrames are:
    - Wiki_movies_df has 7,310 rows and 193 columns;
    - Kaggle_metadata has 45,465 rows and 24 columns;
    - Ratings has 4 rows and 26,024,289 rows.

#### `2. The extraction and transformation the Wikipedia Data`
  The creation an function that extract and transform the Wikipedia data and catch errors by a try-except block with a regular expression string and dropping duplicates is in the [ETL_clean_wiki_movies](./ETL_clean_wiki_movies.ipynb) file.
  
  The following columns are cleaned in the Wikipedia DataFrame:
  - the box office column;
  - the budget column;
  - the release date column;
  - the running time column.
#### `3. The extraction and transformation the Kaggle Data`
  The extraction and transformation Kaggle metadata and MovieLens rating data, also the merged data of the Kaggle DataFrame with the Wikipedia movies DataFrame and with the MovieLens rating DataFrame are in the [ETL_clean_wiki_movies](./ETL_clean_wiki_movies.ipynb) file.
#### `4. The creation the Movie Database`
  The addition of the merged movies_df DataFrame and MovieLens rating CSV data to a SQL database is in the [ETL_create_database](./ETL_create_database.ipynb) file.
 
  Screenshot of query and the output of the movies_df is following:
![image](https://user-images.githubusercontent.com/68247343/130376984-6612f53b-a623-4d82-8741-0eaef8132286.png)


  Screenshot of query and the output of the MovieLens rating is following:
![image](https://user-images.githubusercontent.com/68247343/130376997-6e492eb9-578e-4e6c-88fb-8319f7bca4c1.png)
  
