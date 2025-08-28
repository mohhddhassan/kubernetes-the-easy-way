# 🚀 Advanced Kubernetes

This folder is where we move past the basics and workloads stuff.  
Here we’re diving into topics that make a cluster *production-ready* – configs, networking, storage, scaling, etc.  

---

## 📂 What’s inside?

- **Config & Secrets Management**  
  → How to handle app configs, environment variables, and sensitive data (ConfigMaps, Secrets, best practices).

- **Networking Deep Dive**  
  → Understand how pods talk to each other, CNI plugins, kube-proxy internals, and service types (Ingress, LB, NodePort).

- **Storage in Kubernetes**  
  → Persistent Volumes (PV), PVCs, and StorageClasses for dynamic provisioning of storage.

- **Security**  
  → RBAC, Service Accounts, Network Policies, and how to lock down your cluster properly.

- **Monitoring & Logging**  
  → Tools & strategies (Prometheus, Grafana, EFK stack, etc.) to keep an eye on your cluster health.

- **Helm Basics (Optional)**  
  → Intro to Helm charts – the package manager for Kubernetes. Super useful for deploying complex apps.

- **Scaling & Autoscaling**  
  → Manual scaling, HPA (Horizontal Pod Autoscaler), VPA, and Cluster Autoscaler – how Kubernetes keeps up with traffic.

---

## 🎯 Goal
By the end of this section, you’ll get a good idea of how Kubernetes is actually run in production.  
This isn’t just “hello-world pods” anymore, but how real apps survive traffic, failures, and scaling challenges 🚦.

---

## ⚡ Note
- Not all topics are mandatory (like Helm – optional).  
- Pick & learn based on what you need for projects or job prep.  
