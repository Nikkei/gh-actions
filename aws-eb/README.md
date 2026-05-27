# aws-eb

Custom actions for deploying Docker-based applications to AWS Elastic Beanstalk

## Description
### build-image

This action
- build images using docker custom actions
- also automatically cache docker images

### init-eb

This action
- create an EB environment
   - also set up a Lifecycle
- does nothing if EB environment already exists

### install-deploy-tools

This action installs necessary tools for deployment.

`ebi` and `awsebcli` are installed from a hash-pinned lock file (`install-deploy-tools/v1/requirements.txt`) using pip's hash-checking mode. To bump versions, edit `requirements.in` and regenerate the lock:

```sh
cd install-deploy-tools/v1
uv pip compile requirements.in --generate-hashes --python-version 3.12 --python-platform linux -o requirements.txt
```

### login-aws

This action
- authenticates to AWS
- also creates a credential file for EB command

### pre-deploy

This action updates configs and installs extensions for EB deployment

### push-image

This action
- pushes docker images to ECR
- also create a ECR and configure it
