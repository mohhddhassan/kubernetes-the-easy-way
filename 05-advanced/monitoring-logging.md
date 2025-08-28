# Security in Kubernetes

---

Security is a pretty big topic in k8s, but here are the main areas we need to keep in mind:

## 1. RBAC (Role-Based Access Control)
- Controls **who can do what** inside the cluster.  
- Example: A developer might only get read access to pods, but an admin can create/delete.  
- Always follow the principle of **least privilege**.

## 2. Service Accounts
- Pods don’t run as root user randomly → they run under a **service account**.  
- This account defines what API calls the pod can make inside the cluster.  

## 3. Network Policies
- Think of them like firewall rules for pods.  
- By default, all pods can talk to each other → network policies restrict that.  
- Example: Only allow frontend → backend communication, block everything else.  

## 4. Pod Security
- Avoid running pods as root.  
- Use `securityContext` to enforce rules (readOnly FS, drop Linux capabilities, etc).  
- Newer clusters use **Pod Security Standards (baseline/restricted)**.  

## 5. Secrets & Encryption
- Always keep sensitive data in Secrets, never in plain YAML.  
- Enable **encryption at rest** for Secrets.  

👉 TLDR: Lock things down step by step → users (RBAC), pods (service accounts, securityContext), and traffic (network policies).
