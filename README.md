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

- Once the licenses are applied it will take a few minutes up to 30 minutes to complete licensing the user.
- To view all the available admin center’s for the selected user with a proper license click on the all-admin centres on the left side menu

### Active Directory Synchronisation To Entra ID
Since we all have a windows server on premises with Active Directory services running, it is important and more practical to sync our Active Directory to the Microsoft Entra ID. Microsoft has allowed this possible by providing a synchronisation tool. This tool syncs all users on prem and in the Cloud. Keep in mind that the built in users on Active Directory are not synced.
I have my Active Directory services running on my windows server 2022. Since I created this server for a previous lab and the domain name is referring to a local domain (AD.DASHERSWINLAB.local), I may have some sort of issues syncing because of two different domain names. So, I have to perform some additional steps, which is a good learning process as it is possible to have different domain names in reality. Microsoft also has acknowledged this and provided some options, which you will see below.

To make this happen follow the steps below.

- Go to Microsoft download centre and download the Entra connect tool.(it’s still called Azure AD connect)
https://download.microsoft.com/download/B/0/0/B00291D0-5A83-4DE7-86F5-980BC00DE05A/AzureADConnect.msi

- Then run the tool in your Windows server and install the tool.
- Agree to the terms and install it.
- After installation run the tool.

- You can use customize option or Express settings. I’ll use the express settings.

- It asks you to login with Entra ID global admin account.
- So Login with your Entra ID admin credentials.

- My account is setup with MFA so it will ask me for Microsoft credentials

- Once entered it will then ask for the approval from authenticator app.
- Go to the authenticator app on the phone and key in the number and say yes.
- After verification it will then allow the sign in to continue.

- Now it asks you to login to the Active Directory domain administrator credentials.
- Once you enter and press next it will continue to configure.

- Check the box which says start synchronisation when configuration completes.

- It presents with a warning about the UPN Domain suffix not matching the Entra ID domain suffix.
- Its right because my on prem domain is a local one (AD.DASHERSWINLAB.local) it has to be (“XX.com”).

- So, to fix this I can either enter a Domain I own, which I don’t, or you can add the suffix.com to the domain. 
- So ill open the Active Directory Domains and Trust menu on my server.
- This provides me an option to add alternate UPN Suffixes. 
- I’ll go ahead and add “dasherswinlab.com” and “securedasher.onmicrosoft.com” to the list.
- Also ill make sure the on prem users have the Alternate domains connected.

- I’ll continue the installation of the connect tool and it and the warning slightly changes, and it gives me an option to continue without matching all UPN suffixes to verified domains.

- Check the box and hit next and it will complete the configuration of Entra connect tool.
- Now it completes the configuration successfully and asks you to verify the user accounts.

- The Microsoft Entra Connect website has been updated recently, below is the older version with the link to the new Microsoft Entra Connect link. Click on it and it should take you to the new website.

