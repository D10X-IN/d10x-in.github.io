**Steps for creating Wildcard certificate using let's encrypt**  
  
**Update Ubuntu**     
sudo apt update  
  
**Install certbot**     
sudo apt -y install certbot  
  
**Create a wildcard ssl certificate**     
sudo certbot certonly --manual     
Note : here we need to add an email address for expiration email and domain name, while adding domain name please add **\*.yourdomainname**  
  
**After that we need to create a txt record for our domain at our domain provider side (Godaddy, domain India etc)**  
  
**Verify the record is deployed or not**     
dig -t txt \_acme-challenge.{our-domainname}  
  
**Verify certificate**     
sudo certbot certificates  
  
Note : Certificate is only valid for 90 days.  
  
**Certificate renew command**     
sudo letsencrypt renew --dry-run --agree-tos  
  
**Certificate force renew command**     
sudo letsencrypt renew --force-renewal  
  
**Self signed certificate**  
  
[https://www.sslshopper.com/article-how-to-create-and-install-an-apache-self-signed-certificate.html](https://www.sslshopper.com/article-how-to-create-and-install-an-apache-self-signed-certificate.html)  
  
**Manual certificate renew command**  
  
sudo certbot certonly --manual    
  
then enter domain name like **\*.yourdomainname**  
  
**Nginx Restart**  
  
sudo systemctl restart nginx.service