# Voting App on Minikube

This repository contains files and instructions to deploy a simple Voting App on Minikube using Kubernetes.

## Prerequisites

Before getting started, ensure that you have the following installed on your machine:

- Minikube
- kubectl
- Docker

## Getting Started

1. Start Minikube with Docker as the driver:
   ```bash
   minikube start --driver=docker
   ```

2. Deploy the application components (pods and services):
   ```bash
   	kubectl apply -f voting-app-pod.yaml -f voting-app-service.yaml 
   	kubectl apply -f redis-pod.yaml -f redis-service.yaml 
   	kubectl apply -f posgres-pod.yaml -f posgres-service.yaml 
   	kubectl apply -f worker-app-pod.yaml 
   	kubectl apply -f result-app-pod.yaml -f result-app-service.yaml
   ```

3. Access the application using the Minikube service URLs:
   ```bash
   	minikube service <service-name>
   ```
# Components
## The Voting App consists of the following components:

	voting-app: Frontend web application where users can vote.
	redis: Redis database for storing votes.
	postgres: PostgreSQL database for storing voting results.
	worker-app: Worker application that counts votes and stores results in the PostgreSQL database.
	result-app: Frontend web application to display voting results.

# Troubleshooting
   If you encounter any issues during setup or deployment, you can check the Minikube logs for more information:

   ```bash
   	minikube logs
   ```
# Cleanup
   To stop and delete the Minikube cluster, run:
   ```bash
	minikube stop
	minikube delete
