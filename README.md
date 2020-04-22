Project: Data Modeling with Postgres
Introduction
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

I will be creating a Postgres database with tables designed to optimize queries on song play analysis, considering the database schema and ETL pipeline. 

Project Description
I'll do data modeling with Postgres and build an ETL pipeline using Python. The fact and dimension tables for a star schema and ETL pipeline that transfers data from files in two local directories into these tables in Postgres is created using Python and SQL accordingly.

Schema for Song Play Analysis
Using the song and log datasets, a star schema optimized for queries on song play analysis has been designed. This includes the following tables.

Fact Table
songplays - records in log data associated with song plays i.e. records with page NextSong
songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

Dimension Tables
users - users in the app
user_id, first_name, last_name, gender, level

songs - songs in music database
song_id, title, artist_id, year, duration

artists - artists in music database
artist_id, name, location, latitude, longitude

time - timestamps of records in songplays broken down into specific units
start_time, hour, day, week, month, year, weekday

Justification of the data types for the datatypes:
The decision to choose "text" over "varchar(n)" and "varchar" is because "varchar(n)" faces some challenges to change the length of "n" in a production. Similarly, "text" and "varchar" works the same but "text" is choosen for clearer readibility.
Source: https://stackoverflow.com/questions/4848964/postgresql-difference-between-text-and-varchar-character-varying




