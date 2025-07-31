# Kubernetes Basics

---

### **What is Kubernetes?**

- A **container orchestration platform** that manages **hundreds or thousands of containers**.
- Commonly used with **Docker containers** (but supports other runtimes like containerd, CRI-O, etc.).
- Handles:
    - Scaling 🔄
    - Auto-restarts ♻️
    - Load balancing ⚖️
    - Rolling updates 🚀
    - Networking 🌐
    - Storage 💾

---

### **Why Kubernetes?**

- Modern apps are **split into microservices**, each running in separate containers.
- Managing these manually is impossible at scale → Kubernetes automates this.

---

## **Core Components**

### **1. Node**

- A **machine** (physical/VM/cloud) where containers run.
- Kubernetes cluster = **multiple nodes** (one control plane + multiple worker nodes).

---

### **2. Pod**

- **Smallest deployable unit** in Kubernetes.
- **Abstraction over containers**:
    - Wraps one or more containers.
    - Adds **networking, storage, configs, restart policies, monitoring hooks**.
- Usually **1 Pod = 1 microservice**.

---

### **3. Services**

- Provide **stable IP addresses** to access pods (as pod IPs change on restart).
- **Types:**
    - **ClusterIP** – internal access only.
    - **NodePort** – external access via `<NodeIP>:<Port>`.
    - **LoadBalancer** – cloud LB integration (AWS ELB, GCP LB, etc.).

---

### **4. Ingress**

- Provides **domain-based routing** instead of IP:Port.
- Lets you access apps like `https://myapp.com` instead of `http://IP:Port`.

---

### **5. ConfigMap**

- Stores **non-sensitive configuration data** (DB endpoints, app settings, feature flags).
- **Benefits:**
    - Keeps images generic.
    - Update configs without rebuilding images.
    - Centralized config management.
- **Usage:** Mounted as files or injected as environment variables.

---

### **6. Secret**

- Stores **sensitive data** (passwords, API keys, certs).
- **Difference from ConfigMap:** Secrets are **Base64 encoded** & designed for credentials.
- **Usage:** Same as ConfigMap (files or env variables).
- **Best practice:** Never commit Secrets to Git.

---

### **7. Volumes**

- Provide **persistent storage** to pods (containers lose data on restart).
- **Types:**
    - `emptyDir` → temporary storage (deleted when pod stops).
    - `hostPath` → mounts a host directory into pod.
    - `PersistentVolume (PV)` → cluster-wide storage resource.
    - `PersistentVolumeClaim (PVC)` → pod-level request for PV.
- **Use Case:** Databases, file uploads, caching, logs.

---

### **8. Deployment**

- **Recommended way** to manage **stateless apps**.
- Handles:
    - Replica scaling.
    - Rolling updates & rollbacks.
    - Self-healing (replacing failed pods automatically).
- **Typical usage:** APIs, web apps, frontends.

---

### **9. StatefulSet**

- Used for **stateful apps** that need **stable network IDs & persistent storage**.
- Pods in StatefulSet have:
    - **Unique, predictable names** (`pod-0`, `pod-1`, …)
    - **Persistent storage binding** (one PVC per pod).
- **Examples:** Databases (MySQL, MongoDB, Cassandra), Kafka, Zookeeper.

---

## **Key Networking Concept**

- **Problem:** Pod restarts → new IP → broken connections.
- **Solution:**
    - Use **Service** (static virtual IP).
    - Internal service for DB, external + Ingress for frontend.

---

## **Docker Refresher**

- **Image:** Blueprint for containers (from Dockerfile).
- **Container:** Running instance of image.
- **Official Images:** `nginx`, `mysql`, `python` (used as base images).

**Wanna learn about Docker basics?**  
Check out my **Docker for Beginners** repo for hands-on learning → [Docker Basics for Data Engineers](https://github.com/mohhddhassan/Docker-Basics-for-Data-Engineers/tree/main)

---

### **Key Differences**

- **ConfigMap → Non-sensitive configuration**
- **Secret → Sensitive information**
- **Deployment → Stateless apps**
    - **StatefulSet → Stateful apps**

---

## **StatefulSet and DB replica**

We don’t usually use StatefulSet for database replica as they are a tedious work and scaling them is a complex job, so for that we usually host the db outside the k8’s cluster and add the DB endpoint to the ConfigMap file.
