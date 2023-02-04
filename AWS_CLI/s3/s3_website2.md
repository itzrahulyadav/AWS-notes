#!/bin/bash

bucket_name='your-bucket-name'
website_directory='/path/to/website/'

region='us-east-1'
profile='default'


aws s3 sync \
  --profile $profile \
  --region $region \
  $website_directory "s3://$bucket_name/" 
