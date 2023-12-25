Before you begin

1-
This procedure assumes familiarity with Docker and Docker Compose. If you haven’t worked with these tools before, you should take a moment to run through the Docker Quick Start (especially the section on Docker Compose) so you are familiar with how they work.

Follow these steps to install the necessary tools, if you have not already done so.

https://docs.docker.com/engine/install/

2-
Fetching docker-compose.yaml

To deploy Airflow on Docker Compose, you should fetch docker-compose.yaml.

With Console:

curl -LfO 'https://airflow.apache.org/docs/apache-airflow/2.8.0/docker-compose.yaml'

3-
Setting the right Airflow user

On Linux, the quick-start needs to know your host user id and needs to have group id set to 0. Otherwise the files created in dags, logs and plugins will be created with root user ownership. You have to make sure to configure them for the docker-compose:

With Console:

mkdir -p ./dags ./logs ./plugins ./config

echo -e "AIRFLOW_UID=$(id -u)" > .env

4-
Initialize the database

On all operating systems, you need to run database migrations and create the first user account. To do this, run.

With Console:

docker compose up airflow-init

5-
Running Airflow

Now you can start all services:

With Console:

docker compose up

And Finish :)

The account created has the login airflow and the password airflow.

The webserver is available at http://localhost:8080.

Running Airflow, Postgres and Redis programs.

You can do that:

https://airflow.apache.org/docs/apache-airflow/stable/howto/docker-compose/index.html

![EF8A5F25-9956-4FDE-B3BD-F0B9D5BE7DC6](https://github.com/azizhudai/airflow-docker/assets/24457063/0721f805-12c4-40af-9210-de6f5b3eea92)
