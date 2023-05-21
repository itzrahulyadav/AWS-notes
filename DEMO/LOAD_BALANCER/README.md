### Working with LOAD_BALANCERS

#### Launch your instances in different AZs


### Availability Zones

- physical data centers used for high availability zones.
- ![module-9-guided-lab-task-2](https://github.com/itzrahulyadav/AWS-notes/assets/65400893/840ca285-204c-480c-9d7d-9b09f4e29a3c)

#### Target Groups :  
-  Target groups define where to send traffic that
comes into the load balancer. The Application Load Balancer can send traffic to multiple target groups based upon the URL of the incoming request, such as having requests from mobile apps going to a different
set of servers. Your web application will use only one target group.

#### Auto Scaling groups

Amazon EC2 Auto Scaling is a service
designed to launch or terminate Amazon EC2 instances automatically based on user-defined policies, schedules, and health checks. It also automatically distributes instances across multiple Availability Zones to make applications highly available.

#### Launch Configuration

 This defines the type of instances that Amazon EC2 Auto Scaling should launch. 
 The interface looks similar to when you launch an EC2 instance. However, instead of launching an instance, it stores the configuration for later use.


### Steps:

##### Create a load balancer

1. give a name
2. select a vpc or create a new one.
3. select the azs and public subnets in the azs
4. create a new security group that allows traffic from the load balancer.
5. in the security group allows http traffic from anywhere.

###### create a target group.
1. choose instances.
2. load balancers check traffic automatically but we can increaase the threshold.
3.  Healthy threshold: 2
    Interval: 10 (seconds)
    
4. In the register targets section choose the ec2 instances that will respond to the traffic.
5. Now select this target group.
6. click on create a load balancer.

#### Create a auto scaling group.

-  ![module-9-guided-lab-task-3](https://github.com/itzrahulyadav/AWS-notes/assets/65400893/f01a6f1f-4d57-42c4-ad90-e3dca4a886e2)

1. create an ami for auto scaling group.
2. select the instance and click on actions and select image and templates > create image.
3. note the ami id

#### Create a launch configuration.

1. launch configuration defines the type of instances that Amazon EC2 Auto Scaling should launch .
2. 
