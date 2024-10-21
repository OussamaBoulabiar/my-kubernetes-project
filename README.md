My Kubernetes Project
Overview
This project demonstrates the deployment of a multi-container application using Kubernetes. It consists of an Nginx web server and a MongoDB database, orchestrated within a Kubernetes cluster. The application is designed for scalability and reliability, showcasing best practices in container orchestration.

Features
Multi-Container Setup: Utilizes Nginx as a web server and MongoDB as a database, each running in separate containers.
Kubernetes Deployment: Managed using Kubernetes Deployment to ensure desired state management and easy scaling.
Service Exposure: Exposes the application using a NodePort service to allow external access.
Configuration Management: Environment variables are injected into containers using ConfigMaps and Secrets for sensitive information.
Architecture
Nginx: Serves static content and proxies requests to the backend.
MongoDB: Serves as the database, initialized with user credentials through Kubernetes Secrets.
Kubernetes Resources:
Pods
Deployments
Services
ConfigMaps
Secrets
Deployment Steps
Clone the repository:

bash
Copier le code
git clone https://github.com/your-username/my-kubernetes-project.git
cd my-kubernetes-project
Create the Kubernetes namespace:

bash
Copier le code
kubectl create namespace my-app-namespace
Apply ConfigMaps and Secrets:

bash
Copier le code
kubectl apply -f app-config.yaml
kubectl apply -f app-secret.yaml
Deploy the application:

bash
Copier le code
kubectl apply -f app-deployment.yaml
kubectl apply -f app-service.yaml
Access the application: Use minikube service app-service -n my-app-namespace --url to get the URL to access the application.

Scaling
The deployment can easily be scaled by modifying the replicas field in the app-deployment.yaml file:
yaml
Copier le code
spec:
  replicas: 4  # Adjust the number of replicas as needed
Cleanup
To remove all resources created by this project:

bash
Copier le code
kubectl delete namespace my-app-namespace
Conclusion
This project serves as a foundational example of deploying and managing a containerized application with Kubernetes. It highlights key concepts like multi-container deployments, configuration management, and scaling, making it a valuable learning resource for Kubernetes practitioners.
