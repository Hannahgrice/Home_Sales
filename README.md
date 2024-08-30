# Home_Sales Project 
Issue
Spark stopped running after a second attempt to set it up. Here’s the initial code that worked:

python
Copy code
import os

spark_version = 'spark-3.5.2'
os.environ['SPARK_VERSION'] = spark_version

!wget -q http://www.apache.org/dist/spark/$SPARK_VERSION/$SPARK_VERSION-bin-hadoop3.tgz
!tar xf $SPARK_VERSION-bin-hadoop3.tgz

os.environ["JAVA_HOME"] = "/usr/lib/jvm/java-11-openjdk-amd64"
os.environ["SPARK_HOME"] = f"/content/{spark_version}-bin-hadoop3"

import findspark
findspark.init()

from pyspark.sql import SparkSession
spark = SparkSession.builder.appName("SparkSession").getOrCreate()
Instructions
Create Repository: Name it Home_Sales and clone it.
Files: Download from Module 22 Challenge files.
Rename: Home_Sales_starter_code.ipynb to Home_Sales.ipynb.
Data Analysis:
Import PySpark functions.
Load home_sales_revised.csv.
Create temporary table home_sales.
Queries: Run SQL queries for average home prices and measure performance.
Caching: Cache home_sales, compare runtimes.
Partitioning: Partition by "date_built", create a temporary table, and compare runtimes.
Uncaching: Uncache and verify.
