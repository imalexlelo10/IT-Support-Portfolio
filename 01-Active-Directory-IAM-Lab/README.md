# Active Directory IAM Lab

## Objective

Essentially, this lab simulated onboarding three employees into our Active Directory domain. We divided the employees into separate Organizational Units (OUs) for better administrative structure and management. We also created role-based security groups and assigned each employee to the appropriate group based on their job role, establishing the foundation for managing access through RBAC.

## Environment & Tools

- Oracle VirtualBox
- Windows Server 2025
- Active Directory Domain Services (AD DS)
- Active Directory Users and Computers (ADUC)
- DNS
- PowerShell / Command Line
- IPv4 Networking

## Scenario
As an IAM Administrator, I'm tasked with onboarding three new employees from different departments into the LeloTech Active Directory domain. Each employee must be placed into their designated Organizational Unit (OU) based on their department for better organization and administration. I must also assign each employee to the appropriate security group based on their job role, establishing a role-based structure that can later be used to manage access to company resources.

## What I Configured

1. Verified my authenticated identity, hostname, and Active Directory domain using PowerShell commands.

2. Created an Organizational Unit (OU) structure within the LeloTech domain to organize users based on their departments.

3. Provisioned three employee accounts using Active Directory Users and Computers (ADUC) and placed each employee into their designated departmental OU.

4. Configured each employee with a temporary password and required a password change at the next logon so the administrator-created credential would not remain the employee's permanent password.

5. Created Global Security Groups based on the employees' job roles.

6. Assigned each employee to their appropriate security group to establish the identity-to-role structure for Role-Based Access Control (RBAC).

7. Verified each employee's security group assignment through the **Member Of** section in ADUC.


## IAM Concepts Demonstrated

### Organizational Units (OUs)
Organizational Units help provide better organization and administration within Active Directory. In this lab, I created separate OUs for each department and organized employees into their designated OUs based on their department. The OUs were used for administrative organization rather than directly providing access to resources.

### Security Groups
Security groups provide a more organized and scalable way of managing access. Instead of assigning permissions individually to every employee, users can be assigned to security groups based on their job roles. This creates a role-based structure that can later be used to assign permissions to company resources.

### Role-Based Access Control (RBAC)
RBAC is an access-control model where permissions are assigned based on a user's role rather than individually to each user. In this lab, I established the identity-to-role portion of RBAC by creating security groups based on job roles and assigning each employee to their designated group. These groups can later be assigned permissions to specific company resources.

### Authentication vs. Authorization
Authentication verifies the identity of a user and answers the question, "Who are you?" Authorization determines what an authenticated user is permitted to access or perform. During this lab, I verified my authenticated identity before making administrative changes and established security group memberships that can later be used when authorizing access to resources.

### Joiner-Mover-Leaver (JML)
JML represents the identity lifecycle of a user within an organization. A Joiner is a new employee whose identity and required access must be provisioned. A Mover is an existing employee whose role or responsibilities have changed and may require their access to be modified. A Leaver is an employee leaving the organization whose access must be revoked or disabled according to the organization's offboarding procedures.

This lab demonstrated the **Joiner** process by provisioning three new employee identities, placing them into their appropriate departmental OUs, and assigning them to security groups based on their newly hired roles.


## Verification

I verified my configuration by navigating to each newly added user in Active Directory Users and Computers (ADUC) and reviewing the **Member Of** tab. Seeing the designated security group listed under each user's group memberships confirmed that each employee had been assigned to the correct role-based security group.

The following group memberships were verified:

- Jordan Smith (`jsmith`) → `GG_IT_Support`
- Maya Johnson (`mjohnson`) → `GG_HR_Specialists`
- Daniel Carter (`dcarter`) → `GG_Finance_Analysts`

This verification confirmed that the identity-to-role assignments were configured correctly. Resource-level permissions were not configured or tested during this lab.


## What I Learned

Before completing this lab, I did not fully understand the Joiner-Mover-Leaver (JML) identity lifecycle or some of the tools and concepts used to establish RBAC. I was already familiar with Organizational Units (OUs) and security groups, but I did not fully understand how useful they could be for organizing and managing identities within Active Directory.

After completing this lab, I have a better understanding of the purpose behind OUs and security groups. OUs provide a structured way to organize and administer identities within a domain, while security groups provide a scalable way to organize users based on their roles and eventually manage access through group membership rather than assigning permissions individually.

I also gained hands-on experience with the Joiner portion of the JML lifecycle by provisioning new employee identities and assigning them to the appropriate OUs and security groups. One of the biggest things that stood out to me was understanding how security groups can make access management more efficient while helping reduce permission-management mistakes and unnecessary access.

