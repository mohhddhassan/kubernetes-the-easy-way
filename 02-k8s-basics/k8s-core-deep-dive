# Kubernetes Basics – In Depth but Beginner Friendly

---

### **What is Kubernetes?**

Kubernetes (aka **K8s**) is a **container orchestration platform** that takes care of running, managing, and scaling **hundreds or even thousands of containers**.

Most people use it with **Docker containers**, but it also supports other runtimes like **containerd** and **CRI-O**.

What does it handle?

* **Scaling** apps up and down automatically 🔄
* **Restarting** containers when they crash ♻️
* **Load balancing** traffic between containers ⚖️
* **Rolling updates** so you can update apps without downtime 🚀
* **Networking** between containers 🌐
* **Storage** so data doesn’t get lost 💾

---

### **Why Do We Even Need Kubernetes?**

Modern applications are **split into microservices** (like separate Lego blocks), each running inside its own container.

Manually starting, stopping, scaling, and updating these containers becomes a nightmare when your app grows → **Kubernetes automates all that**.

Think of it like an **orchestra conductor** for your containers:
you tell it what song (state) you want, and it makes sure all instruments (containers) play together.

---

## **Core Kubernetes Components**

---

### **1. Node**

A **Node** is just a machine (physical server, VM, or cloud instance) where containers actually run.
A Kubernetes cluster typically has:

* **Control Plane (Master)** – brain of the cluster
* **Worker Nodes** – where your application workloads (pods) run

Each worker node has:

* **kubelet** – manages pods on the node
* **container runtime** – runs the actual containers
* **kube-proxy** – handles node-level networking

---

### **2. Pod**

A **Pod** is the **smallest deployable unit** in Kubernetes.
Think of it as a wrapper around one or more containers with extra features:

* **Network** (each pod gets its own IP)
* **Storage**
* **Configs & Secrets injection**
* **Restart policies & monitoring hooks**

Usually, **1 Pod = 1 microservice**.
If you need scaling, Kubernetes just creates **more copies (replicas) of pods**.

---

### **3. Services**

Pods have **ephemeral IPs** (they change if the pod restarts), so how do you access them reliably? → **Services**.

A Service gives **stable networking** inside the cluster and sometimes outside it.

**Types of Services:**

* **ClusterIP** – internal only (default). Good for DB or internal APIs.
* **NodePort** – exposes on `<NodeIP>:<Port>`.
* **LoadBalancer** – integrates with cloud load balancers (AWS ELB, GCP LB, Azure LB).

---

### **4. Ingress**

Instead of remembering `http://NodeIP:Port`, you can expose apps via a domain name like `https://myapp.com`.
**Ingress** provides:

* **Domain-based routing**
* **TLS termination (HTTPS)**
* **Path-based routing** (`/api`, `/frontend`, etc.)

---

### **5. ConfigMap**

Used to store **non-sensitive configuration data** like:

* DB endpoints
* App feature flags
* External API URLs

**Benefits:**

* Makes images reusable (no need to hardcode config inside).
* Allows updating configs without rebuilding or redeploying containers.

**How to use?** Mount as files or inject as environment variables into pods.

---

### **6. Secret**

Like ConfigMaps but for **sensitive data**:

* Passwords
* API keys
* TLS certs

Secrets are **Base64 encoded** by default (not encryption, just obfuscation).
They’re used in the same way as ConfigMaps (files/env vars) but with tighter access control.

**Golden rule:**
Never commit secrets to GitHub or share them in plaintext.

---

### **7. Volumes**

Containers are **ephemeral** – data disappears if a container restarts.
**Volumes** solve this by giving persistent storage to pods.

**Types:**

* `emptyDir` → temporary storage, wiped when the pod is deleted.
* `hostPath` → directly mounts a folder from the node.
* `PersistentVolume (PV)` → storage abstraction (NFS, EBS, Ceph, etc.).
* `PersistentVolumeClaim (PVC)` → pod’s request for a PV.

**Typical Use Cases:**

* Databases
* File uploads
* Caching or storing logs

---

### **8. Deployment**

The go-to way to run **stateless apps** in Kubernetes.
It takes care of:

* Scaling replicas up and down
* Rolling updates (no downtime)
* Rollbacks if something goes wrong
* Self-healing (replacing failed pods automatically)

**Examples:** Web apps, APIs, frontends.

---

### **9. StatefulSet**

Used for **stateful apps** that need stable network identities and persistent storage.
Key features:

* Predictable pod names (`pod-0`, `pod-1`, etc.)
* One-to-one storage mapping (each pod gets its own PVC)

**Examples:** Databases (MongoDB, MySQL, Cassandra), Kafka, Zookeeper

---

### **Networking Problem & Solution**

**Problem:** Pod restarts = new IP = broken connections.
**Solution:**

* Use **Service** for stable internal connectivity
* Use **Ingress** or LoadBalancer for external access

---

### **Quick Docker Refresher** (since K8s builds on it)

* **Image:** Template/blueprint of a container (built from a Dockerfile)
* **Container:** Running instance of an image
* **Popular base images:** `nginx`, `mysql`, `python`

Want to learn Docker first?
Check out my repo → [Docker Basics for Data Engineers](https://github.com/mohhddhassan/Docker-Basics-for-Data-Engineers/tree/main)

---

### **ConfigMap vs Secret vs Deployment vs StatefulSet**

* **ConfigMap → Non-sensitive configs**
* **Secret → Sensitive stuff (passwords, keys)**
* **Deployment → Stateless workloads**
* **StatefulSet → Stateful workloads (databases, messaging queues)**

---

## **What About Databases in Kubernetes?**

While StatefulSet can run databases, scaling & managing DB replicas **inside Kubernetes** is complex and often not worth it for production.
The common practice:

* Run your DB outside the Kubernetes cluster (RDS, Cloud SQL, Managed Mongo, etc.)
* Use Kubernetes ConfigMap or Secret to store the **DB endpoint and credentials**

This way, Kubernetes focuses on what it’s best at: **app orchestration, not database babysitting**.

---
