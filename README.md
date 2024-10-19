# assignment- EKs 

This assignment requires setting up a three-tier architecture on AWS EKS using Terraform. Here's an overview:

# Introduction
This project will involve creating a highly available, secure, and scalable 3-tier architecture on AWS using EKS, RDS, Terraform, and several AWS services. The architecture consists of:

Presentation/Web Tier: Frontend applications hosted on EKS (Elastic Kubernetes Service).
Application Tier: Backend services also running on EKS.
Database Tier: Using RDS (Relational Database Service) with MySQL.
We'll use Terraform to automate infrastructure provisioning, while S3 and DynamoDB ensure consistency and state locking.


# VPC Setup:
Create a VPC with public, private, and database subnets.
Configure NAT gateways, internet gateways, and security groups.
Tag subnets for proper integration with EKS ingress.
RDS Deployment:

Set up a MySQL RDS instance in the database subnet with encryption and secure access.

# EKS Cluster:
Deploy an EKS cluster with worker nodes using the EKS module.
Configure cluster add-ons and manage the node group.

# IAM and Policies:
Create policies for Load Balancer and Cluster Autoscaler IAM roles.
Assign proper trust relationships and service accounts.
ALB & Ingress Controller:

Use ALB for routing traffic via an ingress controller.
Ensure SSL/TLS termination and domain-based routing.
Route 53 & Certificates:

Set up a hosted zone and an SSL certificate for your domain, securing ALB traffic.

# Kubernetes Deployment:
Deploy applications via Kubernetes manifests and services.
Include environmental variables for database connections and autoscaling.
Secrets Management:

Use Kubernetes Secrets to manage sensitive information (e.g., database credentials).
The setup focuses on modularizing infrastructure with Terraform, ensuring high availability, security, and scalability.


For the Docker CI/CD pipeline with monitoring, here's an overview:

# Docker
Create Dockerfiles for your application services.
Use Docker Compose (for local development) and Kubernetes for orchestration in production.

# CI/CD Pipeline:
Use tools like Jenkins, GitLab CI, or GitHub Actions for the pipeline.
Build stage: Automate building Docker images from the Dockerfile.
Test stage: Run unit, integration, and end-to-end tests.
Push stage: After tests pass, push Docker images to a container registry like Docker Hub or AWS ECR.
Deploy stage: Use Kubernetes manifests to deploy images to an EKS cluster.
Automated rollback: Integrate failure detection and automatic rollbacks for failed deployments.
Monitoring Setup:

# Prometheus
Use Prometheus to scrape metrics from Kubernetes pods and monitor resource usage like CPU, memory, and network traffic.

# Grafana
Visualize the metrics collected by Prometheus on dashboards, providing insights into your application's performance and infrastructure.

# ELK Stack
Use Elasticsearch, Logstash, and Kibana to centralize and analyze logs from your Docker containers and Kubernetes cluster.

# Alerting
Set up alerts in Prometheus or Grafana to trigger notifications via Slack or email for abnormal behaviors (e.g., high CPU, memory leaks, pod failures).
This pipeline automates Docker image builds, testing, and deployments, while the monitoring ensures performance tracking and alerts for issues in production.

# Output
Ensure Terraform displays:

VPC ID, Subnet IDs (Public, Private, Database)
RDS Endpoint
EKS Cluster details (ID, security group ID, OIDC provider URL)
This structured plan covers all major components for deploying a 3-tier architecture on AWS using Terraform, ensuring state consistency, security, and scalability.








