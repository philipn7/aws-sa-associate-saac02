# IAM, Accounts and AWS Organizations
## Identity Policies
- Attached to AWS identities and either ALLOW or DENY access to AWS resources.
- By default, identities have no access (Implicit DENY)
- Priority of policies: **Explicit DENY always overrides Explicit ALLOW.** This rule carries over if the identity is part of multiple policies.
- Managed Policies: Apply to multiple identities. Single JSON file to modify.
- Inline: For specific accounts. Good for special/exceptional allow/deny.

## IAM Users
- IAM Users are an identity used for anything long-term AWS access. for: humans, applications, service accounts. "Something you can name."
- Principle: another way to say entity trying to access AWS
- ![](images/Pasted%20image%2020211020175557.png)
- Once authorized a principal becomes an 'authenticated identity'
- ![](images/Pasted%20image%2020211020175835.png)
- ![](images/Pasted%20image%2020211020180124.png)