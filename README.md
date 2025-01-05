# Azure Identity and Access Management tasks

## Practical Task 1: Introduction to Microsoft Entra ID

Create a basic Microsoft Entra ID setup for an organization to manage identity and access.

1. Create a new Microsoft Entra ID tenant.

    1. Sign in to the Microsoft Entra Admin Center:

       - Go to the Microsoft Entra Admin Center.
       - Use your Microsoft account credentials to log in.
    2. Create a New Tenant:

       - In the left-hand menu, select Azure Active Directory.
       - Click on Manage tenants (or Switch tenants).
       - In the top menu, click + Create.
       - Select Azure Active Directory as the tenant type and click Next.
       - Enter the following:
         - Organization name.
         - Initial domain name (e.g., yourorg.onmicrosoft.com).
         - Select a region.
       - Click Review + Create, and then Create.
    3. Switch to Your New Tenant:

       - Once the tenant is created, go back to Manage tenants, select your new tenant, and click Switch.

![img](/screenshots/1_1.png)
---

2. Add at least two users to the directory.

   1. Go to the Users Section:
      - In your new tenant, select Users in the left-hand menu.
   2. Add Users:
      - Click + New user.
      - For each user:
        - Select Create user.
        - Provide the following information:
          - Username (e.g., <user1@yourorg.onmicrosoft.com> and <user2@yourorgonmicrosoft.com>).
          - Name (e.g., User 1, User 2).
          - Password: Auto-generate or provide one manually.
        - Save the user details.

![img](/screenshots/1_2_1.png)
![img](/screenshots/1_2_2.png)
![img](/screenshots/1_2_3.png)
![img](/screenshots/1_2_4.png)
---

3. Create two groups named Developers and Admins.

   1. Navigate to Groups:
      - In the left-hand menu, select Groups.
   2. Create the Developers Group:
      - Click + New group.
      - Choose Security as the group type.
      - Provide the following:
        - Group name: Developers.
        - Group description: Optional.
      - Click Create.
  
   3. Create the Admins Group:
      - Repeat the process to create a second group named Admins.

![img](/screenshots/1_3_1.png)
![img](/screenshots/1_3_2.png)
![img](/screenshots/1_3_3.png)
---

4. Assign the users to appropriate groups.

   1. Add Users to the Developers Group:
      - Go to the Groups section and select the Developers group.
      - Click Members, then + Add members.
      - Search for and select the appropriate user(s) (e.g., User 1).
      - Click Add.
   2. Add Users to the Admins Group:
      - Go to the Admins group and repeat the process to add the other user (e.g., User 2).

![img](/screenshots/1_4_1.png)
![img](/screenshots/1_4_2.png)
---

5. Assign the Global Reader role to the Admins group.

    - On the main screen go to Azure subscription
    - In the left-hand menu, go to Access control (IAM).
    - Click + Add assignments.
    - Search for an appropriate role and select the Admins group.
    - Click Add.

![img](/screenshots/1_5_1.png)
![img](/screenshots/1_5_2.png)
![img](/screenshots/1_5_3.png)
![img](/screenshots/1_5_4.png)
![img](/screenshots/1_5_5.png)
---

6. Assign the Application Developer role to the Developers group.

    - On the main screen go to Azure subscription
    - In the left-hand menu, go to Access control (IAM).
    - Click + Add assignments.
    - Search for appropriate roles and select the Developers group.
    - Click Add.

![img](/screenshots/1_6_1.png)
![img](/screenshots/1_6_2.png)
![img](/screenshots/1_6_3.png)
![img](/screenshots/1_6_4.png)
![img](/screenshots/1_6_5.png)
---

7. Verify that the role assignments function as expected for both groups.

   1. Test Admins Group:
      - Sign in with a user from the Admins group.
      - Navigate to the Azure Active Directory section and verify that they have read-only access to all resources.

![img](/screenshots/1_7_1.png)
![img](/screenshots/1_7_2.png)

   2. Test Developers Group:
      - Sign in with a user from the Developers group.
      - Attempt to register or manage applications to ensure the Application Developer role functions as expected.

![img](/screenshots/1_7_3.png)
![img](/screenshots/1_7_4.png)
---

