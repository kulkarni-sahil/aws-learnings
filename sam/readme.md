# SAM

## SAM Template

### Transform: AWS::Serverless-2016-10-31

This instructs CloudFormation that this is a SAM template. This will "unwrap" the SAM template and transforms it to a full-fledged CloudFormation template.

### Globals

You can provide common configurations using Globals. For instance, if you would like to set up the runtime as nodejs14.x and timeout as 30 seconds, you can do that for all the Lambda functions in the Globals section. In this example, the timeout is set at 3 seconds. This will apply to all functions within this template.


cmds:
sam build
sam deploy --guided

sam build
sam deploy

## SAM Accelerate

SAM Accelerate allows faster deployment via sam sync, and also provides a mechanism to observe the application, via sam logs and sam traces. Today, we will be touching on the deployment only.

sam sync --watch
Let's first talk about sam sync. This command bypasses the CloudFormation changeset process for code changes and uses the underlying service APIs to upload the changes. This makes the deployment of code changes much faster. On top of this, the --watch flag will "watch" the changes to the application and deploys the changes to your stack automatically.

sam sync --stack-name api --watch


## SAM Pipelines

sam pipeline init --bootstrap