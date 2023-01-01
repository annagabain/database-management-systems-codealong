To run a backend Python file, type `python3 app.py`, if your Python file is named `app.py` of course.

A blue button should appear to click: _Make Public_,

Another blue button should appear to click: _Open Browser_.

In Gitpod you have superuser security privileges by default. Therefore you do not need to use the `sudo` (superuser do) command in the bash terminal in any of the lessons.

----------

## 01 - Installing the Chinook Database
Download the Chinook PostgreSql database
source
wget https://raw.githubusercontent.com/lerocha/chinook-database/master/ChinookDatabase/DataSources/Chinook_PostgreSql.sql

Access the Postgres CLI
psql

Create the new "chinook" database
CREATE DATABASE chinook;

View existing tables on the database
\l

Switch between databases
\c postgres (switch to the database called "postgres")
\c chinook (switch to the database called "chinook")

#### Install / Initialize the downloaded Chinook SQL database
\i Chinook_PostgreSql.sql (takes several minutes)

---------

If you get the following error after typing psql in the terminal:

psql: error: could not connect to server: No such file or directory

Please use the following command in the terminal to set an environment variable needed for it to work:

set_pg

And then try the psql command again

----------

## 02 - PostgreSQL from the Command Line
Quit the entire Postgres CLI
\q
Connect to the "chinook" Postgres CLI database
psql -d chinook
Display all tables on the "chinook" database
\dt
Quit the query / return back to CLI after a query
q
Retrieve all data from the "Artist" table
SELECT * FROM "Artist";
Retrieve only the "Name" column from the "Artist" table
SELECT "Name" FROM "Artist";
Retrieve only "Queen" from the "Artist" table
SELECT * FROM "Artist" WHERE "Name" = 'Queen';
Retrieve only "Queen" from the "Artist" table, but using the "ArtistId" of '51'
SELECT * FROM "Artist" WHERE "ArtistId" = 51;
Retrieve all albums from the "Album" table, using the "ArtistId" of '51'
SELECT * FROM "Album" WHERE "ArtistId" = 51;
Retrieve all tracks from the "Track" table, using the "Composer" of 'Queen'
SELECT * FROM "Track" WHERE "Composer" = 'Queen';


--------

## 03 - Installing the Libraries and Setting Up
Install the "psycopg2" Python package
pip3 install psycopg2
Create a new file: "sql-psycopg2.py"
touch sql-psycopg2.py

