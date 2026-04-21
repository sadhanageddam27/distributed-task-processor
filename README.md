# Distributed Task Processing System

![Python](https://img.shields.io/badge/Python-3.9+-blue?logo=python)
![Docker](https://img.shields.io/badge/Docker-containerized-blue?logo=docker)
![Kubernetes](https://img.shields.io/badge/Kubernetes-orchestration-326ce5?logo=kubernetes)
![AWS](https://img.shields.io/badge/AWS-EC2%20%7C%20S3-orange?logo=amazonaws)

Distributed system for asynchronous job execution and concurrent task
management — containerized worker nodes deployed on AWS using Docker
and Kubernetes with fault-tolerant execution and activity logging.

## Live Project Page
**https://sadhanageddam27.github.io/distributed-task-processor/**

---

## Architecture

    Job Submission (REST API)
          │
          ▼
    Task Queue (central broker)
          │
          ▼
    Worker Nodes (Docker containers)
    ├── Worker 1 — async task execution
    ├── Worker 2 — concurrent processing
    └── Worker N — auto-scaled by K8s
          │
          ▼
    Results + Activity Logging

---

## What This System Does

- Accepts task submissions via REST API
- Distributes work across containerized worker nodes
- Executes tasks asynchronously and concurrently
- Auto-restarts failed workers via Kubernetes health checks
- Logs job execution frequency and status for monitoring
- Scales horizontally based on queue depth

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Language | Python 3.9+ |
| Containerization | Docker |
| Orchestration | Kubernetes |
| Cloud | AWS EC2 + S3 |
| API Layer | REST APIs |
| CI/CD | GitHub Actions |
| OS | Linux |

---

## Key Design Decisions

**Containerized workers** — each worker runs in an isolated Docker
container for consistent environments and clean failure isolation.

**Kubernetes orchestration** — K8s manages pod lifecycle, auto-restarts
unhealthy workers, and scales based on workload.

**Async execution** — non-blocking job dispatch allows multiple tasks
to execute in parallel without blocking the submission queue.

**Fault tolerance** — failed tasks are re-queued with retry logic;
dead letter queue captures permanently failed jobs.

---

## Topics
`python` `docker` `kubernetes` `aws` `distributed-systems`
`async` `rest-api` `cloud` `linux` `ci-cd`
