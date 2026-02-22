# Event-Driven Python Microservices Platform on AWS EKS

This project demonstrates the deployment of a distributed, event-driven microservices architecture on AWS Elastic Kubernetes Service (EKS). The platform integrates multiple Python-based services with message queue communication, persistent databases and Kubernetes orchestration within a cloud-native environment.

The primary objective was to implement a scalable and reliable deployment architecture focusing on container orchestration, infrastructure management, and inter-service communication rather than application development.

---

## Architecture Overview

The platform consists of multiple microservices communicating asynchronously through RabbitMQ while maintaining persistent state in PostgreSQL and MongoDB databases.

Core components:

- Authentication Service
- API Gateway Service
- Media Converter Service
- Notification Service
- RabbitMQ Message Broker
- PostgreSQL Database
- MongoDB Database
- Kubernetes Cluster (AWS EKS)

---

## Key Objectives

- Deploy microservices in a Kubernetes environment
- Implement event-driven communication using message queues
- Manage persistent storage using cloud-native volumes
- Configure secure access and service routing
- Validate distributed system workflows
- Demonstrate DevOps collaboration with prebuilt container images

---

## Technology Stack

- AWS EKS
- Kubernetes
- Helm
- Docker
- RabbitMQ
- PostgreSQL
- MongoDB
- Python
- AWS IAM
- AWS EBS CSI Driver

---

## Infrastructure Setup

The Kubernetes cluster was provisioned using AWS EKS with managed node groups.

Key infrastructure configurations included:

- Cluster IAM role configuration
- Node group IAM roles
- Security group rules
- Persistent volume support using EBS CSI driver
- kubectl access configuration via AWS CLI

Cluster context configuration:

```bash
aws eks update-kubeconfig --name <cluster_name> --region <region>

Service Deployment
Databases

MongoDB and PostgreSQL were deployed using Helm charts with custom credentials and initialization scripts.

helm install mongo .
helm install postgres .

Message Queue

RabbitMQ was deployed via Helm and configured with required queues:

mp3

video

Microservices Deployment

Each microservice was deployed using Kubernetes manifests.

Services included:

Auth Service

Gateway Service

Converter Service

Notification Service

Deployment example:

kubectl apply -f .

Networking and Access

Ingress resources were configured to expose the gateway service externally.

Internal communication between services occurred through Kubernetes service discovery and RabbitMQ messaging.

Validation

Cluster status:

kubectl get all


API workflow validation:

Login
POST /login

Upload
POST /upload

Download
GET /download


Successful execution confirmed:

Authentication workflow

Message queue processing

Media conversion pipeline

Notification delivery

DevOps and Engineering Practices

This project reflects real-world DevOps collaboration patterns:

Prebuilt container images provided by development teams

Infrastructure and deployment handled independently

Configuration-driven deployment approach

Reproducible Kubernetes manifests

Cloud-native service orchestration

Lessons Learned

Managing inter-service dependencies in distributed systems

Kubernetes networking and service discovery

Stateful workloads on Kubernetes

Event-driven architecture reliability considerations

Infrastructure role separation between developers and platform engineers

Future Improvements

CI/CD automation pipeline for deployments

Infrastructure as Code using Terraform

Observability stack integration (Prometheus & Grafana)

Autoscaling policies

Secrets management improvements

Cleanup
To remove infrastructure:
Delete Kubernetes resources
Remove node groups
Delete EKS cluster

Author

James Chege
DevOps Engineer | Cloud Infrastructure | Kubernetes
