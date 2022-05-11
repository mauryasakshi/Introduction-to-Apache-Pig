# Introduction to Apache Pig
This article is focused on Introduction to Apache Pig and how pig programming can be used to perform data analysis on Big Data. This article contains the programming that were actually performed to obtain the result.

## Introduction

In recent years, most of the data scientist have encountered the term Big Data. This data contains a massive amount of information that can be further used to generate knowledge, profit, decision making processes and many more. As data growth is exponential, analyzing them with the traditional methods are really difficult. In order to overcome this issue; we need Big data tools like Hadoop, Cassandra, CouchDB etc. 

In the Hadoop ecosystem, we have map reduce jobs to do the data processing but these are very complex codes written in Java. In order to reduce this complexity Apache Pig provides a high-level language called Pig Latin.

In most of the sources on Pig Latin, you can only find either definition or data manipulation in very complex technical terms and with least application. Due to this complexity, students face issues understanding and implementing Pig for analysis purposes. So here, I will explain Apache Pig script programming and usage in simpler terms using Amazon Product Reviews Dataset.

## What is Apache Pig ?

Apache Pig is termed as abstraction over map-reduce which basically means writing code as per requirement rather than thinking of what is happening in the background.

### Example : If we want to find maximum value from a column, so just need to focus on obtaining maximum value rather than thinking of what happens in backend.

Apache Pig is an open-source technology that reduces the complexity of writing a Map-Reduce program. They are used to analyze large amounts of data and help build ETL (Extract, Transform, Load ) Pipelines. Pig Latin, which is similar to SQL( Sequel Query Language), is used to write pig scripts and it is also know as Data flow Language. Using Pig, we can read a file from HDFS (Hadoop Distributed File System), manipulate those files, and store those results back to HDFS.

## What is Map Reduce ?

Map-reduce is a data processing technique and a programming model for the purpose of distributed computing. It mainly consist of two significant task, Map and Reduce.

Map breakdown the data into key value pair. Reduce takes the input from map and reduces them to more smaller tuples, processes it and stores the result back into Hadoop.

## Importance of Apache Pig

The advantages of writing pig scripts are that it requires less scripting than writing map-reduce, and it is a very high-level data flow tool. Pig is faster than any other data manipulation language such as Hive.

In Hadoop, the environment query is executed in the sequence of Map-Reduce jobs. Still, writing Map Reduce scripts often require Java programming language, which is difficult for a non-Java programmer. So to tackle this complexity, a Pig script is written, and internally, within the system gets converted into Map Reduce jobs.
Pig has an iterative nature and uses Multi Query Approach to reduce the length of the code. It can handle structured, semi-structured, and unstructured data. Pig facilitates a user by giving the advantage of creating User Defined Functions for a particular purpose of processing. 10 lines of Apache Pig code is equivalent to 200 lines of map-reduce code.  Pig Latin is very easy to learn and implement.

## Terminologies used in this article

Let's get familiar with some terminologies used in this article :

    HDFS : Hadoop Distributed File System is a data storage system for large amount of data
    Grunt: We can run our Pig Latin script in grunt shell
    Load: Loading the file in pig variable
    Dump: Dump is used to execute Pig Latin statements and print outcome on the console
    Group: To group the data around an attribute/column's
    Foreach: To access each element individually

We have used Amazon Product Reviews Dataset from data. world and analyzed it using pig.

Link to the data set: https://data.world/datafiniti/consumer-reviews-of-amazon-products

## Pig Scripting

Pig Latin contains different kinds of operators such as Arithmetic, Comparison, Relational Operators, and many more. It also supports filter, group, joins, and sorting functions. Pig Latin programming is similar to SQL programming and, to some extent, formal programming syntax ( example: foreach ).

Pig scripts are written in grunt shell and executed using the Dump command. To perform Pig operations, we need to set up Hadoop and later Apache Pig on the Linux environment. Installation can be performed using the link below :

https://pig.apache.org/docs/r0.16.0/start.html#Pig+Setup

Or another option is installation through a virtual box on the windows environment.

First thing we did here is, we loaded the AmazonProductReviews.csv file. Below you can successfully file has been loaded in HDFS.

Now we opened the Pig console. In the pig console you would be able to see the Grunt shell.

### 1. Loading the dataset in Pig

In order to load our dataset in Apache Pig, first we will create a Pig Variable named "Amazon_Review" .

Here id, name, brand, primaryCategories, manufacturerNumber etc. are the features/attributes of the dataset.

### 2. Check top 5 observations of the data

After successfully loading the dataset into Apache Pig, we will check the top 5 observations.

Note : Here 6 is written because 1st row is the row of attributes/features.

<i><b> Output</b></i> :


Hurray ! first step to load and check the data has been successfully completed. Now let's try some very basic analysis over the data.

### 3. Find the number of sales in each category

Here we need to find sales in each category. In our dataset we have primary Categories.

Grouping the Amazon_Review by 'primaryCategories'

 Here we have counted number of observations as number of sales in each category.

Applying foreach to count sales in each category

<i><b> Output </b></i> :

Here we observe that Electronics and Health & Beauty has highest sales in our dataset.

 ### 4. Average rating of each product category

Next task is to find average rating in each product category. The rating scale is between 1 to 5.

Here we have used AVG. It is an aggregate function in Pig Latin.

<i><b> Output </b></i>

## EndNotes

This article explains the importance of Apache Pig, how to load data into pig variable and perform some basic analysis using Pig Latin scripts. Working with Big Data is a tedious task but I hope this article will give a push towards programming in Pig and perform analysis over the huge data.
