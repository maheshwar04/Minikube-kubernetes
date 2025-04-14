
# Hello Minikube: Kubernetes on Your Local Machine

This guide helps you run a simple Hello World app using Kubernetes and Minikube.

## Prerequisites

Make sure you have the following installed:

- [Kubectl](https://kubernetes.io/docs/tasks/tools/)
- [Minikube](https://minikube.sigs.k8s.io/docs/start/)

## 1. Start Minikube

```bash
minikube start
```

## 2. Deploy Hello Minikube App

Create a deployment:

```bash
kubectl create deployment hello-minikube --image=kicbase/echo-server:1.0
```

Expose the deployment:

```bash
kubectl expose deployment hello-minikube --type=NodePort --port=8080
```

## 3. Access the App

Use `minikube service` to open the service in a browser:

```bash
minikube service hello-minikube
```

## 4. View Pod Logs

To view logs:

```bash
kubectl logs -l app=hello-minikube
```

## 5. Clean Up

To delete the deployment and service:

```bash
kubectl delete service hello-minikube
kubectl delete deployment hello-minikube
```

To stop Minikube:

```bash
minikube stop
```

## Resources

- Full tutorial: [Hello Minikube](https://kubernetes.io/docs/tutorials/hello-minikube/)
