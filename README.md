

# Node Hello Application Deployment Project

## Repo Structure

├── app <-- app files/directories and Dockerfile go here. Docker image already pushed to public Dockerhub registry.
├── k8s-manifest
│   └── microservice.yml <-- only this single file needed to deploy your microservice to Kubernetes.

Dockerhub registry path: https://hub.docker.com/r/rohanshinde08/node-hello
Docker Pull Command
```
docker pull rohanshinde08/node-hello
```
This repository contains the Kubernetes manifests inside 'k8s-manifest' directory to deploy the Node Hello application using a Deployment and Service.



## Prerequisites

Before deploying the application, ensure that you have the following:

- Docker Desktop or a running Kubernetes cluster
- kubectl command-line tool configured to access your cluster


## Commands

In this example, the Deployment and Service are defined as separate objects using --- to separate them.

To apply the combined YAML file and deploy the application, run the following command:

```
kubectl apply -f microservice.yml
```
This command will create both the Deployment and Service based on the definitions in the YAML file.

In this example, the type field is set to NodePort, and the nodePort field is set to 30000. This means that the service will be accessible on all nodes in the cluster on port 30000. Requests to any node on that port will be forwarded to the service.

## Verify the deployment:

```
kubectl get deployments
kubectl get pods
```
You can then access the application by opening http://localhost:30000 in your web browser.
It should return 'Hello Node!' in the output on the webpage.





