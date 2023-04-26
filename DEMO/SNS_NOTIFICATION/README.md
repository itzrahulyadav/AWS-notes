# Creating a sns notification for object upload in s3

1. Enable eventbridge in s3 bucket that you want to enable notification for.
2. create a sns topic 
     - Give a proper name
     - choose standard
     - change the access policy to s3 account owner
              - select aws account
              - again select the aws account and provide the account id

3. Create a subscription for the topic
     - select email/json
     - type the email
     - create subscription

4. confirm the subscription to the email provided
5. configure eventbridge

-  Create eventbridge rule
- give a proper name
- for the define pattern select event pattern
- select predefined service by name
- for the service provider select aws 
- for the service name select s3
- for the event type select aws s3 event notification
- select specific event in the next option and select object created
- select specific bucket name in the next option and provide the name of the bucket

-  select target --> sns topic
-  select topic name that you created in step 1
-   select create and you are all set.
-   you can test the notification by uploadin an object in your s3 bucket.
