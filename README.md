Sparkify is the next generation music provider to all users with free and paid subscriptions. The company collects and stores music and data related to the artists & songs. Aim of this project is to extract data from logs collected from users and develop ETL pipeline to transfer data from json files to Postgresql database. 

Database is designed in dimension & fact table formats. Dimension tables are as following: 
* Users
* Time
* Songs
* Artists

Fact tables are as following:
* Song plays of users in time-series format

Design of the dimension tables satisfy the rule of only storing data which are related to the primary key of the table. 

ETL pipeline is designed to start from creation of tables and continues with the insertion of data to tables. Fact table is filled at the end of the process by using dimension tables.


