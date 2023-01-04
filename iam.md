# Identity and Access Management Service

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