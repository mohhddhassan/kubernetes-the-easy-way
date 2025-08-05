## What is Kubernetes?

Kubernetes (K8s) is a **container orchestration platform** to manage containers at scale.
It automates:

* Scaling 🔄
* Self-healing (auto restarts) ♻️
* Load balancing ⚖️
* Rolling updates 🚀
* Networking 🌐
* Storage 💾

### **Why?**
Modern apps use **microservices** → each runs in its own container → managing them manually is hard. Kubernetes handles it for you.

---

## Core Components

### Node

A **machine** (VM or physical) where your containers run.
A cluster has **1 control plane node** and **multiple worker nodes**.

### Pod

Smallest deployable unit.

* Usually **1 Pod = 1 microservice**.
* Wraps one or more containers with networking & storage.

### Service

Gives a **stable way** to access pods (since pod IPs change).

* **ClusterIP** → internal
* **NodePort** → external (`NodeIP:Port`)
* **LoadBalancer** → cloud LB integration

### Ingress

Provides **domain-based access** (like `https://myapp.com` instead of `http://IP:Port`).

### ConfigMap & Secret

* **ConfigMap** → non-sensitive config data (Database endpoints).
* **Secret** → sensitive data (passwords, API keys).

### Volumes

Provide **persistent storage** to pods (containers lose data on restart).

* `emptyDir` → temp storage
* `PersistentVolume (PV)` + `PersistentVolumeClaim (PVC)` → permanent storage

### Deployment

**Recommended way** to manage **stateless apps**.
- Handles:
    - Replica scaling.
    - Rolling updates & rollbacks.
    - Self-healing (replacing failed pods automatically).
- **Typical usage:** APIs, web apps, frontends.

### StatefulSet

Used for **stateful apps** that need **stable network IDs & persistent storage**.

> Often, databases are hosted **outside Kubernetes** and connected via ConfigMaps.

---

## Key Networking Concept

Pods restart → IP changes → broken connections.
**Solution:** Use **Services** for stable networking and **Ingress** for clean URLs.

---

## Quick Docker Refresher

* **Image** → container blueprint
* **Container** → running instance
* **Official images** like `nginx`, `mysql`, `python`

For Docker basics → [Docker Basics for Data Engineers](https://github.com/mohhddhassan/Docker-Basics-for-Data-Engineers)

---