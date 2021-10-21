# IAM, Accounts and AWS Organizations
## Identity Policies
- Attached to AWS identities and either ALLOW or DENY access to AWS resources.
- By default, identities have no access (Implicit DENY)
- Priority of policies: **Explicit DENY always overrides Explicit ALLOW.** This rule carries over if the identity is part of multiple policies.
- Managed Policies: Apply to multiple identities. Single JSON file to modify.
- Inline: For specific accounts. Good for special/exceptional allow/deny.

## IAM Users
- IAM Users are an identity used for anything long-term AWS access. for: humans, applications, service accounts. "Some single thing you can name."
- Principle: another way to say entity trying to access AWS
- ![](images/Pasted%20image%2020211020175557.png)
- Once authorized a principal becomes an 'authenticated identity'
- ![](images/Pasted%20image%2020211020175835.png)
- ![](images/Pasted%20image%2020211020180124.png)

## IAM Groups
- IAM Groups are containers for Users. **You cannot log in as a group. No credentials.**
- Exam: There is **no native 'all users'** group.
- **No nesting** of groups
- **300 limit** per account, but can be increased
- **A resource policy cannot grant access to a group.** Can't reference them.
- Simply a container for users. Don't overestimate what it can do on the exam.

## IAM Roles
- 'one of the more difficult topics on identities'
- ![](images/Pasted%20image%2020211020193542.png)
- Assume role for short time.
- If you see 'sts:AssumeRole' you know roles are involved
- 'Trust policy' to authenticate -> Temp security credentials -> 'Permissions Policy'

### When to use Roles
- If you don't know how many principals there will be Roles are a good candidate
- 'Break glass' emergency. Emergency Role. Logged
- External accounts cannot directly access AWS services. Existing ID provides can assume a Role.
- > 5000 identities (IAM user limit)

## AWS Organizations
- For multiple AWS Accounts
- 'Management Account' can invite other accounts. (Standard -> Member Account)
- ![](images/Pasted%20image%2020211020200208.png)
- ![](images/Pasted%20image%2020211020200227.png)
- ![](images/Pasted%20image%2020211020201114.png)
- Use roles to assume the identity of other accounts.