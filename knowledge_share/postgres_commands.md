**Installation steps**  
  
sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb\_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'         
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -         
sudo apt-get update         
sudo apt-get -y install postgresql-13  
  
Download link : [https://www.postgresql.org/download/](https://www.postgresql.org/download/)  
  
**How to created database and user with all privileges**  
  
CREATE DATABASE **DATABASE\_NAME**;  
  
CREATE USER **USERNAME** WITH PASSWORD **'PASSWORD'**;  
  
ALTER ROLE **USERNAME** SET client\_encoding TO 'utf8';         
ALTER ROLE **USERNAME** SET default\_transaction\_isolation TO 'read committed';         
ALTER ROLE **USERNAME** SET timezone TO 'UTC';  
  
GRANT ALL PRIVILEGES ON DATABASE **DATABASE\_NAME** TO **USER\_NAME**;  
  
**Granting permission for public schema**  
  
1. connect to database  
2. execute GRANT ALL ON SCHEMA **public** TO **USERNAME**;  
  
* Start the PostgreSQL server  
  
sudo service postgresql start  
  
* Stop the PostgreSQL server:  
  
sudo service postgresql stop  
  
**WAL File Configurations**         
wal\_level = replica   # minimal, replica, or logical # (change requires restart)  
  
synchronous\_commit = on  # synchronization level;    # off, local, remote\_write, remote\_apply, or on  
  
\# The archive\_mode must be set to on for archiving to happen.         
archive\_mode = on  
  
\# Ensure there is at least one WAL file for each "archive\_timeout" duration.         
archive\_timeout = 1h  
  
\# Copy to Google Cloud bucket         
archive\_command = 'gsutil cp %p gs://unovest-production/%f'  
  
#Copy to local directory         
archive\_command = 'cp %p /home/unovest/archive\_wal/%f'  
  
**PostgreSQL service commands**  
  
sudo service postgresql restart          
sudo service postgresql start         
sudo service postgresql status  
  
**How to get PostgreSQL database backup**  
  
PGPASSWORD="**USER\_PASSWORD**" pg\_dump -U **USER\_NAME** -h localhost **DATABASE\_NAME** > **OUTPUT\_FILE\_NAME.sql**  
  
**Database Restore Command**  
  
psql -U **UserName** -h localhost -d **DatabaseName** < **SqlFilePath**  
  
**How to enable pg\_stat\_statements**  
  
open 'postgresql.conf',  usually located in  **/etc/postgresql/(postgres version)/main/**  in a text editor (you might need to use sudo)  
  
locate the  'shared\_preload\_libraries' attribute  
  
uncomment that line and add 'pg\_stat\_statements' after the '=' sign, append the list if there already exist any entries  
  
connect to the postgres database on which you want to enable it (sudo -u  **username**  psql  **dbname**)  
  
run the command "CREATE EXTENSION pg\_stat\_statements;" (only required for the first time)  
  
References: 1. https://www.postgresql.org/docs/current/pgstatstatements.html  
  
1. [https://pganalyze.com/docs/install/01\_enabling\_pg\_stat\_statement](https://pganalyze.com/docs/install/01_enabling_pg_stat_statement)  
  
Upgrading Postgres from 13.8 to 14.05  
  
https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-14-04  
  
1. `sudo apt-get update`  
2. `sudo apt-get install postgresql postgresql-contrib`  
3. `sudo -i -u postgres`  
  
`**Restore .tgz** backup`\[Does not work\]  
  
`pg_restore -d database_name -U username -C backup.dump`  
  
Restore .tgz backup file created in backup\_db command:  
  
pg\_restore --no-owner --dbname=postgresql://{user}:{password}@{host}:{port}/{db\_name} -v {file\_path}