
URL: [https://cloud.google.com/architecture/chrome-desktop-remote-on-compute-engine#xfce](https://cloud.google.com/architecture/chrome-desktop-remote-on-compute-engine#xfce)  
  
```plaintext  
sudo apt update  
sudo apt install --assume-yes wget tasksel  
```  
  
```plaintext  
wget https://dl.google.com/linux/direct/chrome-remote-desktop_current_amd64.debsudo apt-get install --assume-yes ./chrome-remote-desktop_current_amd64.deb  
```  
  
Install Xfce desktop:  
  
```plaintext  
sudo DEBIAN_FRONTEND=noninteractive \&nbsp; &nbsp; apt install --assume-yes xfce4 desktop-base dbus-x11 xscreensaver  
```  
  
```plaintext  
sudo bash -c 'echo "exec /etc/X11/Xsession /usr/bin/xfce4-session" > /etc/chrome-remote-desktop-session'  
```  
  
```plaintext  
sudo apt install --assume-yes task-xfce-desktop  
```  
  
```plaintext  
sudo systemctl disable lightdm.service  
```  
  
```plaintext  
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.debsudo apt install --assume-yes ./google-chrome-stable_current_amd64.deb  
```  
  
URL: [https://remotedesktop.google.com/headless](https://remotedesktop.google.com/headless)   (To Download and install Chrome Remote Desktop)  
  
On the **Set up another computer** page, click **Begin**.  
  
Click **Authorize**.  
  
```plaintext  
sudo systemctl status chrome-remote-desktop@$USER  
```