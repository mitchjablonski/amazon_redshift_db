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

### Running the Pipeline
#### To start, we will run the generate_redshift_cluster notebook, this will stand up our cluster and generate our iam role, with the correct policy.  When the cluster shows available, we will be able to start testing against it.  From there, we can jump over to the run_pipeline.ipynb, this brings in the main function from create_tables, which will drop any tables if they exist and then regenerate them.  After the tables are deleted/recreated we will begin the ETL process, this will perform the copy from s3 into our redshift cluster, then, once the data is copied into our cluster, we will execute our insert statements, where we query against the data we copied into redshift.  Additionally, we have some very basic queries to run at the end of the notebook to ensure population has occured.  Finally, when we are done with our redshift cluster, we can run the delete_redshift_cluster.ipynb.  This will go ahead, and remove the iam role that we generated, as well as spinning the cluster down.