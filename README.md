# Docker and Docker-compose Exercise

## Create Dockerfile

image: tiangolo/uwsgi-nginx-flask:python3.6
sources:
    - dependencies file: requirements.txt
    - code folder: app
install dependencies: pip install -r ./requirements.txt --no-cache-dir
environment variables: FLASK_APP=app.py
execute app: flask db upgrade && flask run -h 0.0.0.0 -p 5000

## Create Docker-compose

The app needs a postgres (version 10) database. The app need the next environment variables to connect to the database:

- DBHOST  -> Database host
- DBPASS  -> Database password
- DBUSER  -> Database user
- DBNAME  -> Database name