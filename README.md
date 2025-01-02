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

![img](/Task_1/screenshots/1_1.png)
---

2. Add at least two users to the directory.

   1. Go to the Users Section:
      - In your new tenant, select Users in the left-hand menu.
   2. Add Users:
      - Click + New user.
      - For each user:
        - Select Create user.
        - Provide the following information:
          - Username (e.g., <user1@yourorg.onmicrosoft.com> and <user2@yourorg.onmicrosoft.com>).
          - Name (e.g., User 1, User 2).
          - Password: Auto-generate or provide one manually.
        - Save the user details.

![img](/Task_1/screenshots/1_2_1.png)
![img](/Task_1/screenshots/1_2_2.png)
![img](/Task_1/screenshots/1_2_3.png)
![img](/Task_1/screenshots/1_2_4.png)
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

![img](/Task_1/screenshots/1_3_1.png)
![img](/Task_1/screenshots/1_3_2.png)
![img](/Task_1/screenshots/1_3_3.png)
---

4. Assign the users to appropriate groups.

   1. Add Users to the Developers Group:
      - Go to the Groups section and select the Developers group.
      - Click Members, then + Add members.
      - Search for and select the appropriate user(s) (e.g., User 1).
      - Click Add.
   2. Add Users to the Admins Group:
      - Go to the Admins group and repeat the process to add the other user (e.g., User 2).

![img](/Task_1/screenshots/1_4_1.png)
![img](/Task_1/screenshots/1_4_2.png)
---

5. Assign the Global Reader role to the Admins group.

    - On the main screen go to Azure subscription
    - In the left-hand menu, go to Access control (IAM).
    - Click + Add assignments.
    - Search for apropriate role and select the Admins group.
    - Click Add.

![img](/Task_1/screenshots/1_5_1.png)
![img](/Task_1/screenshots/1_5_2.png)
![img](/Task_1/screenshots/1_5_3.png)
![img](/Task_1/screenshots/1_5_4.png)
![img](/Task_1/screenshots/1_5_5.png)
---

6. Assign the Application Developer role to the Developers group.

    - On the main screen go to Azure subscription
    - In the left-hand menu, go to Access control (IAM).
    - Click + Add assignments.
    - Search for apropriate role and select the Developers group.
    - Click Add.

![img](/Task_1/screenshots/1_6_1.png)
![img](/Task_1/screenshots/1_6_2.png)
![img](/Task_1/screenshots/1_6_3.png)
![img](/Task_1/screenshots/1_6_4.png)
![img](/Task_1/screenshots/1_6_5.png)
---

7. Verify that the role assignments function as expected for both groups.

   1. Test Admins Group:
      - Sign in with a user from the Admins group.
      - Navigate to the Azure Active Directory section and verify that they have read-only access to all resources.

   2. Test Developers Group:
      - Sign in with a user from the Developers group.
      - Attempt to register or manage applications to ensure the Application Developer role functions as expected.

![img]()
![img]()
---

## Practical Task 2: Enabling Single Sign-On (SSO) and Multi-Factor Authentication (MFA)

Configure Single Sign-On (SSO) and Multi-Factor Authentication (MFA) for users in a Microsoft Entra ID directory to enhance identity and access security.

1. Enable Single Sign-On (SSO) for your Microsoft Entra ID tenant.
2. Enforce Multi-Factor Authentication (MFA) for all users in the directory.
3. Configure conditional access policies to require MFA for high-risk sign-ins.
4. Verify that SSO and MFA settings are correctly applied for the users.
