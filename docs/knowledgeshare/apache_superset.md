Apache Superset is a modern, enterprise-ready business intelligence web application. It is fast, lightweight, intuitive, and loaded with options that make it easy for users of all skill sets to explore and visualize their data, from simple pie charts to highly detailed deck.gl geospatial charts.


[Documentation Link ](https://superset.apache.org/)

## Installing Superset from Scratch

### Python Virtual Environment

```
pip install virtualenv
python -m venv venv
source venv/bin/activate
```

### Installing and Initializing Superset

```
pip install apache-superset
superset fab create-admin 
superset db upgrade
superset init
superset run -p 8088 --with-thrds --reload --debugger
```