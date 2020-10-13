# Machine-Learning-with-pyspark
## Distributed Computing  Techniques:
![Implementation of Machine Learning using pyspark](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/spark%20architecture.png)

The picture as shown above is the aproach of spark. Spark is general purpose framework for cluster computing. Spark cluster consists of one or more nodes. Each node is a computer with CPU, RAM and physical storage. A cluster Manager is used to coordinate to allocate resources across clusters. Every application on spark has a driver. Driver communicates with Cluster Manager to coordinates tasks.

<br><br>
 # Connecting to Spark
---
![Connecting to Spark](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/sparkSession.png)
1. We can connect to spark by creating a SparkSession which provided by Spark API. 
The SparkSession class has a builder attribute, which is an instance of the Builder class. The Builder class exposes three important methods that let you specify the location of the master node name the application (optional) and retrieve an existing SparkSession or, if there is none, create a new one.
The SparkSession class has a version attribute which gives the version of Spark. It is a good practice to stop the session while we have done process our data in Spark by using stop method as shown in the picture. 
---
<br><br>
# Loading the Data
---
![Reading the data from csv](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/loadthedata.png)
1. We can load the data that is formed in the dataframe using read.csv method which is provided by SparkSession. There are few methods that are extremely useful such as count() which is used to count how many records in a dataframe ,show() used the dataframe records, and printSchema() to print the schema of our data. We can also use dtypes attribute like in pandas to know the column type.
---
<br><br>
Data Preparation
---
Data Preparation is essential to do before implementing Machine Learning algorithm. A good quality of data can influence the performance of our result. In Spark, we could prepare the data by cleaning few factors such as removing the null values, changing datatype of a column. 

![Clean the data](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/removedata.jpeg)
<br>
We will be building model by physical characteristics so that we will remove the maker and model columns. We can use drop method  to remove the columns as shown  below:
![Remove the columns](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/dropcolumns.png)

Filtering out Missing Values
--
Filtering out Missing values is part of data preparation in order to filter the null values. we can use filter method and remove the missing values using dropna method. 
![Filter out missing values](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/filtermissingvalues.png)

Mutating the columns
--
We can mutate the columns using withColumn method . 
![Mutating the columns](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/mutatingcolumns.png)

Indexing categorical data
--
We can index the categorical data using StringIndexer method  to change the string into the numeric columns. 
![Indexing categorical data](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/changingcategoricalcolumn.png)

Transforming the data using vector assembler
--
![Transforming the data](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/assembling.png)






