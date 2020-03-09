---
layout: default
title: CLI
parent: AWS
nav_order: 1
---

# AWS CLI
{: .no_toc }

## SSM Parameter Store

Inserting a parameter into parameter store, using KMS for encryption.

```bash
aws ssm put-parameter --name "$PARAM_NAME" --type SecureString --value "$PARAM_VALUE" --key-id alias/$KMS_KEY_NAME --profle $AWS_PROFILE
```

Retreiving a parameter from parameter store, using the a key to decrypt as it's pulled, from the London region.

```bash
aws ssm get-parameter --name "$PARAM_NAME" --with-decryption --region eu-west-2 --output text --query 'Parameter.Value' --profile $AWS_PROFILE
```