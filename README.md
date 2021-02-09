# Sparkify Data Warehouse
## Sparkify has a need for a data warehouse due to company growth.  Here, we set that up in the cloud, using Amazon's Redshift service.  Along the way, we will utilize an ETL pipeline,
## As part of this pipeline, we will stage data in s3, before pushing it into Redshift.  We'll set up dimension tables, to aide our analytics team in gleaning insights from the data.  

## The components are as follows
### Generating the Cluster
#### This is a notebook, that will go through, and generate us a cluster, as well as an arn with the correct policy for the task.  We'll take this info and add it to our config

### Create the Tables
#### Based on the sql statements we defined to create/drop the tables, they will be executed

### Populate the Tables
#### Using the statements we defined to perform the loading, we will populate the database

### Inspect the Data
#### A quick utility to download and inspect the S3 data

### Run the Pipeline
#### Chain our tasks together for an end to end pipeline.  Very basic queries also exist here to ensure data populated the database

### Delete Redshift Cluster
#### Clean up our resources at completion

