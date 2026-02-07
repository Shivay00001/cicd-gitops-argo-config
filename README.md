# GitOps Infrastructure with ArgoCD

[![ArgoCD](https://img.shields.io/badge/ArgoCD-2.9-orange.svg)](https://argo-cd.readthedocs.io/en/stable/)
[![Kubernetes](https://img.shields.io/badge/Kubernetes-1.28-326CE5.svg)](https://kubernetes.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A **production-ready GitOps repository** managed by ArgoCD. This repository serves as the single source of truth for the state of the Kubernetes cluster, containing declarative infrastructure definitions, application manifests, and project configurations using the App-of-Apps pattern.

## 🚀 Features

- **App-of-Apps Pattern**: Hierarchical management of applications using a root "bootstrap" application.
- **Project Isolation**: Logical separation of resources using ArgoCD Projects (e.g., Finance, BioTech).
- **Declarative Infrastructure**: All Kubernetes resources (Deployments, Services, Ingress) defined in YAML.
- **Automated Sync**: Continuous synchronization between Git state and cluster state.
- **Drift Detection**: Automatic detection and correction of configuration drift.
- **Multi-Environment**: Structure supports overlay-based configuration for Dev, Staging, and Prod.

## 📁 Project Structure

```
cicd-gitops-argo-config/
├── bootstrap/             # Cluster bootstrap scripts
├── projects/              # ArgoCD Project definitions
│   └── finance-project.yaml
├── applications/          # ArgoCD Application definitions
│   └── payment-gateway.yaml
└── manifests/             # Raw Kubernetes manifests
    └── payment-gateway/
        ├── deployment.yaml
        └── service.yaml
```

## 🛠️ Quick Start

```bash
# Clone
git clone https://github.com/Shivay00001/cicd-gitops-argo-config.git

# Install ArgoCD (if not installed)
./bootstrap/install-argo.sh

# Apply the Root Application
kubectl apply -f bootstrap/root-app.yaml
```

## 📄 License

MIT License
