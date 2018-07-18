# gatsby-app-aws-devops-pipeline
A template for a CI/Cd pipeline for a gatsby single page application.

## Usage
Add the pipeline as a submodule to your project repository:

```bash
git add submodule https://github.com/magnus1984/react-app-aws-devops-pipeline.git
```

You can then deploy the pipeline using cloudformation
```bash
aws cloudformation deploy --template-file pipeline.yaml --stack-name <YOUR-PIPELINE-STACK-NAME> --capabilities CAPABILITY_IAM --parameters ...
```

## Templates Parameters
The buildspec uses environment variable for a quick and easy way to deploy every component required by the gatsby website. When you deploy the 
pipeline with cloudformation, you MUST specify the following parameters to be passed along as environments variables to CodeBuild:

1. INFRASTRUCTURE_TEMPLATE: the path, relative to the projects root, where the cloudformation infrastructure template required for the gatsby app is.
2. PROJECT_NAME: the name of your project; used with DEPLOY_ENVIRONMENT to create a stack name for your pipeline.
3. DEPLOY_ENVIRONMENT: the environment created to deploy the project. Used with PROJECT_NAME to create a stack name for you pipeline.
   Alos, only commits to a branch having this exact name will trigger a build + deploy.

## Asumptions
The buildspec assumes that the infrastructure cloudformation template will return the bucket name for static assets deployment as the first
output of the template.


## Author
Jonathan Pelletier (jonathan.pelletier1@gmail.com, https://hedgenet.info)
