https://registry.terraform.io/providers/hashicorp/aws/latest/docs#authentication-and-configuration



AWS Provider

Use the Amazon Web Services (AWS) provider to interact with the many resources supported by AWS. You must configure the provider with the proper credentials before you can use it.

Use the navigation to the left to read about the available resources.

To learn the basics of Terraform using this provider, follow the hands-on get started tutorials. Interact with AWS services, including Lambda, RDS, and IAM by following the AWS services tutorials.
Example Usage


Authentication and Configuration

Configuration for the AWS Provider can be derived from several sources, which are applied in the following order:

    Parameters in the provider configuration
    Environment variables
    Shared credentials files
    Shared configuration files
    Container credentials
    Instance profile credentials and region
