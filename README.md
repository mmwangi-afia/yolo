# YOLO E-Commerce Platform - Kubernetes Deployment

## Overview
A full-stack e-commerce application deployed on Google Kubernetes Engine (GKE), featuring a React frontend, Node.js backend, and MongoDB database with persistent storage.

## Live Application
🌐 **Access the app**: http://136.119.117.144

## Architecture
- **Frontend**: React app served by Nginx (2 replicas)
- **Backend**: Node.js API (2 replicas)
- **Database**: MongoDB StatefulSet with 5Gi persistent storage
- **Orchestration**: Kubernetes on GKE
- **Images**: Docker Hub (`muthoni880/yolo-client:v1.1`, `muthoni880/yolo-backend:1.0.0`)
Screenshot: `docs/dockerhub-backend.png`, `docs/dockerhub-client.png`

## Prerequisites
- kubectl configured
- Access to GKE cluster
- (For developers) Docker, Docker Hub account

## Deployment Instructions

### Deploy to Kubernetes:
```bash
# Create namespace and deploy all resources
kubectl apply -f k8s/

# Verify deployment
kubectl get all -n yolo-app

# Get service external IP
kubectl get svc frontend-service -n yolo-app
```