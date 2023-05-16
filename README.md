
![container-banner](https://github.com/ron8cr/node-hello/assets/124076577/31c3f11d-33b4-4532-92be-0cae4e9b6ce8)

# Node Hello Application Deployment Project

## Repo Structure
![Screen Shot 2023-05-16 at 4 26 15 PM](https://github.com/ron8cr/node-hello/assets/124076577/57d063d6-6f32-4ecc-b9ef-aec5ea5fbe24)

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





