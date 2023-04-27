
URL: https://cloud.google.com/storage/docs/discover-object-storage-gsutil#create  
  
Connect you instance to a cloud storage device          
\- gcloud init  
  
Create new bucket (must choose globally-unique name)          
\- gsutil mb -b on -l us-east1 gs://bucket\_name/  
  
If bucket name is already in use           
\- Creating gs://my-awesome-bucket/…          
  ServiceException: 409 Bucket my-awesome-bucket already exists.  
  
Copy files to bucket          
\- gsutil cp file\_location/file\_name gs://bucket\_name  
  
Downloading files from bucket          
\- gsutil cp gs://bucket\_name/file\_name file\_location/file\_name  
  
Give access to specific email address to read or write          
\- gsutil iam ch user:user\_name@gmail.com:objectCreator,objectViewer gs://bucket\_name  
  
To remove permission          
\- gsutil iam ch -d user:user\_name@gmail.com:objectCreator,objectViewer gs://bucket\_name  
  
Installing gsutil          
URL: https://cloud.google.com/storage/docs/gsutil\_install?hl=en#deb          
\- sudo apt-get install apt-transport-https ca-certificates gnupg  
  
gcloud auth login  
  
Copy file from VM to bucket  
  
gsutil ls -p d10x-cust-bucket  
  
Bucket mount command  
  
mount -t gcsfuse -o rw bucket\_name /full/path  
  
gcsfuse bucket\_name folder-path  
  
Check if bucket is mounted or not       
df -h  
  
gsutil cp /home/d10x\_customer/unovest/my\_bucket/test.txt gs://d10x-cust-bucket/test  
  
[https://devconnected.com/how-to-mount-and-unmount-drives-on-linux/](https://devconnected.com/how-to-mount-and-unmount-drives-on-linux/)  
  
d10x-cust-bucket /mnt/db\_backup gcsfuse rw,\_netdev,allow\_other,file\_mode=777,dir\_mode=777  
  
[https://stackoverflow.com/questions/27275063/gsutil-copy-returning-accessdeniedexception-403-insufficient-permission-from](https://stackoverflow.com/questions/27275063/gsutil-copy-returning-accessdeniedexception-403-insufficient-permission-from)