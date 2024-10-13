# Data Modeling with Postgres: Sparkify 


## Project Purpose

The purpose of this project is to create a database to store and organize Sparkify's song play data and user activities. 
In this project we will desgin a database schema and implement ETL pipeline for efficient query and data analytics. 
In this system we will transform raw JSON data from log files and song metadata stored locally into strucutred tables for better analysis.

## How to Run the Python Scripts

   - Run the 'sql_queries.py' 
   - Run the 'create_tables.py' to create tje Sparkify database.
   - Run the 'etl.py' script to extract, tranform, and load data into the database.
   - Run 'test.ipynb' to verify the successfull creation of the database and the columns. 


## Explanation of files in the repository

- **create_tables.py**: This script drops any existing tables in the database and creates new tables defined by the schema. It should be run every time before the executing the ETL process.

- **etl.ipynb**: This notebook is used to develop ETL processes for each table from the song_data and log_data files, and load data into the respective tables in database.
  
- **etl.py**: This script processes the JSON files containing raw song and log data and loads it into the database. It extracts data from JSON files, transforms it into the required format, and inserts it into the fact and dimension tables.
  
- **sql_queries.py**: This script contains all the SQL statements, for table creation, data insertion and querying.
  
- **test.ipynb**: This notebook is used to test and validate the database by running simple queries to ensure data is loaded correctly.

- **README.md**: This file explains the project purpose, setup steps, database design, and instructions to run the scripts.


## Database Schema Design

The database uses a **Star Schema** design, for this project. The schema consists of one **Fact Table** ('songplays') and four **Dimension Tables** ('users', 'songs', 'artist', 'time'):

### Fact Table:

- **songplays**: Contains records of each user’s song play activity (based on log files).

### Dimension Tables:

- **users**: Stores user information, like user id, first name, last name, gender, and level.
- **songs**: Stores details about the songs, including song id, title, artist id, year, and duration.
- **artists**: Stores artist information like artist id, name, location, latitude, and longitude.
- **time**: Stores timestamps of records in songplays such as start time, hour, day, week, month, year and weekday.

### Justification for Schema Design:

- The star schema is designed for easy querying and analysis, where the **songplays** fact table links to the **users**, **songs**, **artists**, and **time** dimension tables. This setup is supports efficient querying and analysis of song plays, user engagement. 
