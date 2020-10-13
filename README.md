# Machine-Learning-with-pyspark
## Distributed Computing  Techniques:
![Implementation of Machine Learning using pyspark](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/spark%20architecture.png)

The picture as shown above is the aproach of spark. Spark is general purpose framework for cluster computing. Spark cluster consists of one or more nodes. Each node is a computer with CPU, RAM and physical storage. A cluster Manager is used to coordinate to allocate resources across clusters. Every application on spark has a driver. Driver communicates with Cluster Manager to coordinates tasks.

<br><br>
Connecting to Spark
---
![Connecting to Spark](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/sparkSession.png)
1. We can connect to spark by creating a SparkSession which provided by Spark API. 
The SparkSession class has a builder attribute, which is an instance of the Builder class. The Builder class exposes three important methods that let you specify the location of the master node name the application (optional) and retrieve an existing SparkSession or, if there is none, create a new one.
The SparkSession class has a version attribute which gives the version of Spark. It is a good practice to stop the session while we have done process our data in Spark by using stop method as shown in the picture. 
---
<br><br>
