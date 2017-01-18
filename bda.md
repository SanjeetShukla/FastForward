## 1. Big Data Fundamentals
In its raw form , Oil has little value
Once processed and refined it helps power the world.


Volume
Variety
Velocity
Veracity: conformity to facts; accuracy.


Big Data is a platform
Datawarehouse: OLAP

### Five High value Big Data use cases
1. Hive: 
2. Impala (Cloudera)
3. Big SQL (IBM) Hive, Hbase, csv files
4. Stinger (Hortanworks)
5. Drill (Map R)
6. HAWQ (Pivotal)
7. SQL-H (TeraData)

## 2. Hadoop Fundamentals
### 1. What is Hadoop? 
Open source project of the Apache Foundation, Originally written by Doug Cutting.
It can handle massive quantity of data parallely using commodity hardware. It is reliable through replication. current version is 2.7.3.
### 2. What is Big Data?
Large collection of unstructured data that grows rapidly. It can be RFID data, tweet data, cellphone suers data, machine logs, 80 % of data is unstructured.
### 3.Other open source projects related to Hadoop
Eclipse IDE by IBM 
Lucene Text search engine library written in Java
HBase Hadoop Database
Hive Datawarehousing tool to ETL and Query data stored in hadoop files
PIG High level language that generates map reduce code to analyze large dataset
JAQL Query language for json 
Zookeeper Centralized configuration service and naming registry for large distributed system.
AVRO Data serialization system
UIMA Arcitecture for development discovery composition and deployment for the analysis of unstructured data.


### Hadoop is not good for. 
1. Not good for Processing transtions.
2. Not good when can not be parallelized.
3. Not good for low  latency data access.
4. Not good for processing lots of samll files. (IBM ADAPTIVE MAP REDUCE)
5. Not good for intensive calculation on little data.

### Big Data solutions are more than just Hadoop.

## Hadoop Architecture
Node:-A computer, a non enterprise commodity type hardware used for node that contain data.
Rack:- is collection of multiple nodes connected to same network switch.
Network bandwidth:- bandwith between nodes in a rack > bandwidth between nodes on different rack
Cluster:- collection of rack.
Replication:-
Rack awareness (Network topology)

Two major components of Hadoop are 
DFS Distributed File system.
  HDFS
  GPFS-FPO
Map Reduce Engine.
  Framework for performing calculations on data in the file system
  Has a built in resource manager and scheduler.
  
### HDFS Hadoop distributed file sysetm.
Runs on top of existing file system.
It is not posix comliant
Designed to tolerate high component failure rate.
Reliability through replication

Designed to handle very large files
Large streaming data access patterns
No random access.
Hadoop uses blocks to store files.
One hadoop block may have many blocks on underlying file system.
Blocks work well with replication.


### Map Reduce Framework
Based on Google technology
Processes huge datasets for certain kind of distributed problems using a large number of nodes.
Map and reduce functions are components of mapreduce program, they run in parallel.


Name Node:-One name node per cluster, Meta data is stored here, Data is not here, data does not goes through here, It should be best hardware with most RAM as it keeps entire metadata in memory
Data Node:-Stored blocks of data., Client gets information from Name node about which data node stores that data. Commodity hardware. Replication is provided at software level.

Name node is single point of failure
Journal node decides which name node be active one.

Task Tracker:-Many task trackers for parallelism, each has jvm to run MapReduce task, communicates to job tracker and reads blocks from the data nodes.

job Tracker:-Mananges map reduce v1 jobs, Only 1 on cluster, Receives job request submitted by client. Schedules and monitors MapReduce jobs on appropriate task trackers.

Client

### POSIX Compliance.
The Portable Operating System Interface (POSIX)[1] is a family of standards specified by the IEEE Computer Society for maintaining compatibility between operating systems. POSIX defines the application programming interface (API), along with command line shells and utility interfaces, for software compatibility with variants of Unix and other operating systems



Using Command line:-
$BIGINSIGHT_HOME/bin/start-all.sh
hadoop fs -ls
hadoop fs -ls /user/biadmin
hadoop fs -mkdir /user/biadmin/test
hadoop fs -ls user/biadmin

cat > myfile.txt
this is some data in my file

hadoop fs -put ~/myfile.txt test/myfile.txt
haddop fls -ls test

hadoop fs -ls /user/biadmin | grep test
hadoop fs -du /user/biadmin/test/myfile.txt
hadoop fs -du /user/biadmin

hadoop fs -du -s /user/biadmin

1. Hue and Ambari are some good opensource tools for Hadoop administration, in addition to IBM biginsight.
2. Hadoop also has a builtin task tracker page.

%BIGINSIGHTS_HOME/bin/stop-all.sh

Hadoop 2.2 Architecture
YARN:- YET ANOTHER RESOURCE NETWORK

Node manager on each node


