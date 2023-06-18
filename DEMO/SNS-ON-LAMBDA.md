## How to send custom message via SNS notification when an object is uploaded to s3.

follow the steps:

1. Create a s3 bucket
2. Create an sns topic.
          - for type select standard 
          - give it a name and click on create.

3. Create a subscription for the topic.
4. Create an IAM role that allows full access of s3 buckets and sns topics (we will use it for our lambda execution rule)
5. Create a lambda function from the scratch and choose python as runtime
6. paste the following code
7. choose the role that you created on step 5 
```
import boto3

def lambda_handler(event, context):
    # Extract bucket and key information from the event
    bucket = event['Records'][0]['s3']['bucket']['name']
    key = event['Records'][0]['s3']['object']['key']
    
    # Create an SNS client
    sns_client = boto3.client('sns')
    url = f'https://{bucket}.s3.amazonaws.com/{key}'
    # Publish message to the SNS topic
    sns_client.publish(
        TopicArn='arn:aws:sns:ap-south-1:192043038610:ry-testing-sns',  # Replace with your SNS topic ARN
        Message=f'New object is uploaded,you can check it here - {url}'  # Customize the notification message
    )

```

8. Configure S3 Event Notification: Go to the S3 bucket properties and set up an event notification. Choose the event type as "ObjectCreated" and configure the event destination as the Lambda function you created in step 7
9. make sure to make the bucket public so that the objects can be seen.


### To trigger different sns topic on different object uplaod use the below code
```
import boto3

def lambda_handler(event, context):
    # Extract relevant information from the event
    bucket = event['Records'][0]['s3']['bucket']['name']
    key = event['Records'][0]['s3']['object']['key']
    
    # Extract the object name from the key
    object_name = key.split('/')[-1]
    
    # Check the object name and send custom notifications
    if object_name == 'example.txt':
        send_notification('example notification')
    elif object_name == 'another.txt':
        send_notification('another notification')
    else:
        send_notification('default notification')

def send_notification(message):
    # Use an appropriate notification mechanism (e.g., SNS, SES, etc.)
    # to send the notification to your users
    # Implement the code here based on your chosen notification service
    # Example using SNS:
    sns = boto3.client('sns')
    sns.publish(
        TopicArn='your_topic_arn',
        Message=message
    )



```
