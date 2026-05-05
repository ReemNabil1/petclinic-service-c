# PetClinic Service C

This is a Spring Boot microservice that is part of a microservices architecture deployed using a complete CI/CD pipeline with Jenkins, Docker, and Kubernetes (k3s).

---

## Tech Stack

* Java 17
* Spring Boot
* Maven
* Docker
* Kubernetes (k3s)
* Jenkins

---

## ⚙️ CI/CD Pipeline

This service is built and deployed using a Jenkins pipeline powered by a shared library.

Pipeline stages:

1. Clean Workspace
2. Build (Maven)
3. Run Unit Tests
4. Package Application (JAR)
5. Build Docker Image
6. Push Image to Docker Hub
7. Deploy Container

---

## 🐳 Docker

Docker Image:

```
reemnabil/service-c:latest
```

Build manually:

```
docker build -t reemnabil/service-c .
```

Run container:

```
docker run -d -p 9092:8080 reemnabil/service-c
```

---

## ☸️ Kubernetes (k3s)

Deployment:

* Name: service-c

Service:

* Name: service-c-svc
* Type: ClusterIP
* Port: 80 → 8080

Apply:

```
kubectl apply -f k8s/
```

---

## 🌐 Access

* Docker:
  http://10.145.128.17:9092

* Nginx Reverse Proxy:
  http://10.145.128.17/service-c

---

## Notes

* Uses Jenkins Shared Library for CI/CD
* Fully automated pipeline
* Can be deployed locally or on Kubernetes
