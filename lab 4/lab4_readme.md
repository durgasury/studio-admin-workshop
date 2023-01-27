# Lab 4: Access the Studio UI by creating a pre-signed URL using AWS CLI

In an IAM mode, users get access to SageMaker Studio through a pre-signed URL. When users go to the SageMaker console, and click Launch -> Studio, the [CreatePresignedDomainUrl](https://docs.aws.amazon.com/sagemaker/latest/APIReference/API_CreatePresignedDomainUrl.html) API call is made.

Administrators can choose to abstract this away and use Lambda functions or custom applications to generate the URL using the Boto3 SDK. In this task, we will simply generate the URL from AWS CLI.

Ensure you have AWS CLI installed, with administrator access. Alternatively, you can also use [AWS CloudShell](https://aws.amazon.com/cloudshell/) to interact with a terminal from your browser.

![cloud-shell](/img/cloud-shell.png)

## Task

Run the following command on the terminal to generate the presigned URL - 

```
aws sagemaker create-presigned-url --domain-id <your-domain-id> --user-profile-name <your-user-profile-name>
```

Copy the returned `AuthorizedURL` value and paste it in your browser to be redirected to the Studio UI. 

*Note*: You can customize the `--expires-in-seconds` value (minimum of 5 seconds) to prevent unauthorized access.