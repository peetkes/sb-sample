# sb-sample
Marklogic Spring Batch Sample Project

This projects shows how to make use of Marklogic Spring Batch to add content to MarkLogic.

Find all info about MLSB here: https://github.com/marklogic-community/marklogic-spring-batch/wiki

## Prerequisites
MarkLogic 9+
JDK 1.8+

## MarkLogic JobRepository
Spring Batch has the concept of a JobRepository that serves as a persistent mechanism for the metadata generated from running batch processing jobs. This project offers an implementation of the JobRepository using MarkLogic.

To setup the MarkLogicJobRepository, use the mlJobRepo utility to bootstrap a JobRepository using MarkLogic.

Once setup, then your JobConfig must access the required Job Properties to use the MarkLogic JobRepo.
