# DevOps Practical – End-to-End CI/CD Pipeline

**A Complete DevOps Project Using Flask, Git, GitHub Actions, Docker, Kubernetes & Render**

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Flask](https://img.shields.io/badge/Flask-3.0.0-black)
![Docker](https://img.shields.io/badge/Docker-Containerization-2496ED?logo=docker)
![Kubernetes](https://img.shields.io/badge/Kubernetes-Orchestration-326CE5?logo=kubernetes)
![CI/CD](https://img.shields.io/badge/CI%2FCD-GitHub%20Actions-success)

## Project Overview

This project demonstrates a complete DevOps workflow by developing, testing, containerizing, deploying, and automatically updating a Python Flask web application.

The project implements Continuous Integration (CI) using GitHub Actions and Continuous Deployment (CD) using Render.

It also demonstrates container orchestration and self-healing capabilities using Kubernetes (Minikube).

## Technologies Used

| Technology | Purpose |
|---|---|
| Python | Application development |
| Flask | Web framework |
| Git & GitHub | Version control |
| GitHub Actions | Continuous Integration |
| Pytest | Automated testing |
| Docker | Application containerization |
| Docker Hub | Container image registry |
| Kubernetes | Container orchestration |
| Minikube | Local Kubernetes cluster |
| kubectl | Kubernetes management |
| Render | Cloud deployment |

## Architecture

```text
        Developer
            |
            v
       Git & GitHub
            |
            v
     GitHub Actions
      (CI Pipeline)
            |
      Automated Tests
            |
            v
       Docker Build
            |
       Docker Hub
            |
            v
       Kubernetes
        (Minikube)
            |
       Flask App
            |
            v
       Render Cloud
       (Deployment)
            |
            v
      Live Web Application
```

## Project Phases

### Phase 1 – Foundation: Flask & Git

- Created a Python Flask application.
- Configured project dependencies.
- Developed an automated test using Pytest.
- Initialized a Git repository.
- Pushed the project to GitHub.

**Initial application response:**

`Hello, DevOps World! V1`

### Phase 2 – Continuous Integration (CI)

Implemented a GitHub Actions workflow.

The pipeline automatically:

1. Checks out the source code.
2. Sets up Python 3.9.
3. Installs project dependencies.
4. Runs automated tests using Pytest.

Workflow location:

`.github/workflows/ci.yml`

### Phase 3 – Containerization with Docker

Created a Dockerfile to package the Flask application and its dependencies.

**Docker image:**

`yasiru453/flask-app:v1`

The image was built, tested locally, and pushed to Docker Hub.

[View Docker Hub Repository](https://hub.docker.com/r/yasiru453/flask-app)

### Phase 4 – Kubernetes Orchestration

Deployed the Flask application to a local Kubernetes cluster using Minikube.

Implemented:

- Kubernetes Deployment.
- Two application replicas.
- Kubernetes Service.
- NodePort networking.
- Pod management using kubectl.

Configuration files:

- `k8s/deployment.yaml`
- `k8s/service.yaml`

### Phase 5 – Kubernetes Self-Healing Test

Performed a practical failure simulation by deleting one running Pod.

Kubernetes automatically detected the missing replica and created a replacement Pod.

**Result:** The desired state of two running replicas was restored.

### Phase 6 – Continuous Deployment (CD)

Connected the GitHub repository to Render.

Configured Render to build and deploy the Flask application using Docker.

The application was successfully deployed and made accessible through a public URL.

**Initial live response:**

`Hello, DevOps World! We are LIVE on Render!`

#### Automated Deployment Test – V2

Updated the application response to:

`CI/CD and Docker Pipeline is a massive success! V2`

Updated the automated test, committed the changes, and pushed them to GitHub.

Render automatically detected the new commit and deployed the updated application.

**Final Result:** The V2 response was successfully displayed on the live application.

## Project Structure

```text
devops-practical/
│
├── .github/
│   └── workflows/
│       └── ci.yml
│
├── k8s/
│   ├── deployment.yaml
│   └── service.yaml
│
├── app.py
├── test_app.py
├── requirements.txt
├── Dockerfile
├── .gitignore
└── README.md
```

## Run Locally

### 1. Clone the Repository

```bash
git clone https://github.com/imsanilka/devops-practical.git
cd devops-practical
```

### 2. Create a Virtual Environment

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Application

```bash
python app.py
```

Open:

`http://localhost:5000`

### 5. Run Automated Tests

```bash
pytest
```

## Docker Commands

Build the image:

```bash
docker build -t flask-app:v1 .
```

Run the container:

```bash
docker run -p 5000:5000 flask-app:v1
```

## Kubernetes Commands

Start Minikube:

```bash
minikube start --driver=docker
```

Deploy the application:

```bash
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
```

Check running Pods:

```bash
kubectl get pods
```

Check the Deployment:

```bash
kubectl get deployments
```

Access the application:

```bash
minikube service flask-service
```

## Key DevOps Concepts Demonstrated

- Version Control
- Continuous Integration (CI)
- Automated Testing
- Containerization
- Container Registry
- Container Orchestration
- Desired State Management
- Self-Healing Infrastructure
- Continuous Deployment (CD)
- Cloud Hosting
- Automated Application Updates

## Final Outcome

Successfully developed and deployed a Flask application through an end-to-end DevOps workflow.

The project demonstrates how source code changes can be tested automatically, packaged into containers, deployed to cloud infrastructure, and updated through a Git push.

**Final Application Output:**

`CI/CD and Docker Pipeline is a massive success! V2`

---

**Developer:** Sanilka Gimhan

**GitHub:** https://github.com/imsanilka

**Project Repository:** https://github.com/imsanilka/devops-practical

**Docker Hub:** https://hub.docker.com/r/yasiru453/flask-app

*Built as a hands-on DevOps practical project.*
