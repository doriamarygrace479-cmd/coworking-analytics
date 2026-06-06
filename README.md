
# Coworking Space Analytics Deployment

This project demonstrates the deployment of a coworking space analytics application using AWS and Kubernetes.

The application is containerized using Docker and pushed to Amazon Elastic Container Registry (ECR).  
Continuous Integration is implemented using AWS CodeBuild, which automatically builds and pushes updated Docker images whenever changes are made to the repository.

The deployment consists of two main components:
1. A PostgreSQL database deployed inside the Kubernetes cluster.
2. An analytics application that connects to the database and exposes API endpoints.

The EKS (Elastic Kubernetes Service) cluster is used to orchestrate and manage containerized services.  
The application and database are deployed using Kubernetes Deployment and Service YAML configurations.

Kubernetes ConfigMap is used to store non-sensitive environment variables such as database name, host, and port.  
Kubernetes Secret is used to securely store sensitive data like the database password.

The Docker image for the analytics application is built using a Python base image and installs dependencies from the `requirements.txt` file.

After building, the image is pushed to ECR and deployed to the Kubernetes cluster using `kubectl apply`.

The application is exposed via a Kubernetes Service, allowing external access through a LoadBalancer.

CloudWatch Container Insights is enabled to monitor logs and observe application health and activity.

This deployment demonstrates a full DevOps workflow including containerization, CI/CD, and Kubernetes orchestration.

Overall, the project showcases how to build, deploy, and manage a cloud-native application on AWS using modern DevOps practices.
trigger webhook build
