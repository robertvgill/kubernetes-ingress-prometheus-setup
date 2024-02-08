# Kubernetes Ingress and Prometheus Setup

This repository contains an Ansible playbook to automate the setup of a Kubernetes cluster with NGINX Ingress Controller and Prometheus monitoring.

## Prerequisites

Before running the Ansible playbook, ensure that the following prerequisites are met:

- Linux environment (tested on Ubuntu)
- Ansible installed on your local machine
- Docker installed on your local machine
- `curl` command-line tool installed on your local machine

## How to Run

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/yourusername/kubernetes-ingress-prometheus-setup.git

2. **Navigate to the Repository Directory:**

   ```bash
   cd kubernetes-ingress-prometheus-setup

3. **Run the Ansible Playbook:**

	```bash
	ansible-playbook playbook.yml

This command will start the automation process to set up the Kubernetes cluster, NGINX Ingress Controller, and Prometheus monitoring.

## Verify the Setup:

Once the playbook execution completes, you can verify that the setup was successful:

1. **Access the Kubernetes dashboard by running:**

	```bash
	kubectl proxy

Then navigate to http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/#!/login.

2. **Verify NGINX Ingress Controller by checking the status of the Ingress Controller pods:**

	```bash
	kubectl get pods -n ingress-nginx

3. **Access the NGINX Ingress Controller dashboard by running:**

	```bash
	kubectl --namespace ingress-nginx get services -o wide -w nginx-ingress-controller

Then use the external IP address to access the dashboard.

4. **Access the Prometheus dashboard by running:**

	```bash
	kubectl port-forward -n monitoring <prometheus-pod-name> 9090:9090

Then navigate to http://localhost:9090 in your browser.
