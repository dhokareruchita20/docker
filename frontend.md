# React Project Setup and Deployment Guide for Windows

This guide provides step-by-step instructions for setting up a React project.

## 1. Go to frontend 

```shell
cd Easycrud/frontend
```

## 2. edit .env file

To edit the .env file, run the following command:

```shell
nano .env
```
change ip address

## 3. Build docker image

To build the docker image, run:

```shell
docker build . -t frontend:v1
```
frontend:v1 is the name of an image

## 4. Create container from docker image

```shell
docker run -d -p 80:80 --name frontend frontend:v1
```
frontend is the name of container 

You can access the application on http://localhost:80
