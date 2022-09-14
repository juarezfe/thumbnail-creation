<!--
title: 'AWS Python Example: Thumbnail Creation'
description: 'This template demonstrates how to deploy a Python project running on AWS Lambda using the traditional Serverless Framework.'
layout: Doc
framework: v3
platform: AWS
language: python
priority: 2
authorLink: 'https://github.com/serverless'
authorName: 'Serverless, inc.'
authorAvatar: 'https://avatars1.githubusercontent.com/u/13742415?s=200&v=4'
-->


# Serverless Framework AWS Python Example: Thumbnail Creation

This template demonstrates how to deploy a Python project running on AWS Lambda using the traditional Serverless Framework.
The project consist on:

1. Configure the s3 bucket and permissions required to upload images and create a thumbnail generation function that will create a thumbnail image automatically from the image uploaded in S3 and then save it to a database (dynamoDB).

2. Create REST API (API GATEWAY) Methods:
  - s3_get_thumbnail_urls
  - s3_get_item
  - s3_delete_item
  
3. 

## Usage

### Deployment

In order to deploy the example, you need to run the following command:

```
$ sls deploy
```

After running deploy, you should see output similar to:

```bash
Deploying aws-python-project to stage dev (us-east-1)

✔ Service deployed to stack aws-python-project-dev (112s)

functions:
  s3_thumbnail_generator: aws-python-project-dev-s3_thumbnail_generator (1.5 kB)
```

### Local development

### Bundling dependencies

In case you would like to include third-party dependencies, you will need to use a plugin called `serverless-python-requirements`. You can set it up by running the following command:

```bash
serverless plugin install -n serverless-python-requirements
```

Running the above will automatically add `serverless-python-requirements` to `plugins` section in your `serverless.yml` file and add it as a `devDependency` to `package.json` file. The `package.json` file will be automatically created if it doesn't exist beforehand. Now you will be able to add your dependencies to `requirements.txt` file (`Pipfile` and `pyproject.toml` is also supported but requires additional configuration) and they will be automatically injected to Lambda package during build process. For more details about the plugin's configuration, please refer to [official documentation](https://github.com/UnitedIncome/serverless-python-requirements).
