---
layout: default
title: CLI
parent: AWS
nav_order: 1
---

# AWS CLI
{: .no_toc }

## SSM Parameter Store

**Inserting a parameter into parameter store**  
_Using KMS for encryption_

```bash
aws ssm put-parameter --name "$PARAM_NAME" --type SecureString --value "$PARAM_VALUE" --key-id alias/$KMS_KEY_NAME --profle $AWS_PROFILE
```

**Retreiving a parameter from parameter store**  
_Decrypts from KMS, in the London region_

```bash
aws ssm get-parameter --name "$PARAM_NAME" --with-decryption --region eu-west-2 --output text --query 'Parameter.Value' --profile $AWS_PROFILE
```