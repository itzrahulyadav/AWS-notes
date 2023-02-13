# CloudFormation

### Resources 
- [AWS Workshop](https://catalog.workshops.aws/cfn101/en-US/introduction)


### Definition

-  CloudFormation is an IaC tool that allows you to model your infrastructure in a template file.
-  It supports both Json and YAML format.
-  CloudFormation template structure:

          -  AWSTemplateFormatVersion: 'version date' (optional)
          
          -  Description: 'String' (optional) # a text description of the Cloudformation template
            
          -  Metadata: 'template metadata' (optional) # objects that provide additional information about the template
            
          -  Parameters: 'set of parameters' (optional) # a set of inputs used to customize the template
            
          -  Rules: 'set of rules' (optional) # a set of rules to validate the parameters provided at deployment/update
            
          -  Transform: 'set of transforms' (optional) # for serverless applications
            
          -  Resources: 'set of resources' (required) # a components of your infrastructure
            
          -  Hooks: 'set of hooks' (optional) # Used for ECS Blue/Green Deployments
            
          -  Outputs: 'set of outputs' (optional) # values that are returned whenever you view your stack's properties
 
 ### Stack
 
 A stack contains a collection of AWS resources that you can manage as a single unit. All the resources in a stack are defined by the stack's AWS CloudFormation template.
 
 Stack is created in entirety i'e either fully or not at all.
 

### Intrinsic functions

 Intrinsic functions are pre-defined functions that allow you to dynamically configure and customize AWS resources during stack creation or update
 
 
-  !Ref: Returns the value of the named resource or parameter.
-  !Fn::ImportValue: Retrieves the value of an output exported by another stack in the same region.
-  !Fn::Join: Concatenates a list of strings into a single string, using a specified delimiter.
-  !Fn::Select: Returns a single object from a list of objects at the specified index.
-  !Fn::Split: Splits a string into a list of substrings using a specified delimiter.
-  !Fn::Sub: Replaces variables in a string with their values, using the ${VariableName} syntax.
-  !Fn::FindInMap: Returns the value associated with a specified key in a specified mapping.
-  !Fn::Base64: Encodes a string as Base64.
-  !Fn::GetAtt: Returns the value of the named attribute from the specified resource.
-  !If: Returns one value if a condition is true, and another value if it is false.

### Psudo Parameters

Pseudo parameters in CloudFormation are predefined values that are available for use in templates. They are automatically provided by CloudFormation and do not need to be defined or declared explicitly in the template.

Some examples of pseudo parameters include:

1.  AWS::AccountId: The AWS account ID of the account in which the stack is being created.
2.  AWS::Region: The name of the region in which the stack is being created.
3.  AWS::StackId: The unique ID of the stack.
4.  AWS::StackName: The name of the stack.
5.  AWS::URLSuffix: The suffix for the endpoint of AWS services in the current region.

### Mappings

Mappings in CloudFormation are a way to declare a set of key-value pairs that can be used in a template to look up and retrieve values based on a specified key.

__example__:

```
Mappings:
  RegionMap:
    us-east-1:
      AMI: ami-0ff8a91507f77f867
    us-west-2:
      AMI: ami-0a887e401f7654935
```
Here we are using one map called RegionMap.It has two key value pair.
Now we can use this map like this

```
Resources:
  MyInstance:
    Type: AWS::EC2::Instance
    Properties:
      ImageId: !FindInMap [RegionMap, !Ref 'AWS::Region', AMI]
      InstanceType: t2.micro
      ...
```
-  The FindInMap function will retrieve the value based on aws region.
