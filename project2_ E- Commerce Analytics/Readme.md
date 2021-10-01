
E- Commerce Analytics

Objective: Use Spark features for data analysis to derive the valuable insights.

Problem Statement: You are working as a Big Data consultant for an E-commerce company. Your role is to analyze sales data. The company has multiple stores across the globe. They want you to do the analytics of their sales transaction data. You need to provide valuable insights to understand their sales across cities, state on a daily and weekly basis. Also, provide various other insights regarding the review of the products.

Domain: E-Commerce

Analysis to be done: Exploratory analysis, to determine actionable insights.

Dataset File: olist_public_dataset.csv

![image](https://user-images.githubusercontent.com/8849821/135619748-928f8e90-0f98-4ad7-a8b0-0db3ceb1acc1.png)


#Tasks to perform: Week 1: Approach Overview and Basic Configurations

Install maven (3.6.2).
Set environment variable of Maven a) Check if maven is setup properly using “mvn -version”
Install Java 1.8 and Scala 2.11.7
Use Intellij to validate or modify source code
Click “mvn clean install” to build jar file
Use README.md for details instructions and helper commands A) Install Anaconda (miniconda3) B) Install spark-scala-version-hadoop-version C) Download and place winutils.exe in SPARK_HOME\hadoop !set SPARK_HOME and HADOOP_HOME=%SPARK_HOME%\hadoop
OR PATH=%PATH%,%SPARK_HOME%\bin

Create and Change to workspace directory 'learningPyspark'
Launch Anaconda prompt (miniconda)
Create and activate a anaconda environment from conda prompt !conda create -name learningPysparkPacktpub !conda activate learningPysparkPacktpub
Install jupyterlab and pyspark packages !conda install jupyterlab pyspark -y
Launch Jupyter Lab !jupyter lab
Week 2: Data Ingestion

Upload the entire data into Hive from CSV a. Create table in hive: CREATE TABLE IF NOT EXISTS emp.employee ( id int, name string, age int, gender string ) COMMENT 'Employee Table' ROW FORMAT DELIMITED FIELDS TERMINATED BY ','; b. LOAD CSV File from the LOCAL filesystem: LOAD DATA [LOCAL] INPATH 'filepath' [OVERWRITE] INTO TABLE tablename [PARTITION (partcol1=val1, partcol2=val2 ...)] [INPUTFORMAT 'inputformat' SERDE 'serde']
i. LOAD DATA LOCAL INPATH '/home/parth/data.csv or fileserver path' INTO TABLE emp.employee; ii. LOAD DATA LOCAL INPATH '/home/parth/data.csv' OVERWRITE INTO TABLE emp.employee PARTITION(date=2020); 2. Copy the data from Hive into HDFS a. Hdfs dfs –cp arv /user/hive/warehouse/emp.employee /user/hive/data/ 3. Check the data in HDFS path hdfs dfs -ls /user/hive/warehouse/emp.db/employee/ CREATE EXTERNAL TABLE mydata (key STRING, value INT) ROW FORMAT DELIMITED FIELDS TERMINATED BY ' ' LOCATION 's3n://mysbucket/';

Week 3 : Data Streaming

Create sample Maven Scala Project
Add necessary spark dependencies
Create Schema of CSV files
Create Spark Session a) Add S3 details b) Add all variables to your environment as they have sensitive data
Read CSV file and convert into dataset
Create Map of City and Country
Convert Date to Hour, Month, Year, Daily, and Day Bucket using UDF
Iterate through all metrics for each column
For each type of segment, calculate stats of different cities. Stats include max, min, average, and total records
Week 3 : Data Streaming 1. Add necessary spark dependencies 2. Create Schema of the CSV files 3. Create Spark session a) Add Object Storage Service details as per the Cloud provider b) Add all variables to your environment as they contain sensitive data 4. Read CSV files and convert them into dataset 5. Convert “order_purchase_timestamp” to week and day using UDF 6. Calculate Total Sales and Order distribution for day and week for each city 7. Calculate Total Sales and Order distribution for day and week for each state 8. Calculate Average Review score, Average Freight Value, Average order approval, and deliver time 9. Calculate the freight charges per city and total freight charges

Week 4 : Data Analysis and Visualization

Write the results into the HDFS
Save final dataset into Amazon S3
Create Amazon Document DB Cluster
Save insights in Document DB and provide APIs to view aggregate data
