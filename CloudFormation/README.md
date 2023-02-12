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
 