## Practical Task 2: Enabling Single Sign-On (SSO) and Multi-Factor Authentication (MFA)

Configure Single Sign-On (SSO) and Multi-Factor Authentication (MFA) for users in a Microsoft Entra ID directory to enhance identity and access security.

1. Enable Single Sign-On (SSO) for your Microsoft Entra ID tenant.

---

2. Enforce Multi-Factor Authentication (MFA) for all users in the directory.
   - MFA enhances security by requiring a second form of authentication.
     - Enable Security Defaults:
       - Go to Microsoft Entra ID in the admin center.
       - Under Properties, click Manage security defaults.
       - Toggle Enable security defaults to Enabled. This enforces MFA for all users without advanced configuration.

![img](/screenshots/2_2_1.png)
---

3. Configure conditional access policies to require MFA for high-risk sign-ins.
   - Sign in to the Microsoft Entra admin center as at least a Conditional Access Administrator.
   - Browse to Protection > Conditional Access.
   - Select New policy.
     - Give your policy a name. We recommend that organizations create a meaningful standard for the names of their policies.
     - Under Assignments, select Users or workload identities.
     - Under Include, select All users.
     - Under Exclude, select Users and groups and choose your organization's emergency access or break-glass accounts.
     - Select Done.
     - Under Cloud apps or actions > Include, select All resources (formerly 'All cloud apps').
     - Under Conditions > Sign-in risk, set Configure to Yes.
     - Under Select the sign-in risk level this policy will apply to, select High and Medium. This guidance is based on Microsoft recommendations and might be different for each organization
     - Select Done.
     - Under Access controls > Grant, select Grant access.
     - Select Require authentication strength, then select the built-in Multifactor authentication authentication strength from the list.
     - Select Select.
     - Under Session.
     - Select Sign-in frequency.
     - Ensure Every time is selected.
     - Select Select.
     - Confirm your settings and set Enable policy to Report-only.
   - Select Create to create to enable your policy.
![img](/screenshots/2_3_1.png)
![img](/screenshots/2_3_2.png)
![img](/screenshots/2_3_3.png)
---

4. Verify that SSO and MFA settings are correctly applied for the users.
![img](/screenshots/2_4_1.png)
---

## Practical Task 3: Implementing Role-Based Access Control (RBAC)

Implement Role-Based Access Control (RBAC) in Azure to manage access to resources based on roles and ensure fine-grained access management.

   1. Create a custom role named Resource Viewer with read-only permissions for a specific resource group.
   2. Assign the Resource Viewer role to the Developers group created earlier.
   3. Assign the built-in Contributor role to the Admins group for the same resource group.
   4. Verify that members of the Developers group have only read access and members of the Admins group have full access to the resource group.

## Practical Task 4: Securing Sensitive Information with Azure Key Vault

Set up Azure Key Vault to securely store and manage sensitive information such as keys, secrets, and certificates.

   1. Create a new Azure Key Vault in your subscription.
   2. Add a secret to the Key Vault (e.g., a database connection string).
   3. Set access policies to grant the Application Developer role (assigned to the Developers group) permission to retrieve secrets from the Key Vault.
   4. Verify that only members of the Developers group can access the stored secret.

## Practical Task 5: Creating and Assigning Basic Azure Policies

Define and assign Azure Policies to enforce compliance with organizational standards for resource management.

   1. Create an Azure Policy to enforce tagging for all newly created resources with a specific tag (e.g., Environment: Development).
   2. Assign the policy to a resource group.
   3. Verify that any new resource created in the resource group without the required tag is marked as non-compliant.
   4. Review and document the compliance status of the resource group.

## Practical Task 6: Using Policy Effects to Enforce Compliance

Configure Azure Policies with different policy effects to enforce compliance and manage resources according to organizational standards.

   1. Create a policy with the Audit effect to monitor and log untagged resources within a resource
group.
   2. Create a policy with the DeployIfNotExists effect to automatically add a specific tag (Owner: IT) to any newly created resource.
   3. Assign these policies to a resource group and verify their behavior by:
      - Creating a resource without a tag and checking the compliance logs.
      - Creating a resource to validate the automatic tag deployment.