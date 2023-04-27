GCP - GENERAL  
  
Steps to configure GCP Repository  
  
1\] Open terminal and run following command to generate public and private key  
  
* ssh-keygen -t rsa -C "[[mailto:your-email-id@d10x.io|your-email-id@d10x.io]]"  
  
2\] Copy public key from ssh directory  
  
* cd ~/.ssh/  
* cat id\_[rsa.pub](http://rsa.pub)  
  
3\] Open following link and click register ssh key  
  
[**source.cloud.google.com/user/ssh\_keys?register=true**](http://source.cloud.google.com/user/ssh_keys?register=true)  
  
4\] Click Register SSH key. The Register SSH Key dialog opens.  
  
5\] In the Key name field, type a unique name for the key.  
  
6\] In the Key field, copy the key string from your public key file.  
  
7\] Click Register.  
  
Now you are ready to clone repository