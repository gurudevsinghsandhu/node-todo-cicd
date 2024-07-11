# Google Kubernetes Engine (GKE) Autopilot and Kustomize
Welcome to the NodeJS DevOps Project GitHub repository! This repository contains instructions and resources to help you get started with Google Kubernetes Engine (GKE) Autopilot and Google Cloud Shell.

# Table of Contents
 - Introduction
 - Prerequisites
 - Getting Started
 - Install HELM
 - Install nginx-controller
 - Kubernetes Autopilot
 - Create a Namespace
 - Deploy an Application
 - Google Cloud Shell
 - Useful Commands

# Introduction
This repository provides a step-by-step guide to setting up a Kubernetes environment with GKE Autopilot and using Google Cloud Shell for management and deployment tasks.

# Prerequisites
Before you begin, make sure you have the following prerequisites:
  - A Google Cloud Platform (GCP) account with billing enabled.
  - Google Cloud SDK (gcloud) installed on your local machine.
  - Access to a GKE cluster with Autopilot enabled.

# Google Cloud Shell
Google Cloud Shell provides a browser-based shell environment that you can use for managing your GCP resources and interacting with Kubernetes clusters.

To access Google Cloud Shell, follow these steps:

Log in to your GCP Console. Click on the "Activate Cloud Shell" button in the upper-right corner.

Install HELM
To install HELM, use the following commands:

# Add & Update the HELM repository
helm repo add helm https://helm.sh/helm

helm repo update

#Install nginx-controller
To install the nginx-controller, use the following commands:

# Add & Update the nginx-controller repository
helm repo add nginx https://kubernetes.github.io/ingress-nginx
helm repo update
helm install nginx nginx/ingress-nginx 
helm search repo nginx

# List all ValidatingWebhookConfigurations in all namespaces
kubectl get ValidatingWebhookConfiguration -A


# On Shell
# Create a Namespace
You can create a Kubernetes namespace using the following command:
- kubectl create namespace <namespace-name>

# Deploy an Application using Kustomize
To deploy an application, apply the YAML configuration file to your namespace:
 - kubectl apply -k <path-to-overlays-environment>

# Useful Commands
Here are some useful commands to help you manage your Kubernetes environment:

# List all pods in the current namespace
kubectl get pods -n <>namespace>

# Create a new Kubernetes namespace (e.g., "dev" or "sit")
kubectl create ns <namespace-name>

# Apply a YAML configuration file to create resources
kubectl apply -f <path-to-yaml-file>
