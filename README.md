# MovieLens 100k Dataset Analysis using Cassandra and Spark
A repository for Project 3 Data Management - utilising Cassandra Query Language and SQL

## Introduction
This project analyzes the MovieLens 100K Dataset using **Cassandra** and **Spark**. The dataset, collected by the GroupLens Research Project at the University of Minnesota, consists of 100,000 ratings from 943 users on 1,682 movies. The analysis uses both Cassandra Query Language (CQL) and Spark2 Structured Query Language (SQL) to answer key questions about user demographics and movie ratings.

***

## Project Goals

The analysis in this project is focused on answering the following questions:

1.  **Calculate the average rating for each movie.**
2.  **Identify the top ten movies with the highest average ratings.**
3.  **Find users who have rated at least 50 movies and identify their favorite movie genres.**
4.  **Find all users who are less than 20 years old.**
5.  **Find all users whose occupation is "scientist" and whose age is between 30 and 40 years old.**

***

## Prerequisites

To run this project, you'll need the **Docker** installed. The project uses a containerized environment with a custom Docker network to connect Apache Zeppelin and Apache Cassandra. The setup is included in the *json* file.

***

## Technologies Used

* **Docker**: Containerization platform.
* **Apache Spark2**: Distributed data processing engine.
* **Apache Cassandra**: NoSQL database for scalable data storage.
* **Apache Zeppelin**: A web-based notebook for interactive data analytics.
* **Python**: The programming language for the wrapper script.

***

## Instructions

### 1. Download the Dataset

First, you need to download the MovieLens 100K Dataset from the official GroupLens website: [https://grouplens.org/datasets/movielens/](https://grouplens.org/datasets/movielens/)

### 2. Prepare the Environment

Make sure you have Docker installed and running. This project uses a Docker-based setup for Zeppelin and Cassandra.

### 3. Run the Python Script

The core of this project is a Python script that acts as a wrapper. It orchestrates the entire data flow and analysis process.

The script performs the following tasks:

1.  **Library Import**: Imports necessary Python libraries for Spark and Cassandra sessions.
2.  **Data Parsing**: Parses the `u.user`, `u.item` and `u.data` files.
3.  **RDD and DataFrame Creation**: Creates RDD objects from the data and converts them into Spark DataFrames.
4.  **Cassandra Integration**: Writes the DataFrames into a new keyspace table in Cassandra.
5.  **Query Execution**: Reads the data back from Cassandra into a new DataFrame and executes Spark2 SQL and CQL queries to answer the project goals.
6.  **Output**: Displays the top ten results for each question.
