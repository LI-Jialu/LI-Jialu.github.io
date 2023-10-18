---
layout: post
title: From Centralized to Distributed Data Analytics MapReduce & Hadoop 
date: 2023-09-26 23:11:00 +/-5000
categories: [Data Analytics]
tags: [mapreduce, hadoop]     # TAG names should always be lowercase
---

# Motivations 
### Drawbacks of traditional centralized data analytics architecture
- Scale of data 
- IO bounded: biggest performance bottleneck is IO to disk,  reading from disk is 100+ times slowers than from main memory. 
### Prototype of distributed data analytics architecture
brief intro of distributed architecture: .... 

### Challenges of the prototype of distributed data analytics architecture
- node fail => duplicate data => Hadoop 
- network as bottleneck => bring computation to node, rather than data => MapReduce 
- traditional distributed programming is complicated => a programming system easy to distribute => MapReduce 

## Hadoop: Storage infrastructure 
- Data kept in **chunks** spread acroos machines 
- Chunk **duplicates** on different machines 
### Hadoop

### GFS: Google File System 

## MapReduce 
Divide and Conque => Map and Reduce 