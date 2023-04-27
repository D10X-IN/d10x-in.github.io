Apache superset installation steps  
  
**Run the below steps on command line**  
  
* sudo apt install python3.10-dev  
* pip install psycopg2-binary  
* pip install apache-superset  
* superset fab create-admin  
* superset db upgrade  
* superset init  
* superset run -p 8088 --with-thrds --reload --debugger