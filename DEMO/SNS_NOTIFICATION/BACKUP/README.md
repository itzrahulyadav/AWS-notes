## AWS backup
-  we can use aws backup to automate and protect data protection across aws services.
-  It uses aws backup vault which is a container that stores and organize your backup.
-  A backup plan which is a part of backup vault defines when and how you want to backup your aws resources.Different backup plans can be created for different requirments.
-  Resources can be assigned to backup plan.(using tags or resource ids)
-  Each backup vault uses a KMS which encrypts the backup created by backup vault.

### To backup an AWS EBS 
- select the volume that needs to be backuped.
- assign tags to the volume id
- Search for AWS backup in the search bar.
- Click on the backup vault and click on create backup vault.
- Provide name to vault and select kms key and click on create.

#### Select protected resources from left navigation pane
- select create on demand backup
- select aws resources like EBS,RDS etc.
- for now select EBS and select the volume id
- select create backup now.
- select the retention period.(days-7)
- select the backup vault that you created in the previous step.
- select a role .(role must have awsbackupfullaccess,AWSBackupServiceRolePolicyForBackup,AWSBackupServiceRolePolicyForRestores)
- click create on demand backup
#### Go to the Jobs page
#### Create a backup plan
- click create a backup plan
- select build a new plan
- give name to the plan
- In the  backup rule configuration
         - Give name to the rule
         - select backup vault
         - choose backkup frequency to weekly and select sunday
         - Click create plan
- Assign resources to the plan
     -  Provide name
     -  choose a role
     -  select include all resource types.

-  In the refine selection using tags provide value for key ,condition and value.
-  select assign resources
-  Go to the jobs page to see the status of jobs
-  Go to the protected resources to see all the protected resources.
-  
