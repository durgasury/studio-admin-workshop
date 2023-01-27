 # Lab 2: Create a domain

 Creating a domain can be done easily using the [Quick Setup](https://docs.aws.amazon.com/sagemaker/latest/dg/onboard-quick-start.html), where Studio automatically creates the EFS associated with the domain in your region's default VPC, with public internet access and in IAM mode. However, for most enterprise cases, we recommend using the Standard Setup. 

 These are the primary considerations when setting up a domain:
 1. Authentication mode: There are two modes of authenticating users into a domain
    1. IAM mode: Users login to the AWS console either as IAM users or through AWS account federation, and Launch Studio from the SageMaker console (https://console.amazon.com/sagemaker)
    2. SSO mode (IAM Identity Center): Users login to AWS Identity Center, and directly access the Studio UI through single sign-on experience. 

Here are a few considerations when choosing the mode (a domain's authentication mode cannot be changed after creation):
1. If you want your users to not access the AWS console and view the Studio UI directly, use SSO mode.
2. If you want your users to not access the AWS console and view the Studio UI directly in IAM mode, you can do that by using a Lambda function in the backend to generate a presigned URL for the user profile and redirecting them to the Studio UI. 
2. In SSO mode, each user is mapped to a single user profile. 
3. If you're using AWS Identity Center and need a single physical user needs access to multiple user profiles (for example - different access to data required as part of multiple projects), you will need to set up a custom SAML application and set up Studio in **IAM mode**. See this blog [Team and user management with Amazon SageMaker and AWS SSO](https://aws.amazon.com/blogs/machine-learning/team-and-user-management-with-amazon-sagemaker-and-aws-sso/)
4. The users are automatically assigned the default execution role in SSO mode. If you would like your users to be assigned different execution roles, you will need to update the user profiles.
5. Shared spaces is not available in SSO mode.

## Task

1. Create a SageMaker Domain from the console. Use the following settings -
    1. Choose Standard Setup
    2. Choose IAM mode 
    3. Specify the Studio user role created in Lab 1 as the default execution role
    4. Specify a VPC and a private subnet in the VPC (if using VPC only traffic mode), or a VPC and subnets (if using Public internet mode)
    5. If you're choosing VPC only traffic mode,
        1. a NAT gateway is required for users in Studio to access internet, and to access other AWS services. 
        2. You can also choose to restrict internet traffic and add VPC endpoints instead.
        3. Ensure you have the required endpoints and the Security groups allow the required communication, based on the documentation [here](https://docs.aws.amazon.com/sagemaker/latest/dg/studio-notebooks-and-internet-access.html).

You can instead use the template in the blog [here](https://aws.amazon.com/blogs/machine-learning/securing-amazon-sagemaker-studio-connectivity-using-a-private-vpc/) to create a domain in VPC-only mode with minimum permissions (the template will also create a least privilege IAM role for the domain).

2. Create a Studio user profile with the same default execution role. Documentation - https://docs.aws.amazon.com/sagemaker/latest/dg/domain-user-profile-add-remove.html

## Additional Resources

- [Secure access to Amazon SageMaker Studio with AWS SSO and a SAML application](https://aws.amazon.com/blogs/machine-learning/secure-access-to-amazon-sagemaker-studio-with-aws-sso-and-a-saml-application/)
- [Configuring Amazon SageMaker Studio for teams and groups with complete resource isolation](https://aws.amazon.com/blogs/machine-learning/configuring-amazon-sagemaker-studio-for-teams-and-groups-with-complete-resource-isolation/)
- [Onboarding Amazon SageMaker Studio with AWS SSO and Okta Universal Directory](https://aws.amazon.com/blogs/machine-learning/onboarding-amazon-sagemaker-studio-with-aws-sso-and-okta-universal-directory/)
- [Onboard to Amazon SageMaker Domain](https://docs.aws.amazon.com/sagemaker/latest/dg/gs-studio-onboard.html)
- [Securing Amazon SageMaker Studio connectivity using a private VPC](https://aws.amazon.com/blogs/machine-learning/securing-amazon-sagemaker-studio-connectivity-using-a-private-vpc/)
- [Connect SageMaker Studio Notebooks in a VPC to External Resources](https://docs.aws.amazon.com/sagemaker/latest/dg/studio-notebooks-and-internet-access.html)