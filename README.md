Sparkify is the next generation music provider to all users with free and paid subscriptions. The company collects and stores music and data related to the artists & songs. Aim of this project is to extract data from logs collected from users and develop ETL pipeline to transfer data from the JSON files to Postgresql database.  ETL pipeline is designed to start from creation of tables and continues with the insertion of data to tables. Fact table is filled at the end of the process by using dimension tables.

Database is designed as 4 dimension & 1 fact tables. Dimension tables are as following: 

#### 1- Users
    Description: users in the app
    Columns: user_id, first_name, last_name, gender, level
    
#### 2- Time
    Description: time dimension table for the timestamp of records
    Columns: start_time, hour, day, week, month, year, weekday

#### 3- Songs
    Description: songs provided in the app
    Columns: start_time, hour, day, week, month, year, weekday
#### 4- Artists
    Description: time dimension table for the timestamp of records
    Columns: start_time, hour, day, week, month, year, weekday

Fact tables are as following:
* Song plays of users in time-series format

Design of the dimension tables satisfy the rule of only storing data which are related to the primary key of the table.

------
    
### *Script Files:*
    * create_tables.py
        - This script is used to create fact and dimension tables. First database connection will be established, then tables to be created are dropped at first, then recreated create_tables. main function handles all process at once
    * sql_queries.py
        - This file contains the drop, create, and insert queries for the ETL process. 
    * etl.py
        - This script is run the entire ETL process for every song and log file in the source data. Destination is the postgresql database.

### *How to run the files*
1) Run create_tables.py
2) Run etl.py
3) Run each cell of test.ipynb to see the results of the ETL pipeline