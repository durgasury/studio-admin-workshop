# SageMaker Studio Adminstration workshop

This is a workshop designed for SageMaker Studio administration and best practices. The target audience is ML Platform administrators, or data science teams responsible for creating a Studio environment for their experimentations. 

For best practices in setting up SageMaker Studio, refer to the whitepaper here - https://docs.aws.amazon.com/whitepapers/latest/sagemaker-studio-admin-best-practices/sagemaker-studio-admin-best-practices.html

*Note*: This workshop expects users to create and manage IAM roles in addition to SageMaker resources, so an Administrator access is required. Remember to delete the apps and domain once you complete the workshop to avoid incurring charges.


## Domains Overview

![domain-and-apps](/img/domains-spaces-entity-diagram.svg)

## Labs

[Lab 1: Create a least privilege role for data scientists using Role Manager](/lab%201/lab1_readme.md)

[Lab 2: Create a domain](/lab%202/lab2_readme.md)

[Lab 3: Customize the domain by setting lifecycle configurations](/lab%203/lab3_readme.md)

[Lab 4: Access the Studio UI by creating a pre-signed URL using AWS CLI](/lab%204/lab4_readme.md)

[Lab 5: Launch a Studio notebook](/lab%205/lab5_readme.md)

[Lab 6: Create an end-to-end SageMaker Project](/lab%206/lab6_readme.md)

[Lab 7: Launch a shared space](/lab%207/lab7_readme.md)