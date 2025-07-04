# terraform-k8s-minikube
terraform-k8s-minikube is a simple local Terraform project that uses the Kubernetes provider to create and manage resources on a local Minikube cluster
## 🛠️ Requirements

Make sure the following tools are installed and properly configured:

✅ [Terraform](https://developer.hashicorp.com/terraform/downloads) (recommended v1.0 or higher)  
✅ [Minikube](https://minikube.sigs.k8s.io/docs/start/) (local Kubernetes cluster)  
✅ [kubectl](https://kubernetes.io/docs/tasks/tools/) (Kubernetes CLI)  
✅ Docker (required if using Docker driver with Minikube)  

## 📂 Project Structure
terraform-k8s-minikube/
├── main.tf
├── provider.tf
├── versions.tf
├── README.md
└── images/
    ├── kubectl-get-namespaces.jpg
    ├── kubectl-get-nodes.jpg
    ├── terraform-init.jpg
    ├── terraform-apply.jpg

## 🚀 Setup Instructions

1. Start Minikube (adjust memory/CPU based on your system):

```bash
minikube start --driver=docker --memory=1968 --cpus=2

2.Check Minikube is running:

```bash
kubectl get nodes
### ✅ kubectl get nodes
![Nodes](images/kubectl-get-nodes.jpg)

3.Initialize Terraform:

```bash
terraform init
### ✅ terraform init
![Terraform Init](images/terraform-init.jpg)

4.Apply the Terraform configuration:

```bash
terraform apply
### ✅ terraform apply
![Terraform Apply](images/terraform-apply.jpg)

Type yes when prompted to confirm the creation of resources.
5.Verify the resources in Kubernetes:


```bash
kubectl get namespaces
kubectl get all -n demo-namespace

You should see the nginx Deployment, Pods, and Service running in the demo-namespace.
### ✅ kubectl get namespaces
![Namespaces](images/kubectl-get-namespaces.jpg)

6.(Optional) Access the Minikube dashboard:

```bash
minikube dashboard

A web-based dashboard for managing Kubernetes resources will open in your browser.
