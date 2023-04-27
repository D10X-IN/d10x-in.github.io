Creating a NFS/SMB mount drive:  
  
Two parts create a SMB mount  
  
1\] Server  
Wther machine where the folder which needs to be shared  
And SMB/samba server service running  
  
Steps to set up samba server   
Refernece https://ubuntu.com/tutorials/install-and-configure-samba#2-installing-samba  
  
\>sudo apt update  
\>sudo apt install samba  
#check is it installed properly  
\> whereis samba  
  
#create server share folder configuration  
\> sudo nano /etc/samba/smb.conf  
\# at bottom of the file add   
\[\]  
   comment = Samba on Ubuntu  
   path = /path/of/folder/to/be/share  
   read only = no  
   browsable = yes  
  
\# Then press Ctrl-O to save and Ctrl-X to exit from the nano text editor  
  
\> sudo service smbd restart  
\> sudo ufw allow samba  
  
\# set samba user password  
sudo smbpasswd -a  
  
Client machine from where you wish to acess shared folder  
  
From client side you can connect to this shared folder using   
"Add a network location"   
This option is available in windows file explorer after rigth click  
In Ubuntu  
in File explorer(nautils)  
left panel + button can be used  
  
When prompted for location url  
On windows  
\\\\ip-address\\\[\]  
  
on ubuntu  
smb://ip-address/\[\]