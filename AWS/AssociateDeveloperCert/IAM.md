# IAM - Identity and Access Management

## Summary

Users: Mapped to a physical user, has a password for AWS console
Groups: Contains users only
Policies: Json document that outlines permissions for users or groupss
Roles: for EC2 instances or AWS services 
Security: MFA + Password Policy
AWS CLI: manage your was services in the command line
AWS SDK: manage your services using a programming language
Access Keys: access AWS using the CLI or SDK
Audit: IAM credential reports and IAM Access Advisor

## Best Practices

- Don’t use root account except for setup
- One physical user, create new users for others
- Create a strong password policy
- Use and Enforce the sue of MultiFactorAuthentication
- Create and use roles anytime you are giving perms to AWS services
- Use Access Keys for Programmatic Access (CLI/SDK)
- Audit permissions
- Never share IAM users and Access Keys

### Permissions

Users or groups can be assigned permissions using JSON documents called Policies
Policies define permissions fo the users. 

Policies are structured like so:
version - policy language version
Id - identifier for the policy
Statement
    - Sid - Identifier for Statement
    - Effect - Allow or Deny
    - Prinicipal - who this is applied to
    - Action - list of actions this policy allows or denies
    - Resource - list of resources to which the actions applied to 
    - Condition (optional) - Conditions for when this policy is in effect

### IAM Roles for services

Allow services to take actions as though it were a user
Common Roles: 
    - EC2
    - Lambda 
    - Cloudformation

### IAM Security Tools

- IAM Credentials Report (account-level)
    - Report that lists all your accounts users and the status of their various credentials
- IAM Access Advisor(user level)
    - Shows service permissions granted to a user and when those were last accessed
    - You can use this to revise policies

These can be found in IAM -> Credential Report and IAM -> Users -> Select User -> Access Advisor
