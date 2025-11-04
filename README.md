# Example `cml-runner` workflow

This repository contains a sample project using [CML](https://github.com/iterative/cml) to provision and launch an EC2 instance and run a machine learning workflow on the instance:
- GitHub will deploy a runner machine and setup CML with the `setup-CML` GitHub Action
- The workflow uses `cml-runner` to provision and launch a `g4dn.xlarge` instance on AWS EC2
- The new `g4dn.xlarge` instance runs a workflow to pull a Docker container, install Python package requirements, and train a `scikitlearn` model.
- CML returns a summary of the model accuracy and a confusion matrix as a comment in your Pull Request. 

The key file enabling these actions is `.github/workflows/cml.yaml`.

## Secrets and environmental variables
In this example, `.github/workflows/cml.yaml` contains three environmental variables that are stored as repository secrets.

| Secret  | Description  | 
|---|---|
|  PERSONAL_ACCESS_TOKEN | You must create a personal access token with repository and workflow permissions. |
| AWS_ACCESS_KEY_ID  | AWS credential for accessing S3 storage  | 
| AWS_SECRET_ACCESS_KEY | AWS credential for accessing S3 storage |
