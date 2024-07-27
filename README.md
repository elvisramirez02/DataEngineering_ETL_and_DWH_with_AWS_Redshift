# 🎵 Data Analysis Project Overview

## Introduction

Hey there! 👋 Welcome to my project repository! I'm working with a startup called **Sparkify** to analyze the data they've been collecting on songs and user activity through their new music streaming app. The analytics team is especially keen on understanding what songs users are listening to, but they face a challenge—they don't have an easy way to query their data, which resides in JSON logs on user activity and metadata on the songs.

## How to Run the Python Scripts

To get this database up and running and to start processing the ETL pipeline, you'll need to run two scripts in the following order:

1. **Create Database Tables**
   ```bash
   python3 create_tables.py
   ```

2. **Run ETL Pipeline**
   ```bash
   python3 etl.py
   ```

## Purpose of This Database

📊 **Why use a database?** Using a database simplifies data analysis. By leveraging SQL and the star schema design, it allows for efficient queries through various joins and aggregations. This approach is critical as the volume of data can grow exponentially, making a distributive database essential for handling large datasets effectively.

## Database Schema Design and ETL Pipeline

To facilitate Sparkify's data analysis needs, I've designed a **Relational Database Schema** filled through an ETL pipeline. This schema is centered around a **star schema**, optimizing for queries on user behavior across multiple dimensions.

### Fact Table

- **songplays**: Records in log data associated with song plays (i.e., records where page is `NextSong`).
  - Columns: songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

### Dimension Tables

- **users**: Users in the app.
  - Columns: user_id, first_name, last_name, gender, level

- **songs**: Songs in the music database.
  - Columns: song_id, title, artist_id, year, duration

- **artists**: Artists in the music database.
  - Columns: artist_id, name, location, latitude, longitude

- **time**: Timestamps of records in songplays broken down into specific units.
  - Columns: start_time, hour, day, week, month, year, weekday

## Conclusion

This project showcases how data modeling and ETL processes can significantly enhance the ability to analyze complex datasets in a music streaming context. By creating a well-structured database and an effective ETL pipeline, Sparkify can now easily query their data to gain insights into user preferences and behaviors.
