## Kinesis

- It has kinesis video streams,data streams,data firehose,data analytics
 
#### Kinesis data firehose

- click on kinesis data firehose.
- click on create delivery stream.
#### on create a delivery stream.
- for source choose direct put.
- for destination choose amazon s3
- Give a delivery stream name of your choice.
-  For Transform source records with AWS Lambda, choose the check box to select Enable data transformation. 
-  For AWS Lambda function, click Browse and select a lambda function.
-  Go to the next step.
-  In the destination settings
        -  select a s3 bucket
        -  provide the prefix for data and one for error.
-  Expand the buffer hints,expression and encryption
-  Expand the advanced settings and select existing IAM role.
-  click on create stream service.
-  
