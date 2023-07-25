## Yolo Kubernetes deployment

The docker images are deployed on the dockerhub public repository.

Frontend - ekibet/yolo-k8s-frontend:1.0.2
Backend -  ekibet/yolo-k8s-backend:1.0.0


### Note:
```bash
Mongo db is using the mongo docker image. This is being configure on the deployment.yaml in the database folder
```


## Project Structure

We have the kubernetes deployment yamls files for the following:

1. Database 
    - deployment.yml:  For pushing the docker image and build the docker container in the kubernetes cluster
    - pvc.yml: For peristant volumes
    - secrets.yml: For storing the database secrets
    - service.yml: For exposing the database container to the external world through a LoadBalancer

2. Backend
    - deployment.yml:  For pushing the docker image and build the docker container in the kubernetes cluster
    - secrets.yml: For storing the backend secrets, in this case is the MONGOURI
    - service.yml: For exposing the backend container to the external world through a LoadBalancer

3. Frontend
    - deployment.yml:  For pushing the docker image and build the docker container in the kubernetes cluster
    - service.yml: For exposing the Frontend container to the external world through a LoadBalancer



## How to run the project:

Use below command followed by the .yml file you want to deploy

```bash

minikube apply -f <name of the docker yml file to deploy>

```