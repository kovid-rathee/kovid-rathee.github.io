---
layout: page
title:  "How MapReduce Really Works?"
date:   2018-04-08 13:31:31 +0530
categories: science
permalink: /mapreduce/
---

How MapReduce really works?

Information is stored in HDFS - storage nodes
MapReduce processes the stored information - processing nodes

A query is distributed to all the HDFS servers. An HDFS server can also run
programs to process files saved on HDFS.

Load the data into HDFS

Map program - executes on each node
Reduce program - combines results of all Map programs to analyse the results

SMP vs MPP

Default HDFS Block Size - 128 MB

# of input splits = # of mappers

Hadoop can run MapReduce in the form of key-value pairs only

Word Count example

For every input split, there will be once RecordReader interface
Every line is a record. You have to convert it to key-value pairs
RecordReader knows how to read one line at a time
RecordReader is a predefined interface

Predefined Input Classes -

1) TextInputFormat
2) KeyValueTextInputFormat
3) SequenceFileInputFormat
4) SequenceFileTextInputFormat

byteoffset, record


[sql-fiddle]: http://www.sqlfiddle.com/#!9/9eecb/26319
