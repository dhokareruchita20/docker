# Backend Deployment Guide 

## Step 1: Install docker

1. Verify if docker is installed by running the following command:

   ```bash
   docker -version
   ```

If Java is not installed, install the docker.

```shell
apt update && apt install docker.io -y
```

## Step 2: clone the repository

```shell
git clone (repository url)
```
Go to EasyCRUD/backend

## Step 3: Build the Spring Boot Application
### Update DB credentials in application.properties:

```shell
cd backend
vim src/main/resources/application.properties
```
```sh
   server.port=8080
   spring.datasource.url=jdbc:mariadb://<DB_HOST>:3306/<DB_NAME>
   spring.datasource.username=<DB_USER>
   spring.datasource.password=<DB_PASS>
```

## Step 4: create docker image

```shell
docker build . -t backend:v1
```

## Step 5: create container from image 

```bash
docker run -d -p 8080:8080 --name backend backend:v1
```

The application will start and be accessible at:

http://localhost:8080

```shell
docker run -d -p 80:80 --name frontend frontend:v1
```
frontend is the name of container 

You can access the application on http://localhost:80
