# Cloud-Native-Flask-Microservice-on-Kubernetes-Helm-Autoscaling-Full-Observability
Built a cloud-native Flask application deployed on Kubernetes using Docker and Helm. Implemented ConfigMaps, Secrets, resource management, and Horizontal Pod Autoscaling (HPA). Integrated Prometheus and Grafana for monitoring, observability, dashboards, and alerting to simulate production-grade DevOps practices.
flask-k8s-project/
│
├── README.md
│
├── app.py
├── Dockerfile
├── requirements.txt
│
├── k8s/
│   ├── deployment.yaml
│   ├── service.yaml
│   ├── configmap.yaml
│   ├── secret.yaml
│   └── hpa.yaml
│
├── flask-chart/
│   ├── Chart.yaml
│   ├── values.yaml
│   └── templates/
│       ├── deployment.yaml
│       ├── service.yaml
│       ├── configmap.yaml
│       └── secret.yaml
│
├── screenshots/
│   ├── kubernetes-deployment.png
│   ├── helm-chart.png
│   ├── hpa-scaling.png
│   ├── prometheus-targets.png
│   ├── grafana-dashboard.png
│   └── grafana-alerts.png
│
└── .gitignore

# Cloud-Native Flask Application Deployment with Kubernetes, Helm, Prometheus & Grafana

## Overview

This project demonstrates the deployment of a containerized Flask application on Kubernetes using modern DevOps practices. The application is packaged using Docker, deployed using Kubernetes manifests and Helm charts, monitored using Prometheus and Grafana, and automatically scaled using Horizontal Pod Autoscaler (HPA).

The project simulates a production-style cloud-native environment with application deployment, configuration management, monitoring, alerting, and scalability.

---

## Architecture

```
Flask Application
        |
        v
      Docker
        |
        v
   Kubernetes Cluster
        |
        +----------------+
        |                |
      Helm             HPA
        |                |
        v                v
 Configuration     Auto Scaling
        |
        v
Prometheus ---> Grafana ---> Alerts
```

---

## Technologies Used

* Python (Flask)
* Docker
* Kubernetes
* Helm
* Prometheus
* Grafana
* Node Exporter
* kube-state-metrics
* Minikube
* Git & GitHub

---

## Features Implemented

### Application Deployment

* Containerized Flask application using Docker
* Kubernetes Deployment and Service configuration
* Multi-replica deployment for availability

### Kubernetes Configuration

* ConfigMaps for application configuration
* Secrets for sensitive information
* CPU and Memory resource requests and limits

### Helm Deployment

* Created reusable Helm chart
* Parameterized deployments using `values.yaml`
* Managed Kubernetes resources through Helm templates

### Horizontal Pod Autoscaler (HPA)

* Implemented CPU-based autoscaling
* Configured minimum and maximum replicas
* Tested automatic scaling behaviour

Example:

```
Minimum replicas: 2
Maximum replicas: 5
Target CPU utilization: 50%
```

### Monitoring & Observability

Implemented monitoring stack using:

* Prometheus for metrics collection
* Node Exporter for infrastructure metrics
* kube-state-metrics for Kubernetes metrics
* Grafana dashboards for visualization

### Alerting

Configured Grafana alerts for:

* High CPU usage
* High Memory usage
* Node availability
* Pod restart detection
* Deployment availability

---

## Project Structure

```
flask-k8s-project/

├── app.py
├── Dockerfile
├── requirements.txt

├── k8s/
│   ├── deployment.yaml
│   ├── service.yaml
│   ├── configmap.yaml
│   ├── secret.yaml
│   └── hpa.yaml

├── flask-chart/
│   ├── Chart.yaml
│   ├── values.yaml
│   └── templates/

└── screenshots/
```

---

## Deployment Steps

### Build Docker Image

```bash
docker build -t flask-app:v1 .
```

### Deploy Kubernetes Resources

```bash
kubectl apply -f k8s/
```

### Verify Deployment

```bash
kubectl get pods
kubectl get svc
```

### Deploy Using Helm

```bash
helm install flask-app ./flask-chart
```

### Verify Helm Release

```bash
helm list
```

### Check Autoscaling

```bash
kubectl get hpa
```

---

## Monitoring Setup

Access Grafana dashboard:

```bash
minikube service grafana -n monitoring
```

Access Prometheus:

```bash
minikube service prometheus -n monitoring
```

---

## Screenshots

### Kubernetes Deployment

(Add screenshot)

### Helm Chart

(Add screenshot)

### Horizontal Pod Autoscaler

(Add screenshot)

### Prometheus Targets

(Add screenshot)

### Grafana Dashboards

(Add screenshot)

### Grafana Alerts

(Add screenshot)

---

## Future Improvements

* Deploy application to Azure Kubernetes Service (AKS)
* Add CI/CD pipeline using GitHub Actions
* Configure Kubernetes Ingress with TLS
* Add persistent storage for Grafana
* Implement centralized logging using Loki/ELK

---

## Author

Phanindra Shatagopam

Cloud & DevOps Engineer
