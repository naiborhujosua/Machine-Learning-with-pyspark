# Machine-Learning-with-pyspark
## Distributed Computing  Techniques:
![Implementation of Machine Learning using pyspark](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/spark%20architecture.png)


The picture as shown above is the approach of spark. Spark is general purpose framework for cluster computing. Spark cluster consists of one or more nodes. Each node is a computer with CPU, RAM and physical storage. A cluster Manager is used to coordinate to allocate resources across clusters. Every application on spark has a driver. Driver communicates with Cluster Manager to coordinates tasks.

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
<br>

## Implementing Machine Learning Algorithm:
![ML Algorithms](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/sparkml.png)
We can implement Machine learning algorithm through these processes: 
---

1. Splitting the data
After cleaning the data, we will implment machine learning algorithm. In this course, we will use Decision Tree as our algorithm. One thing we should remember before implementing the algorithm is splitting our data into two parts namely training and test data. We will use this in order to avoid data leakage. 
We can use RandomSplit method which is provided by Spark. 
![Splitting the data](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/splitdata.png)

2. Implementing Decision Tree can use training data and test data using transform method
![Splitting the data](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/Dtimplementation.png)
![Splitting the data](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/testdata.png)


## Evaluate the Decision Tree 
![Evaluate Algorithm](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/confusionmatrix.png)
We can evaluate the Decision Tree using confusion matrix which consists of 4 elements such as 
1. True Negatives (TN) — model predicts negative outcome & known outcome is negative
2. True Positives (TP) — model predicts positive outcome & known outcome is positive
3. False Negatives (FN) — model predicts negative outcome but known outcome is positive
4. False Positives (FP) — model predicts positive outcome but known outcome is negative.

Based on the confusion matrix as shown above, we can quantify the accuracy through this formula:
![Accuracy](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/Accuracy.png)
<br><br>
Accuracy is generally not a very reliable metric because it can be biased by the most common target class. There are two other useful metrics:
<br>
1. **Precision** is the proportion of positive predictions which are correct. For all flights which are predicted to be delayed, what proportion is actually delayed?
2. **Recall** is the proportion of positives outcomes which are correctly predicted. For all delayed flights, what proportion is correctly predicted by the model?
![Precision and Recall](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/precisionrecall.png)


## Turning text into Tables 
Given a SMS document as shown below. We will train the sms to classify the sms into spam or not.<br>
![Dataframe](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/dataframe.png)
We will try to clean the data by manipulating and changing the unimportant parts of the data by implementing tokenizer,stopwords,hashing and IDF befroe implementing Machine Learning Algorithms.

## Cleaning the Data
![Cleaning the data](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/cleanthedata.png)
The picture above shows the implementation of regex and tokenizer to clean our data. We change the all the punctuation characters into a space and do the same thing  to the number. Then we will be implementing the tokenizer to change the the doc into a word. 

## Stop Words and hashing
![Stopwords and Hashing](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/idfhashing.png)
1. The hashing trick provides a fast and space-efficient way to map a very large (possibly infinite) set of items (in this case, all words contained in the SMS messages) onto a smaller, finite number of values.
2. The TF-IDF matrix reflects how important a word is to each document. It takes into account both the frequency of the word within each document but also the frequency of the word across all of the documents in the collection.
We will get the output shown below : <br>
![Hashing](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/hashingnum.png)

## Train the Spam Classifier
Before implementing LogisticRegression, we will split the data into train and test data. 
![Splitting the sms data](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/split%20data.png)
![Confusion matrix](https://github.com/naiborhujosua/Machine-Learning-with-pyspark/blob/main/confusionmatrixsms.png)

---
References
---
[Learning Spark 2nd Edition](https://www.oreilly.com/library/view/learning-spark-2nd/9781492050032/)<br>
[Spark  Python API Documentation](https://spark.apache.org/docs/latest/api/python/index.html)










