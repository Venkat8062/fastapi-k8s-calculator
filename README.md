# FastAPI Calculator on Kubernetes

This project demonstrates how to deploy a **Dockerized FastAPI application** on a **Kubernetes cluster** using **Minikube**.

The application image is built separately and reused here to focus purely on **Kubernetes orchestration concepts**.

---

## 🚀 What This Project Demonstrates

- Running containerized applications on Kubernetes
- Using **Deployments** for application lifecycle management
- Exposing applications using **Services (NodePort)**
- Local Kubernetes cluster using **Minikube**
- Clear separation between:
  - Application & Docker (build phase)
  - Kubernetes (runtime & orchestration phase)

---

## 🧱 Architecture Overview
```
Docker Image
↓
Kubernetes Deployment
↓
Kubernetes Pod
↓
Kubernetes Service (NodePort)
↓
Browser / Client
```
---

## 📦 Prerequisites

- Docker
- Minikube
- kubectl

---

## ▶️ Running the Project Locally

###  Start Minikube

```bash
minikube start --driver=docker
```
---

### Load the Docker Image into Minikube

The image was built in a separate Docker project and is reused here.
```
minikube image load fastapi-docker-calculator:1.0
```
---

### Deploy the Application
```
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
```
---

### Verify Pod Status
```
kubectl get pods
```
---

### Access the Application
```
minikube service fastapi-calculator-service

Available endpoints:

/health
/docs (Swagger UI)
```
---

### 📂 Project Structure
```
.
├── README.md
└── k8s
    ├── deployment.yaml
    └── service.yaml
```
---

### 🎯 Learning Outcomes

 -- Understood how Kubernetes replaces docker run
 -- Learned the role of Pods, Deployments, and Services
 -- Gained hands-on experience with real Kubernetes APIs
 -- Practiced production-style project organization
 -- Learned to debug Docker vs Kubernetes runtime confusion

### 🔮 Next Steps

 -- Add CI/CD pipeline using GitHub Actions
 -- Push images to a container registry
 -- Deploy the same manifests to managed Kubernetes (EKS)

### 👤 Author

**Venkatraman**
**Aspiring Cloud / DevOps Engineer**
