---
layout: page
title:  "Shorts: Big Data"
date:   2018-04-08 13:31:31 +0530
categories: big data, hadoop, hive, scala, java, mapreduce, data science, data
permalink: /shorts-big-data/
---

#### Big Data
##### is used to define data which is often unstructured and very large in size; also which cannot be processed via traditional data processing mechanisms like relational databases. photos, videos, raw text accounts for such data.

#### MapReduce
##### is an algorithm which takes the input data set and splits it into small chunks which are processed by several mappers parallely. output from the mappers are sorted individually and are sent to the reducers. the reducer combines all the chunks into a single file and presents the output. the idea is to store and process a large set of data on separate nodes (machines) and process them parallely.

#### Hadoop
##### is the most famous, widely used implementation of the MapReduce algorithm. An analogy would be Google using PageRank algorithm for their search engine. MapReduce was also written at Google, it was open-sourced. PageRank has not been open-sourced.

#### HDFS
##### is hadoop distributed file system. a file system is the collection of methods and data structures that an operating system uses to keep track on a disk. essentially, how data is organized on disk. hadoop framework has it's own filesystem which is installed on the systems where hadoop data is stored, called data nodes in the hadoop cluster. the difference between a normal file system and this one is that a normal file system has small block size (in kilobytes), the deault in hadoop distributed file system is 128 megabytes. it's meant for storing large files easily. large files are accessed easily when the opearting system has to do less work (read less blocks) while accessing a file.

#### NoSQL
##### read not only sequel. unstructured data cannot be efficiently processed with SQL all the time, which is why there are new technologies and frameworks which solve for data processing for specific data formats. Unlike relational databases, NoSQL databases are usually schema-less. They are schema-less because they lack a rigid structure. data in NoSQL databases is usually stored in key-value pairs. examples of such databases are MongoDB and Cassandra.

#### Hive
##### this is a data management platform over hadoop. while hadoop processes the data, we need hive to manage and query the data using HQL or hive query language.
