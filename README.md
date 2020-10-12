# Machine-Learning-with-pyspark
## Distributed Computing  Techniques:
![Implementation of Machine Learning using pyspark](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/spark%20architecture.png)

Generally, More Data is a good thing to generalize a new data. When data fits into the memory, it could be very good in analyzing it but it willl be a problem when the data no longer fits into the memory. That is why we use virtual memory. Distributed Computing across cluster is the answer to solve the big dataset in many machine which is divided into partition and fits into RAM in single computer in a cluster. This is the aproach of spark. Spark is general purpose framework for cluster computing. Spark cluster consists of one or more nodes. Each node is a computer with CPU, RAM and physical storage. A cluster Manager is used to coordinate to allocate resources across clusters. Every application on spark has a driver. Driver communicates with Cluster Manager to coordinates tasks.

