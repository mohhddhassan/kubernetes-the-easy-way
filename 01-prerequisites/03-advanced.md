# Prerequisites - Advanced (Optional Deep Dives)

This section is for when you want to go beyond the basics and “just enough” learning.  
These topics are **not required to start using Kubernetes** but will make you a stronger engineer in the long run.

---

## 1. Container Internals
- **Namespaces & Cgroups:** How containers isolate processes.
- **Overlay Filesystems:** Why Docker images are lightweight.
- **Hands-on:**  
  ```bash
  docker run --rm -it alpine sh
  ps aux
  ```
- **Why?**  
  Helps you troubleshoot weird container issues.

---

## 2. Kubernetes Architecture Deep Dive
- **Control Plane Components:** API Server, Scheduler, Controller Manager, etcd.
- **Node Components:** Kubelet, Kube-Proxy.
- **Cluster Networking:** CNI plugins (Calico, Flannel, Cilium).

---

## 3. Security Concepts
- **RBAC:** Role-based access control.
- **Pod Security Standards (PSS):** Running pods with minimal privileges.
- **Secrets Management:** Storing sensitive data securely.

---

## 4. CI/CD with Kubernetes
- Jenkins, GitHub Actions, or GitLab CI deploying to K8s.
- GitOps concepts using ArgoCD or Flux.

---

## 5. Observability
- **Logging:** EFK (Elasticsearch-Fluentd-Kibana) or Loki.
- **Monitoring:** Prometheus & Grafana.
- **Tracing:** Jaeger or OpenTelemetry.

---

## Summary
These topics aren’t required to get your first Kubernetes workload running.  
Pick them up **only when you feel comfortable** with the basics and intermediate concepts.
