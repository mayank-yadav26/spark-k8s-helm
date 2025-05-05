# spark-k8s-helm
This project to learn spark setup on Argo , using k8s and helm charts

# Spark on Kubernetes with Argo Workflows

This repository contains configurations for running Apache Spark applications on Kubernetes using Argo Workflows and Helm charts.

## Project Overview

This project demonstrates how to:
1. Set up a local Kubernetes cluster using Kind
2. Deploy and run Apache Spark applications using Argo Workflows
3. Package and deploy applications using Helm charts
4. Configure proper RBAC (Role-Based Access Control) for Spark on Kubernetes

## Prerequisites

- Docker installed
- Kind installed
- kubectl installed
- Helm installed
- Argo Workflows installed in your cluster

## Getting Started

### 1. Create a Kind Cluster

```bash
# Create a Kind cluster with the provided configuration
./create-kind-cluster.sh
```

### 2. Install Argo Workflows

Argo Workflows needs to be installed in your cluster:

```bash
# Install Argo Workflows using kubectl
kubectl create namespace argo
kubectl apply -n argo -f https://github.com/argoproj/argo-workflows/releases/latest/download/install.yaml
```

### 3. Set up RBAC for Argo and Spark

```bash
# Apply RBAC configurations
kubectl apply -f argo-role.yaml
kubectl apply -f argo-rolebinding.yaml
kubectl apply -f service-account.yaml
```

### 4. Deploy Spark Application with Helm

```bash
# Install the Spark application chart
helm install spark-app ./spark-k8s-helm/spark-chart

# For a simple hello-spark application
helm install hello-spark ./spark-k8s-helm/hello-spark-chart
```

### 5. Submit a Spark Workflow

```bash
# Submit a Spark workflow
kubectl apply -f spark-workflow.yaml
```

## Helm Charts

The repository includes two Helm charts:

1. **spark-chart**: Main chart that sets up the Kubernetes namespace, RBAC roles, and service account for Spark applications.

2. **hello-spark-chart**: A simple example chart that deploys a basic Spark application workflow.

## Configuration

### Spark Chart Configuration

Edit `spark-k8s-helm/spark-chart/values.yaml` to customize:
- Namespace for Spark applications
- Spark Docker image 
- Service account settings

### Hello Spark Chart Configuration

Edit `spark-k8s-helm/hello-spark-chart/values.yaml` to customize:
- Workflow name
- Container image
- Resource requests and limits

## Architecture

The project uses:

- **Kind** as the local Kubernetes environment
- **Argo Workflows** as the workflow engine to orchestrate Spark jobs
- **Helm** for packaging and deploying applications
- **Kubernetes RBAC** to manage permissions

## Docker Images

The project uses custom Docker images:
- `mayankyadav25/spark_test:v1.0` - Simple Spark application
- `mayankyadav25/spark_agent:v10.0` - Advanced Spark agent



