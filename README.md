
# 🗳️ Voting App — Containerized & Kubernetes-Orchestrated

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![CSharp](https://img.shields.io/badge/C%23-239120?style=flat-square&logo=c-sharp&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)

> A production-ready, containerized polling application demonstrating multi-service architecture, Docker Compose orchestration, and Kubernetes deployment at scale.

---

## 📌 Problem → Solution → Outcome

| | |
|---|---|
| **Problem** | Building a scalable, multi-service web app where frontend, backend, database, and worker services are independently deployable and resilient |
| **Solution** | Designed a microservices architecture containerized with Docker, orchestrated with Kubernetes, and composed with Docker Compose for local development |
| **Outcome** | Fully portable, environment-agnostic deployment — runs identically on local Docker Desktop or a cloud Kubernetes cluster |

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────┐
│                   Voting App                         │
│                                                     │
│  [Vote UI]──►[Python API]──►[Redis Queue]           │
│                                  │                  │
│                             [.NET Worker]           │
│                                  │                  │
│                          [PostgreSQL DB]            │
│                                  │                  │
│                          [Result UI (Node)]         │
└─────────────────────────────────────────────────────┘
```

**Services:**
- `vote` — Python/Flask frontend for casting votes
- `result` — Node.js frontend for real-time results
- `worker` — .NET background worker processing votes
- `redis` — In-memory queue between vote and worker
- `db` — PostgreSQL persistent storage

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend (Vote) | Python · Flask · HTML/CSS |
| Frontend (Results) | Node.js · JavaScript |
| Backend Worker | C# · .NET |
| Queue | Redis |
| Database | PostgreSQL |
| Containerization | Docker · Docker Compose |
| Orchestration | Kubernetes (k8s-specifications/) |
| Health Checks | Custom healthcheck scripts |

---

## 🚀 Quick Start

### Option 1 — Docker Compose (Recommended for local)

```bash
# Clone the repo
git clone https://github.com/hmahajan299/voting-app.git
cd voting-app

# Start all services
docker-compose up -d

# Access the app
# Vote UI    → http://localhost:5000
# Result UI  → http://localhost:5001
```

### Option 2 — Kubernetes

```bash
# Apply all manifests
kubectl apply -f k8s-specifications/

# Check pods
kubectl get pods

# Get service URLs
kubectl get svc
```

---

## 📁 Project Structure

```
voting-app/
├── vote/                  # Python Flask voting frontend
├── result/                # Node.js results frontend
├── worker/                # .NET background worker
├── seed-data/             # Database seed scripts
├── healthchecks/          # Service health check scripts
├── k8s-specifications/    # Kubernetes manifests
│   ├── vote-deployment.yaml
│   ├── result-deployment.yaml
│   ├── worker-deployment.yaml
│   ├── redis-deployment.yaml
│   └── db-deployment.yaml
├── docker-compose.yml     # Local development compose
├── docker-compose.images.yml
├── docker-stack.yml       # Docker Swarm stack
└── architecture.excalidraw.png
```

---

## 🔑 Key DevOps Concepts Demonstrated

- ✅ **Multi-container architecture** with Docker Compose
- ✅ **Kubernetes manifests** for production-grade deployment
- ✅ **Service discovery** between containers via Docker networking
- ✅ **Health checks** for service readiness
- ✅ **Persistent storage** with PostgreSQL volumes
- ✅ **Message queue pattern** with Redis

---

## 📸 Architecture Diagram

![Architecture](architecture.excalidraw.png)

---

## 👤 Author

**Harshal Mahajan** — DevOps & Cloud Engineer
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=flat-square&logo=linkedin)](https://linkedin.com/in/harshal-mahajan)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=flat-square&logo=github)](https://github.com/hmahajan299)
