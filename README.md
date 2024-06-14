# Microsoft Cloud Administration With Entra  ( Azure )
## Overview
Welcome to my home lab setup! "Dashershomelab" I've created this environment to learn and understand various aspects of networking, monitoring, prevention, administration, and hardening techniques. It's been an incredible learning experience, and I'm excited to share my setup with you.

### Microsoft Enterprise Mobility + Security 

<img align="center" src="assets/images/title.jpg" /><br/>

## Purpose
My home lab serves as a hands-on environment for:
- Learning networking concepts and technologies.
- Practicing monitoring, prevention, and administration techniques.
- integration of cloud services with on prem devices
<br> <br>
<!--# Home Lab Setup-->
- # Privileged Identity Management + Security

  
<b>This lab focuses on Privileged Identity Management + Security using Microsoft Entra and integral services</b><br>
<b>As we all know Azure AD has been renamed as Entra and Entra ID and throughout this lab ill be referring as Entra ID.<br>

### Goal in this lab is to:
- Understand Microsoft Cloud Administration
- Microsoft Entra ID – (Azure AD)
- Microsoft Privileged Identity Management (PIM)

### prerequisites for this lab:

- Azure account and Subscription
- EMS + E3 (Enterprise Mobility and Security) Licence
- windows 10 or later PC managed by Intune / Entra

### create Azure account

- Create an Azure Account
- Open https://Portal.azure.com  and create an account.
- Follow the instructions and register. You will get access to Azure portal with $200 credit for one month.
- Once logged in with your Microsoft login credentials you will find the Azure Home page.
- Click on the subscription and you will find the details.
- you can also find cost analysis of the services and resources.
- You can click on the Microsoft Entra ID, and it will take you to the Entra ID admin Centre.
- Now to manage devices and users we need to buy a license.
- These licenses can be purchased from either Entra admin center or Microsoft 365 Admin center.
- You need to be the domain admin to purchase the license.
- You can go to the M365 Admin center by typing  https://Admin.microsoft.com
- Once you open the M65 amin center home page, navigate to Billing on the left menu and you will see the purchase licenses menu. Click on that and you can purchase required licenses.
- The one license we need id the EMS (Enterprise Mobility and Security) + E3 license.
- Once you purchase the license you will be able to use it by assigning it to a user.
- There are two Variants EMS + E3 and EMS + E5 (I am using EMS + E3 Trial version ). 
- The differences between E3 and E5 apart form the cost are:
 
| EMS + E3                       | EMS + E5                        |
| :--:                           | :--:                            |
|Identity and access management  |	Identity and access management |
|Endpoint management             |	Endpoint management            |
|Defender for Identity           |	Defender for Identity          |
|                                | 	Defender for Cloud and Apps Identity|

 
The products included in the license are:
1. Products
2. Microsoft Entra ID
Microsoft Intune (Microsoft endpoint manager)
3. Compliance admin console
4. Defender for cloud
5. Defender for Identity
6. Purview Information Protection
7. Privileged Identity management (PIM).
8. Secure Score
 
### Microsoft 365 admin center<br>
You can enter by typing: https://admin.microsoft.com

- When you first create an account with Microsoft Azure or M365 console an Entra ID is provisioned.
  - Entra ID as we know is the new name for Azure AD. So, from now on I’ll be referring to Azure and Azure AD as Entra and Entra ID respectively.
- Entra Id provides the following features.
- Secure Identity Management
	- All other EMS products are reliant upon proper setup of Entra ID.
	-  Automatically creates a database with all types of users when Azure AD and M365 accounts are created. 
- Enhanced Cloud Security
	- It provides a enhanced cloud security to keep all users safe from hackers.
- Single Sign On (SSO)
	- For members signed into a computer as a member of a Domain or Entra ID, it automatically signs you into office 365 apps including outlook.
- Multifactor Authentication (MFA)
	- Users can be assigned with MFA (Multi Factor Authentication), which can be something you have, something you are and something you know. Common are mobile and fingerprints and face identification.
- Identity protection
	- This protects the user’s identity from being stolen.
- Role Based Access Control (RBAC)
	- The RBAC allows admins to set up junior administrators with various roles based on necessity and this avoids a global admin or admin with higher privileges active on the network. This is one of the best practices and provides only users and admins with least privilege active, providing additional security.<br>
 
By having a single place to authenticate we can automatically be able to use web services and mobile applications on our mobile devices or clients PCs, devices with multiple different operating systems.
