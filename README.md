# Real-time-data-streaming-pipeline-using-Kafka-AWS-S3-Glue-and-Athena

## Overview

This project demonstrates the implementation of a real-time data streaming pipeline for stock market data using Apache Kafka, AWS S3, AWS Glue, and Athena. 

## Prerequisites

An AWS EC2 instance for hosting Kafka server.

Python installed on the local machine.

AWS account with permissions for S3, Glue, and Athena.

## Setup Instructions

### Kafka Server Setup

Download and extract Kafka:

wget https://dlcdn.apache.org/kafka/3.6.1/kafka_2.13-3.6.1.tgz

tar -xvf kafka_2.13-3.6.1.tgz

cd kafka_2.13-3.6.1.tgz

### Install Java

java -version

sudo yum install java-1.8.0-openjdk

java -version

### Start Zookeeper (in one terminal):

bin/zookeeper-server-start.sh config/zookeeper.properties

### Start Kafka Server (in another terminal):

export KAFKA_HEAP_OPTS="-Xmx256M -Xms128M"

cd kafka_2.13-3.6.1

bin/kafka-server-start.sh config/server.properties

### Kafka Topic and Producers

#### Create a Kafka topic:

cd kafka_2.13-3.6.1

bin/kafka-topics.sh --create --topic demo_testing2 --bootstrap-server {Put the Public IP of your EC2 Instance:9092} --replication-factor 1 --partitions 1

#### Implement Kafka Producer (Python):

#Code for Kafka Producer

#### Implement Kafka Consumer (Python):

#Code for Kafka Consumer

### AWS Glue Crawler and Athena

#### Set up AWS Glue Crawler:

Go to AWS Glue Console.

Click on "Crawlers" and then "Add crawler."

Complete IAM role setup and other configurations.

Click "Run crawler" to start the crawling process.

#### Verify Athena Table:

Go to Athena on the AWS console.

Query the discovered table under the 'stock market Kafka' database.
