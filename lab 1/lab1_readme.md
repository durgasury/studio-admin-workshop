# Lab 1: Create a least privilege role for data scientists using Role Manager

AWS IAM recommends giving your users the least privilege permissions to AWS resources as a security best practice. To interact with SageMaker, you have the following roles -
1. ML Admin user role - this is the user/principal who provisions the environment for data scientists by creating the domain, creating the IAM roles, user profiles, S3 buckets for data, networking settings etc. 
2. Studio user role - this is the persona logging into SageMaker Studio. This user will need access to data based on their access level, need to experiment by creating training jobs, processing jobs, experiments, pipelines, etc. Based on their persona, this user can be a data engineer, data scientist, MLOps engineer or a custom role.
3. SageMaker execution service role - When a data scientist launches the jobs and creates models, SageMaker service needs a service execution role to access resources on the user's behalf. For experimentation and development, this role can be the same as the Studio user role. In production settings, we recommend a separate service role for CI/CD.

## IAM roles and personas

![roles-policies-diagram](/img/user-service-roles.png)

## Task

Role manager documentation: https://docs.aws.amazon.com/sagemaker/latest/dg/role-manager-tutorial.html

1. Create a role for the training jobs, models etc. using the SageMaker Compute Role persona, following the directions in the documentation. Add VPC configurations and encryption restrictions as required. Once the role is created, view the role and copy the role ARN. You will need it for Step 2. Look into the policies attached to the role as well. 

2. Create a role for the Studio user, using the Data Scientist persona. You will need to provide the compute ARN from Step 1. Once the role is created, copy the role name. You will need this for Lab 2. 

Optionally, add the policy in [Domain resource isolation](https://docs.aws.amazon.com/sagemaker/latest/dg/domain-resource-isolation.html) documentation, to restrict your user access to resources in their domain. SageMaker Studio automatically tags SageMaker resources created from the console.

## Additional Resources

- [Define customized permissions in minutes with Amazon SageMaker Role Manager](https://aws.amazon.com/blogs/machine-learning/define-customized-permissions-in-minutes-with-amazon-sagemaker-role-manager/)
- [Amazon SageMaker Role Manager](https://docs.aws.amazon.com/sagemaker/latest/dg/role-manager.html)