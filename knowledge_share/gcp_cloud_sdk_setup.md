**Install/Setup GCP Cloud SDK**   
IMPORTANT LINKS  
  
1. cloud.google.com/sdk/docs/install#deb  
2. https://cloud.google.com/compute/docs/instances/stop-start-instance  
  
1\] Add the Cloud SDK distribution URI as a package source   
echo "deb \[signed-by=/usr/share/keyrings/[cloud.google](http://cloud.google).gpg\] [packages.cloud.google.com/apt](https://packages.cloud.google.com/apt) cloud-sdk main" | sudo tee -a /etc/apt/sources.list.d/google-cloud-sdk.list  
  
2\] Make sure you have apt-transport-https installed   
sudo apt-get install apt-transport-https ca-certificates gnupg  
  
3\] Import the Google Cloud public key   
curl [packages.cloud.google.com/apt/doc/apt-key.gpg](https://packages.cloud.google.com/apt/doc/apt-key.gpg) | sudo apt-key --keyring /usr/share/keyrings/[cloud.google](http://cloud.google).gpg add -  
  
4\] Update and install the Cloud SDK   
sudo apt-get update && sudo apt-get install google-cloud-sdk  
  
5\] Run gcloud init to get started   
gcloud init  
  
**Important command**  
---------------------  
  
1\] Run the following command it will popup   
gcloud auth login  
  
2\] Command to check active user and active project name   
gcloud config configurations list  
  
3\] List all projects   
gcloud projects list  
  
4\] Set project   
gcloud config set project  
  
5\] Get a list of all instance available in the selected project   
gcloud compute instances list  
  
Stop Instance   
gcloud compute instances stop --zone=  
  
6\] Start Instnace   
gcloud compute instances start --zone=  
  
**IMPORTANT NOTE**   
Once you stop gcp instance and check the status from gcloud command of instance it will show you TERMINATED that means the instance is stoped.