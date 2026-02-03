# YOLO E-Commerce Platform - Kubernetes Deployment

## Overview
A full-stack e-commerce application deployed on Google Kubernetes Engine (GKE), featuring a React frontend, Node.js backend, and MongoDB database with persistent storage.

### GKE Cluster
The application is deployed on Google Kubernetes Engine.
- **Cluster name**: studious-set-485019-j9
- **Region**: us-central1

### Kubernetes Context
kubectl is configured to communicate with the GKE cluster.

![See the provided screenshot](/k8s/screenshots/image.png)

## Live Application
The application is exposed using a Kubernetes LoadBalancer service.
**Access the app**: http://136.119.117.144
![See the provided screenshot](/k8s/screenshots/image1.png)

## Architecture
- **Frontend**: React app served by Nginx (2 replicas)
- **Backend**: Node.js API (2 replicas)
- **Database**: MongoDB StatefulSet with 5Gi persistent storage
- **Orchestration**: Kubernetes on GKE
- **Images**: Docker Hub (`muthoni880/yolo-client:v1.1`, `muthoni880/yolo-backend:1.0.0`)
Screenshot for the dockerhub images: `docs/dockerhub-backend.png`, `docs/dockerhub-client.png`

## Prerequisites
- kubectl configured
- Access to GKE cluster
- (For developers) Docker, Docker Hub account

## Deployment Instructions
The application is deployed in the `yolo-app` namespace, which is defined in `k8s/namespace.yaml`.

### Deploy to Kubernetes:
```bash
# Create namespace and deploy all resources
kubectl apply -f k8s/

# Verify deployment
kubectl get all -n yolo-app

# Get service external IP
kubectl get svc frontend-service -n yolo-app
```

