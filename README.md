# react-app-aws-devops-pipeline
A template for a CI/Cd pipeline for a react single page application.

## Usage
Add the pipeline as a submodule to your project repository:

```bash
git add submodule https://github.com/magnus1984/react-app-aws-devops-pipeline.git
```

You can then deploy the pipeline using cloudformation
```bash
aws cloudformation deploy --template-file pipeline.yaml --stack-name <YOUR-PIPELINE-STACK-NAME> --capabilities CAPABILITY_IAM --parameters ...
```

## Author
Jonathan Pelletier (jonathan.pelletier1@gmail.com, https://hedgenet.info)
