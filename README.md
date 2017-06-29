(Please note,.... This documen I have developed only for my reference and learning purpose.... 
most of the content is not my own  and I have refered itversity.com, coursera.org, edx.org, simplilearn.com and many other youtube videos)

# Apache-Spark 2.0
1. About Spark:

Spark is a distributed programming model where the user specifies transformations, which build up a directed-acyclic-graph of instructions, and actions, which begin the process of executing that graph of instructions, as a single job, by breaking it down into stages and tasks to execute across the cluster. 
The way we store data on which to perform transformations and actions are DataFrames and Datasets


2. Environment Setup
    Intellij Environment Setup
    Eclipse Environemnt Setup
3. SparkContext and SparkConf
4. Programming




3. SparkContext and SparkConf:

SparkConf – Configuration information of the application
SparkContext – Tells Spark how to access the cluster (YARN or Mesos or local) Application parameters and configurations

SparkConf

Let us see details about SparkConf and how it is used while submitting spark applications.

As part of Cluster setup we will have a directory which in turn have files such as spark-env.sh and spark-defaults.conf.
spark-env.sh and spark-defaults.conf will be accessible using SparkConf
As part of application development first we need to create SparkConf object
There are several set and get methods to override parameter values or environment variables
setAppName can be used to give readable name to the application to get the logs
setMaster can be used to run the application in YARN mode or local mode or mesos mode
setExecutorEnv can be used to override environment variable of executor (such as memory)
set is generic method to override any configuration parameter

How to create Sparkconf:

val conf = new SparkConf().setAppName("generate wc report").setMaster("Local")

SparkContext

SparkContext tells how application should be run (based on default or SparkConf setMaster)
Following are different contexts in which spark applications can run
local
yarn-client
mesos URL
spark URL
Once SparkContext object is created we can invoke functions such as
textFile – to read text files from local, s3, HDFS etc
sequenceFile – to read Hadoop’s sequence file
parallelize – to parallelize collection 
and many more




