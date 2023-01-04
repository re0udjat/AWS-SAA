# Identity and Access Management Service

## IAM Policy Structure

Identity-based policy structure:

```json
{
    "Statement": [{
        "Effect": "effect",
        "Action": "action",
        "Resource": "arn",
        "Condition": {
            "condition": {
                "key": "value"
            }
        }
    }]
}
```

An IAM policy is a JSON document that consists of one or more statements:

- **Effect:** Can be *Allow* or *Deny*.
- **Action:** The specific API action for which you are granting or denying permission.
- **Resource:** Specifies the resource that's affected by the action.
- **Condition:** (Optional) Can be used to control when your policy is in effect.

Resource-based policy structure:

```json
{
    "Version": "2012-10-17",
    "Id": "ExamplePolicy",
    "Statement": [{
        "Sid": "ExampleStatement",
        "Effect": "Allow",
        "Principal": {
            "AWS": "*"
        },
        "Action": [
            "elasticfilesystem:ClientRootAccess",
            "elasticfilesystem:ClientMount",
            "elasticfilesystem:ClientWrite"
        ],
        "Condition": {
            "Bool": {
                "aws:SecureTransport": "true"
            }
        }
    }]
}
```

An IAM policy is a resource-based policy if we define *Principal* in that policy.

## IAM Best Practices

Best practices for IAM services:

- Lock away access keys of AWS account root user.
- Create individual IAM users and login with that user instead of root user.
- Use groups to assign permissions to IAM users in that groups instead of each IAM user.
- Do not give people more access rights than they need to do their job (i.e. least privilege).
- Create your own policies (i.e. customer managed policies) instead of inline policies.
- Audit the permissions that are assigned to all of your users and other principals in your account regularly.
- Enforce a password policy within IAM and that enables you to make sure that users have complex passwords that are difficult to guess.
- Enable MFA.
- Use roles for applications that run on AWS EC2 instances rather than having access keys hard-coded into the codes because it is a security risk.
- Use roles to delegate permissions.
- Do not share access keys.
- Change your passwords, renew your access keys regularly.
- Remove unnecessary credentials.
- Use policy conditions for extra security.
- Always monitor, try and know what is going on so that if there is any suspicious activity, you can identify it and act upon it.