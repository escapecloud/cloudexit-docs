# AWS

This page explains how to authenticate cloudexit against AWS and what permissions are required.

**Authentication Methods**

cloudexit supports:
- **Access key / secret key** (interactive or config file)
- **AWS CLI profiles** (`--profile PROFILE`)

**Required Permissions**

To run an AWS assessment, the following AWS managed policies must be attached:

- **ViewOnlyAccess** [(AWS Docs)](https://docs.aws.amazon.com/aws-managed-policy/latest/reference/ViewOnlyAccess.html)
- **AWSBillingReadOnlyAccess** [(AWS Docs)](https://docs.aws.amazon.com/aws-managed-policy/latest/reference/AWSBillingReadOnlyAccess.html)

See also: [Required permissions](required-permissions.md)

**Run an assessment (AWS)**

***Interactive***

```bash
python3 main.py aws
```

cloudexit will prompt you for:
- Exit strategy
- Assessment type
- Access key
- Secret key
- Region

***Interactive with AWS Profile***

```bash
python3 main.py aws --profile default
```

cloudexit will use credentials from your local AWS CLI config.
[(AWS Docs)](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-quickstart.html)
