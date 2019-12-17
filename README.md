# Cloud-formation nested stacks to s3 sync from GitHub and cloud-front invalidation.
## Description
This repository contains cloud-formation nested stacks to create code pipeline to perform s3 sync from GitHub repository and cloud-front invalidation. Codepipeline contains two stages one for UAT and other for Production. Both stages contains code-build to perform actions. Production stage has its manual trigger and optional as well which you can define in parameters.
## Table of contents
-   [Structure](https://github.com/sikandarqaisarch/codepipeline-s3sync-cloudfrontInvalidation#structure)
-   [Prerequisites](https://github.com/sikandarqaisarch/codepipeline-s3sync-cloudfrontInvalidationStack#prerequisites)
-   [Parameters](https://github.com/sikandarqaisarch/codepipeline-s3sync-cloudfrontInvalidation#Parameters)
- [Deploy Stack](https://github.com/sikandarqaisarch/codepipeline-s3sync-cloudfrontInvalidation#Deploy-Stack)
-   [Output](https://github.com/sikandarqaisarch/codepipeline-s3sync-cloudfrontInvalidation#Output)


# Cloud-formation nested stacks to s3 sync from GitHub and cloud-front invalidation.
## Description
This repository contains cloud-formation nested stacks to create code pipeline to perform s3 sync from GitHub repository and cloud-front invalidation. Codepipeline contains two stages one for UAT and other for Production. Both stages contains code-build to perform actions. Production stage has its manual trigger and optional as well which you can define in parameters.
## Table of contents
-   [Structure](https://github.com/sikandarqaisarch/codepipeline-s3sync-cloudfrontInvalidation#structure)
-   [Prerequisites](https://github.com/sikandarqaisarch/codepipeline-s3sync-cloudfrontInvalidation#prerequisites)
-   [Parameters](https://github.com/sikandarqaisarch/codepipeline-s3sync-cloudfrontInvalidation#Parameters)
- [Deploy Stack](https://github.com/sikandarqaisarch/codepipeline-s3sync-cloudfrontInvalidation#Deploy-Stack)
-   [Output](https://github.com/sikandarqaisarch/codepipeline-s3sync-cloudfrontInvalidation#Output)




## [](https://github.com/sikandarqaisarch/codepipeline-s3sync-cloudfrontInvalidation#structure)Structure

Structure contains cloud-formation nested stacks to create code pipeline to perform s3 sync from GitHub repository and cloud-front invalidation.

- main.yaml
- CodeBuild.yaml
- Pipeline.yaml
- Roles.yaml
      
## [](https://github.com/sikandarqaisarch/codepipeline-s3sync-cloudfrontInvalidation#prerequisites) Prerequisites
- Create a cicd folder in s3.
- upload all stack on your desired s3 bucket in cicd folder. 
- Create Oauth token in GitHub.
- Create aws secrete manager which is key value based and store GitHub Oauth token in it.


## [](https://github.com/sikandarqaisarch/codepipeline-s3sync-cloudfrontInvalidation#Deploy-Stack)Deploy Stack
- Deploy main.yaml file in cloud-formation.
-  Provide values to parameters.

## [](https://github.com/sikandarqaisarch/codepipeline-s3sync-cloudfrontInvalidation#Parameters)Parameters



| Parameters | Required | Description |
| --- | --- | --- |
| ApplicationName 			|yes| Application Name for the reference. |
| ArtifactStoreS3Location 	|yes| Name of the S3 bucket to store CodePipeline artificat. |
| BranchName 				|yes| Branch for GitHub source code. |
| DeploymentPath 			|yes | S3 bucket folder for source code storage. |
| GitHubOwner 				|yes | Repository owner name as per GitHub account. |
| Paths 					|yes | Path for Cloud-front build command. |
| ProdBucketName 			|Optional | Name of the Production S3 bucket to store application source code ** OPTIONAL **. |
| ProdDistributionId 		|Optional | Cloud-front Distribution Id for Production ** OPTIONAL ** if ProdDistributionId not provided.  |
| RepositoryName 			|yes | Github source code repository name. |
| SecretManagerName 		|yes | Name of the secret in which GitHub token is stored. |
| SecureStringKey			|yes | Secret key in which GitHub token is stored. |
| TemplateBucket 			|yes | Nested stacks bucket location |
| UATBucketName 			|yes | Name of the UAT S3 bucket to store application source code. |
| UATDistributionId 		|yes | Cloud-front Distribution Id for UAT. |


## [](https://github.com/sikandarqaisarch/codepipeline-s3sync-cloudfrontInvalidation#Output)Output
