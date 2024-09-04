# AWS Identity Policies

- Identity Policies are attached to AWS identities and either `ALLOW` or `DENY` access to AWS resources.
- IAM Policy Document
  - Statements
    - Sid
    - Effect
    - Action
    - Resource

## IAM Policy Document

- Allow access to all S3
- Deny access to `bucket_name` S3 bucket
- Analysis Order
  - Explicit Deny
  - Explicit Allow
  - Default Deny (Implicit)

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "FullAccess",
      "Effect": "Allow",
      "Action": ["s3:*"],
      "Resource": ["*"]
    },
    {
      "Sid": "DenyBucket",
      "Effect": "Deny",
      "Action": ["s3:*"],
      "Resource": ["arn:aws:s3:::bucket_name", "arn:aws:s3:::bucket_name/*"]
    }
  ]
}
```