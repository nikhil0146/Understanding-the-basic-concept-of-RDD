# Understanding-the-basic-concept-of-RDD

# What is Apache Spark?

Spark is a big data solution that has been proven to be easier and faster than Hadoop MapReduce. MapReduce were favorite but were slow. To overcome this issue, Spark offers a solution that is both fast and general-purpose. The main difference between Spark and MapReduce is that Spark runs computations in memory during the later on the hard disk. It allows high-speed access and data processing, reducing times from hours to minutes.

# What is PySpark?

PySpark is a tool created by Apache Spark Community for using Python with Spark. It allows working with RDD (Resilient Distributed Dataset) in Python. It also offers PySpark Shell to link Python APIs with Spark core to initiate Spark Context. Spark is the name engine to realize cluster computing, while PySpark is Python’s library to use Spark.

# How Does Spark work?

Spark is based on computational engine, meaning it takes care of the scheduling, distributing and monitoring application. Each task is done across various worker machines called computing cluster. A computing cluster refers to the division of tasks. One machine performs one task, while the others contribute to the final output through a different task. In the end, all the tasks are aggregated to produce an output. The Spark admin gives a 360 overview of various Spark Jobs.
A significant feature of Spark is the vast amount of built-in library, including MLlib for machine learning. Spark is also designed to work with Hadoop clusters and can read the broad type of files, including Hive data, CSV, JSON, Casandra data among other.

# Why use Spark?

One of the main advantages of Spark is to build an architecture that encompasses data streaming management, seamlessly data queries, machine learning prediction and real-time access to various analysis.

Spark works closely with SQL language, i.e., structured data. It allows querying the data in real time.


Spark Context:
SparkContext is the internal engine that allows the connections with the clusters. If you want to run an operation, you need a SparkContext.

# Resilient Distributed Datasets (RDDs):

Spark revolves around the concept of a resilient distributed dataset (RDD), which is a fault-tolerant collection of elements that can be operated on in parallel. There are two ways to create RDDs: parallelizing an existing collection in your driver program, or referencing a dataset in an external storage system, such as a shared filesystem, HDFS, HBase, or any data source offering a Hadoop InputFormat.

# Parallelized Collections:

Parallelized collections are created by calling SparkContext’s parallelize method on an existing iterable or collection in your driver program. The elements of the collection are copied to form a distributed dataset that can be operated on in parallel. For example, here is how to create a parallelized collection holding the numbers 1 to 5:

data = [1, 2, 3, 4, 5]
distData = sc.parallelize(data)

Once created, the distributed dataset (distData) can be operated on in parallel. For example, we can call distData.reduce(lambda a, b: a + b) to add up the elements of the list. We describe operations on distributed datasets later on.

One important parameter for parallel collections is the number of partitions to cut the dataset into. Spark will run one task for each partition of the cluster. Typically you want 2-4 partitions for each CPU in your cluster. Normally, Spark tries to set the number of partitions automatically based on your cluster. However, you can also set it manually by passing it as a second parameter to parallelize (e.g. sc.parallelize(data, 10)). Note: some places in the code use the term slices (a synonym for partitions) to maintain backward compatibility.












