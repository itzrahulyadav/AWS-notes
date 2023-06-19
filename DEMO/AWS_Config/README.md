## AWS Config
-  It continually monitors and records your aws resources configurations so that you can automatically evaluate recorded configurations against desired configurations.
-  It records details of changes to resources and delivers a configuratio history file to a specified bucket.
-  A sns is used to send a notification when a change from a previous state is detected.
-  we can use aws lambda to define custom rules to define custom best practices.
-  config console can be used to view and monitor the resource inventory,configuration history etc.

### Create a config rule 
-  Go to aws config and select get started
-  select all current and future resources selected in this region.
-  click all global resources.
-  click create aws service linked role.
-  for delivery method select s3 bucket
-   click next
-   Select rules.
-   review and click confirm
-   ` Select rules` to see if the rule is created.
-   Go to dashboard and check compliant and non compliant rules.   
