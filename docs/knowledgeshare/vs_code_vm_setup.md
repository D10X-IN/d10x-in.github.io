### SSH on windows
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


### Connecting to a Linux server SSH machine. (ideal for Rpi / Jetson Nano edge processors)

Steps to Set up Remote SSH (On Linux server machine) 
1. Client and server must be on same network. Check the local ip address of server using ifconfig. Or use arp-scan on client machine.
2. On server - Install OpenSSH server “sudo apt-get update” “sudo apt-get install openssh-server”. 
3. Enable SSH service “sudo service ssh start”. On server
4. Connect to SSH from client “ssh client_ip -l your_server_username” eg “ssh 192.168.1.100 -l snam1009”.  You will be now able to access the terminal of the server from the client.
5. For client and server not on the same machine, ngrok or localxpose can be used on the server to expose the local SSH port (usually 22). “./ngrok tcp 22” 
6. Download remote SSH vs code extension on client.
7. Press control + shift +p and select add new host. Add ip, username and password. user@hostname. Eg snam@192.168.29.100
8. Then connect to host using the extension. You can use remote SSH extension to browse files on server and access terminal from VS code


