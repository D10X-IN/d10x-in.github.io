Following process applies if Local System is Windows:  
  
**Prerequisites:**  
  
1. OpenSSH  
2. VSCode  
  
**Procedure:**  
  
1. Follow process on [https://code.visualstudio.com/docs/remote/troubleshooting](https://code.visualstudio.com/docs/remote/troubleshooting) and create ssh key with command:  
  
          ssh-keygen -t rsa -b 2048  
  
2\. Open VSCode > Remote Explorer > SSH Targets > Add New , use command :   
  
        ssh username@hostname @ -i /path/to/ssh/key   
  
3\. For any issue, visit [https://code.visualstudio.com/docs/remote/troubleshooting](https://code.visualstudio.com/docs/remote/troubleshooting)