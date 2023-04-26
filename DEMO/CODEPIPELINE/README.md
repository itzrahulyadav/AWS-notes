{
    "pipeline": {
     "roleArn": "arn:aws:iam::<FMI_1>:role/RoleForCodepipeline",
     "stages": [
       {
         "name": "Source",
         "actions": [
           {
             "inputArtifacts": [],
             "name": "Source",
             "actionTypeId": {
               "category": "Source",
               "owner": "AWS",
               "version": "1",
               "provider": "CodeCommit"
             },
             "outputArtifacts": [
               {
                 "name": "MyApp"
               }
             ],
             "configuration": {
               "RepositoryName": "front_end_website",
               "BranchName": "main"
             },
             "runOrder": 1
           }
         ]
       },
       {
         "name": "Deploy",
         "actions": [
           {
             "inputArtifacts": [
               {
                 "name": "MyApp"
               }
             ],
             "name": "CafeWebsite",
             "actionTypeId": {
               "category": "Deploy",
               "owner": "AWS",
               "version": "1",
               "provider": "S3"
             },
             "outputArtifacts": [],
             "configuration": {
               "BucketName": "<FMI_2>",
               "Extract": "true",
               "CacheControl": "max-age=14"
             },
             "runOrder": 1
           }
         ]
       }
     ],
     "artifactStore": {
       "type": "S3",
       "location": "codepipeline-us-east-1-<FMI_1>-website"
     },
     "name": "cafe_website_front_end_pipeline",
     "version": 1
    }
   }
