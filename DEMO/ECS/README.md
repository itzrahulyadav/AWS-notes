### To Work with ECS

1. Deploy your container to Dockerhub/ECR
2. Optional 
   -  Create a VPC and subnets

#### ECS
Create a cluster
- Create a Task Defintion
  -  Give cluster a name
  -  Provide the Docker image details.
  -  Give the port details.
  -  click on next
on the Configure environment, storage, monitoring, and tags section
-  select fargate as the app environment
-  select operating system
-  In the task size select cpu and memory
-  select a task role
-  leave everything as is.
Create a service
- In the environment under compute options select launch type
- In the deployment configuration under application type select service
- select your taskdefinition
- provide the service name
- select the number of desired task
- select the security group and make sure the inbound ports are open on your sg as defined in your docker image
- 
