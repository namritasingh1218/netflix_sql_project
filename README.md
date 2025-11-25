# Netflix Movies and TV Shows Data Analysis using SQL

![Netflix Logo](https://github.com/namritasingh1218/netflix_sql_project/blob/main/logo.png)

## Overview
This project involves a comprehensive analysis of Netflix's movies and TV shows data using SQL. The goal is to extract valuable insights and answer various business questions based on the dataset. The following README provides a detailed account of the project's objectives, business problems, solutions, findings, and conclusions.

## Objectives
1. Analyze the distribution of content types (movies vs TV shows).
2. Identify the most common ratings for movies and TV shows.
3. List and analyze content based on release years, countries, and durations.
4. Explore and categorize content based on specific criteria and keywords.

## Dataset
The data for this project is sourced from the Kaggle dataset:

Dataset Link: https://www.kaggle.com/datasets/shivamb/netflix-shows?resource=download

## Schema
DROP TABLE IF EXISTS netflix_titles;


--Create Table of Netflix Data
CREATE TABLE dbo.netflix_titles (
    show_id        VARCHAR(20),
    type           VARCHAR(50),
    title          VARCHAR(500),
    director       VARCHAR(500),
    cast           VARCHAR(MAX),
    country        VARCHAR(200),
    date_added     VARCHAR(100),
    release_year   INT,
    rating         VARCHAR(20),
    duration       VARCHAR(50),
    listed_in      VARCHAR(500),
    description    VARCHAR(MAX)
);

## Large Data Set Imported Through BULK INSERT IN SQL Server
BULK INSERT dbo.netflix_titles
FROM 'C:\Users\Public\netflix_titles.csv'
WITH (
    FORMAT = 'CSV',
    FIRSTROW = 2,
    FIELDTERMINATOR = ',',
    ROWTERMINATOR = '\n',
    TABLOCK
);

## Business Problems and Solutions

1. Count the number of Movies vs TV Shows
SELECT 
     type,
     COUNT(*) as total_content
FROM netflix_titles
GROUP BY type ;
## Objective: Determine the distribution of content types on Netflix.





