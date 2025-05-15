# Airflow project

## General information
Based on the Udemy course 'The Complete Hands-On Introduction to Apache Airflow' by Marc Lamberti
Useful link: https://www.udemy.com/course/the-complete-hands-on-course-to-master-apache-airflow/learn/lecture/32289376#content


## Project structure
<!-- You can describe the folders here later -->

## Installation & Usage

### Download Airflow Docker Files
- download and install docker from https://docs.docker.com/get-started/get-docker/
- download _docker compose file_ and store in your project 
  - https://airflow.apache.org/docs/apache-airflow/2.5.1/docker-compose.yaml
- create a new file _.env_ in your project, add the following lines
```
AIRFLOW_IMAGE_NAME=apache/airflow:2.8.1
AIRFLOW_UID=50000
AIRFLOW_PROJ_DIR=C:/path/to/your/project
```

### (Optional) Set Up a Python virtual environment

This is only needed when you're running Python scripts locally, not inside Docker.
```bash
# install and activate virtual environment
python -m venv sandbox
source sandbox/Lib/activate # in Windows

# install airflow
pip install --upgrade pip
pip install wheel apache-airflow
```
### Usage
1. Start Docker Desktop
2. Run Airflow services
```bash
docker compose up airflow-init # one-time initialization
docker compose up -d # start Airflow in the background
```
3. Open airflow in a browser - http://localhost:8080


### Stop and Clean Up
```bash
docker compose down # stop containers
docker compose down --volumes --remove-orphans # full cleanup
```