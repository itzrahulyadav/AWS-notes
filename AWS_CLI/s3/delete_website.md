#!/bin/bash

bucket_name='your-bucket-name'
website_directory='/path/to/website/'

region='us-east-1'
profile='default'


aws s3 rm \
  --profile $profile \
  --region $region \
  --recursive s3://$bucket_name
  
aws s3api delete-bucket \
  --profile $profile \
  --region $region \
  --bucket $bucket_name
