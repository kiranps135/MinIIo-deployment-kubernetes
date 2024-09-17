# Minio Object Storage Deployment on Kubernetes

Minio is an open-source object storage server compatible with the Amazon S3 cloud storage service. This repository contains the configuration files and instructions to deploy Minio on a Kubernetes cluster for scalable and secure object storage.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Accessing Minio](#accessing-minio)
- [Managing Minio](#managing-minio)


## Prerequisites

Before deploying Minio, ensure you have the following:

- A Kubernetes cluster (version 1.26 and later)
- `kubectl` configured to interact with your cluster
- Storage class or Persistent Volumes (PV) configured for persistence
- A valid domain or access to the external IP of your cluster

## Installation

### 1. Standalone Minio Deployment

#### Step 1: Create a Namespace for Minio

```bash 

kubectl create namespace minio
```

### Step 2: Deploy Minio with Persistent Storage


```bash 

kubectl apply -f minio-pvc.ymal
```

### Apply the provided Kubernetes YAML manifest to deploy Minio:

```bash

kubectl apply -f minio-deployment.yaml
```

### Step 3: Verify the Deployment

```bash
kubectl get pods -n minio
kubectl get svc -n minio 
```

### Minio will be accessible at the external IP provided by the LoadBalancer.
