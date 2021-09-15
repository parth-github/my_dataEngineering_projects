# my_dataEngineering_projects
my_dataEngineering_projects

E- Commerce Analytics

Objective: Use Spark features for data analysis to derive the valuable insights.

Problem Statement:
You are working as a Big Data consultant for an E-commerce company. Your role is to analyze sales data. The company has multiple stores across the globe. They want you to do the analytics of their sales transaction data. You need to provide valuable insights to understand their sales across cities, state on a daily and weekly basis. Also, provide various other insights regarding the review of the products.

Domain: E-Commerce 

Analysis to be done: Exploratory analysis, to determine actionable insights. 

Dataset File: olist_public_dataset.csv

![image](https://user-images.githubusercontent.com/8849821/133379039-28705d36-fa8f-4f0a-8629-85ac3d37907d.png)

#Tasks to perform:
Week 1: Approach Overview and Basic Configurations
1.	Install maven (3.6.2).
2.	Set environment variable of Maven
  a) Check if maven is setup properly using  “mvn -version” 
3.	Install Java 1.8 and Scala 2.11.7
4.	Use Intellij to validate or modify source code
5.	Click “mvn clean install” to build jar file
6.	Use README.md for details instructions and helper commands
A) Install Anaconda (miniconda3)
B) Install spark-scala-version-hadoop-version
C) Download and place winutils.exe in SPARK_HOME\hadoop
!set SPARK_HOME and HADOOP_HOME=%SPARK_HOME%\hadoop

OR
PATH=%PATH%,%SPARK_HOME%\bin
1.	Create and Change to workspace directory 'learningPyspark'
2.	Launch Anaconda prompt (miniconda)
3.	Create and activate a anaconda environment from conda prompt
!conda create -name learningPysparkPacktpub
!conda activate learningPysparkPacktpub
4.	Install jupyterlab and pyspark packages !conda install jupyterlab pyspark -y
5.	Launch Jupyter Lab !jupyter lab

Week 2: Data Ingestion
1.	Upload the entire data into Hive from CSV
a.	Create table in hive:
CREATE TABLE IF NOT EXISTS emp.employee (
 id int,
 name string,
 age int,
 gender string )
 COMMENT 'Employee Table'
 ROW FORMAT DELIMITED
 FIELDS TERMINATED BY ',';
b.	LOAD CSV File from the LOCAL filesystem: 
LOAD DATA [LOCAL] INPATH 'filepath' [OVERWRITE] 
INTO TABLE tablename [PARTITION (partcol1=val1, partcol2=val2 ...)] 
[INPUTFORMAT 'inputformat' SERDE 'serde']

i.	LOAD DATA LOCAL INPATH '/home/parth/data.csv or fileserver path' INTO TABLE emp.employee;
ii.	LOAD DATA LOCAL INPATH '/home/parth/data.csv' OVERWRITE INTO TABLE emp.employee PARTITION(date=2020);
2.	Copy the data from Hive into HDFS
a.	Hdfs dfs –cp arv /user/hive/warehouse/emp.employee /user/hive/data/
3.	Check the data in HDFS path
hdfs dfs -ls /user/hive/warehouse/emp.db/employee/
CREATE EXTERNAL TABLE mydata (key STRING, value INT)
    ROW FORMAT DELIMITED FIELDS TERMINATED BY ' '
    LOCATION 's3n://mysbucket/';
    
Week 3 : Data Streaming 
1.	Create sample Maven Scala Project
2.	Add necessary spark dependencies
3.	Create Schema of CSV files
4.	Create Spark Session
  a) Add S3 details
  b) Add all variables to your environment as they have sensitive data
5.	Read CSV file and convert into dataset
6.	Create Map of City and Country
7.	Convert Date to Hour, Month, Year, Daily, and Day Bucket using UDF
8.	Iterate through all metrics for each column
9.	For each type of segment, calculate stats of different cities. Stats include max, min, average, and total records

Week 3 : Data Streaming
1.	Add necessary spark dependencies
2.	Create Schema of the CSV files
3.	Create Spark session
         a) Add Object Storage Service details as per the Cloud provider
         b) Add all variables to your environment as they contain sensitive data
     4.    Read CSV files and convert them into dataset
     5.   Convert “order_purchase_timestamp” to week and day using UDF
     6.   Calculate Total Sales and Order distribution for day and week for each city
     7.   Calculate Total Sales and Order distribution for day and week for each state
     8.   Calculate Average Review score, Average Freight Value, Average order approval, and deliver time
     9.   Calculate the freight charges per city and total freight charges

Week 4 : Data Analysis and Visualization
1.	Write the results into the HDFS
2.	Save final dataset into Amazon S3
3.	Create Amazon Document DB Cluster
4.	Save insights in Document DB and provide APIs to view aggregate data
