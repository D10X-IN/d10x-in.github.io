
* **upgrade Ansible and python versions:**  
  
1. Check versions of Ansible core (version above-2.9)and python(version above-3.8).  
  
* **upgrade Ansible core:**  
  
1. python3 -m pip install --upgrade --user Ansible.  
2. check version: ansible --version  
  
* **For python version upgrade:**  
  
1. first check version: python --version  
2. At first configure the deadsnakes PPA to the machine: sudo add-apt-repository ppa:deadsnakes/ppa  
3. update the apt cache and install the latest Python  package: sudo apt update  
4. Install latest Python version: sudo apt install python  
5. When prompted, type **Y** to start the installation.  
6. Though Python will be installed, checking the installation with the command: python3 --version command will still return the old version. To fix this, Python 3 must be updated to point to Python: sudo update-alternatives --config python3.  
  
To check if the changes have taken effect, recheck the version of Python: python3 --version.  
  
* **Installing Ansible collections:**  
* To install an Ansible collection hosted in Galaxy: ansible-galaxy collection install google.cloud  
* **Note:** If you install a collection manually as described in this paragraph, the collection will not be upgraded automatically when you upgrade the `Ansible` package or `ansible-core`.