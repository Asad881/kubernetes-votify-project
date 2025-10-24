# Kubernetes Votify Project

This project demonstrates the deployment of a multi-service distributed voting application onto a Kubernetes cluster. The entire infrastructure is defined declaratively using Kubernetes manifest (YAML) files.

## Application Architecture

The application consists of five microservices:
*   **voting-app:** A front-end web app in Python for casting votes.
*   **redis:** An in-memory database to queue new votes.
*   **worker:** A .NET worker that processes votes from Redis and stores them in PostgreSQL.
*   **db:** A PostgreSQL database for persistent vote storage.
*   **result-app:** A Node.js web app to display the voting results.

## Key Kubernetes Concepts Used

*   **Deployments:** To manage the lifecycle and replicas of each microservice.
*   **Services:** To provide stable network endpoints for inter-service communication (`ClusterIP`) and external access (`NodePort`).
*   **PersistentVolume (PV) & PersistentVolumeClaim (PVC):** To provide stable, persistent storage for the PostgreSQL database.
*   **Labels and Selectors:** To logically group and link Kubernetes objects together.

## Manifest Files

This repository contains all the YAML manifests required to deploy the application:
1.  `redis-deployment.yaml` & `redis-service.yaml`
2.  `db-pvc.yaml`, `db-deployment.yaml` & `db-service.yaml`
3.  `worker-deployment.yaml`
4.  `voting-app-deployment.yaml` & `voting-app-service.yaml`
5.  `result-app-deployment.yaml` & `result-app-service.yaml`
