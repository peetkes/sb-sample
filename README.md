# SB-Sample
Marklogic Spring Batch Sample Project

This project is based on the sample described by Scott Stafford in the [Getting Started](https://github.com/marklogic-community/marklogic-spring-batch/wiki/Getting-Started) guide of [MarkLogic Spring Batch](https://github.com/marklogic-community/marklogic-spring-batch) and shows how to make use of Spring Batch to add content to MarkLogic.

Find all info about MLSB here: https://github.com/marklogic-community/marklogic-spring-batch/wiki

## Prerequisites
- [MarkLogic 9+](https://developer.marklogic.com/products)
- JDK 1.8+
- [Gradle 4+](https://www.gradle.org/)
- [MarkLogic JobRepository](https://github.com/marklogic-community/marklogic-spring-batch/releases/download/1.6.0/mlJobRepo-1.6.0.zip)

## How do I get started?
[Getting Started](https://github.com/marklogic-community/marklogic-spring-batch/wiki/Getting-Started) - a tutorial to build a sample program which builds random JSON and loads into MarkLogic.
Read the [Spring Batch Cookbook](https://github.com/sastafford/spring-batch-cookbook) to view some existing programs utilizing SB and MSB.

## MarkLogic JobRepository
Spring Batch has the concept of a JobRepository that serves as a persistent mechanism for the metadata generated from running batch processing jobs. This project offers an implementation of the JobRepository using MarkLogic.

To [setup the MarkLogicJobRepository](https://github.com/marklogic-community/marklogic-spring-batch/wiki/SetupMarkLogicJobRepository), use the mlJobRepo utility to bootstrap a JobRepository using MarkLogic.

Once setup, then your JobConfig must access the required Job Properties to use the MarkLogic JobRepo.

## Running the samples

#### Running the OneStepJobConfig sample:

    gradle runOneStepJob
    
This will insert 100 json documents into MarkLogic

#### Running the TwoStepJobConfig sample:

    gradle runTwoStepJob
    
This wil not insert any documents but shows how a multi job config should look like.

#### Running the MigrationJobConfig sample:
First you need to set up the H2 in memory database
    
    gradle loadH2Data
    
This will prepare a H2 database with 4 tables:
- Product
- Item
- Invoice
- Customer

Then you can run the MigrationJob

    gradle runMigrationJob
    
This will pull all data from all tables of the H2 database


    