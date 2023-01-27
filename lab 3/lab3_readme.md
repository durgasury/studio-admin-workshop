# Lab 3: Customize the domain by setting lifecycle configurations

You can customize your SageMaker Studio using lifecycle configuration scripts, which are essentially shell scripts that are executed at startup.
Some of the common examples are - 
1. Preloading datasets and libraries
2. Setting up source code repositories
3. Setting environment variables
4. Configuring Jupyterlab extensions
5. Automatically shutting down idle kernels to save costs

See the diagram below for a representation of Studio architecture (this does not include Shared spaces).

![studio-arch](/img/studio-arch.jpg)

LCC configurations such as configuring Jupyterlab extensions need to be set as `JupyterServer` scripts, while preloading packages need to be set as `KernelGateway` scripts, so the notebook compute instance has the libraries installed. 

## Task

View the LCC script samples in [Github](https://github.com/aws-samples/sagemaker-studio-lifecycle-config-examples), and the documentation [here](https://docs.aws.amazon.com/sagemaker/latest/dg/studio-lcc-create.html)

1. Set the [auto shutdown extension LCC script](https://github.com/aws-samples/sagemaker-studio-lifecycle-config-examples/blob/main/scripts/install-autoshutdown-server-extension/on-jupyter-server-start.sh) as a default JupyterServer script at the Domain level. Remember to set it as default for it to be automatically picked up at start up. 

2. Set the [install pypi package script](https://github.com/aws-samples/sagemaker-studio-lifecycle-config-examples/blob/main/scripts/install-pip-package-on-kernel/on-kernel-start.sh) as a KernelGateway script for the user created in Lab 2. You do not need to set this as a default, since the user will be prompted to choose a LCC script at startup. You can do this by editing the user profile. 

## Additional References

- [Customize Amazon SageMaker Studio using Lifecycle Configurations](https://aws.amazon.com/blogs/machine-learning/customize-amazon-sagemaker-studio-using-lifecycle-configurations/)
- [SageMaker Notebook Instance Lifecycle Config Samples - Github](https://github.com/aws-samples/sagemaker-studio-lifecycle-config-examples)
- [Use Lifecycle Configurations with Amazon SageMaker Studio](https://docs.aws.amazon.com/sagemaker/latest/dg/studio-lcc.html)
- [Dive deep into Amazon SageMaker Studio Notebooks architecture](https://aws.amazon.com/blogs/machine-learning/dive-deep-into-amazon-sagemaker-studio-notebook-architecture/)
- [Save costs by automatically shutting down idle resources within Amazon SageMaker Studio](https://aws.amazon.com/blogs/machine-learning/save-costs-by-automatically-shutting-down-idle-resources-within-amazon-sagemaker-studio/)