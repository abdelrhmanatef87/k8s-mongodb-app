
# 🐳 Kubernetes MongoDB + Mongo Express Deployment

This project demonstrates how to deploy a MongoDB database alongside the Mongo Express web-based MongoDB admin interface using Kubernetes. It includes secure credentials management and proper exposure of services.

## 📦 What’s Inside

### 🚀 Deploying MongoDB and Mongo Express:
- ✅ Created **MongoDB Deployment**
- ✅ Created **Secret** for MongoDB credentials
- ✅ Created **MongoDB Internal Service** (ClusterIP)
- ✅ Created **Mongo Express Deployment**
- ✅ Created **ConfigMap** for MongoDB connection settings
- ✅ Created **Mongo Express External Service** (NodePort)

## 🧠 Components Overview

| Component             | Type        | Purpose                                           |
|----------------------|-------------|---------------------------------------------------|
| `mongodb-deployment` | Deployment  | Runs the MongoDB database                         |
| `mongo-secret`       | Secret      | Stores MongoDB username and password              |
| `mongodb-service`    | ClusterIP   | Internal service to access MongoDB                |
| `mongo-express`      | Deployment  | Admin web interface for MongoDB                   |
| `mongo-config`       | ConfigMap   | Holds environment variable for DB connection URL  |
| `mongo-express-svc`  | NodePort    | Exposes Mongo Express to access via browser       |

## 🛠️ How to Deploy

1. Apply the Kubernetes manifests in order:
```bash
kubectl apply -f mongo-secret.yaml
kubectl apply -f mongodb-deployment.yaml
kubectl apply -f mongodb-service.yaml
kubectl apply -f mongo-configmap.yaml
kubectl apply -f mongo-express-deployment.yaml
kubectl apply -f mongo-express-service.yaml
