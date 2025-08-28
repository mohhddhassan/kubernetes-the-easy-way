# Helm Basics 🪖 (Optional but super useful)

---

## What is Helm?
- Helm is basically the **package manager for Kubernetes**.  
- Instead of writing long YAML files, we can use Helm charts which are pre-built templates.  
- Think of it like `apt-get` or `npm` but for k8s apps.

## Key Concepts
- **Chart** → A package of YAMLs/templates describing a k8s app.  
- **Release** → A running instance of a chart in your cluster.  
- **Repository** → Where charts are stored (like DockerHub but for Helm).  

## Why Helm?
- No need to copy-paste giant YAMLs.  
- Easy to upgrade, rollback, and manage versions.  
- Helps with reusable templates (same app, different environments).  

## Example
```sh
# Add Helm repo
helm repo add bitnami https://charts.bitnami.com/bitnami

# Install nginx
helm install my-nginx bitnami/nginx

# List releases
helm list

