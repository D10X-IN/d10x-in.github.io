AZURE - GENERAL REFERENCES  
==========================  
  
Add general information about Azure (tutorials, documentation links, etc) to this page.  
  
**Connect Azure VM from Ubuntu 18.04 system:**  
  
> **1\] Install remmina using following commands.**  
>  
> * snap install remmina  
>  
> * sudo snap connect remmina:avahi-observe :avahi-observe  
>  
> * sudo snap connect remmina:cups-control :cups-control  
>  
> * sudo snap connect remmina:mount-observe :mount-observe  
>  
> * sudo snap connect remmina:password-manager-service :password-manager-service  
>  
>  
> **2\] Open remmina**  
>  
> * Click on create new connection profile  
>  
> * From Protocol select RDP - Remote Desktop Protocol.  
>  
> * Server - Public IP  
>  
> * Username  
>  
> * Password  
>  
>  
> \*Note : You can get username and password in =>All Services => KeyVault => kv-amp-mgmt-bo - Secrets => vm-amp-bo-win01-password =>  
  
**\----------------------------------------------------------------------------------------------------------------------**  
  
**Connect Azure SQL from Ubuntu 18.04 System:**  
  
Link : https://www.sqlshack.com/sql-server-2019-on-linux-with-ubuntu-and-azure-data-studio/  
  
**1\] Install azure data studio using following commands**  
  
* Link to download azure data studio deb package - https://go.microsoft.com/fwlink/?linkid=2109254  
* cd Downloads  
* sudo dpkg -i azuredatastudio-linux-.deb  
* azuredatastudio  
  
**2\] Open Azure data studio**  
  
Go to connection details section  
  
Connection type : Microsoft SQL Server  
  
Server : Server Name  
  
Authentication Type :   
  
**\-----------------------------------------------------------------------------------------------------------------------**  
  
**Steps to create vm in azure**  
  
1. Login to your azure account portal.azure.com  
2. Go to Virtual Machine => Create a Virtual Machine  
3. In Basics section => Resource group \[Create new OR Select Existing \]  
4. Virtual machine name => d10x-windows-vm  
5. Region => Select region  
6. Availability options  
  
* * *  
  
**Steps add backup policy on azure vm**  
1\] Select Virtual Machine  
2\] Go to `Backup` section  
3\] You can create new policy or select existing \*Here we are going to see create new policy  
4\] Enter `resource name` \[You can keep this as default or give name\]  
5\] Select `resource group`  
6\] Choose backup policy \*By default it is having daily backu policy which is having retention period for 180 days we are going to edit it.  
7\] Click on `create or edit new policy`  
7.1\] Policy name  
7.2\] Backup schedule  
7.3\] Instant Restore  
7.4\] Retention range  
7.5\] OK  
8\] Enable