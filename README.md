# prometheus_install

To install Prometheus on your **Mac Pro** using **Helm**, follow these steps:

### **Prerequisites**
1. **Install Homebrew (if not installed)**
   ```sh
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. **Install Helm**
   ```sh
   brew install helm
   ```

3. **Install Kubernetes (Minikube or Kind)**
   If you don’t have a Kubernetes cluster, install Minikube:
   ```sh
   brew install minikube
   minikube start
   ```

### **Install Prometheus using Helm**
1. **Add the Prometheus Helm repository**
   ```sh
   helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
   helm repo update
   ```

2. **Install Prometheus**
   ```sh
   helm install prometheus prometheus-community/prometheus
   ```

3. **Verify the Installation**
   ```sh
   helm list
   kubectl get pods
   ```

### **Access Prometheus Dashboard**
1. **Port-forward the Prometheus server**
   ```sh
   kubectl port-forward svc/prometheus-server 9090:80
   ```
2. Open your browser and go to:
   ```
   http://localhost:9090
   ```
