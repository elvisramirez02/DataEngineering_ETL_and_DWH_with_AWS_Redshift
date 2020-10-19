# Summary of project

Startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

# How to run the python scripts

To create the database tables and run the ETL pipeline, you must run the following two files in the order that they are listed below

To create tables:
python3 create_tables.py

To fill tables via ETL:
python3 etl.py


# The purpose of this database

Using a database makes it easier to analyze the data. 
By using SQL and the star schema, differents joins and aggregations, the data can be searched and summarized quickly and easily. 
Since the amount of data can become very large very quickly, it makes sense to use a distributive database. 

# The database schema design and ETL pipeline.

In order to enable Sparkify to analyze their data, a Relational Database Schema was created, which can be filled with an ETL pipeline.

The so-called star schema enables the company to view the user behaviour over several dimensions.
The fact table is used to store all user song activities that contain the category "NextSong". 
Using this table, the company can relate and analyze the dimensions users, songs, artists and time.

* **Fact Table**: songplays
* **Dimension Tables**: users, songs, artists and time.

# Dataset used

The data is queried from s3 buckets hosten at AWS

* **Song data**: s3://udacity-dend/song_data
* **Log data**: s3://udacity-dend/log_data