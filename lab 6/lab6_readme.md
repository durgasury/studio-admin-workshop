# Lab 6: Create an end-to-end SageMaker Project

SageMaker Projects help organizations to set up and standarize developer environments for data scientists and CI/CD systems for MLOps engineers. Projects are AWS CloudFormation templates that are provisioned through AWS Service Catalog. 

SageMaker provides a list of templates for users to get started. Administrators can also create custom project templates, and restrict their users to only their custom templates. 

![sagemaker-project](/img/projects-ml-workflow.png)

## Task

From the Studio Home page, launch a Project using a SageMaker provided template. View the CloudFormation stack to understand the resources provisioned and the CI/CD mechanisms. You can view the Project, Pipeline, Pipeline execution status, and the versioned model in the Model Registry as well. Follow along the instructions [here](https://docs.aws.amazon.com/sagemaker/latest/dg/sagemaker-projects-create.html) to create a project. 

## Additional Resources

- [Automate MLOps with SageMaker Projects](https://docs.aws.amazon.com/sagemaker/latest/dg/sagemaker-projects.html)
- [Build Custom SageMaker Project Templates – Best Practices](https://aws.amazon.com/blogs/machine-learning/build-custom-sagemaker-project-templates-best-practices/)