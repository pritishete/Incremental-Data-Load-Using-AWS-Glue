# Incremental Data Load Using AWS Glue

It is data pipeline to load the input file coming on S3 bucket on daily basis using glue job with the help of glue crawler and job bookmarking

## Tech Stack

**Language:** Python

**Storage:**  S3 bucket

**ETL Service:** AWS GLUE

## Steps to run 

1.Create bucket with name as telecom-data-glue-analysis in S3

2.Create the crawler in glue as telecom-data-cralwer to look for input file under s3 bucket. Once crawler get created run the crawler
  so that it will create metadata table for the input file into glue data catalog

3.Write the glue application where it will read data with the help of glue catalog and pyspark dataframe and print the records and their count in the output log

4.Go to the Glue under visual ETL and choose Script editor with Spark option and write the code to read the table present in the glue catalog.
  Here in this case i have created incremental_data_in_glue.py 

5.Go to the job-detail section and add new parameter as --JOB_NAME and give some value like "glue-data-test" and enable the job-bookmarking option so that it will keep the
  history of the files that read so far and avoid duplication

6.Run the glue job script that has created , once it runs successfull then check the output logs ,you will the records from the file get printed with its count

