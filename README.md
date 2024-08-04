# k8s-weatherapp

This repository contains a weather application designed to run on a Kubernetes (k8s) cluster. The app provides weather data to users by integrating with external weather APIs.

## Features

- **Weather Data**: Provides real-time weather information using external APIs.
- **Kubernetes Deployment**: Deployed and managed within a Kubernetes cluster for scalability and reliability.
- **Microservices Architecture**: Designed with a microservices architecture for flexibility and ease of maintenance.

## Getting Started

### Prerequisites

- Docker
- Kubernetes cluster (Minikube, GKE, EKS, etc.)
- Kubectl configured to access your Kubernetes cluster

### Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Zivgl66/k8s-weatherapp.git
   cd k8s-weatherapp
   ```

2. **Build Docker images**:
   Build the Docker images for the application components.
   ```bash
   docker build -t weatherapp-api ./api
   docker build -t weatherapp-frontend ./frontend
   ```

3. **Deploy to Kubernetes**:
   Apply the Kubernetes manifests to deploy the application to your cluster.
   ```bash
   kubectl apply -f k8s/deployment.yaml
   kubectl apply -f k8s/service.yaml
   ```

### Usage

Once deployed, access the weather app via the service's external IP or load balancer. The frontend will provide an interface for querying weather data.

## Contributing

Contributions are welcome! Please follow these steps to contribute:

1. **Fork the repository** on GitHub.
2. **Create a new branch** for your feature or bugfix.
3. **Commit your changes** with clear commit messages.
4. **Push your changes** to your forked repository.
5. **Create a pull request** to the main repository.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```

Feel free to modify any sections to better suit your project's specifics or add any additional details you think are necessary.
