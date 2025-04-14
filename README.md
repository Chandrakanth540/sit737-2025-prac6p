```markdown
# 🚀 Node.js App Deployment with Docker, Kubernetes, and Minikube

This project demonstrates how to containerize a Node.js application, push it to Docker Hub, and deploy it using Kubernetes on a local Minikube cluster.

---

## 📦 Prerequisites

Make sure the following tools are installed on your machine:

- [Docker](https://www.docker.com/)
- [Node.js](https://nodejs.org/)
- [Minikube](https://minikube.sigs.k8s.io/docs/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/)

---

## 🛠️ Steps to Deploy

### 1️⃣ Build Docker Image

Build the Docker image from your app’s `Dockerfile`:

```bash
docker build -t chandrakanth00/node-app .
```

### 2️⃣ Login to Docker Hub

Authenticate with Docker Hub to push the image:

```bash
docker login
```

### 3️⃣ Push Image to Docker Hub

Push the tagged image to your Docker Hub repository:

```bash
docker push chandrakanth00/node-app
```

### 4️⃣ Start Minikube

Ensure Minikube is running:

```bash
minikube start
```

### 5️⃣ Deploy App to Kubernetes

Apply the Kubernetes deployment and service configuration:

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

### 6️⃣ Check Pod Status

Verify that your pods are running:

```bash
kubectl get pods
```

### 7️⃣ Access the Application

Use Minikube to expose and open the service in your browser:

```bash
minikube service node-app-service
```

This will open the Node.js app in your default web browser.

---

## 📁 File Structure

```
.
├── Dockerfile
├── deployment.yaml
├── service.yaml
└── README.md
```

---

## 📌 Notes

- Ensure your `deployment.yaml` references the correct Docker image (`chandrakanth00/node-app`).
- If using a different image name, update all references accordingly.
- You can scale your app using `kubectl scale deployment`.

---

## 🧑‍💻 Author

**Chandrakanth**  

---

## 📃 License

This project is free to use.
