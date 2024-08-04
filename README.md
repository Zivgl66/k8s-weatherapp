# k8s-weatherapp

This repository is dedicated to the deployment and management of a weather application on a Kubernetes (k8s) cluster using ArgoCD. It serves as a configuration source for ArgoCD to continuously monitor and manage the application's deployment state.

## Overview

The k8s-weatherapp repository is set up for the purpose of demonstrating and utilizing GitOps principles with ArgoCD. The application, designed as a weather app, is managed through Kubernetes manifests and Helm charts, enabling automated deployment and monitoring.

## ArgoCD Integration

ArgoCD is a declarative, GitOps continuous delivery tool for Kubernetes. This repository contains the necessary manifests and configurations for ArgoCD to:

- **Automate Deployments**: ArgoCD pulls the latest changes from this repository and deploys them to the Kubernetes cluster.
- **Monitor Application State**: Continuously monitors the live state of the weather app against the desired state defined in the Git repository.
- **Rollback and Rollforward**: Provides the ability to easily rollback to previous versions or apply newer changes as defined in the Git history.

## Repository Structure

- **`k8s/`**: Contains the Kubernetes manifests for deploying the weather application.
- **`helm/`**: If applicable, contains Helm charts used for the deployment.

## Getting Started

### Prerequisites

- Kubernetes cluster (Minikube, GKE, EKS, etc.)
- ArgoCD installed and configured in your Kubernetes cluster
- Kubectl configured to access your Kubernetes cluster

### ArgoCD Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Zivgl66/k8s-weatherapp.git
   cd k8s-weatherapp
   ```

2. **Register the application with ArgoCD**:
   Register this repository with ArgoCD to start monitoring and managing the application.
   ```bash
   argocd app create weatherapp \
     --repo https://github.com/Zivgl66/k8s-weatherapp.git \
     --path k8s \
     --dest-server https://kubernetes.default.svc \
     --dest-namespace default
   ```

3. **Sync the application**:
   Sync the application to deploy the current state defined in the repository.
   ```bash
   argocd app sync weatherapp
   ```

## Usage

Once ArgoCD is set up, it will continuously monitor this repository for changes and automatically update the application deployment accordingly. You can access the ArgoCD dashboard to manage and observe the application's state.

## Contributing

Contributions are welcome! Please follow these steps to contribute:

1. **Fork the repository** on GitHub.
2. **Create a new branch** for your feature or bugfix.
3. **Commit your changes** with clear commit messages.
4. **Push your changes** to your forked repository.
5. **Create a pull request** to the main repository.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

This version focuses solely on the use of ArgoCD for the deployment and management of the weather app.
