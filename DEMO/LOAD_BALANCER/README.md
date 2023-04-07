### Working with LOAD_BALACERS

#### Launch your instances in different AZs

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
