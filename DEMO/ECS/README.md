### To Work with ECS


#### what is ECS ?

- ECS is a container orchestrator just like Docker swarm and k8
- it managesthe lifecycle of a container create/destroy/restart
- deploying and load balancing application across multiple servers
- Autoscaling to handle variant of traffic
- rolling out changes to application
- We cannot scale out our application to different servers using docker-compose.
- If we run our application across 3 servers by running our docker-compose across 3 servers they are running in 3 servers but they are not aware of other servers so its not called orchestrating.
- ECS doesn't act as a server,it does not have compute power
- ECS can only create and delete containers
- Cluster is a bunch of resources that our containers are going to run on like EC2.





#### EC2 launch type 
##### - In EC2 cluster we have to manage the underlying infrastructure.
- we have to create individual and manage this ec2
- we have to install docker and ecs agent that ecs control plane can talk to and give instructions.
- we have to install firewalls and other routing pathces and upgrades to keep our servers up to date.
- we get full control our infrastructure.
![Screenshot_20230528-164642_Video Player](https://github.com/itzrahulyadav/AWS-notes/assets/65400893/5773732d-2174-4dac-8fb5-c49c912b4311)




### ECS fargate
##### - In ecs fargate aws manages the underlying infrastructure.
- It follows a serverless architecture.
- No need to create servers
- ECS will talk to fargate and it will create our servers on demand like EC2
- then ECS can launch our app to ec2
- Fargate manages the underlying resources
![VideoCapture_20230528-165040](https://github.com/itzrahulyadav/AWS-notes/assets/65400893/9abd4c42-506a-4f4c-b050-a2f54673843a)


### ECS task definition

- Blueprint that describes how containers should launch.
- How much mem/CPU
- what image to use
- what ports to use/vlumes
- It contains a configuration just like a docker-compose file.
- 
![VideoCapture_20230528-165320](https://github.com/itzrahulyadav/AWS-notes/assets/65400893/f70e1066-85c3-4687-86f2-50a77a414ae4)

### ECS Task

- It's just an instance of a task definition.
- A task is just a running container with settings defined in the task DF
![VideoCapture_20230528-165635](https://github.com/itzrahulyadav/AWS-notes/assets/65400893/fbeeb096-c485-4e0a-a87d-e7e96229f56d)


### ECS services

- A service just ensures that a certain number of tasks are running at all times
- Suppose we have an application on python and we want 2 seperate instances(tasks)/containers of our application running at all times.Serviecs will check and create two instances and deploy it in some servers in our cluster.
- It also restart the crashed container.
- ECS instance fails,the service will restart the task on working ec2 instance.
![VideoCapture_20230528-170205](https://github.com/itzrahulyadav/AWS-notes/assets/65400893/fceffa95-cbae-49fd-bc9a-a8bc5f011b39)


#### Load Balancers

- We can assign load balancer to route traffice to our services.
- ![VideoCapture_20230528-170422](https://github.com/itzrahulyadav/AWS-notes/assets/65400893/7fb55260-193c-470f-902d-e7b3f8a474e0)






1. Deploy your container to Dockerhub/ECR
2. Optional 
   -  Create a VPC and subnets

#### ECS
1. Create a cluster
2. Create a Task Defintion
  -  Give cluster a name
  -  Provide the Docker image details.
  -  Give the port details.
  -  click on next
### on the Configure environment, storage, monitoring, and tags section__
-  select fargate as the app environment
-  select operating system
-  In the task size select cpu and memory
-  select a task role
-  leave everything as is.
3. Create a service
- In the environment under compute options select `launch type`
- In the deployment configuration under application type select `service`
- select your taskdefinition
- provide the service name
- select the number of desired task
- select the security group and make sure the inbound ports are open on your sg as defined in your docker image.
- In the clusters click on the cluster name and click on the tasks tab which is present next to services.
