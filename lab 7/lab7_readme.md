# Lab 7: Launch a shared space

At re:Invent 2022, SageMaker launched Shared spaces within a Studio domain (refer to the domain overview diagram on the Readme file). Shared spaces allow for users within a domain to collaborate in real-time, using a shared IDE application. The underlying compute and EFS file directory is also shared by the users sharing the space. Shared spaces displays a cursor with users' co-editing in real-time. 

SageMaker resources created within the shared space is automatically tagged with the Space ARN, and automatically filters only resources that match the Space ARN on the UI. 

*Note*:
- The access control still needs to be done through IAM. The filtering is at the UI level, users can use APIs to access other spaces' resources without IAM restrictions.
- All shared spaces in a domain share the same execution role.
- [Source Identity](https://docs.aws.amazon.com/sagemaker/latest/dg/monitor-user-access.html) is not propagated within a space.
- If the SageMaker Studio domain is set in a VPC-only mode, administrators need to update the domain with the space security group settings, through the CLI. See a sample command [here](https://docs.aws.amazon.com/sagemaker/latest/dg/domain-space-create.html#domain-space-add:~:text=image%2Darn%7D%7D%22-,%23%20VPCOnly%20domain,-aws%20%2D%2Dregion%20region)

## Task

1. Create a shared space in the domain (remember to update the domain if it is in VPC-only mode). Launch an app in the shared space. 
2. Optionally, you can create a second user profile, and launch the shared space from the second user profile in a different browser to see co-editing in real-time.

## Additional resources

- [Organize machine learning development using shared spaces in SageMaker Studio for real-time collaboration](https://aws.amazon.com/blogs/machine-learning/organize-machine-learning-development-using-shared-spaces-in-sagemaker-studio-for-real-time-collaboration/)
- [Collaborate with shared spaces](https://docs.aws.amazon.com/sagemaker/latest/dg/domain-space.html)