# Prerequisites - Learn Along the Way

Once you’ve got the basics (Linux, Docker, YAML), you’ll naturally bump into concepts while using Kubernetes.  
This section lists those “learn as you go” skills - you don’t need to master them upfront but knowing what they are helps.

---

## 1. Linux Networking Basics
- Check IPs & routes:
  ```bash
  ip addr
  ip route
  ```
- Port usage & processes:
  ```bash
  netstat -tulnp
  ```
- **Why?**  
  Kubernetes deals with Pods, Services, and networking — basic IP/port knowledge helps troubleshoot.

---

## 2. Git Basics
You’ll likely work with YAML manifests stored in Git.

- Clone and work with repos:
  ```bash
  git clone <repo>
  git add <file>
  git commit -m "message"
  git push
  ```
- **Why?**  
  All modern DevOps workflows are Git-based.

---

## 3. kubectl CLI Basics
- **What it is:** Kubernetes command-line tool.
- Most used commands:
  ```bash
  kubectl get pods
  kubectl describe pod <pod-name>
  kubectl logs <pod-name>
  ```
- **Why?**  
  You’ll interact with your cluster mainly through `kubectl`.

---

## 4. Helm (Optional but Handy)
- **What is Helm?**  
  A package manager for Kubernetes.
- Basic usage:
  ```bash
  helm repo add bitnami https://charts.bitnami.com/bitnami
  helm install myapp bitnami/nginx
  ```
- **Why?**  
  Makes deploying complex apps easier.

---

## Summary
You don’t need to learn all of this on day one.  
Just bookmark this page and refer back when these terms pop up while using Kubernetes.
