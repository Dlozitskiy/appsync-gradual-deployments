This is a project to showcase a safe deployment of AppSync lambda datasources to production environment.

## Getting Started

First, package the template using S3 bucket in your account:

```bash
aws cloudformation package --template-file template.yaml --s3-bucket s3-bucket-in-your-account --output-template-file template-updated.yaml
```

## Deploy to AWS account

Deploy stack using a template produced by `package` command.

```bash
aws cloudformation deploy --template-file template-updated.yaml --stack-name appsync-gradual-deployment-stack --capabilities CAPABILITY_NAMED_IAM CAPABILITY_AUTO_EXPAND
```

Check out our [Safe deployment strategies for AppSync Lambda datasources](https://medium.com/@dlozitskiy/safe-deployment-strategies-for-appsync-lambda-datasources-20db91d82651) for more details.
